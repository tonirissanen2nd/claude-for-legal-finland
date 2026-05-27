# Lainvalmistelu

Säädösvalmistelun apuri suomalaiseen lainsäädäntötyöhön: säädöstekstin ja hallituksen
esityksen laatiminen, rakenne, lakikieli ja valmisteluprosessi. Skillit perustuvat
virallisiin oppaisiin.

> **Jokainen tuotos on valmisteleva luonnos, jonka valmistelusta vastaava taho
> tarkistaa — ei virallinen säädös eikä oikeudellinen kanta.** Katso [`CLAUDE.md`](CLAUDE.md).

## Skillit

| Skill | Lähde | Mitä tekee |
|---|---|---|
| **lainkirjoittajan-opas** | Lainkirjoittajan opas | Säädösten laadinta: säädösten lajit, rakenne, lakikieli, viittaaminen ja johtolause. |
| **hallituksen-esityksen-laatimisohjeet** | HELO | Hallituksen esitysten kirjoittaminen: perusrakenne, mallirakenteet, EU-taustaiset, valtiosopimustaustaiset ja täydentävät esitykset. |
| **lainvalmistelun-prosessiopas** | Lainvalmistelun prosessiopas | Valmisteluprosessi aloitteesta voimaantuloon: esivalmistelu, perusvalmistelu, lausuntomenettely, jatkovalmistelu, päätöksenteko ja eduskunta, täytäntöönpano. |
| **lakikieli-opas** | — | Lakikielen merkit ja taivutusmuodot: pykälänmerkki, numerot, prosentit, mitta- ja rahayksiköt, välimerkit ja lyhenteet säädöstekstissä. |

## Tietolähteet (`.mcp.json`)

- **oik.ai** (`https://oik.ai/mcp`) — säädösvalmistelussa muutettavan lain voimassa olevan
  sanamuodon ja seurannaismuutosten tarkistamiseen sekä relevantin oikeuskäytännön hakuun.
  Vaatii oik.ai-tilin (OAuth liitettäessä).

## Asennus

```
/plugin marketplace add akunikkola/claude-for-legal-finland
/plugin install lainvalmistelu@claude-for-legal-finland
```

Suositus: asenna myös `juristi`-plugari, joka tarjoaa läpileikkaavan oikeustutkimuksen
(`oikeustutkimus`) ja asiakirjan tarkistuksen.
