---
name: asiakirjan-tarkistus
description: >
  Juridisen asiakirjan järjestelmällinen monivaiheinen laaduntarkistus suomalaisessa
  kontekstissa. Käytä tätä skilliä, kun juridinen asiakirja pitää tarkistaa ennen
  käyttöä: sopimus, lausunto, valitus, hallintopäätös, muistio, sopimusluonnos,
  ohjesääntö tai muu oikeudellinen asiakirja. Triggeröi kun käyttäjä pyytää
  tarkistamaan, oikolukemaan tai laadunvarmistamaan juridisen tekstin, etsimään
  riskejä tai aukkoja, tai varmistamaan asiakirjan ennen allekirjoitusta, lähettämistä
  tai jättämistä viranomaiselle tai tuomioistuimeen.
---

# Asiakirjan tarkistus — monivaiheinen juridinen laaduntarkistus

Tämä skill tarkistaa juridisen asiakirjan järjestelmällisesti useassa vaiheessa. Tavoite on löytää virheet, aukot ja riskit ennen kuin asiakirja otetaan käyttöön. **Perusteellisuus menee nopeuden edelle** — huolellinen tarkistus säästää moninkertaisesti ajan, jonka se vie.

> **Vastuuvapaus:** tämä on laadunvarmistuksen apuväline, joka **täydentää** mutta ei korvaa ihmisen oikeudellista harkintaa. Lopullisen arvion asiakirjan laadusta, riskin hyväksymisestä ja käyttöönotosta tekee aina pätevä ihminen. Katso `juristi/CLAUDE.md` → *Vastuuvapaus*.

---

## Lähdetarkistus on pakollinen

Aina kun asiakirja viittaa lakiin, pykälään tai oikeuskäytäntöön ja viittauksen oikeellisuus on olennainen, **käytä `oikeustutkimus`-skilliä** ja tarkista lainkohta oik.ai-/Finlex-MCP:stä. Älä vahvista lakiviittausta muistista. Jos lähdettä ei voi tarkistaa, merkitse löydös `[ei voitu tarkistaa lähteestä]`.

---

## Löydös-skeema

Raportoi jokainen löydös tässä muodossa, jotta ne ovat jäljitettäviä:

```
TUNNUS: [vaihe#-vakavuus-juokseva]
VAKAVUUS: [Kriittinen / Merkittävä / Vähäinen]
VAIHE: [1–8]
SIJAINTI: [pykälä/kohta/sivu]
TYYPPI: [vaihekohtainen luokka]
KUVAUS: [mikä ongelma on]
MIKSI MERKITYKSELLINEN: [vaikutus ja riski]
KORJAUSEHDOTUS: [konkreettinen korjaus]
LUOTTAMUS: [Korkea / Keskitaso / Matala]
TILA: [Avoin / Ohjattu asiantuntijan tarkistukseen]
```

Jokaisessa vaiheessa ilmoitetaan **luottamustaso** ja mahdolliset **pysäytysehdot** (kriittiset ongelmat, jotka on ratkaistava ennen jatkamista).

---

## Vaihe 1 — Asiakirjan ymmärtäminen ja konteksti

Selvitä ennen tarkistusta:
- **Asiakirjatyyppi**: sopimus, lausunto, valitus/oikaisuvaatimus, hallintopäätös, muistio, ohje-/johtosääntö, sopimusluonnos, HE-/säädösluonnos, testamentti, valtakirja jne. Mitkä ovat tämän tyypin vakiintuneet vaatimukset?
- **Jurisdiktio ja oikeudenala**: Suomen kansallinen oikeus, EU-oikeus, Ahvenanmaan erityisasema, alakohtainen sääntely. Mitkä lait ovat relevantteja?
- **Osapuolet ja yleisö**: ketkä ovat osapuolia, kuka lukee, mikä on heidän juridinen osaamisensa ja valta-asemansa (esim. kuluttaja vs. elinkeinonharjoittaja, työnantaja vs. työntekijä, viranomainen vs. asianosainen)?
- **Tarkoitus**: mitä asiakirjan on määrä saada aikaan?
- **Panokset ja riski**: taloudelliset, oikeudelliset ja maineeseen liittyvät seuraukset, jos asiakirja epäonnistuu.

**Pysäytysehto:** jos asiakirjatyyppiä tai jurisdiktiota ei voi määrittää → kysy käyttäjältä ennen jatkamista.

---

## Vaihe 2 — Käytettävyys ja rakenteen palvelevuus

Palveleeko asiakirjan muoto ja rakenne todellista käyttöä?
- Onko muoto oikea sisällölle ja yleisölle? Löytääkö lukija olennaisen (otsikointi, sisällys, selkeät kohdat)?
- Onko velvoitteet, oikeudet, määräajat ja toimet selvästi merkitty? Tietääkö lukija, mitä hänen pitää tehdä ja milloin?
- **Taloudelliset sitoumukset** (jos asiakirjaan liittyy maksuja): ovatko hinnat, irtisanomis- ja peruutusehdot, automaattiset jatkumiset ja korotusmekanismit selvästi ja näkyvästi esillä — ei haudattuna alaviitteeseen?

