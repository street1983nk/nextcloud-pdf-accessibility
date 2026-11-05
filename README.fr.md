[Deutsch](README.md) | [English](README.en.md) | Français

# PDF Accessibility

[![Python gates](https://github.com/street1983nk/nextcloud-pdf-accessibility/actions/workflows/python.yml/badge.svg)](https://github.com/street1983nk/nextcloud-pdf-accessibility/actions/workflows/python.yml)
[![Security scans](https://github.com/street1983nk/nextcloud-pdf-accessibility/actions/workflows/security.yml/badge.svg)](https://github.com/street1983nk/nextcloud-pdf-accessibility/actions/workflows/security.yml)
[![Nextcloud App Store](https://img.shields.io/badge/App_Store-pdf__accessibility-0082c9)](https://apps.nextcloud.com/apps/pdf_accessibility)
[![Licence](https://img.shields.io/badge/Licence-AGPL--3.0--or--later-blue)](LICENSE)

PDF Accessibility vérifie l'accessibilité des fichiers PDF de Nextcloud selon PDF/UA et explique clairement ce qui manque et comment le corriger. La vérification fonctionne localement sur votre propre serveur.

**Statut :** en développement, pas encore dans l'App Store.

## Ce que fait PDF Accessibility

- Vérification selon PDF/UA-1 avec veraPDF
- Rapport en allemand, en anglais et en français, avec des conseils de correction
- Fonctionne entièrement dans votre propre instance, aucune télémétrie
- Ne modifie jamais vos fichiers

## Prérequis

- Nextcloud 33 à 35 avec AppAPI et un démon de déploiement configuré (HaRP recommandé)
- CPU : amd64 ou arm64

## Installation

Installer PDF Accessibility depuis la section External Apps de l'App Store. Les
réglages se trouvent ensuite dans Paramètres d'administration, Paramètres
supplémentaires.

## Architecture

PDF Accessibility est une External App : un conteneur Python (FastAPI) qu'AppAPI
démarre via le démon de déploiement et ne joint que par AppAPI/HaRP. Chaque
requête vers le conteneur porte la signature d'AppAPI ; sans elle, la réponse
est 401.

## Confidentialité

Tout fonctionne localement dans le conteneur, rien ne quitte votre serveur.
L'application n'enregistre que ses réglages et les rapports de vérification ; aucun document ne quitte le serveur.

## Licence

AGPL-3.0-or-later. Voir [LICENSE](LICENSE).
