# JavaScript: Hammurabi

Hammurabi war nicht nur ein altertümlicher Herrscher, sondern auch Namensgeber für eine der allerersten Wirtschaftssimulationen, die den Grundstein für ein eigenes Spielegenre legt. 

Hammurabi war ein bekannter Herrscher im alten Babylon. Umfangreiche Gesetzgebung, wirtschaftliches Handeln und ein gut funktionierender Beamtenapparat stellten sicher, dass das Reich blühte und gedeihet. 

Unter dem Namen "Hamurabi" wurde in der Anfangszeit der Computer eine der ersten Wirtschaftssimulationen geschrieben. Über eine festgelegte Anzahl von Jahren musste der Spieler in die Rolle des weisen Herrschers Hammurabi schlüpfen und die Geschicke seines Landes steuern. Hammurabi legte den Grundstein für ein ganzes Genre und beeinflusste direkt oder indirekt die meisten Spiele, die wir heute als Wirtschaftssimulationen kennen. 
https://de.wikipedia.org/wiki/Hamurabi

## Wie funktioniert das Spiel
Über eine festgelegte Anzahl von Jahren, zum Beispiel 20, steuert der Spieler die Geschehnisse im Reich über die Eingabe bestimmter werte 

Du startest mit einer gewissen Menge an **Korn** bzw. Getreide. Wenn man so möchte, ist dies die recht einfache **Währung** im Spiel, mit der auch Handel getrieben werden kann. In jeder Runde musst du überlegen, wie du diese Ressourcen sinnvoll einsetzt 

Du musst genug **Nahrung** an deine Bevölkerung verteilen. Bekommen die Einwohner zu wenig Nahrung, dann verhungern sie (oder verlassen weniger dramatisch das Land). Verteilst du mehr Nahrung als notwendig, dann vermehrt sich die Bevölkerung 

Genauso musst du festlegen, wie viel Korn du auf den vorhandenen Äckern als **Aussaat** für das kommende Jahr verwendest. Sahst du zu wenig Korn, wird der Ertrag zu gering sein - dein Kornspeicher wird sehr schnell leer sein 

In jedem Jahr kannst du Land, das als **Acker** verwendet wird, **kaufen oder verkaufen**. Korn ist dafür deine Währung. Der Landpreis **variiert** von Jahr zu Jahr. Mit etwas Glück kannst du allein durch den Kauf und Verkauf von Land eine Menge Geld machen bzw. deinen Kornspeicher auffüllen 

Genauso kann übrigens auch die **Ernte** sehr unterschiedlich ausfallen. In manchen Jahren wächst das Getreide sehr gut, in anderen Jahren musst du froh sein, wenn deine Vorräte überhaupt zum Überleben reichen 

Und natürlich musst du genügend Einwohner haben, um das Korn überhaupt aussäen zu können. Sind nicht genug Einwohner da, können nicht genug Felder bewirtschaftet werden, und die Ernte fällt geringer aus 

