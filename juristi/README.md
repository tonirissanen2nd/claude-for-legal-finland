# Juristi — perusta

Läpileikkaava perusta suomalaiseen juridiseen työhön. Tämä plugari on pohja, johon
käytäntöaluekohtaiset plugarit (lainvalmistelu, lausunnot, sopimukset, työoikeus,
tietosuoja, hallinto-oikeus, riidanratkaisu) nojaavat.

> **Jokainen tuotos on tarkistettava luonnos — ei oikeudellista neuvontaa.** Lopullisen
> vastuun kantaa sitä käyttävä ihminen. Katso [`CLAUDE.md`](CLAUDE.md).

## Skillit

| Skill | Mitä tekee |
|---|---|
| **juristi** | Suomalaisen lakikielen ja lainsäädännön yleisapuri: säädösten rakenne, pykäläviittausten oikea muoto, lakikielen kirjoitussäännöt, sopimukset ja oikeuslähteet. Käynnistyy automaattisesti, kun työskennellään juridisen sisällön kanssa. |
| **oikeustutkimus** | Hakee voimassa olevan lain ja oikeuskäytännön oik.ai-/Finlex-MCP:stä, lukee ne ja viittaa oikein. Estää muistinvaraiset ja keksityt pykälät ja ratkaisutunnukset. |
| **asiakirjan-tarkistus** | Juridisen asiakirjan monivaiheinen laaduntarkistus suomalaisessa kontekstissa: konteksti, käytettävyys, kieli, rakenne, oikeellisuus (lähdetarkistus), täydellisyys, riski ja käyttövalmius. |
| **suomen-kieli** | Suomen kielen oikeinkirjoitus-, kielioppi- ja tyyliohjeet (Kielitoimiston ohjepankki). Juristi-skill viittaa tähän kielenhuollossa. |

## Tietolähteet (`.mcp.json`)

- **oik.ai** (`https://oik.ai/mcp`) — suomalainen oikeuskäytäntö ja ajantasainen lainsäädäntö ohjelmallisesti. Vaatii oik.ai-tilin; liitettäessä OAuth-kirjautuminen.

Vaihtoehtoisesti voi käyttää muuta yhteensopivaa Finlex-MCP:tä, joka tarjoaa työkalut
`get_legislation`, `search_decisions` ja `get_decision`.

## Asennus

Lisää tämä repo markkinapaikkana ja ota plugari käyttöön Claude Codessa:

```
/plugin marketplace add <repo-url tai polku>
/plugin install juristi@claude-for-legal-finland
```

Liitä sen jälkeen oik.ai-konnektori (custom connector → URL `https://oik.ai/mcp` → kirjaudu).
