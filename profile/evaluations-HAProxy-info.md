## L’ANSSI apporte un complément d’information à la section *7.2 ACL filtering* de l’audit du produit HAProxy commandité en 2025 par l’ANSSI à la société Almond

> **7.2 ACL filtering** (p. 19 du [Technical audit report](https://almond.eu/wp-content/uploads/PUBLIC-TAR-HAProxy-1.00-Almond.pdf))
>
> Tests for the path filter have revealed what the evaluators first identified as a vulnerability. The path filter can be bypassed since it is based only on strings and does not try to resolve the real targeted path. Meaning that even if a page (e.g. /login) is protected, it is still accessible by encoding characters in the request (e.g. /log%69n).
>
> Exchanges with the developer revealed that they have been aware of this for a long time. The reason this has not been fixed is for compatibility issues with customers and web servers.

---

Les interfaces d’administration des applications Web constituent une augmentation significative de la surface d’attaque et doivent, à ce titre, faire l’objet d’une attention particulière **dès la phase de conception**. Elles exposent généralement des fonctionnalités à privilèges élevés et sont des cibles privilégiées pour les attaquants. Leur identification et leur sécurisation font d’ailleurs l’objet de recommandations spécifiques, notamment dans l’*OWASP Web Security Testing Guide* (WSTG-CONF-05) [^1].

La question de isolation des interfaces d'administration vis-à-vis du reste de l’application doit être **traitée par défaut** (*security by design*). Cette isolation peut être mise en œuvre selon plusieurs approches complémentaires :

- **Une isolation logique**, où l’interface d’administration est intégrée à l’application mais protégée par des mécanismes de sécurité renforcés : authentification forte [^2], contrôles d’accès stricts (RBAC ou ABAC), journalisation des actions [^3], supervision des activités suspectes [^4], etc.  
- **Une isolation physique ou par l’infrastructure**, reposant sur une séparation des composants (serveurs, réseaux…) et un accès restreint à l’interface d’administration. Cette approche peut inclure l’utilisation de réseaux dédiés, de bastions d’administration ou de mécanismes de filtrage d’adresses IP, conformément notamment aux recommandations de l’ANSSI [^5].

---

Lorsque ces interfaces n’ont pas été correctement isolées dès la conception, il peut être tentant de s’appuyer sur des mécanismes de filtrage au niveau d’un serveur mandataire inverse (*reverse proxy*) pour en restreindre l’accès (p. ex. en bloquant certains chemins d’URL tels que `/admin`). Ce type d’approche présente toutefois des limites importantes.

Les mécanismes de filtrage basés sur des **listes de blocage (*blocklist*)** sont **intrinsèquement fragiles**, car ils reposent sur une énumération exhaustive des cas à bloquer. Ils sont particulièrement sensibles aux techniques de contournement liées aux différences de normalisation des requêtes HTTP (p. ex. encodage URL, double encodage, variations de syntaxe, manipulation de chemins, etc.).

Les approches par **liste d’autorisation (*allowlist*)** sont plus robustes en théorie, **mais restent complexes à mettre en œuvre correctement**, surtout dans un contexte applicatif riche. Elles nécessitent une parfaite maîtrise des flux légitimes et peuvent être contournées en cas d’**incohérences de normalisation des requêtes entre les différents composants de la chaîne** (*reverse proxy*, serveur Web, application).

---

Un serveur mandataire inverse, bien qu’il puisse contribuer à la sécurité globale (contrôle d’accès, terminaison TLS, authentification déportée), **ne constitue pas à lui seul un mécanisme de protection suffisant pour sécuriser une interface d’administration exposée**.

L’ajout d’un pare-feu applicatif (*WAF*) permet d’améliorer la détection de certaines attaques génériques (p. ex. *path traversal*, injections, contournements d’encodage), mais ne protège pas contre les failles de logique métier ni contre l’exploitation de comptes légitimes compromis.

Dans une logique de **défense en profondeur**, il est recommandé de **ne pas faire reposer la sécurité sur un seul composant ou une seule couche**. La séparation des responsabilités (p. ex. entre les fonctions de répartition de charge et de filtrage applicatif) peut contribuer à limiter l’impact d’un contournement ou d’une compromission. Toutefois, cette séparation doit être adaptée au contexte technique et aux contraintes opérationnelles, notamment dans des architectures modernes distribuées (p. ex. cloud, microservices). La **mutualisation** (hébergement de plusieurs fonctions dans le même composant ou processus - p. ex. *reverse proxy* et *WAF*) devient un problème quand elle casse l’**isolation**, c’est-à-dire la capacité à garantir qu’une fonction ne peut pas compromettre ou influencer une autre de manière non prévue.

---

## Synthèse

La sécurisation des interfaces d’administration doit prioritairement reposer sur :

- leur **non-exposition directe** ;
- une **authentification robuste** ;
- un **contrôle d’accès fort** ;
- une **segmentation réseau adaptée**.

Les mécanismes de filtrage (*reverse proxy*, *WAF*) doivent être considérés comme des **mesures complémentaires** et non comme des solutions principales.


[^1]: [WSTG - v4.2 | OWASP Foundation](https://owasp.org/www-project-web-security-testing-guide/)
[^2]: [Recommandations relatives à l’authentification multifacteur et aux mots de passe | MesServicesCyber](https://messervices.cyber.gouv.fr/guides/recommandations-relatives-lauthentification-multifacteur-et-aux-mots-de-passe)
[^3]: [Recommandations de sécurité pour l’architecture d’un système de journalisation | MesServicesCyber](https://messervices.cyber.gouv.fr/guides/recommandations-de-securite-pour-larchitecture-dun-systeme-de-journalisation)
[^4]: [Les clés de décision | MesServicesCyber](https://messervices.cyber.gouv.fr/guides/la-supervision-de-securite-les-cles-de-decision) et [Piloter un projet de supervision | MesServicesCyber](https://messervices.cyber.gouv.fr/guides/la-supervision-de-securite-piloter-un-projet-de-supervision)
[^5]: [Recommandations relatives à l’administration sécurisée des SI | MesServicesCyber](https://messervices.cyber.gouv.fr/guides/recommandations-relatives-ladministration-securisee-des-si)
