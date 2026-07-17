# Skript-Rohtext Teil 2: Generics – Einfache Generics & Standard-Interfaces (Skript S. 550–559)

Generische Klassen (Generics) Einfache Generics und deren Anwendung Prof. Dr. Ute Matecki 550
Eine einfache Generic: Ein Paar von gleichartigen Objekten
... kann verwendet werden für:
ein Arbeitsteam zweier Studierender im Praktikum,

Generische Klassen (Generics) Einfache Generics und deren Anwendung Prof. Dr. Ute Matecki 550
Eine einfache Generic: Ein Paar von gleichartigen Objekten
... kann verwendet werden für:
ein Arbeitsteam zweier Studierender im Praktikum,
ein Team von 2 Wettkämpfern, welches gegen ein anderes antritt,

Generische Klassen (Generics) Einfache Generics und deren Anwendung Prof. Dr. Ute Matecki 550
Eine einfache Generic: Ein Paar von gleichartigen Objekten
... kann verwendet werden für:
ein Arbeitsteam zweier Studierender im Praktikum,
ein Team von 2 Wettkämpfern, welches gegen ein anderes antritt,
Artikel, die paarweise verkau werden,

Generische Klassen (Generics) Einfache Generics und deren Anwendung Prof. Dr. Ute Matecki 550
Eine einfache Generic: Ein Paar von gleichartigen Objekten
... kann verwendet werden für:
ein Arbeitsteam zweier Studierender im Praktikum,
ein Team von 2 Wettkämpfern, welches gegen ein anderes antritt,
Artikel, die paarweise verkau werden,
...

Generische Klassen (Generics) Einfache Generics und deren Anwendung Prof. Dr. Ute Matecki 551
Eine sehr einfache Generic: Ein Paar von gleichartigen Objekten
Anwendungsfall bei uns: Verschiedene Arten von Personen
Laeufer
 - gelaufeneZeit: double
 - gelaufeneStrecke: int 
 + Laeufer( vorname: String, nachname: String, gelaufeneZeit: double, gelaufeneStrecke: int)
 + getGelaufeneZeit(): double
 + getGelaufeneStrecke(): int
 + toString(): String
Person
 - vorname: String 
 - nachname: String 
 + Person( vorname: String, nachname: String)
 + getVorname(): String
 + setVorname( vorname: String)
 + getNachname(): String
 + setNachname( nachname: String)
 + toString(): String
SenatsMitglied
 - gewaehltBis: LocalDate 
 + SenatsMitglied( vorname: String, nachname: String, matnr: int, gewaehltBis: LocalDate)
 + getGewaehltBis(): LocalDate
 + setGewaehltBis( in gewaehltBis: LocalDate)
 + toString(): String
Studierende
 - matnr: int
 + Studierende( vorname: String, nachname: String, in matnr: int)
 + getMatnr(): int
 + setMatnr( matnr: int)
 + toString(): String
Object
 + toString(): String
Oberste Klasse in der Klassenhierarchie ist immer von Object 
abgeleitet!

