# Lumora Fadenkreuz

Eigenes Fadenkreuz statt des Vanilla-Kreuzes: gezeichnete Formen, fertige Vorlagen oder ein selbst gemaltes
Pixel-Fadenkreuz, mit Farbe, Umrandung und Skalierung.

Eingebautes Addon des Lumora Clients (Id `lumora-crosshair`, im Spiel: Lumora-Hub → Addons). Läuft in allen 18
unterstützten Minecraft-Versionen (1.8.9 bis 26.3). Standard: **aus**.

> Dieses Repository ist eine **Kopie zum Lesen und Nachschlagen**. Das Addon ist Teil des Clients, weil es an
> Minecraft-Stellen andockt, die sich je Version unterscheiden. Gebaut, getestet und ausgeliefert wird es in
> [LumoraClient/lumora-launcher](https://github.com/LumoraClient/lumora-launcher). Eigene Addons baust du mit dem
> [Addon-Template](https://github.com/LumoraClient/lumora-addon-template).

## Editor

Oben in den Einstellungen sitzt ein Fadenkreuz-Editor mit großer Vorschau und drei Reitern:

- **Formen**: Kreuz mit Lücke, Kreuz, T, X, Kreis, Punkt; Größe, Abstand und Dicke darunter einstellbar.
- **Vorlagen**: 27 fertige Pixel-Fadenkreuze zum Anklicken; „Als eigenes Fadenkreuz bearbeiten“ übernimmt eine Vorlage
  in den Pixel-Editor.
- **Eigene**: 15 × 15-Raster wie beim Vanilla-Fadenkreuz. Linksklick malt, Rechtsklick radiert, Ziehen malt weiter;
  „Spiegeln“ malt in allen vier Vierteln gleichzeitig, dazu Leeren, Umkehren und Vorlage übernehmen.

Darunter ein Farbbalken; Weiß, Schwarz und Deckkraft stehen in der Zeile „Farbe“.

## Einstellungen

| Schlüssel | Bedeutung |
|---|---|
| `mode` | Art: `shape` (Form), `preset` (Vorlage), `custom` (eigenes) |
| `style` | Form |
| `preset` | Id der Vorlage |
| `pixels` | Eigenes Fadenkreuz: 15 Zeilen zu je vier Hex-Ziffern (Bit 14 = linkes Pixel) |
| `scale` | Skalierung von Vorlage und eigenem Fadenkreuz (0,5 bis 3) |
| `size` | Größe |
| `gap` | Abstand zur Mitte |
| `thickness` | Dicke |
| `color` | Farbe |
| `outline` | Umrandung |
| `outline_color` | Farbe der Umrandung |
| `dot` | Punkt in der Mitte |

## Aufbau

| Ordner | Inhalt | Im Haupt-Repository |
|---|---|---|
| `src/` | Das Addon (versionsunabhängig, nur Lumora-API und Lumora-Core) und die gemeinsamen Helfer, die es braucht | `lumora-core/src/main/java/dev/lumora/core/` |
| `hooks/<version>/` | Die Andockstellen je Minecraft-Version (Mixins und Adapter) | `client/mc<version>/src/main/java/dev/lumora/client/` |
| `tests/` | Unit-Tests (laufen im Haupt-Repository) | `lumora-core/src/test/java/` |

## Lizenz

GPL-3.0-or-later (siehe `LICENSE`), wie der ganze Lumora Client.
