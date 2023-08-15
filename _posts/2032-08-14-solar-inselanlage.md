---
title: Solar-Inselanlage für Wohnmobile
date: 2023-08-13 08:00:00 -0400
categories: [DIY, Projekte, Solaranlage]
tags: [Wohnmobil, Solar-Inselanlage, Photovoltaik, Erzeuger, Speicher, Entnahme, LiFePO4, Akkutechnologie, Systemspannung, 48V, Elektrische Versorgung, Großverbraucher, Mittelverbraucher, Kleinverbraucher, Primer-Verbraucher, Sekundär-Verbraucher, Kostenschätzung, Elektrische Absicherung, Energieunabhängigkeit, Off-Grid, Selbstversorgung]
author: sergius
image:
  path: /assets/img/blogpost-230814/230814-blogpost-inselanlage.png
---

## Solar-Inselanlage für Wohnmobile

Eine **Solar-Inselanlage**, auch als autarkes Solarsystem oder Off-Grid-Solarsystem bezeichnet, ist ein eigenständiges Energieerzeugungssystem, das nicht mit dem öffentlichen Stromnetz verbunden ist. Für Wohnmobile bietet es die Möglichkeit, unabhängig von externen Stromquellen zu sein, besonders nützlich für Reisen in abgelegene Gebiete.

### Hauptkomponenten

1. **Solarmodule**: Wandeln Sonnenlicht in elektrische Energie um.
2. **Batteriespeicher**: Speichert Energie für Zeiten ohne Sonneneinstrahlung, z.B. nachts.
3. **Laderegler**: Steuert den Ladevorgang der Batterien.
4. **Wechselrichter**: Wandelt Gleichstrom in Wechselstrom um.
5. **Überwachungs- und Steuerungssystem**: Ermöglicht die Überwachung und Anpassung der Anlage.

### Vorteile

- **Unabhängigkeit**: Ideal für Reisen in abgelegene Gebiete.
- **Umweltfreundlich**: Reduziert den CO2-Fußabdruck.
- **Skalierbarkeit**: Kann bei Bedarf erweitert werden.

### Nachteile

- **Anfangsinvestition**: Kann teuer sein.
- **Wartung**: Regelmäßige Pflege und möglicher Austausch von Teilen.
- **Energieverfügbarkeit**: Abhängig von der Sonneneinstrahlung und Batteriekapazität.

Solar-Inselanlagen für Wohnmobile sind eine großartige Lösung für diejenigen, die Unabhängigkeit auf ihren Reisen suchen. Eine sorgfältige Planung und Wartung sind jedoch unerlässlich.

## Step 1: Aufgabenstellung: Elektrische Versorgung eines Wohnmobils

Es handelt sich um ein kleines Wohnmobil, das Helmut, einem Freund, gehört. Nach einer ersten Besprechung des Projekts und der Erläuterung der technologischen Grundlagen wurde das Gesamtprojekt in drei Hauptthemen unterteilt: **Erzeuger**, **Speicher** und **Entnahme**.

### Erzeuger

Die Energieerzeugung erfolgt durch **Photovoltaik-Module**, die entweder:

- Direkt auf dem Dach montiert werden
- Oder extern aufgestellt werden können

### Speicher

Hierbei handelt es sich um einen Akku. Es wurde über die verschiedenen Akkutechnologien diskutiert, wobei die **LiFePO4-Technologie** als bevorzugte Option in Betracht gezogen wurde. Als Systemspannung haben wir uns vorläufig für **48V** entschieden, obwohl auch 24V oder 12V möglich wären. Die endgültige Entscheidung bezüglich der Systemspannung wurde als Detailpunkt zur späteren Klärung vorgemerkt.

### Entnahme

Die Entnahme bezieht sich auf die elektrische Absicherung und Verteilung im Wohnmobil. Sie wurde in drei Kategorien unterteilt:

1. **Großverbraucher**: Wechselstromverbraucher mit 230V und 2500W Nominallaeitung und 3500W Peakleistung
2. **Mittelverbraucher**: Gleichstrom mit ca. 600W, z.B. Kühlschrank, Küchengeräte, Primerverbraucher wie Heizungen bis 500W Infarotstrahler. *Hinweis*: Die Beschaffung der Geräte aus dem üblichen Markt muss geplant werden. Bei DC-Anschluss ist entweder ein Umbau oder die direkte Beschaffung von DC-Verbrauchern zu berücksichtigen.
3. **Kleinverbraucher**: Alles bis 100W, z.B. Handy, Laptop, Primerverbraucher wie Beleuchtung, Haustechnik, Pumpen usw.

