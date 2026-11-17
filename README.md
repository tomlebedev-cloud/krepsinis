# EUROLEAGUE HUB

Projekto aplankas ir repozitorija: `KREPSINIS` / `tomlebedev-cloud/krepsinis`.

Visos krepšinio lygos vienoje vietoje: rezultatai, statistika, prognozės ir statymų įrankiai.

Svetainė: https://tomlebedev-cloud.github.io/krepsinis/

| Aplankas | Lyga | Duomenų šaltinis |
|----------|------|------------------|
| `euroleague/` | Eurolyga | oficialus EuroLeague API |
| `eurocup/` | Europos taurė (EuroCup) | oficialus EuroLeague API |
| `lkl/` | LKL | lkl.lt |
| `acb/` | ACB (Liga Endesa) | acb.com |

`index.html` – pradinis puslapis su informaciniais blokais kiekvienai lygai.
Kiekvieno aplanko `README.md` aprašo tos lygos puslapius, modelį ir duomenų atnaujinimą.

## Statymų žurnalas

`statymai/statymai.csv` – asmeninis statymų žurnalas (buvęs BETS projektas). Jis git-ignoruojamas ir į GitHub nekeliamas, nes repozitorija vieša.

## Duomenų atnaujinimas

Kiekviena lyga turi savo GitHub Actions darbą (`.github/workflows/<lyga>.yml`) su savo tvarkaraščiu:
greiti patikrinimai per rungtynių laiką ir pilnas atnaujinimas kiekvieną rytą 05:23 UTC.

Rankiniu būdu: `cd <lyga> && python update_data.py`

## Paleisti lokaliai

```
python3 -m http.server 8000
```

ir atidaryk http://localhost:8000.

## Istorija

2026-11-17 sujungti keturi atskiri projektai (`acb`, `euroleague`, `eurocup`, `lkl`) su visa jų git istorija.
Senos svetainės (`tomlebedev-cloud.github.io/acb/` ir kt.) nukreipia į naująsias.
