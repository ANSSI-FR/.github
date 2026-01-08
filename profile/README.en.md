# ANSSI
<img src="https://www.sgdsn.gouv.fr/files/styles/ds_image_paragraphe/public/files/Notre_Organisation/logo_anssi.png" alt="Texte alternatif" width="30%">

This organization hosts repositories for various open source project developed by [ANSSI](https://cyber.gouv.fr).

*Les francophones peuvent consulter la [version originale](README.md) de ce fichier.*

## Free and open-source software at ANSSI

ANSSI open source strategy is detailed on the
[website](https://cyber.gouv.fr/open-source-lanssi)

## Project categories

The strategy recognizes three categories for the projects maintained by the
agency:

- **doctrinal projects**
  (![badge_catégorie_doctrinal](https://img.shields.io/badge/catégorie-doctrinal-%23e9c7e7))
  sharing doctrinal elements or published alongwhile:
    - technological demonstrators,
    - reference implcementations,
    - source code used to write a scientific paper or generate data (research
      artifacts),
    - content exposing tangible recommandations from the Agency
      ("actionables").
- **internal tools**
  (![badge_catégorie_interne](https://img.shields.io/badge/catégorie-interne-%23d08fce)):
  projects developed for an internal need and published for transparency reason
  or as a will to share resources useful to the cyber ecosystem.
- **external tools**
  (![badge_catégorie_externe](https://img.shields.io/badge/catégorie-externe-%23b556b6)):
  tools shared with beneficiaries and partners (like CERTS), available directly
  or through services provided by the agency.

## Openness level

The strategy also classifies projects using an "openness level" based on the
[classification](https://documentation.ouvert.numerique.gouv.fr/les-parcours-de-documentation/ouvrir-un-projet-num%C3%A9rique/#niveau-ouverture)
done by DINUM (French government OSPO)

- 📘 Level A - **contributive**
  ([![badge_ouverture_A](https://img.shields.io/badge/code.gouv.fr-contributif-blue)](https://documentation.ouvert.numerique.gouv.fr/les-parcours-de-documentation/ouvrir-un-projet-num%C3%A9rique/#niveau-ouverture)):
  source code is published, external contributions are actively seeked and
  handled.
- 📗 Level B - **open**
  ([![badge_ouverture_B](https://img.shields.io/badge/code.gouv.fr-ouvert-green)](https://documentation.ouvert.numerique.gouv.fr/les-parcours-de-documentation/ouvrir-un-projet-num%C3%A9rique/#niveau-ouverture)):
  source code is published, external contributions are handled but not actively
  seeked.
- 📙 Level C - **published**
  ([![badge_ouverture_C](https://img.shields.io/badge/code.gouv.fr-publié-orange)](https://documentation.ouvert.numerique.gouv.fr/les-parcours-de-documentation/ouvrir-un-projet-num%C3%A9rique/#niveau-ouverture)):
  source code is published but external contributions aren't treated.

Doctrinal projects and internal tools are usually at level C while external
tools are at level B. Each project managers can elaborate (in a
`CONTRIBUTING.md` document) on the expectations this project contributors
should have.

## ANSSI repositories

While most ANSSI repositories are hosted in the
[ANSSI-FR](https://github.com/ANSSI-FR) organization, some of them are hosted
in other places (grouped by topic, or for collaboration with other entities):

- [DFIR-ORC](https://dfir-orc.github.io/) ([Github
  organization](https://github.com/dfir-orc/)) is a set of digital forensics
  tools, especially used by the CERT when investigating incidents.
- [FCSC-FR](https://github.com/FCSC-FR) hosts repositories used for the _French
  CyberSecurity Challenge_ CTF competition ([2024
  edition](https://cyber.gouv.fr/france-cybersecurity-challenge-2024)),
  including the [Hackropole](https://hackropole.fr) archive website)

The [innovation lab](https://lab.cyber.gouv.fr/) also develops online services
under the [BetaGouv](https://beta.gouv.fr/) initiative. Those projects are
hosted in the [BetaGouv](https://github.com/betagouv) organization:

- [Mon Service Sécurisé](https://github.com/betagouv/mon-service-securise)
- [Mes Services Cyber](https://github.com/betagouv/anssi-portail)
- [Mon Aide Cyber](https://github.com/betagouv/mon-aide-cyber)
- [Mon Espace NIS 2](https://github.com/betagouv/anssi-nis2)
- [Mes Questions Cyber](https://github.com/betagouv/anssi-recommandations-cyber/)
- [Demain Spécialiste Cyber](https://github.com/betagouv/anssi-demain-specialiste-cyber)

## Contact

Contact policy depends on each project and can be explicited in the `README`,
`CONTRIBUTING`, `SECURITY` or `CONTACT` file in each repository. It is also
usually possible to open issues or merge requests, each project beeing free to
handle them as they see fit (and explained in the `CONTRIBUTING` file).

The ANSSI open source program office can be reached using the
[opensource@ssi.gouv.fr](mailto:opensource@ssi.gouv.fr) mail address but no
support will be provided.

For any other request, readers can use the
[Contact](https://cyber.gouv.fr/contact-acces/contact/) page on ANSSI website.

In case of cyber incident, please contact [CERT-FR](https://cyber.gouv.fr/en-cas-dincident).
 
## Archived project

A number of older projects aren't maintained anymore but are available for reference:

- archived repository [list](https://github.com/orgs/ANSSI-FR/repositories?q=archived%3Atrue)
- [Wookey](https://wookey-project.github.io/) [Github
  organization](https://github.com/wookey-project))
- [LEIA](https://github.com/cw-leia) (Lab Embedded ISO7816 Analyzer A Custom
  Smartcard Reader for the ChipWhisperer)
- [CLIP OS](https://clip-os.org/fr/) ([Github
  organization](https://github.com/clipos) and
  [archives](https://github.com/clipos-archive)) was a Linux-based hardened
  operating system targeting multi-level environments.
