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

| Befehl       | Beschreibung                                       |
| ------------ | -------------------------------------------------- |
| docker run   | Führt ein Befehl in einem neuen Container aus      |
| docker start | Startet einen oder mehrere gestoppte Container     |
| docker stop  | Stoppt einen oder mehrere laufende ontainer        |
| docker build | Erstellt ein Image aus einem Docker-File           |
| docker pull  | Ladet ein Image aus der Registry                   |
| docker push  | Ladet ein Image in die Registry hoch               |
| docker exec  | Führ einen Befehl in einem laufenden Container aus |

## Eingerichtete Umgebung Dokumentieren
    +---------------------------------------------------------------+
    ! Container: Apache Webserver - 127.0.0.1 - 8080                !
    ! Container: PHP                                                !
    ! Container: MySQL Datenbank - Hostname: mysql                  !
    +---------------------------------------------------------------+
    ! Container-Engine: Docker                                      !
    +---------------------------------------------------------------+
    ! Ubuntu VM - VirtualBox                                        !
    +---------------------------------------------------------------+
    ! Notebook HP - Schulnetz 10.x.x.x                              !
    +---------------------------------------------------------------+

Die Umgebung umfasst eine Webapplikation (Apache), eine PHP Applikation und eine SQL Applikation. Per PHP wird dann auf die Datenbank connected. 
Ich habe den Port der Webapplikation weitergeleitet um ein wenig Sicherheit zu schaffen. Zudem ist diese Applikation von aussen nicht erreichbar. Der Server auf dem diese Applikationen Läuft ist Passwortgeschützt und auch nicht von aussen erreichbar. Dies könnte man jedoch mithilfe einer Firewall ändern. Der Server hat ein aktuelles Ubuntu insttalliert und wird regelmässig geupdated. Mit diesen Massnahmen erhöhe ich die SIcherheit dieses Systemes.

#Funktionsweise Tests

| Testfall                        | Resultat                                                         |
|---------------------------------|------------------------------------------------------------------|
| Container starten               | Die Container starten ohne Probleme                              |
| Connection auf SQL              | Die Webseite bzw PHP greift auf die Datenbank zu. Keine Probleme |
| Webseite öffnen: 127.0.0.1:80   | Die Webseite kann nicht aufgerufen werden. Wie gewollt           |
| Webseite öffnen: 127.0.0.1:8080 | Die Webseite wird geöffnet                                       |                                             |

# K4
## Sicherheitsmassnahmen
Ich habe die Lokale Firewall so wenig wie möglich geöffnet. Zudem ist der Server nicht direkt von ausen erreichbar. Die Webseite ist nicht von ausen erreichbar. Der Server verfügt über ein Passwort. Durch diese Massnahmen kann ich sicherstellen, dass keine unbefugten Personen auf den Server bzw. auf die Webseite zugreifen können.

