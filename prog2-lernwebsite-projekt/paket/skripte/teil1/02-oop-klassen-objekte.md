# Skript-Rohtext: Einstieg in die OOP – Klassen und Objekte/Instanzen (Skript S. 162–232)

2
• © Prof. Dr. Ute Matecki
Fakultät Informatik
Programmierung 2
Einstieg in die OOP: Klassen und
Objekte/Instanzen

Einstieg in die OOP: Klassen und Objekte/Instanzen Prof. Dr. Ute Matecki 162
Vorwort
Einstieg in Java
Einstieg in die OOP: Klassen und Objekte/Instanzen
Objekte in der OOP
Klassen in Java
Vereinbarung von Klassen in Java
Erzeugung und Verwendung von Objekten/Instanzen
Sichtbarkeit von Variablen und Methoden – private, public,
protected und Package (kein Modifier)
Instanzvariablen/Instanzmethoden vs.
Klassenvariablen/Klassenmethoden
Arrays aus Objekten/Instanzen
Listen aus Objekten/Instanzen

Einstieg in die OOP: Klassen und Objekte/Instanzen Prof. Dr. Ute Matecki 163
Die Klasse String
Graphische Darstellung von Klassen mit der UML – Teil 1
Vererbungsbeziehungen
Exceptions
Einstieg Streams

Einstieg in die OOP: Klassen und Objekte/Instanzen Objekte in der OOP Prof. Dr. Ute Matecki 164
Objekte in der realen Welt – abgebildet in der Informatik
Beispiele für Objekte
Ein grün lackierter Mini, der Herrn Müller-Lüdenscheid gehört.
Ein Buch mit dem Titel „Grauen der OOP“ von Erna Etepetete,
Ein Besatzungsmitglied eines Raumschis mit dem Namen Spock,
...

Einstieg in die OOP: Klassen und Objekte/Instanzen Klassen in Java Prof. Dr. Ute Matecki 165
Klassen in Java
Was sind Klassen?
Klassen sind Baupläne für Objekte, die versuchen, gemeinsame
Eigenschaen bestimmter Objektarten zu modellieren: Sie enthalten unter
anderem:
Klassenname,
Attribute (Felder) :Zustände eines Objektes dieser Klasse
Methoden :Verhalten eines Objektes dieser Klasse
Konstruktoren (besondere Methoden zur Initialisierung der Attribute)

Einstieg in die OOP: Klassen und Objekte/Instanzen Klassen in Java Prof. Dr. Ute Matecki 166
Klassen und Objekte/Instanzen in Java
Was ist ein Objekt einer Klasse?
Ein Objekt einer Klasse XY ist eine Ausprägung dieser Klasse, welche
anschließend über einen Variablennamen ansprechbar ist. Objekte werden
auch als Instanzen einer Klasse bezeichnet.
Objekte werden immer mit new erzeugt.
Der Aufruf von new bewirkt einen Konstruktoraufruf für das Objekt.
Mit diesem Konstruktoraufruf wird das Objekt im Freispeicherbereich
(Heap) der Java-Virtual-Machine angelegt und initialisiert.

Einstieg in die OOP: Klassen und Objekte/Instanzen Klassen in Java Prof. Dr. Ute Matecki 167
Vereinbarung von Klassen in Java
Vereinbarungssyntax – ohne Vererbungsmechanismen
1 [modifizierer] class KlassenName {
2
3 // Variablen, welche in allen Methoden INNERHALB
4 // der Klassenvereinbarung sichtbar sind
5 [Vereinbarung von Attributen]
6
7 // Konstruktoren sind spezielle Methoden, welche
8 // die Attribute mit Werten initialisieren.
9 [Vereinbarung von Konstruktoren]
10
11 [Vereinbarung von Methoden]
12 }

Einstieg in die OOP: Klassen und Objekte/Instanzen Klassen in Java Prof. Dr. Ute Matecki 168
Vereinbarung von Klassen in Java
Vereinbarungsbeispiel – ohne Vererbungsmechanismen – Teil 1
1 public class Buch1 {
2 String autor; // Attribut 1
3 String titel; // Attribut 2
4
5 // Standardkonstruktor
6 // ACHTUNG: Konstruktoren haben KEINEN Rueckgabetyp!
7 Buch1() {
8 autor="Hugo Helmchen";
9 titel="Allein im Weltraum";
10 } // end constructor
11 // .. weiter auf der naechsten Seite

Einstieg in die OOP: Klassen und Objekte/Instanzen Klassen in Java Prof. Dr. Ute Matecki 169
Vereinbarung von Klassen in Java
Vereinbarungsbeispiel – ohne Vererbungsmechanismen – Teil 1
Hier wird eine Klasse mit 2 Attributen vereinbart
Der parameterlose Konstruktor wird auch als Standardkonstruktor
bezeichnet.
Er setzt die Attribute auf Standard-Werte, die immer gleich sind.
Wichtig: Konstruktoren geben nichts zurück – sie haben also keinen
Rückgabetyp!

Einstieg in die OOP: Klassen und Objekte/Instanzen Klassen in Java Prof. Dr. Ute Matecki 170
Vereinbarung von Klassen in Java
Vereinbarungsbeispiel – ohne Vererbungsmechanismen – Teil 2
12 // ... weiter von Teil 1 ...
13 // Voll qualifizierter Konstruktor
14 Buch1(String autor, String titel) {
15 this.autor = autor;
16 this.titel = titel;
17 } // end constructor
18
19 // Ausgabemethode -- sie gibt die Attributwerte aus!
20 void print() {
21 System.out.println("Titel: " + titel);
22 System.out.println("Autor: " + autor);
23 } // end method
24 } // end class

