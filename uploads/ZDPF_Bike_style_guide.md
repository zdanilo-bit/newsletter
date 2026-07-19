# ZDPF Bike — Style Guide Infografiche

Riferimento tipografico/layout per replicare la serie di infografiche nutrizionali (datteri, tart cherry, taurina). Copia questo file come base per ogni nuova scheda.

## Font

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@500;600;700;800&family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@500;700&display=swap" rel="stylesheet">
```

| Font | Uso | Pesi |
|---|---|---|
| **Barlow Condensed** | Titoli hero, h2 sezioni, moment h3, kcal/numeri grandi | 700, 800 |
| **Inter** | Body text, paragrafi, checklist | 400, 500, 600, 700 |
| **JetBrains Mono** | Eyebrow, numeri sezione, label tabella, timeline "when", valori dati | 500, 700 |

Tutto **maiuscolo + text-transform:uppercase** per titoli/eyebrow/label. Body sempre sentence case.

## Palette (CSS variables)

```css
:root{
  --navy:#0B2A42;   /* sfondo header/footer, testo titoli */
  --sea:#155A82;    /* accenti secondari, label tabella */
  --ember:#E15A2C;  /* accenti primari — numeri sezione, check, dot timeline */
  --gold:#F0B429;   /* eyebrow, mega title, badge border */
  --sand:#F4EFE3;   /* sfondo alternato sezioni, card bg */
  --ink:#0B2A42;    /* testo body (= navy) */
}
```

Regola: **una variante di hero per tema**, palette fissa per il resto. Il gradiente hero cambia colore dominante in base al soggetto:

| Scheda | Hero gradient (radial-gradient) |
|---|---|
| Datteri | foto reale con overlay navy |
| Tart cherry | `#6E1030 → #3B0B1D → #1A0510` (bordeaux) |
| Taurina | `#B8460E → #5A2005 → #1A0A02` (arancio caldo) |

Per un nuovo tema: scegli 3 stop di un colore coerente col soggetto, sempre `radial-gradient(circle at 30% 20%, ...)`.

## Struttura pagina (ordine fisso)

```
.wrap (max-width:760px, bg bianco)
 ├─ .hero
 │   ├─ .hero-badge (cerchio + tag SVG, top-right)
 │   ├─ .hero-top → .eyebrow + .mega
 │   └─ .hero-bottom → h1 + p + (opzionale nota tecnica)
 ├─ .profile (divider navy con SVG elevation + 5 label)
 ├─ section 01 → cards + table.data (+ opzionale .dose-warn)
 ├─ section 02 (bg sand) → timeline
 ├─ section 03 → checklist
 ├─ section 04 (opzionale, bg sand) → timeline "come usarlo"
 └─ footer (navy, span sinistra ZDPF Bike / span destra fonte)
```

Sezioni alternano sfondo bianco/sand (`background:var(--sand); padding-top:36px; padding-bottom:44px;` sulle pari).

## Componenti riutilizzabili

### Eyebrow
```html
<div class="eyebrow">ZDPF Bike · Nutrizione in sella</div>
```
Trattino `·` sempre come separatore, non `-` o `|`.

### Hero badge (cerchio in alto a destra)
98×98px, bordo oro 3px, tag SVG a forma di etichetta ruotata -13° in basso a sinistra con testo mono bold (es. "10 G", "30 ML", "50MG/KG" — il dato chiave della dose).

### Section head
```html
<div class="section-head">
  <span class="num">01</span>
  <h2>Titolo sezione</h2>
  <div class="rule"></div>
</div>
```
Numerazione progressiva a 2 cifre, sempre in ember mono bold.

### Cards (metriche in evidenza)
Grid 2 colonne, per dose/quantità chiave. `.qty` = label mono uppercase sea, `.kcal` = numero grande Barlow 800 ember + unità piccola navy.

### Table.data
Riga header nascosta/vuota + righe dato con `.val` allineato a destra in mono bold navy.

### Timeline (momenti/fasi)
Linea tratteggiata verticale ember, pallini oro con bordo navy. Ogni `.moment`: `.when` (mono, ember, uppercase) + h3 (Barlow, navy) + p (Inter, grigio-blu #3A4550).

### Checklist finale
Quadratini con check ember, bold navy per i termini chiave in ogni voce.

### Dose-warn (opzionale)
Box rosso (`#FCEBEB` bg, bordo sinistro ember) per avvertenze tipo dose-risposta non lineare — usalo solo se il dato lo richiede, non di default.

## Regole di scrittura contenuti

- Numeri sempre con **unità esplicita** e fonte tracciabile (DOI, autore, anno) in footer
- Ogni scheda: max 3-4 sezioni numerate, mai di più (altrimenti si sfalda la leggibilità mobile)
- Timeline usata sia per "quando assumere" sia per "effetti osservati" sia per "come testarlo" — è il componente più flessibile della serie
- Footer sempre: `<span>ZDPF Bike</span>` a sinistra, `<span><b>Fonte:</b> ...</span>` a destra

## Responsive breakpoint

```css
@media (max-width:480px){
  .hero-badge{width:76px; height:76px; top:14px; right:14px;}
  .badge-tag{width:40px; bottom:-6px; left:-12px;}
  .hero-top{padding:20px 96px 0 22px;}
  .hero .mega{font-size:36px;}
  .hero h1{font-size:24px;}
  .cards{grid-template-columns:1fr;}
}
```

## Checklist per nuova scheda

1. Copia un HTML esistente (taurina è il più completo, 4 sezioni)
2. Cambia gradient hero + badge tag (colore tema + dato chiave)
3. Aggiorna eyebrow, mega title, h1, p intro
4. Riempi cards (01) con dose/quantità
5. Riempi table.data con dati numerici tracciabili
6. Timeline (02) con 3 momenti/effetti
7. Checklist (03) con 4 punti "da sapere" — sempre bilanciata: pro + limite
8. Footer con fonte (DOI o autore+testata)
