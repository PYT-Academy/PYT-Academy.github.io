---
title: Arch-Linux, mein Setup 
author: sergius
date: 2023-11-03 11:33:00 +0800 #Datumformat entscheidet über die Sortierreinfolge.
categories: [Linux, Arch-Setup Sergius ] #Kategorieauswahl laut Webseite bestimmen.
tags: [Anfänger, Anleitung, Arch, Community, ] #mindestens 3 Tags aus jeweils einzelnen Wörtern verfassen
pin: true #ist zum Anpinnen des Artikels auf den Oberen Rängen. mehrere Angepinnte Artikel werden nach Datum sortiert
math: true #nur für Matematische Formeln im Artikel benötigt
mermaid: true #nur für Mermaid diagramme benötigt
image:
  path: assets/img/blogpost-231103/Arch-kiss.png
  alt: Arch Logo mit KISS-Philosophie (Keep it simple and Stupid)
---

## Begrüßung

Nach monatelangem Distro-Hopping und dem desaster der Desktopmanager bin ich jetzt zu einer Entscheidung gekommen und möchte sie dir vorstellen. Ich benutze 4 Systeme. Zwei sind für die Arbeit das dritte ist für's Studium und das Vierte ist Privat. Hier soll es um das Studium Setup gehen welches später mein Privates Setup erseten wird. 

### warum Arch?

- ist primär eine Persönliche Entscheidung. Ich mag das System hauptsächlich wegen der dahinterstehenden Philosophie und der Community. 
- Wer lesen kann ist ist hier klar im Vorteil. Das meiste ist bereits Dokumentiert, mann muss nur wissen wo ind wie man darauf zugreift.
- Arch bietet ein Minimales Grundsystem und überlässt dem Nutzer sämtliche Entscheidungen über die weitere Konfiguration. Arch zwingt dich dazu sich mit deinem System zu beschäftigen. Das gilt auch für Arch basierende Distributionen (ausnahme bidet Manjaro, von der Disro habe ich mich bereits Distanziert) Aber mein Berufliches Linux System ist EndevourOS und diese Distribution verzichtet bewusst auf Grafische Packetmanager wie es auch die Arch-Wiki empfielt.
- Ich beziehe mich auch oft auch die [Deutschsprachige Arch-Wiki](https://wiki.archlinux.de/title/Hauptseite){:target="_blank"} und deren Unterseiten. Falls es keine Deutschsprachige Anleitung gibt geht es mit der [Englischsprachigen Arch-Wiki](https://wiki.archlinux.org/){:target="_blank"} weiter. Und zu guterletzt geht's weiter ins [Arch-Forum](https://bbs.archlinux.org/){:target="_blank"}. Achtung: wer im Forum Fragen stellt die in der Arch-Wiki beschrieben sind, erntet unter umständen Hohn und Spott. Bitte benutze das Forum ausschließlich wenn du in der Arch-Wiki nicht weiterkommst und verweise auch auf die Entsprechenden Artikel damit sich die Forumleute das genau ansehen können...

### Hardware

hier möchte ich kurz auf die Hardware von meinem Studium-System sprechen. Ich präferiere die ThinkPad Reihe aus 2011. Insbesondere die ThinkPad Modelle [X220](https://thinkwiki.de/X220){:target="_blank"}, [W520](https://thinkwiki.de/W520){:target="_blank"} und das [T420](https://thinkwiki.de/T420){:target="_blank"}. Die Anderen modelle aus der Rheihe sind möglich, jedoch obsolet. es werden die Displaydiagonalen 12,5", 14" und 15" abgedeckt und jedes Modell steht für seinen Zweck top ausgestattet und solide da. In der [Deutschsprachigen ThinkPad-Wiki](https://thinkwiki.de/Hauptseite){:target="_blank"} findest du alle informationen. 

Natürlich gehen auch andere Modelle und neuere Hardware. Fühl dich frei zu nutze was du willst. Ich beziehe meine Anleitungen ausschließlich auf diese Geräte und Arch-Linux basierte Systeme.

### bevor es losgeht

- nutze die `Kommentarfunktion` und schreibe mir bei unklerheiten.
- nutze den 