Einstieg in die OOP: Klassen und Objekte/Instanzen Klassen in Java Prof. Dr. Ute Matecki 171
Vereinbarung von Klassen in Java
Vereinbarungsbeispiel – ohne Vererbungsmechanismen – Teil 2
Der Konstruktor mit Parametern, die alle Attribute belegen wird auch
als voll qualifizierter Konstruktor bezeichnet.
Er setzt die Attribute auf die Werte, die als Parameter übergeben wurden.
Die Variable this ist eine Referenz auf das Objekt, in dem wir uns gerade
befinden, wenn der Konstruktor abläu. Also dieses Objekt. (vgl. self in
Python).
Würden wir this im voll qualifizierten Konstruktor nicht verwenden:
autor = autor;
In diesem Fall würde der Übergabeparameter einfach mit sich selbst
belegt werden! (Gültigkeitsbereiche: lokaler Parameter überlagert
global!)

Einstieg in die OOP: Klassen und Objekte/Instanzen Klassen in Java Prof. Dr. Ute Matecki 172
Begriswiederholung: Klassen und Objekte/Instanzen in Java
Wir wiederholen: Was ist ein Objekt einer Klasse?
Ein Objekt einer Klasse XY ist eine Ausprägung dieser Klasse, welche
anschließend über einen Variablennamen ansprechbar ist. Objekte werden
auch als Instanzen einer Klasse bezeichnet.
Objekte werden immer mit new erzeugt.
Der Aufruf von new bewirkt einen Konstruktoraufruf für das Objekt.
Mit diesem Konstruktoraufruf wird das Objekt im Freispeicherbereich
(Heap) der Java-Virtual-Machine angelegt und initialisiert.

Einstieg in die OOP: Klassen und Objekte/Instanzen Klassen in Java Prof. Dr. Ute Matecki 173
Erzeugung von Objekten/Instanzen
Syntax der Objekterzeugung
// Erzeugung eines Objektes mit Standardkonstruktor
KlassenName variablenName1 = new KlassenName();
// Erzeugung eines Objektes mit einem parametrisierten
// Konstruktor
// Dies kann beispielsweise ein voll qualifizierter
// Konstruktor sein
KlassenName variablenName2 =
new KlassenName(param1,...,paramN);

Einstieg in die OOP: Klassen und Objekte/Instanzen Klassen in Java Prof. Dr. Ute Matecki 174
Attribute und Methoden von erzeugten Objekten/Instanzen
Zugri auf Attribute und Methoden von Objekten
// Zugriff auf ein Attribut von Objekt obj1:
obj1.attribut1 = wert;
// Aufruf einer Methode von Objekt obj1:
obj1.methode();

Einstieg in die OOP: Klassen und Objekte/Instanzen Klassen in Java Prof. Dr. Ute Matecki 175
Beispiel zu Objekterzeugung und Methodenaufruf
Unsere Buch-Klasse von vorhin – Teil 1
public class Buch1 {
String autor; // Attribut 1
String titel; // Attribut 2
// Standardkonstruktor
// ACHTUNG: Konstruktoren haben KEINEN Rueckgabetyp!
Buch1() {
autor="Hugo Helmchen";
titel="Allein im Weltraum";
} // end constructor
// .. weiter auf der naechsten Seite

Einstieg in die OOP: Klassen und Objekte/Instanzen Klassen in Java Prof. Dr. Ute Matecki 176
Beispiel zu Objekterzeugung und Methodenaufruf
Unsere Buch-Klasse von vorhin – Teil 2
12 // ... weiter von Teil 1 ...
13 // Voll qualifizierter Konstruktor
14 Buch1(String autor, String titel) {
15 this.autor = autor;
16 this.titel = titel;
17 } // end constructor
18
19 // Ausgabemethode -- sie gibt die Attributwerte aus!
20 void print() {
21 System.out.println("Titel: " + titel);
22 System.out.println("Autor: " + autor);
23 } // end method
24 } // end class

Einstieg in die OOP: Klassen und Objekte/Instanzen Klassen in Java Prof. Dr. Ute Matecki 177
Beispiel zu Objekterzeugung und Methodenaufruf
Eine main()-Klasse, die zwei Bücher erzeugt – Teil 1
1 public class BuchMain1 {
2
3 public static void main(String[] args) {
4
5 // Objekt b1: Aufruf des voll qualifizierten
6 // Konstruktors
7 Buch1 b1 = new Buch1("Gernot Grusel",
8 "Das Grauen der OOP");
9
10 // Objekt b2: Aufruf des Standardkonstruktors
11 Buch1 b2 = new Buch1();
12 // ... weiter in Teil 2

Einstieg in die OOP: Klassen und Objekte/Instanzen Klassen in Java Prof. Dr. Ute Matecki 178
Beispiel zu Objekterzeugung und Methodenaufruf
Eine main()-Klasse, die zwei Bücher erzeugt – Teil 2
13 // ... weiter von Teil 1
14 // Methodenaufruf bei b1:
15 b1.print();
16
17 // Methodenaufruf bei b2:
18 b2.print();
19 } // end method main()
20 } // end class

Einstieg in die OOP: Klassen und Objekte/Instanzen Klassen in Java Prof. Dr. Ute Matecki 179
Beispiel zu Objekterzeugung und Methodenaufruf
Compilierung und Start des Buch-Programms mit ...
javac Buch1.java
javac BuchMain1.java
java BuchMain1
... oder innerhalb von Eclipse ...

