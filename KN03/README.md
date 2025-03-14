# KN03

## Teil 1

1. Hier habe ich mich mit ssh auf den Ubuntu Server verbunden.
![alt text](../images/kn03-1.png)

2. Hier sind die Versionen von Docker und Podman auf dem Server
![alt text](../images/kn03-2.png)
3. **Podman vs Docker**
Docker nutzt einen dauerhaften Daemon (dockerd), um Container zu verwalten.
Podman arbeitet ohne Daemon, Container laufen direkt im Benutzerkontext.
**Warum ist der Podman-Dienst inactive?**
Podman benötigt keinen ständig laufenden Dienst. Container-Prozesse werden direkt gestartet und laufen unabhängig, was Ressourcen spart.

**Vorteile von Podman**   
   - Sicherer (Rootless-Betrieb)
   - Weniger Ressourcenverbrauch (kein Daemon)
   - Kompatibel mit Docker (gleiche CLI-Befehle)

# Teil 2
### Aufgabe 1
Docker Container anzeigen 
Wenn man ``docker ps -a`` eingibt sieht man folgendes
![alt text](../images/kn03-3.png)
Hier sieht man welche Container aktiviert sind und welche nicht, und man sieht auch welche Ports geöffnet sind und den Namen des Containers, falls man etwas mit dem Container machen will.
Den nginx container kann man mit ``docker run -d -p 8080:80 nginx`` starten.
## **Docker Container VS Virtual Machines**
| Docker-Container| Virtuelle Maschine (VM)|
| :----------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------ |
| Container nutzen eine gemeinsame Kernel-Schicht des Host-Systems und sind leichtgewichtig. | VMs emulieren ein vollständiges Betriebssystem mit eigenem Kernel.              |
| Startet innerhalb von Sekunden.                                                            | Braucht mehr Ressourcen und startet langsamer.                                  |
| Nutzt weniger Speicherplatz, da es nur die Anwendung und Abhängigkeiten enthält.           | Enthält ein komplettes OS (z. B. Debian, Ubuntu), was mehr Speicher verbraucht. |
| Container sind portabel, da sie überall laufen, wo Docker installiert ist.                 | VMs müssen für jedes System einzeln konfiguriert werden.                        |

# Teil 3 OCI-Images mit Docker - RUN & ADMINISTRATION 

## Container
Als erster Schritt wird ein Docker-compose file erstellet, da man dort viele Konfigurationen machen kann. Sowie Passwort Datenbank. Und denn freigegebenen Port kann man auch noch eintragen.

![docker-compose.yml](../images/kn03-6.png)

Als nächster Schritt den Heidisql Client öffnen. Und die Connection-Credentials eingeben, um mich mit der Datenbank verbinden zu können 

![Heidsql Crendetials](../images/kn03-5.png)

Hier muss man IP-Adresse, Benutzer und Password eintragen, damit man sich verbinden kann und wenn es richtig gemacht wurde kann man sich verbinden

![Connection Succesfull](../images/kn03-4.png)

### Mit container Verbinden
Mit ``sudo docker exec -it <<containername>> /bin/bash`` kann man sich mit einem Container verbinden.

# Teil 4
Um den nginx server zu starten, muss man in das KN03 verzeichnsi gehen und folgendes ausführen: ``docker run -d -p 8080:80 automatisiert:latest``

## Image Layering

```Dockerfile
FROM ubuntu:latest
# Erste Layer mit dem Betriebsystem

RUN apt-get update && apt-get install -y \
    apache2 \
    fortune \
    cowsay \
    && rm -rf /var/lib/apt/lists/*
# Zweite Layer, mit dem Aktualisierten packages

COPY index.html /var/www/html/index.html
# Dritte Layer, mit dem index.html file

EXPOSE 80
# Vierte Layer mit dem Exposten Port

CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
# Fünfte Layer mit dem gestarteten Command 

# Sechste Layer mit allem, was danach drauf passiert.
```

![fortune | cowsay](image-1.png)

### Dockerhub push
![Dockerhub gepushtes Image ](image.png)

# Teil 5, Netzwerk
Mit ``docker network create mynetwork`` kann man ein Netzwerk erstellen, mit dem Driver **bridge**.

Dannach kann man mit ``docker network inspect mynetwork`` die Einstellungen des Netzwerkes anschauen.

Und dann kann man mit ``docker network connect mynetwork <<container Name>`` ein Belibigen Container mit den Netzwerk verbinden.