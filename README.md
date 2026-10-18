# Preislisten (Zola)

Umschreibung des ursprünglichen [Hugo-Projekts](https://github.com/klaus1958/preisliste) nach **Zola**.

## Unterschiede zu Hugo

| Hugo | Zola |
|------|------|
| `hugo.toml` | `config.toml` |
| `layouts/` + Go Templates | `templates/` + Tera Templates |
| `{{ partial "..." . }}` | `{% include "..." %}` |
| `.Site.Data.xxx` | `load_data(path="data/xxx.yaml")` |
| Front Matter YAML (`---`) | Front Matter TOML (`+++`) |
| `layout: "xyz"` | `template = "xyz.html"` |

## Starten

```bash
# Zola installieren: https://www.getzola.org/documentation/getting-started/installation/
zola serve
# → http://127.0.0.1:1111
```

## Struktur

```
├── config.toml
├── content/
│   ├── _index.md              # Startseite
│   ├── glaspreise.md
│   ├── kontaktlinsenabo.md
│   └── reparatur-optometrie.md  (noch draft)
├── data/
│   ├── preise_glaeser.yaml
│   └── preise_kontaktlinsen_abo.yaml
├── static/css/
│   ├── pico.classless.css
│   └── preisliste.css
└── templates/
    ├── base.html
    ├── index.html
    ├── page.html
    ├── preisliste-glaeser.html
    ├── preisliste-kontaktlinsen-abo.html
    ├── glaeser-preisliste.html
    └── kontaktlinsen-preisliste-abo.html
```

## Daten anpassen

Preise und Produkte einfach in den YAML-Dateien unter `data/` ändern – die Templates rendern sie automatisch.
