### Erläuterung des bestehenden Codes

Da wir uns auf das Machine Learning konzentrieren wollen, hat Mitutoyo das Snake-Spiel bereits implementiert. Über diese Implementierung haben wir uns einen Überblick verschafft.

#### Snake

Der Kern des Programms, das Spiel, ist in der Klasse `Snake` untergebracht. Das Spiel akzeptiert 7 mögliche Bewegungen:

* `north`, um nach oben zu laufen
* `east`, um nach rechts zu laufen
* `south`, um nach unten zu laufen
* `west`, um nach links zu laufen
* `turn left`, um in Laufrichtung der Schlange links abzubiegen
* `turn right`, um in Laufrichtung der Schlange rechts abzubiegen
* `straight`, um weiter geradeaus in Laufrichtung der Schlange zu laufen

Die Klasse `Snake` nutzt eine andere Klasse `Field`, um sich zu zeichnen. Dabei handelt es sich um ein zweidimensionales Array, das wir als Spielfeld bezeichnen. `Field` enthält bereits die Farben, wie sie später abgebildet werden sollen.

Normalerweise würde das Snake Spiel von einem Menschen mit einem Controller bedient. Das ist in unserem Fall unpraktisch. Daher gibt es um die Klasse `Snake` herum noch ein sogenanntes Gym (englisch *gymnasium* = Sporthalle), also einen Ort, in der die künstliche Intelligenz trainieren kann. Dieses Gym ist kompatibel zu der Definition eines Gym von OpenAI. Die Klasse dafür bei uns heißt `SnakeGym`.

#### Algorithmen

Damit beim Programmieren von unterschiedlichen Strategien der Schlange weder das Gym, noch das Spiel selbst geändert werden muss, haben wir eine Klasse `Algorithm` definiert. Diese Klasse ist vorbereitet auf Machine Learning, d.h. sie hat Methoden und Eigenschaften, die wir am Anfang noch nicht brauchen, sondern erst, wenn wir tatsächlich Machine Learning mit neuronalen Netzen betreiben. Mit dieser Klasse `Algorithm` ist es sehr einfach, selbst eine Idee zu verwirklichen, wie die Schlange sich bewegen soll.

Ein Beispiel für einen solchen Algorithmus ist `RotateForever`. Dieser Algorithmus basiert auf der Idee, dass Snake möglichst lang gespielt werden soll. Die einfachste Art, ewig zu spielen ist, sich immer im Kreis zu drehen. Leider bekommt man dafür keine Punkte. Die Implementierung dieser Idee ist beinahe trivial:

```python
from Algorithms.Algorithms import Algorithm
from GameData import GameData


class RotateForever(Algorithm):
    def __init__(self):
        super().__init__()

    def decide(self, info: GameData) -> str:
        return "turn left"
```

Die ersten Zeilen sind immer identisch. Lediglich die Funktion `decide()` muss angepasst werden.

Von diesen sehr einfachen Algorithmen haben wir einige zusammengestellt:

* `RotateForever`: dreht sich immer im Kreis
* `RandomChoice`: wählt eine Zufallsaktion, als ob man einfach blind auf dem Controller herumdrückt

#### Entscheidungsgrundlagen für Algorithmen

Damit man sich nicht blind für eine Aktion entscheiden muss, bekommt man für die Entscheidung ein paar Grundlagen, und zwar im Parameter `info` vom Typ `GameData`. Darin sind allerhand Informationen zu finden, die man für Entscheidungen braucht:

* `head_x` und `head_y`: wo der Kopf der Schlange sich befindet

* `snake_length`: Länge der Schlange

* `direction`: Aktuelle Laufrichtung der Schlange

* `food_x` und `food_y`: wo sich das Futter befindet

* `food_direction`: Richtung, in der sich das Futter befindet. Die Winkel sind dabei wie folgt:

  ![Richtungen](D:/Projekte non-backup/Github/AI-Preparation/images/directions.png)

* `food_distance_in_steps`: Schritte bis zum Futter (kürzester Weg, ohne Berücksichtigung von Hindernissen)

* `air_line_distance`: Abstand zum Futter in Kästchen (diagonal, Pythagoras)

* `walldistance_`...: Abstand zur Wand (vom Kopf aus)

* u.a.

Ebenfalls nützlich sind einige Funktionen:

* `can_move_to(x,y)`: findet heraus, ob an diese Position gelaufen werden kann, ohne zu sterben

* `body_age(x,y)`: findet heraus, wie bald sich der Körper an dieser Stelle hier wegbewegt

* `is_body(x,y)`, `is_food(x,y)` und `is_head(x,y)`: um abzufragen, um welche Sorte Kästchen es sich handelt

Das Spielfeld ist dabei folgendermaßen aufgebaut:

​    ![Aufbau des Spielfelds](D:/Projekte non-backup/Github/AI-Preparation/images/playground.png)

Diese Richtung der Achsen ist in der Bildverarbeitung üblich. Euer Monitor hat z.B. ebenfalls die Ecke P(0|0) oben links.

#### Die Anzeige

Damit wir eine hübsche Anzeige mit allerhand Statistik bekommen, gibt es die Klasse `Visualization`. Diese nutzt die Bibliothek PyGame, um ein Fenster zu zeigen.

Die Daten der Statistik kommen aus der Klasse `TrainingData`.

#### Zum lauffähigen Programm zusammengestellt

Das Programm `main.py` fügt alle Dinge zusammen: 

* es baut das Gym auf
* es zeigt alle Algorithmen an und lässt den Benutzer einen auswählen
* es lässt den Algorithmus in einigen Runden (`max_epochs`) spielen
* zeigt am Ende die Statistik auf der Konsole an.

Auch das Programm `main.py` ist schon auf Machine Learning vorbereitet. Deshalb gibt es dort auch schon ein Belohnungssystem vom Typ `RewardSystem` und einen Algorithmus für Zufallsentscheidungen, aus denen die KI später lernen wird.

Die Klassen `Snake`, `Field`,`SnakeGym`, `Algorithm`, `RotateForever`, `RandomChoice` und `GameData` müssen im Laufe des Praktikums nicht geändert werden.

### Aufgabe: schreibe einen Algorithmus

Die Aufgabe für diesen Vormittag ist, einen eigenen Algorithmus zu schreiben, der hoffentlich schon besser funktioniert als der Algorithmus, der per Zufall entscheidet. Dazu verwenden wir noch keine KI. Wir möchten zunächst herausfinden, wie schwierig es eigentlich ist, gut Snake zu spielen.

Das Grundgerüst sieht so aus:

```python
from Algorithms.Algorithms import Algorithm
from GameData import GameData


class B⸻(Algorithm):  # Passe den Klassen-Namen hier an
    def __init__(self):
        super().__init__()

    def decide(self, info: GameData) -> str:
        # Programmiere hier
```