Zwischen diesen Verbrauchsklassen wird weiter differenziert, ob es sich um **Primer-** oder **Sekundär-Verbraucher** handelt.

> **Anmerkung**: Eine System-Skizze, die alle Komponenten und ihre Abhängigkeiten zeigt, ist beigefügt.

![Erste Skizze der Solar-Inselanlage](/assets/img/blogpost-230814/230814-Schema-Inselanlage.png)
_Erste Skizze der Solar-Inselanlage_

---

## Step 2: Planung und Kostenschätzung der Inselversorgung

Für die Planung wurden Annahmen getroffen über den Bedarf. Wobei der eigentliche Bedarf noch von Helmut definiert werden sollte. Die Annahmen zusammengefasst betreffen die Entnahme und zum anderen wird der Fokus auf eine preiswerte Lösung gelegt. Die daraus folgenden Entscheidungen sind:

- **48V Systemspannung**: Der Erzeuger muss 48V liefern, um den 48V Akku laden zu können. Die 48V werden vom Akku bis zur Zentralabsicherung weitergegeben. Aus Kostengründen wird auf einen Direktverbrauch der solar gewonnenen Energie verzichtet. Eine Erweiterung oder Ausrüstung ist möglich, solange die Systemspannung bei 48V belassen wird.
- Die Komponenten wurden anhand der Systemübersicht bei Ebay recherchiert. Die Hauptkomponenten wurden in einer Vorkalkulation aufgeführt und die erste Schätzung i.h.v. 1550€ wurde ermittelt und notiert.

> **Anlage**: Kostenschätzung

![erte Kostenschätzung](/assets/img/blogpost-230814/230814-kostenschatzung-Inselanlage.png)
_Erste Kostenschätzung der Solar-Inselanlage_

## Entscheidungsfindung: DIY vs. Vorgefertigte Solar-Inselanlage

Bei der Planung und Umsetzung eines Projekts, insbesondere eines so wichtigen wie der autarken Energieversorgung für ein Wohnmobil, ist es entscheidend, alle Optionen sorgfältig zu prüfen. Das Ziel ist es, das bestmögliche Ergebnis zu erzielen, das sowohl `funktional` als auch `wirtschaftlich` sinnvoll ist. In diesem Sinne möchten wir die Vor- und Nachteile von zwei Ansätzen gegenüberstellen: dem DIY (Do It Yourself) und dem Kauf einer vorgefertigten Lösung.

| Kriterium | DIY (Do It Yourself) | Vorgefertigte Lösung |
|-----------|----------------------|----------------------|
| **Kosten** | Oft kostengünstiger durch den Kauf einzelner Teile. | Oft teurer, aber mit dem Vorteil der Optimierung und Integration. |
| **Anpassbarkeit** | `Hoch anpassbar an individuelle Bedürfnisse.` | Erweiterbar durch den Kauf weiterer Module. |
| **Lernmöglichkeit** | `Bietet die Chance, viel über die Technologie zu lernen.` | Weniger Lernmöglichkeiten, da alles vorgefertigt ist. |
| **Zeitaufwand** | Kann zeitaufwändig sein (Recherche, Beschaffung, Montage). | `Schnellere Installation durch Plug-and-Play`. |
| **Zuverlässigkeit** | Abhängig von individuellem Fachwissen, Montage und Planung. | Oft `von Fachleuten entworfen und getestet`. |
| **Garantie** | Oft keine umfassende Garantie. | In der Regel mit Garantie. |
| **Erweiterbarkeit** | `Einfacher und günstiger zu erweitern oder zu modifizieren`. | Erweiterbar durch den Kauf weiterer Module. |
| **Abhängigkeit** | wird auf mehere Anbieter verteilt sowie eigenverantwortung bei Problemen | Abhängigkeit vom Hersteller bei Problemen oder Erweiterungen. |

Während der DIY-Ansatz die Möglichkeit bietet, ein System genau nach den eigenen Vorstellungen zu gestalten, bieten vorgefertigte Lösungen eine gewichts- und platzoptimierte, transportable Option, die besonders interessant sein kann, wenn Strom abseits des Wohnmobils benötigt wird.

Ich bin bestrebt, die beste Lösung zu finden, die sowohl funktional als auch wirtschaftlich sinnvoll ist. Dabei möchte ich alle verfügbaren Optionen sorgfältig prüfen und mich nicht nur auf meine DIY-Begeisterung verlassen. Es geht darum, die optimale Lösung für das Projekt zu finden und dabei alle Aspekte zu berücksichtigen.
