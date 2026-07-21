# ZD Bike — Archivio Newsletter

Hub statico che raccoglie le newsletter/infografiche HTML del brand **ZD Bike** (ciclismo). Homepage: `index.html`, con filtri per categoria e griglia di card verso ogni scheda.

Il progetto nasce come modo per **semplificare e rendere visive informazioni** che riguardano principalmente il mondo del ciclismo — allenamento, fisiologia, materiali, dati di prestazione — ma anche curiosità collaterali (nutrizione, clima, mercato) che possono interessare chi pedala. Ogni scheda cita le proprie fonti, sempre verificate (studi scientifici, dati ufficiali, report), per restare affidabile pur nella forma sintetica dell'infografica.

## Newsletter incluse

| # | Titolo | Categoria | File |
|---|--------|-----------|------|
| 01 | Datteri: rifornimento in sella | Nutrizione | `infografica_datteri_bici.html` |
| 02 | La strada misura tutto: Garmin 2026 | Dati globali | `garmin_cycling_intelligence.html` |
| 03 | Taurina contro il caldo | Nutrizione | `infografica_taurina.html` |
| 04 | Tart Cherry per ciclisti | Nutrizione | `infografica_tart_cherry.html` |
| 05 | Bending Spoons: crea valore o lo estrae? | Finanza | `bending_spoons_punti_oscuri.html` |
| 06 | Winspace Cycling: carbonio a prezzo DTC | Dati globali | `winspace_due_diligence.html` |
| 07 | Strava Dashboard | Dati globali | `analisi_dati_strava.html` |
| 08 | Fisica del Ciclismo | Allenamento | `fisica_ciclismo_zdpf.html` |
| 09 | Zona 2: sotto la prima soglia | Allenamento | `zona2_prima_soglia.html` |
| 10 | Perché i piccoli vincono in salita (peso/potenza) | Allenamento | `peso_potenza_ciclismo.html` |
| 11 | Il caldo che ferma le pedalate | Dati globali | `clima_caldo_ciclismo.html` |
| 12 | Tour de France 2026: il montepremi | Finanza | `tour_de_france_2026_montepremi.html` |
| 13 | La qualità del telaio si misura, non si legge sul prezzo | Dati globali | `qualita_telaio_carbonio.html` |

## Struttura

```
index.html          → homepage archivio (filtri + griglia card)
images/logo.png      → logo ZD Bike
*.html               → singole newsletter (una pagina autonoma ciascuna)
```

## Pubblicazione (GitHub Pages)

Caricare nella root del repo, tramite drag&drop:
- `index.html`
- tutti i file `.html` delle newsletter elencate sopra
- la cartella `images/`

Non caricare altri file di lavoro (progetto/versioni DC): non servono al sito pubblicato.

## Note

- Palette: navy `#0B2A42`, sea blue `#155A82`, ember `#E15A2C`, gold `#F0B429`, sand `#F4EFE3`.
- Font: Barlow Condensed (titoli), Inter (corpo), JetBrains Mono (dati/eyebrow).
- Due stili di scheda: infografica dati/nutrizione vs. report finanziario (Bending Spoons, Winspace).
