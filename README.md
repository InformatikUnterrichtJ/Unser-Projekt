# Unser-Projekt
### Inhaltsverzeichnis
- [Die Spielidee](https://github.com/InformatikUnterrichtJ/Unser-Projekt/blob/main/README.md#die-spielidee)
- [Übersicht zur Steuerung](https://github.com/InformatikUnterrichtJ/Unser-Projekt/blob/main/README.md#%C3%BCbersicht-zur-steuerung)
- [Elemente des Spiels](https://github.com/InformatikUnterrichtJ/Unser-Projekt/blob/main/README.md#elemente-des-spiels)
  
  I. [Startbildschirm](https://github.com/InformatikUnterrichtJ/Unser-Projekt/blob/main/README.md#i-startbildschirm)
  
  II. [Raumschiff](https://github.com/InformatikUnterrichtJ/Unser-Projekt/blob/main/README.md#ii-raumschiff)
  
  III. [Laser](https://github.com/InformatikUnterrichtJ/Unser-Projekt/blob/main/README.md#iii-laser)
  
  IV. [Meteroiten](https://github.com/InformatikUnterrichtJ/Unser-Projekt/blob/main/README.md#iv-meteroiten)
  
  V. [Farbauswahl](https://github.com/InformatikUnterrichtJ/Unser-Projekt/blob/main/README.md#5-farbauswahl)
  
  VI. [Schriftzüge](https://github.com/InformatikUnterrichtJ/Unser-Projekt/blob/main/README.md#6-schriftz%C3%BCge) 
    
    → ["Bewege dich mit den Pfeiltasten nach Oben und Unten"](https://github.com/InformatikUnterrichtJ/Unser-Projekt/blob/main/README.md#6a-bewege-die-mit-den-pfeiltasten-nach-oben-und-unten)
    
    → ["Drücke "a" zum Schießen"](https://github.com/InformatikUnterrichtJ/Unser-Projekt/blob/main/README.md#6b-dr%C3%BCcke-a-zum-schie%C3%9Fen)

## Die Spielidee
Das Spiel kann man den Arkade-Shootern zuordnen. Die Idee ist, dass man ein Raumschiff auf der linken Seite des Bildschirms steuert um den Meteroiten, die von links nach rechts über den Bildschirm fliegen, ausweicht und diese zerschießt.

Gesteuert wird das Spiel mit der Tastaur, wobei die Zahlentasten zum Auswählen der Farbe benutzt werden, die Pfeiltasten das Raumschiff bewegen und mit der "a"-Taste geschossen wird. Nur zum Neustarten wird eine Maus benötigt, da dies durch das Anklicken des Fahnensymbols geschieht.

Zu Anfang des Spiels wird dem Spieler die Steuerung erklärt. Zuerst wird man aufgefordert die Pfeiltasten zu benutzen, damit die Bewegungssteuerung erprobt werden kann, wird dem Spieler erst nach einer 30 sekündigen Pause erklärt, dass er "a" zum Schießen nutzen kann. Nachdem die Pfeiltasten erstmalig benutzt wurden werden die Meteroiten in regelmäßigen Absänden mehr und bewegen sich auch schneller, wodurch das Spiel zunehmend schwieriger wird. Auf dem Bildschirm wird mit einer Anzeige mitgezählt wie viele Meteroiten während des Spieldurchgangs getroffen wurden. Enden tut das Spiel, wenn das Raumschiff von einem Meteroiten getroffen wird. Level gibt es keine, da es sich um ein endloses Spiel handelt, welches zunehmend schwieriger wird und somit den Spieler zum Scheitern bringt, wodurch das Spiel dann endet.

## Übersicht zur Steuerung
⚑= Neustarten des Spiels

↑= Raumschiff bewegt sich nach oben

↓= Raumschiff bewegt sich nach unten

"a"= Raumschiff schießt einen Laser

## Elemente des Spiels
##### I. Startbildschirm
-> Soll zu Anfang des Spiels gezeigt werden und anschließend nicht mehr auftauschen ab dem Moment wo die Leertaste gedrückt wurde

Aussehen des Sprites:

(schwarzes Rechteck ergänzt, damit die weiße Schrift zu erkennen ist)![Download (1)](https://user-images.githubusercontent.com/111415429/208243068-e50f57e7-a4fe-42e8-82ce-84859982030d.png)

Code:

<img width="218" alt="Bildschirmfoto 2022-12-17 um 14 21 25" src="https://user-images.githubusercontent.com/111415429/208245038-92eba36b-899c-46a1-8541-f4fb1f62b22e.png">


##### II. Raumschiff
Aussehen des Sprites:
- blau

![blau](https://user-images.githubusercontent.com/111415429/208243301-46e8a4c0-ffc2-4cdc-8865-ac7f9d7743a8.png)
- grün

![grün](https://user-images.githubusercontent.com/111415429/208243349-5f263209-45eb-49c9-b500-637b9e9cfc4a.png)
- rot

![rot](https://user-images.githubusercontent.com/111415429/208243327-fb1973a0-6b4f-4e8b-bbe4-cbcd3e43e607.png)
- gelb

![gelb](https://user-images.githubusercontent.com/111415429/208243362-0bddb8d1-aca3-4c51-9ecc-0a877b6abad2.png)

Code:

(beinahe identisch für alle vier Farben)

<img width="204" alt="Bildschirmfoto code_raumschiff neustart" src="https://user-images.githubusercontent.com/111415429/208245666-01aced0d-e601-40aa-8116-3ec6c5702610.png"> 

Damit der Sprite nicht auf dem Startbildschirm zu sehen ist, wird dieser versteckt, wenn die Fahne gedrückt wird.

Wenn die Leertaste gedrückt wird kommt zuerst die Farbauswahl (siehe "Farbauswahl"). Das Raumschiff taucht durch das drücken der Leertaste bei dem für ihn zugewiesenden Platz bei der Farbauswahl auf. An dieser Stelle werden die farblich unterschiedlichen Raumschiffe auf der Linie mit der x-Koordinate -150 aufgereiht. Die y-Koordinate varriert hierbei je nach Farbe des Raumschiffs (blau= 105, grün= 35, rot= -35, gelb= -105). Außerdem wird die eigene Variable auf Null gesetzt.

Anschließend wartet das Raumschiff darauf, dass es von dem Sprite "Meteroit" berührt wird. Tritt dieser Fall ein, so wird das Kostüm erst zur Explosion gewechselt und anschließend verschwindet der Sprite und taucht als "Verloren!"-Schriftzug in der Mitte des Bildschirms auf. Die eigene Variable wird auch hier wieder auf Null gesetzt, damit die Steuerung der Pfeiltasten ausgesetzt wird.

<img width="495" alt="Bildschirmfoto code_raumschiff auswahl" src="https://user-images.githubusercontent.com/111415429/208246347-167d3b78-32b9-400b-99ee-38379c6e6807.png">

Wird das farblich passende Raumschiff bei der Farbauswahl ausgewählt, indem die passende Zahlentaste gedrückt wurde (blau= 1, grün= 2, rot= 3, gelb= 4), wird die eigene Variabel des Raumschiffs auf Eins gewechselt und somit die Steuerung aktiviert. Desweiteren wird davor noch eine Amination durchlaufen, die das Raumschiff in der Mitte des Bildschirms blinkend auftauchen und dieses anschließend nach links zur x-Koordinate -150 gleiten lässt. Hierzu haben wir den Block "blink" kreiert, der den Sprite wiederholt in 0,25 sekunden Abständen verschwinden und wieder auftauchen lässt.

<img width="340" alt="Bildschirmfoto code_raumschiff steuerung" src="https://user-images.githubusercontent.com/111415429/208246333-fc787083-0a49-44cb-bce7-85b8f6ee239c.png">

Die Steuerung der Raumschiffe geschieht durch die Pfeiltasten. Werden diese gedrückt, bewegt sich das Raumschiff, dessen eigene Variable zuvor zu Eins gewechselt wurde, solange in die Richtung der Pfeiltaste bis diese nicht mehr gedrückt wird. Dies ermöglicht dem Raumschiff sich flüssig zu bewegen. Die Dreierschritte wurden gewählt, da diese die ideale Geschwindigkeit für die Bewegung darstellen.

##### III. Laser
blau: ![costume1](https://user-images.githubusercontent.com/111415429/208244740-1d18efe7-f0d5-4444-87a8-6cde8b4c5818.svg), grün:  ![costume1 (1)](https://user-images.githubusercontent.com/111415429/208244745-c05175e0-a0ba-4683-97c6-3997447d7889.svg), rot: ![costume1 (2)](https://user-images.githubusercontent.com/111415429/208244751-618e5388-3aa8-445e-9128-b142ed6bf9df.svg), gelb:  ![costume1 (3)](https://user-images.githubusercontent.com/111415429/208244757-c54f6152-cac2-4ab6-947b-785f6caba59c.svg)

Code:

<img width="492" alt="Bildschirmfoto code_Laser" src="https://user-images.githubusercontent.com/111415429/208293507-d59816b4-bbb7-4e33-842c-3cf6d67680c4.png">

Der Laser soll ebenfalls nicht auf dem Startbildschirm zu sehen sein, weshalb dieser verschwindet sobald die Fahne gedrückt wird.

Nach der Farbauswahl soll nur der farblich zugehörige Laser des ausgewählten Raumschiffes aktiv sein, weshalb die Laser mit den Zahlentasten aktiviert werden. Folglich wird (wie im Beispiel des Screenshots) der blaue Laser auch mit der Eins ausgewählt, was beim grünen, roten und gelben Laser angepasst wurde (grün= 2, rot= 3, gleb= 4).

Ist der Laser aktiv, dadurch das die zugehörige Zahlentaste gedrückt wurde, so durchläuft er eine endlose Schliefe. In der Schleife wartet er darauf, dass "a" gedrückt wird. Tritt dieser Fall ein wird ein Sound abgespielt und ein Klon kreiert. Damit das Drücken der "a"-Taste nur einen Laser abschießt und nicht mehrere, wartet der Laser am Ende der Schleife bis "a" nicht mehr gedrückt wird. So wiederholt sich die Schleife erst, wenn "a" losgelassen und eine kurze Pause abgewartet wurde. Die Pause ist zeitlich nicht wirklich relevant, verhindert jedoch, dass der Laser gespamt wird.

Startet der Laser als Klon, geht er erst zum zugehörigen Raumschiff und zeigt sich dann. Anschließend geht er, bis zum Rand, wo er gelöscht wird, fünfer Schritte auf der X-Achse. Parallel läuft ein Script, welches darauf wartet, dass ein Meteroit berührt wird und den Klon löscht, sobald dies eintrifft. Der Laser läuft somit vom Punkt, wo dieser abgeschossen wird nach rechts über den Bildschirm und wird gelöscht, wenn er einen Meteroiten berührt oder am Rand angekommen ist.

##### IV. Meteroiten
Aussehen des Sprites:
- Meteroit1

![Meteorit1 (1)](https://user-images.githubusercontent.com/111415429/208243445-8e8bc088-2034-4b07-b36d-dea1df0b01ce.png)
- Meterorit2

![Meteorit2](https://user-images.githubusercontent.com/111415429/208243433-7db61437-14fc-48fc-a9b8-ac2b1dfb50e3.png)
- Meteroit3

![Meteorit3](https://user-images.githubusercontent.com/111415429/208243427-562d2f0b-2051-4208-948e-1fe5e5ec0395.png)
- Explosion

![Explosion](https://user-images.githubusercontent.com/111415429/208243470-a56a0e54-3050-4b4f-8c96-968b787303a4.png)

Code:

<img width="685" alt="Bildschirmfoto code_meterorit verhalten" src="https://user-images.githubusercontent.com/111415429/208295472-da9b49f8-66ff-4463-82b4-259611de9043.png">

Dem Meteroiten sind mehrere Variablen zugeschrieben, die beim Neustarten des Spiels alle wieder zum Ausgangszustand gesetzt werden müssen. Der Zähler der getroffenen Meteroiten und der Status "von Laser getroffen" werden durch die Fahne wieder auf Null gesetzt (für den Status bedeutet dies inaktiv) und die beiden anderen Variablen durch das drücken der Leertaste wieder auf den Ausgangszustand. Zusätzlich wird der Zähler für die Meteroiten wieder versteckt, damit dieser nicht zu sehen ist, wenn das eigentliche Spielen noch nicht begonnen hat. Der Meteroit wird ebenfalls versteckt. Nun wartet der Meteroit, bis das eigentliche Spiel beginnt. Das heißt, bis eine Farbe ausgesucht wurde (Block siehe Schriftzüge → "...Pfeiltasten...") und die Pfeiltasten erstmalig benutzt wurden. Somit wird verhindert, dass das Raumschiff schon von Meteroiten getroffen wird, wenn der Spieler noch nicht die Grundscteuerung verstanden hat.

Jetzt wird der Zähler für getroffene Meteroiten gezeigt und in einer Endlosschleife zum nächsten Kostüm gewechselt, von diesem dann ein Klon erstellt und dann die Erscheinungsgeschwindigkeit als Pause abgewartet. Die Erscheinungsgeschwindigkeit ist eine Variable, die zu Beginn der Spielphase, also nach der farbauswahl und dem erstmaligen Benutzen der Pfeiltasten vom Spieler, erst zum Ausgangzustand zurückgesetzt wird und anschließend, bis sie kleiner als 0,5 ist, alle zehn sekunden um -0,01 geändert wird. Sie gibt an wie viele Sekunden abgewartet werden bis ein neuer Klon entsteht.

Die andere Variable die zunimmt, damit das Spiel schwieriger wird ist "steps". Sie gibt an in welchen Schritten sich die Meteroiten bewegen. Auch diese Variable wird zu Anfang der eigentlichen Spielphase auf den Ausgangzusatnd zurückgesetzt. Anschließend wird die Variable alle zehn sekunden um 0,5 erhöht, bis sie gleich zehn ist.

<img width="586" alt="Bildschirmfoto code_meteroit bewegung" src="https://user-images.githubusercontent.com/111415429/208296971-8d638a01-1a57-44b2-bdec-56c9e9a1fae2.png">

In der am Anfang beschriebenden Endlosschleife, wechselt der Sprite zu Anfang das Kostüm, jedoch besitzt der Sprite ebenfalls ein Kostüm für die Explosion, wenn er getroffen wird. Um zu umgehen, dass dieses Kostüm angezeigt wird bei den Meteroiten die über den Bildschirm fliegen, wird sobald ein Klon entsteht dieser darauf geprüft, ob er derzeitig das Kostüm trägt. Sollte diese der Fall sein ändert er sein Kostüm zu Meteroit1 und durchläuft dann das restliche Protokol. Andernfalls durchläuft er sofot das Bewegungsprotokoll. Die Protkolle in der If-else-Klammer sind somit bisauf den Kostümwechsel identisch. Sie besagen, dass der Klon auf einer zufälligen Position auf der Linie mit der x-Koordinate 260 auftaucht, die Laufrichtung auf -90° setzt, was von rechts nach links über den Bildschirm entspricht, und von dort Fortlaufend der Variable ["steps"](https://github.com/InformatikUnterrichtJ/Unser-Projekt/blob/main/README.md#:~:text=neuer%20Klon%20entsteht.-,Die,-andere%20Variable%20die) entsprechend Schritte in die vorgegebene Richtung geht. Nach jedem Schritt wird dabei der Status "von Laser getroffen" geprüft. Sollte dieser gleich Eins, bezieungsweise aktiv sein, wird das Script und somit auch die fortlaufende Schleife gestoppt.

Ebenfalls wartet der Klon darauf, dass seine X-Position kleiner als -250 ist und wird, sobald dies eintrifftgelöscht. Hierdurch wird sichergestellt, dass die Klone am linken Bildschirmrand verschwinden und dort nicht einfach stehen bleiben.

Zusätzlich durchlaufen die Klone eine Schleife, die prüft, ob der Klon von einem Laser berührt wird und diesem eine Explosionsanimation durchlaufen lässt, sobald dies der Fall ist. Nach er Animition wird der Klon gelöscht, damit das Raumschiff nicht mehr von ihm getroffen werden kann. Damit jedoch nicht das Bewegungsscript der nächsten Klone gestoppt wird, wird zu beginn der Schleife der Status "von Laser getroffen" wieder deaktiviert, beziehungsweise auf Null gesetzt.

##### V. Farbauswahl
Aussehen des Bildschirms:
![Download](https://user-images.githubusercontent.com/111415429/208243557-22cf11d7-5fc6-467c-a2eb-45489e5c2b53.png)

Die Farbauswahl besteht aus einem Schriftzug, der durch die Leertaste an dem ihm zugewiesenden Platz auftaucht und durch das auswählen einer Farbe, sowie durch das Drücken der Fahne wieder verschwindet, und den Farbknöpfen.

Code:

<img width="443" alt="Bildschirmfoto code_farbauswahl" src="https://user-images.githubusercontent.com/111415429/208298397-e1de589e-00b9-4a4d-ac98-97d124e65838.png">

Die Farbknöpfe sind einzelnt programmiert. Sie folgen dem gleichen Prinzip wie dem Schriftzug. Die X-Koordinate des zugewiesenden Platzes varriert hierbei je nach Knopf.

Code (Beispiel: button blau):

<img width="442" alt="Bildschirmfoto code_button" src="https://user-images.githubusercontent.com/111415429/208298588-10ed8051-6cb2-4b50-ac8f-56a667cbc908.png">

##### VI. Schriftzüge

Die Schrifftzüge folgen alle dem selben Prinzip. Sie sollen zu einem bestimmten Zeitpunkt auftauchen und verschwinden sobald sie ihre Aufgabe getan haben. Um Dies zu erleichtern haben wir den Block "wait until color is picked" kreiert. Ebenfalls wurde darauf geachtet, dass die Schriftzüge immer in der Obersten Lage sind, damit sie nicht verdeckt werden können.

<img width="388" alt="Bildschirmfoto 2022-12-18 um 13 38 14" src="https://user-images.githubusercontent.com/111415429/208298817-22fc1529-3257-4d29-bfdf-f0acee00e628.png">

Er besagt nur, dass gewartet werden soll, bis eine der Zahlentasten zum auswählen einer farbe gedrückt wurde.

  ###### → "Bewege dich mit den Pfeiltasten nach Oben und Unten"
  
  <img width="402" alt="Bildschirmfoto code_pfeiltasten" src="https://user-images.githubusercontent.com/111415429/208298884-ca5002de-9b6d-4c08-9260-b97d861eb1bd.png">

Der Schrifftzug soll erscheinen, sobald die Spielphase begonnen hat und die Animation des ausgewählen Raumschiffes durchgespielt wurde. Diese deuert ca. drei sekunden. Anschließend verschwindet der Schrifftzug, wenn das in ihm besagte getan wurde, also der Spieler sich mit den Pfeiltasten bewegt hat.
  
  ###### → "Drücke "a" zum Schießen
  
  <img width="403" alt="Bildschirmfoto code_ a" src="https://user-images.githubusercontent.com/111415429/208298991-26b80e8e-9df5-447d-89e0-fc9052715a07.png">

Damit der Spieler sich zuerst mit der Grundsteuerung bekannt machen kann, wartet der Schrifftzug weitere 30 sekunden nachdem der erste Schrifftzug verschwunden ist. Auch dieser Schriftzug verschwindet, sobald das in ihm besagte ausgeführt wurde, in diesem Fall ist das das Drücken von "a".
