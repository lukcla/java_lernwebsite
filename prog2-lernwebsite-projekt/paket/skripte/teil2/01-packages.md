# Skript-Rohtext Teil 2: Programmieren im Großen – Packages (Pakete) (Skript S. 464–512)

Programmierung 2
Programmieren im Großen – Packages
(Pakete)

Programmieren im Großen – Packages (Pakete) Prof. Dr. Ute Matecki 464
Vorwort
Programmieren im Großen – Packages (Pakete)
Wozu Packages?
Zuordnung von Klassen zu Packages
Import von Klassen aus fremden Packages
Compilierung und Klassenpfad
Verwaltung des Klassenpfades unter Eclipse
Darstellung von Packages in der UML
Packages – Ein Komplettbeispiel
Einstieg Streams
Generische Klassen (Generics)

Programmieren im Großen – Packages (Pakete) Prof. Dr. Ute Matecki 465
Annotationen
Threads

Programmieren im Großen – Packages (Pakete) Wozu Packages? Prof. Dr. Ute Matecki 466
Programmieren im Großen – Packages (Pakete)
Packages – was ist das und wozu wird’s benötigt?
Packages ermöglichen eine Strukturierung eines Programmsystems
oberhalb der Klassen-Ebene.

Programmieren im Großen – Packages (Pakete) Wozu Packages? Prof. Dr. Ute Matecki 466
Programmieren im Großen – Packages (Pakete)
Packages – was ist das und wozu wird’s benötigt?
Packages ermöglichen eine Strukturierung eines Programmsystems
oberhalb der Klassen-Ebene.
Große, operationelle Programmsysteme enthalten o mehrere 100
Klassen – hier wird eine solche übergeordnete Struktrierung benötigt.

Programmieren im Großen – Packages (Pakete) Wozu Packages? Prof. Dr. Ute Matecki 466
Programmieren im Großen – Packages (Pakete)
Packages – was ist das und wozu wird’s benötigt?
Packages ermöglichen eine Strukturierung eines Programmsystems
oberhalb der Klassen-Ebene.
Große, operationelle Programmsysteme enthalten o mehrere 100
Klassen – hier wird eine solche übergeordnete Struktrierung benötigt.
Packages ordnen Gruppen von zusammengehörenden Klassen in
gemeinsame Unterverzeichnisse ein.

Programmieren im Großen – Packages (Pakete) Wozu Packages? Prof. Dr. Ute Matecki 467
Programmieren im Großen – Packages (Pakete)
Packages – was ist das und wozu wird’s benötigt?
In jeder Klasse, die zu einem Package gehört, ist diese Zugehörigkeit
vermerkt.

Programmieren im Großen – Packages (Pakete) Wozu Packages? Prof. Dr. Ute Matecki 467
Programmieren im Großen – Packages (Pakete)
Packages – was ist das und wozu wird’s benötigt?
In jeder Klasse, die zu einem Package gehört, ist diese Zugehörigkeit
vermerkt.
Eine Klasse, die zu einem Package gehört, wird auch als Member des
Packages bezeichnet.

Programmieren im Großen – Packages (Pakete) Zuordnung von Klassen zu
Packages Prof. Dr. Ute Matecki 468
Zuordnung von Klassen zu Packages
Package-Pfad bei einfachen Packages
wird über die package-Anweisung festgelegt.

Programmieren im Großen – Packages (Pakete) Zuordnung von Klassen zu
Packages Prof. Dr. Ute Matecki 468
Zuordnung von Klassen zu Packages
Package-Pfad bei einfachen Packages
wird über die package-Anweisung festgelegt.
Diese steht über dem Kopf der Klassendeklaration.

Programmieren im Großen – Packages (Pakete) Zuordnung von Klassen zu
Packages Prof. Dr. Ute Matecki 468
Zuordnung von Klassen zu Packages
Package-Pfad bei einfachen Packages
wird über die package-Anweisung festgelegt.
Diese steht über dem Kopf der Klassendeklaration.
Aus dem Namen des Packages wird von Java ein Unterordner erzeugt.
Die Compilate (.class-Datei) einer Klasse werden vom Compiler
automatisch in ihrem zugehörigen Package-Unterordner abgelegt.

