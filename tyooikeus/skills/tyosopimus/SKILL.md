---
name: tyosopimus
description: >
  Työsopimuksen laatiminen ja tarkistus Suomen työoikeuden mukaan (työsopimuslaki
  55/2001). Käytä tätä skilliä, kun käyttäjä laatii tai tarkistaa työsopimusta,
  kysyy työsuhteen ehdoista, määräaikaisuudesta, koeajasta, kilpailukiellosta,
  salassapidosta, työehtosopimuksen (TES) vaikutuksesta, irtisanomisajoista tai
  työntekijän vähimmäisehdoista. Triggeröi kun mainitaan työsopimus, työsuhde,
  määräaikainen sopimus, koeaika, kilpailukieltosopimus tai työehtosopimus.
---

# Työsopimus — laatiminen ja tarkistus

Tämä skill auttaa laatimaan ja tarkistamaan työsopimuksen Suomen työoikeuden mukaan.
Lähtökohta poikkeaa yleisestä sopimusoikeudesta: **työlainsäädäntö on pakottavaa
työntekijän hyväksi**, ja työehtosopimukset (TES) asettavat vähimmäisehtoja, joista ei
voi poiketa työntekijän vahingoksi.

> **Vastuuvapaus:** luonnos/arvio tarkistettavaksi — ei oikeudellista neuvontaa.
> Katso `tyooikeus/CLAUDE.md`. Perusteet: `references/tyooikeus-perusteet.md`.

## Tarkista pakottava sääntely ja TES ensin

- **Sovellettava työehtosopimus:** selvitä, sitooko alalla yleissitova tai normaalisitova
  TES. TES voi määrätä palkasta, työajasta, lomista ym. työsopimusta sitovammin. Älä laadi
  ehtoa, joka alittaa TES:n tai pakottavan lain vähimmäistason työntekijän vahingoksi.
- Tarkista työsopimuslain (55/2001) ja muiden lakien voimassa olevat säännökset
  **`juristi`-plugarin `oikeustutkimus`-skillillä** (oik.ai/Finlex). Yleinen sopimusmekaniikka:
  `sopimukset`-plugari.

## Työsopimuksen keskeiset ehdot

Käy läpi vähintään:
1. **Osapuolet** ja työnteon alkamisajankohta.
2. **Työtehtävät** ja työntekopaikka.
3. **Sopimuksen kesto:** toistaiseksi voimassa oleva vai **määräaikainen**. Määräaikaisuus edellyttää **perusteltua syytä** (työsopimuslaki 55/2001); toistuvat määräaikaiset ilman perustetta voidaan katsoa toistaiseksi voimassa olevaksi. Työnantajan aloitteesta tehty perusteeton määräaikaisuus on riski → merkitse.
4. **Koeaika:** sallittu laissa säädetyissä rajoissa; pituus ja ehdot tarkistettava lähteestä. Koeajan kuluessa sopimus voidaan purkaa kevyemmin, mutta ei syrjivin tai epäasiallisin perustein.
5. **Palkka** ja palkanmaksukausi (huomioi TES:n vähimmäispalkka).
6. **Työaika** (työaikalaki) ja **vuosiloma** (vuosilomalaki) — tarkista numerot `oikeustutkimus`-skillillä.
7. **Kilpailukieltosopimus:** sallittu vain **erityisen painavasta syystä**, rajoitettu kestoltaan, ja siitä on pääsääntöisesti maksettava **korvaus** (työsopimuslain 2022 uudistuksen jälkeen). Perusteeton tai liian laaja kilpailukielto on osin tehoton → merkitse ja tarkista voimassa oleva säännös lähteestä.
8. **Salassapito**, immateriaalioikeudet ja muut ehdot.
9. **Irtisanomisajat** (laki/TES) ja päättämisen perusteet (ks. `tyosuhteen-paattaminen`-skill).

## Työnkulku

- **Laadinta:** kokoa ehdot yllä olevan mukaan; merkitse täydennettävät kohdat hakasulkein; varmista TES-yhteensopivuus. Tuota uusi sopimus `docx`-skillillä tai olemassa olevan muokkaus `adeu`-MCP:llä (jälkimuutokset).
- **Tarkistus:** käy ehdot läpi pakottavan lain ja TES:n kannalta; nosta esiin ehdot, jotka alittavat vähimmäistason tai ovat työntekijän vahingoksi tehottomia (perusteeton määräaikaisuus, ylilaaja kilpailukielto ilman korvausta, koeaikaehto yli sallitun). Merkitse `[varmista — työoikeusjuristin arvioitava]`.

## Raportoi

Tuota sopimus/arvio lähdemerkinnöin (säädös + pykälä tarkistettuna `oikeustutkimus`-skillillä,
sovellettava TES nimettynä). Erota selvästi pakottava vähimmäistaso, TES-ehto ja
sopimusvapauden piiriin kuuluva ehto.
