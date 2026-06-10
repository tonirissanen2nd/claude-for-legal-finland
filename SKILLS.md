# Skillit

> Autogeneroitu `scripts/generate-skills-md.mjs`-skriptillä `.claude-plugin/marketplace.json`:sta
> ja kunkin `SKILL.md`:n frontmatterista. Älä muokkaa käsin — aja skripti uudelleen.

Markkinapaikalla on **11 plugaria** ja **33 skilliä**. Asennus: ks. [QUICKSTART.md](QUICKSTART.md).

## Juristi — perusta

`/plugin install juristi@claude-for-legal-finland` — [`./juristi/`](./juristi/)

Läpileikkaava perusta suomalaiseen juridiseen työhön: lakikieli ja pykäläviittaukset, suomen kielen oikeinkirjoitus, oikeustutkimus voimassa olevasta laista ja oikeuskäytännöstä (Finlex/oik.ai-MCP), sekä juridisen asiakirjan monivaiheinen tarkistus. Pohja, johon muut käytäntöaluekohtaiset plugarit nojaavat.

| Skill | Kuvaus |
|---|---|
| [`asiakirjan-tarkistus`](juristi/skills/asiakirjan-tarkistus/SKILL.md) | Juridisen asiakirjan järjestelmällinen monivaiheinen laaduntarkistus suomalaisessa kontekstissa. Käytä tätä skilliä, kun juridinen asiakirja pitää tarkistaa ennen käyttöä: sopimus, lausunto, valitus, hallintopäätös, muistio, sopimusluonnos… |
| [`juristi`](juristi/skills/juristi/SKILL.md) | Suomalaisen oikeuden ja lakikielen yleisapuri. Käytä tätä skilliä AINA kun käyttäjä työskentelee lakien, pykälien, säädösten, sopimusten tai muiden juridisten dokumenttien kanssa — riippumatta siitä, onko käyttäjä juristi vai ei. Triggeröi… |
| [`oikeustutkimus`](juristi/skills/oikeustutkimus/SKILL.md) | Suomalaisen voimassa olevan lainsäädännön ja oikeuskäytännön haku, lukeminen ja oikea viittaaminen oik.ai- tai Finlex-MCP:n avulla. Käytä tätä skilliä AINA kun tarvitaan ajantasaista lakitekstiä, pykälän sisältö, KKO:n tai KHO:n ennakkopää… |
| [`suomen-kieli`](juristi/skills/suomen-kieli/SKILL.md) | Suomen kielen oikeinkirjoitus-, kielioppi- ja tyyliohjeistus verkkosivujen, dokumenttien ja muun sisällön tuottamiseen ja tarkastamiseen. Käytä tätä skilliä AINA kun kirjoitat tai tuotat suomenkielistä tekstiä, tarkistat suomenkielistä sis… |
| [`toimeksianto`](juristi/skills/toimeksianto/SKILL.md) | Uuden toimeksiannon, jutun tai asian aloitus ja aineiston haltuunotto suomalaisessa juridisessa työssä. Käytä tätä skilliä AINA kun käyttäjä aloittaa uuden toimeksiannon tai jutun, tuo asiakirjan tai asiakirjanipun käsiteltäväksi, pyytää j… |

## Lainvalmistelu

`/plugin install lainvalmistelu@claude-for-legal-finland` — [`./lainvalmistelu/`](./lainvalmistelu/)

Säädösvalmistelun apuri: Lainkirjoittajan opas (säädösten rakenne, kieli, viittaaminen, johtolause), hallituksen esitysten laatimisohjeet (HELO), lainvalmistelun prosessiopas ja lakikielen merkit ja taivutusmuodot. Perustuu virallisiin oppaisiin.

