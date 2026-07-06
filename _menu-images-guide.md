# Content Guide — `web_imagen/` (application screenshots)

> **Source:** GitHub repository `corralejo-htls/sofia2221`, folder `web_imagen/` (25 PNG images).
> **Method:** every image was opened and visually analyzed (not just inferred from its filename). Analysis date: 2026-07-06.
> **Cross-cutting finding:** the application is branded **"Juliette Hotels"** ; the internal translation domain is named `sofiahoteles`. The screenshots confirm the system's two faces: the **administration dashboard** and the **generated public websites** on `*.site-hotel.com` subdomains.

---

## 1. Full dashboard sidebar menu (visible in the screenshots)

`Inicio (Home) · Reservas (Bookings) · Alojamientos (Accommodations) · Usuarios (Users) · Empresas (Companies) · Destinos (Destinations) · Lista negra (Blacklist) · Portal contenidos (Content portal) · Opiniones (Reviews) · Traducciones (Translations) · Sitemaps · Servicios de colas (Queue services) · CRM · Dominios redireccionados (Redirected domains) · Configuración (Settings) · Reportes (Reports) · Anuncios (Ads) · Analytics`

> Note: the screenshots cover 11 of these sections. `Reservas`, `Usuarios`, `Lista negra`, `CRM` and `Reportes` appear in the menu but have **no** dedicated screenshot.

---

## 2. Reference table: image name → content

### A) Administration dashboard (`menu_*.png`)

