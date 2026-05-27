# Riidanratkaisu

Riita-asian ratkaiseminen yleisissä tuomioistuimissa (oikeudenkäymiskaari 4/1734):
vireillepano, todistelu ja muutoksenhaku.

> **Luonnokset ja arviot ovat tarkistettavia — ei oikeudellista neuvontaa eikä arvio
> menestymisestä.** Toimeksiannon hoitava asianajaja vastaa lopputuloksesta. Katso [`CLAUDE.md`](CLAUDE.md).

## Skillit

| Skill | Mitä tekee |
|---|---|
| **haastehakemus** | Riita-asian haastehakemuksen laatiminen ja tarkistus (OK 5:2 §): vaatimukset, perusteet, todisteet, kulut, toimivalta, prosessiosoite. Sisältää riidanratkaisun perusteiden referenssin. |
| **todistelu** | Todistelun suunnittelu ja arviointi (OK 17 luku): näyttötaakka, todistuskeinot, todistusteemat, rajoitukset, todistelusuunnitelma. |
| **muutoksenhaku-tuomioon** | Valitus hovioikeuteen (jatkokäsittelylupa, OK 25/25 a luku) ja korkeimpaan oikeuteen (valituslupa, OK 30 luku): tyytymättömyyden ilmoitus, määräajat, kirjelmät. |

## Perustana varmistetut säädökset

Lähteestä (oik.ai/Finlex) varmistettu: **oikeudenkäymiskaari (4/1734)** — mm. haastehakemuksen
sisältö (5:2 §) haettu sanatarkasti — ja **tuomioistuinlaki (673/2016)**. Aineellinen laki ja
muut säädökset (mm. laki välimiesmenettelystä 967/1992) tarkistetaan `juristi:oikeustutkimus`-skillillä.

## Liittyy

- **`juristi`-plugari** — `oikeustutkimus` (prosessisäännökset, aineellinen laki ja KKO/hovioikeus-käytäntö) ja `asiakirjan-tarkistus`.
- **`sopimukset`-plugari** — sopimusriitojen aineellinen pohja.
- **`tietosuoja`-plugari** — aineiston anonymisointi (PII Shield) ennen käsittelyä.

## Asennus

```
/plugin marketplace add akunikkola/claude-for-legal-finland
/plugin install riidanratkaisu@claude-for-legal-finland
```

oik.ai-konnektori: katso juuren [QUICKSTART.md](../QUICKSTART.md).