Einstieg in die OOP: Klassen und Objekte/Instanzen Klassen in Java Prof. Dr. Ute Matecki 180
Beispiel zu Objekterzeugung und Methodenaufruf
Start des Programms liefert die Ausgabe
Titel: Das Grauen der OOP
Autor: Gernot Grusel
Titel: Allein im Weltraum
Autor: Hugo Helmchen

Einstieg in die OOP: Klassen und Objekte/Instanzen Klassen in Java Prof. Dr. Ute Matecki 181
Zusammenfassung Klassen und Objekte
Was sind Klassen?
Klassen sind Baupläne für Objekte, die versuchen, gemeinsame
Eigenschaen bestimmter Objektarten zu modellieren: Sie enthalten unter
anderem:
Klassenname,
Attribute (Felder) :Zustände eines Objektes dieser Klasse
Methoden :Verhalten eines Objektes dieser Klasse
Konstruktoren (besondere Methoden zur Initialisierung der Attribute)

Einstieg in die OOP: Klassen und Objekte/Instanzen Klassen in Java Prof. Dr. Ute Matecki 182
Zusammenfassung Klassen und Objekte
Was ist ein Objekt einer Klasse?
Ein Objekt einer Klasse XY ist eine Ausprägung dieser Klasse, welche
anschließend über einen Variablennamen ansprechbar ist. Objekte werden
auch als Instanzen einer Klasse bezeichnet.
Objekte werden immer mit new erzeugt.
Der Aufruf von new bewirkt einen Konstruktoraufruf für das Objekt.
Mit diesem Konstruktoraufruf wird das Objekt im Freispeicherbereich
(Heap) der Java-Virtual-Machine angelegt und initialisiert.

Einstieg in die OOP: Klassen und Objekte/Instanzen Klassen in Java Prof. Dr. Ute Matecki 183
Zusammenfassung Klassen und Objekte
Was ist ein Objekt einer Klasse?
Attribute und Methoden von Objekten/Instanzen werden mit dem
„.“-Operator angesprochen:
obj.attribut=wert;
obj.methodenaufruf();
Objekte existieren nach der Erzeugung auf dem Freispeicher nur einmal.
Die Variable, über die ein Objekt/eine Instanz angesprochen wird,
enthält nur eine Referenz auf das Objekt – also seine Adresse.

Einstieg in die OOP: Klassen und Objekte/Instanzen Klassen in Java Prof. Dr. Ute Matecki 184
Zusammenfassung Klassen und Objekte
Was ist ein Objekt einer Klasse?
Mehrere Referenzen können auf das gleiche Objekt verweisen –
beispielsweise mit:
Klassenname obj2 = obj;
Hier wird kein neues Objekt erzeugt – die Referenz obj2 verweist auf
die gleiche Adresse wie obj!

Einstieg in die OOP: Klassen und Objekte/Instanzen Sichtbarkeit von Variablen und Methoden – private, public, protected und Package (kein Modifier)
Prof. Dr. Ute Matecki 185
Bisherige Klassenvereinbarungen ...
... mit Attributen und Methoden ohne zusätzliche Angaben
public class Buch1 {
String autor; // Attribute ohne weitere Angaben ...
String titel;
Buch1() { // Konstruktor ohne weitere Angaben ...
// ...
}
void print() { // Methode ohne weitere Angaben ...
// ...
}
} // end class

Einstieg in die OOP: Klassen und Objekte/Instanzen Sichtbarkeit von Variablen und Methoden – private, public, protected und Package (kein Modifier)
Prof. Dr. Ute Matecki 186
Bisherige Klassenvereinbarungen ...
... mit Attributen und Methoden ohne zusätzliche Angaben
Konsequenz aus dem Weglassen zusätzlicher Angaben (Modifizierer)
Attribute eines sind einfach von jeder Methode jeder Klasse aus
sichtbar, die sich in der gleichen Organisationseinheit (Package)
befindet, wie das Objekt, dem die Attribute gehören.
Das gleiche gilt für die Methoden eines Objektes.

Einstieg in die OOP: Klassen und Objekte/Instanzen Sichtbarkeit von Variablen und Methoden – private, public, protected und Package (kein Modifier)
Prof. Dr. Ute Matecki 187
Erzeugung und Verwendung von Objekten der bisherigen Klassen
Zunächst Erzeugung und Ausgabe ...
1 public class BuchMain2 {
2
3 public static void main(String[] args) {
4
5 // Objekt b1: Aufruf des voll qualifizierten
6 // Konstruktors
7 Buch1 b1 = new Buch1("Gernot Grusel",
8 "Das Grauen der OOP");
9
10 // Methodenaufruf bei b1: Ausgabe der
11 // Attribute von b1
12 b1.print();

Einstieg in die OOP: Klassen und Objekte/Instanzen Sichtbarkeit von Variablen und Methoden – private, public, protected und Package (kein Modifier)
Prof. Dr. Ute Matecki 188
Ausgabe nach der Objekterzeugung ist ...
... ähnlich wie vorher:
Titel: Das Grauen der OOP
Autor: Gernot Grusel

Einstieg in die OOP: Klassen und Objekte/Instanzen Sichtbarkeit von Variablen und Methoden – private, public, protected und Package (kein Modifier)
Prof. Dr. Ute Matecki 189
Erzeugung und Verwendung von Objekten der bisherigen Klassen
...danach Manipulation eines Attributes
13 // Wir aendern den Autor des Buches ...
14 b1.autor = "Hans Hinkel";
15
16 // ... und geben nochmals die Attribute aus:
17 b1.print();
18
19 } // end method main()
20 } // end class