| Image | Verified content |
|---|---|
| `menu_Analytics.png` | **Analytics › Accounts** module: analytics accounts table (Type, Code, Product, Creation date, Status, System). Contains one active **Google Analytics 4** account (`G-…` code), with *Add* button and edit/delete actions. |
| `menu_alojamientos_hotel-list.png` | **Accommodations › List**: bulk hotel listing (500 per page) with Id, Name, **SEO Domain** (`<hotel>.site-hotel.com`), Rk/Fc/Fd metrics, Tourist destination, General destination (Austria), Quality (stars) and actions. Filters by destination, sub-destination, IP, host, tag, quality, product type and company; batch actions and chains. This is the central inventory screen. |
| `menu_alojamiento_ficha_hotel_edit_.png` | **Hotel edit form** (e.g. *Apartment 5 Peaks*, Zell am See). Sections: Contract type · Destination & chain · Configuration (official website, accommodation type, category, rack, gallery type, tags, meta tags, related hotels) · **Domains** (SEO domain + history) · **Sales** (promo price, booking email/phone, affiliate cart, multi-affiliate sale) · Affiliates · Integrations · **Address with lat/long** · Services · Conditions · Rooms · **Per-language SEO** (title, description, keywords + *Regenerate SEO* button) · Image **gallery** with autofill. The master product record. |
| `menu_anuncios_list.png` | **Ads › List**: 22 ad blocks with Score, Identifier (positions `AD_P1…P18`, `_ATF`/`_BTF` variants —above/below the fold— plus `AMP_*`/`MOB_*`), Type (Web), Position, Company/Destination/Product, Date and Status (mostly *Inactive*). Manages the advertising slots on the generated websites. |
| `menu_configuracion_list.png` | **Settings › List**: key-value parameters grouped by set: *Accommodations* (SEO/domain regeneration flags, affiliation, cart), *General* (proxy, sync-point, CRM email copy, `REDIRECT_LOCALE`, **Apache Solr endpoint** on an internal IP, reCAPTCHA key) and *Geolocation* (per-country ISO locale). ⚠️ The screenshot exposes sensitive values (keys/passwords): rotate them and do not publish this image. |
| `menu_destination_list.png` | **Destinations › List**: hierarchical destination tree by country with internal IDs (Antigua, Austria —expanded into its 9 states—, Belgium, Spain, France, Italy, Mexico, USA, etc.), *Close/Open all* buttons, *Add sub-destination* and *Add general destination*. |
| `menu_destinations-edit.png` | **Destinations › Edit**: tree expanded down to Tyrol municipalities (Abfaltersbach, Absam…, with IDs) and the **destination edit modal**: General data (multi-language name, Ufi code, alias), **SEO data** (widget, SEO domain, URL, tags) and **Integration** (OnLineTravel ID). Context menu: Edit/Delete/Web configuration/Gallery/HTML contents. |
| `menu_dominios-redireccionados .png` | **Redirected domains › List**: table of **301** redirects from former hotel subdomains (`*.site-hotel.com`) to `site-hotel.com`, with date, redirect status, status filter and batch actions. An SEO clean-up tool. |
| `menu_empresas.png` | **Companies › List**: 2 companies of type *Distributor* — “Europa Hotels” (0 hotels) and “Community Oriented Marketing” (**3,513 hotels**) — with Id, trade name, tax number, type and actions. |
| `menu_empresas_edit.png` | **Companies › Edit**: company data (type, names, language, booking phone/WhatsApp, **payment method and profit %**, IBAN, **default domain `site-hotel.com`**, country), contact person, configuration (search toggle, status, Google search domain —“Google France”— and “Hotel + Tourist Destination” pattern), logo/cover photo, description and SEO meta tags. Header buttons: *Add content in batch* and *Domain sitemap*. |
| `menu_empresas_edit_afiliaciones.png` | **Companies › Edit › “Edit affiliations” modal**: create/edit a *Sale* affiliation with Affiliate, booking URL, extra URL parameters, issuing/receiving countries (ISO A-2), label, preferred and active flags. |
| `menu_empresas_edit_afiliaciones_list-afiliados .png` | Same modal with the **dropdown of available affiliates/OTAs**: NeoBooking, Agoda, Expedia, Hotels.com, Playa Sol, Travel Cuba, OnlineTravel, Booking.com (entity URL), TripExplorer, HotelAdvisor, Priceline(.com), Awin (Booking/Trip.com/Agoda), Generic Sale, Hotels Combined, Destinia, Tarifas WEB. Confirms the **affiliate monetization model**. |
| `menu_empresas_web-configuration.png` | **Companies › Web configuration** (for “Community Oriented Marketing”): **web template** selection (“Officiallight”) with parameters; settings (slogan, “Hotels & Resorts” breadcrumb, SSL redirect, multi-affiliation SSL, availability form, force AMP); **widgets per template region** (company-front, content-top, main-content, final) and resources. Controls the look of the generated sites. |
| `menu_opiniones.png` | **Reviews › List**: user reviews with Id (UUID), Hotel, User and Language (FR/DE/ES/EN/IT). Visible total: **462,684 reviews**. Actions: approve, info, delete. |
| `menu_portal-de-contenidos.png` | **Content portal › List**: web content pieces with Id, Name, Identifier (e.g. `CONTACT-INCREASE-USER-STAY`), Type (*Web contents*), User and Status; filter and batch actions. |
| `menu_servicio-de-colas_list.png` | **Queue services › List**: catalogue of asynchronous *workers* with Name, Alias, retries, batch size and last run: `queue.parser.load` (hotel-loading robot), `queue.import.destination`, `queue.update.hotel`, `queue.parser.google` (Maps/phones), `queue.maintenance.hotel.content/.delete/.storage/.legal`, `queue.crm.email.download/.send/.respond`, `queue.batch.hotel`, `queue.batch.sitemap`, `queue.maintenance.database`, `queue.booking.cron`, `queue.maintenance.related.hotel`. The heart of the background processing. |
| `menu_sitemaps.png` | **Sitemaps › List** (wide view): one sitemap per hotel with Name, Type (*Hotel*), **SEO Domain** and **sitemap URL** (`sitemaps/<domain>-sitemap.xml`), distributor (“Community Oriented Marketing”) and a **+ Generate** button. |
| `menu_sitemaps_list.png` | The same **Sitemaps** screen in a narrow layout: alphabetical hotel list with domain and sitemap XML. Confirms mass sitemap generation per subdomain. |
| `menu_traducciones_.png` | **Translations › Overview** (LexikTranslationBundle): translation-progress matrix by **domain** (`LexikTranslationBundle`, `sofiahoteles` —388 keys—, `templateDefault`, `templateMatch`, `templateOfficial`) × **~40 languages** (AR…ZH), with ZIP import/export and last-translation date. |
| `menu_traducciones_grid.png` | **Translations › Grid**: editable grid of translation keys (ID, domain, key) with per-language columns (DE, EL, EN, ES, FR, HU, IT, PT…), inline editing, *New translation*, *Invalidate cache* and pagination (30 pages). |

