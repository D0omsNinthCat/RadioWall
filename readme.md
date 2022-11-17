# Radio-Landkarten-Projekt (Title subject to change)
## Projektidee:

Pin in Landkarte -> Konvertierung der Koordinaten auf der Landkarte zu digital -> Auswahl aus nächstgelegenen Internet-Radiostationen

## Details:

### The Sauce
Als Quelle für den Radiostream kann die  [Radio Garden openApi](https://jonasrmichel.github.io/radio-garden-openapi/) verwendet werden.
Die Challenge hier wird es sein die imput Koordinaten in so zu formattieren, dass die Api uns Internetradios in der Umgebung vorschlägt.
Eine Liste aller Orte mit registrierten Radiostationen und derer Lat/Long Werte bietet die Api unter /ara/content/places bzw. [http://radio.garden/api/ara/content/places]{http://radio.garden/api/ara/content/places}. Das bestmögliche Ergebnis ist also, dass man den den dem Pin am nähesten liegenden Ort findet. Wenn man also den Marker auf Wien setzt können nur alle Wiener Radiostationen auf einmal zurückkommen. Der Parameter "LocalPopularStations" kann dann noch die Radiostationen an einem gewählten Ort nach Popularität sortieren.

### Dimensionen
Die Karte soll an einer Wand angebracht werden können, jedoch groß genug sein um eine präzise Auswahl der Radiostationen zu ermöglichen (z.B. soll noch zwischen London & Bristol unterschieden werden können). Eine übliche Weltkarte hat einen Seitenverhältnis von 1:2.05458.

### Große Welt, kleine Karte
Wenn, wie in größeren Städten oft vorkommt, viele Radiostationen auf kleinem Raum sind, soll dem Nutzer eine Auswahl präsentiert werden. Hierbei wäre denkbar einen Radius in km angeben zu können um zu bestimmen wie groß die Selektion sein soll. Andernfalls wäre eine Auswahl nach "die nähesten X Stationen" denkbar.

### Die Hardware
Als Grundlage für das System kann vorerst ein Raspberry Pi verwendet werden (keine Ahnung welches Modell wir haben aber solange es Wifi hat und einen Aux/BT Output hat und Python darauf läuft sind wir glücklich) welcher im Endprodukt hinter der Karte oder in einem Rahmen verdeckt werden könnte.
Bisherige Recherche hat folgende 2 Ansätze als Favoriten:

1. 2 String potentiometer & Mathe (Corni mach mal eine Skizze).
2. 1 LED Pin und 1 Kamera

Zum Prototyping der Software wird zuerst die LED Lösung umgesetzt. Langfristig ist aber ein kompakteres All-in-one Produkt vorgesehen, welches Raumunabhängig an jeder Wand funktioniert.

### Potentiometer Ansatz
Vorteile:
- portabel
- präzise
- geringer Stromverbrauch

Nachteile:
- teuer
- komplex
- fragil
- zusätzliche Stromquellen

### LED-Lösung
Vorteile:
- billig
- wenige Teile
- läuft über USB
- braucht keinen Rahmen, geht auch an der nackten Wand

Nachteile:
- anfällig auf externe Faktoren (Lichtverhältnisse, Hinderniss vor Kamera)
- braucht eine Kamera gegenüber der Karte
- womöglich weniger präzise
- hacky
- nicht schön