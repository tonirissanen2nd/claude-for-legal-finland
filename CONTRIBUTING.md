# Osallistuminen

Lyhyet ohjeet niille, jotka kirjoittavat tai muokkaavat tämän repon skillejä ja
plugareita. Tämä ei ole tyyliopas, vaan ne periaatteet, jotka vaikuttavat eniten
tuotoksen laatuun ja turvallisuuteen.

## Suunnitteluperiaate: SKILL.md koodaa oikean toiminnan, CLAUDE.md on varaverkko

Jokainen plugari sisältää kaksi ohjekerrosta:

1. **`<plugari>/skills/<skill>/SKILL.md`** – mitä tämä skill tekee, vaihe vaiheelta.
   Kapea, tehtäväkohtainen rakenne.
2. **`<plugari>/CLAUDE.md`** – jaetut suojaukset ja käytäntöprofiili. Lähdemerkintä,
   ajantasaisuuden pakko, premissien tarkistus, vastuuvapaus, jurisdiktio näkyviin.
   Laaja, plugaritason turvaverkko.

**Jos skillin oikea lopputulos riippuu siitä, että jokin CLAUDE.md-suojaus pelastaa
virheen, jonka SKILL.md olisi tehnyt, se on suunnitteluvirhe.** Vie tieto SKILL.md:hen.
Suojaus jää paikalleen henkivakuutuksena, mutta skill kantaa tarvitsemansa tiedon itse.

## Konkreettiset säännöt

- **Perustu aitoihin lähteisiin.** Tämän repon arvo on siinä, että ohjeet nojaavat
  todellisiin suomalaisiin lähteisiin: Finlex, oik.ai, Lainkirjoittajan opas, HE:n
  laatimisohjeet, Kielitoimiston ohjepankki, säädökset ja oikeuskäytäntö. Älä keksi
  pykäliä, ratkaisutunnuksia tai sääntöjä. Merkitse lähde.
- **Liitä provenienssimerkintä numeroon, älä kappaleeseen.** `[mallin laskelma —
  tarkista]` luvun viereen; `(410/2015, 7 §, Finlex)` lainkohdan perään.
- **Tarkista laki lähteestä, älä muistista.** Kun käytettävissä on oik.ai/Finlex-MCP,
  käytä sitä. Muistinvaraiset väitteet merkitään selvästi.
- **Vastuuvapaus pidetään.** Tuotos on aina tarkistettava luonnos; ihminen vastaa.
- **Kieli kunnossa.** Suomenkieliset skillit noudattavat suomen kielen ja lakikielen
  sääntöjä (ks. `juristi`-plugarin `suomen-kieli`- ja `juristi`-skillit).

- **Noudata jaettua viittausstandardia.** Säädös-, oikeuskäytäntö- ja
  esityöviittauksissa: [`references/viittaustyyli.md`](references/viittaustyyli.md)
  (kolmiportainen varmuusmerkintä, lähdehierarkia, ratkaisutunnusten muodot,
  esimerkkikuri). Älä koskaan väitä ratkaisun sisältöä ilman lähteestä tarkistusta.

## Skillin lisääminen

1. Sijoita skill oikean plugarin alle: `<plugari>/skills/<nimi>/SKILL.md`.
2. Kirjoita selkeä `description`-kenttä frontmatteriin: milloin skill triggeröidään
   (suomalaiset triggerit, säädösnumerot, §-merkki, asiakirjatyypit). Frontmatterissa
   **vain `name` ja `description`** – ei muita kenttiä. `name` = kebab-case = kansion nimi.
3. Jaa yksityiskohdat tarvittaessa `references/`-tiedostoihin ja lue ne Read-työkalulla.
4. Päivitä plugarin README ja tarvittaessa juuren `marketplace.json`.
5. **Päivitä generoidut tiedostot:** `bash scripts/check-generated.sh` ajaa
   molemmat generaattorit (`generate-skills-md.mjs` → `SKILLS.md`,
   `generate-codex.mjs` → Codex-manifestit) ja varmistaa, ettei mitään jäänyt
   committaamatta. Älä muokkaa generoituja tiedostoja (`SKILLS.md`,
   `.codex-plugin/plugin.json`, `agents/openai.yaml`) käsin.
6. **Aja validaattori ja testit ennen pushia:**
   - `node scripts/validate.mjs`
   - `node --test tests/*.test.mjs`
7. **Jos muutit skillin `description`-kenttää**, aja triggeritestit
   (`bash evals/aja-triggeritestit.sh`, ks. [evals/README.md](evals/README.md)) —
   kuvaus on skillin triggeröitymisen ainoa signaali, ja huono muotoilu
   hukkaa skillin hiljaa. Huom: ajaa oikeita mallikutsuja (ei CI:hin).
8. **Jos tilastot muuttuvat** (plugari-, skilli- tai agenttimäärä,
   säädösrekisterin koko, versio), päivitä katselmussivu
   (`docs/index.html` + `docs/en/index.html`) ja regeneroi OG-jakokuvat —
   ohjeet ja renderöintikomennot: [docs/og-source.html](docs/og-source.html).

CI ajaa täsmälleen samat tarkistukset (`check-generated.sh` + validaattori +
testit), joten paikallisesti vihreä tarkoittaa vihreää myös CI:ssä.

## Lisenssi

Osallistumalla hyväksyt, että työsi julkaistaan [MIT](LICENSE)-lisenssillä.
