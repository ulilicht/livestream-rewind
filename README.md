# livestream-rewind

Eine einfache Web-App, die einen HLS-Livestream abspielt und automatisch an eine bestimmte Uhrzeit zurückspringt. Voraussetzung ist ein Stream mit DVR-Unterstützung (typischerweise 2h Puffer).

## URL-Parameter

| Parameter | Beschreibung | Beispiel |
|---|---|---|
| `url` | URL-encodierte m3u8 Stream-URL | `url=https%3A%2F%2F...master.m3u8` |
| `target` | Zieluhrzeit (HH:MM) – die App berechnet den Versatz automatisch | `target=19:00` |
| `offset` | Manueller Versatz in Sekunden ab jetzt | `offset=900` |

`target` und `offset` schließen sich gegenseitig aus. Wenn beide angegeben sind, hat `offset` Vorrang.

## Beispiel

```
https://ulilicht.github.io/livestream-rewind/?url=https%3A%2F%2Fzdf-hls-15.akamaized.net%2Fhls%2Flive%2F2016498%2Fde%2Fhigh%2Fmaster.m3u8&target=19:00
```

Öffnet den ZDF-Livestream und springt automatisch auf 19:00 Uhr.

## Player-Funktionen

- Seekbar über das gesamte DVR-Fenster (bis 2h)
- Skip-Buttons: −30s, −10s, +10s, +30s
- 🔴 LIVE-Button springt ans aktuelle Ende
