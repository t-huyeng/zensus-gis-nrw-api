[[DE]](README.md)/[[EN]](README_en.md)


# [Zensus API - Einwohnerzahlen]

Die vorliegende API ermöglicht es für einen gegebenen Bereich (GeoJSON) die Einwohnerzahlen auf Basis der Zensusdaten abzuschätzen.

Weitere Informationen: https://atlas.zensus2011.de/

### Beispiel

```bash
curl -X 'POST' \
  'https://www.gis-rest.nrw.de/grs/rest/statistik/zensus_2011/einwohner_sum.json' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
  "type": "Feature",
  "geometry": {
    "type": "Polygon",
    "coordinates": [
      [
        [
          8.616714477539062,
          49.89728832544083
        ],
        [
          8.605728149414062,
          49.84506757956392
        ],
        [
          8.690185546875,
          49.83842530390878
        ],
        [
          8.69842529296875,
          49.89419205992558
        ],
        [
          8.616714477539062,
          49.89728832544083
        ]
      ]
    ]
  },
  "crs": {
    "type": "name",
    "properties": {
      "name": "EPSG:4326"
    }
  }
}'
```

Response:

```json
{
  "type": "Feature",
  "properties": {
    "einwohner": 88997.06589856217,
    "grid": "100m"
  }
}
```

