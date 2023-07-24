---
title: Git und Github
date: 2023-07-21 17:30:00 -0300
last_modified_at: 2023-07-21 17:30:00 -0300
categories: [Git, Github, Anleitung]
tags: [git, github, anleitung]
author: david
image:
  path: /assets/img/GitHub-banner.png
---
# Ein einfacher Leitfaden zu Git und GitHub, erklärt wie für einen Fünfjährigen
Heute werden wir über zwei coole Dinge sprechen: Git und GitHub. Das sind besondere Werkzeuge fürs Programmieren, die dir helfen, deinen Fortschritt zu speichern und deine Arbeit mit anderen zu teilen. Lasst uns das einfach und verständlich erklären!

## Was ist Git?
Gut, also Git ist wie eine magische Speicherkarte für deinen Code. Stell dir vor, du spielst ein Videospiel und möchtest deinen Fortschritt speichern, damit du, wenn etwas schiefgeht, zu diesem Punkt zurückkehren kannst. Nun, Git macht dasselbe für deinen Code! Es hilft dir, deine Änderungen zu speichern, zum Beispiel wenn du neue Dateien hinzufügst oder Code aktualisierst.

### Hier sind die grundlegenden Git-Befehle, die du kennen musst:
1. **Initialisierung eines Git-Repositories:** Wenn du Git in deinem Projektordner verwenden möchtest, sagst du "Hey Git, ich möchte dich hier haben!" und das machst du, indem du `git init` eingibst.

2. **Speichern deiner Änderungen:** Genauso wie wenn du ein Bild von deinem coolen Lego-Gebilde machst, sagst du Git "Hey, ich möchte das speichern!" Das machst du mit dem Befehl `git add .` oder `git add dateiname`, wenn du bestimmte Dateien speichern möchtest.

3. **Bestätigen der Änderungen:** Nun gibst du deinem gespeicherten Bild einen Namen. Wenn du speicherst, musst du sagen, was du gemacht hast, also benutzt du `git commit -m "deine Nachricht"`, um Git zu sagen, welche Änderungen du vorgenommen hast.

4. **Anzeigen der Versionshistorie:** Git behält eine Liste aller gespeicherten Bilder und du kannst sie dir später ansehen. Dazu benutzt du `git log`, um eine Liste all deiner gespeicherten Änderungen anzusehen.

## Was ist GitHub?
Nun, lasst uns über GitHub sprechen. Das ist wie eine besondere Webseite, auf der du deine coolen Lego-Gebilde allen zeigen kannst! Du kannst deinen Code teilen, mit anderen zusammenarbeiten und sehen, was sie bauen.

### So benutzt du GitHub:
1. **Erstelle ein GitHub-Profil:** Zuerst musst du ein spezielles Profil auf GitHub erstellen, genauso wie wenn du dich für ein neues Spiel anmeldest.

2. **Erstelle ein neues Repository:** Das ist wie das Erstellen eines neuen Ordners für deine Lego-Gebilde. Folge den Anweisungen auf der Webseite, um das zu tun.

3. **Verbinde dein lokales Projekt mit GitHub:** Jetzt musst du deinen coolen Lego-Ordner auf deinem Computer mit GitHub verknüpfen. Das machst du, indem du `git remote add origin <repository_url>` eingibst.

4. **Teile deinen Code:** Sobald du einige coole Änderungen gemacht und sie mit Git gespeichert hast, kannst du deinen Code mit GitHub teilen, indem du `git push origin master` verwendest.

### Zusammenarbeit auf GitHub:
1. **Branches:** Stell dir Branches vor wie eigene spezielle Kopien deiner Lego-Gebilde. Du kannst an neuen Sachen arbeiten, ohne das Original durcheinander zu bringen. Um einen Branch zu erstellen, sagst du "Ich möchte eine neue Kopie!" mit `git checkout -b branch_name`.

2. **Zusammenführen (Merging):** Wenn du mit deinen neuen Sachen fertig bist, möchtest du sie vielleicht mit dem Original-Lego-Gebilde kombinieren. Das nennt man Zusammenführen und du kannst es mit einem Pull Request machen.

3. **Änderungen holen (Pulling changes):** Wenn jemand anderes coole Änderungen am Original-Lego-Gebilde auf GitHub vorgenommen hat, kannst du diese Änderungen in dein eigenes Projekt holen, indem du `git pull origin master` verwendest.

## Zusammengefasst
Git ist wie eine Speicherkarte, die deine Code-Änderungen speichert, und GitHub ist wie eine besondere Webseite, auf der du deine Programmierkreationen zeigen und mit anderen zusammenarbeiten kannst. Denkt daran, genau wie mit Lego, Übung macht den Meister, also bleibt am Ball und erkundet die Welt von Git und GitHub! Viel Spaß beim Programmieren!

## Video
**Wenn ihr wolt könnt ihr das englishe video von Nick White dazu anschauen**<br>
{% include embed/youtube.html id='mJ-qvsxPHpY' %}