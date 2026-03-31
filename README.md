# decidim-lucerne-term-customizer-sets

CSV translation sets for **Decidim Term Customizer** on [dialogluzern.ch](https://dialogluzern.ch) (Dialog Stadt Luzern).  
They replace and complement platform strings in **German (Switzerland)** with Schweizer Hochdeutsch, Du-Form, and local terminology.

## Repository contents

| Item | Description |
|------|-------------|
| **`*.csv`** | One file per Decidim area (proposals, meetings, admin, …). Import or merge into Term Customizer as needed. |
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

Aus den ursprünglichen Input-Sets wurden **1'951 gültige Keys** in **20 thematische Output-Files** aufgeteilt.

| Datei | Keys | Thema |
|---|---|---|
| `proposals.csv` | 303 | Vorschläge |
| `initiatives.csv` | 222 | Impulse / Initiativen |
| `account_authentication.csv` | 209 | Konto, Anmeldung & Verifikation |
| `meetings.csv` | 191 | Veranstaltungen |
| `general.csv` | 184 | Allgemein (nicht zuordenbar) |
| `assemblies.csv` | 162 | Organisationen |
| `notifications.csv` | 112 | Benachrichtigungen & Events |
| `participatory_processes.csv` | 110 | Projekte / Partizipationsprozesse |
| `admin.csv` | 113 | Admin-Bereich |
| `surveys.csv` | 76 | Umfragen & Formulare |
| `conferences.csv` | 57 | Konferenzen |
| `decidim_awesome.csv` | 47 | Decidim Awesome (Plugin) |
| `comments.csv` | 43 | Kommentare |
| `budgets.csv` | 38 | Budgets / Abstimmungen |
| `newsletters.csv` | 20 | Newsletter |
| `blogs.csv` | 14 | Blog-Posts |
| `pages.csv` | 26 | Seiten, Menü & Layout |
| `debates.csv` | 8 | Debatten |
| `datetime.csv` | 4 | Datum & Uhrzeit (time.*) |
| `accountability.csv` | 12 | Rechenschaft / Ergebnisse |

### Zuteilung nach Key-Präfix

#### proposals.csv
`decidim.proposals.*`, `activemodel.attributes.proposal.*`, Gamification-Badges für Vorschläge

#### initiatives.csv
`decidim.initiatives.*`, `activemodel.attributes.initiative.*`, `activemodel.attributes.initiatives_type.*`

#### account_authentication.csv
`decidim.account.*`, `decidim.devise.*`, `devise.*`, `decidim.verifications.*`,
`decidim.authorization_handlers.*`, `decidim.authorization_modals.*`, `decidim.doorkeeper.*`,
`activemodel.attributes.user.*`, `activemodel.attributes.account.*`,
`activemodel.attributes.confirmation.*`, `activemodel.attributes.id_document_upload.*`,
`activemodel.attributes.mobile_phone.*`, `password_validator.*`  
**Ausnahme Newsletter:** `decidim.devise.shared.newsletter_modal.*` verbleibt hier (korrekt)

#### meetings.csv
`decidim.meetings.*`, `activemodel.attributes.meeting.*`, `decidim.forms.meetings.*`

#### general.csv
Alle Keys ohne spezifische Komponenten-Zuweisung, u.a.:
`decidim.amendments.*`, `decidim.gamification.*`, `decidim.messaging.*`,
`decidim.scopes.*`, `decidim.groups.*`, `decidim.links.*`, `decidim.system.*`,
`decidim.export_mailer.*`, `decidim.user_conversations.*`, `decidim.user_interests.*`,
`decidim.user_update_mailer.*`, `decidim.content_blocks.*` (nicht-awesome),
`decidim.design.foundations.*`, `decidim.design.helpers.*`,
`decidim.orders.*`, `decidim.metrics.*` (allgemein), u.v.m.

#### assemblies.csv
`decidim.assemblies.*`, `activemodel.attributes.assembly.*`, `activerecord.models.decidim/assembly*`

#### notifications.csv
`decidim.events.*` (ausser conferences-Events → conferences.csv),
`decidim.notification_mailer.*`, `decidim.notifications_digest_mailer.*`,
`decidim.welcome_notification.*`, `decidim.endorsement_buttons_cell.*`,
`activemodel.models.decidim/*`

#### participatory_processes.csv
`decidim.participatory_processes.*`, `decidim.participatory_process_groups.*`,
`activemodel.attributes.participatory_process.*`

#### admin.csv
`decidim.admin.*` (ausser newsletters und registration_types → eigene Files),
`decidim.admin_log.*`, `decidim.admin_terms_of_service.*`

#### surveys.csv
`decidim.surveys.*`, `decidim.forms.*`, `decidim.templates.*`,
`activemodel.attributes.questionnaire*`, `activemodel.attributes.question.*`

#### conferences.csv
`decidim.conferences.*`, `decidim.events.conferences.*`,
`decidim.admin.registration_types.*`, `decidim.admin.models.registration_type.*`,
`activemodel.attributes.conference.*`, `layouts.decidim.conferences.*`

#### decidim_awesome.csv
`decidim.decidim_awesome.*`, `layouts.decidim.decidim_awesome.*`,
`decidim.components.awesome_iframe.*`, `decidim.components.awesome_map.*`

#### comments.csv
`decidim.comments.*`

#### budgets.csv
`decidim.budgets.*`, `decidim.orders.*` (Budget-spezifisch)

#### newsletters.csv
`decidim.admin.newsletters.*`, `decidim.newsletter_mailer.*`,
`decidim.newsletter_templates.*`, `decidim.newsletters.*`,
`decidim.newsletters_opt_in_mailer.*`,
`decidim.notifications_settings.show.newsletter_notifications`

#### blogs.csv
`decidim.blogs.*`, `activemodel.models.decidim/blogs*`

#### pages.csv
`decidim.menu.*`, `decidim.pages.*`, `layouts.decidim.data_consent.*`,
`layouts.decidim.offline_banner.*`, `layouts.decidim.social_media_links.*`,
`layouts.decidim.user_menu.*`, `layouts.decidim.user_profile.*`,
`layouts.decidim.impersonation_warning.*`, `layouts.decidim.timeout_modal.*`

#### debates.csv
`decidim.debates.*`, `decidim.components.debates.*`

#### datetime.csv
`time.*` (am, pm, formats) – Standard Rails-Zeitformate

#### accountability.csv
`decidim.accountability.*`, `activemodel.attributes.result.*`

### Aufgehobene Files (leer, können gelöscht werden)

| Datei | Inhalt war in … verschoben |
|---|---|
| `content_blocks.csv` | `general.csv` / `decidim_awesome.csv` |
| `models.csv` | `conferences.csv` / `general.csv` |
| `navigation_ui.csv` | umbenannt zu `pages.csv` |
| `search.csv` | `debates.csv` / `general.csv` |
| `voting.csv` | `budgets.csv` / `decidim_awesome.csv` / `debates.csv` / `notifications.csv` / `general.csv` |

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
