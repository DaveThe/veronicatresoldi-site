# Veronica Tresoldi - Neuropsicomotricista

Sito di [veronicatresoldi.it](https://veronicatresoldi.it), pubblicato con GitHub Pages dal branch `main`.

## Come è fatto

Le pagine sono HTML normale. GitHub Pages le passa attraverso **Jekyll** solo per due motivi:

1. **Parti condivise** in `_includes/` (modificandole si aggiornano tutte le pagine):
   - `head.html`: meta tag SEO, Open Graph, favicon, CSS
   - `schema.html`: dati strutturati dello studio e di Veronica (indirizzo, orari, albo…)
   - `nav.html`: menu (la voce attiva dipende da `nav:` nel front matter della pagina)
   - `footer.html`: footer, pulsante Doctolib, script
   - `icon.html`: icona dallo sprite `images/icons.svg`, es. `{% include icon.html name="phone" %}`
2. **Esclusioni**: i file elencati in `_config.yml` sotto `exclude` restano nel repository ma non
   vengono pubblicati (documentazione, `email_template.html`, `images/originali/`…).

Ogni pagina inizia con un front matter:

```yaml
---
nav: "faq"                  # voce di menu attiva
title: "Titolo della pagina"
description: "Descrizione per Google (150-160 caratteri)"
preload_image: "/images/..." # immagine dell'intestazione
updated: 2026-10-22          # data di ultima modifica, finisce nella sitemap
---
```

`sitemap.xml` si genera da solo con tutte le pagine (tranne quelle con `noindex: true`).

## Struttura

```
├── _config.yml                    # impostazioni, link Doctolib/Google, esclusioni
├── _includes/                     # parti condivise (vedi sopra)
├── index.html                     # Home
├── chi-sono.html
├── servizi/
│   ├── index.html
│   ├── valutazione.html
│   ├── trattamento.html
│   └── supporto-genitoriale.html
├── contatti-e-prenotazioni.html   # modulo EmailJS
├── faq.html
├── privacy-policy.html
├── cookie-policy.html
├── 404.html
├── styles.css
├── script.js                      # menu, FAQ, quiz "Bussola Evolutiva", modulo contatti
├── js/emailjs-4.4.1.min.js        # SDK EmailJS ospitato sul sito
├── fonts/                         # Lato, Arvo, Merriweather (woff2, ospitati sul sito)
├── images/
│   ├── icons.svg                  # icone (Font Awesome Free, CC BY 4.0)
│   └── originali/                 # foto ad alta risoluzione, NON pubblicate
├── docs/                          # proposte da approvare (non pubblicate)
├── ROADMAP.md                     # attività in sospeso (non pubblicato)
└── email_template.html            # copia del template EmailJS (non pubblicato)
```

## Attività frequenti

### Aggiungere o cambiare una foto
1. Metti l'originale in `images/originali/`.
2. Crea una versione ridimensionata in WebP (larghezza massima: 1920px per le intestazioni,
   800px per le altre, più una da 400px per i telefoni) e mettila in `images/`.
   Una foto pubblicata non dovrebbe superare circa 150 KB.

### Modificare una FAQ
Modifica la domanda nella pagina **e** nel blocco JSON-LD in cima a `faq.html`: Google vuole che
coincidano.

### Modulo contatti (EmailJS)
Service ID e template ID sono in `script.js`, la public key in `contatti-e-prenotazioni.html`.
Il template email è nella dashboard EmailJS; `email_template.html` ne è una copia di riferimento.

### Statistiche (GoatCounter, senza cookie)
1. Crea un account gratuito su [goatcounter.com](https://www.goatcounter.com) (es. codice `veronicatresoldi`).
2. Inserisci il codice in `_config.yml` → `goatcounter_code: "veronicatresoldi"`.

Vengono contati anche i click sui pulsanti Doctolib, sul quiz e l'invio del modulo.
Non è stato usato Google Analytics: richiederebbe un banner cookie e il consenso preventivo.

## Sviluppo locale

```bash
gem install jekyll
jekyll serve
```

Poi apri http://localhost:4000.
