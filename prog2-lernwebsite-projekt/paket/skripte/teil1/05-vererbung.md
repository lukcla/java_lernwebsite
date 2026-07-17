# Skript-Rohtext: Vererbungsbeziehungen (Skript S. 282–408)

2
• © Prof. Dr. Ute Matecki
Fakultät Informatik
Programmierung 2
Vererbungsbeziehungen

Vererbungsbeziehungen Prof. Dr. Ute Matecki 282
Vorwort
Einstieg in Java
Einstieg in die OOP: Klassen und Objekte/Instanzen
Die Klasse String
Graphische Darstellung von Klassen mit der UML – Teil 1
Vererbungsbeziehungen
Wozu Vererbung?
Einfache Vererbungsbeziehungen in Java
Grundzüge Vererbung

Vererbungsbeziehungen Prof. Dr. Ute Matecki 283
Vererbungsprinzip in Java – Eltern- und Kindklassen
Einfachvererbung – Mehrfachvererbung in Java
Vererbungsprinzip in Java – Objekterzeugung
Polymorphie – Vielgestaltigkeit von Objekten
DIE Superklasse aller Java-Klassen: Die Klasse Object
Überladen vs. Überschreiben in der OOP
Abstrakte Klassen
Wozu abstrakte Klassen?
Darstellung abstrakter Klassen
Einschub: Annotation @Override
Interfaces
Grundlagen Interfaces
Einfache Vererbungsbeziehungen mit Interfaces
Default-Implementierung von Interface-Methoden
Mehrstufige Vererbungshierarchien
Auswirkungen von Interfaces auf Polymorphie
Der instanceof-Operator
Exceptions

Vererbungsbeziehungen Prof. Dr. Ute Matecki 284
Einstieg Streams

Vererbungsbeziehungen Wozu Vererbung? Prof. Dr. Ute Matecki 285
Bisher bekannte OOP-Konzepte
Sie kennen bereits ...
Klassen mit Attributen und Methoden
Zugrisschutz-Modifizierer
Modifizierer static
Assoziative Klassenbeziehungen – können hat-Beziehungen
modellieren.

Vererbungsbeziehungen Wozu Vererbung? Prof. Dr. Ute Matecki 286
Bisher bekannte OOP-Konzepte
Was tun in folgendem Fall? – UML-Sicht
Lehrende
-vorname: String
-nachname: String
-persnr: int
-jahresgehalt: double
+Lehrende(vorname: String, nachname: String, persnr: int, jahresgehalt: double)
+getNachname(): String
+setNachname(nachname: String): void
+getVorname(): String
+getPersnr(): int
+getJahresgehalt(): double
Person
-vorname: String
-nachname: String
+Person(vorname: String, nachname: String)
+getNachname(): String
+setNachname(nachname: String): void
+getVorname(): String
Studierende
-vorname: String
-nachname: String
-matrikelnr: int
+Studierende(vorname: String, nachname: String, matrikelnr: int)
+getNachname(): String
+setNachname(nachname: String): void
+getVorname(): String
+getMatrikelnr(): int
Die Attribute
 - vorname
 - nachname
müssen in jeder Klasse neu implementiert werden!
Ebenso die getter() bzw. setter()

Vererbungsbeziehungen Wozu Vererbung? Prof. Dr. Ute Matecki 287
Bisher bekannte OOP-Konzepte
Was tun in folgendem Fall? – Java-Sicht – Klasse Person
1 public class Person {
2 private String vorname;
3 private String nachname;
4 public Person(String vorname, String nachname) {
5 this.vorname = vorname;
6 this.nachname = nachname;
8 } // end constructor

Vererbungsbeziehungen Wozu Vererbung? Prof. Dr. Ute Matecki 288
Bisher bekannte OOP-Konzepte
Was tun in folgendem Fall? – Java-Sicht – Klasse Person
9 public String getNachname() {
10 return nachname;
11 } // end method
12
13 public void setNachname(String nachname) {
14 this.nachname = nachname;
15 } // end method
16
17 public String getVorname() {
18 return vorname;
19 } // end method
20 } // end class

Vererbungsbeziehungen Wozu Vererbung? Prof. Dr. Ute Matecki 289
Bisher bekannte OOP-Konzepte
Was tun in folgendem Fall? – Java-Sicht – Klasse Studierende
1 public class Studierende {
2 private String vorname;
3 private String nachname;
4 private int matrikelnr; Wiederholt sich!
5
6 public Studierende(String vorname,
7 String nachname, int matrikelnr) {
8 this.vorname = vorname;
9 this.nachname = nachname;
10 this.matrikelnr = matrikelnr;
11 } // end constructor

Vererbungsbeziehungen Wozu Vererbung? Prof. Dr. Ute Matecki 290
Bisher bekannte OOP-Konzepte
Was tun in folgendem Fall? – Java-Sicht – Klasse Studierende
12 public String getNachname() {
13 return nachname;
14 } // end method
15
16 public void setNachname(String nachname) {
17 this.nachname = nachname;
18 } // end method
19
20 public String getVorname() {
21 return vorname;
22 } // end method
Wiederholt sich!

Vererbungsbeziehungen Wozu Vererbung? Prof. Dr. Ute Matecki 291
Bisher bekannte OOP-Konzepte
Was tun in folgendem Fall? – Java-Sicht – Klasse Studierende
23 public int getMatrikelnr() {
24 return matrikelnr;
25 } // end method
26 } // end class

Vererbungsbeziehungen Wozu Vererbung? Prof. Dr. Ute Matecki 292
Bisher bekannte OOP-Konzepte
Was tun in folgendem Fall? – Java-Sicht – Objekterzeugung Person und
Studierende
1 public class PersonenMain1 {
2 public static void main(String[] args) {
3 // Eine Person mit
4 // Vorname Hugo, Nachname Helmchen
5 Person p1 = new Person("Hugo","Helmchen");
6
7 // Eine Studierende mit
8 // Vorname Erna, Nachname Etepetete
9 // Matrikelnr. 4711
10 Studierende s1 = new Studierende("Erna","Etepetete",4711);

Vererbungsbeziehungen Wozu Vererbung? Prof. Dr. Ute Matecki 293
Bisher bekannte OOP-Konzepte
Was tun in folgendem Fall? – Java-Sicht – Objekterzeugung Person und
Studierende
11 // Aufruf getter()-Implementierung von Person
12 String nachname1 = p1.getNachname();
13
14 // Aufruf getter-Implementierung von Studierende
15 String nachname2 = s1.getNachname();
16 } // end method main
17 } // end class

Vererbungsbeziehungen Wozu Vererbung? Prof. Dr. Ute Matecki 294
Bisher bekannte OOP-Konzepte
Mit den bisherigen Konzepten können wir nicht ...
ist-Beziehungen modellieren.
Beispiel: Ein/e Studierende/r ist eine Person mit zusätzlichen Attributen
Ebenso ein/e Lehrende/r
Eigentlich gemeinsame Eigenschaen werden in jeder Klasse
neu implementiert!

