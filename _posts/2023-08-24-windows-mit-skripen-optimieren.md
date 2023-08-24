---
title: Einfache Windows-Skripte und Sicherheitstipps für den Alltag
date: 2023-08-23 10:00:00 -0400
last_modified_at: 2023-08-24 12:00:00 -0400
categories: [Tutorials, Windows]
tags: [BAT-Dateien, Windows-Skripte, Brave-Browser, Softonic, Sicherheit, Datenschutz, "Bat to EXE"]
author: sergius
image:
  path: /assets/img/Sergius-Logo-1200x630.png
---

# Einfache Windows-Skripte und Sicherheitstipps für den Alltag

In diesem Blogbeitrag werden wir uns ansehen, wie man einfache Skripte in Windows erstellt, diese in ausführbare Dateien umwandelt und wie man sicher im Internet surft, insbesondere im Hinblick auf potenziell unerwünschte Download-Portale.

## 1. Erstellung einfacher Skripte in Windows als BAT-Datei

Ein einfaches Beispiel ist das Ein- und Ausblenden von versteckten Dateien.

erstelel eine Datei im Texteditor und benene sie nach vorlieben. Als Dateiendung brauchen wir ``*.bat``

```Dateiendungen anzeigen
@echo off
REG ADD "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v Hidden /t REG_DWORD /d 1 /f
REG ADD "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v ShowSuperHidden /t REG_DWORD /d 1 /f
RUNDLL32.EXE USER32.DLL,UpdatePerUserSystemParameters ,1 ,True
Pfad_zu_nircmd\nircmd.exe sendkeypress f5
```

und eine zum ausblenden

```Dateiendungen verbergen
@echo off
REG ADD "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v Hidden /t REG_DWORD /d 2 /f
REG ADD "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v ShowSuperHidden /t REG_DWORD /d 0 /f
RUNDLL32.EXE USER32.DLL,UpdatePerUserSystemParameters ,1 ,True
Pfad_zu_nircmd\nircmd.exe sendkeypress f5
```

um die geänderten Einstellungen zu sehen, drücke im Explorer `F5` und das war die ganze Magie.

Da war zu einfach, stimmts? Ok, lass uns aus den hässlichen Batch-Dateien ausführbare Dateien machen. Dazu brauchen wir ein Tool namens "Bat to Exe". Such danach im Netz und du wirst eine Menge Quellen finden. Ich benutze gerne vertrauenswürdige Quellen, wie `heise.de`, und dir wird in der Suche bestimmt `softonic` auffallen. ...

... Gönn dir einen Kaffee und lade das Tool herunter:

- [Bat to EXE](https://pyt-academy.github.io/){:target="_blank"} natürlich direkt von der `Heise.de` Webseite

Installiere das Tool, ziehe die `*.bat` Datei hinein und erstelle mit `F9` eine `*.exe`. Das ist die ganze Magie.

Und da du jetzt ein halber Windows Programmierer bist, kannst du zur Übung diesen Code verwenden, um ausführbare Dateien zu erstellen, die den Defender ein- und ausschalten.

```Defender OFF
@echo off
echo Sind Sie sicher, dass Sie den Windows Defender deaktivieren moechten? Druecken Sie die Leertaste zum Bestaetigen.
choice /C " " /N
if errorlevel 2 exit
REG ADD "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender" /v DisableAntiSpyware /t REG_DWORD /d 1 /f
net stop WinDefend
echo Windows Defender wurde deaktiviert.
pause
```

```Defender ON
@echo off
echo Sind Sie sicher, dass Sie den Windows Defender aktivieren moechten? Druecken Sie die Leertaste zum Bestaetigen.
choice /C " " /N
if errorlevel 2 exit
REG DELETE "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender" /v DisableAntiSpyware /f
net start WinDefend
echo Windows Defender wurde aktiviert.
pause
```

Teile mit mir deine Anpassungen und Codesnipsel auf Discord [PYT Discord-Server](https://discord.gg/WxaJcnuXAh) ich nehme sie gerne hier auf, dann haben wir alle was davon.