Einstieg in die OOP: Klassen und Objekte/Instanzen Sichtbarkeit von Variablen und Methoden – private, public, protected und Package (kein Modifier)
Prof. Dr. Ute Matecki 190
Ausgabe nach der Manipulation ...
... zeigt einen anderen Autor des gleichen Buches:
Titel: Das Grauen der OOP
Autor: Hans Hinkel
Wir stellen uns derartige Manipulationen in 100000 lines of code vor ... .

Einstieg in die OOP: Klassen und Objekte/Instanzen Sichtbarkeit von Variablen und Methoden – private, public, protected und Package (kein Modifier)
Prof. Dr. Ute Matecki 191
Prinzip des Information Hiding
... wurde mit der bisherigen Klassenstruktur verletzt
Da die Attribute des Objektes mit der Referenz b1 von außenstehenden
Klassen sichtbar sind, können sie von beliebigen Stellen im Code
manipuliert werden. Dies kann zu beliebig unlesbaren Programmen und zu
bösen Stolperfallen führen.

Einstieg in die OOP: Klassen und Objekte/Instanzen Sichtbarkeit von Variablen und Methoden – private, public, protected und Package (kein Modifier)
Prof. Dr. Ute Matecki 192
Prinzip des Information Hiding
Unter Information Hiding in der OOP verstehen wir ...
das Verbergen der Daten in den Objektattributen, sowie
das Verbergen der Implementierung von Methoden.
z. B. die Attribute eines Objektes sollen nur über den Konstruktor einmal
intitial gesetzt werden, und danach nicht mehr verändert werden.
z. B. will ein Bauplan einer Klasse nur einige wenige Methoden nach
außen hin sichtbar machen. Kleine Hilfsmethoden, die von diesen
genutzt werden, sollen verborgen werden.

Einstieg in die OOP: Klassen und Objekte/Instanzen Sichtbarkeit von Variablen und Methoden – private, public, protected und Package (kein Modifier)
Prof. Dr. Ute Matecki 193
Prinzip des Information Hiding
... in Java umgesetzt durch Modifier (dt. Modifizierer)
Modifier sind Schlüsselworte, mit denen wir das Standardverhalten von
Klassen, Attributen und Methoden verändern können.
Diese Schlüsselworte werden vor die Klassen-, Methoden- oder
Attributdefinition geschrieben.
Modifier für die Sichtbarkeit verändern das Sichtbarkeitsverhalten von
Klassen, Methoden und Attributen.
Wir werden im Laufe der Vorlesung die drei dieser Modifier
public,private und protected kennenlernen.
Wir werden auch das Verhalten ohne diese drei Modifier beleuchten.

Einstieg in die OOP: Klassen und Objekte/Instanzen Sichtbarkeit von Variablen und Methoden – private, public, protected und Package (kein Modifier)
Prof. Dr. Ute Matecki 194
Übersicht Sichtbarkeitsmodifizierer
Modifier Beschreibung
public
Außenstehende Klassen und Objekte und Methoden können public gesetzte Attribute und Methoden von anderen Objekten sehen und voll darauf
zugreifen.
private
Außenstehende Klassen, Objekte und Methoden
können Attribute und Methoden mit diesem Zugrisschutz nicht sehen.

Einstieg in die OOP: Klassen und Objekte/Instanzen Sichtbarkeit von Variablen und Methoden – private, public, protected und Package (kein Modifier)
Prof. Dr. Ute Matecki 195
Übersicht Sichtbarkeitsmodifizierer
Modifier Beschreibung
protected
Außenstehende Objekte können Attribute und Methoden mit diesem Zugrisschutz nicht sehen.
Nur Methoden von Kindklassen oder von Klassen
im gleichen Package (kommt beides später) können auf Attribute und Methoden mit diesem Zugrisschutz zugreifen.
kein Sichtbarkeitsmodifizierer
Nur Methoden von Klassen im gleichen Package
(kommt später) können auf Attribute und Methoden ohne Sichtbarkeitsmodifizierer zugreifen.

Einstieg in die OOP: Klassen und Objekte/Instanzen Sichtbarkeit von Variablen und Methoden – private, public, protected und Package (kein Modifier)
Prof. Dr. Ute Matecki 196
Beispiel zu den Modifizierern public und private
Modifizierte Buch-Klasse – Teil 1
1 public class Buch2 {
2 private String autor;
3 private String titel;
4 private int auflage;
Ein weiteres Attribut (auflage) ist hinzugekommen.
Alle drei Attribute sind private

Einstieg in die OOP: Klassen und Objekte/Instanzen Sichtbarkeit von Variablen und Methoden – private, public, protected und Package (kein Modifier)
Prof. Dr. Ute Matecki 197
Beispiel zu den Modifizierern public und private
Modifizierte Buch-Klasse – Teil 2
5 public Buch2() {
6 this.autor="Hugo Helmchen";
7 this.titel="Allein im Weltraum";
8 this.auflage=1;
9 } // end constructor
10
11 public Buch2(String autor, String titel, int auflage) {
12 this.autor = autor;
13 this.titel = titel;
14 this.auflage = auflage;
15 } // end constructor
Beide Konstruktoren sind public
Sie belegen nun alle drei Attribute mit Werten.

Einstieg in die OOP: Klassen und Objekte/Instanzen Sichtbarkeit von Variablen und Methoden – private, public, protected und Package (kein Modifier)
Prof. Dr. Ute Matecki 198
Beispiel zu den Modifizierern public und private
Modifizierte Buch-Klasse – Teil 3
16 // get-Methoden fuer Autor und Titel
17 public String getAutor() {
18 return autor;
19 } // end method
20
21 public String getTitel() {
22 return titel;
23 } // end method
Es gibt nun zwei public-Methoden zum Abfragen von Autor und Titel
Wir erinnern uns: Die Attribute, die hier mit return zurückgegeben
werden, sind private!
Wir können mit diesen Methoden nur Werte abfragen – nicht ändern!

Einstieg in die OOP: Klassen und Objekte/Instanzen Sichtbarkeit von Variablen und Methoden – private, public, protected und Package (kein Modifier)
Prof. Dr. Ute Matecki 199
Beispiel zu den Modifizierern public und private
Modifizierte Buch-Klasse – Teil 4
24 public int getAuflage() {
25 return auflage;
26 } // end method
27
28 public void setAuflage(int auflage) {
29 this.auflage = auflage;
30 } // end method
31 } // end class
Für das Attribut Auflage: public getter()-Methode und
setter()-Methode
Wir können mit der setter()-Methode das Attribut auflage nach der
Objekterzeugung verändern!