Vererbungsbeziehungen Wozu Vererbung? Prof. Dr. Ute Matecki 295
Bisher bekannte OOP-Konzepte
Das gezeigte Klassensystem widerspricht dem DRY-Prinzip
DRY } Don’t Repeat Yourself!
:Code-Anteile sollten nur einmal implementiert werden!
:Wiederholungen sind fehleranfällig!

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 296
Neuer Ansatz: Vererbungsprinzip
Mit dem Vererbungsprinzip können wir ...
Gemeinsame Eigenschaen (z.B. Vorname und Nachname) werden in
einer Superklasse implementieren.
- Synonym: Elternklasse,
- Basisklasse
- Oder, da Klassen eben auch Datentypen sind: Supertyp
Unterscheidende Eigenschaen (z. B. Matrikelnummer oder
Jahresgehalt) werden in Subklassen implementieren.
- Synonym: Kindklasse,
- abgeleitete Klasse
- Oder, da Klassen eben auch Datentypen sind: Subtyp

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 297
Vererbungsprinzip – Klassenstruktur
Klassensystem mit Vererbungsbeziehung – UML-Sicht
Studierende
-matrikelnr: int
+Studierende(vorname: String, nachname: String, matrikelnr: int)
+getMatrikelnr(): int
Lehrende
-jahresGehalt: double
+Lehrende(vorname: String, nachname: String, jahresGehalt: double)
+getJahresGehalt(): double
Person
-vorname: String
-nachname: String
+Person(vorname: String, nachname: String)
+getNachname(): String
+setNachname(nachname: String): void
+getVorname(): String
Pfeilspitze mit offenem Dreieck:
Vererbungsbeziehung
Hier: Studierende und Lehrende
erben Attribute und Methoden
von Klasse Person

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 298
Vererbungsprinzip – Klassenstruktur
Klassensystem mit Vererbungsbeziehung – UML-Sicht
Die Beziehung Klasse B erbt von Klasse A wird in der UML ausgedrückt
durch:
B A
Jede Klasse enthält nur noch die Inhalte, für die sie wirklich zuständig
ist!

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 299
Vererbungsprinzip – Klassenstruktur
Klassensystem mit Vererbungsbeziehung – Java-Sicht – Klasse Person
1 public class Person {
2
3 private String vorname; // Attribute sind
4 private String nachname; // unveraendert
5
6 public Person(String vorname, String nachname) {
7
8 this.vorname = vorname;
9 this.nachname = nachname;
10 } // end constructor

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 300
Vererbungsprinzip – Klassenstruktur
Klassensystem mit Vererbungsbeziehung – Java-Sicht – Klasse Person
11 public String getNachname() {
12 return nachname;
13 } // end method
14
15 public void setNachname(String nachname) {
16 this.nachname = nachname;
17 } // end method
18
19 public String getVorname() {
20 return vorname;
21 } // end method
22 } // end class

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 301
Vererbungsprinzip – Klassenstruktur
Java-Sicht – Klasse Studierende – Attribute
1 public class Studierende extends Person {
2 // nur Attribute, die NICHT SCHON in der Superklasse
3 // stehen, werden hier noch implementiert.
4 private int matrikelnr;
Klasse Studierende erbt von Klasse Person.
Anders ausgedrückt: Klasse Studierende erweitert Klasse Person um
bestimmte Eigenschaen!
Die Vererbungsbeziehung erbt von wird in Java mit dem Schlüsselwort
extends ausgedrückt.

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 302
Vererbungsprinzip – Klassenstruktur
Java-Sicht – Klasse Studierende – Konstruktor
5 public Studierende(String vorname,
6 String nachname, int matrikelnr) {
7 // Aufruf des Superklassenkonstruktors -- er setzt
8 // Vorname und Nachname in der Elternklasse
9 super (vorname, nachname);
10
11 // Setzen der Matrikelnr. im eigenen Konstruktor
12 this.matrikelnr = matrikelnr;
13 } // end constructor
Konstruktor von Klasse Studierende muss benötigte Parameter an den
Konstruktor von Klasse Person weitergeben.
Dies geschieht durch den super()-Aufruf an erster Stelle im Rumpf des
Konstruktors von Klasse Studierende.

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 303
Vererbungsprinzip – Klassenstruktur
Java-Sicht – Klasse Studierende – Konstruktor – Das geht NICHT:
5 public Studierende(String vorname,
6 String nachname, int matrikelnr) {
7 // Setzen der ererbten Attribute
8 this.vorname = vorname;
9 this.nachname = nachname;
10 this.matrikelnr = matrikelnr; // Setzen der Matrikelnr.
11 } // end constructor
Die Attribute vorname und nachname sind private!
Kind-Klassen können auf ererbte, private Attribute nicht direkt
zugreifen!
Dies ist nur über den Superklassen-Konstruktor möglich!

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 304
Vererbungsprinzip – Klassenstruktur
Java-Sicht – Klasse Studierende – Konstruktor – Auch das geht NICHT:
5 public Studierende(String vorname,
6 String nachname, int matrikelnr) {
7
8 this.matrikelnr = matrikelnr; // Setzen der Matrikelnr.
9 super (vorname,nachname); // Aufruf Superklassenkonstr.
10
11 } // end constructor
Der Superklassen-Konstruktor muss immer zuerst aufgerufen werden!
Erst danach können weitere Statements abgesetzt werden!

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 305
Vererbungsprinzip – Klassenstruktur
Java-Sicht – Klasse Studierende – getter/setter:
14 // Nur noch getter fuer die eigenen Attribute --
15 // getter und setter der ererbten Attribute sind
16 // in der Superklasse implementiert!
17 public int getMatrikelnr() {
18 return matrikelnr;
19 } // end method
20 } // end class
Die Klasse Studierende enthält nur noch getter/setter für die eigenen
Attribute.
Sie erbt die getter/setter für die ererbten Attribute.

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 306
Vererbungsprinzip – Mehrfachvererbung
Mehrfachvererbung – Darstellung in der UML
Computer Phone
Smartphone
Mehrfachvererbung: Eine Kindklasse hat mehrere Elternklassen
Dieses Prinzip ist in der OOP zwar bekannt, aber ...
Mehrfachvererbung wird von Java nicht unterstützt! (Von C++: ja!)
:Java-Klassen können nur eine Eltern-Klasse haben!

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 307
Vererbungsprinzip – Objekterzeugung
Java-Sicht – Objekterzeugung mit Vererbungsprinzip – einfachster Fall
1 // Objekterzeugung
2 Person p1 = new Person("Hugo","Helmchen");
3 Studierende s1 = new Studierende("Erna","Etepetete",4711);
4
5 // Aufruf der eigenen Methode getNachname()
6 String nachname1 = p1.getNachname();
7
8 // Aufruf der ererbten Methode getNachname()
9 String nachname2 = s1.getNachname();
Von s1 wird die ererbte Methode getNachname() aufgerufen.
Sie verhält sich so, als ob zu Klasse Studierende gehört!

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 308
Vererbungsprinzip – Polymorphie
Java-Sicht – Objekterzeugung mit Vererbungsprinzip – Polymorphie
1 // Objekterzeugung
2 Person s1 = new Studierende("Erna","Etepetete",4711);
3
4 // Aufruf der ererbten Methode getNachname()
5 String nachname1 = s1.getNachname();
Von s1 kann als Person deklariert werden ...
... und als Studierende erzeugt werden.
Eine Instanz vom Typ Studierende ist eine Person!

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 309
Vererbungsprinzip – Polymorphie
Java-Sicht – Objekterzeugung mit Vererbungsprinzip – Polymorphie – das
geht NICHT:
1 // Objekterzeugung
2 Person s1 = new Studierende("Erna","Etepetete",4711);
3
4 // Aufruf der ererbten Methode getNachname() -- OK
5 String nachname = s1.getNachname();
6
7 // Aufruf einer Methode der Klasse Studierende -- NICHT OK
8 int matnr = s1.getMatrikelnr();
Instanz s1 ist vom Typ Person ...
... Person kennt keine Methode getMatrikelnr()!

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 310
Vererbungsprinzip – Polymorphie
Java-Sicht – Objekterzeugung mit Vererbungsprinzip – Polymorphie – das
geht:
1 // Objekterzeugung
2 Person s1 = new Studierende("Erna","Etepetete",4711);
3
4 // Aufruf der ererbten Methode getNachname() -- OK
5 String nachname = s1.getNachname();
6
7 // Aufruf einer Methode der Klasse Studierende
8 // mit TypeCast -- Klammerung,weil Punkt vor Cast (Prio)
9 int matnr = ( (Studierende) s1).getMatrikelnr();
Methode aus Klasse Studierende ist nach TypeCast wieder sichtbar ...
... und kann verwendet werden – sie wurde ja beim new-Aufruf erzeugt!

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 311
Vererbungsprinzip – Polymorphie
Java-Sicht – Objekterzeugung mit Vererbungsprinzip – Polymorphie –
Zusammenfassung
Objekte von Kindklassen können an eine Referenz vom Typ Elternklasse
zugewiesen werden:
Elternklasse var = new Kindklasse();
In diesem Fall sind die Methoden der Kindklasse nicht sichtbar.
Sie können beim Aufruf wieder sichtbar gemacht werden mit:
((Kindklasse)var).kindMethode();
Achtung: Der Punkt . hat Priorität vor dem Cast (Kindklasse). Damit
zuerst gecastet wird und dann erst mit . auf die Methode zugegrien
wird, muss der Cast geklammert werden!

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 312
DIE Superklasse aller Java-Klassen: Die Klasse Object
Wenn eine Java-Klasse scheinbar keine Superklasse hat ...
1 public class Person {
2 // Attribute ...
3 // Konstruktoren ...
4 // Methoden ...
5 }
... so erbt sie von der API-Klasse Object.
Diese enthält für jedes Objekt dieser Klasse Metainformationen wie
Klassenname, usw., die zur Laufzeit abgefragt werden können.
Sie enthält auch interessante Methoden z.B. zum Vergleich von
Objektinhalten.

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 313
DIE Superklasse aller Java-Klassen: Die Klasse Object
Bisher bekannte Vererbungshierarchie
Person
Studierende Lehrende
Aus dieser Konstruktion wird also ...

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 314
DIE Superklasse aller Java-Klassen: Die Klasse Object
Vererbungshierarchie mit Betrachtung der Klasse Object
Object
+equals(obj: Object)
+getClass(): Class
+toString(): String
+... weitere Methoden()
Person
Studierende Lehrende ... in Wirklichkeit diese!

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 315
DIE Superklasse aller Java-Klassen: Die Klasse Object
Szenario zum Testen von Klasse Object: Klasse Person
1 public class Person {
2 private String vorname;
3 private String nachname;
4
5 public Person(String vorname, String nachname) {
6 this.vorname = vorname;
7 this.nachname = nachname;
8 } // end constructor
9 // Rest wie vorher ...
10 } // end class

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 316
DIE Superklasse aller Java-Klassen: Die Klasse Object
Szenario zum Testen von Klasse Object: Klasse Studierende
1 public class Studierende extends Person{
2
3 private int matrikelnr;
4
5 public Studierende(String vorname,
6 String nachname, int matrikelnr) {
7 // Aufruf Superklassenkonstruktor
8 super (vorname,nachname);
9 this.matrikelnr = matrikelnr;
10 } // end constructor
11 // Rest wie vorher ...
12 } // end class

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 317
DIE Superklasse aller Java-Klassen: Die Klasse Object
Szenario zum Testen von Klasse Object: Klasse Lehrende
1 public class Lehrende extends Person{
2 private int persnr;
3 private double jahresgehalt;
4
5 public Lehrende(String vorname, String nachname,
6 int persnr, double jahresgehalt) {
7 // Aufruf Superklassenkonstruktor
8 super (vorname,nachname);
9 this.persnr = persnr;
10 this.jahresgehalt = jahresgehalt;
11 } // end constructor
12 // Rest wie vorher ...
13 } // end class

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 318
DIE Superklasse aller Java-Klassen: Die Klasse Object
Szenario zum Testen von Klasse Object: Klasse TesteObjectMain
1 import java.util.Scanner;
2
3 public class TesteObjectMain {
4
5 public static void main(String[] args) {
6
7 Person pers=null ;
8 Scanner s = new Scanner(System.in);
9
10 System.out.println("Was wollen Sie erzeugen?");
11 System.out.println("Person, Studierende oder Lehrende?");
12 String clazzname = s.next();

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 319
DIE Superklasse aller Java-Klassen: Die Klasse Object
Szenario zum Testen von Klasse Object: Klasse TesteObjectMain
13 switch(clazzname) {
14 case "Person": pers =
15 new Person("Hans","Koch"); break;
16 case "Studierende":
17 pers = new Studierende("Hans","Koch",4711);
18 break;
19 case "Lehrende":
20 pers = new Lehrende("Hans","Koch", 5678, 35000.0);
21 break;
22 } // end switch

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 320
DIE Superklasse aller Java-Klassen: Die Klasse Object
Szenario zum Testen von Klasse Object: Klasse TesteObjectMain
21 String clazzchosen = pers.getClass().getName();
22 System.out.println(
23 "Sie haben gewaehlt: " + clazzchosen);
24 } // end method main()
25 } // end class
:Über von Object ererbte Methode getClass() fragen wir den
Klassennamen ab!

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 321
Überladen und Überschreiben in der OOP
Überladen von Methoden – UML-Sicht
Person
- vorname: String
- nachname: String
+ Person( vorname: String, nachname: String)
+ getNachname():String
+ setNachname( nachname: String)
+ getVorname():String
Studierende
- matrikelnr: int
+ Studierende( vorname: String, nachname: String, matrikelnr: int)
+ getMatrikelnr():int
+ print()
 + print(gruss: String)
