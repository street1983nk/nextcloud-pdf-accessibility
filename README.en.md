[Deutsch](README.md) | English | [Français](README.fr.md)

# PDF Accessibility

[![Python gates](https://github.com/street1983nk/nextcloud-pdf-accessibility/actions/workflows/python.yml/badge.svg)](https://github.com/street1983nk/nextcloud-pdf-accessibility/actions/workflows/python.yml)
[![Security scans](https://github.com/street1983nk/nextcloud-pdf-accessibility/actions/workflows/security.yml/badge.svg)](https://github.com/street1983nk/nextcloud-pdf-accessibility/actions/workflows/security.yml)
[![Nextcloud App Store](https://img.shields.io/badge/App_Store-pdf__accessibility-0082c9)](https://apps.nextcloud.com/apps/pdf_accessibility)
[![License](https://img.shields.io/badge/License-AGPL--3.0--or--later-blue)](LICENSE)

PDF Accessibility checks PDF files in Nextcloud for accessibility according to PDF/UA and explains in plain words what is missing and how to fix it. The check runs locally on your own server.

**Status:** in development, not yet in the App Store.

## What PDF Accessibility does

- Check against PDF/UA-1 with veraPDF
- Report in German, English and French, with hints on how to fix each finding
- Runs entirely inside your own instance, no telemetry
- Never modifies your files

## Requirements

- Nextcloud 33 to 35 with AppAPI and a configured deploy daemon (HaRP recommended)
- CPU: amd64 or arm64

## Installation

Install PDF Accessibility from the External Apps section of the App Store. Its
settings are under Administration settings, Additional settings.

## Architecture

PDF Accessibility is an External App: a Python container (FastAPI) that AppAPI
starts through the deploy daemon and reaches only through AppAPI/HaRP. Every
request to the container carries the AppAPI signature; without it the answer
is 401.

## Privacy

Everything runs locally in the container, nothing leaves your server.
The app only stores its settings and the check reports; no document leaves the server.

## License

AGPL-3.0-or-later. See [LICENSE](LICENSE).