Generische Klassen (Generics) Einfache Generics und deren Anwendung Prof. Dr. Ute Matecki 552
Eine sehr einfache Generic: Ein Paar von gleichartigen Objekten
Klasse Couple
1 public class Couple<T> {
2
3
4 private T member1;
5 private T member2;
6
Der Datentyp T, welcher über die spitzen Klammern <> an die Klasse
Couple durchgereicht wird, wird bei der Instanziierung mit
new Couple<Datentyp> (Datentyp obj1, Datentyp obj2) durch den
real durchgereichten Datentyp ersetzt!
Hier wird der Typ-Parameter an die
generische Klasse durchgereicht.
Diese beiden Referenzen werden
bei Instanziierung in den realen
Datentyp von T konvertiert.

Generische Klassen (Generics) Einfache Generics und deren Anwendung Prof. Dr. Ute Matecki 553
Eine sehr einfache Generic: Ein Paar von gleichartigen Objekten
Klasse Couple
7 public Couple(T member1, T member2) {
8 this.member1 = member1;
9 this.member2 = member2;
10 } // end constructor
Die Objektreferenzen, welche an
den Konstruktor durchgereicht
werden, haben den Datentyp T, mit
dem vorher instanziiert wurde!

Generische Klassen (Generics) Einfache Generics und deren Anwendung Prof. Dr. Ute Matecki 553
Eine sehr einfache Generic: Ein Paar von gleichartigen Objekten
Klasse Couple
7 public Couple(T member1, T member2) {
8 this.member1 = member1;
9 this.member2 = member2;
10 } // end constructor
Bei
Couple<String> c = new Couple<String>("Asterix","Obelix");
wird T zum Datentyp String.
Die Objektreferenzen, welche an
den Konstruktor durchgereicht
werden, haben den Datentyp T, mit
dem vorher instanziiert wurde!

Generische Klassen (Generics) Einfache Generics und deren Anwendung Prof. Dr. Ute Matecki 553
Eine sehr einfache Generic: Ein Paar von gleichartigen Objekten
Klasse Couple
7 public Couple(T member1, T member2) {
8 this.member1 = member1;
9 this.member2 = member2;
10 } // end constructor
Bei
Couple<String> c = new Couple<String>("Asterix","Obelix");
wird T zum Datentyp String.
Bei
Couple<Integer> c = new Couple<Integer>(2,42);
wird T zum Datentyp der Wrapper-Klasse Integer.
Die Objektreferenzen, welche an
den Konstruktor durchgereicht
werden, haben den Datentyp T, mit
dem vorher instanziiert wurde!

Generische Klassen (Generics) Einfache Generics und deren Anwendung Prof. Dr. Ute Matecki 554
Eine sehr einfache Generic: Ein Paar von gleichartigen Objekten
Klasse Couple
11 public void print() {
12 System.out.println("Member 1: " + member1.toString() );
13 System.out.println("--------------------------------");
14 System.out.println("Member 2: " + member2.toString() );
15 System.out.println("===============================");
16 } // end method print()
17 } // end class

Generische Klassen (Generics) Einfache Generics und deren Anwendung Prof. Dr. Ute Matecki 554
Eine sehr einfache Generic: Ein Paar von gleichartigen Objekten
Klasse Couple
11 public void print() {
12 System.out.println("Member 1: " + member1.toString() );
13 System.out.println("--------------------------------");
14 System.out.println("Member 2: " + member2.toString() );
15 System.out.println("===============================");
16 } // end method print()
17 } // end class
Die Klasse Object stellt eine rudimentäre toString()- Methode bereit. Sie
kann aber in API-Klassen wie String, Integer, oder auch in eigenen
Klassen wie Person überschrieben sein!

Generische Klassen (Generics) Einfache Generics und deren Anwendung Prof. Dr. Ute Matecki 555
Eine sehr einfache Generic: Ein Paar von gleichartigen Objekten
Anwendung der generischen Klasse Couple auf verschiedene Datentypen
1 public class MainCouple1 {
2 public static void main(String[] args) {
3
4 Studierende member1 =
5 new Studierende("Heinz","Meier",4711);
6 Studierende member2 =
7 new Studierende("Hugo","Helmchen",4712);
8
9 Couple<Studierende> programmierTeam =
10 new Couple<Studierende>(member1,member2);
11
12 programmierTeam.print();
Ein Couple mit
zwei Objekten
vom Typ
Studierende.

Generische Klassen (Generics) Einfache Generics und deren Anwendung Prof. Dr. Ute Matecki 556
Eine sehr einfache Generic: Ein Paar von gleichartigen Objekten
Anwendung der generischen Klasse Couple auf verschiedene Datentypen
13 Laeufer lauf1 =
14 new Laeufer("Asterix","X",9.2,100);
15 Laeufer lauf2 =
16 new Laeufer("Obelix","O",9.1,100);
17
18 Couple<Laeufer> wettkampfTeam =
19 new Couple<Laeufer>(lauf1,lauf2);
20
21 wettkampfTeam.print();
22 } // end method main()
23 } // end class
Ein Couple mit zwei
Objekten vom Typ
Laeufer.