| Skill | Kuvaus |
|---|---|
| [`hallituksen-esityksen-laatimisohjeet`](lainvalmistelu/skills/hallituksen-esityksen-laatimisohjeet/SKILL.md) | Hallituksen esitysten laatimisohjeet (HELO) - Opas hallituksen esitysten kirjoittamiseen. Sisältää ohjeet perusrakenteen, EU-taustaisten, valtiosopimustaustaisten ja muiden hallituksen esitysten laatimiseen. |
| [`lainkirjoittajan-opas`](lainvalmistelu/skills/lainkirjoittajan-opas/SKILL.md) | Kattava opas suomalaisen lainsäädännön laadintaan. Lainkirjoittajan opas sisältää keskeisiä ohjeita säädösten laadintaprosessista, rakenteesta, kielestä ja muusta sääntelystä. Hyödyllinen ressurssi lakimiehille, lainsäädäntöä valmistaville… |
| [`lainvalmistelun-prosessiopas`](lainvalmistelu/skills/lainvalmistelun-prosessiopas/SKILL.md) | Opas lainsäädännön valmisteluprosessista Suomessa. Sisältää kaikki vaiheet aloitteesta lain saattamiseen voimaan, mukaan lukien esivalmistelun, perusvalmistelun, lausuntomenettelyn ja jatkovalmistelun prosessit. |
| [`lakikieli-opas`](lainvalmistelu/skills/lakikieli-opas/SKILL.md) | Opas lakikielen merkkien ja taivutusmuotojen käyttöön suomalaisessa säädöstekstissä. Sisältää ohjeet pykälänmerkin, numeroiden, prosenttien, mittayksiköiden, rahayksiköiden, välimerkkien ja lyhenteiden käytöstä lakitekstissä. |

## Lausunnot

`/plugin install lausunnot@claude-for-legal-finland` — [`./lausunnot/`](./lausunnot/)

Lausunnon laatiminen lakiuudistuksiin ja lakiluonnoksiin: lakiehdotuksen analyysi, vaikutusarviointi lausunnonantajan näkökulmasta, muiden lausuntojen tiivistäminen ja perustellun lausunnon kirjoittaminen. Soveltuu kunnille, kuntayhtymille, virastoille, järjestöille ja yrityksille.

| Skill | Kuvaus |
|---|---|
| [`lausuntoapuri`](lausunnot/skills/lausuntoapuri/SKILL.md) | Lausunnon laatiminen lakiuudistuksiin ja lakiluonnoksiin minkä tahansa lausunnonantajan (kunta, kaupunki, kuntayhtymä, virasto, järjestö, yritys) näkökulmasta. Auttaa analysoimaan lakiehdotusta, vertaamaan sitä voimassa olevaan lakiin, tun… |

## Sopimukset

`/plugin install sopimukset@claude-for-legal-finland` — [`./sopimukset/`](./sopimukset/)

Sopimusten laatiminen ja tarkistus Suomen oikeuden mukaan: sopimuksen rakenne ja kommentoitu lausekekirjasto, sopimusoikeuden perusteet sekä lausekekohtainen riskiarvio (VIHREÄ/KELTAINEN/PUNAINEN) kohtuullistamis- ja pakottavan lain lippuineen.

| Skill | Kuvaus |
|---|---|
| [`sopimuksen-laatiminen`](sopimukset/skills/sopimuksen-laatiminen/SKILL.md) | Sopimuksen laatiminen Suomen oikeuden mukaan: rakenne, keskeiset lausekkeet ja sopimusoikeuden perusteet. Käytä tätä skilliä, kun käyttäjä laatii, luonnostelee tai täydentää sopimusta — toimitus-, palvelu-, salassapito-, työ-, vuokra-, toi… |
| [`sopimuksen-tarkistus`](sopimukset/skills/sopimuksen-tarkistus/SKILL.md) | Sopimuksen lausekekohtainen riskiarvio Suomen oikeuden mukaan ja luokittelu (VIHREÄ / KELTAINEN / PUNAINEN). Käytä tätä skilliä, kun käyttäjä haluaa tarkistaa, arvioida tai kommentoida saamaansa tai laatimaansa sopimusta, etsiä siitä riske… |

## Tietosuoja

`/plugin install tietosuoja@claude-for-legal-finland` — [`./tietosuoja/`](./tietosuoja/)

Henkilötietojen käsittelyn tietosuoja EU:n tietosuoja-asetuksen (2016/679) ja tietosuojalain (1050/2018) mukaan: käsittelyn arviointi ja DPIA, tietosuojaseloste ja seloste käsittelytoimista sekä rekisteröidyn tietopyyntöihin vastaaminen.

