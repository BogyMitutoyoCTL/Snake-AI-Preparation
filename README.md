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

* [Von der Spaghetti-Schlange zu Q-Tables](praesentationen/Von%20der%20Spaghetti-Schlange%20zu%20Q-Tables.pptx)

Mit diesem Wissen haben wir zunächst das Programm "DecisionRecorder" ausgeführt und eine 2-dimensionale Struktur geschaffen, in der für jede Situation (Blickweite 1 Kästchen) hinterlegt ist, wie die Schlange sich verhalten soll. Das hat schon gut funktioniert und die Schlange erreicht Längen von 40 oder 50.

Im nächsten Schritt haben wir die 2-dimensionale Struktur auf 3 Dimensionen erweitert. Dadurch gibt es Platz, um für jede mögliche Entscheidung eine Zuversichtlichkeit zu hinterlegen. Basierend auf den Erfahrungen, die die Schlange macht, kann die Zuversichtlichkeit angepasst werden. Die Schlange wählt dann den Zug mit der höchsten Zuversichtlichkeit aus und lernt auf diese Art hinzu.

Nachdem wir eine Möglichkeit geschaffen hatten, die Erfahrungen abzuspeichern, haben wir über Nacht diesen Algorithmus in 100.000 Epochen trainieren lassen.

## Donnerstag 22.10.2020

Am Donnerstag Morgen kam dann die Ernüchterung: aufgrund eines Programmierfehlers hat die Schlange nicht so gelernt wie erwartet. Nach der Korrektur sahen die Versuche der Schlange schon besser aus.

Im Laufe des Vormittags haben wir das Sichtfeld der Schlange auf ein 5x5-Feld erweitert. Außerdem haben wir die Performance erhöht, indem wir die Visualisierung nur jede n-te Epoche anzeigen lassen.

Dann haben wir uns den Aufbau von neuronalen Netzen angesehen:

* [Neuronale Netze](praesentationen/Neuronale%20Netze.pptx)

An unserer [Excel-Tabelle](praesentationen/NeuronalesNetz_tanh.xlsx) konnten wir nachvollziehen, dass die Berechnungen selbst relativ einfach sind - es sind nur viele davon.

Über Nacht konnten wir den Algorithmus mit 5x5 Feld in 300.000 Epochen trainieren lassen. 

## Freitag 23.10.2020

Die Schlange ist über Nacht mehr als 11.000.000 Schritte gelaufen und hat über 1.100.000 unterschiedliche Situationen auf dem Spielfeld gesehen und daraus gelernt. Das beste Ergebnis lag bei einer Länge von 50.

Ein Neustart mit den gelernten Daten zeigt: die Schlange erreicht schnell maximale Längen von über 35. Im Schnitt wird sie allerdings nur 15 Kästchen lang.

Wir haben die Inhalte des BOGYs schnell umgesetzt und erreicht, so dass wir uns am Freitag mit der Lösung mathematischer Probleme bei [Project Euler](https://projecteuler.net/archives) beschäftigt haben.