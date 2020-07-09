## Installation:
- ### MacOS 10.13 or later:
    - [Downloaden](https://hub.docker.com/editions/community/docker-ce-desktop-mac/) Sie den Installer von Docker Hub
    - Führen Sie den Installer aus. (Ziehen Sie Docker in ihren Applikation Ordner)
    - Starten Sie Docker über das Launchpad oder suchen Sie mit Spotlight nach ``Docker`` und starten Sie Docker.
    - Bestätigen Sie den Dialog und geben Sie ihr Passwort ein. Dies schließt dann die Installation von Docker ab.
    - Nach Der Installation sollte der Docker Wal in der Statusleiste vorhanden sein.  
    ![Status-Bar](https://d1q6f0aelx0por.cloudfront.net/icons/whale-in-menu-bar.png)

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

**WICHTIG:** Die Container werden nicht mit MacOS gestartet. Deshalb müssen Sie die Container nach jedem Neustart erneut starten, falls Sie sie benötigen.
