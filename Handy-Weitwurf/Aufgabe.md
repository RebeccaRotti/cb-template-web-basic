# JavaScript Spiel: Handy Weitwurf

- In diesem Spiel sollst du mit deinem Handy ein Monster treffen
- Du musst dazu den Winkel und die Kraft eingeben mit der du das Handy wirfst um das Monster zu treffen
- Die Entfernung zum Monster darf nicht immer gleich sein
- Drei Versuche darf es geben 
  - für Fortgeschrittene: die Anzahl an Versuchen kann vom User eingegeben werden
- Definiere die Fallbeschleunigung als Konstante
  - Für Fortgeschrittene: Lass den User eingeben ob er auf der Erde, dem Mond, Mars oder Jupiter ist. Dementsprechend wird die Fallbeschleunigung zur Berechnung genommen
- Gib dem User aus ob er getroffen hat oder wie weit weg das Monster noch ist und wie weit er geworfen hat
- Achte auf ein angenehmes Styling der Seite

- `g` steht für die Fallbeschleunigungder Wert `g` beträgt auf der
  - Erde 9.81 m/s²
   - Mond 1.62 m/s²
   - Mars 3.69 m/s²
   - Jupiter 24.79 m/s²

- `var v0` ist die Anfangsgeschwindigkeit und ist mit einem Formular und einem Inputfeld vom User einzugeben

- `var derWinkel` ist der Winkel in dem der User wirft. Es darf nur eine Zahl zwischen 1 und 90 sein. Dieser Wert ist auch mit einem Inputfeld in einem Formular vom User einzugeben
  - Die Berechnung die du hier brauchst:<br>
  `derWinkel= derWinkel* ( Math.PI/ 180 )`
  
- `var wurfweite` berechnet sich aus dem Wurfwinkel und der Anfangsgeschwindigkeit
  - Die Berechnung sieht folgendermaßen aus: `wurfweite = ((v0 * v0) * Math.sin(2 * derWinkel)) / g`<br>
  Achtung: Runde das Ergebnis
  
- `var entfernungZumMonster` speichert den Wert der zufällig gewählt wird. Er stellt die Entfernung zum Monster dar
  - `entfernungZumMonster= Math.random() * 90 + 10;`<br>
  Mit dieser Zeile generierst du eine zufällige Zahl
  - `entfernungZumMonster= Math.round(entfernungZumMonster)`<br>
  Hier wird der Wert noch gerundet um eine ganze Zahl zu erhalten