Einstieg in die OOP: Klassen und Objekte/Instanzen Sichtbarkeit von Variablen und Methoden – private, public, protected und Package (kein Modifier)
Prof. Dr. Ute Matecki 200
Beispiel zu den Modifizierern public und private
Modifizierte main()-Klasse Teil 1
1 public class BuchMain2Modified {
2
3 public static void main(String[] args) {
4
5 Buch2 b = new Buch2("G. Grusel","Grauen der OOP",5);
6
7 // Attribute abfragen
8 String aut = b.getAutor();
9 String ti = b.getTitel();
10 int aufl = b.getAuflage();
:getter() liefern Attribute zurück

Einstieg in die OOP: Klassen und Objekte/Instanzen Sichtbarkeit von Variablen und Methoden – private, public, protected und Package (kein Modifier)
Prof. Dr. Ute Matecki 201
Beispiel zu den Modifizierern public und private
Modifizierte main()-Klasse Teil 1
11 // Abgefragte Attribut-Werte mit ihren aktuellen
12 // Werten ausgeben
13 System.out.println("Autor: "+ aut);
14 System.out.println("Titel: "+ti);
15 System.out.println("Auflage: " + aufl);
Die mit den getter()-Methoden abgefragten Attribut-Werte
werden in lokalen Variablen in main() abgelegt.
Die Werte dieser lokalen Variablen geben wir auf die Konsole aus.

Einstieg in die OOP: Klassen und Objekte/Instanzen Sichtbarkeit von Variablen und Methoden – private, public, protected und Package (kein Modifier)
Prof. Dr. Ute Matecki 202
Beispiel zu den Modifizierern public und private
Modifizierte main()-Klasse Teil 1
17 // Wert von aufl aendern und neu einsetzen:
18 // Buch liegt nun in der 6. Auflage vor
19 aufl ++;
20 b.setAuflage(aufl);
21 System.out.println(
22 "Auflage: " + b.getAuflage());
23 } // end method main()
24 } // end class
Der private Attributwert auflage von b wird nun mit der setter()-
Methode auf den Wert 6 gesetzt.
Anschließend wird er mit der getter()-Methode für die Konsol-Ausgabe
wieder abgefragt.

Einstieg in die OOP: Klassen und Objekte/Instanzen Sichtbarkeit von Variablen und Methoden – private, public, protected und Package (kein Modifier)
Prof. Dr. Ute Matecki 203
Zusammenfassung zu Sichtbarkeitsmodifizierern
Sichtbarkeitsmodifizierer und das Prinzip des Information Hiding
Sichtbarkeitsmodifizierer können auf Methoden und Attribute
innerhalb von Klassen angewendet werden:
- private bedeutet: Das Attribut / Die Methode ist von Methoden anderer Klassen aus
nicht sichtbar.
- Es ist also nicht möglich, mit obj.variable=wert; oder mit
obj.methodenaufruf(); auf sie zuzugreifen.
- public bedeutet: Das Attribut / Die Methode ist von überall aus sichtbar!
Daneben können Sichtbarkeitsmodifizierer auch auf
Klassendefinitionen angewendet werden.
So bedeutet z.B. public class Foo {...}: Die Klasse Foo ist auch in
jedem anderen Package außerhalb des eigenen Packages sichtbar.
(Packages kommen später ...)

Einstieg in die OOP: Klassen und Objekte/Instanzen Instanzvariablen/Instanzmethoden vs. Klassenvariablen/Klassenmethoden Prof. Dr. Ute Matecki 204
Bisher behandelt: Instanzvariablen/Instanzmethoden
Für Instanzvariablen und Instanzmethoden gilt:
Variablen werden bei jeder neu erzeugten Instanz einer Klasse separat
aufgebaut.
Methoden u. U. auch. Das bedeutet: Jedes Objekt einer Klasse XY hat
seine eigenen Instanzvariablen und Instanzmethoden.
Um Methoden aufrufen zu können, mussten wir ein Arbeitsobjekt bzw.
eine Arbeitsinstanz einrichten.
Das gleiche galt für den Variablenzugri.