---

## Vaihe 3 — Kielen ja ilmaisun selkeys

Tunnista kielelliset ongelmat ennen sisällön tarkistusta (korjaukset muuttavat tekstiä).
- **Käytä `juristi`-skilliä ja sen referenssejä** (`references/lakikieli.md`, `references/suomen-kieli.md`): yhdyssanat, pilkutus, pykäläviittausten muoto, 3-3-3-sääntö, johdonmukainen termistö.
- **Monitulkintaisuus**: epämääräiset ilmaukset ("kohtuullinen aika", "viipymättä", "olennainen") — onko ne määritelty tai sidottu kontekstiin?
- **Johdonmukainen termistö**: samasta asiasta sama termi, ei synonyymeja. Vaihteleva termi luo tulkintariidan.
- **Vääräperäinen täsmällisyys**: lupaako teksti tarkkuutta, jota ei voi toteuttaa ("24 tunnin kuluessa", kun todellinen kyky on 2–3 arkipäivää)? Näyttävätkö esimerkkiluettelot tyhjentäviltä, vaikka ovat vain esimerkkejä (lisää "muun muassa")?

---

## Vaihe 4 — Rakenteellinen eheys

- **Sisäiset viittaukset**: osoittavatko kohta- ja liiteviittaukset olemassa oleviin kohtiin? Ei orpoja eikä kehäviittauksia.
- **Numerointi ja otsikot**: juokseva ja yhtenäinen, ei kaksoiskappaleita.
- **Määritelmät**: onko kaikki määritellyt termit todella määritelty ja käytetty johdonmukaisesti? Onko käyttämättömiä tai ristiriitaisia määritelmiä?
- **Ulkoiset viittaukset**: jos olennainen sisältö on vain ulkoisen linkin tai erikseen viitatun asiakirjan takana, joka voi muuttua yksipuolisesti — se on hauras. Merkitse.
- **Täydellisyys**: ovatko luvatut liitteet mukana, allekirjoituslohkot ja osapuolet täydellisiä?

---

## Vaihe 5 — Sisällöllinen oikeellisuus

Jaa kahteen tasoon sen mukaan, mitä voidaan luotettavasti tarkistaa.

### Taso 1 — sisäinen oikeellisuus (korkea luottamus)
- **Sisäinen johdonmukaisuus**: eivätkö kohdat ole keskenään ristiriidassa faktoista?
- **Määritellyt termit**: käytetäänkö niitä määritelmänsä mukaisesti?
- **Laskelmat ja päivämäärät**: täsmäävätkö summat, prosentit ja määräaikalaskelmat? Ovatko päivämäärät loogisia? **Tarkista määräaikojen laskenta** (esim. arkipäivät vs. kalenteripäivät; pyhät; viikonloppuun osuva määräpäivä).
- **Ajantasaisuus**: viittaako asiakirja kumottuun lakiin, vanhentuneeseen standardiin, lakkautettuun viranomaiseen tai vanhaan nimeen (esim. ennen organisaatiouudistusta)?

### Taso 2 — ulkoiset oikeuslähteet (vaatii tarkistuksen lähteestä)
**Tarkista nämä `oikeustutkimus`-skillillä (oik.ai/Finlex), älä muistista:**
- Lakiviittaukset: onko säädösnumero, pykälä ja momentti oikein ja voimassa?
- Oikeustapausviittaukset: onko ratkaisutunnus oikea ja tukeeko ratkaisu väitettä?
- Pakottava lainsäädäntö: onko ehto ristiriidassa pakottavan säännöksen kanssa (esim. työsopimuslaki, kuluttajansuojalaki)?
- HE-viittaukset: onko numero ja sivu oikein?

Merkitse jokainen lähteestä tarkistettava kohta löydökseksi, jossa `LUOTTAMUS: Matala` ja `TILA: Ohjattu asiantuntijan tarkistukseen`, ellei sitä voitu tarkistaa MCP:stä.

**Pysäytysehto:** yli 5 tason 1 oikeellisuusvirhettä → korjaa ennen jatkamista. Keskeisiä lakiviittauksia ei voitu tarkistaa → ohjaa asiantuntijalle.

---

## Vaihe 6 — Täydellisyys ja aukkoanalyysi

- **Kattavuus**: ovatko kaikki tarpeelliset asiat käsitelty? Puuttuuko vakiolausekkeita (esim. sovellettava laki, riidanratkaisu, voimassaolo, irtisanominen, vastuunrajoitus)?
- **Hiljaisuus, joka sattuu**:
  - **Vastuunjako**: onko selvää, kuka tekee mitä? Onko velvoite, jolle ei ole vastuutahoa?
  - **Seuraamukset**: mitä tapahtuu, jos velvoitetta rikotaan? Onko oikeus ilman täytäntöönpanokeinoa?
  - **Etusijasäännöt**: kumpi ehto voittaa ristiriidassa? Onko sovellettu pätevyysjärjestystä?
  - **Siirtymämekaniikka**: miten edetään tilasta A tilaan B — kuka hyväksyy, ilmoittaa, toimii, missä järjestyksessä?
