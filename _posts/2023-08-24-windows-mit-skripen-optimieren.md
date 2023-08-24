---
title: Einfache Windows-Skripte und Sicherheitstipps für den Büro-Alltag
date: 2023-08-23 10:00:00 -0400
last_modified_at: 2023-08-24 12:00:00 -0400
categories: [Tutorials, Windows]
tags: [BAT-Dateien, Windows-Skripte, Brave-Browser, Softonic, Sicherheit, Datenschutz, "Bat to EXE"]
author: sergius
image:
  path: /assets/img/Sergius-Logo-1200x630.png
---

In diesem Blogbeitrag werden wir uns ansehen, wie man einfache Skripte in Windows erstellt, diese in ausführbare Dateien umwandelt und wie man sicher im Internet surft, insbesondere im Hinblick auf potenziell unerwünschte Download-Portale.

## 1. Erstellung einfacher Skripte in Windows als BAT-Datei

Ein einfaches Beispiel ist das Ein- und Ausblenden von versteckten Dateien.

erstel eine Datei im Texteditor und benene sie nach vorlieben. Als Dateiendung brauchen wir ``*.bat``

### Dateiendungen anzeigen

```batch
@echo off
REG ADD "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v Hidden /t REG_DWORD /d 1 /f
REG ADD "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v ShowSuperHidden /t REG_DWORD /d 1 /f
RUNDLL32.EXE USER32.DLL,UpdatePerUserSystemParameters ,1 ,True
Pfad_zu_nircmd\nircmd.exe sendkeypress f5
```

### Dateiendungen verbergen

```batch
@echo off
REG ADD "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v Hidden /t REG_DWORD /d 2 /f
REG ADD "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v ShowSuperHidden /t REG_DWORD /d 0 /f
RUNDLL32.EXE USER32.DLL,UpdatePerUserSystemParameters ,1 ,True
Pfad_zu_nircmd\nircmd.exe sendkeypress f5
```

Doppelklcik auf deine `*.bat`-Datei fürht den Skript aus. Um die geänderten Einstellungen zu sehen, drücke im Explorer `F5` und das war die ganze Magie.

### BAT to exe

Da war zu einfach, stimmts? Ok, lass uns aus den hässlichen Batch-Dateien ausführbare Dateien machen. Dazu brauchen wir ein Tool namens "Bat to Exe". Such danach im Netz und du wirst eine Menge Quellen finden. Ich benutze gerne vertrauenswürdige Quellen, wie [heise.de](https://www.heise.de/download/){:target="_blank"}{:.prompt-tip}

... Gönn dir einen Kaffee und lade das Tool herunter:

- [Bat to EXE](https://www.heise.de/download/product/quick-batch-file-compiler-69417/download/danke?id=da8772aa-2147-4281-bfb8-fe63d4ec5c17){:target="_blank"}{: .prompt-tip } natürlich direkt, kostenlos und Virenfrei von der [heise.de](https://www.heise.de/download/){:target="_blank"}{:.prompt-tip} Download-Webseite

Installiere das Tool, ziehe die `*.bat` Datei hinein und erstelle mit `F9` eine `*.exe`. Das ist die ganze Magie. Die `EXE-File` kannst du beliebing im Aussehen anpassen und auf dem Desktop oder Startmenu plazieren.

### Filterregeln in Brave

Wenn ich im Netz nach Tools suche, lande ich oft bei nicht trauenswürdigen Quellen wie *Softtonic*. Ja genau, die mit den fragwürdigen Downloads, die immer ganz oben in den Suchergebnissen auftauchen. Ehrlich gesagt, ich hab da noch nie was wirklich Brauchbares gefunden. Und wenn du, so wie ich, den Brave-Browser nutzt, dann hab ich einen kleinen Tipp für dich: 

> Blockier einfach alles von softonic.com. Du wirst nichts verpassen, versprochen!
{: .prompt-tip }

Um das zu machen, fügst du einen benutzerdefinierten Filter in Brave hinzu. Hier die Syntax dafür:

```batch
||softonic.com^
```

Und zack – keine nervigen Softonic-Ergebnisse mehr!

## Weitere Skripe zum Üben

Und da du jetzt ein halber Windows Programmierer bist, kannst du zur Übung diesen Code verwenden, um ausführbare Dateien zu erstellen

### Defender OFF

```batch
@echo off
echo Sind Sie sicher, dass Sie den Windows Defender deaktivieren moechten? Druecken Sie die Leertaste zum Bestaetigen.
choice /C " " /N
if errorlevel 2 exit
REG ADD "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender" /v DisableAntiSpyware /t REG_DWORD /d 1 /f
net stop WinDefend
echo Windows Defender wurde deaktiviert.
pause
```

### Defender ON

```batch
@echo off
echo Sind Sie sicher, dass Sie den Windows Defender aktivieren moechten? Druecken Sie die Leertaste zum Bestaetigen.
choice /C " " /N
if errorlevel 2 exit
REG DELETE "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender" /v DisableAntiSpyware /f
net start WinDefend
echo Windows Defender wurde aktiviert.
pause
```

## Fazit und Kommentare

So simle kann Skripten sein, vieles basiert darauf auch das schreiben diesen Block-Artikel wird in der Markdown Skripsprache geschrieben und per Jekyll in eine Statische Webseite generiert.

Teile mit mir deine Anpassungen und Codesnipsel auf Discord [PYT Discord-Server](https://discord.gg/WxaJcnuXAh){:target="_blank"}{: .prompt-tip } ich nehme sie gerne hier auf, dann haben wir alle was davon.
