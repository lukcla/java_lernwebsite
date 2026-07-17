# Skript-Rohtext: Einstieg Streams (Skript S. 436–455)

2
• © Prof. Dr. Ute Matecki
Fakultät Informatik
Programmierung 2
Einstieg Streams

Einstieg Streams Prof. Dr. Ute Matecki 436
Vorwort
Einstieg in Java
Einstieg in die OOP: Klassen und Objekte/Instanzen
Die Klasse String
Graphische Darstellung von Klassen mit der UML – Teil 1
Vererbungsbeziehungen
Exceptions

Einstieg Streams Prof. Dr. Ute Matecki 437
Einstieg Streams
Stream-Konzept in Java
Dateizugri mit einfachen, zeichenorientierten Streams
Klassenzoo der Streams in Java

Einstieg Streams Prof. Dr. Ute Matecki 438
Ein- und Ausgabe bisher: Scanner ...
... ermöglichte Tastatur-Eingaben
1 import java.util.Scanner;
2
3 public class ScannerInput {
4
5 public static void main(String[] args) {
6 Scanner tastatur = new Scanner(System.in);
7 System.out.print("Bitte eine Eingabe: ");
8 String input = tastatur.next();
9 System.out.println("Ihre Eingabe: " + input);
10 } // end main()
11 } // end class
Nutzereingabe erfolgt über Klasse Scanner ...

Einstieg Streams Stream-Konzept in Java Prof. Dr. Ute Matecki 439
Ein- und Ausgabe neu: Streams
... ermöglichen auch Tastatureingaben ...
1 import java.io.*; // Alle Klassen aus java.io
2 public class StreamInput {
3
4 public static void main(String[] args)
5 throws IOException {
6 BufferedReader console =
7 new BufferedReader(new InputStreamReader(System.in));
8 System.out.print("Bitte eine Eingabe: ");
9 String input = console.readLine();
10 System.out.println("Ihre Eingabe: " + input);
11 } // end main()
12 } // end class
Nutzereingabe erfolgt über Klasse BueredReader ...

Einstieg Streams Stream-Konzept in Java Prof. Dr. Ute Matecki 440
Ein- und Ausgabe neu: Streams
Visualisierung des Stream-Konzepts für die obige Tastatureingabe
95
System.in
57 53 10
Tastatur
Eingabe auf der
Tastatur:
95 <Enter>
BufferedReader-Objekt
console
9 5 \n
String-Objekt input
System.out Ausgabe auf dem
Bildschirm:
Eine Zeile mit
95 
9 5 
9 5 \n
9 5 \n
InputStreamReaderObjekt
nimmt Bytes aus dem
Tastaturpuffer entgegen
konvertiert Bytes in
Zeichen
kann Zeichenfolgen zeilenweise verarbeiten
gibt Bytes des Strings als
Zeichen auf die Konsole aus

Einstieg Streams Stream-Konzept in Java Prof. Dr. Ute Matecki 441
Ein- und Ausgabe neu: Streams
Abschnittsweise Interpretation des Programms
1 import java.io.*;
2 public class StreamInput {
3
4 public static void main(String[] args)
5 throws IOException {
6 BufferedReader console =
7 new BufferedReader(new InputStreamReader(System.in));
8 System.out.print("Bitte eine Eingabe: ");
9 String input = console.readLine();
10 System.out.println("Ihre Eingabe: " + input);
11 } // end main()
12 } // end class
Einbinden aller Klassen aus Package java.io

