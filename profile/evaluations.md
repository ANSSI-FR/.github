# Evaluations de sécurité de logiciels open source financées par l'ANSSI

*"Le succès n'est pas final, l'échec n'est pas fatal. C'est le courage de continuer qui compte."* Winston Churchill

<img src="https://www.sgdsn.gouv.fr/files/styles/ds_image_paragraphe/public/files/Notre_Organisation/logo_anssi.png" alt="Logo ANSSI" width="30%">

La version HTML de cette page se trouve [ici](https://anssi-fr.github.io/evaluations.html).


Chaque année, l’ANSSI sélectionne des logiciels open source afin de les soumettre à des audits de sécurité « à façon » 
ou à des évaluations de sécurité conformes au schéma de certification CSPN, avec pour objectifs primordiaux de renforcer
le niveau de cybersécurité de ses bénéficiaires et de soutenir le développement de l’écosystème open source. Ces 
résultats d'évaluation sont mis à profit pour élever la posture de sécurité globale :
- par renforcement de la robustesse du code source et de l’architecture de sécurité des logiciels open source : les 
résultats sont transmis aux éditeurs et aux communautés de développement concernées, potentiellement accompagnés de
recommandations détaillées pour corriger les vulnérabilités identifiées ;  
- par diffusion des bonnes pratiques : les constats réalisés sont susceptibles de nourrir la doctrine technique de l'ANSSI
(p. ex. élaboration ou mise à jour des guides d’installation et d’utilisation destinés en premier lieu aux bénéficiaires
de l'Agence et plus généralement, à l'écosystème numérique).

Ces évaluations de sécurité sont pilotées et accompagnés  par des experts ANSSI et réalisées par des experts des Centres
d’Evaluation de la Sécurité des Technologies de l’Information ([CESTI](https://cyber.gouv.fr/offre-de-service/solutions-certifiees-et-qualifiees/evaluer-les-produits-et-services/centres-evaluation/)). Les résultats des évaluations sont mis à la disposition des développeurs afin de corriger les éventuelles vulnérabilités identifiées. Après une période d’attente raisonnable, dans le cadre d’une procédure de divulgation responsable, l'ANSSI publie les résultats.

Le tableau ci-après liste les travaux de l'ANSSI et donne les pointeurs vers les livrables associés à chaque évaluation.
Ces informations peuvent être utiles à des professionnels de la cybersécurité pour les aider à se faire une idée du niveau 
de sécurité d'un logiciel open source particulier. Elles viennent compléter les recommandations générales de l'ANSSI pour
sélectionner un logiciel open source [[FR](https://messervices.cyber.gouv.fr/documents-guides/anssi_essentiels_selection_logiciel_libre_1.0.pdf),
[EN](https://messervices.cyber.gouv.fr/documents-guides/anssi_back%20to%20basics_select_open_source_software.pdf)].



| Année* | Logiciel | Type d’évaluation | Statut CSPN | Résultats |
| --- | --- | --- | --- | --- |
| 2025 | **Sentry** [[dépôt](https://camelot-os.h2lab.org/)] | CSPN | n.a. | Début de l'évaluation en mars 2026  |
| 2025 | **Shibboleth** [[web](https://www.shibboleth.net/)] | Audit | n.a. | Evaluation en cours  |
| 2025 | **Vault** [[dépôt](https://github.com/hashicorp/vault)] | Audit | n.a. | Evaluation en cours  |
| 2025 | **HAProxy** [[dépôt](https://github.com/haproxy/haproxy)] [[SILL](https://code.gouv.fr/sill/detail?name=HAProxy)] | Audit | n.a. | Aucune vulnérabilité identifiée <br> [Blog-post](https://almond.eu/cybersecurity-insights/publication-of-a-security-audit-report-performed-on-haproxy/) (CESTI [Almond](https://almond.eu/)) <br> [Blog-post](https://www.haproxy.com/blog/haproxy-security-audit-results) ([HAProxy Technologies](https://www.haproxy.com/)) |
| 2025 | **step-ca** [[dépôt](https://github.com/smallstep/certificates)] | Audit | n.a. | [1 vulnérabilité identifiée](https://github.com/smallstep/certificates/security/advisories/GHSA-j7c9-79x7-8hpr)  ([CVE-2025-66406](https://nvd.nist.gov/vuln/detail/CVE-2025-66406)) <br> [Blog-post](https://www.amossys.fr/insights/blog-technique/cve-2025-66406-arbitrary-ssh-certificate-revocation-on-step-ca/) (CESTI [Amossys](https://almond.eu/))|
| 2025 | **MLA** [[dépôt](https://github.com/ANSSI-FR/MLA)] | Audit | n.a. | [Security assessment report](https://github.com/ANSSI-FR/MLA/blob/main/doc/20260130-mla-security-assessment.pdf)  (CESTI [Synacktiv](https://www.synacktiv.com/))  |
| 2025 | **fuzzysully** [[dépôt](https://github.com/ANSSI-FR/fuzzysully)] | n.a. | n.a. | Développement et publication par l'ANSSI d'un fuzzer OPC-UA.   |
| 2024 | **CAS** [[dépôt](https://github.com/apereo/cas)] [[SILL](https://code.gouv.fr/sill/detail?name=Apereo%20CAS)] | Audit | n.a. | 4 vulnérabilités identifiées <br> [Blog-post](https://www.amossys.fr/insights/blog-technique/responsible-disclosure-of-vulnerabilities-found-on-apereo-cas/) (CESTI [Amossys](https://almond.eu/)) |
| 2023 | **KeePassXC** [[dépôt](https://github.com/keepassxreboot/keepassxc)] | CSPN | ✅ [Certificat](https://messervices.cyber.gouv.fr/visas/ANSSI-CSPN-2025-16-rapport.pdf) <br> [Rapport certification](https://messervices.cyber.gouv.fr/visas/ANSSI-CSPN-2025-16-rapport.pdf) |  |
| 2023 | **WireGuard** [[dépôt](https://github.com/wireguard)] | CSPN | ❌ Pas de certificat à l’issue du processus |   |
| 2023 | **Keycloak** [[dépôt](https://github.com/keycloak/keycloak)] [[SILL)](https://code.gouv.fr/sill/detail?name=Keycloak)] | Audit | n.a. |   |
| 2022 | **S2OPC** [[dépôt](https://github.com/monate/s2opc)] | CSPN | ✅ [Certificat](https://messervices.cyber.gouv.fr/visas/ANSSI-CSPN-2023-14-certificat.pdf) <br> [Rapport certification](https://messervices.cyber.gouv.fr/visas/ANSSI-CSPN-2023-14-rapport.pdf) |   |
| 2022 | **OpenSSH** [[dépôt](https://github.com/openssh)] | Audit | n.a. |   |
| 2022 | **nftables** [[web](https://wiki.nftables.org/wiki-nftables/index.php/Main_Page)] | CSPN | ✅ [Certificat](https://messervices.cyber.gouv.fr/visas/ANSSI-CSPN-2024-02-certificat.pdf) <br> [Cible de sécurité](https://messervices.cyber.gouv.fr/visas/ANSSI-CSPN-2024-02-cible.pdf) <br> [Rapport certification](https://messervices.cyber.gouv.fr/visas/ANSSI-CSPN-2024-02-rapport.pdf) |   |
| 2022 | **cert-manager** [[dépôt](https://github.com/cert-manager/cert-manager)] | CSPN | ⚠️ Abandon |   |
| 2021 | **Sudo** [[dépôt](https://github.com/sudo-project/sudo)] | CSPN | ❌ Pas de certificat à l’issue du processus |   |
| 2021 | **Belenios** [[dépôt](https://github.com/glondu/belenios)] | CSPN | ❌ Pas de certificat à l’issue du processus |   |
| 2021 | **Secretin** [[dépôt](https://github.com/secretin/secretin-app)] | CSPN | ❌ Pas de certificat à l’issue du processus |   |
| 2021 | **KeePass** [[SILL](https://code.gouv.fr/sill/detail?name=KeePass)] | CSPN | ❌ Pas de certificat à l’issue du processus |   |
| 2019 | **S20PC** [[dépôt](https://github.com/monate/s2opc)] | CSPN | ❌ Pas de certificat à l’issue du processus |   |
| 2019 | **strongSwan** [[dépôt](https://github.com/strongswan/strongswan)] | CSPN | ❌ Pas de certificat à l’issue du processus |   |
| 2018 | **KeePass 2.5** [[SILL](https://code.gouv.fr/sill/detail?name=KeePass)] | CSPN | ❌ Pas de certificat à l’issue du processus |   |
| 2018 | **E2Guardian** [[dépôt](https://github.com/e2guardian/e2guardian)] | CSPN | ✅ |   |
| 2018 | **Suricata v6.0.8** [[dépôt](https://github.com/OISF/suricata)] | CSPN | ✅[Certificat](https://messervices.cyber.gouv.fr/visas/ANSSI-CSPN-2023-02-certificat.pdf) <br> [Rapport certification](https://messervices.cyber.gouv.fr/visas/ANSSI-CSPN-2023-02-rapport.pdf) |   |
| 2018 | **Ansible** [[dépôt](https://github.com/ansible/ansible)] [[SILL](https://code.gouv.fr/sill/detail?name=Ansible)] | CSPN | ❌ Pas de certificat à l’issue du processus |   |
| 2018 | **Keystone** [[dépôt](https://github.com/openstack/keystone)] | CSPN | ❌ Pas de certificat à l’issue du processus |   |
| 2018 | **Barbican** [[dépôt](https://github.com/openstack/barbican)] | CSPN | ✅ [Certificat](https://messervices.cyber.gouv.fr/visas/ANSSI-CSPN-2022-02-certificat.pdf) <br> [Rapport certification](https://messervices.cyber.gouv.fr/visas/ANSSI-CSPN-2022-02-rapport.pdf) |   |

\* *Année de lancement de l'évaluation de sécurité*
