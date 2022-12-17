# Unser-Projekt
### Inhaltsverzeichnis
- [Die Spielidee](https://github.com/InformatikUnterrichtJ/Unser-Projekt/blob/main/README.md#elemente-des-spiels)
- [Übersicht zur Steuerung](https://github.com/InformatikUnterrichtJ/Unser-Projekt/blob/main/README.md#%C3%BCbersicht-zur-steuerung)
- [Elemente des Spiels](https://github.com/InformatikUnterrichtJ/Unser-Projekt/blob/main/README.md#die-spielidee)

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
##### 1. Startbildschirm
-> Soll zu Anfang des Spiels gezeigt werden und anschließend nicht mehr auftauschen ab dem Moment wo die Leertaste gedrückt wurde

Aussehen des Sprites:

(schwarzes Rechteck ergänzt, damit die weiße Schrift zu erkennen ist)![Download (1)](https://user-images.githubusercontent.com/111415429/208243068-e50f57e7-a4fe-42e8-82ce-84859982030d.png)

Code:

<img width="218" alt="Bildschirmfoto 2022-12-17 um 14 21 25" src="https://user-images.githubusercontent.com/111415429/208245038-92eba36b-899c-46a1-8541-f4fb1f62b22e.png">


##### 2. Raumschiff
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

##### 3. Laser
blau: ![costume1](https://user-images.githubusercontent.com/111415429/208244740-1d18efe7-f0d5-4444-87a8-6cde8b4c5818.svg), grün:  ![costume1 (1)](https://user-images.githubusercontent.com/111415429/208244745-c05175e0-a0ba-4683-97c6-3997447d7889.svg), rot: ![costume1 (2)](https://user-images.githubusercontent.com/111415429/208244751-618e5388-3aa8-445e-9128-b142ed6bf9df.svg), gelb:  ![costume1 (3)](https://user-images.githubusercontent.com/111415429/208244757-c54f6152-cac2-4ab6-947b-785f6caba59c.svg)

##### 4. Meteroiten
Aussehen des Sprites:
- Meteroit1

![Meteorit1 (1)](https://user-images.githubusercontent.com/111415429/208243445-8e8bc088-2034-4b07-b36d-dea1df0b01ce.png)
- Meterorit2

![Meteorit2](https://user-images.githubusercontent.com/111415429/208243433-7db61437-14fc-48fc-a9b8-ac2b1dfb50e3.png)
- Meteroit3

![Meteorit3](https://user-images.githubusercontent.com/111415429/208243427-562d2f0b-2051-4208-948e-1fe5e5ec0395.png)
- Explosion

![Explosion](https://user-images.githubusercontent.com/111415429/208243470-a56a0e54-3050-4b4f-8c96-968b787303a4.png)
##### 5. Farbauswahl
Aussehen des Bildschirms:
![Download](https://user-images.githubusercontent.com/111415429/208243557-22cf11d7-5fc6-467c-a2eb-45489e5c2b53.png)
##### 6. Schriftzüge
  ###### 6a. "Bewege die mit den Pfeiltasten nach Oben und Unten"
  ###### 6b. "Drücke "a" zum Schießen
  ###### 6c.