+ print()
 + print(gruss: String)
Die print()-Methode wurde in
der Klasse Person 2x überladen
Die print()-Methode wurde in
der Klasse Studierende ebenfalls 2x überladen
Die Methoden der Superklasse Person
wurden dabei überschrieben.

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 322
Überladen und Überschreiben in der OOP
Überladen von Methoden – Grundlagen
Überladen von Methoden innerhalb einer Klasse bedeutet: Wir stellen
mehrere Varianten einer Methode zur Verfügung.
Die Varianten heissen gleich, haben aber unterschiedliche Signaturen.
:Die Parameterlisten müssen sich unterscheiden!
Vorteil des Überladens von Methoden: Methoden die gleiche Dinge tun,
aber unterschiedliche Parameter benötigen, können gleich heißen.
Wichtig: Auch Konstruktoren können mehrfach überladen werden!

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 323
Überladen und Überschreiben in der OOP
Java-Sicht – Überladen von Methoden – Klasse Person
1 public class Person {
2
3 private String vorname;
4 private String nachname;
5
6 public Person(String vorname, String nachname) {
7 this.vorname = vorname;
8 this.nachname = nachname;
9 } // end constructor

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 324
Überladen und Überschreiben in der OOP
Java-Sicht – Überladen von Methoden – Klasse Person
10 public String getNachname() {
11 return nachname;
12 } // end method
13
14 public void setNachname(String nachname) {
15 this.nachname = nachname;
16 } // end method
17
18 public String getVorname() {
19 return vorname;
20 } // end method

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 325
Überladen und Überschreiben in der OOP
Java-Sicht – Überladen von Methoden – Klasse Person
21 public void print() {
22 System.out.println("Ich heisse "
23 + vorname + " " + nachname);
24 } // end method
25
26 public void print(String gruss) {
27 System.out.println(gruss + ", ich heisse "
28 + vorname + " " + nachname);
29 } // end method
31 } // end class
:2 überladene Versionen von print(...)

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 326
Überladen und Überschreiben in der OOP
Überladen von Methoden – Zusammenfassung
Eine Methode / einen
Konstruktor mehrfach
überladen =
Mehrere Versionen der
Methode/des Konstruktors
mit unterschiedlichen
Parameterlisten innerhalb
einer Klasse bereitstellen.

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 327
Überladen und Überschreiben in der OOP
Überschreiben von Methoden – UML-Sicht
Studierende
-vorname: String
-nachname: String
-matrikelnr: int
+Studierende(vorname: String, nachname: String, matrikelnr: int)
+getMatrikelnr(): int
+print(): void
+print(gruss: String): void
Person
-vorname: String
-nachname: String
+Person(vorname: String, nachname: String)
+getNachname(): String
+setNachname(nachname: String): void
+getVorname(): String
+print(): void
+print(gruss: String): void
Die print()-Methode wurde in 
Klasse Person 2 x überladen
Die print()-Methode wurde in Klasse Studierende ebenfalls 
2 x überladen
Die print()-Methoden aus Klasse Person werden überschrieben!
}
}

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 328
Überladen und Überschreiben in der OOP
Überschreiben von Methoden – Grundlagen
Überschreiben von Methoden innerhalb einer Kindklasse bedeutet: Wir
implementieren Methoden neu, die bereits mit gleicher Signatur in der
Elternklasse existieren.
Beim Aufruf
objKindklasse.methode();
wird so die Neuimplementierung aus der Kindklasse aufgerufen.
:Die Implementierung aus der Elternklasse wird überlagert bzw.
überschrieben!

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 329
Überladen und Überschreiben in der OOP
Java-Sicht – Überschreiben von Methoden – Klasse Studierende
1 public class Studierende extends Person {
2
3 private int matrikelnr;
4
5 // voll qualifizierter Konstruktor
6 public Studierende(String vorname,
7 String nachname, int matrikelnr) {
8 // Aufruf Superklassen-Konstruktor
9 super (vorname,nachname);
10 this.matrikelnr = matrikelnr;
11 } // end constructor

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 330
Überladen und Überschreiben in der OOP
Java-Sicht – Überschreiben von Methoden – Klasse Studierende
12 // getter fuer Matrikelnr.
13 public int getMatrikelnr() {
14 return matrikelnr;
15 } // end method

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 331
Überladen und Überschreiben in der OOP
Java-Sicht – Überschreiben von Methoden – Klasse Studierende
16 public void print() {
17 // Aufruf print-Methode aus Superklasse Person
18 super .print();
19 // eigener printout
20 System.out.println("Meine Matrnr: "+matrikelnr);
21 } // end method
print() überschreibt die parameterlose Version aus Superklasse
Person.
Über die super-Referenz rufen wir zuerst die print()-Methode der
Superklasse auf.

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 332
Überladen und Überschreiben in der OOP
Alternative zur print()-Methode auf der vorigen Seite
Java-Sicht – Überschreiben von Methoden – Klasse Studierende
16 public void print() {
17 // Kann aber auch vollstaendig mit eigenen printouts
18 // geloest werden:
19 System.out.println("Ich heisse: " +this.getVorname()
20 + " " + this.getNachname());
21 System.out.println("Meine Matrnr: "+matrikelnr);
22 } // end method
Auch hier: print() überschreibt die parameterlose Version aus
Superklasse Person.
Aber: ohne Zugri auf print() der Superklasse!

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 333
Überladen und Überschreiben in der OOP
Java-Sicht – Überschreiben von Methoden – Klasse Studierende
22 public void print(String gruss) {
23 // Aufruf print-Methode aus Superklasse Person
24 super .print(gruss);
25
26 // eigener printout
27 System.out.println("Meine Matrnr lautet: "+matrikelnr);
28 } // end method
29 } // end class
print(...) überschreibt die Version mit String-Parameter aus
Superklasse Person.
Über die super-Referenz rufen wir zuerst die print(...)-Methode der
Superklasse auf.

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 334
Überladen und Überschreiben in der OOP
Java-Sicht – Überschreiben von Methoden – Wirkungsweise bei Objekten
1 Person p1 = new Person("Hugo","Helmchen");
2 p1.print("Moin");
:Aufruf der Methode aus der Elternklasse

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 335
Überladen und Überschreiben in der OOP
Java-Sicht – Überschreiben von Methoden – Wirkungsweise bei Objekten
1 Studierende s1 = new Studierende("Hugo","Meier",4711);
2 s1.print("Servus");
:Aufruf der Methode aus der Kindklasse

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 336
Überladen und Überschreiben in der OOP
Java-Sicht – Überschreiben von Methoden – Wirkungsweise bei Objekten
1 Person s2 = new Studierende("Erna","Eckert",4712);
2 s2.print("Servus");
:Auch hier: Aufruf der Methode aus der Kindklasse

