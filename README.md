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
> nopeampaa; ne eivät korvaa sitä. Suojan tuottavat **mekanismit** — lähteen
> varmistus, kolmiportainen varmuusmerkintä, premissien tarkistus,
> negatiivirajaus ja ihmisen tarkistusportti — eivät tämä huomautus. Ne on
> koottu tiedostoihin [`references/viittaustyyli.md`](references/viittaustyyli.md)
> ja [`references/vastuu-ja-tietoturva.md`](references/vastuu-ja-tietoturva.md).
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
(`.mcp.json`). Repon juuren [`references/`](references/)-tiedostot määrittävät
jaetut lähde-, vastuu- ja tietoturvastandardit, ja
[`scripts/validate.mjs`](scripts/validate.mjs) (ajetaan CI:ssä) valvoo
markkinapaikan ja skillien rakennetta jokaisessa muutoksessa.

## Plugarit

| Plugari | Mitä kattaa | Tila |
|---|---|---|
| **[juristi](juristi/)** | Läpileikkaava perusta: lakikieli ja pykäläviittaukset, suomen kieli, oikeustutkimus (oik.ai/Finlex) ja juridisen asiakirjan monivaiheinen tarkistus. | ✅ Saatavilla |
| **[lainvalmistelu](lainvalmistelu/)** | Säädösvalmistelu: Lainkirjoittajan opas, HE:n laatimisohjeet (HELO), lainvalmistelun prosessiopas, lakikieli. | ✅ Saatavilla |
| **[lausunnot](lausunnot/)** | Lausuntomenettely: lausunnot lakiehdotuksiin, vaikutusarviointi lausunnonantajan näkökulmasta, Lausuntopalvelu.fi. | ✅ Saatavilla |
| **[sopimukset](sopimukset/)** | Sopimusten laatiminen (rakenne, lausekekirjasto, sopimusoikeus) ja lausekekohtainen riskiarvio Suomen oikeuden mukaan. | ✅ Saatavilla |
| **[työoikeus](tyooikeus/)** | Työsopimus (työsopimuslaki 55/2001), päättämisen arviointi ja yhteistoiminta/muutosneuvottelut (yhteistoimintalaki 1333/2021). | ✅ Saatavilla |
| **[tietosuoja](tietosuoja/)** | Tietosuoja-asetus (GDPR) ja tietosuojalaki: käsittelyn arviointi ja DPIA, tietosuojaseloste, rekisteröidyn pyynnöt. | ✅ Saatavilla |
| **[tekoälysääntely](tekoalysaantely/)** | EU:n tekoälyasetus (AI Act): riskiluokittelu, velvoitteet, määräajat, seuraamukset, GPAI ja FRIA. Avoin, deterministinen EU AI Act -MCP. | ✅ Saatavilla |
| **[hallinto-oikeus](hallinto-oikeus/)** | Hallintopäätös (hallintolaki 434/2003), muutoksenhaku (808/2019) ja asiakirjajulkisuus/tietopyynnöt (julkisuuslaki 621/1999). | ✅ Saatavilla |
| **[riidanratkaisu](riidanratkaisu/)** | Riita-asia yleisissä tuomioistuimissa (oikeudenkäymiskaari 4/1734): haastehakemus, todistelu, muutoksenhaku. | ✅ Saatavilla |

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
