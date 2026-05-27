# Tietosuoja — jaetut suojaukset ja toimintaperiaatteet

Tämän tiedoston ohjeet koskevat **jokaista** tämän plugarin skilliä. SKILL.md kertoo,
*mitä* tehdään; tämä tiedosto on **varaverkko**.

> **Suunnitteluperiaate:** tietosuojadoktriini kuuluu SKILL.md:hen ja referensseihin. Nämä suojaukset ovat henkivakuutus.

---

## Luonnos, jonka ihminen tarkistaa

Tietosuoja-arvio, seloste ja vastausluonnos ovat **tarkistettavia luonnoksia** — ei oikeudellista neuvontaa. Korkean riskin käsittely, arkaluonteiset tiedot, DPIA:t, kielteiset päätökset rekisteröidyn pyyntöihin ja tulkinnanvaraiset poikkeukset kuuluvat tietosuojavastaavan ja tarvittaessa juristin arvioon. Merkitse tällaiset `[varmista — tietosuojavastaavan/juristin arvioitava]`.

## Oikea sääntelykehys

- Sovellettava sääntely on **EU:n yleinen tietosuoja-asetus (EU) 2016/679 (GDPR)**, jota **tietosuojalaki (1050/2018)** täsmentää ja täydentää (vahvistettu lähteestä). Älä käsittele asiaa pelkästään kansallisena — GDPR on suoraan sovellettava.
- Älä viittaa **kumottuun henkilötietolakiin** (523/1999) voimassa olevana — se on kumottu tietosuojalailla.
- Työelämän käsittelyssä huomioi **laki yksityisyyden suojasta työelämässä (759/2004)**: pakottavaa, työnantajaa sitovaa sääntelyä; suostumus on heikko peruste työsuhteen epätasapainon vuoksi.

## Lähteestä, ei muistista

Tarkista kansallisen lain pykälät **`juristi`-plugarin `oikeustutkimus`-skillillä** (oik.ai/Finlex)
ja GDPR-artiklat EUR-Lexistä ennen viittausta. Älä keksi pykälä- tai artiklanumeroita.
Merkitse tarkistamaton viittaus `[muistinvarainen — tarkista]`.

## Arkaluonteiset tiedot ja korkea riski

Erityiset henkilötietoryhmät (9 art) ja rikostiedot (10 art): käsittely lähtökohtaisesti kielletty ilman nimenomaista poikkeusta. Nosta tämä aina esiin. Laaja arkaluonteisten tietojen käsittely, järjestelmällinen seuranta ja automaattinen päätöksenteko ovat DPIA-lippuja (35 art).

## Määräajat ja ilmoitukset

- Rekisteröidyn pyyntöihin: vastaus **kuukauden** kuluessa (jatko enintään 2 kk perustellusti).
- Tietoturvaloukkaus valvontaviranomaiselle **72 tunnin** kuluessa (33 art); korkean riskin loukkaus myös rekisteröidylle (34 art).
Älä esitä määräaikaa arviona — nämä ovat asetuksen kiinteitä määräaikoja.

## Anonymisointi ennen analyysiä

Kun käsiteltävä asiakirja sisältää henkilötietoja eikä niiden tarvitse päätyä mallille,
**anonymisoi ensin**. Suositeltu työkalu on **PII Shield** (ks. README): se korvaa
henkilötiedot paikkamerkeillä paikallisesti ennen kuin teksti lähtee mallille, ja palauttaa
oikeat tiedot jälkikäteen — *henkilötieto ei mene API:in*. Tämä toteuttaa tietojen
minimoinnin ja tukee turvallista jakamista.

> **Suomalaiset tunnisteet:** PII Shieldin oletustunnistimet eivät vielä tunnista
> **henkilötunnusta (HETU)** eikä **Y-tunnusta** rakenteisesti (vireillä upstream-PR
> gregmos/PII-Shield#4). README kertoo, miten saat FI-tunnistimet käyttöön heti forkista.
> Älä oleta, että HETU/Y-tunnus poistuu automaattisesti ilman näitä — tarkista tulos.

## Käytäntöprofiili (valinnainen)

Organisaation rekisterit, tietosuojavastaavan tiedot ja vakiokäytännöt voi tallentaa tähän
otsikon `## Käytäntöprofiili` alle. Oletuksena tyhjä — älä keksi, vaan kysy käyttäjältä.
