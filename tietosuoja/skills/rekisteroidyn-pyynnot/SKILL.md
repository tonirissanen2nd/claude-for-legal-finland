---
name: rekisteroidyn-pyynnot
description: >
  Rekisteröidyn oikeuksien toteuttaminen ja tietopyyntöihin vastaaminen EU:n
  tietosuoja-asetuksen (15–22 art) mukaan: tarkastusoikeus, oikaisu, poisto, käsittelyn
  rajoittaminen, siirto-oikeus, vastustaminen ja automatisoidut päätökset. Käytä tätä
  skilliä, kun käyttäjä on saanut rekisteröidyltä tietopyynnön tai vaatimuksen, haluaa
  vastata siihen, arvioida onko se hyväksyttävä, tai mainitsee tarkastuspyynnön,
  tietojen poistopyynnön, "oikeuden tulla unohdetuksi", omien tietojen pyytämisen tai
  rekisteröidyn oikeudet.
---

# Rekisteröidyn pyynnöt — oikeuksien toteuttaminen

Tämä skill auttaa käsittelemään rekisteröidyn esittämän pyynnön ja laatimaan vastauksen
EU:n tietosuoja-asetuksen mukaisesti. Oikeudet eivät ole ehdottomia — useimmilla on
edellytyksiä ja poikkeuksia.

> **Vastuuvapaus:** vastausluonnos tarkistettavaksi — ei oikeudellista neuvontaa.
> Kielteinen päätös ja monitulkintainen poikkeus kuuluvat tietosuojavastaavan/juristin
> arvioon. Perusteet: `../tietosuoja-arviointi/references/tietosuoja-perusteet.md`.

---

## Vaihe 1: Tunnista pyyntö ja pyytäjä

- **Mikä oikeus** on kyseessä (alla)? Pyyntö voi olla muodoton — tulkitse sisältö, ei otsikkoa.
- **Tunnista pyytäjä** luotettavasti, jotta tietoja ei luovuteta väärälle (mutta älä vaadi kohtuuttomia lisätietoja).
- **Kirjaa vastaanottopäivä** — määräaika alkaa siitä.

## Vaihe 2: Määräaika

Vastaa **ilman aiheetonta viivytystä ja viimeistään kuukauden kuluessa** pyynnön
vastaanottamisesta (12(3) art). Määräaikaa voi jatkaa enintään **kahdella kuukaudella**,
jos pyynnöt ovat monimutkaisia tai useita — tällöin rekisteröidylle on ilmoitettava
viivästyksestä ja syystä kuukauden kuluessa. Toimenpiteet ovat lähtökohtaisesti maksuttomia.

## Vaihe 3: Arvioi oikeus ja edellytykset

| Oikeus | Artikla | Keskeiset edellytykset / poikkeukset |
|---|---|---|
| **Tarkastusoikeus** | 15 | Oikeus saada jäljennös käsitellyistä tiedoista ja käsittelyn tiedot. Ei saa loukata muiden oikeuksia. |
| **Oikaisu** | 16 | Virheellisten tietojen korjaaminen, puutteellisten täydentäminen. |
| **Poisto ("unohdetuksi")** | 17 | Esim. tietoja ei enää tarvita, suostumus peruttu, käsittely lainvastaista. **Ei sovellu**, jos käsittely on tarpeen mm. lakisääteisen velvoitteen tai oikeusvaateen vuoksi. |
| **Käsittelyn rajoittaminen** | 18 | Esim. tietojen oikeellisuus riitautettu — käsittely jäädytetään selvittelyn ajaksi. |
| **Siirto-oikeus** | 20 | Vain kun käsittely perustuu **suostumukseen tai sopimukseen** ja tehdään automaattisesti. Jäsennelty, yleisesti käytetty, koneluettava muoto. |
| **Vastustamisoikeus** | 21 | Erityisesti oikeutettuun etuun tai yleiseen etuun perustuva käsittely; **suoramarkkinointia saa aina vastustaa**. |
| **Automatisoidut päätökset** | 22 | Oikeus olla joutumatta pelkkään automaattiseen käsittelyyn perustuvan, oikeusvaikutuksia aiheuttavan päätöksen kohteeksi (poikkeuksin). |

Tarkista kansalliset täsmennykset ja mahdolliset erityislain poikkeukset (tietosuojalaki
1050/2018; toimialakohtainen laki) `juristi`-plugarin `oikeustutkimus`-skillillä.

## Vaihe 4: Laadi vastaus

- **Myönteinen:** toteuta toimenpide ja kuvaa, mitä tehtiin. Tarkastuspyyntöön: kokoa tiedot ja käsittelyn 15 art mukaiset tiedot; varmista, ettei jäljennös paljasta sivullisten tietoja.
- **Kielteinen tai osittainen:** perustele, mihin poikkeukseen päätös perustuu, ja kerro rekisteröidylle **oikeus tehdä valitus tietosuojavaltuutetun toimistolle** sekä oikeussuojakeinot. Älä kieltäydy ilman perustetta.
- **Ilmeisen perusteeton tai kohtuuton (etenkin toistuva) pyyntö:** voidaan periä kohtuullinen maksu tai kieltäytyä (12(5) art) — mutta tämä on poikkeus, jota on käytettävä varoen ja perustellen.

Kirjoita vastaus asiallisesti ja selkokielisesti (`juristi:suomen-kieli`). Tuota
vastausluonnos ja tarvittaessa toimenpidelistaus. Merkitse `[varmista — tietosuojavastaavan
arvioitava]` kohtiin, joissa poikkeuksen soveltuminen on tulkinnanvaraista.

## Muista

Jos pyyntö paljastaa laajemman ongelman (esim. tietoja säilytetty liian kauan, peruste
puuttuu), nosta se esiin — yksittäinen pyyntö voi olla oire käsittelyn puutteesta, jonka
korjaaminen kuuluu `tietosuoja-arviointi`-skillille.
