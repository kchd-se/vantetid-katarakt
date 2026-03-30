# Ändringslogg

Alla väsentliga ändringar i detta projekt dokumenteras i denna fil.
Formatet baseras på [Keep a Changelog](https://keepachangelog.com/sv/1.0.0/)
och projektet följer [Semantic Versioning](https://semver.org/lang/sv/).

## [1.0.0] — 2026-03-30

### Tillagt
- Initial projektstruktur med VQL-mappstruktur (kodverk, basvy, beräkning, resultatvy)
- ref_kva_katarakt: 15 KVÅ-koder för kataraktoperationer
- ref_avvikelsekoder: Referensvy som dokumenterar avvikelsekoderna (PvV/MoV/SoV)
- ref_filter_region: Konfigurerbar vy för regionens länskoder (utomläningsflagga)
- src_genomford och src_vantande: Interface-vyer (mallar för regionanpassning)
- calc_vantetid_genomford: Beräkningsvy med väntetid, vårdgaranti, is_hemregion
- calc_vantande: Beräkningsvy för väntande patienter
- res_kpi_manad: Månatlig KPI-aggregering med sjukhusnamn i GROUP BY
- res_kpi_per_yrke, _kontaktform, _bokning, _remittent, _kommun: Dimensionsvyer
- res_genomford_detalj och res_vantande_detalj: Detaljvyer
- verif_jamforelse: Verifieringsvy för jämförelse mot vantetider.se (per sjukhus)
- dq_rapport_data: Datakvalitetsrapport med DQ0-DQ6 (rimlighet per sjukhus)
- CLAUDE.md med instruktioner för Claude Code
- manifest.json för versionshantering och regionspårning
- README.md med projektdokumentation
