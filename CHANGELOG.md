# Ändringslogg

Alla väsentliga ändringar i detta projekt dokumenteras i denna fil.
Formatet baseras på [Keep a Changelog](https://keepachangelog.com/sv/1.0.0/)
och projektet följer [Semantic Versioning](https://semver.org/lang/sv/).

## [1.0.1] — 2026-03-28

### Tillagt
- ref_avvikelsekoder: Ny referensvy som dokumenterar avvikelsekoderna (PvV/MoV/SoV)
- ref_filter_region: Ny konfigurerbar vy för regionens länskoder (utomläningsflagga)
- is_hemregion-kolumn i calc_vantetid_genomford och res_genomford_detalj
- Komplett VQL-kod för alla beräknings- och resultatvyer
- verif_jamforelse och dq_rapport_data för verifiering och datakvalitet

### Ändrat
- res_kpi_manad: sjukhusnamn tillagt i GROUP BY (VGR feedback)
- verif_jamforelse: sjukhusnamn tillagt för per-sjukhus-jämförelse mot vantetider.se
- dq_rapport_data: DQ6-rimlighet nu per sjukhus via CONCAT

### Fixat
- Tydligare kommentarer i calc_vantetid_genomford för getdaysbetween-argument

## [1.0.0] — 2026-03-28

### Tillagt
- Initial projektstruktur med VQL-mappstruktur (kodverk, basvy, beräkning, resultatvy)
- CLAUDE.md med instruktioner för Claude Code
- manifest.json för versionshantering och regionspårning
- README.md med projektdokumentation