Programmieren im Großen – Packages (Pakete) Zuordnung von Klassen zu
Packages Prof. Dr. Ute Matecki 469
Zuordnung von Klassen zu Packages
Package-Pfade bei einfachen Packages – Syntax
1 package mypackage;
2 public class NameClass {
3 // Inhalt der Klasse ...
4 }

Programmieren im Großen – Packages (Pakete) Zuordnung von Klassen zu
Packages Prof. Dr. Ute Matecki 469
Zuordnung von Klassen zu Packages
Package-Pfade bei einfachen Packages – Syntax
1 package mypackage;
2 public class NameClass {
3 // Inhalt der Klasse ...
4 }
Compilat NameClass.class landet im Verzeichnis ./mypackage

Programmieren im Großen – Packages (Pakete) Zuordnung von Klassen zu
Packages Prof. Dr. Ute Matecki 470
Zuordnung von Klassen zu Packages
Package-Pfade bei verschachtelten Packages
Falls eine Klasse einem untergeordneten Package (SubPackage)
zugeordnet wird, so werden die einzelnen Hierarchiestufen der
Package-Hierarchie durch Punkt . getrennt.

Programmieren im Großen – Packages (Pakete) Zuordnung von Klassen zu
Packages Prof. Dr. Ute Matecki 470
Zuordnung von Klassen zu Packages
Package-Pfade bei verschachtelten Packages
Falls eine Klasse einem untergeordneten Package (SubPackage)
zugeordnet wird, so werden die einzelnen Hierarchiestufen der
Package-Hierarchie durch Punkt . getrennt.
Aus jedem Package / SubPackage wird von Java einUnterordner erzeugt.

Programmieren im Großen – Packages (Pakete) Zuordnung von Klassen zu
Packages Prof. Dr. Ute Matecki 470
Zuordnung von Klassen zu Packages
Package-Pfade bei verschachtelten Packages
Falls eine Klasse einem untergeordneten Package (SubPackage)
zugeordnet wird, so werden die einzelnen Hierarchiestufen der
Package-Hierarchie durch Punkt . getrennt.
Aus jedem Package / SubPackage wird von Java einUnterordner erzeugt.
Die Compilate (.class-Datei) einer Klasse werden vom Compiler
automatisch in ihrem zugehörigen Package-Unterordner abgelegt.

Programmieren im Großen – Packages (Pakete) Zuordnung von Klassen zu
Packages Prof. Dr. Ute Matecki 470
Zuordnung von Klassen zu Packages
Package-Pfade bei verschachtelten Packages
Falls eine Klasse einem untergeordneten Package (SubPackage)
zugeordnet wird, so werden die einzelnen Hierarchiestufen der
Package-Hierarchie durch Punkt . getrennt.
Aus jedem Package / SubPackage wird von Java einUnterordner erzeugt.
Die Compilate (.class-Datei) einer Klasse werden vom Compiler
automatisch in ihrem zugehörigen Package-Unterordner abgelegt.
Der Punkt . wird hierbei zum jeweils plattformabhängigen
Verzeichnistrenner aufgelöst:
- Unter Linux wird er zu Slash: /
- Unter Windows wird er zu Backslash: \

Programmieren im Großen – Packages (Pakete) Zuordnung von Klassen zu
Packages Prof. Dr. Ute Matecki 471
Zuordnung von Klassen zu Packages
Package-Pfade bei verschachtelten Packages – Syntax
1 package mypackage.subpackage1..subpackageN;
2 public class NameClass {
3 // Inhalt der Klasse ...
4 }

