# Übung 16 - JS 06

## Aufgaben aus den Foliensätzen

## Mathequiz

- Grundgerüst ist eine Seite mit neun nummerierten Feldern
- Aktuelle Spielstand wird dabei dadurch gekennzeichnet, dass das entsprechende Feld, auf dem der Spieler steht einen farbigen Hintergrund erhält
- Wenn Spieler einen Zug durchführen will, muss er auf einen Button unter dem Spielfeld klicken
  - Daraufhin wird ihm eine Rechenaufgabe gestellt
    - Diese sollen jeweils auf Zufallswerten basieren
    - Grundsätzlichen Arten der Aufgabe für jedes Feld fest vorgegeben
    - Schwierigkeitsgrad soll immer weiter ansteigen
    - Wenn Spieler Aufgabe richtig gelöst hat, rückt er ein Feld vor
    - Wenn Ergebnis falsch ist, bleibt er auf der Position
- Zweiter Button für Spiel neu starten

<hr>

### Grundaufbau
1. Grundaufbau der Seite festlegen (Spielfeld 1 – 9 erstellen)
2. Jedes Feld erhält eine ID auf die im JS zugegriffen werden kann
3. Buttons unter dem Spielfeld positionieren und Überschrift setzen
4. JS Code in eigene Datei speichern und mit HTML Seite verlinken
5. Spielstand
    1. Variable für Spielstand deklarieren – den sollte man zu jedem Zeitpunkt im Spiel kennen
    2. Spielstand soll im localStorage mit richtigem Wert gespeichert werden
    3. Entsprechendes Feld laut Wert im localStorage farblich markieren

<hr>

### Funktion für die Buttons
1. Zug ausführen (function weiter())<br>
Besucher wird eine Frage gestellt 
    1. Die eigentliche Frage steht in einer eigenen Funktion (function frage(spielstand))<br>
    hier wird nur die Funktion frage(spielstand) aufgerufendie Funktion für die Frage muss können:
        1. Hat als Übergabewert den Spielstand 
        2. Liefert dem Anwender eine passende (nach Schwierigkeitsgrad) Frage stellt 
        3. Überprüft das Ergebnis gleich. Ist es richtig gibt sie den Wert true zurück, ansonsten false. 
    2. Je nach Ergebnis Spielstand anpassen, neues Feld hervorheben und neuen Spielstand abspeichern oder neue Frage stellen
    3. Sonderfall: Ende des Spielfeldes: Passende Nachricht ausgeben, Spielstand wieder auf 1 setzen um ein neues Spiel zu starten
2. Zweiter Button – neues Spiel starten (function neu())
    1. Bisherige Markierung entfernen
    2. Spielstand auf 1 setzen um neues Spiel zu beginnen
    3. Hintergrund des markierten Feldes setzen

<hr>

### Die Frage stellen
1. Zufallswerte kommen zum Einsatz
2. Grundsätzliche Art der Aufgabenstellung bei jedem Spielfeld fest vorgegeben sein, der Schwierigkeitsgrad steigt von Frage zu Frage
3. Die Funktion (function frage(spielstand)) erhält den Spielstand als Übergabeparameter
    - Genereller Aufbau der Funktion
        - Frage stellen
        - Überprüfung der Eingabe des Spielers
        - Wenn richtig, Funktion gibt entsprechende Nachricht aus und liefert den Wert true zurück
        - Wenn falsch, entsprechende Nachricht ausgeben und false zurück geben
    - Schwierigkeitsgrade
        1. Aufgabe: einfache Addition mit Zufallszahlen zwischen 1 und 50 
        2. Aufgabe: Subtraktion ohne negativen Ergebnis!
        Erste Zahl im Bereich 51 bis 100, zweite Zahl zwischen 1 und 50
        3. Aufgabe: Multiplikation
        4. Aufgabe: Division
        hier wird der Divisor und das Ergebnis per Zufall bestimmt, da sonst komplizierte Nachkommastellen berechnet werden müssen
        5. bis 7. Aufgabe: Berechnungen mit drei verschiedenen Zufallsvariablen
        8. Aufgabe: Quadratwurzel eines Werts (Math.pow())
        Sinnvoll auch hier das Ergebnis per Zufallswert zu bestimmen. Stellt sicher, dass es eine ganze Zahl ist. Für die Aufgabenstellung wird dieser dann mit sich selbst multipliziert
        9. Aufgabe: Logarithmus eines Werts (Math.pow())
        Per Zufall die Basis und das Ergebnis bestimmt. Eher kleine Werte nehmen, da sonst Potenz-Funktion sehr große Werte hat