| Skill | Kuvaus |
|---|---|
| [`rekisteroidyn-pyynnot`](tietosuoja/skills/rekisteroidyn-pyynnot/SKILL.md) | Rekisteröidyn oikeuksien toteuttaminen ja tietopyyntöihin vastaaminen EU:n tietosuoja-asetuksen (15–22 art) mukaan: tarkastusoikeus, oikaisu, poisto, käsittelyn rajoittaminen, siirto-oikeus, vastustaminen ja automatisoidut päätökset. Käytä… |
| [`tietosuoja-arviointi`](tietosuoja/skills/tietosuoja-arviointi/SKILL.md) | Henkilötietojen käsittelyn tietosuoja-arviointi: käsittelyperuste, käsittelyn periaatteet ja vaikutustenarvioinnin (DPIA) tarve EU:n tietosuoja-asetuksen (2016/679) ja kansallisen tietosuojalain (1050/2018) mukaan. Käytä tätä skilliä, kun… |
| [`tietosuojaseloste`](tietosuoja/skills/tietosuojaseloste/SKILL.md) | Tietosuojaselosteen (informointi rekisteröidylle, GDPR 13–14 art) ja käsittelytoimien selosteen (GDPR 30 art) laatiminen EU:n tietosuoja-asetuksen ja tietosuojalain (1050/2018) mukaan. Käytä tätä skilliä, kun käyttäjä laatii tai päivittää… |

## Tekoälysääntely

`/plugin install tekoalysaantely@claude-for-legal-finland` — [`./tekoalysaantely/`](./tekoalysaantely/)

EU:n tekoälyasetuksen (asetus (EU) 2024/1689, AI Act) noudattaminen: tekoälyjärjestelmän riskiluokittelu, velvoitteet roolin ja riskiluokan mukaan sekä määräajat, seuraamukset, GPAI-kynnys ja perusoikeusvaikutusten arviointi (FRIA). Nojaa avoimeen, deterministiseen EU AI Act -MCP:hen.