Programmieren im Großen – Packages (Pakete) Zuordnung von Klassen zu
Packages Prof. Dr. Ute Matecki 471
Zuordnung von Klassen zu Packages
Package-Pfade bei verschachtelten Packages – Syntax
1 package mypackage.subpackage1..subpackageN;
2 public class NameClass {
3 // Inhalt der Klasse ...
4 }
Compilat NameClass.class landet in
./mypackage/subpackage1/../subpackageN/NameClass.class

Programmieren im Großen – Packages (Pakete) Import von Klassen aus
fremden Packages Prof. Dr. Ute Matecki 472
Import von Klassen aus fremden Packages
Import von einzelnen Klassen
1 package mypackage.subpackage1..subpackageN;
2 import java.io.BufferedReader;
3 public class NameClass {
4 // Inhalt der Klasse ...
5 }

Programmieren im Großen – Packages (Pakete) Import von Klassen aus
fremden Packages Prof. Dr. Ute Matecki 472
Import von Klassen aus fremden Packages
Import von einzelnen Klassen
1 package mypackage.subpackage1..subpackageN;
2 import java.io.BufferedReader;
3 public class NameClass {
4 // Inhalt der Klasse ...
5 }
Eine einzelne Klasse aus Package java.io wird eingebunden.

Programmieren im Großen – Packages (Pakete) Import von Klassen aus
fremden Packages Prof. Dr. Ute Matecki 473
Import von Klassen aus fremden Packages
Import von allen Klassen eines Packages
1 package mypackage.subpackage1..subpackageN;
2 import java.io.*;
3 public class NameClass {
4 // Inhalt der Klasse ...
5 }

Programmieren im Großen – Packages (Pakete) Import von Klassen aus
fremden Packages Prof. Dr. Ute Matecki 473
Import von Klassen aus fremden Packages
Import von allen Klassen eines Packages
1 package mypackage.subpackage1..subpackageN;
2 import java.io.*;
3 public class NameClass {
4 // Inhalt der Klasse ...
5 }
Alle Klassen aus Package java.io werden eingebunden.
Klassen aus Sub-Packages von java.io werden nicht eingebunden!

Programmieren im Großen – Packages (Pakete) Compilierung und Klassenpfad Prof. Dr. Ute Matecki 474
Compilierung und Klassenpfad
Compileraufruf bisher (Klasse ist keinem Package zugeordnet):
javac NameClass.java

Programmieren im Großen – Packages (Pakete) Compilierung und Klassenpfad Prof. Dr. Ute Matecki 474
Compilierung und Klassenpfad
Compileraufruf bisher (Klasse ist keinem Package zugeordnet):
javac NameClass.java
oder ...

Programmieren im Großen – Packages (Pakete) Compilierung und Klassenpfad Prof. Dr. Ute Matecki 474
Compilierung und Klassenpfad
Compileraufruf bisher (Klasse ist keinem Package zugeordnet):
javac NameClass.java
oder ...
javac *.java

Programmieren im Großen – Packages (Pakete) Compilierung und Klassenpfad Prof. Dr. Ute Matecki 474
Compilierung und Klassenpfad
Compileraufruf bisher (Klasse ist keinem Package zugeordnet):
javac NameClass.java
oder ...
javac *.java
:Compilate landen im gleichen Verzeichnis wie die Quelltexte.

Programmieren im Großen – Packages (Pakete) Compilierung und Klassenpfad Prof. Dr. Ute Matecki 475
Compilierung und Klassenpfad
Compileraufruf neu: Compilate werden in ein anderes Verzeichnis platziert
bin mypackage
Klasse1.class
Klasse2.class
Klasse3.class
src mypackage
Klasse1.java
Klasse2.java
Klasse3.java
Quelldateien
befinden sich
im src-Ordner
Compilate
befinden sich
im bin-Ordner

Programmieren im Großen – Packages (Pakete) Compilierung und Klassenpfad Prof. Dr. Ute Matecki 476
Compilierung und Klassenpfad
Compileraufruf neu: Compilate werden in ein anderes Verzeichnis platziert
Compiler-Option Erläuterung
-cp <pfad> gibt an, unter welchem Pfad importierte
Klassen zu finden sind.
Hier dürfen absolute und relative Pfade
angegeben werden.
Werden mehrere Pfade angegeben, so sind
diese
- unter Windows mit Semikolon ; bzw.
- unter Linux mit Doppelpunkt : zu trennen.

