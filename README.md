# K2
## Persönlicher Wissensstand

| Begriff           | Was ich darüber weiss                                                                                                                                    |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| Containerisierung | Ich habe bisher noch nie etwas über Containerisierung gehört. Ich kann mir zwar ein wenig was darunter vorstellen, aber ich kenne es nicht.              |
| Docker            | Ich kenne Docker noch nicht. Ich habe zwar schon davon gehört, da meine Kollegen mal damit gearbeitet haben, jedoch habe ich es selber noch nie genutzt. |
| Microservices     | Unter desem Begriff kann ich mir zwar etwas vorstellen, jedoch nutzte ich es noch nie und habe auch noch nie davon gehört.                               |

# K3
## Bestehende Docker-Container kombinieren

Ich habe einen Apache und einen PHP Container sowie einen MySql Container kombiniert und dann ein paar Änderungen/Einstellungen gemacht.

## Kennt die DOckerspezifischen Befehle

Standard-Test:
```Shell
    $ docker run hello-world
```

Startet einen Container mit einer interaktiven Shell (interactive, tty):
```Shell
    $ docker run -it ubuntu /bin/bash
```

**docker ps** <br>
* Gibt einen Überblick über die aktuellen Container, wie z.B. Namen, IDs und Status.

Aktive Container anzeigen:
```Shell
    $ docker ps
```

Aktive und beendete Container anzeigen (all):
```Shell
    $ docker ps -a
```

Nur IDs ausgeben (all, quit):
```Shell
    $ docker ps -a -q
```

**docker images** <br>
* Gibt eine Liste lokaler Images aus, wobei Informationen zu Repository-Namen, Tag-Namen und Grösse enthalten sind.

Lokale Images ausgeben:
```Shell
    $ docker images
```

Alternativ auch mit `... image ls`:
```Shell
    $ docker image ls
```

**docker rm und docker rmi** <br>
* `docker rm`
    *  Entfernt einen oder mehrere Container. Gibt die Namen oder IDs erfolgreich gelöschter Container zurück.
* `docker rmi`
    *  Löscht das oder die angegebenen Images. Diese werden durch ihre ID oder Repository- und Tag-Namen spezifiziert.

Docker Container löschen:
```Shell
    $ docker rm [name]
```

## Eingerichtete Umgebung Dokumentieren
    +--------------------+          +---------------------+
    ! Web Server         !          ! Datenbank Server    !
    !                    !          !                     !
    ! IP: 127.0.0.1      ! <------> ! IP:                 !
    ! Port: 80           !          ! Port 3306           !
    ! Nat: 8080          !          ! Nat: -              !
    +--------------------+          +---------------------+

Die Umgebung umfasst eine Webapplikation (Apache), eine PHP Applikation und eine SQL Applikation. Per PHP wird dann auf die Datenbank connected. 
Ich habe den Port der Webapplikation weitergeleitet um ein wenig Sicherheit zu schaffen. Zudem ist diese Applikation von aussen nicht erreichbar. Der Server auf dem diese Applikationen Läuft ist Passwortgeschützt und auch nicht von aussen erreichbar. Dies könnte man jedoch mithilfe einer Firewall ändern. Der Server hat ein aktuelles Ubuntu insttalliert und wird regelmässig geupdated. Mit diesen Massnahmen erhöhe ich die SIcherheit dieses Systemes.

#Funktionsweise Tests

| Testfall                       | Soll                                                                    | Ist                                                                                              |
|--------------------------------|-------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|
| Docker Container starten       | Der Container startet ohne Probleme                                     | Der Container startete ohne Probleme                                                             |
| Webseite aufrufen              | Die Webseite wird angezeigt und die Verbidung mit MySQL wird aufgebaut  | Die Webseite wird korrekt angezeigt und auch die Verbindung mit MySQL funktioniert ohne Probleme |
| Webseite per Terminal aufrufen | Die Webseite bzw die Verbindung mit MySQL wird gezeigt und funktioniert | Die Verbindung mit MySQL wird aufgebaut                                                          |

# K4
## Sicherheitsmassnahmen
Ich habe die Lokale Firewall so wenig wie möglich geöffnet. Zudem ist der Server nicht direkt von ausen erreichbar. Die Webseite ist nicht von ausen erreichbar. Der Server verfügt über ein Passwort. Durch diese Massnahmen kann ich sicherstellen, dass keine unbefugten Personen auf den Server bzw. auf die Webseite zugreifen können.

