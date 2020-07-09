## Installation:
- ### Windows 10 Pro / Enterprise / Education:
    - Check that you have **Build 19041** or higher:
      - Drücke Windows + R
      - Trage im Dialog: `winver` ein und klicke auf OK
      - Überprüfen Sie ihre Windows Version. Wenn nötig bitte updaten.
      ![Windows Version](https://raw.githubusercontent.com/Flusinerd/Uni-Docker-Manual/master/images/windows-version.jpg)
    - [Download](https://hub.docker.com/editions/community/docker-ce-desktop-windows/) Docker Desktop von DockerHub
    - Führen Sie die Installation aus.
    - Falls gefragt wird, stellen Sie sicher, dass ``Enable Hyper-V Windows Features`` ausgewählt ist.
- ### Windows 10 Home:
    - Stellen Sie sicher, dass sie Windows **Version 2004** or neuer haben:
      - Drücken Sie Windows + R.
      - Trage im Dialog: `winver` ein und klicke auf OK
      - Überprüfen Sie ihre Windows Version. Wenn nötig bitte updaten.
      - **DEN PC NEUSTARTEN!!!**
    - [Downloaden](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi) Sie das Linux Kernel Update und installieren Sie es.
    - [Downloaden](https://hub.docker.com/editions/community/docker-ce-desktop-windows/) Sie Docker Desktop von DockerHub
    - Führen Sie die Installation aus.
    - Falls gefragt wird, stellen Sie sicher, dass ``Enable Hyper-V Windows Features`` ausgewählt ist.

## Startet von Postgres und PGAdmin
Nun, da wir alles Installiert haben können wir die Container starten.
Dazu öffnen Sie eine Powershell (muss nicht als admin) und gehen in den Ordner in dem die bereitgestellte ``docker-compose.yml`` und ``servers.json`` liegt.

Sie können mit ``cd <Verzeichnis>`` in ein Verzeichnis gehen.
Alternativ können Sie auch einfach mit dem Explorer in den Ordner gehen und oben in der Adressleiste ``powershell`` eintragen und mit Enter bestätigen. Dann öffnet sich eine Powershell im aktuellen Ordner.

Nun da wir eine Powershell offen haben geben Sie ``docker-compose up -d`` ein und die Container sollten starten. Sobald die Container gestartet sind, könne Sie die Powershell schließen.

## Stoppen der Container
Um die Container wieder zu stoppen gehen Sie wie oben vor und öffnen eine Powershell im Ordner wo die ``docker-compose.yml`` liegt.
Anschließend geben Sie ``docker-compose down`` ein. Dies stoppt die beiden Container.

## Zugriff auf PgAdmin
Um nun auf PgAdmin zuzugreifen öffnen Sie ihren Browser und gehen auf ``http://localhost``.  
Jetzt sollten Sie auf der PgAdmin Anmeldeseite sein. Ihre Anmeldedaten sind wie folgt:  
Email: ``postgres@hs-bochum.de``  
Passwort: ``uni``  

Jetzt klicken Sie links in der Leiste auf ``Servers`` und dann auf den Postgres Server. Jetzt werden Sie nach einem Passwort gefragt. Das lautet: ``uni``  
Sie können das Passwort noch speichern und damit ist die Installation abgeschlossen.  

**WICHTIG:** Die Container werden nicht mit Windows gestartet. Deshalb müssen Sie die Container nach jedem Neustart erneut starten, falls Sie sie benötigen.