Vererbungsbeziehungen Einfache Vererbungsbeziehungen in Java Prof. Dr. Ute Matecki 337
Überladen und Überschreiben in der OOP
Überschreiben von Methoden – Zusammenfassung
Kindklassen können Methoden aus der Elternklasse überschreiben:
Dies geschieht durch Neuimplementierung von Methoden der Elternklasse
in der Kindklasse.

Vererbungsbeziehungen Abstrakte Klassen Prof. Dr. Ute Matecki 338
Abstrakte Klassen
Abstrakte Klassen – was ist das und wozu wird’s benötigt?
Es gibt Sowarearchitekturen, in denen man „erzwingen“ will, dass von
der obersten Superklasse kein Objekt erzeugt werden kann, sondern nur
von einer Kindklasse.
Es gibt Sowarearchitekturen, in denen man „erzwingen“ will, dass in
den Kindklassen bestimmte Methoden auf jeden Fall implementiert
werden.
Wenn „wichtige“ Methoden in einem Sowareentwurf „vergessen“
werden, so wird die Soware später fehlerha laufen.
Diese Methoden werden in der Superklasse nur als Methodenkopf
deklariert, nicht aber implementiert :abstrakte Methoden!

Vererbungsbeziehungen Abstrakte Klassen Prof. Dr. Ute Matecki 339
Abstrakte Klassen
Abstrakte Klassen – was ist das und wozu wird’s benötigt?
Abstrakte Klassen werden am Klassenkopf mit dem Schlüsselwort
abstract gekennzeichnet.
Abstrakte Klassen können abstrakte Methoden enthalten (müssen aber
nicht!)
Von abstrakten Klassen können keine Objekte gebildet werden.

Vererbungsbeziehungen Abstrakte Klassen Prof. Dr. Ute Matecki 340
Abstrakte Klassen – Darstellung in der UML
Darstellungsmöglichkeit 1
BuchungsService
-anbieter: String
+BuchungsService(anbieter: String)
+getAnbieter(): String
+preis(): double
+rechnung(): String
Klassenname kursiv:
Abstrakte Klasse
Methodenname kursiv:
Abstrakte Methode
Die UML kennt zwei Darstellungsmöglichkeiten für abstrakte Klassen.
Entweder werden Klassenname und abstrakte Methoden kursiv
geschrieben, ...

Vererbungsbeziehungen Abstrakte Klassen Prof. Dr. Ute Matecki 341
Abstrakte Klassen – Darstellung in der UML
Darstellungsmöglichkeit 2
BuchungsService
-anbieter: String
+BuchungsService(anbieter: String)
+getAnbieter(): String
+preis(): double {abstract}
+rechnung(): String {abstract}
Zusicherung {abstract}
unter dem Klassennamen:
Abstrakte Klasse
{abstract}
Zusicherung {abstract}
hinter der Methodendeklaration:
Abstrakte Methode
... oder die Zusicherung {abstract} wird unter den Klassennamen und
neben die Methodenköpfe geschrieben.

Vererbungsbeziehungen Abstrakte Klassen Prof. Dr. Ute Matecki 342
Abstrakte Klassen – Darstellung in Java
Abstrakte Klassen in Java – Syntax
1 [weitere Modifizierer] abstract class Klassenname {
2 [Attribute]
3 [Konstruktoren]
4 [Methoden]
5 [Modifizierer] abstract returnTyp methodenname() ;
6 }
Schlüsselwort abstract vor dem Schlüsselwort class.
Schlüsselwort abstract vor dem Methodenkopf.
Semikolon ; hinter dem Methodenkopf.
Kein Methodenrumpf, da abstrakte Methoden erst in den abgeleiteten
Klassen implementiert werden.

Vererbungsbeziehungen Abstrakte Klassen Prof. Dr. Ute Matecki 343
Abstrakte Klassen – Anwendungsbeispiel
Buchungs-Service mit abstrakter Superklasse – Beschreibung
Der Service muss bezahlt werden – es muss ein Preis berechnet werden
:Methode preis().
Es soll eine Rechnung für den Service erstellt werden können –
:Methode rechnung().
Beide Methoden sind davon abhängig, welche Art Service wir vor uns
haben:
- Flugbuchung,
- Mietwagenbuchung,etc.
Daher können diese Methoden noch nicht in der Elternklasse
implementiert werden.

Vererbungsbeziehungen Abstrakte Klassen Prof. Dr. Ute Matecki 344
Abstrakte Klassen – Anwendungsbeispiel – UML-Darstellung
BuchungsService
-anbieter: String
+BuchungsService(anbieter: String)
+getAnbieter(): String
+preis(): double
+rechnung(): String
FlugTicketService
-flugNr: String
-reihe: int
-sitzNr: int
-hatZusatzGepaeck: boolean
-flugDatum: String
+FlugTicketService(anbieter: String, flugNr: String, reihe: int, sitzNr: int, hatZusatzGepaeck: boolean, flugDatum: String)
+preis(): double
+rechnung(): String
MietwagenService
-gebuchteTage: int
-kategorie: int
+MietwagenService(anbieter: String, gebuchteTage: int, kategorie: int)
+getGebuchteTage(): int
+getKategorie(): int
+preis(): double
+rechnung(): String
Implementierung für FlugTicketService
Implementierung für MietwagenService
Abstrakte Klasse mit
abstrakten Methoden

