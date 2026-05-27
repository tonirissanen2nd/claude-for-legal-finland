# Pika-aloitus

## 1. Lisää markkinapaikka

Claude Codessa:

```
/plugin marketplace add anthropics/claude-for-legal-finland
```

tai paikallisesta polusta kehittäessä:

```
/plugin marketplace add /polku/claude-for-legal-finland
```

## 2. Asenna plugari

```
/plugin install juristi@claude-for-legal-finland
```

## 3. Liitä oik.ai (suositeltava)

`juristi`-plugarin `oikeustutkimus`-skill hakee voimassa olevan lain ja
oikeuskäytännön oik.ai-MCP:stä. Liitä se:

- **Claude.ai / Claude Desktop:** lisää custom connector osoitteella
  `https://oik.ai/mcp` ja kirjaudu (OAuth). Käyttö edellyttää oik.ai-tiliä.
- **Claude Code:** plugarin `.mcp.json` viittaa oik.ai:hin valmiiksi; hyväksy
  konnektori ja suorita kirjautuminen pyydettäessä.

Ilman MCP-yhteyttä skillit toimivat yhä, mutta merkitsevät lakiviittaukset
muistinvaraisiksi ja kehottavat tarkistamaan ne Finlexistä.

## 4. Kokeile

- "Tarkista tämä sopimus" → `asiakirjan-tarkistus`
- "Mitä kuntalaki sanoo toimivallan siirrosta? Onko KHO-käytäntöä?" → `oikeustutkimus`
- "Korjaa tämän pykäläviittauksen muoto" → `juristi`

## Muista

Jokainen tuotos on tarkistettava luonnos — ei oikeudellista neuvontaa. Ihminen
vastaa lopputuloksesta.
