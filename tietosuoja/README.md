# Tietosuoja

Henkilötietojen käsittelyn tietosuoja EU:n yleisen tietosuoja-asetuksen ((EU) 2016/679,
GDPR) ja kansallisen tietosuojalain (1050/2018) mukaan.

> **Arviot, selosteet ja vastausluonnokset ovat tarkistettavia luonnoksia — ei
> oikeudellista neuvontaa.** Korkean riskin käsittely, arkaluonteiset tiedot ja DPIA:t
> kuuluvat tietosuojavastaavan/juristin arvioon. Katso [`CLAUDE.md`](CLAUDE.md).

## Skillit

| Skill | Mitä tekee |
|---|---|
| **tietosuoja-arviointi** | Käsittelyperuste (6/9 art), käsittelyn periaatteet (5 art) ja vaikutustenarvioinnin (DPIA, 35 art) tarpeen arviointi. Sisältää referenssin tietosuojan perusteista. |
| **tietosuojaseloste** | Tietosuojaseloste / informointi rekisteröidylle (13–14 art) ja sisäinen seloste käsittelytoimista (30 art). |
| **rekisteroidyn-pyynnot** | Rekisteröidyn oikeuksien toteuttaminen ja tietopyyntöihin vastaaminen (15–22 art), kuukauden määräaika ja poikkeukset. |

## Perustana varmistetut säädökset

Lähteestä (oik.ai/Finlex) varmistettu: **tietosuojalaki (1050/2018)** täsmentää ja
täydentää **EU:n tietosuoja-asetusta (2016/679)**; työelämässä sovelletaan **lakia
yksityisyyden suojasta työelämässä (759/2004)**. GDPR-artiklat: EUR-Lex. Kansallisen lain
pykälät tarkistetaan `juristi:oikeustutkimus`-skillillä.

## Liittyy

- **`juristi`-plugari** — `oikeustutkimus` (kansallisen lain tarkistus) ja `asiakirjan-tarkistus`.

## Asennus

```
/plugin marketplace add akunikkola/claude-for-legal-finland
/plugin install tietosuoja@claude-for-legal-finland
```

oik.ai-konnektori: katso juuren [QUICKSTART.md](../QUICKSTART.md).