Vererbungsbeziehungen Abstrakte Klassen Prof. Dr. Ute Matecki 345
Abstrakte Klassen – Anwendungsbeispiel – Java-Darstellung
Abstrakte Klasse BuchungsService
1 public abstract class BuchungsService {
2
3 private String anbieter; // Name des Anbieters
4
5 public BuchungsService(String anbieter) {
6 this.anbieter = anbieter;
7 } // end constructor
8
9 public String getAnbieter() {
10 return anbieter;
11 } // end method
Abstrakte Klasse enthält Anbieternamen als String,
voll qualifizierten Konstruktor, getter-Methode, sowie ...

Vererbungsbeziehungen Abstrakte Klassen Prof. Dr. Ute Matecki 346
Abstrakte Klassen – Anwendungsbeispiel – Java-Darstellung
Abstrakte Klasse BuchungsService
12 // Preisberechnung muss in der Kindklasse
13 // implementiert werden!
14 public abstract double preis() ;
15
16 // Rechnungserstellung muss in der Kindklasse
17 // implementiert werden!
18 public abstract String rechnung() ;
19
20 } // end class
... 2 abstrakte Methoden

Vererbungsbeziehungen Abstrakte Klassen Prof. Dr. Ute Matecki 347
Abstrakte Klassen – Anwendungsbeispiel – Java-Darstellung
Abgeleitete Klasse MietwagenService – Attribute und Konstruktor
1 public class MietwagenService extends BuchungsService {
2
3 private int gebuchteTage;
4 private int kategorie;
5
6 public MietwagenService(String anbieter,
7 int gebuchteTage, int kategorie) {
8 // Anbietername an Superklassenkonstruktor geben
9 super (anbieter);
10 this.gebuchteTage = gebuchteTage;
11 this.kategorie = kategorie;
12 } // end constructor

Vererbungsbeziehungen Abstrakte Klassen Prof. Dr. Ute Matecki 348
Abstrakte Klassen – Anwendungsbeispiel – Java-Darstellung
Abgeleitete Klasse MietwagenService – getter-Methoden
13 public int getGebuchteTage() {
14 return gebuchteTage;
15 } // end method
16
17 public int getKategorie() {
18 return kategorie;
19 } // end method

Vererbungsbeziehungen Abstrakte Klassen Prof. Dr. Ute Matecki 349
Abstrakte Klassen – Anwendungsbeispiel – Java-Darstellung
Abgeleitete Klasse MietwagenService – Implementierung der Methode preis()
20 @Override public double preis () {
21 double preis = 0.0;
22 if (kategorie == 0) {
23 preis = 35.50 * gebuchteTage;
24 }
25 else if (kategorie >= 1 ) {
26 preis = 43.20 * gebuchteTage;
27 }
28 return preis;
29 } // end method
Annotation
@Override

Vererbungsbeziehungen Abstrakte Klassen Prof. Dr. Ute Matecki 350
Abstrakte Klassen – Anwendungsbeispiel – Java-Darstellung
Klasse MietwagenService – Implementierung der Methode rechnung()
30 @Override public String rechnung() {
31 String rechnungsString = "";
32 rechnungsString +="Rechnung von "+getAnbieter() + "\n";
33 rechnungsString += "Gebuchte Tage: "+gebuchteTage + "\n";
34 rechnungsString += "Endpreis: "+preis() + "EUR" +"\n";
35
36 return rechnungsString;
37 } // end method
38 } // end class
Achtung: Die Mehrwertsteuer wurde in dieser Rechnung vernachlässigt!

Vererbungsbeziehungen Abstrakte Klassen Prof. Dr. Ute Matecki 351
Einschub: Annotationen am Beispiel @Override
Was ist eine Annotation?
Metainformation zu Deklarationen von
- Klassen,
- Methoden,
- Attributen
Beginnt immer mit dem Zeichen @, gefolgt von dem Annotationsnamen
Werden von einem Bestandteil des Compilers ausgewertet
Unterschied zu Modifizierern: In Java können auch eigene Annotationen
implementiert werden (späteres Kapitel ...).

Vererbungsbeziehungen Abstrakte Klassen Prof. Dr. Ute Matecki 352
Einschub: Annotationen am Beispiel @Override
Häufig genutzte Annotationen
Name der Annotation Bedeutung
@Override Wird am Kopf von Methoden angegeben, die eine Methode einer Elternklasse überschreiben – insbesondere bei der Implementierung von abstrakten Methoden, die von einer abstrakten Elternklasse oder von einem Interface vorgegeben werden. (Nicht zwingend,
aber empfehlenswert! Compiler kontrolliert so, ob wir
auch die richtige Methode überschreiben!)
@Deprecated Wird bei veralteten Methoden oder Attributen angegeben, die man aus Kompatibilitätsgründen noch nicht
löschen will.

Vererbungsbeziehungen Abstrakte Klassen Prof. Dr. Ute Matecki 353
Abstrakte Klassen – Anwendungsbeispiel – Java-Darstellung
Nutzung MietwagenService in einer anwendenden main()-Klasse
(Codefragment)
1 String firmenName = "MietwagenService Rostlaube";
2 int tage = 2;
3 int kategorie = 1;
4
5 // Buchung eines Mietwagens
6 BuchungsService buchung1 =
7 new MietwagenService(firmenName, tage, kategorie);
8
9 double preis = buchung1.preis();
10 String rechnung = buchung1.rechnung();
11 System.out.println(rechnung);

Vererbungsbeziehungen Abstrakte Klassen Prof. Dr. Ute Matecki 354
Abstrakte Klassen – Anwendungsbeispiel – Java-Darstellung
Was NICHT geht: Objekterstellung von der abstrakten Klasse
1 String firmenName = "MietwagenService Rostlaube";
2 BuchungsService buchung1 =
3 new BuchungsService(firmenName);
Objekterstellung von abstrakten Klassen ist nicht möglich.
Welcher Code sollte hier auch für die abstrakten Methoden aufgerufen
werden?!