- **Skenaariotestaus**: mitä tapahtuu keskeisissä tilanteissa (sopimusrikkomus, viivästys, ylivoimainen este, irtisanominen)?
- **Asiakirjatyypin pakolliset osat**: sopimukselta sopimuksen syntyedellytykset; valitukselta vaatimukset, perusteet ja määräaika; hallintopäätökseltä perustelut ja muutoksenhakuohje (hallintolaki).

---

## Vaihe 7 — Riski ja pätevyys (riskisignaalit, ei johtopäätöksiä)

**Kaikki tämän vaiheen löydökset ovat riskisignaaleja, jotka vaativat asiantuntijan arvion — eivät lopullisia oikeudellisia johtopäätöksiä.**

- **Pätevyys ja täytäntöönpanokelpoisuus**: voiko ehto olla pätemätön tai sovitteluun johtava? Suomalaisia kiinnekohtia: oikeustoimilain (228/1929) 36 §:n kohtuullistaminen, pakottava kuluttajansuoja, työoikeuden pakottavuus, kilpailukieltojen rajat, sopimussakon kohtuullisuus. **Tarkista relevantit säännökset `oikeustutkimus`-skillillä.**
- **Loogiset ja ehdolliset virheet**:
  - "Jos X niin Y" -rakenteet, joissa ehto on poistettu tai mahdoton.
  - "Molemminpuolinen" velvoite, joka ei tosiasiassa ole symmetrinen.
  - Poikkeus, joka nielee pääsäännön ("paitsi kohdan X sallimissa tapauksissa", kun X sallii kaiken).
- **Sisällölliset epäjohdonmukaisuudet**: vaihteleva huolellisuusstandardi, eri kynnysarvot tai määräajat samankaltaisissa tilanteissa, oikeus joka annetaan ja sitten kumotaan toisaalla.
- **Tasapaino ja yksipuolisuus**: irtisanomis- ja exit-oikeuksien symmetria, kohtuuttomat sopimussakot, yksipuolinen muutosoikeus. Erityishuomio heikomman osapuolen suojaan (kuluttaja, työntekijä, pienyritys vakioehdoissa).

**Suositus** asteikolla: *Etene varauksin / Asiantuntijan tarkistus suositeltava / Asiantuntijan tarkistus pakollinen / Ei käytettäväksi ilman merkittävää korjausta.*

**Pysäytysehto:** kriittisiä riskisignaaleja → ohjaa asiantuntijalle ennen jatkamista.

---

## Vaihe 8 — Valmius käyttöön

- **Tarkoituksenmukaisuus**: täyttääkö asiakirja tehtävänsä? Onko jäljellä [TÄYDENNÄ]-kohtia tai paikkamerkkejä?
- **Ammattimaisuus ja muoto**: onko muotoilu yhtenäistä? Onko kirjoitusvirheitä?
- **Allekirjoitus- ja jättövalmius**: ovatko allekirjoituslohkot, osapuolet ja päivämäärät kunnossa? Täyttääkö asiakirja viranomaisen tai tuomioistuimen muotovaatimukset (esim. valituksen sisältö ja liitteet)?
- **Sävy ja etiikka**: onko sävy asiallinen? Onko mitään harhaanjohtavaa?
- **Aiempien vaiheiden kriittiset löydökset**: onko ne ratkaistu?

**Lopullinen suositus**: *Valmis käyttöön / Valmis ehdolla [X] / Ei valmis — kriittisiä ongelmia jäljellä.*

---

## Loppuraportti

Tuota lopuksi tiivis yhteenveto:

```
========================================
JURIDISEN ASIAKIRJAN TARKISTUSRAPORTTI
========================================
Asiakirja: [nimi/tyyppi]
Päivämäärä: [pvm]
Tarkistaja: Claude (tekoälyavusteinen) — tarkistettava ihmisen toimesta

LÖYDÖSTEN YHTEENVETO
| Tunnus | Vakavuus | Vaihe | Sijainti | Ongelma |
|---|---|---|---|---|

Pikatilasto: Kriittisiä [X] · Merkittäviä [Y] · Vähäisiä [Z]

KOKONAISARVIO: [Valmis / Valmis varauksin / Ei valmis / Vaatii merkittävän korjauksen]

KRIITTISET LÖYDÖKSET: [lista tunnuksineen]

ASIANTUNTIJAN TARKISTUSTA VAATIVAT KOHDAT:
- [lakiviittausten varmistus oik.ai/Finlex]
- [pätevyys- ja kohtuullisuuskysymykset]
- [tulkinnanvaraiset oikeudelliset kannat]

SEURAAVAT TOIMET: [priorisoitu lista]

VASTUUVAPAUS: Tarkistuksen teki tekoäly ja se täydentää, ei korvaa, ihmisen
oikeudellista harkintaa. Käyttäjä vastaa lopputuloksesta.
========================================
```
