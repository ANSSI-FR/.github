# ANSSI
<img src="https://www.sgdsn.gouv.fr/files/styles/ds_image_paragraphe/public/files/Notre_Organisation/logo_anssi.png" alt="ANSSI" width="30%">

Cet espace comprend les dépôts de différents projets open source maintenus par
l'[ANSSI](https://cyber.gouv.fr).

*English readers can check the [localized](README.en.md) version of this README.*

## L'open source à l'ANSSI

La stratégie open source de l'ANSSI est détaillée sur son [site
internet](https://cyber.gouv.fr/open-source-lanssi)

## Actualités

### 17/03/2026 : Publication d'outils d'aide au durcissement de configuration Linux

L'ANSSI a
publié [actionnable-linux](https://github.com/ansSI-FR/actionnable-linux), un
rôle Ansible déclinant les recommandations du [guide de durcissement
Linux](https://cyber.gouv.fr/sites/default/files/document/linux_configuration-en-v2.pdf).

### 20/02/2026 : Publication d'un rapport d'évaluation du produit MLA

[Publication](https://github.com/ANSSI-FR/MLA/blob/main/doc/20260130-mla-security-assessment.pdf) 
d'un rapport technique d'évaluation de la sécurité du produit 
[Multi Layer Archive](https://github.com/ANSSI-FR/MLA) (MLA) suite à une analyse conduite par
le CESTI [Synacktiv](https://www.synacktiv.com/). *--> Plus d'informations sur les [évaluations de 
sécurité](https://github.com/fb-anssi/.github-anssi/blob/main/profile/evaluations.md) financées par l'ANSSI.*

### 18/02/2026 : Publication de la bibliographie ANSSI

[Publication](https://github.com/ANSSI-FR/bibliotex) de la bibliographie des
publications de l'ANSSI au format BibTeX. Cette bibliographie contient les
références vers les guides techniques, recommandations, référentiels de
qualifications, instructions (inter)ministérielles, etc., publiées sur le [site
institutionnel](https://cyber.gouv.fr), ainsi que les états de la menace et
rapports d' incidents publiés sur le site du
[CERT-FR](https://cert.ssi.gouv.fr).

## Types de projets

La stratégie identifie trois catégories de projets publiés sur les dépôts de
code de l'ANSSI :

- les projets doctrinaux
(![badge_catégorie_doctrinal](https://img.shields.io/badge/catégorie-doctrinal-%23e9c7e7))
diffusant des éléments de doctrine de l'Agence ou en accompagnant la
publication :
	- démonstrateur technologique,
	- implémentation de référence,
	- code source ayant servi à réaliser un article scientifique ou à générer des
données (artefacts de recherche),
	- contenu illustrant concrètement des recommandations de l'Agence
(« actionnables »)
- les outils internes
(![badge_catégorie_interne](https://img.shields.io/badge/catégorie-interne-%23d08fce)) :
projets développés pour un besoin interne de l'ANSSI, publiés pour des raison
de transparence ou par volonté de partager des ressources utiles à
l'écosystème.
- les outils externes
(![badge_catégorie_externe](https://img.shields.io/badge/catégorie-externe-%23b556b6) :
outils mis à disposition des bénéficiaires ou des partenaires de l'ANSSI (comme
les CERT), accessibles directement ou à travers des services fournis pas
l'Agence.

## Niveau d'ouverture

Le document de stratégie catégorise aussi les projets suivant leur « niveau
d'ouverture » sur la base de la
[classification](https://documentation.ouvert.numerique.gouv.fr/les-parcours-de-documentation/ouvrir-un-projet-num%C3%A9rique/#niveau-ouverture)
élaborée par la DINUM :

- 📘 Niveau A - contributif
  ([![badge_ouverture_A](https://img.shields.io/badge/code.gouv.fr-contributif-blue)](https://documentation.ouvert.numerique.gouv.fr/les-parcours-de-documentation/ouvrir-un-projet-num%C3%A9rique/#niveau-ouverture)) :
  le code source est publié, les contributions extérieures sont activement
  recherchées et traitées.
- 📗 Niveau B - ouvert
  ([![badge_ouverture_B](https://img.shields.io/badge/code.gouv.fr-ouvert-green)](https://documentation.ouvert.numerique.gouv.fr/les-parcours-de-documentation/ouvrir-un-projet-num%C3%A9rique/#niveau-ouverture)) :
  le code source est publié, les contributions extérieures sont traitées mais
  non activement recherchées.
- 📙 Niveau C - publié
  ([![badge_ouverture_C](https://img.shields.io/badge/code.gouv.fr-publié-orange)](https://documentation.ouvert.numerique.gouv.fr/les-parcours-de-documentation/ouvrir-un-projet-num%C3%A9rique/#niveau-ouverture)) :
  le code source est publié mais les contributions extérieures ne sont pas
  traitées.

Les projets doctrinaux et les outils internes sont habituellement au niveau C
tandis que les outils externes sont habituellement au niveau B, avec un focus
particulier sur les contributions ayant trait à la sécurité. Chaque projet peut
préciser (par exemple dans un document `CONTRIBUTING`) les attentes que les
contributeurs éventuels peuvent avoir.

## Dépôts de l'ANSSI

Si la plupart des dépôts de l'ANSSI sont hébergés dans l'organisation
[ANSSI-FR](https://github.com/ANSSI-FR), un certain nombre sont hébergés dans
d'autres organisations (regroupement par thématiques, collaborations avec
d'autres entités, etc.)

- [DFIR-ORC](https://dfir-orc.github.io/) ([organisation
  Github](https://github.com/dfir-orc/)) est un ensemble d'outils de recherche
  de compromission, utilisés en particulier par la sous-direction des
  Opérations lors de traitement d'incidents cyber.
- [FCSC-FR](https://github.com/FCSC-FR) regroupe les dépôts liés à
  l'organisation de la compétition French CyberSecurity Challenge ([édition
  2024](https://cyber.gouv.fr/france-cybersecurity-challenge-2024)), y compris
  le site d'archives [Hackropole](https://hackropole.fr).

Le [laboratoire d'innovation](https://lab.cyber.gouv.fr) de l'ANSSI développe
des services en lien avec la DINUM, en particulier dans le cadre de
l'initiative [BetaGouv](https://beta.gouv.fr) d'incubation de services
numériques. Ces services sont hébergés dans l'organisation Github
[BetaGouv](https://github.com/betagouv):

- [Mon Service Sécurisé](https://github.com/betagouv/mon-service-securise)
- [Mes Services Cyber](https://github.com/betagouv/anssi-portail)
- [Mon Aide Cyber](https://github.com/betagouv/mon-aide-cyber)
- [Mon Espace NIS 2](https://github.com/betagouv/anssi-nis2)
- [Mes Questions Cyber](https://github.com/betagouv/anssi-recommandations-cyber/)
- [Demain Spécialiste Cyber](https://github.com/betagouv/anssi-demain-specialiste-cyber)

## Evaluations de sécurité de logiciels open source

L’ANSSI mène depuis 2017 des évaluations de sécurité de logiciels open source. Ces 
évaluations peuvent prendre deux formes. Soit soumettre un logiciel open source au 
processus devant mener à l’obtention de la [Certification de Sécurité de Premier Niveau](https://cyber.gouv.fr/offre-de-service/solutions-certifiees-et-qualifiees/comprendre-levaluation-de-securite/certification-de-produits/presentation-certification-cspn/)
(CSPN), schéma français faisant partie de la famille des Visas de sécurité de l’ANSSI.
Soit des audits « à façon » qui ne donnent pas lieu à la délivrance d’un Visa de sécurité
mais dont les résultats ont pour vocation de donner un aperçu de la robustesse d’un logiciel
open source aux professionnels de la cybersécurité pour les aider concrètement dans leurs
activités opérationnelles (dossier d’homologation, analyse de risque…).

[Liste des évaluations de sécurité de logiciels open source financées par l'ANSSI](https://anssi-fr.github.io/evaluations.html)

## Contact

La politique de contact des mainteneurs dépend de chaque projet. Celle-ci
peut-être explicitée dans les fichiers `README`, `CONTRIBUTING`, `SECURITY` ou
éventuellement `CONTACT` de chaque dépôt. Il est aussi possible d'ouvrir des
*issues* ou des *pull requests* mais chaque projet est libre de les prendre en
compte ou non (comme explicité dans le document `CONTRIBUTING`).

Il est possible de contacter l'équipe en charge de l'open-source à l'ANSSI au
travers de l'adresse [opensource@ssi.gouv.fr](mailto:opensource@ssi.gouv.fr)
mais aucun support ne sera fourni au travers de ce moyen de contact.

Pour tout autre demande, le lecteur est invité à se rendre sur la page
« [Contacts](https://cyber.gouv.fr/contact-acces/contact/) » du site de
l'ANSSI.

En cas d'incident cyber, vous pouvez contacter le
[CERT-FR](https://cyber.gouv.fr/en-cas-dincident).

## Projets archivés

L'ANSSI a publié par le passé un certain nombre de projets qui ne sont plus
activement maintenus mais qui sont toujours disponibles à des fins de
références et inspiration.

On peut trouver en particulier:

- la [liste](https://github.com/orgs/ANSSI-FR/repositories?q=archived%3Atrue)
  des projets archivés de l'organisation ANSSI-FR
- [Wookey](https://wookey-project.github.io/) ([organisation
  Github](https://github.com/wookey-project))
- [LEIA](https://github.com/cw-leia) (Lab Embedded ISO7816 Analyzer A Custom
  Smartcard Reader for the ChipWhisperer)
- [CLIP OS](https://clip-os.org/fr/) ([organisation
  Github](https://github.com/clipos) et ses
  [archives](https://github.com/clipos-archive)) était un système
  d'exploitation durci sur base Linux visant des environnements multiniveaux
  (cohabitation d'environnement de différents niveaux de sensibilité)