Vererbungsbeziehungen Abstrakte Klassen Prof. Dr. Ute Matecki 355
Zusammenfassung
Wir merken uns zu Abstrakten Klassen
Es gibt Sowarearchitekturen, in denen man „erzwingen“ will, dass in
den Kindklassen bestimmte Methoden auf jeden Fall implementiert
werden.
Derartige Methoden werden in der Elternklasse als abstract vereinbart:
datentyp methodenName(...);
Eine Klasse mit abstrakten Methoden muss ebenfalls als abstract
vereinbart werden.
Die konkrete Methodenimplementierung erfolgt in einer abgeleiteten
Klasse.
Von einer abstrakten Klasse können wir keine Objekte instanziieren!

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 356
Interfaces
Interfaces – was ist das und wozu wird’s benötigt?
i. d. R. Abstrakte Vorgaben von Methodenschnittstellen für abgeleitete
Klassen.
Wenn eine Klasse von einem Interface „erbt“, so sagt wir: Die Klasse
implementiert das Interface.
Wir benötigen Interfaces, wenn wir erzwingen wollen, dass bestimmte
Methoden implementiert werden, aber keine normale Klasse schreiben
wollen.
Eine Klasse kann mehrere Interfaces implementieren, aber nur von
einer Klasse abgeleitet sein! :Interfaces können also indirekt
Mehrfachvererbung möglich machen.

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 357
Interfaces
Interfaces – was ist das und wozu wird’s benötigt?
Bis Java 7 gilt: Interfaces können keine Methodenimplementierungen
enthalten, sondern nur:
- Rein abstrakte Methoden (Methodenköpfe). Diese sind automatisch public
- Konstanten. Diese sind automatisch public static final.
Ab Java 8 gilt:
- Interfaces können Default-Implementierungen ihrer Methodenvorgaben enthalten.
- Dies wird durch das Schlüsselwort default vor dem Rückgabetyp des
Methodenkopfes kennntlich gemacht.

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 358
Interfaces
Interfaces – Darstellung in der UML
«interface»
IShapeReader
+ read(): void
«interface»
IShapeWriter
+ write(): void
Drawing
- myShapes : ArrayList<Shape>
+ Drawing()
+ write(): void
+ read(): void
Zwei Interfaces, die
jeweils eine Methode
vorgeben
Eine Klasse, die beide Interfaces implementiert :Vererbungspfeil ist gestrichelt!

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 359
Interfaces
Interfaces – Syntax in Java
1 [weitere Modifizierer] interface InterfaceName1 {
2 [public static final Attribute]
3
4 [Modifizierer] returnTyp methodenname() ;
5 // Weitere Methodenprototypen
6 }

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 360
Interfaces
Interfaces – Syntax in Java bei implementierenden Klassen
1 [weitere Modifizierer] class Klassenname
2 implements InterfaceName1,
3 Interfacename2,... {
4 [Attribute]
5 [Konstruktoren]
6 [Methoden]
7 [Implementierung der Methoden, die von den
8 Interfaces vorgegeben sind]
9 }
:Klasse „erbt“ von den implementierten Interfaces

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 361
Interfaces – Anwendungsbeispiel 1 – UML-Darstellung
Zeichnung mit verschiedenen geometrischen Formen
Shape
- identifier : String
+ Shape(identifier : String)
+ getIdentifier() : String
+ print(): void
«interface»
IShapeReader
+ read(): void
«interface»
IShapeWriter
+ write(): void
Drawing
- myShapes : ArrayList<Shape>
+ Drawing()
+ write(): void
+ read(): void
Point
- x : int
- y : int
+ Point(identifier : String, x : int, y : int)
+ getX() : int
+ setX(x : int): void
+ getY() : int
+ setY(y : int): void
+ print(): void
Circle
- x : int
- y : int
- radius : int
+ Circle(identifier : String, x : int, y : int, radius : int)
+ getX() : int
+ setX(x : int): void
+ getY() : int
+ setY(y : int): void
+ getRadius() : int
+ setRadius(radius : int): void
+ print(): void
Die abstrakte Klasse Shape gibt vor:
Eine geometrische Form hat immer
einen Namen.
Sie muss ihre Daten zum Testen
ausgeben können. 
Die beiden Interfaces geben vor,
dass eine implementierende Klasse
eine Lese- und eine Schreibmethode
haben muss (z.B. auf Datei)
Eine Zeichnung muss ihre geometrischen
Figuren einlesen und herausschreiben
können (z. B. von / auf Datei)

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 362
Interfaces – Anwendungsbeispiel 1 – Java-Darstellung
Interfaces – Anwendungsbeispiel 1 – Abstrakte Klasse Shape
1 // Superklasse fuer geometrische Figuren
2 public abstract class Shape {
3
4 // Eine geometrische Form hat immer
5 // einen Bezeichner / Namen, zB. kreis1
6 private String identifier;
7
8 public Shape(String identifier) {
9 this.identifier = identifier;
10 } // end constructor

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 363
Interfaces – Anwendungsbeispiel 1 – Java-Darstellung
Interfaces – Anwendungsbeispiel 1 – Abstrakte Klasse Shape
11 public String getIdentifier() {
12 return identifier;
13 } // end method
14
15 // Abstrakte Methode: Eine geometrische Form soll
16 // immer ihre Daten ausgeben koennen
17 public abstract void print();
18 } // end class

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 364
Interfaces – Anwendungsbeispiel 1 – Java-Darstellung
Interfaces – Anwendungsbeispiel 1 – Klasse Point
1 // Punkt in einem 2-dimensionalen, ganzzahligen
2 // Koordinatensystem (zB. Bildschirm)
3 public class Point extends Shape {
4 private int x;
5 private int y;
6
7 public Point(String identifier, int x, int y) {
8 super (identifier); // identifier an Superklasse
9 this.x = x;
10 this.y = y;
11 } // end constructor

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 365
Interfaces – Anwendungsbeispiel 1 – Java-Darstellung
Interfaces – Anwendungsbeispiel 1 – Klasse Point
12 // getter / setter
13 public int getX() { return x; }
14
15 public void setX(int x) { this.x = x; }
16
17 public int getY() { return y; }
18
19 public void setY(int y) { this.y = y; }

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 366
Interfaces – Anwendungsbeispiel 1 – Java-Darstellung
Interfaces – Anwendungsbeispiel 1 – Klasse Point
20 @Override
21 public void print() {
22 System.out.println(
23 "Dies ist ein Punkt mit dem Bezeichner" +
24 this.getIdentifier());
25 System.out.println("x = " + x);
26 System.out.println("y = " + y);
27
28 } // end method print()
29 } // end class

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 367
Interfaces – Anwendungsbeispiel 1 – Java-Darstellung
Interfaces – Anwendungsbeispiel 1 – Klasse Circle
1 public class Circle extends Shape {
2
3 private int x;
4 private int y;
5 private int radius;
6
7 public Circle(String identifier, int x, int y,
8 int radius) {
9 super (identifier);
10 this.x = x;
11 this.y = y;
12 this.radius = radius;
13 } // end constructor

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 368
Interfaces – Anwendungsbeispiel 1– Java-Darstellung
Interfaces – Anwendungsbeispiel 1 – Klasse Circle
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
25 public void setRadius(int radius) { this.radius = radius;
26 } // end method

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 369
Interfaces – Anwendungsbeispiel 1 – Java-Darstellung
Interfaces – Anwendungsbeispiel 1 – Klasse Circle
27 @Override
28 public void print() {
29 System.out.println(
30 "Dies ist ein Kreis mit dem Bezeichner"
31 + this.getIdentifier());
32 System.out.println("Mittelpunkt x = " + x);
33 System.out.println("Mittelpunkt y = " + y);
34 System.out.println("Radius = " + radius);
35 } // end method print()
36 } // end class

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 370
Interfaces – Anwendungsbeispiel 1 – Java-Darstellung
Interfaces – Anwendungsbeispiel 1 – Interface IShapeReader
1 public interface IShapeReader {
2
3 // Shape einlesen (zB von Tastatur oder Datei)
4 public void read();
5 } // end interface
:Interface gibt der implementierenden Klasse eine Einlesemethode vor

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 371
Interfaces – Anwendungsbeispiel 1 – Java-Darstellung
Interfaces – Anwendungsbeispiel 1 – Interface IShapeWriter
1 public interface IShapeWriter {
2 // Shape ausgeben (zB auf Konsole oder Datei)
3 public void write();
4 }
:Interface gibt der implementierenden Klasse eine Herausschreibemethode
vor

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 372
Interfaces – Anwendungsbeispiel 1 – Java-Darstellung
Interfaces – Anwendungsbeispiel 1 – Klasse Drawing
1 import java.util.ArrayList;
2 import java.util.Scanner;
3
4 public class Drawing implements IShapeReader, IShapeWriter {
5
6 private ArrayList<Shape> myShapes;
7
8 public Drawing() {
9 // Lege leere ArrayList fuer Shapes
10 // an. (Hier konkret: Point oder Circle)
11 myShapes = new ArrayList<Shape>();
12 } // end constructor
:Klasse implementiert die Interfaces IShapeReader und IShapeWriter
Liste für Shapes (Pointund Circle-Objekte)
:Polymorphie

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 373
Interfaces – Anwendungsbeispiel 1 – Java-Darstellung
Interfaces – Anwendungsbeispiel 1 – Klasse Drawing – Methode
write()/Variante 1
13 @Override public void write( ) {
14 // Rufe von allen Shapes die print()-Methode
15 // auf --> write() erfolgt auf Konsole
16 for (int i=0; i<myShapes.size(); i++) {
17 myShapes.get(i).print();
18 } // end for
19 } // end implementation of method write()
:Implementierung der Methodenvorgabe von Interface IShapeWriter
:Schreiben erfolgt auf die Konsole

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 374
Interfaces – Anwendungsbeispiel 1 – Java-Darstellung
Interfaces – Anwendungsbeispiel 1 – Klasse Drawing – Methode
write()/Variante 2
13 @Override public void write( ) {
14 // Rufe von allen Shapes die print()-Methode
15 // auf --> write() erfolgt auf Konsole
16 for (Shape s : myShapes) {
17 s.print();
18 } // end for
19 } // end implementation of method write()
:Implementierung der Methodenvorgabe von Interface IShapeWriter
:Schreiben erfolgt auf die Konsole

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 375
Interfaces – Anwendungsbeispiel 1– Java-Darstellung
Interfaces – Anwendungsbeispiel 1 – Klasse Drawing – Methode read()/Teil1
20 @Override public void read() {
21 // read() erfolgt von Tastatur!
22 Scanner tastatur = new Scanner(System.in);
23 String eingabe = "";
24 String s ; // Name der Shape
25 int x,y; // x/y-Koordinate der Shape
26
27 do {
28 // Nutzer gibt gewuenschte Objektart ein
29 System.out.print("Welche Objektart? ");
30 eingabe = tastatur.next();
:Implementierung der Methodenvorgabe von Interface IShapeReader
:Einlesen erfolgt von Tastatur in do – while-Schleife

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 376
Interfaces – Anwendungsbeispiel 1 – Java-Darstellung
Interfaces – Anwendungsbeispiel 1 – Klasse Drawing – Methode read()/Teil2
31 // Je nach Objektart -- andere Objekterzeugung
32 switch (eingabe) {
33
34 case "point":
35 System.out.print("Bezeichner: ");
36 s = tastatur.next();
37 System.out.print("x-Wert: ");
38 x = tastatur.nextInt();
39 System.out.print("y-Wert: ");
40 y = tastatur.nextInt();
41
42 Point p = new Point(s,x,y);
43 myShapes.add(p); break;
Nutzer gibt Daten für
den gewünschten Punkt
ein
Shapes-Liste bekommt
Point hinzugefügt

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 377
Interfaces – Anwendungsbeispiel 1 – Java-Darstellung
Interfaces – Anwendungsbeispiel 1 – Klasse Drawing – Methode read()/Teil3
44 case "circle":
45 // Daten fuer Kreis einlesen
46 System.out.print("Bezeichner: ");
47 s = tastatur.next();
48 System.out.print("Mittelpunkt x-Wert: ");
49 x = tastatur.nextInt();
50 System.out.print("Mittelpunkt y-Wert: ");
51 y = tastatur.nextInt();
52 System.out.print("Radius: ");
53 int radius = tastatur.nextInt();
54
55 Circle c = new Circle(s,x,y, radius);
56 myShapes.add(c); // Kreis in Liste haengen

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 378
Interfaces – Anwendungsbeispiel 1 – Java-Darstellung
Interfaces – Anwendungsbeispiel 1 – Klasse Drawing – Methode read()/Teil4
57 case "ende": break;
58 default: break;
59 } // end switch
60
61 }while(!eingabe.equals("ende")); // end do-while
62
63 } // // end implementation of method read()
64 } // end class

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 379
Interfaces – Anwendungsbeispiel 1 – Java-Darstellung
Interfaces – Anwendungsbeispiel 1 – main()-Klasse
1 public class ShapesMain1 {
2 public static void main(String[] args) {
3 Drawing d = new Drawing();
4 d.read(); // Shapes vom Nutzer einlesen
5 d.write();// Shapes auf die Konsole ausgeben
6 }
7 }

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 380
Interfaces – Default-Implementierung von Methoden
Wozu Default-Implementierung von Interface-Methoden?
Bequemlichkeit für diejenigen, die das Interface nutzen!
Nicht jede „Mini-Methode“ des Interfaces muss dann implementiert
werden.
Sehr häufig sind diese Default-Implementierungen leer – nämlich dann,
wenn die Methode nicht in jeder implementierenden Klasse benötigt
wird.

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 381
Interfaces – Default-Implementierung von Methoden
Interfaces – Syntax bei der Default-Implementierung von Methoden
1 public interface Ixyz {
2
3 default returnType method1 (...) {
4 // code of implementation
5 } // end of implementation
6
7 // other method prototypes ...
8
9 } // end interface

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 382
Interfaces – Anwendungsbeispiel 2 – Default-Implementierung
Interfaces – Anwendungsbeispiel 2 – UML-Darstellung
«Interface»
IGambler
 + getNameOfGame(): String