Einstieg in die OOP: Klassen und Objekte/Instanzen Instanzvariablen/Instanzmethoden vs. Klassenvariablen/Klassenmethoden Prof. Dr. Ute Matecki 205
Bisher behandelt: Instanzvariablen/Instanzmethoden
Für Instanzvariablen und Instanzmethoden gilt:
Daher werden derartige Variablen und Methoden als Instanzvariablen
bzw. Instanzmethoden bezeichnet.
Als Synonym werden auch die Begrie Objektvariablen bzw.
Objektmethoden verwendet.

Einstieg in die OOP: Klassen und Objekte/Instanzen Instanzvariablen/Instanzmethoden vs. Klassenvariablen/Klassenmethoden Prof. Dr. Ute Matecki 206
Beispiel zu Instanzvariablen
Klasse Person1
1 public class Person1 {
2 private String name;
3
4 public Person1(String name) {
5 this.name = name;
6 } // end constructor
7
8 public String getName() {
9 return name;
10 } // end method
11 } // end class
Instanzvariable

Einstieg in die OOP: Klassen und Objekte/Instanzen Instanzvariablen/Instanzmethoden vs. Klassenvariablen/Klassenmethoden Prof. Dr. Ute Matecki 207
Beispiel zu Instanzvariablen
Klasse PersonMain1 erzeugt zwei Instanzen
public class PersonMain1 {
public static void main() {
Person1 p = new Person1("Erna");
Person1 q = new Person1("Hugo");
}
}

Einstieg in die OOP: Klassen und Objekte/Instanzen Instanzvariablen/Instanzmethoden vs. Klassenvariablen/Klassenmethoden Prof. Dr. Ute Matecki 208
Einführung von Klassenvariablen und Klassenmethoden
Klasse Person2 mit Modifizierer static
1 public class Person2 {
2 private static String name;
3
4 public Person2(String name) {
5 this.name = name;
6 } // end constructor
7
8 public static void print() {
9 System.out.println("Ich heisse: " + name);
10 }
11 } // end class
Klassenvariable

Einstieg in die OOP: Klassen und Objekte/Instanzen Instanzvariablen/Instanzmethoden vs. Klassenvariablen/Klassenmethoden Prof. Dr. Ute Matecki 209
Einführung von Klassenvariablen und Klassenmethoden
Klasse Person2 mit Modifizierer static
1 public class Person2 {
2 private static String name;
3
4 public Person2(String name) {
5 this.name = name;
6 } // end constructor
7
8 public static void print() {
9 System.out.println("Ich heisse: " + name);
10 }
11 } // end class
Klassenmethode

Einstieg in die OOP: Klassen und Objekte/Instanzen Instanzvariablen/Instanzmethoden vs. Klassenvariablen/Klassenmethoden Prof. Dr. Ute Matecki 210
Einführung von Klassenvariablen und Klassenmethoden
Klasse PersonMain2 erzeugt ebenfalls 2 Instanzen, aber:
public class PersonMain2 {
public static void main(String [] args) {
Person2 p = new Person2("Erna");
Person2 q = new Person2("Hugo");
p.print();
q.print();
} // end method main()
} // end class

Einstieg in die OOP: Klassen und Objekte/Instanzen Instanzvariablen/Instanzmethoden vs. Klassenvariablen/Klassenmethoden Prof. Dr. Ute Matecki 211
Einführung von Klassenvariablen und Klassenmethoden
Klasse PersonMain2 erzeugt ebenfalls 2 Instanzen, aber:
Variablen mit dem Modifizierer static existieren nur einmal,
gleichgültig, wie viele Instanzen der Klasse erzeugt werden!
Bei der Benutzung von statischen Variablen und Methoden kann auf die
Erstellung einer Arbeitsinstanz verzichtet werden!
Statt dessen können wir statische Variablen und Methoden direkt über
den Klassennamen ansprechen :Klassenvariablen bzw.
Klassenmethoden!

Einstieg in die OOP: Klassen und Objekte/Instanzen Instanzvariablen/Instanzmethoden vs. Klassenvariablen/Klassenmethoden Prof. Dr. Ute Matecki 212
Einführung von Klassenvariablen und Klassenmethoden
Klassenvariablen und Klassenmethoden können ohne Instanz
angesprochen werden
1 public class Person3 {
2 public static String name;
3
4 public Person3(String name) {
5 this.name = name;
6 } // end constructor
7
8 public static void print() {
9 System.out.println("Ich heisse: " + name);
10 }
11 } // end class
Zu Testzwecken hier public

Einstieg in die OOP: Klassen und Objekte/Instanzen Instanzvariablen/Instanzmethoden vs. Klassenvariablen/Klassenmethoden Prof. Dr. Ute Matecki 213
Einführung von Klassenvariablen und Klassenmethoden
Klassenvariablen und Klassenmethoden können ohne Instanz
angesprochen werden
public class PersonMain3 {
public static void main(String [] args) {
Person3.name = "Hugo";
Person3.print();
} // end method main()
} // end class

Einstieg in die OOP: Klassen und Objekte/Instanzen Instanzvariablen/Instanzmethoden vs. Klassenvariablen/Klassenmethoden Prof. Dr. Ute Matecki 214
Einführung von Klassenvariablen und Klassenmethoden
Wo machen statische Variablen/Methoden denn nun Sinn?
Für allgemeine Konstanten (final), die dann mit Klasse.konstante
verwendet werden.
Für Methoden, die sich zwischen ihren Aufrufen keine Zwischenzustände
merken müssen.

