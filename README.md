Deutsch | [English](README.en.md) | [Français](README.fr.md)

# PDF Accessibility

[![Python gates](https://github.com/street1983nk/nextcloud-pdf-accessibility/actions/workflows/python.yml/badge.svg)](https://github.com/street1983nk/nextcloud-pdf-accessibility/actions/workflows/python.yml)
[![Security scans](https://github.com/street1983nk/nextcloud-pdf-accessibility/actions/workflows/security.yml/badge.svg)](https://github.com/street1983nk/nextcloud-pdf-accessibility/actions/workflows/security.yml)
[![Nextcloud App Store](https://img.shields.io/badge/App_Store-pdf__accessibility-0082c9)](https://apps.nextcloud.com/apps/pdf_accessibility)
[![Lizenz](https://img.shields.io/badge/Lizenz-AGPL--3.0--or--later-blue)](LICENSE)

PDF Accessibility prüft PDF-Dateien in Nextcloud auf Barrierefreiheit nach PDF/UA und zeigt verständlich, was fehlt und wie es sich beheben lässt. Die Prüfung läuft lokal auf dem eigenen Server.

**Status:** in Entwicklung, noch nicht im App Store.

## Was PDF Accessibility kann

- Prüfung nach PDF/UA-1 mit veraPDF
- Prüfbericht auf Deutsch, Englisch und Französisch, mit Hinweisen zur Behebung
- Läuft komplett in Ihrer eigenen Instanz, keine Telemetrie
- Verändert nie Ihre Dateien

## Anforderungen

- Nextcloud 33 bis 35 mit AppAPI und einem eingerichteten Deploy-Daemon (HaRP empfohlen)
- CPU: amd64 oder arm64

## Installation

Im App Store unter External Apps die App PDF Accessibility installieren. Die
Einstellungen stehen danach unter Verwaltungseinstellungen, Weitere
Einstellungen.

## Architektur

PDF Accessibility ist eine External App: ein Python-Container (FastAPI), den AppAPI
über den Deploy-Daemon startet und nur über AppAPI/HaRP erreicht. Jede Anfrage
an den Container trägt die Signatur von AppAPI; ohne sie antwortet er mit 401.

## Datenschutz

Alles läuft lokal im Container, nichts verlässt den Server.
Die App speichert nur ihre Einstellungen und die Prüfberichte, kein Dokument verlässt den Server.

## Lizenz

AGPL-3.0-or-later. Siehe [LICENSE](LICENSE).
