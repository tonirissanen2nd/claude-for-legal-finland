# Claude for Legal Finland

Avoimen lähdekoodin skillit ja plugarit, jotka auttavat juristeja ja muita
oikeudellisten asioiden parissa työskenteleviä **Suomessa** hyödyntämään Claudea
suomalaisen oikeuden, lakikielen ja oikeuslähteiden ehdoilla. Suomalainen vastine
Anthropicin [claude-for-legal](https://github.com/anthropics/claude-for-legal)
-kokoelmalle.

> [!IMPORTANT]
> **Jokainen näiden plugarien tuotos on tarkistettava luonnos — ei oikeudellista
> neuvontaa, ei oikeudellinen johtopäätös eikä juristin korvaaja.** Plugarit on
> rakennettu suojauksilla, jotka heijastavat tätä: lähdemerkintä jokaiseen
> viittaukseen, lähteestä tarkistettu laki ja oikeuskäytäntö muistin sijaan,
> jurisdiktio-oletukset näkyvissä ja varmistus ennen kuin mitään lähetetään,
> jätetään tai allekirjoitetaan. Pätevä ihminen tarkistaa, varmistaa ja kantaa
> ammatillisen vastuun lopputuloksesta. Nämä työkalut tekevät tarkistuksesta
> nopeampaa; ne eivät korvaa sitä.
>
> Tämä on avoimen lähdekoodin yhteisöhanke, ei viranomais- tai
> asianajopalvelu. Se ei edusta minkään organisaation virallista oikeudellista kantaa.

## Idea

Suomalainen juridinen työ poikkeaa angloamerikkalaisesta: civil law -järjestelmä,
Finlexin säädöskanta, hallituksen esitykset (HE) tulkinta-aineistona, KKO:n ja KHO:n
ennakkopäätökset, pakottava lainsäädäntö ja tarkka lakikieli. Tämä kokoelma rakentaa
Clauden avuksi näiden **aitojen lähteiden** ehdoilla ja kytkeytyy työkaluihin kuten
**oik.ai** ja **Finlex**.

Rakenne mukailee Anthropicin claude-for-legalia: markkinapaikka
([`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json)) listaa
käytäntöaluekohtaiset plugarit. Jokainen plugari sisältää skillit
(`skills/<nimi>/SKILL.md`), jaetut suojaukset (`CLAUDE.md`) ja datakonnektorit
(`.mcp.json`).

## Plugarit

| Plugari | Mitä kattaa | Tila |
|---|---|---|
| **[juristi](juristi/)** | Läpileikkaava perusta: lakikieli ja pykäläviittaukset, suomen kieli, oikeustutkimus (oik.ai/Finlex) ja juridisen asiakirjan monivaiheinen tarkistus. | ✅ Saatavilla |
| **[lainvalmistelu](lainvalmistelu/)** | Säädösvalmistelu: Lainkirjoittajan opas, HE:n laatimisohjeet (HELO), lainvalmistelun prosessiopas, lakikieli. | ✅ Saatavilla |
| **[lausunnot](lausunnot/)** | Lausuntomenettely: lausunnot lakiehdotuksiin, vaikutusarviointi lausunnonantajan näkökulmasta, Lausuntopalvelu.fi. | ✅ Saatavilla |
| sopimukset | Sopimusten laatiminen ja tarkistus Suomen oikeuden mukaan. | 🚧 Tulossa |
| työoikeus | Työsuhteet, TES, yhteistoiminta, päättäminen. | 🚧 Tulossa |
| tietosuoja | Tietosuoja-asetus ja kansallinen tietosuojalaki. | 🚧 Tulossa |
| hallinto-oikeus | Julkishallinto, hallintopäätökset, muutoksenhaku. | 🚧 Tulossa |
| riidanratkaisu | Prosessi yleisissä ja hallintotuomioistuimissa. | 🚧 Tulossa |

## Aloitus

Katso [QUICKSTART.md](QUICKSTART.md). Lyhyesti:

```
/plugin marketplace add <repo-url tai polku>
/plugin install juristi@claude-for-legal-finland
```

## Osallistuminen

Katso [CONTRIBUTING.md](CONTRIBUTING.md). Pääperiaate: oikea toiminta kuuluu
SKILL.md:hen ja perustuu aitoihin lähteisiin; CLAUDE.md-suojaukset ovat varaverkko.

## Lisenssi

[MIT](LICENSE) © 2026 Aku Nikkola.