Einstieg in die OOP: Klassen und Objekte/Instanzen Instanzvariablen/Instanzmethoden vs. Klassenvariablen/Klassenmethoden Prof. Dr. Ute Matecki 215
Einführung von Klassenvariablen und Klassenmethoden
Sinnvolles Beispiel für static
1 // Klasse zur Umrechnung Kelvin --> Celsius
2 public class StaticOk {
3 // Konstante: Absoluter Nullpunkt
4 static final double kelvinNull=-273.15;
5
6 // Methode zur Umrechnung Kelvin --> Celsius
7 static double gradCelsius(double kelvin) {
8 double celsius = kelvin + kelvinNull;
9 return celsius;
10 } // end method
11 } // end class
Statische Konstante

Einstieg in die OOP: Klassen und Objekte/Instanzen Instanzvariablen/Instanzmethoden vs. Klassenvariablen/Klassenmethoden Prof. Dr. Ute Matecki 216
Einführung von Klassenvariablen und Klassenmethoden
Sinnvolles Beispiel für static
1 // Klasse zur Umrechnung Kelvin --> Celsius
2 public class StaticOk {
3 // Konstante: Absoluter Nullpunkt
4 static final double kelvinNull=-273.15;
5
6 // Methode zur Umrechnung Kelvin --> Celsius
7 static double gradCelsius(double kelvin) {
8 double celsius = kelvin + kelvinNull;
9 return celsius;
10 } // end method
11 } // end class
Statische Methode: Sie muss sich keine „Objektzustände“ merken –
wird einfach immer wieder bei Bedarf mit neuer ◦K-Zahl aufgerufen.

Einstieg in die OOP: Klassen und Objekte/Instanzen Instanzvariablen/Instanzmethoden vs. Klassenvariablen/Klassenmethoden Prof. Dr. Ute Matecki 217
Einführung von Klassenvariablen und Klassenmethoden
Sinnvolles Beispiel für static – Anwendung in main()
1 import java.util.Locale;
2 // ... Ausschnitt aus main()-Methode ...
3 double k=245.0;
4 Locale.setDefault(Locale.ENGLISH); // Punkt statt Komma
5 System.out.println(
6 "Abs. Nullpunkt Kelvin: " + StaticOk.kelvinNull );
7
8 double c = StaticOk.gradCelsius(k) ;
9 // %.2f heisst: Ausgabe als float oder double mit
10 // 2 Nachkomma-Stellen
11 System.out.printf(
12 "%.2f Grad Kelvin entspricht %.2f Grad Celsius", k,c);

Einstieg in die OOP: Klassen und Objekte/Instanzen Instanzvariablen/Instanzmethoden vs. Klassenvariablen/Klassenmethoden Prof. Dr. Ute Matecki 218
Einführung von Klassenvariablen und Klassenmethoden
Zusammenfassung Klassenvariablen und Klassenmethoden
Statische Variablen werden auch als Klassenvariablen bezeichnet, da
der Zugri auf sie nur an den Klassennamen, nicht aber an ein Objekt
gebunden ist.
Dementsprechend werden Statische Methoden auch als
Klassenmethoden bezeichnet.
Nicht-Statische Variablen werden auch als Instanzvariablen bzw.
Objektvariablen bezeichnet, da der Zugri auf sie immer an ein
Objekt/eine Instanz gebunden ist.
Dementsprechend werden Nicht-Statische Methoden auch als
Instanzmethoden bzw. Objektmethoden bezeichnet.

Einstieg in die OOP: Klassen und Objekte/Instanzen Arrays aus Objekten/Instanzen Prof. Dr. Ute Matecki 219
Bereits kennengelernt: Arrays elementarer Datentypen
Syntax zur Vereinbarung von Arrays
// Moeglichkeit 1:
datentyp [] arrayname = new datentyp [anzahl];
// Moeglichkeit 2:
datentyp [] arrayname2 = {element1, element2, ... , elementN};
:Arrays haben, nachdem sie einmal angelegt wurden, eine feste Größe!

Einstieg in die OOP: Klassen und Objekte/Instanzen Arrays aus Objekten/Instanzen Prof. Dr. Ute Matecki 220
Neu: Arrays aus Objekten/Instanzen
Arbeitsschritte zur Erzeugung von Arrays aus Objekten
Erzeugung der Referenz für das Array selbst
Erzeugung der Instanzen
Einhängen der Instanzen ins Array

Einstieg in die OOP: Klassen und Objekte/Instanzen Arrays aus Objekten/Instanzen Prof. Dr. Ute Matecki 221
Beispiel zu Arrays aus Objekten/Instanzen
Unsere Personenklasse wird zur Objekterzeugung verwendet
1 public class Person1 {
2 private String name;
3
4 public Person1(String name) {
5 this.name = name;
6 } // end constructor
7
8 public String getName() {
9 return name;
10 } // end method
11 } // end class

