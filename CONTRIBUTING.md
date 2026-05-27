# Osallistuminen

Lyhyet ohjeet kenelle tahansa, joka kirjoittaa tai muokkaa tämän repon skillejä ja
plugareita. Tämä ei ole tyyliopas vaan ne periaatteet, jotka eniten vaikuttavat
tuotoksen laatuun ja turvallisuuteen.

## Suunnitteluperiaate: SKILL.md koodaa oikean toiminnan, CLAUDE.md on varaverkko

Jokainen plugari sisältää kaksi ohjekerrosta:

1. **`<plugari>/skills/<skill>/SKILL.md`** — mitä tämä skill tekee, vaihe vaiheelta.
   Kapea, tehtäväkohtainen rakenne.
2. **`<plugari>/CLAUDE.md`** — jaetut suojaukset ja käytäntöprofiili. Lähdemerkintä,
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

## Skillin lisääminen

1. Sijoita skill oikean plugarin alle: `<plugari>/skills/<nimi>/SKILL.md`.
2. Kirjoita selkeä `description`-kenttä frontmatteriin: milloin skill triggeröidään
   (suomalaiset triggerit, säädösnumerot, §-merkki, asiakirjatyypit).
3. Jaa yksityiskohdat tarvittaessa `references/`-tiedostoihin ja lue ne Read-työkalulla.
4. Päivitä plugarin README ja tarvittaessa juuren `marketplace.json`.

## Lisenssi

Osallistumalla hyväksyt, että työsi julkaistaan [MIT](LICENSE)-lisenssillä.
