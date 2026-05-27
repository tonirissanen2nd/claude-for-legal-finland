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

## Suositeltu työkalu: PII Shield (anonymisointi)

[**PII Shield**](https://github.com/gregmos/PII-Shield) anonymisoi dokumentit
**paikallisesti ennen kuin malli näkee ne** (`John Smith → <PERSON_1>`) ja palauttaa
oikeat tiedot jälkikäteen — *henkilötieto ei mene API:in*. Erinomainen pari tietosuojatyöhön
ja luottamuksellisuuteen. Se on erillinen Claude-laajennus (`.mcpb`) / CLI, jonka asennat itse.

**Asennus (virallinen):** lataa `.mcpb` PII Shieldin [releaseista](https://github.com/gregmos/PII-Shield/releases)
ja asenna Claude Desktopiin (Settings → Extensions), tai CLI: `npm install -g pii-shield`.

**🇫🇮 Suomalaiset tunnisteet (HETU + Y-tunnus) heti käyttöön:** viralliset paketit eivät
vielä sisällä suomalaisia tunnistimia — ne on lisätty upstream-PR:ssä
[gregmos/PII-Shield#4](https://github.com/gregmos/PII-Shield/pull/4). Kunnes se sulautuu,
saat ne käyttöön rakentamalla forkista:

```bash
git clone -b feat/finnish-recognizers https://github.com/akunikkola/PII-Shield.git
cd PII-Shield/nodejs-v2
npm ci
npm run build:server          # tuottaa dist/server.bundle.mjs (paikallinen MCP-palvelin)
# (ensimmäisellä ajolla lataa GLiNER-mallin ~634 MB)
```

Lisää sitten paikallinen MCP-palvelin Claude Codeen, esim.:

```bash
claude mcp add pii-shield --transport stdio -- node /ABSOLUUTTINEN/POLKU/PII-Shield/nodejs-v2/dist/server.bundle.mjs
```

Kun PR #4 on mergattu, voit siirtyä viralliseen `.mcpb`-/npm-versioon.

> Huom: tämä on **paikallinen, koneeseesi sidottu** asetus (absoluuttinen polku), ei
> osa siirrettävää plugaria. Siksi PII Shieldiä ei ole kytketty tämän plugarin
> `.mcp.json`:iin — se asennetaan erikseen yllä olevalla tavalla.

## Liittyy

- **`juristi`-plugari** — `oikeustutkimus` (kansallisen lain tarkistus) ja `asiakirjan-tarkistus`.

## Asennus

```
/plugin marketplace add akunikkola/claude-for-legal-finland
/plugin install tietosuoja@claude-for-legal-finland
```

oik.ai-konnektori: katso juuren [QUICKSTART.md](../QUICKSTART.md).