Einstieg Streams Stream-Konzept in Java Prof. Dr. Ute Matecki 442
Ein- und Ausgabe neu: Streams
Abschnittsweise Interpretation des Programms
1 import java.io.*; // Alle Klassen aus java.io
2 public class StreamInput {
3
4 public static void main(String[] args)
5 throws IOException {
6 // Rest wie vorher ...
Methoden der Stream-Klassen nutzen Exceptions – diese müssen weiter
verarbeitet werden!

Einstieg Streams Stream-Konzept in Java Prof. Dr. Ute Matecki 443
Ein- und Ausgabe neu: Streams
Abschnittsweise Interpretation des Programms
1 import java.io.*;
2 public class StreamInput {
3
4 public static void main(String[] args)
5 throws IOException {
6 BufferedReader console =
7 new BufferedReader(new InputStreamReader(System.in)) ;
8 // Rest wie vorher ...
Streams werden so verschachtelt, dass
Daten aus der gewünschten Datenquelle (hier: Tastatur)
in der gewünschten Weise konvertiert werden (hier: zeichenorientiert
mit InputStreamReader und zeilenweise mit BufferedReader)

Einstieg Streams Stream-Konzept in Java Prof. Dr. Ute Matecki 444
Ein- und Ausgabe neu: Streams
Abschnittsweise Interpretation des Programms
1 import java.io.*; // Alle Klassen aus java.io
2 public class StreamInput {
3
4 public static void main(String[] args)
5 throws IOException {
6 BufferedReader tastatur =
7 new BufferedReader(new InputStreamReader(System.in));
8 System.out.print("Bitte eine Eingabe: ");
9 String input = tastatur.readLine() ;
10 System.out.println("Ihre Eingabe: " + input);
11 } // end main()
12 } // end class
BufferedReader verarbeitet Eingabe zeilenweise ...

Einstieg Streams Stream-Konzept in Java Prof. Dr. Ute Matecki 445
Ein- und Ausgabe neu: Streams...
... können auch:
Ein- und Ausgaben aus beliebigen Datenquellen / Datensenken
verarbeiten (z.B. Dateien, Netzwerkverbindungen)
Java unterscheidet zwischen:
- Ein- und Ausgabe-Streams, sowie
- zwischen zeichen- und byteorientierten Streams.

Einstieg Streams Stream-Konzept in Java Prof. Dr. Ute Matecki 446
Ein- und Ausgabe neu: Streams
Vorgehen Nutzung von Streams
Klassen aus Package java.io einbinden mit:
import java.io.*;
Stream-Konstruktoren und Stream-Methoden nutzen das
Exception-Konzept sehr intensiv. Daher:
- Entweder Ihre stream-nutzende Methode wir die entsprechenden Exceptions
weiter, oder
- Sie fängt sie selbst mit try-catch
Vor der Nutzung in der API nachschlagen, welche Methode welche
Exceptions wir!

Einstieg Streams Stream-Konzept in Java Prof. Dr. Ute Matecki 447
Ein- und Ausgabe neu: Streams
Vorgehen Nutzung von Streams
Die Streams so kombinieren, dass beim Lesen:
- aus der gewünschten Datenquelle gelesen wird, und
- die Daten in der gewünschten Art und Weise konvertiert werden.
Die Streams so kombinieren, dass beim Schreiben:
- auf die gewünschte Datensenke geschrieben wird, und
- die Daten in der gewünschten Art und Weise konvertiert werden.
Die Kombination der Streams erfolgt über geeignete Verschachtelung
der Konstruktoraufrufe – also z.B.
1 BufferedReader datei =
2 new BufferedReader(new FileReader("abc.txt"));

Einstieg Streams Dateizugri mit einfachen, zeichenorientierten Streams Prof. Dr. Ute Matecki 448
Dateizugri mit einfachen, zeichenorientierten Streams
Datei einlesen: Methode dateiEinlesen()
1 import java.io.*; // Alle Klassen aus java.io
2 public class Kopierer {
3
4 public String dateiEinlesen (String dateiname)
5 throws IOException,FileNotFoundException{
6 String input="";
7 String zeile;
8
9 // Datei oeffnen
10 BufferedReader dateileser =
11 new BufferedReader( new FileReader(dateiname) );
Datenquelle ist nun eine textorientierte Datei.

Einstieg Streams Dateizugri mit einfachen, zeichenorientierten Streams Prof. Dr. Ute Matecki 449
Dateizugri mit einfachen, zeichenorientierten Streams
Datei einlesen: Methode dateiEinlesen()
12 // Datei auslesen
13 while ( (zeile=dateileser.readLine()) != null ) {
14 input+=zeile + "\n";
15 } // end while
Methode readLine() liefert Zeilen-Inhalt als String
Zuweisung wird zuerst durchgeführt, erst danach der Vergleich mit !=
Wenn die Datei zu Ende ist, liefert readLine() eine null-Referenz.
Methode readLine() schneidet Zeilenumbruch "\n " ab, daher wird er
wieder angefügt

Einstieg Streams Dateizugri mit einfachen, zeichenorientierten Streams Prof. Dr. Ute Matecki 450
Dateizugri mit einfachen, zeichenorientierten Streams
Datei einlesen: Methode dateiEinlesen()
16 dateileser.close() ; // Datei wieder schliessen
17 return input;
18 } // end method dateiEinlesen()
Stream wird wieder geschlossen. Damit wird auch die Datei wieder
geschlossen.

Einstieg Streams Dateizugri mit einfachen, zeichenorientierten Streams Prof. Dr. Ute Matecki 451
Dateizugri mit einfachen, zeichenorientierten Streams
Datei schreiben: Methode dateiSchreiben()
19 public void dateiSchreiben(String dateiname, String inhalt)
20 throws IOException{
21
22 // Datei oeffnen
23 BufferedWriter dateischreiber =
24 new BufferedWriter( new FileWriter(dateiname) );
Datensenke ist nun eine textorientierte Datei

Einstieg Streams Dateizugri mit einfachen, zeichenorientierten Streams Prof. Dr. Ute Matecki 452
Dateizugri mit einfachen, zeichenorientierten Streams
Datei schreiben: Methode dateiSchreiben()
25 // Datei schreiben
26 dateischreiber.write(inhalt) ;
27
28 // Datei wieder schliessen
29 dateischreiber.close();
30 } // end method dateiSchreiben()
Mehrzeiliger String wird „auf einen Schlag“ auf die Datei geschrieben.
Danach wird der Stream (und damit die Datei) wieder geschlossen.

Einstieg Streams Klassenzoo der Streams in Java Prof. Dr. Ute Matecki 453
Zeichenorientierte Streams in Java
BufferedReader
CharArrayReader
FileReader
FilterReader InputStreamReader
PipedReader
PushbackReader
BufferedWriter
CharArrayWriter
LineReader
FileWriter
FilterWriter
LineNumberReader
StringReader
PipedWriter StringWriter OutputStreamWriter
PrintWriter
Reader
Writer
Ausschnitt aus dem
Klassenzoo der
Character-Streams
:Für zeichenorientierte Daten (z.B. Textdateien)

Einstieg Streams Klassenzoo der Streams in Java Prof. Dr. Ute Matecki 454
Byteorientierte Streams in Java InputStream
DataInputStream
FileInputStream FilterInputStream
PipedInputStream
SequenceInputStream
<<interface>>
DataInput
<<interface>>
ObjectInput
BufferedInputStream
ByteArrayInputStream StringBufferInp...
OutputStream
ByteArrayOutputStream
FileOutputStream
PipedOutputStream
FilterOutputStream
BufferedOutputStream DataOutputStream
ObjectOutputStream
<<interface>>
DataOutput
<<interface>>
ObjectOutput
Ausschnitt aus dem
Klassenzoo der
Byte-Streams
ObjectInputStream
:Für byteorientierte Daten (z.B. JPG-Bilder)

Prof. Dr. Ute Matecki 455
Literatur I
[1] GOLL, J. u. a.: Java als erste Programmiersprache. 8. Teubner-Verlag,
2016
[2] OESTEREICH., B.: Analyse und Design mit der UML2.5. 11.
Oldenbourg-Verlag, 2013
[3] ORACLE: The Java-Tutorials – Language Basics.
http://download.oracle.com/javase/tutorial/java/
nutsandbolts/operators.html, 2018
[4] ULLENBOOM, Christian: Java ist auch eine Insel. 12. Rheinwerk Verlag,
2020

