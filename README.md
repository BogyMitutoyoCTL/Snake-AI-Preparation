# Snake AI Preparation
Künstliche Intelligenz am Beispiel vom Spiel Snake. Dieses Repository enthält die vorbereitenden Informationen, die den Schülern beigebracht wurden. Der Code, der bei der Implementierung im Rahmen des Praktikums entstanden ist, ist nicht Teil dieses Repositories.

## Zusammenarbeit

Dieses Praktikum (BOGY; Berufsorientierung im Gymnasium) wurde durchgeführt mit einem Schüler des [Droste Hülshoff Gymnasiums Rottweil](https://www.dhg-in-rw.de) und der Firma [Mitutoyo CTL Germany GmbH](https://www.mitutoyo-ctl.de/).

## Montag 19.10.2020

Wir haben die organisatorischen Dinge geklärt, d.h. Besucheranmeldung, Sicherheits- und Verhaltenshinweise, Zugang zum WLAN, Pausen und das Corona-Konzept.

Die Einführung bestand aus:

* Rundgang durch das Gebäude
* [Firmenpräsentation](praesentationen/Firmenpräsentation.pptx)
* [Raspberry Hardware](praesentationen/Raspberry%20Hardware.pptx), weil wir dem Schüler einen Raspberry Pi 4B als Arbeitsmittel zur Verfügung stellten.

Danach ging es schon ans Lernen. Ein paar Grundlagen, die ein Informatiker unserer Meinung nach kennen sollte, wenn er mit dem Raspberry Pi arbeitet:

* [Linux](praesentationen/Linux.pptx)

* [Bash](praesentationen/Bash.pptx)

* [Pycharm](praesentationen/Pycharm.pptx)

* [Python Einführung](praesentationen/Python%20Einführung.pptx)

* [Python Objektorientierung](praesentationen/Python%20Objektorientierung.pptx)

Um das Gelernte zu vertiefen haben wir noch zwei Aufgaben von [Project Euler](https://projecteuler.net) gelöst.

## Dienstag 20.10.2020

Am zweiten Tag sind wir auf die Versionskontrolle eingegangen mit den Präsentationen:

* [Versionskontrolle](praesentationen/Versionskontrolle.pptx)

* [Git Grundlagen](praesentationen/Git%20Grundlagen.pptx)

Danach haben wir uns allgemein mit Künstlicher Intelligenz vertraut gemacht und auch ein paar ethische Fragen diskutiert:

* [Künstliche Intelligenz](praesentationen/Künstliche%20Intelligenz.pptx)

Mit diesem Vorwissen haben wir zunächst versucht, eine eigene Schlange mit Hilfe eines klassischen Algorithmus zu programmieren. Dazu gibt es die Anleitung

* [Eigener Algorithmus](Eigener%20Algorithmus.md)

## Mittwoch 21.10.2020

Der eigene Algorithmus konnte Schlangenlängen bis etwa 25 erreichen. Der entstandene Code nutzte viele if-Abfragen, um eine Entscheidung zu treffen. Dabei beschränkte sich die "Beobachtung" der Schlange im Wesentlichen auf die vier angrenzenden Felder. Will man auf diese Art weitermachen, entsteht so genannter Spaghetti-Code. Mit ein paar Überlegungen kommt man auf eine andere, allerdings Speicherplatz-intensive Möglichkeit der Implementierung.

* [Von der Spaghetti-Schlange zu Q-Tables](praesentationen/Von der Spaghetti-Schlange zu Q-Tables.pptx)
