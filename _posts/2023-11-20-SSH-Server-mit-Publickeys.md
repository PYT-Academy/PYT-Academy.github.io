---
title: Debian-SSH-Server mit öffentlichen Schlüsseln einrichten
date: 2023-11-20 14:52:00 -0400
last_modified_at: 2023-11-20 14:52:00 -0400
categories: [Projekte, Server]
tags: [open-source, Self-hosted, Server, Projekt, Cloud, Verein, Cryptomator, Tutorial, SSH, SSH-Schlüssel]
author: karl
comments: true
---

1. **SSH-Server installieren:**  
   Um den SSH-Server in einem Debian-System zu installieren, kannst du den Befehl `apt install openssh-server` verwenden.

1. **Passwordauthentifizierung deaktivieren:**  
   Um die Passwordauthentifizierung auf den SSH-Server zu deaktivieren und nur Authentifizierung via SSH-Schlüssel zuzulassen, kannst du den folgenden Befehl verwenden:
   ```bash
   sudo sed -i 's/^#PasswordAuthentication yes/PasswordAuthentication no/' /etc/ssh/sshd_config
   ```

1. **SSH-Server neustarten:**  
   Damit die gerade gemachte Anpassung wirksam wird, müssen wir den SSH-Server neustarten. Das kann mit dem folgenden Befehl erledigt werden:
   ```bash
   sudo service sshd restart
   ```

1. **SSH-Schlüssel hinzufügen:**  
   Füge alle erlaubten öffentlichen SSH-Schlüssel, mit denen Nutzer auf deinen Server zugreifen können, jeweils mit dem folgenden Befehl hinzu, wobei du „YOUR KEY HERE“ durch deinen SSH-Schlüssel ersetzt (muss mit ssh-rsa oder ähnlichem anfangen). Führe diesen Befehl als der Benutzer aus, auf den die Nutzer zugreifen dürfen:
   ```bash
   echo "ssh-rsa your_public_key_here" >> ~/.ssh/authorized_keys
   ```

Fertig! Ich glaube, hiernach ist kein Neustart des SSH-Servers erforderlich. Probiert es einfach aus!
