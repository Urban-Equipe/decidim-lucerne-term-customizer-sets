# decidim-lucerne-term-customizer-sets

CSV translation sets for **Decidim Term Customizer** on [dialogluzern.ch](https://dialogluzern.ch) (Dialog Stadt Luzern). See repositories [Decidim-OCL](https://github.com/stadtluzern/decidim-ocl) and [Decidim.Swiss](https://github.com/decidim-swiss/decidim.swiss) for code.
They replace and complement platform strings in **German (DE)** with Schweizer Hochdeutsch, Du-Form, and local terminology.

## Repository contents

| Item | Description |
|------|-------------|
| **`admin_*.csv`** | One file per Decidim area (proposals, meetings, admin, …). Import or merge into Term Customizer as needed. |
| **Locale** | **German (`de`) only** — each file lists custom terms for `de`; English (`en`) reference rows are not included. |
| **Internal review files** | `_korrekturen.csv`, `_sie_form_manuell_pruefen.csv`, `_ungueltige_keys.csv` are *not* published in this repo; they stay in the local `Output` folder for maintenance only. |

## Using these files

1. In Decidim Admin, open **Term Customizer** (or your organization’s equivalent).
2. Import the CSVs you need, or copy rows into existing translation sets.
3. Keys follow standard Decidim I18n paths (e.g. `decidim.proposals.*`). See the legend below for file ↔ prefix mapping.

## Maintenance snapshot

**Last structural update:** 23 March 2026 — cleanup, restructuring, and reorganization of TermCustomizer language files.

---

## Legende – Sprachfile-Bereinigung Dialog Luzern

### Übersicht

Aus den ursprünglichen Input-Sets wurden **1'951 gültige Keys** in **21 thematische Output-Files** (`admin_*.csv`) aufgeteilt.

| Datei | Keys | Thema |
|---|---|---|
| `admin_proposals.csv` | 303 | Vorschläge |
| `admin_initiatives.csv` | 222 | Impulse / Initiativen |
| `admin_account_authentication.csv` | 209 | Konto, Anmeldung & Verifikation |
| `admin_meetings.csv` | 191 | Veranstaltungen |
| `admin_general.csv` | 184 | Allgemein (nicht zuordenbar) |
| `admin_assemblies.csv` | 162 | Organisationen |
| `admin_notifications.csv` | 112 | Benachrichtigungen & Events |
| `admin_participatory_processes.csv` | 110 | Projekte / Partizipationsprozesse |
| `admin_admin.csv` | 113 | Admin-Bereich |
| `admin_surveys.csv` | 78 | Umfragen & Formulare |
| `admin_conferences.csv` | 57 | Konferenzen |
| `admin_decidim_awesome.csv` | 47 | Decidim Awesome (Plugin) |
| `admin_navigationmaps.csv` | 31 | Navigationskarten (NavigationMaps) |
| `admin_comments.csv` | 43 | Kommentare |
| `admin_budgets.csv` | 38 | Budgets / Abstimmungen |
| `admin_newsletters.csv` | 20 | Newsletter |
| `admin_blogs.csv` | 14 | Blog-Posts |
| `admin_pages.csv` | 26 | Seiten, Menü & Layout |
| `admin_debates.csv` | 8 | Debatten |
| `admin_datetime.csv` | 4 | Datum & Uhrzeit (time.*) |
| `admin_accountability.csv` | 12 | Rechenschaft / Ergebnisse |

### Zuteilung nach Key-Präfix

#### admin_proposals.csv
`decidim.proposals.*`, `activemodel.attributes.proposal.*`, Gamification-Badges für Vorschläge

#### admin_initiatives.csv
`decidim.initiatives.*`, `activemodel.attributes.initiative.*`, `activemodel.attributes.initiatives_type.*`

#### admin_account_authentication.csv
`decidim.account.*`, `decidim.devise.*`, `devise.*`, `decidim.verifications.*`,
`decidim.authorization_handlers.*`, `decidim.authorization_modals.*`, `decidim.doorkeeper.*`,
`activemodel.attributes.user.*`, `activemodel.attributes.account.*`,
`activemodel.attributes.confirmation.*`, `activemodel.attributes.id_document_upload.*`,
`activemodel.attributes.mobile_phone.*`, `password_validator.*`  
**Ausnahme Newsletter:** `decidim.devise.shared.newsletter_modal.*` verbleibt hier (korrekt)

#### admin_meetings.csv
`decidim.meetings.*`, `activemodel.attributes.meeting.*`, `decidim.forms.meetings.*`

#### admin_general.csv
Alle Keys ohne spezifische Komponenten-Zuweisung, u.a.:
`decidim.amendments.*`, `decidim.gamification.*`, `decidim.messaging.*`,
`decidim.scopes.*`, `decidim.groups.*`, `decidim.links.*`, `decidim.system.*`,
`decidim.export_mailer.*`, `decidim.user_conversations.*`, `decidim.user_interests.*`,
`decidim.user_update_mailer.*`, `decidim.content_blocks.*` (nicht-awesome),
`decidim.design.foundations.*`, `decidim.design.helpers.*`,
`decidim.orders.*`, `decidim.metrics.*` (allgemein), u.v.m.

#### admin_assemblies.csv
`decidim.assemblies.*`, `activemodel.attributes.assembly.*`, `activerecord.models.decidim/assembly*`

#### admin_notifications.csv
`decidim.events.*` (ausser conferences-Events → admin_conferences.csv),
`decidim.notification_mailer.*`, `decidim.notifications_digest_mailer.*`,
`decidim.welcome_notification.*`, `decidim.endorsement_buttons_cell.*`,
`activemodel.models.decidim/*`

#### admin_participatory_processes.csv
`decidim.participatory_processes.*`, `decidim.participatory_process_groups.*`,
`activemodel.attributes.participatory_process.*`

#### admin_admin.csv
`decidim.admin.*` (ausser newsletters und registration_types → eigene Files),
`decidim.admin_log.*`, `decidim.admin_terms_of_service.*`

#### admin_surveys.csv
`decidim.surveys.*`, `decidim.forms.*`, `decidim.templates.*`,
`activemodel.attributes.questionnaire*`, `activemodel.attributes.question.*`

#### admin_conferences.csv
`decidim.conferences.*`, `decidim.events.conferences.*`,
`decidim.admin.registration_types.*`, `decidim.admin.models.registration_type.*`,
`activemodel.attributes.conference.*`, `layouts.decidim.conferences.*`

#### admin_decidim_awesome.csv
`decidim.decidim_awesome.*`, `layouts.decidim.decidim_awesome.*`,
`decidim.components.awesome_iframe.*`, `decidim.components.awesome_map.*`

#### admin_navigationmaps.csv
`decidim.navigation_maps.*`, `decidim.components.navigation_maps.*`

#### admin_comments.csv
`decidim.comments.*`

#### admin_budgets.csv
`decidim.budgets.*`, `decidim.orders.*` (Budget-spezifisch)

#### admin_newsletters.csv
`decidim.admin.newsletters.*`, `decidim.newsletter_mailer.*`,
`decidim.newsletter_templates.*`, `decidim.newsletters.*`,
`decidim.newsletters_opt_in_mailer.*`,
`decidim.notifications_settings.show.newsletter_notifications`

#### admin_blogs.csv
`decidim.blogs.*`, `activemodel.models.decidim/blogs*`

#### admin_pages.csv
`decidim.menu.*`, `decidim.pages.*`, `layouts.decidim.data_consent.*`,
`layouts.decidim.offline_banner.*`, `layouts.decidim.social_media_links.*`,
`layouts.decidim.user_menu.*`, `layouts.decidim.user_profile.*`,
`layouts.decidim.impersonation_warning.*`, `layouts.decidim.timeout_modal.*`

#### admin_debates.csv
`decidim.debates.*`, `decidim.components.debates.*`

#### admin_datetime.csv
`time.*` (am, pm, formats) – Standard Rails-Zeitformate

#### admin_accountability.csv
`decidim.accountability.*`, `activemodel.attributes.result.*`

### Aufgehobene Files (leer, können gelöscht werden)

| Datei | Inhalt war in … verschoben |
|---|---|
| `admin_content_blocks.csv` | `admin_general.csv` / `admin_decidim_awesome.csv` |
| `admin_models.csv` | `admin_conferences.csv` / `admin_general.csv` |
| `admin_navigation_ui.csv` | umbenannt zu `admin_pages.csv` |
| `admin_search.csv` | `admin_debates.csv` / `admin_general.csv` |
| `admin_voting.csv` | `admin_budgets.csv` / `admin_decidim_awesome.csv` / `admin_debates.csv` / `admin_notifications.csv` / `admin_general.csv` |

### Bereinigungsregeln

1. **Validierung:** Jeder Key wurde gegen die Crowdin-Files (`*.xliff`, `de.yml`) geprüft. Nicht vorhandene Keys wurden entfernt (43 gelöscht).
2. **Plural-Varianten:** `.one`/`.other`-Suffixe werden auf den Basis-Key gemappt (XLIFF-Format: `[0]`/`[1]`).
3. **Duplikate:** Bei doppelten Keys gilt die höhere ID (neuerer Eintrag) als massgeblich.
4. **Sprachregeln:**
   - Durchgehend **„Du"-Form** (keine „Sie"-Form)
   - **Schweizer Hochdeutsch:** kein `ß` (→ `ss`)
   - Phrasen und Sätze beginnen mit **Grossbuchstaben**
5. **Terminologie:** Assemblies = „Organisationen", Meetings = „Veranstaltungen"
6. **„Sie"-Form-Bereinigung:** 24 Keys aus Crowdin wurden zusätzlich übernommen und in Du-Form konvertiert.