Einstieg in die OOP: Klassen und Objekte/Instanzen Arrays aus Objekten/Instanzen Prof. Dr. Ute Matecki 222
Beispiel zu Arrays aus Objekten/Instanzen
main()-Klasse zur Objekterzeugung
1 import java.util.Scanner;
2
3 public class PersonMainArray1 {
4
5 public static void main(String[] args) {
6
7 // Scanner zum Eintippen der Personen-Namen
8 Scanner tastatur = new Scanner(System.in);
9
10 // Schritt 1: Erzeugung der Array-Referenz
11 // Wir wollen Platz fuer 3 Personen
12 Person1 [] personen = new Person1[3];

Einstieg in die OOP: Klassen und Objekte/Instanzen Arrays aus Objekten/Instanzen Prof. Dr. Ute Matecki 223
Beispiel zu Arrays aus Objekten/Instanzen
main()-Klasse zur Objekterzeugung
13 // Schleife fuer die Belegung des Arrays
14 for (int i=0; i < personen.length; i++) {
15 System.out.print("Name der naechsten Person: ");
16 String name = tastatur.nextLine();
17
18 // Schritt 2: Erzeugung der Instanz
19 Person1 p = new Person1(name);
20
21 // Schritt 3: Einhaengen ins Array
22 personen[i] = p;
23 } // end for

Einstieg in die OOP: Klassen und Objekte/Instanzen Arrays aus Objekten/Instanzen Prof. Dr. Ute Matecki 224
Beispiel zu Arrays aus Objekten/Instanzen
main()-Klasse zur Objekterzeugung
24 // Testen des Arrays: Ausgabe aller Personennamen
25 System.out.println("----- Wir haben eingegeben: -----");
26 // Schleife fuer die Ausgabe des Arrays
27 for (int i=0; i < personen.length; i++) {
28 String name = personen[i].getName();
29 System.out.println(name);
30 } // end for
31 } // end method main()
32 } // end class

Einstieg in die OOP: Klassen und Objekte/Instanzen Listen aus Objekten/Instanzen Prof. Dr. Ute Matecki 225
Listen aus Objekten/Instanzen
Beispiel ArrayList
Unterschied zu Arrays: Listen können wachsen / schrumpfen
Unterschied zu Arrays: Listen können nur Referenzvariablen aufnehmen,
keine Variablen elementaren Typs!
Listen können entweder selbst implementiert werden ...
... oder wir nutzen eine der vorgefertigten Listenklassen von Java: z. B.
die Klasse ArrayList.

Einstieg in die OOP: Klassen und Objekte/Instanzen Listen aus Objekten/Instanzen Prof. Dr. Ute Matecki 226
Listen aus Objekten/Instanzen
Syntax beim Anlegen einer ArrayList
1 ArrayList <Typ> variablenname = new ArrayList<Typ>();
Objekttyp der Liste Konstruktoraufruf

Einstieg in die OOP: Klassen und Objekte/Instanzen Listen aus Objekten/Instanzen Prof. Dr. Ute Matecki 227
Listen aus Objekten/Instanzen
Syntax beim Anlegen einer ArrayList – Liste aus Personen
1 ArrayList <Person1> variablenname = new ArrayList<Person1>();
Objekttyp der Liste Konstruktoraufruf

Einstieg in die OOP: Klassen und Objekte/Instanzen Listen aus Objekten/Instanzen Prof. Dr. Ute Matecki 228
Beispiel zu Listen aus Objekten/Instanzen
main()-Klasse zur Objekterzeugung
1 import java.util.Scanner;
2 import java.util.ArrayList;
3
4 public class PersonMainListe1 {
5
6 public static void main(String[] args) {
7
8 // Wir wollen 3 Personen eintippen
9 int anzahl = 3;
10 // Scanner zum Eintippen der Personen-Namen
11 Scanner tastatur = new Scanner(System.in);

Einstieg in die OOP: Klassen und Objekte/Instanzen Listen aus Objekten/Instanzen Prof. Dr. Ute Matecki 229
Beispiel zu Listen aus Objekten/Instanzen
main()-Klasse zur Objekterzeugung
12 // Schritt 1: Erzeugung der Listen-Referenz
13 ArrayList<Person1> personen = new ArrayList<Person1>(); S

Einstieg in die OOP: Klassen und Objekte/Instanzen Listen aus Objekten/Instanzen Prof. Dr. Ute Matecki 230
Beispiel zu Listen aus Objekten/Instanzen
main()-Klasse zur Objekterzeugung
14 // Schleife fuer die Belegung der Liste
15 for (int i=0; i<anzahl; i++) {
16 System.out.print("Name der naechsten Person: ");
17 String name = tastatur.nextLine();
18
19 // Schritt 2: Erzeugung der Personen-Instanz
20 Person1 p = new Person1(name);
21
22 // Schritt 3: Einhaengen in die Liste
23 personen.add(p);
24 } // end for

Einstieg in die OOP: Klassen und Objekte/Instanzen Listen aus Objekten/Instanzen Prof. Dr. Ute Matecki 231
Beispiel zu Listen aus Objekten/Instanzen
Ausgabe mit Zählschleife for
main()-Klasse zur Objekterzeugung
25 // Testen der Liste: Ausgabe aller Personennamen
26 System.out.println("----- Wir haben eigegeben: -----");
27
28 // Schleife fuer die Ausgabe der Liste
29 for (int i=0; i < personen.size(); i++) {
30 Person1 p = personen.get(i);
31 String name = p.getName();
32 System.out.println(name);
33 } // end for
34 } // end method main()
35 } // end class

Einstieg in die OOP: Klassen und Objekte/Instanzen Listen aus Objekten/Instanzen Prof. Dr. Ute Matecki 232
Beispiel zu Listen aus Objekten/Instanzen
Alternative Ausgabe mit Iteratorschleife for
main()-Klasse zur Objekterzeugung
25 // Testen der Liste: Ausgabe aller Personennamen
26 System.out.println("----- Wir haben eigegeben: -----");
27
28 // foreach-Schleife
29 for (Person1 p : personen) {
30
31 String name = p.getName();
32 System.out.println(name);
33 } // end for
34 } // end method main()
35 } // end class
Es wird kein expliziter get()-Aufruf der Listenvariable personen mehr
benötigt!

