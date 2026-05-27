---
name: haastehakemus
description: >
  Riita-asian haastehakemuksen laatiminen ja tarkistus oikeudenkäymiskaaren (4/1734)
  mukaan: kantajan vaatimukset, niiden perusteet, todisteet, oikeudenkäyntikulut,
  toimivalta ja prosessiosoite. Käytä tätä skilliä, kun käyttäjä panee vireille tai
  laatii riita-asian kannetta käräjäoikeudessa, kirjoittaa haastehakemusta, kysyy mitä
  kanteessa on esitettävä, miten vaatimus muotoillaan, tai mainitsee haastehakemuksen,
  kanteen, kantajan, vastaajan tai vireillepanon.
---

# Haastehakemus — riita-asian kanne käräjäoikeudessa

Tämä skill auttaa laatimaan ja tarkistamaan riita-asian haastehakemuksen
oikeudenkäymiskaaren (4/1734) mukaan. Haastehakemus on asiakirja, jolla riita-asia pannaan
vireille käräjäoikeudessa.

> **Vastuuvapaus:** luonnos/arvio tarkistettavaksi — ei oikeudellista neuvontaa eikä
> arvio menestymisestä. Asianajollinen vastuu on toimeksiannon hoitavalla. Katso
> `riidanratkaisu/CLAUDE.md`. Perusteet: `references/riidanratkaisu-perusteet.md`.

## Pakollinen sisältö (oikeudenkäymiskaari 5 luku 2 §)

Lähteestä vahvistettu (oik.ai/Finlex, OK 5:2 §) — haastehakemuksessa on ilmoitettava:

1. **Kantajan yksilöity vaatimus** — mitä tuomioistuimelta vaaditaan, täsmällisesti (esim. tietty euromäärä korkoineen).
2. **Seikat, joihin vaatimus perustuu** — kanteen perusteet (oikeustosiseikat).
3. **Todisteet mahdollisuuksien mukaan** — mitä todisteita kantaja aikoo esittää ja **mitä kullakin todisteella aiotaan näyttää toteen** (teema).
4. **Oikeudenkäyntikuluvaatimus**, jos aiheellinen.
5. **Toimivaltaperuste**, jos se ei muutoin ilmene.

Lisäksi: **tuomioistuimen nimi**, asianosaisten nimet ja kotipaikat, laillisen edustajan/
asiamiehen yhteystiedot, **prosessiosoite** (postiosoite kutsuja ja ilmoituksia varten),
puhelinnumerot. Jos vastaajan yhteystietoja ei tiedetä, kerrottava mitä on tehty niiden
selvittämiseksi. **Allekirjoitus** (asianosainen tai laatija; laatijan ammatti ja asuinpaikka).

> Tarkista voimassa oleva sanamuoto ja mahdolliset muutokset `juristi:oikeustutkimus`-skillillä
> ennen lopullista käyttöä; summaariset (riidattomat) asiat voivat noudattaa kevyempää menettelyä.

## Työnkulku

1. **Selvitä asia:** mitä vaaditaan ja keneltä, mihin vaatimus perustuu, mitä todisteita on, mikä käräjäoikeus on toimivaltainen (vastaajan kotipaikka tai muu peruste).
2. **Tarkista oikeustila lähteestä:** hae aineelliset säännökset (sopimus-, vahingonkorvaus- ym. oikeus) ja niitä tukeva oikeuskäytäntö `oikeustutkimus`-skillillä. Vaatimuksen on nojattava oikeustosiseikkoihin ja oikeusperusteeseen.
3. **Laadi haastehakemus** yllä olevan rakenteen mukaan:
   - Vaatimukset numeroituna ja täsmällisinä.
   - Perusteet jäsenneltyinä (tapahtumat → oikeudellinen peruste).
   - Todisteet teemoineen (kirjalliset todisteet, todistajat).
   - Korko- ja kuluvaatimukset.
4. **Tarkista** ennen jättämistä: täyttyvätkö OK 5:2 §:n kohdat, onko toimivalta perusteltu, ovatko vaatimus ja perusteet linjassa, onko todisteilla teema.

## Tulostemuoto

Tuota haastehakemus muokattavana asiakirjana (uusi: `docx`-skill; olemassa olevan muokkaus
jälkimuutoksin: `adeu`-MCP). Merkitse täydennettävät kohdat hakasulkein ja
`[varmista — asianajajan/lakimiehen tarkistettava]`. Älä esitä menestymisen todennäköisyyttä.

## Raportoi

Tuota haastehakemus + tarkistuslista (OK 5:2 §:n kohdat tehty/puuttuu) lähdemerkinnöin
(aineellinen laki + pykälä `oikeustutkimus`-skillillä, mahdollinen oikeuskäytäntö). Muistuta
määräajoista ja vanhentumisesta (tarkista vanhentumisaika lähteestä, jos relevantti).
