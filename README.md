# Väntetid Katarakt — Distributionspaket

Standardiserad beräkningslogik i VQL för väntetidsberäkning inom katarakt,
från Vårddatahubben (KCHD, SKR).

## Syfte

Regioner hämtar detta paket och kör det mot sina egna datakällor i Denodo.
Beräkningslogiken är identisk för alla regioner — det enda som anpassas är
**basvyerna** i `vql/01_basvy/`.

## Mappstruktur

```
vql/
├── 00_kodverk/        Referensdata (KVÅ-koder, fas, avvikelser, intervall)
├── 01_basvy/          Interface-vyer — ENDA som regioner anpassar
├── 02_berakning/      Kärnlogik — identisk alla regioner
└── 03_resultatvy/     Färdiga vyer för BI/rapport
tests/                 Testfiler för verifiering av beräkningslogik
```

### Namnkonvention

| Prefix   | Mapp            | Beskrivning                     |
|----------|-----------------|---------------------------------|
| `ref_*`  | `00_kodverk`    | Referensdata och kodverk        |
| `src_*`  | `01_basvy`      | Basvyer (regionanpassade)       |
| `calc_*` | `02_berakning`  | Beräkningslogik                 |
| `res_*`  | `03_resultatvy` | Resultatvyer för BI/rapport     |

## Kom igång

1. Klona repot
2. Anpassa vyerna i `vql/01_basvy/` till er regions datakällor
3. Kör VQL-filerna i ordning (00 → 01 → 02 → 03) mot er Denodo-instans

## Versionshantering

Projektet följer [Semantic Versioning](https://semver.org/lang/sv/).
Se `CHANGELOG.md` för detaljer om ändringar mellan versioner.

## Regionspårning

När er region driftsätter eller uppgraderar, uppdatera `manifest.json` → `regions`-objektet.
