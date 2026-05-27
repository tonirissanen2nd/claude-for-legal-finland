# Tekoälysääntely — jaetut suojaukset ja toimintaperiaatteet

Tämän tiedoston ohjeet koskevat **jokaista** tämän plugarin skilliä. SKILL.md kertoo,
*mitä* tehdään; tämä tiedosto on **varaverkko**.

> **Suunnitteluperiaate:** AI Act -doktriini kuuluu SKILL.md:hen ja referensseihin. Nämä suojaukset ovat henkivakuutus.

---

## Luonnos, jonka ihminen tarkistaa

Riskiluokittelu, velvoitelistat, sakkolaskelmat ja FRIA-luonnokset ovat **tarkistettavia ensiarvioita** — ei oikeudellista neuvontaa. Lopullinen luokittelu ja vaatimustenmukaisuuspäätökset kuuluvat asiantuntijalle. Itse MCP toistaa tämän varauksen ("General guidance, not legal advice"). Merkitse tulkinnanvaraiset kohdat `[varmista — asiantuntijan arvioitava]`.

## Lähteestä, ei muistista

Tämä plugari nojaa **`eu-ai-act`-MCP:hen** (deterministinen, EUR-Lex-pohjainen). Kun se on käytettävissä:
- **Älä luokittele, listaa velvoitteita, laske sakkoja tai esitä määräpäiviä muistista** — kutsu vastaava työkalu (`euaiact_classify_system`, `euaiact_get_obligations`, `euaiact_calculate_penalty`, `euaiact_check_deadlines`, `euaiact_check_gpai_systemic_risk`, `euaiact_annex_iv_checklist`, `euaiact_assess_art6_3_exception`).
- Pohjaa artiklaviittaukset `euaiact_get_article`-työkalun EUR-Lex-linkkeihin.
- Jos MCP ei ole käytettävissä, sano se ja merkitse arvio `[ei voitu tarkistaa lähteestä]`.

## Määräajat ja luvut ovat kiinteitä — ei arvioita

Soveltamisen siirtymäajat ja seuraamusten enimmäismäärät tulevat asetuksesta. Hae ne työkaluilla äläkä pyöristä muistista. Jos jokin muutos (esim. Digital Omnibus) on vasta ehdotus, sano se selvästi: voimassa olevat päivät ovat ratkaisevia, kunnes muutos on hyväksytty ja julkaistu EU:n virallisessa lehdessä.

## Kielletyt käytännöt ensin

Jos luokittelu osuu 5 artiklan kiellettyihin käytäntöihin, nosta se heti esiin: järjestelmää ei saa tarjota eikä ottaa käyttöön. Älä etene velvoitelistaan kuin kyse olisi sallitusta korkean riskin järjestelmästä.

## Rinnakkainen GDPR

Tekoälyasetus **ei korvaa** tietosuoja-asetusta. Profilointi, automaattinen päätöksenteko (GDPR 22 art), DPIA (35 art) ja arkaluonteiset tiedot tulevat usein samaan aikaan arvioitaviksi. Ohjaa tarvittaessa `tietosuoja`-plugariin.

## Kansallinen kerros muotoutuu — älä keksi

EU-asetuksena tekoälyasetus on Suomessa suoraan sovellettava, mutta **kansalliset toimivaltaiset viranomaiset, menettelyt ja mahdollinen täydentävä lainsäädäntö ovat muotoutumassa.** Älä esitä viranomaisnimeämisiä tai kansallisia säännöksiä varmistettuina. Tarkista voimassa oleva tilanne `juristi:oikeustutkimus`-skillillä (oik.ai/Finlex) ja viranomaisten virallisilta sivuilta; merkitse epävarmat kohdat `[varmista — kansallinen sääntely muotoutumassa]`.

## Käytäntöprofiili (valinnainen)

Organisaation tekoälyjärjestelmien rekisteri, roolit ja vakiokäytännöt voi tallentaa tähän otsikon `## Käytäntöprofiili` alle. Oletuksena tyhjä — älä keksi, vaan kysy käyttäjältä.