+ hasWon():boolean
Winner
- nameOfGame: String
+ getNameOfGame(): String
Loser
+ getNameOfGame(): String
+ hasWon(): boolean
Dicer
 + getNameOfGame(): String
 + hasWon(): boolean
Klasse Winner hat keine eigene hasWon()-
Methode, sondern übernimmt die DefaultImplementierung aus dem Interface 
IGambler
Loser verliert immer --
seine hasWon()-Methode
muss also die Default-Methode
aus IGambler überschreiben
Dicer (Würfelspieler) gewinnt
nur, wenn er eine "6" würfelt.
Seine hasWon()-Methode muss
ebenfalls die aus IGambler
überschreiben!
Methode hasWon() hat eine
default-Implementierung, die
immer true zurückgibt.

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 383
Interfaces – Anwendungsbeispiel 2 – Java-Darstellung
Interfaces – Anwendungsbeispiel 2 – Interface IGambler
1 public interface IGambler {
2
3 String getNameOfGame(); // Name des Spiels
4
5 // Wenn nichts anderes implementiert wird,
6 // gewinnt der Spieler immer!
7 default boolean hasWon() {
8 return true ;
9 } // end of method implementation
10 } // end interface

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 384
Interfaces – Anwendungsbeispiel 2 – Java-Darstellung
Interfaces – Anwendungsbeispiel 2 – Klasse Winner
1 public class Winner implements IGambler {
2
3 private final String nameOfGame =
4 "Winner takes all!";
5
6 @Override
7 public String getNameOfGame() {
8 return nameOfGame;
9 } // end method
10
11 // hasWon () muss nicht neu implementiert werden!
12 } // end class

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 385
Interfaces – Anwendungsbeispiel 2 – Java-Darstellung
Interfaces – Anwendungsbeispiel 2 – Klasse Loser
1 public class Loser implements IGambler {
2
3 @Override
4 public String getNameOfGame() {
5 return this.getClass().getName();
6 }
7
8 // Loser verliert immer! Neuimplementation!
9 @Override
10 public boolean hasWon() { return false ; }
11 } // end class

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 386
Interfaces – Anwendungsbeispiel 2 – Java-Darstellung
Interfaces – Anwendungsbeispiel 2 – Klasse Dicer – Teil 1
1 import java.util.Random;
2
3 public class Dicer implements IGambler {
4
5 private int value; // gewuerfelter Wert
6
7 @Override
8 public String getNameOfGame() {
9 return this.getClass().getName();
10 } // end method getNameOfGame()

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 387
Interfaces – Anwendungsbeispiel 2 – Java-Darstellung
Interfaces – Anwendungsbeispiel 2 – Klasse Dicer – Teil 2
11 @Override
12 public boolean hasWon() {
13
14 Random r = new Random();// Wuerfel erzeugen
15
16 // Einmal wuerfeln: nextInt() liefert hier eine
17 // Ganzzahl zwischen 0 und kleiner 6 -- daher +1
18 value = r.nextInt(6) + 1;
19
20 // Gewonnen, wenn eine "6" gewuerfelt
21 return (value==6);
22 } // end method hasWon()
23 } // end class

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 388
Interfaces – Anwendungsbeispiel 2 zu Default-Implementierung
Zusammenfassung
Das Interface IGambler modelliert das Gewinnverhalten eines Spielers
Die Methode hasWon() ist hier als Default-Implementierung konzipiert:
- Wenn nichts anderes in der implementierenden Klasse steht, dann liefert die
Default-Implementierung immer true zurück.
- Der Spieler gewinnt in diesem Fall also immer.
Die Klasse Winner implementiert das Interface und nutzt die
Default-Implementierung von hasWon().
Die Klassen Loser und Dicer (Würfelspieler) haben jeweils eine eigene
Implementierung von hasWon().

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 389
Interfaces – Anwendungsbeispiel 2 zu Default-Implementierung
Übung
Schreiben Sie eine Klasse TestGame, welche
jeweils einen Spieler für jede der 3 Klassen Winner,Loser und Dicer
erzeugt.
Lassen Sie jeden Spieler 10 Runden spielen und geben Sie aus, ob er
gewonnen hat oder nicht!

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 390
Interfaces – mehrstufige Vererbungshierarchien – UML
Interfaces können von anderen Interfaces Vorgaben erben!
«interface»
IShapeReader
+ read(): void
«interface»
IShapeWriter
+ write(): void
«interface»
IShapeReaderWriter
+ print(): void
Drawing
- myShapes : java.util.ArrayList
+ Drawing()
+ print(): void
+ read(): void
+ write(): void
Die Klasse Drawing implementiert
das Interface IShapeReaderWriter
Sie muss alle Methoden des Interfaces implementieren -- auch die ererbten.
Das Interface IShapeReaderWriter erbt von
zwei weiteren Interfaces.

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 391
Interfaces – mehrstufige Vererbungshierarchien – Java
Elterninterface IShapeReader
1 public interface IShapeReader {
2
3 // Shape einlesen (zB von Tastatur oder Datei)
4 public void read();
5 }

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 392
Interfaces – mehrstufige Vererbungshierarchien – Java
Elterninterface IShapeWriter
1 public interface IShapeWriter {
2
3 // Shape ausgeben (zB auf Konsole oder Datei)
4 public void write();
5 }

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 393
Interfaces – mehrstufige Vererbungshierarchien – Java
Kindinterface IShapeReaderWriter
1 public interface IShapeReaderWriter
2 extends IShapeReader, IShapeWriter {
3
4 public void print(); // nur fuer Ausgabe auf Bildschirm
5 }
:erbt Vorgaben von 2 Elterninterfaces
:gibt selbst eine eigene Methode print() vor.

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 394
Interfaces – Zusammenfassung
Wir merken uns:
Interfaces sind rein abstrakte Vorgaben von Methodenschnittstellen für
abgeleitete Klassen.
Wenn eine Klasse von einem Interface „erbt“, so sagt wir: Die Klasse
implementiert das Interface, denn: Sie implementiert die Methoden,
die das Interface vorgibt.
Eine Klasse kann mehrere Interfaces implementieren.

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 395
Interfaces – Zusammenfassung
Wir merken uns:
Eine Implementierungsbeziehung ist eine IST-Beziehung.
In unserem Shape-Beispiel also: Eine Drawing IST auch ein
IShapeReader und ein IShapeWriter
Ein Interface kann auch von anderen Interfaces erben – dies geschieht
mit dem Schlüsselwort extends.

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 396
Auswirkungen von Interfaces auf Polymorphie
Interfaces sind Supertypen!
Ein Interface kann genau so als Supertyp verwendet werden wie eine
Klasse.
Das bedeutet: Wir können Variablen vom Typ eines Interfaces anlegen.
Die Objekterzeugung erfolgt dann – ähnlich wie bei einer abstrakten
Superklasse – mit einer der implementierenden Klassen.
Auf den nächsten Folien folgt ein kleines Beispiel ...

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 397
Auswirkungen von Interfaces auf Polymorphie
Beispiel 1: Abstrakte Klasse als Elterntyp
Sachbuch
 + toString(): String