Programmieren im Großen – Packages (Pakete) Compilierung und Klassenpfad Prof. Dr. Ute Matecki 477
Compilierung und Klassenpfad
Compileraufruf neu: Compilate werden in ein anderes Verzeichnis platziert
Compiler-Option Erläuterung
-d <pfad> gibt an, in welchem Verzeichnis die zu
erzeugenden .class-Dateien landen sollen.
Die Teil-Ordner für die Packages werden
dabei automatisch angelegt, falls sie noch
nicht existieren.

Programmieren im Großen – Packages (Pakete) Compilierung und Klassenpfad Prof. Dr. Ute Matecki 478
Compilierung und Klassenpfad
Beispiel für einen Compileraufruf: Wir stehen im Elternverzeichnis von src
und bin:
javac -cp ".\bin" -d ".\bin" .\src\mypackage\Klasse1.java

Programmieren im Großen – Packages (Pakete) Compilierung und Klassenpfad Prof. Dr. Ute Matecki 478
Compilierung und Klassenpfad
Beispiel für einen Compileraufruf: Wir stehen im Elternverzeichnis von src
und bin:
javac -cp ".\bin" -d ".\bin" .\src\mypackage\Klasse1.java
Die Option ...
-cp sucht im Verzeichnis ./bin nach Klassen und Packages, die mit
import in der Klasse Klasse1 eingebunden sind.

Programmieren im Großen – Packages (Pakete) Compilierung und Klassenpfad Prof. Dr. Ute Matecki 478
Compilierung und Klassenpfad
Beispiel für einen Compileraufruf: Wir stehen im Elternverzeichnis von src
und bin:
javac -cp ".\bin" -d ".\bin" .\src\mypackage\Klasse1.java
Die Option ...
-cp sucht im Verzeichnis ./bin nach Klassen und Packages, die mit
import in der Klasse Klasse1 eingebunden sind.
-d steht für Destination. Hiermit ist das Zielverzeichnis gemeint, in dem
die Compilate (samt Package-Pfad) abgelegt werden.

Programmieren im Großen – Packages (Pakete) Verwaltung des Klassenpfades unter Eclipse Prof. Dr. Ute Matecki 479
Verwaltung des Klassenpfades unter Eclipse
Packages werden unter Eclipse im Projekt angelegt mit ...
File :New :Package

Programmieren im Großen – Packages (Pakete) Verwaltung des Klassenpfades unter Eclipse Prof. Dr. Ute Matecki 479
Verwaltung des Klassenpfades unter Eclipse
Packages werden unter Eclipse im Projekt angelegt mit ...
File :New :Package
Die betreenden Klassen werden dann entweder direkt im Package mit
File :New erzeugt. In diesem Fall erfolgt der package ..-Eintrag in der
ersten Zeile der Klassendatei automatisch durch die
Entwicklungsumgebung.

Programmieren im Großen – Packages (Pakete) Verwaltung des Klassenpfades unter Eclipse Prof. Dr. Ute Matecki 479
Verwaltung des Klassenpfades unter Eclipse
Packages werden unter Eclipse im Projekt angelegt mit ...
File :New :Package
Die betreenden Klassen werden dann entweder direkt im Package mit
File :New erzeugt. In diesem Fall erfolgt der package ..-Eintrag in der
ersten Zeile der Klassendatei automatisch durch die
Entwicklungsumgebung.
Oder: Die Klassen werden nachträglich per Drag’n Drop in den Package
verschoben. Hier fragt die Entwicklungsumgebung nach, ob man den
entsprechenden package ..-Eintrag in der ersten Zeile der
Klassendatei wünscht.