| Anforderung | JavaScript-Code | 
|---|---|
| Das Spiel läuft über **20 Runden** | `var jahr = 0;` |
| Du startest mit **6.000 Scheffel Korn** | `var korn = 6000;` |
| Anfangs leben **100 Bürger** in deinem Königreich | `var buerger = 100;` |
| Jeder Bürger benötigt zum **Überleben** 20 Scheffel Korn im Jahr.<br>Verteilst du mehr Korn,wächst die Bevölkerung für jede 40 Scheffel Korn um einen Bürger | `function bevoelkerung(nahrung)` | 
| Du musst festlegen, wie viel Korn als **Aussaat** verwendet werden soll.<br>Im folgenden Jahr wird diese Ernte automatisch eingebracht und vergrößert den vorhandenen Kornvorrat. <br>Pro Acker werden **2 Scheffel** Korn zur Aussaat benötigt, die Ernte liegt zwischen 1 und 10 Scheffel. Jeder Bürger kann 10 Acker land bewirtschaften | Wir müssen also aussäen können, wir müssen wissen, wie gut die Ernte war, und diesen Wert sollten wir im Spiel in einer Variablen zur Verfügung haben: <br>`function aussaat(saat)`<br>`function bestimmeErnteErfolg()`<br>`var ernteProAcker;` | 
| Land kann **gekauft oder verkauft** werden- Der Landkauf geschieht am Ende der Runde, <br>nachdem alle anderen Aktionen abgeschlossen sind. Der Landpreis variiert zwischen 1 und 10 Scheffel Korn. |Auch den Landpreis sollten wir im Spiel in einer Variablen zur Verfügung haben und ihm einen mittleren Anfangswert geben<br>`function bestimmeLandPreis()`<br>`var landPreis = 5;`  | 
| 400 Acker Land sind bei Spielbeginn in deinem **Besitz**. Du kannst beliebig viel <br>Landhandeln - vorausgesetzt, dein noch vorhandenes Korn reicht für einen Kauf. |`var land = 400;`<br>`function handel(kauf)`  | 
| Hast du weniger als 1 Acker Land, 1 Scheffel Korn oder sinkt die Anzahl der <br>Bewohner unter 1 Bürger endet das Spiel. Ansonsten endet es nach 20 Runden. |`var ende = false;`<br>`function pruefeEnde()` | 
## Eingaben und Spielhinweise 
| Anforderung | JavaScript-Code | 
|---|---|
| Uns fehlt noch eine Eingabe, schließlich will man <br>als Herrscher auch gehört werden | `function verarbeiteBefehle()` |
| Wir benötigen eine Ausgabe, einen Bericht für den <br>Herrscher. Schließlich wollen wir ja wissen, <br>was passiert ist - was hat sich getan? Wie ist der aktuelle <br>Landpreis, wie war die Ernte? | `function erstelleBericht()`|
| Irgendwie muss eine Runde ja gestartet werden. <br>Idealerweise als eigene Funktion, die wir mit einem Klick <br>oder vielleicht auch zeitgesteuert aufrufen können  | `function spieleEineRunde()`|

### Auch wichtig!
Die richtige Reihenfolge. Hier ist nicht gemeint, in welcher Reihenfolge du die Funktionen im Code schreibst - das ist ziemlich egal. Die Funktionen müssen nach dem Start in der richtigen Reihenfolge aufgerufen werden. Sonst kann es zu logischen Fehlern kommen: Wird der Landpreis im aktuellen Bericht verkündet, dann darf er danach nicht mehr verändert werden - bis zum Abschluss des Landkaufs. Ansonsten kann es zu recht überraschenden Ergebnissen führen, wenn der Preis beim Verkauf plötzlich geringer ist. 

### Der Bericht - Inhalte
- das aktuelle **Jahr **
- Die Anzahl der (noch) vorhandenen **Bürger**
- wie viel **Korn** in den Speichern liegt 
- wie der **Preis** für Land in dieser Runde ist 
- Interessant ist außerdem, wie gut die **Ernte** war, also der Wert ernteProAcker. Wir wollen aber nicht einfach die Zahl in den Text schreiben, sondern den Wert in einen passenden Text umschreiben. Dafür brauchst du `switch-case `

### Funktionen die du brauchen kannst

- `function spieleEineRunde() { ... }`
- `function verarbeiteBefehle() { ... }`
- `function bestimmeErnteErfolg() { ... }`
- `function bestimmeLandPreis() { ... }`
- `function bevoelkerung(nahrung) { ... }`
- `function aussaat(saat) { ... }`
- `function handel(kauf) { ... }`
- `function erstelleBericht() { ... }`
- `function pruefeEnde() { ... }`

### Befehle, Code-Snippet, Funktionen, Methoden die du gut brauchen kannst
- `console.log();`
- `Math.round();`
- `Math.random();`
- `prompt();`
- `innerHTML`
- `isNaN`
- `if { ... } else { ... }`
- `alert();`
- `Math.abs();`
- `split(",");`
- `paresInt(); `
