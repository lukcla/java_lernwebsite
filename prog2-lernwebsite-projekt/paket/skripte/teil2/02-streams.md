# Skript-Rohtext Teil 2: Einstieg Streams (Skript S. 513–543)

Programmierung 2
Einstieg Streams

Einstieg Streams Prof. Dr. Ute Matecki 513
Vorwort
Programmieren im Großen – Packages (Pakete)
Einstieg Streams
Stream-Konzept in Java
Dateizugri mit einfachen, zeichenorientierten Streams
Klassenzoo der Streams in Java
———– Ende Teil 1 (ITS/TI/WIN) —————-
———– Start Teil 2 (WIN) ———————-
Dateizugri mit einfachen, byteorientierten Streams
Verarbeitung von Java-Objekten mit Streams
Konzept von ObjectOutputStream und ObjectInputStream
Anwendungsbeispiel Objektserialisierung/-deserialisierung

Einstieg Streams Prof. Dr. Ute Matecki 514
Generische Klassen (Generics)
Annotationen
Threads

Einstieg Streams Dateizugri mit einfachen, byteorientierten Streams Prof. Dr. Ute Matecki 515
Bisher bekannte Aspekte zum Thema Streams
Bisher behandelt:
Stream-Verschachtelungskonzept

Einstieg Streams Dateizugri mit einfachen, byteorientierten Streams Prof. Dr. Ute Matecki 515
Bisher bekannte Aspekte zum Thema Streams
Bisher behandelt:
Stream-Verschachtelungskonzept
Einfache, zeichenorientierte Streams
- Streams zum zeichenorientierten Lesen waren von der Klasse Reader abgeleitet.
- Streams zum zeichenorientierten Schreiben waren von der Klasse Writer abgeleitet.

Einstieg Streams Dateizugri mit einfachen, byteorientierten Streams Prof. Dr. Ute Matecki 515
Bisher bekannte Aspekte zum Thema Streams
Bisher behandelt:
Stream-Verschachtelungskonzept
Einfache, zeichenorientierte Streams
- Streams zum zeichenorientierten Lesen waren von der Klasse Reader abgeleitet.
- Streams zum zeichenorientierten Schreiben waren von der Klasse Writer abgeleitet.
Übersicht über den Klassenzoo der Java-Streams

Einstieg Streams Dateizugri mit einfachen, byteorientierten Streams Prof. Dr. Ute Matecki 516
Weitere Fragestellungen zum Thema Streams?
Noch nicht behandelt:
Wie werden Binärdateien (beispielsweise Bilder) behandelt?
- Streams zum byteorientierten Lesen sind von der Klasse InputStream abgeleitet.
- Streams zum byteorientierten Schreiben sind von der Klasse OutputStream
abgeleitet.
Wie werden ganze Objekte mit Streams verarbeitet?

Einstieg Streams Dateizugri mit einfachen, byteorientierten Streams Prof. Dr. Ute Matecki 517
Binärstreams – Beispielprogramm
Beispiel: Ein kleines Kopierprogramm
KlassenName: KopiereBin
Aufruf des Programms:
java KopiereBin dateiVon dateiNach

Einstieg Streams Dateizugri mit einfachen, byteorientierten Streams Prof. Dr. Ute Matecki 518
Binärstreams – Arbeitsweise des Beispielprogramms
. . .
DataInputStream quelle
quelle.read( dateibytes )
dateibytes: 4 Bytes groß
. . .
senke.write(4,0, dateibytes )
0
DataOutputStream senke