Programmieren im Großen – Packages (Pakete) Darstellung von Packages
in der UML Prof. Dr. Ute Matecki 480
Packages in der UML
Klassendiagramm mit verschachtelten Packages
shapeapp
shapeapp.io
Drawing
«Interface»
IShapeReader «Interface»
IShapeWriter
shapeapp.shapes
Shape
Point Circle
shapeapp.main
ShapesMain1
<<use>>
<<use>>

Programmieren im Großen – Packages (Pakete) Darstellung von Packages
in der UML Prof. Dr. Ute Matecki 481
Packages in der UML
Paketdiagramm mit verschachtelten Packages
io
shapes
main
shapeapp
Legende:
Enthält-Beziehung

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 482
Packages – Komplettbeispiel Shapes – Übersicht
shapes
Point
- x : int
- y : int
+ Point(identifier : String, x : int, y : int)
+ getX() : int
+ setX(x : int):void
+ getY() : int
+ setY(y : int):void
+ toString() : String
Shape
- identifier : String
+ Shape(identifier : String)
+ getIdentifier() : String
+ toString() : String
Circle
- x : int
- y : int
- radius : int
+ Circle(identifier : String, x : int, y : int, radius : int)
+ getX() : int
+ setX(x : int):void
+ getY() : int
+ setY(y : int):void
+ getRadius() : int
+ setRadius(radius : int):void
+ toString() : String

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 483
Packages – Komplettbeispiel Shapes – Übersicht
Hinweise zu dieser Klassenstruktur
Abstrakte Klasse Shape soll für geometrische Formen verschiedener
Dimension als Superklasse dienen.

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 483
Packages – Komplettbeispiel Shapes – Übersicht
Hinweise zu dieser Klassenstruktur
Abstrakte Klasse Shape soll für geometrische Formen verschiedener
Dimension als Superklasse dienen.
Daher werden für die (hier 2D-)Formen die x/y-Koordinate direkt in den
Klassen Point und Circle untergebracht.

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 483
Packages – Komplettbeispiel Shapes – Übersicht
Hinweise zu dieser Klassenstruktur
Abstrakte Klasse Shape soll für geometrische Formen verschiedener
Dimension als Superklasse dienen.
Daher werden für die (hier 2D-)Formen die x/y-Koordinate direkt in den
Klassen Point und Circle untergebracht.
Alternativen wären:
- Bei Festlegung auf 2D-Formen: x und y direkt in Shape unterbringen.
- Oder aber: eine verallgemeinerte Koordinatenklasse als direkte Subklasse von
Shape ...
- ... und diese dann für Point und Circle verwenden.

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 484
Package shapes
Abstrakte Klasse Shape – Teil 1
1 package shapes;
2 // Superklasse fuer geometrische Figuren
3 public abstract class Shape {
4
5 // Eine geometrische Form hat immer
6 // einen Bezeichner / Namen, zB. kreis1
7 private String identifier;
8
9 public Shape(String identifier) {
10 this.identifier = identifier;
11 } // end constructor

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 485
Package shapes
Abstrakte Klasse Shape – Teil 2
13 public String getIdentifier() {
14 return identifier;
15 } // end method
16
17 // Abstrakte Methode (ueberschreibt
18 // Methode aus Klasse Object)
19 @Override
20 public abstract String toString();
21 } // end class

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 486
Package shapes
Klasse Point – Teil 1
1 package shapes;
2
3 public class Point extends Shape {
4 private int x;
5 private int y;
6
7 public Point(String identifier, int x, int y) {
8 super (identifier); // identifier an Superklasse
9 this.x = x;
10 this.y = y;
11 } // end constructor

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 487
Package shapes
Klasse Point – Teil 2
12 // getter / setter
13 public int getX() { return x; }
14
15 public void setX(int x) { this.x = x; }
16
17 public int getY() { return y; }
18
19 public void setY(int y) { this.y = y; }

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 488
Package shapes
Klasse Point – Teil 3
20 @Override
21 public String toString() {
22 String result = "Point\n";
23 result += getIdentifier() + "\n"; // Aus Elternklasse
24 result += x + "\n";
25 result += y + "\n";
26 return result;
27 } // end method print()
28 } // end class
Überschriebene Methode toString()

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 489
Package shapes
Klasse Circle – Teil 1
1 package shapes;
2 public class Circle extends Shape {
3
4 private int x;
5 private int y;
6 private int radius;

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 490
Package shapes
Klasse Circle – Teil 2
8 public Circle(String identifier, int x, int y, int radius) {
9 super (identifier);
10 this.x = x;
11 this.y = y;
12 this.radius = radius;
13 } // end constructor

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 491
Package shapes
Klasse Circle – Teil 3
14 // getter / setter
15 public int getX() { return x; }
16
17 public void setX(int x) { this.x = x; }
18
19 public int getY() { return y; }
20
21 public void setY(int y) { this.y = y; }
22
23 public int getRadius() { return radius; }
24
25 public void setRadius(int radius) { this.radius = radius;}

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 492
Package shapes
Klasse Circle – Teil 4
26 @Override
27 public String toString() {
28 String result = "Circle\n";
29 result += getIdentifier() + "\n"; // Aus Elternklasse
30 result += x + "\n";
31 result += y + "\n";
32 result += radius + "\n";
33 return result;
34 } // end method print()
35 } // end class
Überschriebene Methode toString()

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 493
Packages – Komplettbeispiel Shapes – Übersicht
«interface»
IShapeReader
+ read(): void
«interface»
IShapeWriter
+ write():void
Drawing
- shapeList : ArrayList<Shape>
- fileName : String
+ Drawing(fileName : String)
+ getShapeList() : ArrayList<Shape>
+ write():void
+ read():void
io

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 494
Package io
Interface IShapeReader
1 package io;
2
3 public interface IShapeReader {
4
5 // Shape einlesen (zB von Tastatur oder Datei)
6 public void read();
7 }

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 495
Package io
Interface IShapeWriter
1 package io;
2
3 public interface IShapeWriter {
4 // Shape ausgeben (zB auf Konsole oder Datei)
5 public void write();
6 }

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 496
Package io
Klasse Drawing – Teil 1
1 package io;
2
3 // Standard-Packages
4 import java.io.*;
5 import java.util.ArrayList;
6 // Eigener Package
7 import shapes.*;
Die Klassen Shape,Point und Circle aus Package shapes werden importiert.

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 497
Package io
Klasse Drawing – Teil 2
8 public class Drawing implements IShapeReader,
9 IShapeWriter {
10
11 private ArrayList<Shape> shapeList;
12 private String fileName;

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 498
Package io
Klasse Drawing – Teil 3
13 public Drawing(String fileName) {
14 // Lege leere ArrayList fuer Shapes
15 // an. (Hier konkret: Point oder Circle)
16 this.shapeList = new ArrayList<Shape>();
17 this.fileName = fileName;
18 } // end constructor
19
20 public ArrayList<Shape> getShapeList(){
21 return this.shapeList;
22 } // end method

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 499
Package io
Klasse Drawing – Teil 4
23 @Override
24 public void write( ) {
25 try { ObjectOutputStream out = new ObjectOutputStream(
26 new FileOutputStream(fileName));
27 // Anzahl Listenobjekte auf Datei schreiben
28 out.writeInt(shapeList.size());
29
30 for (Shape s: shapeList) { // Objekte auf Datei schreiben
31 out.writeObject(s);
32 }
33 out.close(); // Stream schliessen
34 } // end try
Implementierte Methode write() aus Interface IShapeWriter

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 500
Package io
Klasse Drawing – Teil 5
35 catch (IOException e) {
36 e.printStackTrace();
37 } // end catch
38 } // end method write()
Implementierte Methode write() aus Interface IShapeWriter

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 501
Package io
Klasse Drawing – Teil 6
39 @Override
40 public void read() {
41 try {
42 ObjectInputStream in = new ObjectInputStream(
43 new FileInputStream(fileName));
44 // Anzahl Elemente einlesen
45 int anzahl = in.readInt();
Implementierte Methode read() aus Interface IShapeReader: Stream für
Datei önen

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 502
Package io
Klasse Drawing – Teil 7
46 // Schleife ueber gewuenschte Anzahl Elemente
47 for (int i=0; i<anzahl; i++) {
48 Shape s = (Shape) in.readObject(); // einlesen ..
49 shapeList.add(s); // .. und in Liste haengen
50 }
51 in.close(); // Stream schliessen
52 } // end try
Implementierte Methode read() aus Interface IShapeReader: Zeile auslesen –
Wenn Point: Point-Daten auslesen

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 503
Package io
Klasse Drawing – Teil 8
53 catch (IOException e) {
54 System.err.println("Stream-Fehler!");
55 e.printStackTrace();
56 }
57 catch (NumberFormatException e) {
58 System.err.println("Fehler Zahlenformat!");
59 e.printStackTrace();
60 } // end catch
61 catch (ClassNotFoundException e) {
62 e.printStackTrace(); // Kein passendes Objekt
63 }
64 } // // end method read()
65 } // end class
IltitMthdd() ItfIShRdWCil

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 504
Package io
Klasse Drawing – Anmerkung
Die ClassNotFoundException wird geworfen, wenn das Objekt, welches wir
einlesen wollen, kein Shape-Objekt ist, oder wenn der Package-Pfad beim
Erstellen der Objekte-Datei ein anderer war.

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 505
Packages – Komplettbeispiel Shapes – Übersicht
main
ShapesMain1
+ main(args : String[]): void

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 506
Package main
Klasse ShapesMain1 – Teil 1
1 package main;
2
3 import java.util.ArrayList;
4
5 import io.Drawing;
6 import shapes.Circle;
7 import shapes.Point;
8 import shapes.Shape;
9
10 public class ShapesMain1 {
Klasse ShapesMain1 mit Package-Zuordnung, allen Importen und Kopf der
main()-Methode

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 507
Package main
Klasse ShapesMain1 – Teil 2
11 Drawing d = new Drawing("shapes.txt");
12 // Noch leere Liste abfragen
13 ArrayList<Shape> liste = d.getShapeList();
14
15 // 2 Shapes zufuegen
16 Point p1 = new Point("p1",33,44);
17 Circle c1 = new Circle("c1",33,67,12);
18 liste.add(p1);
19 liste.add(c1);
20
21 // Liste auf Datei schreiben
22 d.write();

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 508
Package main
Klasse ShapesMain1 – Teil 2
main()-Methode befüllt die Liste eines Drawing- Objektes.

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 508
Package main
Klasse ShapesMain1 – Teil 2
main()-Methode befüllt die Liste eines Drawing- Objektes.
Drawing-Objekt schreibt mit seiner write()-Methode die Shape-Objekte
auf Datei.

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 509
Package main
Klasse ShapesMain1 – Teil 3
23 // Neues Drawing-Objekt anlegen
24 Drawing dNeu = new Drawing("shapes.txt");
25
26 // Datei einlesen
27 dNeu.read();
28 // Liste abfragen und auf Konsole ausgeben
29 ArrayList<Shape> listeNeu = dNeu.getShapeList();
30 for (Shape s : listeNeu) {
31 String str = s.toString();
32 System.out.println(str);
33 } // end for
34 } // end method main()
35 } // end class

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 510
Package main
Klasse ShapesMain1 – Teil 3
main()-Methode legt ein neues Drawing-Objekt an.

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 510
Package main
Klasse ShapesMain1 – Teil 3
main()-Methode legt ein neues Drawing-Objekt an.
Dieses liest mit seiner read()-Methode die Shape-Objekte aus einer
Textdatei ein.

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 510
Package main
Klasse ShapesMain1 – Teil 3
main()-Methode legt ein neues Drawing-Objekt an.
Dieses liest mit seiner read()-Methode die Shape-Objekte aus einer
Textdatei ein.
Diese werden anschließend auf die Konsole ausgegeben.

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 510
Package main
Klasse ShapesMain1 – Teil 3
main()-Methode legt ein neues Drawing-Objekt an.
Dieses liest mit seiner read()-Methode die Shape-Objekte aus einer
Textdatei ein.
Diese werden anschließend auf die Konsole ausgegeben.
Gefährlich an dieser Lösung:
- Das Kapselungsprinzip wird hier durchbrochen!
- Die Listen-Referenz kann von außen bearbeitet werden.
- Die Änderungen wirken sich dann auch auf das Innenleben von Drawing aus!

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 511
Zusammenfassung Packages
Wir merken uns zu Packages in Java:
Packages ermöglichen eine Strukturierung eines Programmsystems
oberhalb der Klassen-Ebene.

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 511
Zusammenfassung Packages
Wir merken uns zu Packages in Java:
Packages ermöglichen eine Strukturierung eines Programmsystems
oberhalb der Klassen-Ebene.
Packages ordnen Gruppen von zusammengehörenden Klassen in
gemeinsame Unterverzeichnisse ein.

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 511
Zusammenfassung Packages
Wir merken uns zu Packages in Java:
Packages ermöglichen eine Strukturierung eines Programmsystems
oberhalb der Klassen-Ebene.
Packages ordnen Gruppen von zusammengehörenden Klassen in
gemeinsame Unterverzeichnisse ein.
In jeder Klasse, die zu einem Package gehört, ist diese Zugehörigkeit
vermerkt.

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 511
Zusammenfassung Packages
Wir merken uns zu Packages in Java:
Packages ermöglichen eine Strukturierung eines Programmsystems
oberhalb der Klassen-Ebene.
Packages ordnen Gruppen von zusammengehörenden Klassen in
gemeinsame Unterverzeichnisse ein.
In jeder Klasse, die zu einem Package gehört, ist diese Zugehörigkeit
vermerkt.
Eine Klasse, die zu einem Package gehört, wird auch als Member des
Packages bezeichnet.

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 512
Zusammenfassung Packages
Wir merken uns zu Packages in Java:
In Java erfolgt die Zuordnung einer Klasses zu einem Package in der
ersten Zeile mit:
package pckname.subpck1...subpckN;

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 512
Zusammenfassung Packages
Wir merken uns zu Packages in Java:
In Java erfolgt die Zuordnung einer Klasses zu einem Package in der
ersten Zeile mit:
package pckname.subpck1...subpckN;
In Java erfolgt das Einbinden von einzelnen Klassen aus fremden
Packages mit:
import pck.subPck.KlassenName;

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 512
Zusammenfassung Packages
Wir merken uns zu Packages in Java:
In Java erfolgt die Zuordnung einer Klasses zu einem Package in der
ersten Zeile mit:
package pckname.subpck1...subpckN;
In Java erfolgt das Einbinden von einzelnen Klassen aus fremden
Packages mit:
import pck.subPck.KlassenName;
In Java erfolgt das Einbinden von allen Klassen aus fremden Packages
mit:
import pck.subPck.*;

Programmieren im Großen – Packages (Pakete) Packages – Ein Komplettbeispiel Prof. Dr. Ute Matecki 512
Zusammenfassung Packages
Wir merken uns zu Packages in Java:
In Java erfolgt die Zuordnung einer Klasses zu einem Package in der
ersten Zeile mit:
package pckname.subpck1...subpckN;
In Java erfolgt das Einbinden von einzelnen Klassen aus fremden
Packages mit:
import pck.subPck.KlassenName;
In Java erfolgt das Einbinden von allen Klassen aus fremden Packages
mit:
import pck.subPck.*;
Achtung: Der Import bindet die Compilate – also die .class-Dateien ein –
nicht die Quelldateien!

2
• © Prof. Dr. Ute Matecki
Fakultät Informatik
