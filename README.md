# copencrime-data

Data-repo til CopenCrime-appen. Indeholder JSON-filer og billeder der deles mellem iOS og Android udgaverne.

## Struktur

```
copencrime-data/
  events.json       ← alle hændelser med koordinater, kategorier og bilingual tekst
  categories.json   ← kategorier med SF Symbol-navn og hex-farve
  periods.json      ← predefinerede tidsperioder til filter
  images/
    events/
      [event-id].jpg
```

## JSON-format

### Event
```json
{
  "id": "unik-kebab-case-id",
  "categories": ["murder", "ww2"],
  "year": 1944,
  "coordinates": [55.6761, 12.5683],
  "title": { "da": "Dansk titel", "en": "English title" },
  "description": { "da": "Dansk beskrivelse", "en": "English description" },
  "source": "Kildeangivelse",
  "imageURL": null
}
```

### Kategorier
Nye kategorier tilføjes i `categories.json`. Appen henter dem dynamisk — ingen app-opdatering nødvendig.

`icon` bruger SF Symbols-navne. `color` er hex-farve.

## Bidrag
Indhold valideres manuelt inden merge. Alle events skal have:
- [ ] Koordinater (latitude, longitude)
- [ ] Tekst på både dansk og engelsk
- [ ] Mindst én kategori
- [ ] Kildeangivelse
