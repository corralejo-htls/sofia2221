# Sofia — Hotel Content Management Platform (`vikahotel/dashboard`)

![Framework](https://img.shields.io/badge/Symfony-2.7-black)
![Language](https://img.shields.io/badge/PHP-%E2%89%A55.3.9-777BB4)
![ORM](https://img.shields.io/badge/Doctrine%20ORM-2.4-orange)
![Database](https://img.shields.io/badge/MariaDB-10.1.48-blue)
![Status](https://img.shields.io/badge/Stack-EOL%20%E2%80%94%20migration%20required-red)
![Docs](https://img.shields.io/badge/Docs-ES%20%7C%20EN-green)

> **Document produced by technical audit — 2026-07-06.**
> Verified sources: GitHub repository `corralejo-htls/sofia2221` (cloned) and Google Drive folder `Codigo_Base` (read via connector). No information has been assumed; anything unverified is marked `[PENDING]`.

---

## Table of contents

1. [Application overview](#1-application-overview)
2. [Project resource locations](#2-project-resource-locations)
3. [GitHub repository structure](#3-github-repository-structure)
4. [Google Drive `Codigo_Base` folder structure](#4-google-drive-codigo_base-folder-structure)
5. [Source code structure (`repo-sofia`)](#5-source-code-structure-repo-sofia)
6. [Technology stack and versions](#6-technology-stack-and-versions)
7. [Installation and environment setup](#7-installation-and-environment-setup)
8. [Project conventions](#8-project-conventions)
9. [Related documentation package](#9-related-documentation-package)
10. [Pending data to complete](#10-pending-data-to-complete)

---

## 1. Application overview

**Sofia** is a web platform for **hotel content and website management**, built as an administration dashboard on Symfony 2.7. Its core purpose is to run a multi-hotel portal that generates and maintains **accommodation websites on subdomains** (observed pattern: `<hotel>.site-hotel.com`), with a strong focus on **SEO and search-engine indexing**.

> **System designations (confirmed by the owner):** *Sofia*, *Juliette Hotels* and *vikahotel* are **the same system deployed on different servers** (independent instances of the same application). This documentation package uses "Sofia" as the generic name; the `web_imagen/` screenshots correspond to the "Juliette Hotels" instance.

**Confirmed functionality** (verified against the `web_imagen/` screenshots and the code modules):

| Functional module | Evidence |
|---|---|
| Accommodation management (hotel records, editing, listings) | `menu_alojamientos_hotel-list.png`, `menu_alojamiento_ficha_hotel_edit_.png` |
| Tourist destination management | `menu_destination_list.png`, `menu_destinations-edit.png` |
| Companies, affiliations and per-company web configuration | `menu_empresas*.png` |
| Content portal and ads | `menu_portal-de-contenidos.png`, `menu_anuncios_list.png` |
| Sitemaps and redirected domains (technical SEO) | `menu_sitemaps*.png`, `menu_dominios-redireccionados.png` |
| Multi-language translations | `menu_traducciones_*.png`, LexikTranslationBundle |
| Reviews/opinions | `menu_opiniones.png` |
| Queue service (background processing) | `menu_servicio-de-colas_list.png`, `QueueBundle` |
| Analytics | `menu_Analytics.png` |
| Public hotel websites with contact form and gallery | `_ apartment5peaks...`, `_ sonnenalmstuhleck...` screenshots |

**Target audience:** the internal content/SEO administration team of the hotel portal; the generated sites serve end users searching for accommodation.

**Relevant operational context** (from `notes/_Protocolo__.md`): an annual protocol exists to regenerate low-traffic subdomains and resubmit sitemaps to Search Console, executed in autumn (October) with results expected by February.

---

## 2. Project resource locations

| Resource | Location | Contents |
|---|---|---|
| **GitHub** | `https://github.com/corralejo-htls/sofia2221` | Documentation: DB notes, protocol, API manuals, application screenshots |
| **Google Drive (root)** | `Codigo_Base` folder (`.../folders/18BH745TFqFRCEk-VgpE_5HDCsLIC70Z-`) | Main container |
| **Google Drive (code)** | `codigo_repositorio` subfolder (`.../folders/1GHqIfZinkwVJ_dpXNIwFY61A0cxLOnLb`) | Source code, SQL dumps, manuals, analysis |

> ⚠️ Consistency note: the link published in the original GitHub README points directly to the `codigo_repositorio` subfolder, which lives **inside** `Codigo_Base`. Both links are valid and refer to the same hierarchy.

---

## 3. GitHub repository structure

**Public** repository `corralejo-htls/sofia2221`, branch `main`, 18 commits. It holds the project **documentation** (the source code lives in Drive).

```
sofia2221/
├── README.md                        ← original README (link to the code in Drive)
├── notes/                           ← technical & operational documentation
│   ├── SQL__db_0921__.md            ← COMPLETE production DB structure `db_0921`
│   │                                   (structure-only dump, 2,467 lines,
│   │                                   header: MariaDB 10.1.48, host localhost)
│   ├── _Protocolo__.md              ← existing operational protocol (77 lines):
│   │                                   annual subdomain regeneration + sitemaps (SEO)
│   ├── consultas_SQL_.md            ← operational/maintenance SQL queries (202 lines)
│   ├── MANUAL-DE-USO_API-ACTUALIZACIÓN-DE-CONTENIDO.md
│   │                                ← content-update API specification (323 lines)
│   │                                   — TO BE DEVELOPED in future versions
│   └── MANUAL-DE-USO_API-TABLA_.md  ← table API specification (33 lines)
│                                       — TO BE DEVELOPED in future versions
└── web_imagen/                      ← 25 PNG screenshots of the application menus
    ├── menu_Analytics.png
    ├── menu_alojamientos_hotel-list.png
    ├── menu_alojamiento_ficha_hotel_edit_.png
    ├── menu_anuncios_list.png
    ├── menu_configuracion_list.png
    ├── menu_destination_list.png
    ├── menu_destinations-edit.png
    ├── menu_dominios-redireccionados .png
    ├── menu_empresas.png  (+ edit, affiliations, web-configuration…)
    ├── menu_opiniones.png
    ├── menu_portal-de-contenidos.png
    ├── menu_servicio-de-colas_list.png
    ├── menu_sitemaps.png / menu_sitemaps_list.png
    ├── menu_traducciones_.png / menu_traducciones_grid.png
    └── _ apartment5peaks... / _ sonnenalmstuhleck...  ← generated public websites
```

---

## 4. Google Drive `Codigo_Base` folder structure

Verified by direct read (2026-07-06):

```
Codigo_Base/                                  ← shared root folder
└── codigo_repositorio/                       ← code repository & DB material
    ├── repo-sofia/                           ← ★ Application SOURCE CODE
    │   ├── app/                              ← Symfony kernel/config (SF2 layout)
    │   ├── src/                              ← first-party code (bundles) — see section 5
    │   ├── web/                              ← public document root (front controllers, assets)
    │   ├── composer.json                     ← dependency manifest (verified)
    │   ├── composer.lock                     ← exact installed versions (169 KB)
    │   └── .htaccess                         ← Apache rules (under src/; 143 bytes)
    ├── codigo_repositorio__05-2024_.zip      ← code snapshot, May 2024 (52.8 MB)
    ├── juliettehotels.sql                    ← ⚠️ FULL dump WITH DATA (1.85 GB)
    ├── JULIETTE_auditoria_ddl.sql            ← audit DDL (128 KB)
    ├── SQL JULIETTE.txt                      ← SQL notes (9.3 KB)
    ├── _tablas_en_CSV_de la db/              ← DB tables exported as CSV
    ├── imagenes del sistema/                 ← system screenshots
    ├── scrap_otros/                          ← misc. scraping/other material
    ├── analisis_proyecto_.pdf                ← previous project analysis (4.9 MB)
    ├── Manual SISTEMA.xlsx                   ← system manual (247 KB)
    ├── tablas.png                            ← DB table diagram (548 KB)
    └── __MACOSX/                             ← macOS compression residue (ignorable/removable)
```

> 🔒 **Security notice:** `juliettehotels.sql` (1.85 GB) is a dump **containing production data**. Treat it as sensitive information: restricted access and exclusion from any public repository.

---

## 5. Source code structure (`repo-sofia`)

**Symfony 2.7 Standard Edition** project (`app/` + `src/` + `web/`). First-party code is organized into **15 bundles** under the `Application\` namespace (verified in Drive):

```
repo-sofia/src/Application/
├── CoreBundle/        ← application core
├── CommonBundle/      ← shared utilities and components
├── ModelBundle/       ← Doctrine entities / data model (DB db_0921)
├── DashboardBundle/   ← admin panel (the menus in web_imagen/)
├── FrontendBundle/    ← public hotel websites (subdomains *.site-hotel.com)
├── WebBundle/         ← complementary web layer
├── TemplateBundle/    ← templates for the generated sites
├── ApiBundle/         ← REST API (FOSRestBundle + NelmioApiDoc)
├── DataTableBundle/   ← dashboard data tables (listings/grids)
├── QueueBundle/       ← queue service ("servicio de colas" menu)
├── ParserBundle/      ← content parsing/import
├── MigrationBundle/   ← data migrations/processes
├── SafetyBundle/      ← security/protections
├── SupportBundle/     ← support
└── TestBundle/        ← tests
```

> Internal detail of each bundle (controllers, entities, services) is documented in the mind map (**DOC 2**) and in the code audit (**DOC 5**).

---

## 6. Technology stack and versions

**Current** versions, verified against `composer.json` and the `SQL__db_0921__.md` dump header:

| Component | Current version | Support status | Evidence |
|---|---|---|---|
| Framework | **Symfony 2.7** | 🔴 EOL (end of support: May 2019) | `symfony/symfony: 2.7.*` |
| Language | **PHP ≥ 5.3.9** (declared requirement) | 🔴 PHP 5.x EOL since Jan 2019 | `composer.json` — exact production version `[PENDING]` |
| ORM | **Doctrine ORM ^2.4.8** | 🔴 unsupported branch | `composer.json` |
| Database | **MariaDB 10.1.48** | 🔴 EOL (Oct 2020) | `db_0921` dump header |
| Web server | Apache (inferred from `.htaccess`) | `[PENDING]` version | `.htaccess` present |
| OS / hosting | `[PENDING]` | — | no evidence in the repositories |

**Main third-party dependencies** (all Symfony 2 generation; to be replaced during migration):

`friendsofsymfony/user-bundle 2.0@dev` · `friendsofsymfony/rest-bundle ^1.7` · `jms/serializer-bundle ^1.0` · `nelmio/api-doc-bundle @dev` · `nelmio/cors-bundle ^1.4` · `symfony/assetic-bundle ~2.3` · `symfony/swiftmailer-bundle ~2.3` · `doctrine/doctrine-bundle ~1.4` · `gedmo/doctrine-extensions dev-master` · `knplabs/knp-paginator-bundle ^2.5` · `lexik/translation-bundle ~3.1` · `liuggio/excelbundle ^2.0` (PHPExcel) · `google/apiclient 2.0` · `php-imap/php-imap ~2.0` · `willdurand/js-translation-bundle ^2.2` · `willdurand/geocoder-bundle @stable` · `stichoza/google-translate-php ^4.0` · `suncat/mobile-detect-bundle 1.0.*` · `incenteev/composer-parameter-handler ~2.0` · `ircmaxell/password-compat ^1.0` · `twig/extensions ^1.4` · `fusonic/linq @dev` · `boekkooi/jquery-validation-bundle dev-master`

> ⚠️ Several dependencies pinned to `dev-master`/`@dev` are a reproducibility risk; `composer.lock` preserves the exact frozen versions.

**Database `db_0921`:** full schema in `notes/SQL__db_0921__.md` (2,467 lines). **Project rule: the schema IS PRESERVED — no redesign of tables, columns or relationships.** The engine-upgrade protocols are DOC 3 (MariaDB 12) and DOC 4 (PostgreSQL 18).

---

## 7. Installation and environment setup

Standard procedure for a Symfony 2.7 project (**legacy** environment; recommended only for development/staging prior to migration):

**Requirements**
- PHP 5.6 or 7.0/7.1 with the usual stack extensions (`pdo_mysql`, `intl`, `mbstring`, `xml`, `gd`, `imap`, `curl`) — exact compatibility with PHP versions > 5.6 must be validated against `composer.lock` `[PENDING]`
- Composer 1.x (the `sensio/distribution-bundle` scripts are not compatible with Composer 2 without adjustments)
- MariaDB 10.1.x (production parity) — via Docker if a modern OS no longer ships it
- Apache with `mod_rewrite` (`.htaccess` present)

**Steps**
```bash
# 1. Obtain the code (Drive: repo-sofia/ or the 05-2024 ZIP)
# 2. Install dependencies with Composer 1.x
composer install
#    → Incenteev will generate app/config/parameters.yml interactively
# 3. Configure parameters (DB, mailer, secrets) in app/config/parameters.yml
#    ⚠️ NEVER commit this file: it contains credentials
# 4. Load the structure database
mysql -u <user> -p db_0921 < notes/SQL__db_0921__.md   # (extract the SQL from the MD)
# 5. Prepare assets and cache (Symfony 2)
php app/console assets:install web --symlink
php app/console assetic:dump
php app/console cache:clear --env=prod
# 6. Point the Apache VirtualHost to repo-sofia/web/ (document root)
```

**Environment variables/parameters** (Symfony 2.7 pattern — `app/config/parameters.yml`): `database_host`, `database_port`, `database_name` (`db_0921`), `database_user`, `database_password`, `mailer_*`, `secret`. Actual values `[PENDING — credentials are deliberately neither read nor documented, for security]`.

---

## 8. Project conventions

- **Documentation languages:** every document in the package is published as a `*_es.md` / `*_en.md` pair with equivalent content.
- **Untouchable DB schema:** no migration redesigns the schema; only the minimum technical type equivalences required by the target engine (documented in DOC 4).
- **Traceability:** every stated fact has a source (GitHub or Drive); anything unverified is marked `[PENDING: …]` and collected in section 10.
- **Audit findings:** numbered `H-001…` with severity 🔴 Blocking / 🟠 High / 🟡 Medium / 🟢 Minor.
- **Operational SEO cycle:** bulk content/subdomain changes run in autumn (protocol `_Protocolo__.md`); technical migrations must be scheduled around that calendar.

---

## 9. Related documentation package

| Doc | File (ES / EN) | Contents | Status |
|---|---|---|---|
| DOC 1 | `README_es.md` / `README_en.md` | This document | ✅ |
| DOC 2 | `mapa-mental-aplicacion_es.md` / `app-mind-map_en.md` | Mermaid mind map + architecture flow | ⏳ next |
| DOC 3 | `protocolo-actualizacion-mariadb12_es.md` / `mariadb12-upgrade-protocol_en.md` | MariaDB 10.1.48 → 12.x protocol | ⏳ |
| DOC 4 | `protocolo-migracion-postgresql18_es.md` / `postgresql18-migration-protocol_en.md` | PostgreSQL 18 migration protocol | ⏳ |
| DOC 5+ | `auditoria-*_es.md` / `audit-*_en.md` | Audits: code, framework/language, server, SEO, master plan | ⏳ |

---

## 10. Pending data to complete

| # | Pending item | Impact | How to obtain it |
|---|---|---|---|
| P-01 | Exact **production PHP version** | Defines the language upgrade path | `php -v` on the server, or inspection of `composer.lock`/logs |
| P-02 | **Web server** (Apache/Nginx) and version | Server doc and deployment protocol | `apachectl -v` / site HTTP headers |
| P-03 | Production **OS / hosting provider** | MariaDB 12 / PostgreSQL 18 compatibility | hosting panel or `cat /etc/os-release` |
| P-04 | Confirm whether `repo-sofia/` ≡ `codigo_repositorio__05-2024_.zip` (same version) | Source of truth for the code audit | checksum comparison or owner confirmation |
| P-05 | Relationship between DB `db_0921` (GitHub) and `juliettehotels.sql` (Drive, 1.85 GB) — same DB, different date? | Scope of the DB protocols | inspect the large dump's header |
| ~~P-06~~ | ✅ **RESOLVED**: Sofia / Juliette Hotels / vikahotel are the same system on different servers (confirmed by the owner, 2026-07-06) | — | — |

---

*Produced by automated technical audit with source verification. EN version. Companion document: `README_es.md`.*

-----
repositorio code en google drive:
https://drive.google.com/drive/folders/18BH745TFqFRCEk-VgpE_5HDCsLIC70Z-?usp=drive_link
-----
web_imagen : diferentes imagenes del menu la aplicacion actual
notes: notas varias
notes/
SQL__db_0921__.md: estructura database completa (produccion) , la estructura de datos se mantiene (sin rediseño de esquema). 
_Protocolo__.md: protocolo de actualizacion. 
consultas_SQL_.md: consultas varias SQL. 
notes/MANUAL-DE-USO_API-ACTUALIZACIÓN-DE-CONTENIDO.md: API a desarollar en Aplicacion (aplicar en futuras actualizaciones).
notes/MANUAL-DE-USO_API-TABLA_.md: API a desarollar (aplicar en futuras actualizaciones).
-----
Source: GitHub repository corralejo-htls/sofia2221/web_imagen/ (25 PNG images):
Method: every image was opened and visually analyzed (not just inferred from its filename). Analysis date: 2026-07-06.
Cross-cutting finding: the application is branded "Juliette Hotels" the internal translation domain is named sofiahoteles. Confirmed by the owner: Juliette Hotels, Sofia and vikahotel are the same system deployed on different servers. The screenshots confirm the system's two faces: the administration dashboard and the generated public websites on *.site-hotel.com subdomains

-----

*Produced by automated technical audit with source verification. EN version. Companion document: `README_es.md`.*
