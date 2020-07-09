- ### Legacy Sytems (Windows 8, MacOS 64-Bit):
    - Stellen Sie sicher, dass Virtualisierung in ihrem BIOS aktiviert ist. (Windows) 
    - Laden Sie sich die neueste Version von [Docker Toolbox](https://github.com/docker/toolbox/releases) herunter.
    ![Download](https://raw.githubusercontent.com/Flusinerd/Uni-Docker-Manual/master/images/Docker-Toolbox-Download.jpg) (exe für Windows, pkg für MacOS)
    - Falls Sie bereits VirtualBox installiert haben, stoppen Sie VirtualBox
    - Führen Sie die Installation aus.
    - Falls Sie VirtualBox bereits installiert haben, wählen Sie VirtualBox in der Liste der zu installierenden Komponenten ab.

# Starten unter Windows:
  ## Startet von Postgres und PGAdmin
Nun, da wir alles Installiert haben können wir die Container starten.
Dazu öffnen Sie eine Powershell (muss nicht als admin gestartet werden)  und gehen in den Ordner in dem die bereitgestellte ``docker-compose.yml`` und ``servers.json`` liegt.

Sie können mit ``cd <Verzeichnis>`` in ein Verzeichnis gehen.  
Sie können mit ``ls`` sich den Inhalt des derzeitigen Ordner anzeigen.  

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
# Starten unter MacOS:
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

