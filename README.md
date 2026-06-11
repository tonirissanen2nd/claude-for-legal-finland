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
| **[yhtiöoikeus](yhtiooikeus/)** | Osakeyhtiölaki (624/2006): perustaminen ja hallinto, johdon vastuu, varojenjako, osakassopimukset, yritysjärjestelyt ja DD. | ✅ Saatavilla |
| **[insolvenssi](insolvenssi/)** | Maksukyvyttömyys: menettelyn valinta (konkurssi 120/2004, saneeraus 47/1993, velkajärjestely 57/1993), konkurssimenettely, perintä ja ulosotto. | ✅ Saatavilla |
| **[immateriaalioikeus](immateriaalioikeus/)** | IPR: tavaramerkki ja toiminimi (544/2019, 128/1979), tekijänoikeus DSM-uudistuksineen (404/1961), liikesalaisuudet (595/2018). | ✅ Saatavilla |
| **[verotus](verotus/)** | Verotusmenettely ja muutoksenhaku (VML 1558/1995), yritysverotus (EVL 360/1968), arvonlisäverotus (AVL 1501/1993). | ✅ Saatavilla |
| **[julkiset hankinnat](julkiset-hankinnat/)** | Hankintalaki (1397/2016): suunnittelu ja menettelyt, tarjouspyyntö ja tarjous, hankintapäätös ja muutoksenhaku markkinaoikeuteen. | ✅ Saatavilla |
| **[rikosprosessi](rikosprosessi/)** | Esitutkinta ja pakkokeinot (805/2011, 806/2011), syyte ja vastaus (ROL 689/1997), asianomistajan asema ja korvaukset. | ✅ Saatavilla |
| **[ympäristö ja kaavoitus](ymparisto-ja-kaavoitus/)** | Ympäristöluvat (YSL 527/2014), kaavoitus ja rakentaminen (rakentamislaki 751/2023), ympäristövastuut ja -DD. LVV-uudistus 2026 huomioitu. | ✅ Saatavilla |
| **[kiinteistöt ja asuminen](kiinteistot-ja-asuminen/)** | Kiinteistökauppa (maakaari 540/1995), asuntokauppa (843/1994), asunto-osakeyhtiö (1599/2009), vuokrasopimukset (481–482/1995). | ✅ Saatavilla |

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
