# Code Breaker

- In diesem Spiel sollst du einen 3 stelligen Zahlencode erraten
- Dafür hast du ein Input Feld mit einem mindestwert von 111 und einem maximalwert von 999
- Der Zahlencode generiert sich automatisch
- Tipp: du generierst drei zahlen zwischen 1 und 9
- Im JavaScript
  - du holst dir den Wert aus dem Inputfeld und speicherst alle drei Werte in eine eigene Variable
    - dazu benötigst du die Methode .charAt()
  - du benötigst außerdem Variablen für:
    - einen Zähler für die Versuche (maximal dürfen es 12 Versuche sein)
    - die richtig geratene Stelle
    - die richtig geratene Zahl
  - du vergleichst die einzelnen geratenen Zahlen mit den einzelnen Zahlen des Geheimcodes
  - folgende Ausgaben gibt es:
    - die Runde
    - wie viele Zahlen richtig geraten sind
    - wie viele Stellen richtig geraten wurden
