## Installation:
- ### Linux:
    - Schauen Sie bitte in der Installationsanleitung für ihre Distro nach: Für gewöhnlich muss nur die Repo in den Paketmanager eingebunden werden und Docker dann damit installiert werden. (Es muss Docker Engine und das Tooling installiert werden.)
    - [CentOS](https://docs.docker.com/engine/install/centos/)
    - [Debian](https://docs.docker.com/engine/install/debian/)
    - [Fedora](https://docs.docker.com/engine/install/fedora/)
    - [Ubuntu](https://docs.docker.com/engine/install/ubuntu/)
    - #### Aditional Step:
      - Fügen Sie ihren Nutzer die Gruppe ``docker`` hinzu. Dann müssen Sie die Docker Kommandos nicht als root ausführen.
  - ## Docker Compose:
    - Folgen Sie der Anleitung in dem [Docker Wiki](https://docs.docker.com/compose/install/).
  
## Startet von Postgres und PGAdmin
Nun, da wir alles Installiert haben können wir die Container starten.
Dazu öffnen Sie ein Terminal und gehen in den Ordner in dem die bereitgestellte ``docker-compose.yml`` und ``servers.json`` liegt.

Sie können mit ``cd <Verzeichnis>`` in ein Verzeichnis gehen.  
Sie können mit ``ls`` sich den Inhalt des derzeitigen Ordner anzeigen.

Nun da wir ein Terminal offen haben geben Sie ``docker-compose up -d`` ein und die Container sollten starten. Sobald die Container gestartet sind, könne Sie das Terminal schließen.

## Stoppen der Container
Um die Container wieder zu stoppen gehen Sie wie oben vor und öffnen ein Terminal im Ordner wo die ``docker-compose.yml`` liegt.
Anschließend geben Sie ``docker-compose down`` ein. Dies stoppt die beiden Container.

## Zugriff auf PgAdmin
Um nun auf PgAdmin zuzugreifen öffnen Sie ihren Browser und gehen auf ``http://localhost``.  
Jetzt sollten Sie auf der PgAdmin Anmeldeseite sein. Ihre Anmeldedaten sind wie folgt:  
Email: ``postgres@hs-bochum.de``  
Passwort: ``uni``  

Jetzt klicken Sie links in der Leiste auf ``Servers`` und dann auf den Postgres Server. Jetzt werden Sie nach einem Passwort gefragt. Das lautet: ``uni``  
Sie können das Passwort noch speichern und damit ist die Installation abgeschlossen.  

**WICHTIG:** Die Container werden nicht mit Linux gestartet. Deshalb müssen Sie die Container nach jedem Neustart erneut starten, falls Sie sie benötigen.