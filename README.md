# Ballstad International Stockfish & Mountain Camp — nettsiden

Statisk nettside. Ingen byggesteg, ingen avhengigheter — bare HTML, én CSS-fil og bilder.
Kan legges rett på GitHub Pages, Netlify, eller hvilken som helst webserver.

## Sider

| Rute | Fil |
| --- | --- |
| `/` | `index.html` |
| `/om/` | `om/index.html` |
| `/overnatting/` | `overnatting/index.html` |
| `/fit-for-love/` | `fit-for-love/index.html` |
| `/program/` | `program/index.html` |
| `/pakkeliste/` | `pakkeliste/index.html` |
| `/booking/` | `booking/index.html` |

Ekte ruter, én mappe per side. Nettleserens tilbakeknapp virker som forventet.
Alle lenker er relative, så siden virker like godt i en undermappe (`bruker.github.io/repo/`)
som på et eget domene.

## Det som står igjen

Alle plassholdere er borte — både tekst og bilder. Én ting mangler fortsatt:

- **Mottaker for påmeldingen.** `VERTSKAP_EPOST` nederst i `booking/index.html` er tom.
  Uten adresse sier skjemaet fra at ingenting ble sendt; med adresse åpner det
  e-postprogrammet ferdig utfylt. Det er også satt av plass til et ekte skjema der.

Bildene på **fit-for-love/** ligger i `assets/galleri/`. De er 480 px brede, så
galleriet holder kolonnene rundt den bredden for å holde dem skarpe.

Siden het tidligere Mountain Adventures. `mountain-adventures/index.html` er en stubb
som sender videre til `fit-for-love/`, slik at lenker som alt er delt fortsatt virker.

## Lokal visning

```bash
python3 -m http.server 8081
```

## Publisering

Ligger på GitHub Pages: <https://jacobjentoft.github.io/ballstad-camp/>
Push til `main` publiserer automatisk — ingen bygging, ingen action som må kjøre.

Alle sidene har `<meta name="robots" content="noindex">` så lenge teksten er
plassholdere. Lenken virker for alle som får den, men siden dukker ikke opp i Google.
Fjern de sju taggene når det ekte innholdet er på plass.

Det ligger med vilje ingen `robots.txt` her: den ville hindret søkemotorene i å lese
`noindex`-taggen, og da kan adressen havne i søkeresultatene likevel.

## Design

Design og tekst kommer fra `design_handoff_ballstad_camp/`. Fargene, typografien og
spacingen ligger som CSS-variabler og klasser øverst i `styles.css`. Skriftene
(Instrument Serif og Jost) hentes fra Google Fonts.

To avvik fra prototypen, begge for å tåle skjermbredder prototypen ikke ble testet på:
faktarutenettet på **overnatting/** tegner hjelpelinjene på cellene i stedet for i
grid-gapet (ellers blir en tom celle et grått felt når raden brytes), og kolonnene i
**pakkeliste/** har 220px minstebredde i stedet for 240px (ellers faller den tredje
kolonnen ned på egen rad på brede skjermer).