Buch
 + toString(): String
Roman
 + toString(): String
Superklasse
(hier abstrakt)
als Elterntyp

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 398
Auswirkungen von Interfaces auf Polymorphie
Beispiel 1: Abstrakte Klasse als Elterntyp
Hier ist folgendes, wie gewohnt, möglich:
1 // Liste anlegen -- typisiert auf Elternklasse
2 ArrayList<Buch> liste = new ArrayList<Buch>();
3
4 // Der Liste ein Element vom Typ Kindklasse hinzufuegen
5 liste.add(new Sachbuch());

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 399
Auswirkungen von Interfaces auf Polymorphie
Beispiel 2: Interface als Elterntyp
Sachbuch
 + toString(): String
Roman
 + toString(): String
Interface
als Elterntyp
«Interface»
IBuch
 + toString(): String

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 400
Auswirkungen von Interfaces auf Polymorphie
Beispiel 2: Interface als Elterntyp
Hier ist folgendes, wie gewohnt, möglich:
1 // Liste anlegen -- typisiert auf Interface
2 ArrayList<IBuch> liste = new ArrayList<IBuch>();
3
4 // Der Liste ein Element vom Typ einer der
5 // implementierenden Klassen hinzufuegen
6 liste.add(new Sachbuch());

Vererbungsbeziehungen Interfaces Prof. Dr. Ute Matecki 401
Auswirkungen von Interfaces auf Polymorphie
Wir merken uns: Interfaces sind Supertypen!
Ein Interface kann genau so als Supertyp verwendet werden wie eine
Klasse.
Das bedeutet: Wir können Variablen vom Typ eines Interfaces anlegen.
Die Objekterzeugung erfolgt dann – ähnlich wie bei einer abstrakten
Superklasse – mit einer der implementierenden Klassen.
Auch Listen oder Arrays können auf ein Interface typisiert werden.
Sie werden dann aber zur Laufzeit mit Objekten von Klassen befüllt, die
dieses Interface implementieren!

Vererbungsbeziehungen Der instanceof-Operator Prof. Dr. Ute Matecki 402
Der instanceof-Operator
Problem bei polymorphen Objekten
Häufig ist eine Referenzvariable auf den Elterntyp typisiert:
Elternklasse variable;
Zur Laufzeit erhält die Variable aber eine Referenz auf ein Objekt einer
Kindklasse:
variable = new Kindklasse1();
(beispielsweise beim Einlesen aus einer Datei)
Manchmal muss später festgestellt werden, zu welcher (Kind-)Klasse das
Objekt einer solchen Referenz gehört.
Hierzu stellt Java den Operator instanceof bereit.

Vererbungsbeziehungen Der instanceof-Operator Prof. Dr. Ute Matecki 403
Der instanceof-Operator
Anwendung des instanceof-Operators
1 if (variable instanceof Kindklasse1) {
2 // Aktion fuer ein Objekt von Kindklasse1
3 }
4 else if(variable instanceof Kindklasse2) {
5 // Aktion fuer ein Objekt von Kindklasse2
6 }
7 else ...

Vererbungsbeziehungen Der instanceof-Operator Prof. Dr. Ute Matecki 404
Der instanceof-Operator
Anwendungsbeispiel: eine kleine Klassenhierachie
Sachbuch
 - fachgebiet: String
 + Sachbuch( autor: String, buchtitel: String, fachgebiet: String)
 + getFachgebiet(): String
 + toString(): String
Buch
 - autor: String
 - buchtitel: String
 + Buch( autor: String, buchtitel: String)
 + getAutor(): String
 + getBuchtitel(): String
 + toString(): String
Roman
 - genre: String
 + Roman( autor: String, buchtitel: String, genre: String)
 + getGenre(): String
 + toString(): String

Vererbungsbeziehungen Der instanceof-Operator Prof. Dr. Ute Matecki 405
Der instanceof-Operator
Anwendungsbeispiel: Klasse VerarbeiteBuch
1 import java.util.Scanner;
2 public class VerarbeiteBuch {
3
4 public void ausgabe( Buch b ) {
Formaler Parameter vom Typ der Elternklasse

Vererbungsbeziehungen Der instanceof-Operator Prof. Dr. Ute Matecki 406
Der instanceof-Operator
Anwendungsbeispiel: Klasse VerarbeiteBuch
5 // Ausgabe Ueberschrift
6 if (b instanceof Roman) {
7 System.out.println("Roman: ");
8 } // end if
9 else if (b instanceof Sachbuch) {
10 System.out.println("Sachbuch");
11 } // end else
12
13 // Ausgabe der Objektdaten als String
14 System.out.println(b.toString());
15 } // end method
16 } // end class
Überprüfung: Welches Objekt steckt hinter der Referenzvariablen b?

Vererbungsbeziehungen Der instanceof-Operator Prof. Dr. Ute Matecki 407
Der instanceof-Operator
Anwendungsbeispiel: Klasse VerarbeiteBuch – Alternative Ausgabe
13 // Ausgabe der Objektdaten als String geht auch
14 // einfacher (Weil toString() die Standard-Konv
15 // Methode ist)
16 System.out.println(b);
17 } // end method
18 } // end class
Überprüfung: Welches Objekt steckt hinter der Referenzvariablen b?

Vererbungsbeziehungen Der instanceof-Operator Prof. Dr. Ute Matecki 408
Der instanceof-Operator
Wir merken uns:
Manchmal muss später festgestellt werden, zu welcher (Kind-)Klasse ein
Objekt einer Elternklassen-Referenz gehört.
Hierzu stellt Java den Operator instanceof bereit.
Der Operator gibt einen boolean-Wert zurück: true, falls der
instanceof-Vergleich zutri, false sonst.