| Skill | Kuvaus |
|---|---|
| [`tekoaly-luokittelu`](tekoalysaantely/skills/tekoaly-luokittelu/SKILL.md) | Tekoälyjärjestelmän riskiluokittelu EU:n tekoälyasetuksen (asetus (EU) 2024/1689, "AI Act") mukaan: kielletty, korkea riski, rajoitettu riski (läpinäkyvyysvelvoitteet) vai minimaalinen riski. Käytä tätä skilliä, kun käyttäjä haluaa selvitt… |
| [`tekoaly-vaatimustenmukaisuus`](tekoalysaantely/skills/tekoaly-vaatimustenmukaisuus/SKILL.md) | Tekoälyasetuksen (EU 2024/1689) vaatimustenmukaisuuden tukitehtävät: soveltamisen määräajat ja siirtymäajat, seuraamusten (sakkojen) suuruus, GPAI-mallin systeemisen riskin kynnys (10^25 FLOPs) ja perusoikeusvaikutusten arviointi (FRIA, 27… |
| [`tekoaly-velvoitteet`](tekoalysaantely/skills/tekoaly-velvoitteet/SKILL.md) | Tekoälyasetuksen (EU 2024/1689) velvoitteiden selvittäminen roolin (tarjoaja/ käyttöönottaja) ja riskiluokan mukaan sekä korkean riskin järjestelmän teknisen dokumentaation (Annex IV) kokoaminen. Käytä tätä skilliä, kun tekoälyjärjestelmän… |

## Työoikeus

`/plugin install tyooikeus@claude-for-legal-finland` — [`./tyooikeus/`](./tyooikeus/)

Suomen työoikeus: työsopimuksen laatiminen ja tarkistus (työsopimuslaki 55/2001), työsuhteen päättämisen perusteen ja menettelyn arviointi sekä yhteistoiminta ja muutosneuvottelut (yhteistoimintalaki 1333/2021). Pakottavan lainsäädännön ja työehtosopimusten ehdoilla.

| Skill | Kuvaus |
|---|---|
| [`tyosopimus`](tyooikeus/skills/tyosopimus/SKILL.md) | Työsopimuksen laatiminen ja tarkistus Suomen työoikeuden mukaan (työsopimuslaki 55/2001). Käytä tätä skilliä, kun käyttäjä laatii tai tarkistaa työsopimusta, kysyy työsuhteen ehdoista, määräaikaisuudesta, koeajasta, kilpailukiellosta, sala… |
| [`tyosuhteen-paattaminen`](tyooikeus/skills/tyosuhteen-paattaminen/SKILL.md) | Työsuhteen päättämisen arviointi Suomen työoikeuden mukaan (työsopimuslaki 55/2001): irtisanominen (henkilöön liittyvä ja tuotannollis-taloudellinen peruste), purkaminen, koeaikapurku, menettely, irtisanomisajat ja riskien luokittelu. Käyt… |
| [`yhteistoiminta`](tyooikeus/skills/yhteistoiminta/SKILL.md) | Yhteistoiminta ja muutosneuvottelut Suomen yhteistoimintalain (1333/2021) mukaan: jatkuva vuoropuhelu, muutosneuvottelujen edellytykset ja kulku, neuvotteluesitys, määräajat ja soveltamisala. Käytä tätä skilliä, kun käyttäjä suunnittelee t… |

## Hallinto-oikeus

`/plugin install hallinto-oikeus@claude-for-legal-finland` — [`./hallinto-oikeus/`](./hallinto-oikeus/)

Suomen hallinto-oikeus ja julkishallinto: hallintopäätöksen laatiminen ja tarkistus (hallintolaki 434/2003), muutoksenhaku — oikaisuvaatimus ja valitus (laki oikeudenkäynnistä hallintoasioissa 808/2019) — sekä asiakirjajulkisuus ja tietopyynnöt (julkisuuslaki 621/1999).

| Skill | Kuvaus |
|---|---|
| [`hallintopaatos`](hallinto-oikeus/skills/hallintopaatos/SKILL.md) | Hallintopäätöksen laatiminen ja tarkistus hallintolain (434/2003) mukaan: hyvän hallinnon perusteet, asian käsittely, kuuleminen, esteellisyys, päätöksen perustelu ja muutoksenhakuohjaus. Käytä tätä skilliä, kun käyttäjä laatii tai tarkist… |
| [`julkisuus-ja-tietopyynnot`](hallinto-oikeus/skills/julkisuus-ja-tietopyynnot/SKILL.md) | Asiakirjajulkisuus ja tietopyyntöihin vastaaminen julkisuuslain (laki viranomaisten toiminnan julkisuudesta 621/1999) mukaan: julkisuusperiaate, salassapitoperusteet, asiakirjapyyntöön vastaaminen, määräajat ja kielteinen päätös. Käytä tät… |
| [`muutoksenhaku`](hallinto-oikeus/skills/muutoksenhaku/SKILL.md) | Muutoksenhaku hallintopäätökseen Suomen hallintoprosessissa: oikaisuvaatimus, hallintovalitus hallinto-oikeuteen ja valitus korkeimpaan hallinto-oikeuteen (laki oikeudenkäynnistä hallintoasioissa 808/2019), valitusoikeus, määräajat, valitu… |

## Riidanratkaisu

`/plugin install riidanratkaisu@claude-for-legal-finland` — [`./riidanratkaisu/`](./riidanratkaisu/)

Riita-asian ratkaiseminen yleisissä tuomioistuimissa (oikeudenkäymiskaari 4/1734): haastehakemuksen laatiminen, todistelun suunnittelu ja arviointi sekä muutoksenhaku tuomioon (hovioikeus ja jatkokäsittelylupa, korkein oikeus ja valituslupa).

| Skill | Kuvaus |
|---|---|
| [`haastehakemus`](riidanratkaisu/skills/haastehakemus/SKILL.md) | Riita-asian haastehakemuksen laatiminen ja tarkistus oikeudenkäymiskaaren (4/1734) mukaan: kantajan vaatimukset, niiden perusteet, todisteet, oikeudenkäyntikulut, toimivalta ja prosessiosoite. Käytä tätä skilliä, kun käyttäjä panee vireill… |
| [`muutoksenhaku-tuomioon`](riidanratkaisu/skills/muutoksenhaku-tuomioon/SKILL.md) | Muutoksenhaku yleisen tuomioistuimen tuomioon oikeudenkäymiskaaren (4/1734) mukaan: valitus käräjäoikeuden tuomiosta hovioikeuteen ja jatkokäsittelylupa, valitus korkeimpaan oikeuteen ja valituslupa, tyytymättömyyden ilmoitus, määräajat ja… |
| [`todistelu`](riidanratkaisu/skills/todistelu/SKILL.md) | Riita-asian todistelun suunnittelu ja arviointi oikeudenkäymiskaaren (4/1734) 17 luvun mukaan: näyttötaakka, todistuskeinot (asiakirjat, todistajat, asiantuntijat, katselmus, asianosaisen kuuleminen), todistusteemat ja todistelun rajoituks… |

## Yhtiöoikeus

`/plugin install yhtiooikeus@claude-for-legal-finland` — [`./yhtiooikeus/`](./yhtiooikeus/)

Suomen yhtiöoikeus (osakeyhtiölaki 624/2006): perustaminen ja hallinto, yhtiökokous ja hallitustyö, johdon vastuu, varojenjaon kaksoistesti, osakassopimusten laatiminen ja riskitarkistus sekä yritysjärjestelyt due diligence -listoineen.

| Skill | Kuvaus |
|---|---|
| [`osakassopimus`](yhtiooikeus/skills/osakassopimus/SKILL.md) | Osakassopimuksen laatiminen ja riskitarkistus Suomen oikeuden mukaan. Käytä tätä skilliä, kun käyttäjä laatii, neuvottelee, tarkistaa tai tulkitsee osakassopimusta tai sen lausekkeita: päätöksenteko ja hallituspaikat, osakkeiden luovutusra… |
| [`yhtion-hallinto`](yhtiooikeus/skills/yhtion-hallinto/SKILL.md) | Osakeyhtiön perustaminen, hallinto ja johdon vastuu Suomen osakeyhtiölain (624/2006) mukaan. Käytä tätä skilliä, kun käyttäjä perustaa osakeyhtiötä, laatii tai muuttaa yhtiöjärjestystä, valmistelee yhtiökokousta tai hallituksen kokousta (k… |
| [`yritysjarjestelyt`](yhtiooikeus/skills/yritysjarjestelyt/SKILL.md) | Yritysjärjestelyjen oikeudellinen jäsennys Suomen oikeuden mukaan: osakekauppa, liiketoimintakauppa, sulautuminen, jakautuminen ja oikeudellinen due diligence. Käytä tätä skilliä, kun käyttäjä valmistelee, arvioi tai dokumentoi yrityskaupp… |

## Insolvenssi

`/plugin install insolvenssi@claude-for-legal-finland` — [`./insolvenssi/`](./insolvenssi/)

Suomen insolvenssioikeus: maksukyvyttömyystilanteen arviointi ja menettelyn valinta (konkurssi 120/2004, yrityssaneeraus 47/1993, velkajärjestely 57/1993), konkurssimenettely velkojan ja velallisen näkökulmasta sekä saatavien perintä, vanhentuminen ja ulosotto.

| Skill | Kuvaus |
|---|---|
| [`konkurssimenettely`](insolvenssi/skills/konkurssimenettely/SKILL.md) | Konkurssimenettelyn kulku Suomen konkurssilain (120/2004) mukaan velkojan ja velallisen näkökulmasta. Käytä tätä skilliä, kun käyttäjä valmistelee tai arvioi konkurssihakemusta, on saanut tiedon vastapuolen konkurssista, valvoo saatavaa ko… |
| [`maksukyvyttomyysarvio`](insolvenssi/skills/maksukyvyttomyysarvio/SKILL.md) | Maksukyvyttömyystilanteen jäsennys ja menettelyn valinta Suomen insolvenssioikeuden mukaan. Käytä tätä skilliä, kun yrityksen tai yksityishenkilön maksukyky horjuu tai velkaa ei pystytä maksamaan ja pitää arvioida vaihtoehdot: vapaaehtoine… |
| [`saatavien-perinta`](insolvenssi/skills/saatavien-perinta/SKILL.md) | Saatavan perinnän elinkaari Suomen oikeuden mukaan: vapaaehtoinen perintä ja hyvä perintätapa (perintälaki 513/1999), velan vanhentumisen hallinta ja katkaisu (728/2003), oikeudellinen perintä ja ulosotto (ulosottokaari 705/2007). Käytä tä… |

---

*Päivitä tämä tiedosto ajamalla `node scripts/generate-skills-md.mjs`.*
