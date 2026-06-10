# Pika-aloitus

Plugarit toimivat sekä **Claude Codessa** (terminaali) että **Claude Coworkissa**
(työpöytäsovellus). Molemmissa käytetään samoja slash-komentoja; Coworkissa
datakonnektorit (oik.ai) lisätään lisäksi asetuksista.

## 1. Lisää markkinapaikka

```
/plugin marketplace add akunikkola/claude-for-legal-finland
```

tai paikallisesta polusta kehittäessä:

```
/plugin marketplace add /polku/claude-for-legal-finland
```

## 2. Asenna plugari — valitse user scope

```
/plugin install juristi@claude-for-legal-finland
```

`juristi` on läpileikkaava perusta, joka kannattaa asentaa aina. Sen päälle
asennetaan oman alan plugarit samalla kaavalla
(`<plugari>@claude-for-legal-finland`): `lainvalmistelu`, `lausunnot`,
`sopimukset`, `tyooikeus`, `tietosuoja`, `tekoalysaantely`, `hallinto-oikeus`,
`riidanratkaisu`, `yhtiooikeus`, `insolvenssi` ja `immateriaalioikeus`.
Koko luettelo skilleineen: [SKILLS.md](SKILLS.md).

Kun kysytään "this project / all projects", **valitse user scope.** Muuten plugari
ei saa lukea projektikansion ulkopuolisia tiedostoja (esim. sopimus Downloadsissa).
User scope ei anna plugarille ylimääräistä pääsyä tiedostoihisi — se vain toimii
mistä tahansa kansiosta.

## 3. Käynnistä uudelleen

- **Claude Code:** sulje ja avaa uudelleen.
- **Cowork:** käynnistä sovellus uudelleen. **Tämä on pakollinen vaihe** — plugari
  ei ole päällä ennen uudelleenkäynnistystä.

## 4. Liitä oik.ai (suositeltava)

`juristi`-plugarin `oikeustutkimus`-skill hakee voimassa olevan lain ja
oikeuskäytännön oik.ai-MCP:stä. Liittäminen riippuu ympäristöstä:

- **Cowork / Claude Desktop / Claude.ai:** **Asetukset → Connectors → Add custom
  connector** → URL `https://oik.ai/mcp` → kirjaudu (OAuth). Käyttö edellyttää
  oik.ai-tiliä.
- **Claude Code:** plugarin `.mcp.json` viittaa oik.ai:hin valmiiksi; hyväksy
  konnektori ja suorita kirjautuminen pyydettäessä.

Ilman MCP-yhteyttä skillit toimivat yhä, mutta merkitsevät lakiviittaukset
muistinvaraisiksi ja kehottavat tarkistamaan ne Finlexistä.

**Paikalliset MCP:t (ei tiliä):** osa plugareista käyttää paikallisia, npx:llä käynnistyviä
MCP-palvelimia, jotka eivät vaadi kirjautumista — **Adeu** (`@adeu/mcp-server`, Word-dokumenttien
redlineäminen jälkimuutoksina) dokumenttiplugareissa ja **EU AI Act** (`@lexbeam-software/eu-ai-act-mcp`)
`tekoälysääntely`-plugarissa. Nämä edellyttävät, että koneella on Node.js asennettuna.

## 5. Kokeile

- "Sain tämän asiakirjan, mitä teen?" → `toimeksianto` (määräaikaskannaus ensin)
- "Tarkista tämä sopimus" → `asiakirjan-tarkistus`
- "Mitä kuntalaki sanoo toimivallan siirrosta? Onko KHO-käytäntöä?" → `oikeustutkimus`
- "Korjaa tämän pykäläviittauksen muoto" → `juristi`
- "Laadi muutos kuntalain 7 §:ään ja sen perustelut HE-muotoon" → `lainvalmistelu`
- "Käy tämä osakassopimusluonnos läpi" → `osakassopimus`
- "Asiakas ei maksa laskuja — mitä vaihtoehtoja?" → `saatavien-perinta` / `maksukyvyttomyysarvio`

## Muista

Jokainen tuotos on tarkistettava luonnos — ei oikeudellista neuvontaa. Ihminen
vastaa lopputuloksesta.
