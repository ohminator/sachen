# sachen
kp, irgendwelche sachen halt


📘 Dokumentation zum Java-Projekt: Wettlauf mit Läufern (BlueJ)

🔧 Projektübersicht
-------------------
Das Projekt simuliert einen Wettlauf, bei dem mehrere Läufer (Laeufer) auf unterschiedlichen Bahnen gegeneinander antreten. 
Es gibt zwei Klassen:

1. Laeufer – beschreibt einzelne Läufer mit Name, Zeit und Qualifikation.
2. Wettlauf – verwaltet den Ablauf des Rennens, z. B. Startaufstellung, Zeitmessung und Qualifikation.


📦 Klasse Laeufer
------------------
🧾 Zweck:
Stellt einen einzelnen Läufer dar.

📋 Attribute:
- name (String): Name des Läufers
- zeit (double): Gelaufene Zeit in Sekunden
- quali (boolean): Ob der Läufer sich qualifiziert hat

🛠️ Konstruktor:
public Laeufer(String pName)
- Erstellt einen neuen Läufer mit dem gegebenen Namen.
- Zeit wird auf 0.0 gesetzt.
- Qualifikation (quali) auf false.

🧪 Methoden:
- getZeit(): Gibt die aktuelle Zeit des Läufers zurück
- setZeit(double): Setzt die gelaufene Zeit
- getName(): Gibt den Namen zurück
- getQuali(): Gibt zurück, ob sich der Läufer qualifiziert hat
- setQuali(boolean): Setzt den Qualifikationsstatus


🏁 Klasse Wettlauf
-------------------
🧾 Zweck:
Organisiert das Rennen, verwaltet die Läufer und simuliert die Zeiten.

📋 Attribute:
- laeuferfeld (Laeufer[]): Array für alle Läufer (nach Bahn sortiert)
- anzahlBahnen (int): Anzahl der verfügbaren Bahnen
- anzahlLaeufer (int): Aktuell eingesetzte Läufer
- laufbahnBelegt (boolean[]): Gibt an, ob eine Bahn belegt ist

🛠️ Konstruktor:
public Wettlauf(int pAnzahlBahnen)
- Erstellt ein Rennen mit pAnzahlBahnen Bahnen.
- Läufer-Array wird entsprechend erstellt.
- Laufbahnen sind zunächst alle frei.

🧪 Methoden:
- anDenStart(int, Laeufer): Setzt einen Läufer auf die angegebene Bahn, falls diese frei ist.
- bahnBelegt(int): Prüft, ob die Bahn belegt ist.
- zeitMessen(): Gibt die beste gelaufene Zeit (niedrigste Zeit) zurück.
- rennenLaufen(): Simuliert den Lauf für alle Teilnehmer.
  Jeder bekommt eine Zufallszeit zwischen 10.0 und 15.0 Sekunden. Wer ≤ 12.0 läuft, ist qualifiziert.


🏃‍♂️ Beispielhafte Verwendung in BlueJ
--------------------------------------
Laeufer erstellen:
    Laeufer l1 = new Laeufer("Max");
    Laeufer l2 = new Laeufer("Anna");

Wettlauf starten:
    Wettlauf rennen = new Wettlauf(3); // 3 Bahnen

Läufer zuordnen:
    rennen.anDenStart(0, l1);
    rennen.anDenStart(1, l2);

Rennen simulieren:
    rennen.rennenLaufen();

Ergebnisse prüfen:
    l1.getZeit();     // z. B. 11.4
    l1.getQuali();    // true oder false
    rennen.zeitMessen();  // beste Zeit des Rennens


💡 Erweiterungsideen
---------------------
- Mehr Infos über jeden Läufer anzeigen (z. B. Nation, Alter).
- Rennverlauf oder Rangliste ausgeben.
- Weitere Rennen verwalten.
- Grafische Darstellung (GUI mit JavaFX oder Swing).
