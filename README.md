# Ballstad International Stockfish & Mountain Camp — nettsiden

Statisk nettside. Ingen byggesteg, ingen avhengigheter — bare HTML, én CSS-fil og bilder.
Kan legges rett på GitHub Pages, Netlify, eller hvilken som helst webserver.

## Sider

| Rute | Fil |
| --- | --- |
| `/` | `index.html` |
| `/om/` | `om/index.html` |
| `/overnatting/` | `overnatting/index.html` |
| `/mountain-adventures/` | `mountain-adventures/index.html` |
| `/program/` | `program/index.html` |
| `/pakkeliste/` | `pakkeliste/index.html` |
| `/booking/` | `booking/index.html` |

Ekte ruter, én mappe per side. Nettleserens tilbakeknapp virker som forventet.
Alle lenker er relative, så siden virker like godt i en undermappe (`bruker.github.io/repo/`)
som på et eget domene.

## Tekst som skal erstattes

Alt som står i `[hakeparentes]` er plassholder fra designet og skal byttes ut:

- **om/** — to avsnitt om vertskapet
- **overnatting/** — ingress, og tallene for rom, senger og fasiliteter
- **mountain-adventures/** — ingress, og navn/tid/grad på toppene
- **program/** — titler og beskrivelser for hver av de fire dagene
- **pakkeliste/** — punktene i de tre kolonnene

Bildeplassholderne (`<div class="placeholder ...">`) byttes ut med `<img>` når bildene finnes:
portrett av vertskapet (16:9) på **om/**, og bilde av rorbua (3:2) på **overnatting/**.

Bookingsiden har en kommentar der et skjema kan settes inn når bookingen åpner.

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
