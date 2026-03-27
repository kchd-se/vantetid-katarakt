# CLAUDE.md — Instruktioner för Claude Code

> Denna fil läses automatiskt av Claude Code varje gång du jobbar i detta repo.
> Du behöver aldrig förklara dessa regler — Claude Code följer dem automatiskt.

## Vad är det här repot?

Ett **distributionspaket** från Vårddatahubben (KCHD, SKR). Innehåller standardiserad
beräkningslogik i VQL som regioner hämtar och kör mot sina egna datakällor i Denodo.

Regioner ändrar BARA filerna i `vql/01_basvy/`. Allt annat är identiskt för alla regioner.

## Versionshantering — följ ALLTID dessa regler

Vi använder **Semantic Versioning (SemVer)**: `MAJOR.MINOR.PATCH`

### När du ändrar kod, bestäm vilken typ av ändring:

- **PATCH** (1.0.0 → 1.0.1): Buggfix, rättning av felaktig logik, stavfel i SQL.
  Regionen kan uppgradera utan att ändra något hos sig.
- **MINOR** (1.0.x → 1.1.0): Ny vy tillagd, ny kolumn i resultatvy, ny testfil.
  Bakåtkompatibelt — regionen kan uppgradera utan att ändra sina basvyer.
- **MAJOR** (1.x.x → 2.0.0): Kolumn bytt namn/borttagen i basvy, ändrad beräkningslogik
  som kräver att regionen uppdaterar sin koppling. UNDVIK om möjligt.

### Vid VARJE commit som ändrar funktionalitet:

1. **Uppdatera `CHANGELOG.md`** — lägg till under rätt version och kategori (Tillagt/Ändrat/Fixat/Borttaget)
2. **Uppdatera `manifest.json`** — ändra `version` och `release_date`
3. **Commit-meddelande** på formatet: `v1.0.1: Kort beskrivning av ändringen`
4. **Skapa git tag** efter commit: `git tag v1.0.1`
5. **Pusha med tags**: `git push && git push --tags`

### CHANGELOG-format (Keep a Changelog):

```markdown
## [1.0.1] — 2026-04-02

### Fixat
- Korrigerat beräkning av vantetid_dagar vid midnattsövergång (VGR feedback)
```

Kategorier att använda: `Tillagt`, `Ändrat`, `Fixat`, `Borttaget`

## Mappstruktur — rör inte

```
vql/
├── 00_kodverk/        Referensdata (KVÅ-koder, fas, avvikelser, intervall)
├── 01_basvy/          Interface-vyer — ENDA som regioner anpassar
├── 02_berakning/      Kärnlogik — identisk alla regioner
└── 03_resultatvy/     Färdiga vyer för BI/rapport
```

Namnkonvention:
- `ref_*` → 00_kodverk
- `src_*` → 01_basvy
- `calc_*` → 02_berakning
- `res_*` → 03_resultatvy

## Regionspårning

När en region driftsätter eller uppgraderar, uppdatera `manifest.json` → `regions`-objektet.

## Språk

Alla commit-meddelanden, CHANGELOG, README och kommentarer i VQL skrivs på **svenska**.

## Kvalitetskontroll

Innan release, verifiera att:
- [ ] Alla VQL-filer har en kommentarsheader med filnamn och paketversion
- [ ] CHANGELOG.md är uppdaterad
- [ ] manifest.json har rätt version och datum
- [ ] Git tag matchar version i manifest.json
- [ ] Tester i tests/ är uppdaterade om ny logik lagts till
