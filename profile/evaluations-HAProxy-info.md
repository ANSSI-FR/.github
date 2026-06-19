## L’ANSSI apporte un complément d’information à la section *7.2 ACL filtering* de l’audit du produit HAProxy commandité en 2025 par l’ANSSI à la société Almond

> **7.2 ACL filtering** (p. 19 du [Technical audit report](https://almond.eu/wp-content/uploads/PUBLIC-TAR-HAProxy-1.00-Almond.pdf))
>
> Tests for the path filter have revealed what the evaluators first identified as a vulnerability. The path filter can be bypassed since it is based only on strings and does not try to resolve the real targeted path. Meaning that even if a page (e.g. /login) is protected, it is still accessible by encoding characters in the request (e.g. /log%69n).
>
> Exchanges with the developer revealed that they have been aware of this for a long time. The reason this has not been fixed is for compatibility issues with customers and web servers.

---

L’audit du produit HAProxy a mis en évidence **des limites dans l’utilisation des mécanismes de filtrage des URL qui s'appuient sur des listes de contrôle d’accès (ACL)**. En particulier, ces mécanismes peuvent être contournés en raison de différences de normalisation des requêtes HTTP et de techniques d’évasion telles que l’encodage, les variations de syntaxe ou encore les manipulations de chemins.
Ces limitations ne constituent pas une vulnérabilité propre à HAProxy, mais résultent du détournement d'un composant de répartition de charge pour implémenter un mécanisme de sécurité applicative. En effet, HAProxy n’a pas vocation à fournir des fonctions avancées de détection d’attaques applicatives et ne garantit pas une interprétation normalisée des requêtes équivalente à celle des applications en aval.
En conséquence, il est recommandé de **renforcer ce filtrage applicatif** ou **de mettre en oeuvre un pare-feu applicatif**.

### Renforcer le filtrage applicatif

De façon générale, il est nécessaire de garantir une cohérence stricte entre tous les composants de la chaîne de traitement (reverse proxy, WAF, serveur web, application, etc.) quant à l’interprétation des données non maîtrisées. À titre d’exemple, une URL telle que `/log%69n` doit être normalisée et interprétée de manière identique par tous les éléments intermédiaires, sans quoi des divergences de traitement peuvent introduire des possibilités de contournement. Dans le cas spécifique de HAProxy, l'utilisation de la directive `http-request normalize-uri` permet de normaliser les URI selon une représentation canonique avant l’application des règles de filtrage[^1]. L’usage de ce mécanisme permet de réduire significativement (pas totalement) les ambiguïtés liées aux encodages et aux variations syntaxiques, sous réserve d’une configuration cohérente avec les autres composants de l’architecture.


On notera toutefois que les mécanismes de filtrage au niveau d’un serveur mandataire inverse présentent des limitations :
1. Les mécanismes de filtrage basés sur des **listes de blocage (*blocklist*)** sont **intrinsèquement fragiles**, car ils reposent sur une énumération exhaustive des cas à bloquer. Ils sont particulièrement sensibles aux techniques de contournement liées aux différences de normalisation des requêtes HTTP (p. ex. encodage URL, double encodage, variations de syntaxe, manipulation de chemins, etc.).
1. Les approches par **liste d’autorisation (*allowlist*)** sont plus robustes en théorie, **mais restent complexes à mettre en œuvre correctement**, surtout dans un contexte applicatif riche. Elles nécessitent une parfaite maîtrise des flux légitimes et peuvent être contournées en cas d’**incohérences de normalisation des requêtes entre les différents composants de la chaîne** (*reverse proxy*, serveur Web, application).


### Mettre en oeuvre un pare-feu applicatif (*Web Application Firewall* ou WAF)

Dans une logique de **défense en profondeur**, il est recommandé de **ne pas faire reposer la sécurité sur un seul composant ou une seule couche**. La séparation des responsabilités (p. ex. entre les fonctions de répartition de charge et de filtrage applicatif) peut contribuer à limiter l’impact d’un contournement ou d’une compromission. Dans ce contexte, l’ajout d’un pare-feu applicatif peut améliorer la détection de certaines attaques génériques (p. ex. *path traversal*, injections, contournements d’encodage), mais il est nécessaire de garder en tête qu'il demeure certaines limitations (p. ex. pas de protection contre les failles de logique métier ni contre l’exploitation de comptes légitimes compromis).

---

## Cas des interfaces d'administration


Les interfaces d'administration exposent généralement des fonctionnalités à privilèges élevés et sont des cibles fréquentes pour les attaquants. Leur identification et leur sécurisation font d’ailleurs l’objet de recommandations spécifiques, notamment dans l’*OWASP Web Security Testing Guide* (WSTG-CONF-05) [^2]. L’utilisation de HAProxy pour réaliser un filtrage de sécurité critique, notamment pour restreindre l’accès à ces interfaces sensibles via des règles portant sur les chemins d’URL (p. ex. blocage de /admin) peut **s'avérer insuffisante et exposer à des risques de contournement**.
Une approche plus mature consiste à isoler les interfaces d'administration. Plusieurs approches complémentaires sont envisageables :
- **Une isolation logique**, où l’interface d’administration est intégrée à l’application mais protégée par des mécanismes de sécurité renforcés : authentification forte [^3], contrôles d’accès stricts (RBAC ou ABAC), journalisation des actions [^4], supervision des activités suspectes [^5], etc.  
- **Une isolation physique ou par l’infrastructure**, reposant sur une séparation des composants (serveurs, réseaux…) et un accès restreint à l’interface d’administration. Cette approche peut inclure l’utilisation de réseaux dédiés, de bastions d’administration ou de mécanismes de filtrage d’adresses IP, conformément notamment aux recommandations de l’ANSSI [^6].

Un serveur mandataire inverse, bien qu’il puisse contribuer à la sécurité globale (contrôle d’accès, terminaison TLS, authentification déportée), **ne constitue pas à lui seul un mécanisme de protection suffisant pour sécuriser une interface d’administration exposée**.

---
[^1]: Attention : l’option `http-request normalize-uri` est une directive expérimentale (pour l'utiliser, il est nécessaire d'ajouter l'option `expose-experimental-directives` dans la section `global`du fichier de configuration). Il convient de maîtriser et tester cette option avant sa mise en oeuvre au sein d'un système d'information en production.
[^2]: [WSTG - v4.2 | OWASP Foundation](https://owasp.org/www-project-web-security-testing-guide/)
[^3]: [Recommandations relatives à l’authentification multifacteur et aux mots de passe | MesServicesCyber](https://messervices.cyber.gouv.fr/guides/recommandations-relatives-lauthentification-multifacteur-et-aux-mots-de-passe)
[^4]: [Recommandations de sécurité pour l’architecture d’un système de journalisation | MesServicesCyber](https://messervices.cyber.gouv.fr/guides/recommandations-de-securite-pour-larchitecture-dun-systeme-de-journalisation)
[^5]: [Les clés de décision | MesServicesCyber](https://messervices.cyber.gouv.fr/guides/la-supervision-de-securite-les-cles-de-decision) et [Piloter un projet de supervision | MesServicesCyber](https://messervices.cyber.gouv.fr/guides/la-supervision-de-securite-piloter-un-projet-de-supervision)
[^6]: [Recommandations relatives à l’administration sécurisée des SI | MesServicesCyber](https://messervices.cyber.gouv.fr/guides/recommandations-relatives-ladministration-securisee-des-si)