### B) Generated public websites (`_ *.site-hotel.com*.png`)

| Image | Verified content |
|---|---|
| `_ apartment5peaks.site-hotel.com.png` | **Generated public website** for *Apartment 5 Peaks* (Zell am See, Salzburg): header with “Hotels & Resorts › Zell am See › …” breadcrumb, “Hotel information and unofficial booking website” notice, **booking widget** (check-in/out, adults/children, “FROM €29.00” price), Details/Rooms/Services/Conditions/Opinions/Contact menu, **review score** (9.8 from 73 reviews), description and a **30-photo gallery**. |
| `_ apartment5peaks.site-hotel.com___contact-form.png` | Same site, **contact view**: after services and the **conditions table** (check-in/out, cancellation, curfew, children, pets, payments), a “**How can we help you?**” block with a CONTACT button (email lead capture), Best price / No surprises / Discounts badges, and a footer with the unofficial-website *disclaimer* and an “Are you the owner of this property?” link. |
| `_ sonnenalmstuhleck.site-hotel.com.png` | **Public website** for *Hotel Sonnenalm Stuhleck ★★★★* (Spital am Semmering, Styria): same template layout — booking widget (“FROM €53.00”), review score (7.8 from 80 reviews), description, **45-photo gallery**. Demonstrates the multi-template/multi-hotel nature of the generator. |
| `_ sonnenalmstuhleck.site-hotel.com___contact-form.png` | Same site, **contact view**: conditions (incl. “Payments by Booking.com”), FAQ and a “**100% real reviews**” section with individual reviews by country/language (pros 👍 / cons 👎) before the contact block. |
| `_ sonnenalmstuhleck.site-hotel.com___view-gallery.png` | Same site, **gallery-expanded view**: full page walk-through — conditions, FAQ and the real-reviews block with per-guest scores (9.0/7.0…), *MORE REVIEWS* button. |

---

## 3. Technical facts the screenshots reveal (useful for the audits)

1. **Active brand/tenant:** Juliette Hotels; main distributor “Community Oriented Marketing” with **3,513 hotels** and **462,684 reviews** — relevant volume for sizing the DB migration.
2. **Business model:** unofficial hotel-information websites + **affiliate monetization** (17+ OTAs) and positional ads (P-1…P-18, ATF/BTF, AMP).
3. **Infrastructure referenced in Settings:** **Apache Solr** search (endpoint on a private IP), reCAPTCHA, integration proxy/sync-point — to be inventoried in the server audit.
4. **Operational SEO:** per-language SEO regeneration on the hotel form, per-subdomain XML sitemaps with mass generation, centralized 301 redirects and per-company default domains.
5. **⚠️ Security:** `menu_configuracion_list.png` shows integration keys and a password in plain text.

---

## Pending data to complete

| # | Pending item | Reason |
|---|---|---|
| P-07 | Screenshots of `Reservas`, `Usuarios`, `Lista negra`, `CRM` and `Reportes` | Sections visible in the sidebar with no dedicated image; their content is not documented to avoid assumptions. |
| P-08 | Confirm the relationship between the “Juliette Hotels” / “Sofia” / “vikahotel” names | The three designations coexist (UI, translation domain, composer.json). |

---

*Companion document: `guia-imagenes-menu_es.md`. Produced by technical audit with visual verification of every image.*