Generische Klassen (Generics) Einfache Generics und deren Anwendung Prof. Dr. Ute Matecki 557
Eine sehr einfache Generic: Ein Paar von gleichartigen Objekten
Ausgabe der main()-Methode
1 Member 1: Heinz Meier
2 Matnr: 4711
3 --------------------------------
4 Member 2: Hugo Helmchen
5 Matnr: 4712
6 ===============================
7 Member 1: Asterix X
8 Gelaufene Zeit: 9.2sec
9 Gelaufene Strecke: 100m
10 --------------------------------
11 Member 2: Obelix O
12 Gelaufene Zeit: 9.1sec
13 Gelaufene Strecke: 100m
14 ===============================
Jede der Klassen
Studierende und Laeufer
hat eine eigene
toString()-Methode, die
für die Ausgabe innerhalb
des Couple genutzt wird!

Generische Klassen (Generics) Einfache Generics und deren Anwendung Prof. Dr. Ute Matecki 558
Zusammenfassung
Wir merken uns:
Bei der Nutzung eines Generics (z.B. ArrayList) wird bei der Typisierung
ein Typ-Parameter in <> übergeben:
Generic <Typ> variablenname;

Generische Klassen (Generics) Einfache Generics und deren Anwendung Prof. Dr. Ute Matecki 558
Zusammenfassung
Wir merken uns:
Bei der Nutzung eines Generics (z.B. ArrayList) wird bei der Typisierung
ein Typ-Parameter in <> übergeben:
Generic <Typ> variablenname;
Dieser Typ-Parameter wird auch beim Konstruktoraufruf durchgereicht:
Generic <Typ> variablenname = new Generic<Typ>();

Generische Klassen (Generics) Einfache Generics und deren Anwendung Prof. Dr. Ute Matecki 558
Zusammenfassung
Wir merken uns:
Bei der Nutzung eines Generics (z.B. ArrayList) wird bei der Typisierung
ein Typ-Parameter in <> übergeben:
Generic <Typ> variablenname;
Dieser Typ-Parameter wird auch beim Konstruktoraufruf durchgereicht:
Generic <Typ> variablenname = new Generic<Typ>();

Generische Klassen (Generics) Einfache Generics und deren Anwendung Prof. Dr. Ute Matecki 558
Zusammenfassung
Wir merken uns:
Bei der Nutzung eines Generics (z.B. ArrayList) wird bei der Typisierung
ein Typ-Parameter in <> übergeben:
Generic <Typ> variablenname;
Dieser Typ-Parameter wird auch beim Konstruktoraufruf durchgereicht:
Generic <Typ> variablenname = new Generic<Typ>();
Die runden () Klammern sind hierbei die Klammern für die
Daten-Parameter des Konstrukturs.

Generische Klassen (Generics) Standard-Interfaces der Java-API für Generics Prof. Dr. Ute Matecki 559
Wichtige Standard-Interfaces der Java-API für Generics
Interessant ist für Generics unter anderem ...
Wenn eine Generic mit der Iterator-Schleife for(Typ x: liste)
durchlaufbar sein soll, so muss sie das Interface Iterable
implementieren. Sie muss also iterierbar sein.

Generische Klassen (Generics) Standard-Interfaces der Java-API für Generics Prof. Dr. Ute Matecki 559
Wichtige Standard-Interfaces der Java-API für Generics
Interessant ist für Generics unter anderem ...
Wenn eine Generic mit der Iterator-Schleife for(Typ x: liste)
durchlaufbar sein soll, so muss sie das Interface Iterable
implementieren. Sie muss also iterierbar sein.
Wenn Listen-Elemente mit den üblichen Vergleichsrelationen
vergleichbar sein sollen (z.B. für eine Sortierung), so muß deren Klasse
das Interface Comparable implementieren.

Generische Klassen (Generics) Standard-Interfaces der Java-API für Generics Prof. Dr. Ute Matecki 559
Wichtige Standard-Interfaces der Java-API für Generics
Interessant ist für Generics unter anderem ...
Wenn eine Generic mit der Iterator-Schleife for(Typ x: liste)
durchlaufbar sein soll, so muss sie das Interface Iterable
implementieren. Sie muss also iterierbar sein.
Wenn Listen-Elemente mit den üblichen Vergleichsrelationen
vergleichbar sein sollen (z.B. für eine Sortierung), so muß deren Klasse
das Interface Comparable implementieren.
Comparable ist selbst ein generisches Interface – also eine Generic.

