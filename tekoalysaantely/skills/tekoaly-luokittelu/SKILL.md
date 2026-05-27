---
name: tekoaly-luokittelu
description: >
  Tekoälyjärjestelmän riskiluokittelu EU:n tekoälyasetuksen (asetus (EU) 2024/1689,
  "AI Act") mukaan: kielletty, korkea riski, rajoitettu riski (läpinäkyvyysvelvoitteet)
  vai minimaalinen riski. Käytä tätä skilliä, kun käyttäjä haluaa selvittää, kuuluuko
  tekoälyjärjestelmä tekoälyasetuksen soveltamisalaan, mikä sen riskiluokka on, onko
  se Annex III -korkean riskin järjestelmä, koskeeko sitä kielto (5 art) tai
  läpinäkyvyysvelvoite (50 art), tai mainitsee tekoälyasetuksen, AI Actin, GPAI:n,
  tekoälyn riskiluokituksen, biometriikan tai profiloinnin.
---

# Tekoälyjärjestelmän riskiluokittelu (EU AI Act)

Tämä skill luokittelee tekoälyjärjestelmän EU:n tekoälyasetuksen (asetus (EU) 2024/1689)
riskiperusteisen kehyksen mukaan ja tunnistaa sovellettavan Annex III -kategorian,
roolin (tarjoaja/käyttöönottaja) ja relevantit artiklat.

> **Vastuuvapaus:** tämä on ensiarvio tarkistettavaksi — ei oikeudellista neuvontaa.
> Lopullinen luokittelu ja vaatimustenmukaisuuspäätökset kuuluvat asiantuntijalle.
> Katso `tekoalysaantely/CLAUDE.md`.

## Käytä EU AI Act -MCP:tä

Tämä skill nojaa **`eu-ai-act`-MCP:hen** (lexbeam, deterministinen, EUR-Lex-pohjainen).
Älä luokittele muistinvaraisesti, kun MCP on käytettävissä.

- **`euaiact_classify_system`** — anna järjestelmän kuvaus (`description`/`use_case`) ja
  mahdollisuuksien mukaan **rakenteiset `signals`** (esim. `domain`, `uses_biometrics`,
  `biometric_realtime`, `is_safety_component_of_regulated_product`,
  `generates_synthetic_content`, `targets_children_or_vulnerable`). Rakenteiset signaalit
  menevät tekstihaun edelle ja antavat deterministisen vastauksen. Palauttaa riskiluokan,
  Annex III -kategorian, roolin, osuneet ja puuttuvat signaalit sekä jatkokysymykset.
- **`euaiact_get_article`** — hae artiklan operatiivinen tiivistelmä ja **EUR-Lex-linkki**
  sitaatin pohjaksi.
- **`euaiact_assess_art6_3_exception`** — käytä ennen kuin nojaat 6(3) "ei merkittävää
  riskiä" -poikkeukseen (huom: ei sovellu profilointia tekeviin järjestelmiin).
- Resurssit `euaiact://annex/iii` ja `euaiact://risk-levels` antavat täydet kategoriat.

Jos MCP ei ole käytettävissä, kerro se ja merkitse arvio `[ei voitu tarkistaa lähteestä]`.
Perusteet ja Suomi-kerros: lue `references/ai-act-perusteet.md`.

---

## Työnkulku

### 1. Kerää signaalit
Selvitä käyttäjältä: mitä järjestelmä tekee, missä kontekstissa, kuka on **tarjoaja**
(provider) ja kuka **käyttöönottaja** (deployer), käsitelläänkö biometriikkaa, tehdäänkö
profilointia tai automaattisia päätöksiä, kohdistuuko se haavoittuviin ryhmiin, onko se
säännellyn tuotteen turvakomponentti, ja tuottaako se synteettistä sisältöä.

### 2. Luokittele
Kutsu `euaiact_classify_system` rakenteisin signaalein. Lue palautuksen `matched_signals`,
`missing_signals` ja `next_questions` — esitä puuttuvat kysymykset käyttäjälle, jos
luokittelu jää epävarmaksi.

### 3. Tulkitse luokka
- **🚫 Kielletty (5 art)** — esim. tietyt manipuloivat, sosiaalisen pisteytyksen tai
  kielletyn biometrisen tunnistuksen käytöt. → Järjestelmää ei saa tarjota/ottaa käyttöön.
- **⚠️ Korkea riski (6 art + Annex III tai Annex I)** — laajat velvoitteet (9–17 art,
  käyttöönottajalle 26–27 art). → Ohjaa `tekoaly-velvoitteet`-skilliin.
- **ℹ️ Rajoitettu riski (50 art)** — läpinäkyvyysvelvoitteet (esim. chatbotista on
  kerrottava käyttäjälle, synteettinen sisältö merkittävä).
- **✅ Minimaalinen riski** — ei erityisvelvoitteita; vapaaehtoiset käytännesäännöt.
- **GPAI (51–56 art)** — yleiskäyttöiset tekoälymallit: tarkista systeeminen riski
  `euaiact_check_gpai_systemic_risk`-työkalulla (`tekoaly-vaatimustenmukaisuus`-skill).

Huomaa **yleinen tekoälylukutaitovelvoite (4 art)**, joka koskee kaikkia tarjoajia ja
käyttöönottajia riskiluokasta riippumatta.

### 4. Raportoi
Tuota: riskiluokka + perustelu, Annex III -kategoria (jos korkea), rooli (tarjoaja/
käyttöönottaja), relevantit artiklat **EUR-Lex-linkein** (`euaiact_get_article`), ja
seuraavat askeleet. Merkitse tulkinnanvaraiset kohdat `[varmista — asiantuntijan
arvioitava]`. Jos kyse on 6(3)-poikkeuksesta, perusta kanta `euaiact_assess_art6_3_exception`
-työkaluun, älä oletukseen.

### 5. Kytkennät
- **Tietosuoja:** jos järjestelmä käsittelee henkilötietoja tai tekee profilointia/
  automaattisia päätöksiä, ohjaa myös `tietosuoja`-plugariin (GDPR 22 art, DPIA).
- **Kansallinen kerros:** Suomen valvontaviranomaiset ja kansallinen täytäntöönpano →
  `references/ai-act-perusteet.md`; tarkista voimassa oleva tilanne `juristi:oikeustutkimus`-skillillä.