Einstieg Streams Dateizugri mit einfachen, byteorientierten Streams Prof. Dr. Ute Matecki 519
Binärstreams – Beispielprogramm
Beispiel: Klasse KopiereBin
1 import java.io.*; // Alle Klassen aus java.io
2 public class KopiereBin {
3
4 public static void main(String[] args)
5 throws IOException {
6
7 // Puffer, um 4 Bytes auf einen Schlag
8 // zu verarbeiten
9 byte [] dateibytes = new byte [4];
:Methode main() wir Exceptions einfach weiter.

Einstieg Streams Dateizugri mit einfachen, byteorientierten Streams Prof. Dr. Ute Matecki 520
Binärstreams – Beispielprogramm
Beispiel: Klasse KopiereBin
10 // Stream zum Einlesen oeffnen
11 DataInputStream quelle =
12 new DataInputStream(
13 new FileInputStream( args[0] ));
14
15 // Stream zum Herausschreiben oeffnen
16 DataOutputStream senke =
17 new DataOutputStream(
18 new FileOutputStream( args[1] ));
:Aufruf: java KopiereBin dateiAlt dateiNeu

Einstieg Streams Dateizugri mit einfachen, byteorientierten Streams Prof. Dr. Ute Matecki 521
Binärstreams – Beispielprogramm
Beispiel: Klasse KopiereBin
19 int anzBytes; // Wie viele Bytes haben wir bekommen?
20 int abWo = 0; // ab wo vom Array abspeichern? (offset)
21
22 // Kopier-Algorithmus
23 while ((anzBytes = quelle.read(dateibytes)) != -1) {
24 senke.write(dateibytes,abWo, anzBytes);
25 }
:Methode quelle.read(...) gibt -1 zurück, wenn das Ende der Datei / des
Streams erreicht ist.

Einstieg Streams Dateizugri mit einfachen, byteorientierten Streams Prof. Dr. Ute Matecki 522
Binärstreams – Beispielprogramm
Beispiel: Klasse KopiereBin
26 // Schliessen der Streams
27 quelle.close();
28 senke.close();
29
30 } // end main()
31 } // end class
:Streams müssen nach Gebrauch wieder geschlossen werden.
Achtung: Wenn der Schreib-Stream nicht geschlossen wird, so ist die
kopierte Datei leer oder unvollständig!
(Bei Programmende werden sie zwar geschlossen – aber nicht alle
Programme laufen so kurz wie dieses!

Einstieg Streams Dateizugri mit einfachen, byteorientierten Streams Prof. Dr. Ute Matecki 523
Binärstreams – Zusammenfassung
Binärstreams werden genutzt ...
... um nicht-textorientierte Daten, wie beispielsweise Bild- oder
Videodaten zu verarbeiten.

Einstieg Streams Dateizugri mit einfachen, byteorientierten Streams Prof. Dr. Ute Matecki 523
Binärstreams – Zusammenfassung
Binärstreams werden genutzt ...
... um nicht-textorientierte Daten, wie beispielsweise Bild- oder
Videodaten zu verarbeiten.
Sie sind abgeleitet von den Klassen InputStream (zum Lesen) bzw.
OutputStream (zum Schreiben).

Einstieg Streams Dateizugri mit einfachen, byteorientierten Streams Prof. Dr. Ute Matecki 523
Binärstreams – Zusammenfassung
Binärstreams werden genutzt ...
... um nicht-textorientierte Daten, wie beispielsweise Bild- oder
Videodaten zu verarbeiten.
Sie sind abgeleitet von den Klassen InputStream (zum Lesen) bzw.
OutputStream (zum Schreiben).
Sie werden – ähnlich wie die zeichenorientierten Streams – nach Bedarf
bei der Erzeugung so verschachtelt, dass sie von der gewünschten
Datenquelle lesen / auf die gewünschte Datensenke schreiben.

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 524
Objekte verarbeiten mit Streams
Die Klassen ObjectInputStream und ObjectOutputStream ...
... sind in der Lage, ganze Java-Objekte (beispielsweise Objekte vom Typ
Person) als Einheit zu lesen/zu schreiben.

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 524
Objekte verarbeiten mit Streams
Die Klassen ObjectInputStream und ObjectOutputStream ...
... sind in der Lage, ganze Java-Objekte (beispielsweise Objekte vom Typ
Person) als Einheit zu lesen/zu schreiben.
Diese Lese-/Schreib-Vorgänge werden als Byte-Sequenz vorgenommen.

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 524
Objekte verarbeiten mit Streams
Die Klassen ObjectInputStream und ObjectOutputStream ...
... sind in der Lage, ganze Java-Objekte (beispielsweise Objekte vom Typ
Person) als Einheit zu lesen/zu schreiben.
Diese Lese-/Schreib-Vorgänge werden als Byte-Sequenz vorgenommen.
Daher nennen wir den Schreibvorgang auch serialisieren.

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 524
Objekte verarbeiten mit Streams
Die Klassen ObjectInputStream und ObjectOutputStream ...
... sind in der Lage, ganze Java-Objekte (beispielsweise Objekte vom Typ
Person) als Einheit zu lesen/zu schreiben.
Diese Lese-/Schreib-Vorgänge werden als Byte-Sequenz vorgenommen.
Daher nennen wir den Schreibvorgang auch serialisieren.
Den Lesevorgang bezeichnen wir als deserialisieren.

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 525
Objekte verarbeiten mit Streams
Die Klassen ObjectInputStream und ObjectOutputStream ...
So können wir beispielsweise Dateien erzeugen, die den Inhalt einer
Liste von Objekten enthalten.

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 525
Objekte verarbeiten mit Streams
Die Klassen ObjectInputStream und ObjectOutputStream ...
So können wir beispielsweise Dateien erzeugen, die den Inhalt einer
Liste von Objekten enthalten.
Diese Objekte können dann wieder als zusammenhängende Einheiten
eingelesen werden.

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 525
Objekte verarbeiten mit Streams
Die Klassen ObjectInputStream und ObjectOutputStream ...
So können wir beispielsweise Dateien erzeugen, die den Inhalt einer
Liste von Objekten enthalten.
Diese Objekte können dann wieder als zusammenhängende Einheiten
eingelesen werden.
Klassen, deren Objekte serialisierbar sein sollen, müssen das leere
Interface Serializable implementieren!

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 525
Objekte verarbeiten mit Streams
Die Klassen ObjectInputStream und ObjectOutputStream ...
So können wir beispielsweise Dateien erzeugen, die den Inhalt einer
Liste von Objekten enthalten.
Diese Objekte können dann wieder als zusammenhängende Einheiten
eingelesen werden.
Klassen, deren Objekte serialisierbar sein sollen, müssen das leere
Interface Serializable implementieren!
Daran erkennt Java, dass auf diese Objekte Methoden der Klassen
ObjectInputStream und ObjectOutputStream anwendbar sind!

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 526
Objekte verarbeiten mit Streams – Konzept
Serialisieren von Objekten – ObjectOutputStream
. . . Java-Objekt
Umformatierung und Ausgabe als Bytestrom =
 Serialisierung

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 527
Objekte verarbeiten mit Streams – Konzept
Deserialisieren von Objekten – ObjectInputStream
. . . . . .
Java-Objekt
Umformung und Wieder-Einlesen eines
Bytestromes in ein Java-Objekt = 
 Deserialisierung

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 528
Anwendungsbeispiel: Fahrtenbuch
Klasse für zu serialisierende Objekte: BenzinVerbrauch
BenzinVerbrauch
Jede Java-Klasse erbt direkt
oder indirekt von Klasse Object:
Benzinverbrauch IST Object!
BenzinVerbrauch implementiert
das Interface Serializable.
Daher können seine Objekte mit
ObjectInputStream/ObjectOutputStream
gelesen/geschrieben werden.
-literGetankt: double
-euroBezahlt: double
-datum: String
-kmStand: int
+BenzinVerbrauch(literGetankt: double, euroBezahlt: double, datum: String, kmStand: int)
+print(): void
Object Serializable
«Interface»

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 529
Anwendungsbeispiel: Fahrtenbuch
Klasse für zu serialisierende Objekte: BenzinVerbrauch
Objekte von Klasse BenzinVerbrauch werden auf Datei serialisiert –
Fahrtenbuch abspeichern!

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 529
Anwendungsbeispiel: Fahrtenbuch
Klasse für zu serialisierende Objekte: BenzinVerbrauch
Objekte von Klasse BenzinVerbrauch werden auf Datei serialisiert –
Fahrtenbuch abspeichern!
Objekte von Klasse BenzinVerbrauch werden von Datei deserialisiert –
Fahrtenbuch einlesen!

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 530
Objektstreams – Beispielprogramm
Beispiel: Klasse BenzinVerbrauch
1 import java.io.Serializable;
2
3 public class BenzinVerbrauch implements Serializable {
4 private double literGetankt;
5 private double euroBezahlt;
6 private String datum;
7 private int kmStand;
Attribute der Klasse

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 531
Objektstreams – Beispielprogramm
Beispiel: Klasse BenzinVerbrauch
8 public BenzinVerbrauch(double literGetankt,
9 double euroBezahlt, String datum, int kmStand) {
10 this.literGetankt = literGetankt;
11 this.euroBezahlt = euroBezahlt;
12 this.datum = datum;
13 this.kmStand = kmStand;
14 } // end constructor
Konstruktor der Klasse

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 532
Objektstreams – Beispielprogramm
Beispiel: Klasse BenzinVerbrauch
15 public void print(){
16 System.out.println("Getankt: " + literGetankt);
17 System.out.println("Bezahlt: " + euroBezahlt);
18 System.out.println("Datum: " + datum);
19 System.out.println("Kilometerstand: " + kmStand);
20 } // end method
21 } // end class
Sehr vereinfacht aufgebaut: nur eine print()-Methode, keine getter/setter!

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 533
Objektstreams – Beispielprogramm
Beispiel: Klasse FahrtenBuchObjectStreams
1 import java.io.*;
2
3 public class FahrtenBuchObjectStreams {
4
5 public static void main(String [] args) {
6
7 // Anzahl der Datensaetze: 2 Stueck
8 int anzahlSchreiben=2, anzahlLesen;
9
10 // Array anlegen fuer zwei Eintraege
11 BenzinVerbrauch [] fahrtenbuch1 =
12 new BenzinVerbrauch[anzahlSchreiben];
Array für 2 Objekte anlegen

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 534
Objektstreams – Beispielprogramm
Beispiel: Klasse FahrtenBuchObjectStreams
13 // Zwei Test-Objekte fuer Verbrauchs14 // eintraege anlegen
15 fahrtenbuch1[0] =
16 new BenzinVerbrauch(
17 50.0, 70.0,"12.02.2018", 10000);
18 fahrtenbuch1[1] =
19 new BenzinVerbrauch(
20 50.0, 75.0,"14.02.2018", 10700);
2 Objekte erzeugen und deren Referenzen ins Array hängen

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 535
Objektstreams – Beispielprogramm
Beispiel: Klasse FahrtenBuchObjectStreams – Serialisierungsvorgang
21 try {
22 // Erzeuge OutputStream fuer Fahrtenbuch
23 ObjectOutputStream out =
24 new ObjectOutputStream(
25 new FileOutputStream("Fahrtenbuch.tmp"));
ObjectOutputStreamfür’s Schreiben des Fahrtenbuches erzeugen

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 536
Objektstreams – Beispielprogramm
Beispiel: Klasse FahrtenBuchObjectStreams
26 // Wie viele Eintraege folgen?
27 out.writeInt(anzahlSchreiben);
28
29 for(int i=0; i< anzahlSchreiben; i++) {
30 // Testausgabe auf Bildschirm
31 fahrtenbuch1[i].print();
32
33 // "Echte" Ausgabe auf Datei
34 out.writeObject(fahrtenbuch1[i]);
35 } // end for
36
37 out.close(); // Schliesse Stream
Algorithmus zum Serialisieren der Objekte auf Datei

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 537
Objektstreams – Beispielprogramm
Schreiben in FahrtenBuchObjectStreams – Dateiformat nach der Serialisierung
Schreibvorgang auf Datei:
Der int-Wert und die beiden Objekte werden in Byte-Sequenzen serialisiert
anzahl1
50.0
70.0
"12.02.2018"
10000
Objekt 0 {
. . . . . .
50.0
75.0
"14.02.2018"
10700
Objekt 1 {
2

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 538
Objektstreams – Beispielprogramm
Beispiel: Klasse FahrtenBuchObjectStreams
38 // Nun testen wir, ob wir die Datei
39 // wieder aufschluesseln koennen
40 ObjectInputStream in =
41 new ObjectInputStream(
42 new FileInputStream("Fahrtenbuch.tmp"));
ObjectInputStream für’s Lesen des Fahrtenbuches erzeugen

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 539
Objektstreams – Beispielprogramm
Beispiel: Klasse FahrtenBuchObjectStreams
43 //Anzahl der Objekte in Datei ermitteln
44 anzahlLesen = in.readInt();
45
46 //neues Fahrtenbuch-Array anlegen
47 BenzinVerbrauch [] fahrtenbuch2
48 = new BenzinVerbrauch[anzahlLesen];
Anzahl zu lesender Objekte ermitteln und Array erzeugen

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 540
Objektstreams – Beispielprogramm
Beispiel: Klasse FahrtenBuchObjectStreams
49 // Objekte wieder aus der Datei lesen. Schlaegt fehl,
50 // wenn die Klasse BenzinVerbrauch nicht gefunden wird.
51 for(int i=0; i< anzahlLesen; i++) {
52
53 // "Echtes" Einlesen vom Stream
54 fahrtenbuch2[i] = (BenzinVerbrauch) in.readObject();
55 // Testausgabe auf Bildschirm
56 fahrtenbuch2[i].print();
57 }// end for
58 in.close();
59 } // end try
Einlese-Algorithmus benötigt TypeCast, da readObject() eine Referenz vom
Typ Object zurückgibt.

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 541
Objektstreams – Beispielprogramm
Beispiel: Klasse FahrtenBuchObjectStreams
70 catch (IOException | ClassNotFoundException e) {
71 e.printStackTrace();
72
73 } // end catch
74 }// end main
75 } // end class
ClassNotFoundException wird geworfen, falls im Programm die Klasse
BenzinVerbrauch nicht existiert oder in einem anderen Package liegt (kommt
noch).

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 542
Objektstreams – Beispielprogramm
Hinweis zu readObject() / writeObject()
Beide Methoden kÃ¶nnen ggf. in einer abgeleiteten Streamklasse
Ã¼berschrieben werden.
ClassNotFoundException wird geworfen, falls im Programm die Klasse
BenzinVerbrauch nicht existiert oder in einem anderen Package liegt (kommt
noch).

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 543
Zusammenfassung ObjectInputStream und ObjectOutputStream
Wir merken uns zum Thema Serialisieren/Deserialisieren von Objekten
Mit einem ObjectOutputStream können Objekte beliebiger Java-Klassen
serialisiert werden. Eine solche Serialisierung geschieht häufig auf
Datei.

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 543
Zusammenfassung ObjectInputStream und ObjectOutputStream
Wir merken uns zum Thema Serialisieren/Deserialisieren von Objekten
Mit einem ObjectOutputStream können Objekte beliebiger Java-Klassen
serialisiert werden. Eine solche Serialisierung geschieht häufig auf
Datei.
Mit einem ObjectInputStream können Objekte beliebiger Java-Klassen
deserialisiert werden – also wieder eingelesen werden.

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 543
Zusammenfassung ObjectInputStream und ObjectOutputStream
Wir merken uns zum Thema Serialisieren/Deserialisieren von Objekten
Mit einem ObjectOutputStream können Objekte beliebiger Java-Klassen
serialisiert werden. Eine solche Serialisierung geschieht häufig auf
Datei.
Mit einem ObjectInputStream können Objekte beliebiger Java-Klassen
deserialisiert werden – also wieder eingelesen werden.
Klassen, deren Objekte mit diesen Streams behandelt werden sollen,
müssen das leere Interface Serializable implementieren.

Einstieg Streams Verarbeitung von Java-Objekten mit Streams Prof. Dr. Ute Matecki 543
Zusammenfassung ObjectInputStream und ObjectOutputStream
Wir merken uns zum Thema Serialisieren/Deserialisieren von Objekten
Mit einem ObjectOutputStream können Objekte beliebiger Java-Klassen
serialisiert werden. Eine solche Serialisierung geschieht häufig auf
Datei.
Mit einem ObjectInputStream können Objekte beliebiger Java-Klassen
deserialisiert werden – also wieder eingelesen werden.
Klassen, deren Objekte mit diesen Streams behandelt werden sollen,
müssen das leere Interface Serializable implementieren.
Beim Einlesen serialisierter Objekte gilt: Falls die Klasse, auf die wir
casten, in unserem Projekt nicht existiert, so wird eine
ClassNotFoundException geworfen!

2
• © Prof. Dr. Ute Matecki
Fakultät Informatik
