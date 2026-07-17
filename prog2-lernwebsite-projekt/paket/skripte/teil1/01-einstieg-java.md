# Skript-Rohtext: Einstieg in Java (Skript S. 8–161)

2
• © Prof. Dr. Ute Matecki
Fakultät Informatik
Programmierung 2
Einstieg in Java

Einstieg in Java Prof. Dr. Ute Matecki 8
Vorwort
Einstieg in Java
Installationsvoraussetzungen
Programmstruktur – Python vs. Java
Programm-Erzeugung und -Start mit Java
Programm-Erzeugung und -Start auf der Kommandozeile
Programm-Erzeugung und -Start mit der Entwicklungsumgebung Eclipse
Java-API
Variablen, Datentypen und Operatoren
Grundlagen zu Variablenvereinbarungen
Elementare Datentypen in Java
Konstanten bei elementaren Datentypen – final
Aggregierte Datentypen in Java – Referenzdatentypen allgemein
Aggregierte Datentypen in Java – einfache Arrays
Aggregierte Datentypen in Java – Mehrdimensionale Arrays
Aggregierte Datentypen in Java – Strings

Einstieg in Java Prof. Dr. Ute Matecki 9
Aggregierte Datentypen in Java – Klassen
Die null-Referenz
Arithmetische Operatoren und Zuweisung – Python vs. Java
Vergleichsoperatoren und Logische Operatoren: Python vs. Java
Bitweise Operatoren: Python vs. Java
Typkonvertierung in Java
Sichtbarkeit von Variablen – Teil 1
Kontrollstrukturen
Kontrollstrukturen in Java
Fallunterscheidung mit if – else if – else
Fallunterscheidung mit switch–case
Kopfgesteuerte Schleifen – while
Kopfgesteuerte Schleifen – for
Fußgesteuerte Schleifen – do – while
Methoden in Java
Methoden in Java vs. Funktionen in Python
Signatur einer Methode
Aufruf von Methoden und Parameterübergabe
Einstieg in die OOP: Klassen und Objekte/Instanzen

Einstieg in Java Prof. Dr. Ute Matecki 10
Die Klasse String
Graphische Darstellung von Klassen mit der UML – Teil 1
Vererbungsbeziehungen
Exceptions
Einstieg Streams

Einstieg in Java Installationsvoraussetzungen Prof. Dr. Ute Matecki 11
Java Development Kit (JDK)
Bestandteile von Java und Bezug von Java
Das aktuelle JDK enthält unter anderem
den Java-Compiler javac.exe (unter Windows) bzw. javac (unter
Linux) für die Erstellung eines lauähigen Java-Programmes aus Ihrem
Quellcode.
das Java-Runtime-Environment java.exe (unter Windows) bzw. java
(unter Linux) zum Laufenlassen Ihrer compilierten Java-Programme.
Sie finden das aktuelle JDK 13 (freie Version) unter
https://jdk.java.net/
Achtung: Ab Version 11 ist nur noch das OpenJDK oen verfügbar. Bei
den niedrigeren Versionsnummern können Sie noch den alten Pfad bei
Oracle verwenden!

Einstieg in Java Installationsvoraussetzungen Prof. Dr. Ute Matecki 12
Java Development Kit (JDK)
Installation von Java
Unter Windows: Entpacken Sie die heruntergeladene .zip-Datei in
einem Verzeichnis Ihrer Wahl (bei mir z.B. C:\Programme\Java –
Achtung: Geht in diesem Ordner nur mit Admin-Rechten!)
Unter Linux: Entpacken Sie die heruntergeladene tar.gz-Datei in einem
Verzeichnis Ihrer Wahl mit
tar xzf namederdatei.tar.gz
Für beide Betriebssysteme: Fügen Sie den Pfad der ausführbaren
Dateien (bei mir unter Windows z. B.
C:\ProgramFiles\Java\jdk-13.0.2\bin) Ihrer PATH-Variablen hinzu.

Einstieg in Java Installationsvoraussetzungen Prof. Dr. Ute Matecki 13
Entwicklungsumgebung Eclipse
Die Entwicklungsumgebung Eclipse enthält
einen intelligenten Editor mit Eingabe-Unterstützung
(Code-Completion),
automatisierte Programm-Compilation während der Eingabe
komfortable Möglichkeiten, Ihre Programme zu testen, uvm.
Sie finden die aktuelle Version unter www.eclipse.org

Einstieg in Java Programmstruktur – Python vs. Java Prof. Dr. Ute Matecki 14
Programmstruktur Python
1 #!/usr/bin/python
2 # Datei: ProgrammStruktur1.py
3
4 # Eine Variable vereinbaren
5 intWert = 10000
6
7 # Diese Variable ausgeben
8 print "Wert von intWert: ",intWert
Im einfachsten Fall:
Imperatives Programmier -
Paradigma
Abfolge von Statements
Diese werden nacheinander
abgearbeitet

Einstieg in Java Programmstruktur – Python vs. Java Prof. Dr. Ute Matecki 15
Programmstruktur Java
1 // Programmdatei: ProgrammStruktur.java
2 public class ProgrammStruktur {
3
4 // main() ist Start-Methode
5 public static void main(String[] args) {
6 // Anlegen einer Variablen
7 int x = 10;
8
9 // Ausgabe der Variablen
10 System.out.println("Wert x=" + x);
11 } // end method main()
12
13 } // end class

Einstieg in Java Programmstruktur – Python vs. Java Prof. Dr. Ute Matecki 16
Programmstruktur Java
Programmstruktur Java – Klassen
1 // Programmdatei: ProgrammStruktur.java
2 public class ProgrammStruktur {
3 // ... methoden wie zB main()
4 } // end class
Objektorientiertes Programmier - Paradigma
Programm-Datei = Klasse!
Programmdatei muss so heißen wie die Klasse
Programmdatei muss auf .java enden.

Einstieg in Java Programmstruktur – Python vs. Java Prof. Dr. Ute Matecki 17
Programmstruktur Python – Blockbildung durch Einrückung
1 # Deklaration einer Funktion
2 def myfunction():
3 alter=input("Wie alt sind Sie? ")
4 print "Sie sind",alter,"Jahre alt!"
5 # Aufruf der Funktion
6 myfunction()
Kopf eines Blockes wird mit : beendet.
Rumpf eines Blockes wird durch Einrückung kenntlich gemacht.
Diese Art der Einrückung wird von Python erzwungen

Einstieg in Java Programmstruktur – Python vs. Java Prof. Dr. Ute Matecki 18
Programmstruktur Java – Blockbildung durch {}-Klammern
1 // ProgrammStruktur.java
2 public class ProgrammStruktur {
3 // method main()
4 public static void main(String[] args) {
5 // Anlegen einer Variablen
6 int x = 10;
7
8 // Ausgabe der Variablen
9 System.out.println("Wert x=" + x);
10 } // end method main()
11 } // end class

Einstieg in Java Programmstruktur – Python vs. Java Prof. Dr. Ute Matecki 19
Programmstruktur Java – Blockbildung durch {}
Blöcke werden durch geschweie Klammern {} begrenzt.
Einrückung wird von Java nicht erzwungen.
Aber: Es gibt Code-Styleguides, die diese Einrückungen vorschreiben.
→ Nicht Java tritt Ihnen bei Formatierungsfehlern auf die Füße,
sondern Ihr Chef!!

Einstieg in Java Programmstruktur – Python vs. Java Prof. Dr. Ute Matecki 20
Programmstruktur Java – main()-Methode
1 // Programmdatei: ProgrammStruktur.java
2 public class ProgrammStruktur {
3 // main() ist Start-Methode
4 public static void main(String[] args) {
5 // Anlegen einer Variablen
6 int x = 10;
7
8 // Ausgabe der Variablen
9 System.out.println("Wert x=" + x);
10 } // end method main()
11 } // end class

Einstieg in Java Programmstruktur – Python vs. Java Prof. Dr. Ute Matecki 21
Programmstruktur Java – main()-Methode
Java-Programm muss enthalten:
Mindestens eine Klasse mit einer main()-Methode
Von dieser Methode aus werden alle weiteren Statements des
Programms aufgerufen.
Hierbei kann es sich um einfache arithmetische Anweisungen handeln,
aber auch ...
... um Aufrufe von Methoden aus weiteren Java-Klassen.

Einstieg in Java Programmstruktur – Python vs. Java Prof. Dr. Ute Matecki 22
Programmstruktur Java – main()-Methode
Aufbau der main()-Methode
1 public static void main(String[] args) {
2 // ... weitere Statements
3 }
main() bekommt immer ein Array aus Strings übergeben.
Dieses kann eventuelle Aufrufparameter des Programms enthalten.
(Später mehr dazu ...)

Einstieg in Java Programm-Erzeugung und -Start mit Java Prof. Dr. Ute Matecki 23
Programm-Erzeugung auf der Kommandozeile
Eine einzelne Quelldatei
Beispielklasse Hello.java
1 public class Hello {
2 public static void main(String [] args) {
3
4 System.out.println("Hello World!");
5 } // end method main()
6 } // end class Hello
Compileraufruf:
javac Hello.java
Erzeugt aus
Hello.java : Hello.class

Einstieg in Java Programm-Erzeugung und -Start mit Java Prof. Dr. Ute Matecki 24
Programm-Erzeugung auf der Kommandozeile
Mehrere Quelldateien
Mehrere Klassen – jede in einer Quelldatei
Klasse MainClass : Datei MainClass.java
Klasse Eingabe : Datei Eingabe.java
Compileraufruf:
javac *.java
Erzeugt aus
MainClass.java : MainClass.class
Eingabe.java : Eingabe.class

Einstieg in Java Programm-Erzeugung und -Start mit Java Prof. Dr. Ute Matecki 25
Zusammenfassung Programm-Erzeugung und -Start (Konsole)
Merke: Manuelle Erzeugung und Start von Java-Programmen
Jede Java-Klasse (Datei mit Endung .java) muss mit dem Compiler
javac compiliert werden:
javac Dateiname.java
- führt einen Syntax-Check der Quelldatei durch.
- liefert im Erfolgsfall:
Dateiname.java : Dateiname.class
- liefert im Fehlerfall (bei Syntaxfehlern) eine Fehlermeldung mit Zeilenangabe.
Start eines Java-Programms mit der Java-Runtime (Java-VM) java:
java NameDerMainKlasse
startet das Programm von der Konsole aus

Einstieg in Java Programm-Erzeugung und -Start mit Java Prof. Dr. Ute Matecki 26
Programmerzeugung in der Entwicklungsumgebung
Was sind Entwicklungsumgebungen?
Programme mit einer schönen Oberfläche zum
Editieren,
Compilieren und
Starten von Programmen in einer einzigen grafischen
Benutzungsoberfläche.
Keine mühsamen Befehlseingaben mehr – die Oberfläche tut dies für
uns im Hintergrund.

Einstieg in Java Programm-Erzeugung und -Start mit Java Prof. Dr. Ute Matecki 27
Programmerzeugung in der Entwicklungsumgebung
Was sind Entwicklungsumgebungen?
Häufig auch als Integrierte Entwicklungsumgebung bezeichnet:
Die Schritte
- Editieren,
- Compilieren und
- Starten
sind in einer einzigen Oberfläche integriert.
Integrierte Entwicklungsumgebung = Integrated Development
Environment = IDE

Einstieg in Java Programm-Erzeugung und -Start mit Java Prof. Dr. Ute Matecki 28
Programmerzeugung in der Entwicklungsumgebung
Die IDE Eclipse
Eclipse unterstützt viele Programmiersprachen und -paradigmen.
Jede Programmiersprache wird in einer sog. Perspektive dargestellt.
Perspektive = Eigene Oberfläche mit etwas anderem Look-and-Feel

Einstieg in Java Programm-Erzeugung und -Start mit Java Prof. Dr. Ute Matecki 29
Programmerzeugung in der Entwicklungsumgebung
Die IDE Eclipse
In der IDE Eclipse werden Java-Programme in Form von Projekten
organisiert.
Die Projekte werden in einem Workspace angelegt. Hierbei handelt es
sich einfach um ein Arbeitsverzeichnis, welches der Nutzer beim Start
der IDE angibt.
Ein Projekt innerhalb des Workspaces ist wiederum in einem eigenen
Verzeichnisbaum angelegt.

Einstieg in Java Programm-Erzeugung und -Start mit Java Prof. Dr. Ute Matecki 30
Programmerzeugung in der Entwicklungsumgebung
Workspace und Projekte
C:\erna\myworkspace\
Projekt1
ProjektN
.
.
.
Projektverzeichnisse liegen innerhalb
Ihres Workspace. Sie enthalten meist
alle Quelldateien eines Programms
{
{
Workspace = Arbeitsverzeichnis für
 alle Projekte

Einstieg in Java Programm-Erzeugung und -Start mit Java Prof. Dr. Ute Matecki 31
Programmerzeugung in der Entwicklungsumgebung
Start der Entwicklungsumgebung ...
... durch Doppelklick auf’s Eclipse-Icon

Einstieg in Java Programm-Erzeugung und -Start mit Java Prof. Dr. Ute Matecki 32
Programmerzeugung in der Entwicklungsumgebung
Eingeben des Verzeichnisses für den Workspace ...
... und weiter mit Launch.

Einstieg in Java Programm-Erzeugung und -Start mit Java Prof. Dr. Ute Matecki 33
Programmerzeugung in der Entwicklungsumgebung
Beim ersten Start sehen Sie den Welcome-Tab ...
... den Sie wegklicken.

Einstieg in Java Programm-Erzeugung und -Start mit Java Prof. Dr. Ute Matecki 34
Programmerzeugung in der Entwicklungsumgebung
Danach sehen Sie Ihren noch leeren Workspace ...

Einstieg in Java Programm-Erzeugung und -Start mit Java Prof. Dr. Ute Matecki 35
Programmerzeugung in der Entwicklungsumgebung
Erzeugung eines neuen Projektes mit dem Menüpunkt ...
File : New : Other liefert folgenden Wizard:
Wählen Sie Java : Java Project und gehen Sie weiter mit Next.

Einstieg in Java Programm-Erzeugung und -Start mit Java Prof. Dr. Ute Matecki 36
Programmerzeugung in der Entwicklungsumgebung
Vergabe eines Projektnamens ...

Einstieg in Java Programm-Erzeugung und -Start mit Java Prof. Dr. Ute Matecki 37
Programmerzeugung in der Entwicklungsumgebung
Java-Perspektive bestätigen, falls gefragt wird ...

Einstieg in Java Programm-Erzeugung und -Start mit Java Prof. Dr. Ute Matecki 38
Programmerzeugung in der Entwicklungsumgebung
Eine Java-Klasse innerhalb des Projektes anlegen ...
... und nach Anwählen des Projektes über den Menüpunkt File : New :
Other
... und danach Java : Class den Wizard zur Erstellung einer Klasse wählen.

Einstieg in Java Programm-Erzeugung und -Start mit Java Prof. Dr. Ute Matecki 39
Programmerzeugung in der Entwicklungsumgebung
Eine Java-Klasse innerhalb des Projektes anlegen ...

Einstieg in Java Programm-Erzeugung und -Start mit Java Prof. Dr. Ute Matecki 40
Programmerzeugung in der Entwicklungsumgebung
Eine Java-Klasse innerhalb des Projektes anlegen ...

Einstieg in Java Programm-Erzeugung und -Start mit Java Prof. Dr. Ute Matecki 41
Programmerzeugung in der Entwicklungsumgebung
Eine Java-Klasse innerhalb des Projektes anlegen ...

Einstieg in Java Programm-Erzeugung und -Start mit Java Prof. Dr. Ute Matecki 42
Programmerzeugung in der Entwicklungsumgebung
Java-Klasse erscheint im Project-Explorer und im Editier-Feld ...

Einstieg in Java Programm-Erzeugung und -Start mit Java Prof. Dr. Ute Matecki 43
Programmerzeugung in der Entwicklungsumgebung
Java-Klasse bearbeiten und abspeichern ...
: Beim Abspeichern wird der Quelltext bereits automatisch compiliert!

Einstieg in Java Programm-Erzeugung und -Start mit Java Prof. Dr. Ute Matecki 44
Programmerzeugung in der Entwicklungsumgebung
Programm starten ...
: Projekt oder main()-Klasse muss angewählt sein!
: Innerhalb des Projektes sucht die IDE automatisch nach der Klasse mit
der main()-Methode!

Einstieg in Java Programm-Erzeugung und -Start mit Java Prof. Dr. Ute Matecki 45
Zusammenfassung Programm-Erzeugung und -Start (Eclipse-IDE)
Merke: Erzeugung und Start von Java-Programmen in Eclipse
Java-Programme sind in Eclipse in Projekten organisiert.
Beim Abspeichern jeder Java-Klasse innerhalb eines Java-Projektes
wird diese automatisch compiliert.
Syntaxfehler werden direkt beim Editieren im Editor gezeigt. Erst nach
Entfernung dieser Fehler wird beim Abspeichern wieder compiliert.
Der Start eines Java-Programms innerhalb von Eclipse erfolgt mit dem
grünen Start-Pfeil

Einstieg in Java Java-API Prof. Dr. Ute Matecki 46
Die Java-API
Schauen Sie in die API!
Damit ist gemeint:
- Schauen Sie in der Dokumentation von Java nach einer bestimmten Java- Klasse /
Java-Methode.
- Nicht alles muss von Hand selbst programmiert werden.
- Für viele Problemstellungen gibt es Klassen und Algorithmen, die von den
Entwicklern von Java „fix und fertig“ zur Verfügung gestellt werden.
Einstiegslink für viele nützliche Java-Klassen:
https://docs.oracle.com/en/java/javase/11/docs/api/java.
base/java/lang/package-summary.html

Einstieg in Java Java-API Prof. Dr. Ute Matecki 47
Die Java-API
Was bedeutet das Akronym „API“?
Application Programming Interface
Deutsch (genaue Übersetzung): Anwendungs-Programmierschnittstelle.
Meist abgekürzt: Programmierschnittstelle.
Vorgefertigte Klassen/Funktionen.
Diese können von Entwicklern/Entwicklerinnen verwendet werden, um
Anwendungsprogramme zu schreiben.

Einstieg in Java Java-API Prof. Dr. Ute Matecki 48
Die Java-API
Was bedeutet das Akronym „API“?
Etwas allgemeiner:
Vorgefertigte Programmpakete (Bibliotheken), die von
Entwicklern(Entwicklerinnen benutzt werden,
- um eigene Programme zu schreiben, ohne jeden jemals erfundenen Algorithmus
noch mal neu entwickeln zu müssen.
- um eigene Programmteile/Programmpakete an ein bestehendes System
anzubinden.
Diese vorgefertigten Bibliotheken sind häufig standardisiert und haben
eine ausführliche HTML-Dokumentation.

Einstieg in Java Java-API Prof. Dr. Ute Matecki 49
Die Java-API
Und was bedeutet nun „Schauen Sie in die API“??
In unserem Fall: Schauen Sie in die oizielle HTML-Doku von Java nach
bestimmten Klassen oder Funktionen!
Auch für selbstdefinierte Java-Klassen kann eine solche Doku mit dem
Programm javadoc erzeugt werden!
Für Sprachen wie C und C++ gibt es ähnliche Doku-Generatoren (z.B.
doxygen)

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 50
Variablen und Datentypen
Variablenvereinbarung allgemein
Generell können Variablen bei ihrer Vereinbarung
implizit oder
explizit
typisiert werden.
Bei der impliziten Typisierung wird der Datentyp einer Variablen durch die
Wertzuweisung festgelegt (vgl. Python).
Bei der expliziten Typisierung wird der Datentyp einer Variablen direkt bei
der Vereinbarung angegeben – Java!

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 51
Variablenvereinbarung in Java
Eine Variablenvereinbarung erfolgt in Java immer explizit:
Explizite Variablenvereinbarung in Java
datentyp variablenname;

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 52
Grobaueilung von Datentypen
In Java unterscheiden wir
Elementare (Primitive) Datentypen (beispielsweise Ganzzahl- oder
Gleitkommazahlen)
Aggregierte (Zusammengesetzte) Datentypen (z.B. Klassen, Arrays,
Aufzählungen, etc.). Sie werden auch als Referenzdatentypen
bezeichnet, da ihre Variablen immer eine Referenz (Speicheradresse) auf
das eigentliche Datenelement enthalten.
Variablen, deren Datentyp ein Referenzdatentyp ist, werden auch als
Referenzvariablen bezeichnet.

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 53
Elementare Datentypen in Java
Datentyp Beschreibung Vereinbarung
mit Literal
byte
8 Bit-Ganzzahl
Wertebereich -128 . . . 127
Negative Zahlen im Zweierkomplement
byte b=2;
short 16 Bit-Ganzzahl
Wertebereich -32768 . . . 32767
Negative Zahlen im Zweierkomplement
short b=45;

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 54
Elementare Datentypen in Java
Datentyp Beschreibung Vereinbarung
mit Literal
int
32 Bit-Ganzzahl
Wertebereich -2147483648 . . .
2147483647
Negative Zahlen im Zweierkomplement
int b=5;
long 64 Bit-Ganzzahl
Wertebereich −2
63
. . . 2
63 − 1
Ab Java 8 sind auch vorzeichenlose
Ganzzahlen von 0 . . . 2
64 − 1 möglich.
Negative Zahlen im Zweierkomplement
long b=1000L;

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 55
Elementare Datentypen in Java
Datentyp Beschreibung Vereinbarung
mit Literal
char
Länge 16 Bit (Unicode)
Wertebereich ganzzahlig 0 . . . 65535
Das Zeichen A hat hier beispielsweise –
wie in der ASCII-Codierung den Wert 65.
char x='A';
boolean Wahrheitswert
Kann die Werte true oder false
annehmen
boolean b=true ;

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 56
Elementare Datentypen in Java
Datentyp Beschreibung Vereinbarung
mit Literal
float
32 Bit-Gleitkommazahl (IEEE 754)
Wertebereich
±1.4 · 10−45. . . ± 3.4 · 10+38
float b=48.7f;
double
64 Bit-Gleitkommazahl (IEEE 754)
Wertebereich
±4.9 · 10−324. . . ± 1.7 · 10+308
double b=55.7;

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 57
Konstanten (konstante Variablen) in Java
Modifier final für konstante Variablen
wird vor die Variablenvereinbarung geschrieben.
Wirkung: Nach der ersten Wertezuweisung kann kein neuer Wert mehr
an diese Variable zugewiesen werden.

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 58
Beispiel für eine final -Variable
Beispielquelltext
1 final double PI=3.141592653589793;
2 System.out.println("PI: " + PI);
3
4 // Versuch: Aenderung von PI
5 PI=9.0;
Modifier final: Variable kann nach der ersten Zuweisung nicht mehr
geändert werden! Compilerfehler!

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 59
Aggregierte Datentypen in Java
Hier sind unter anderem zu nennen
Arrays
Klassen (kommt später – in diesem Kapitel nur ein kurzes Beispiel)
Eine besondere Klasse ist hier die Klasse String
Interfaces (kommt später)
Collections (z.B. Listen) (kommt später), und einige mehr ...

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 60
Aggregierte Datentypen in Java
Aggregierte Datentypen in Java = Referenzdatentypen!
Eine Variable eines aggregierten Datentyps enthält in Java nicht die
tatsächlichen Werte des Datentyps, sondern nur eine Referenz auf die
Speicherstelle, an der die echten Werte stehen.
Eine Referenz ist eine speziell codierter Wert der Speicheradresse der
tatsächlichen Werte.

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 61
Aggregierte Datentypen in Java – einfache Arrays
Arrays
Ein Array ist eine Datenstruktur, die in der Lage ist, eine feste Anzahl von
Variablen gleichen Typs aufzunehmen.
Die Größe eines Arrays bleibt, nachdem es erzeugt wurde, gleich!

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 62
Aggregierte Datentypen in Java – einfache Arrays
Vereinbarung von Array-Variablen
// Moeglichkeit 1:
datentyp [] array1 = new datentyp [anzahl];
// Moeglichkeit 2:
datentyp [] array2 = {element1, element2, ... , elementN};
Die beiden Variablen array1 und array2 enthalten jeweils nur die
Referenz auf die Speicheradresse, an der die Werte des Arrays beginnen!

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 63
Aggregierte Datentypen in Java – einfache Arrays
Beispiel für ein Array vom Typ int – Möglichkeit 1
1 // Vereinbarung eines int-Arrays mit Platz fuer 4 Elemente
2 int [] myArray = new int [4];
3 // Belegung der Array-Elemente mit Werten
4 myArray[0] = 7;
5 myArray[1] = -99;
6 myArray[2] = 102;
7 myArray[3] = 8;
7 -99 102 8
0 1 2 3 

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 64
Aggregierte Datentypen in Java – einfache Arrays
Beispiel für ein Array vom Typ int – Möglichkeit 2
1 // Vereinbarung eines int-Arrays mit Platz fuer 4 Elemente
2 int [] myArray = {7,-99,102,8};
7 -99 102 8
0 1 2 3 

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 65
Aggregierte Datentypen in Java – einfache Arrays
Laenge eines Arrays feststellen: length-Variable
1 int [] myArray = {7,-99,102,8};
2 System.out.println(
3 "Laenge des Arrays: "+ myArray.length );
Array hat 4 Elemente : Ausgabeanweisung gibt aus:
Laenge des Arrays: 4

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 66
Aggregierte Datentypen in Java – mehrdimensionale Arrays
Vereinbarung mehrdimenstionaler Arrays: Allgemeine Form
1 typ [][] ... arrname = new typ [zeilen][spalten][...]... ;
Für jede Dimension wird bei Vereinbarung und Erzeugung ein
[]-Klammerpaar verwendet!

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 67
Aggregierte Datentypen in Java – mehrdimensionale Arrays
Vereinbarung mehrdimenstionaler Arrays: Eine Matrix
1 int rows=3;
2 int columns=5;
3 int [][] matrix1 = new int [rows][columns];

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 68
Aggregierte Datentypen in Java – mehrdimensionale Arrays
Zugri auf mehrdimensionale Arrays
1 int i=2;
2 int j=3;
3 matrix1[i][j]=255;
4 System.out.println("Position [2][3]: "+matrix1[i][j]);

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 69
Aggregierte Datentypen in Java – Strings
Zeichenketten – Strings
Zeichenfolgen / Zeichenketten werden in Java meist über die Klasse
String vereinbart.
Hierbei handelt es sich um eine Standard-Java-Klasse, die jedoch etwas
einfacher funktioniert, als andere Klassen. Sie wird im Kapitel Die
Klasse String ausführlich behandelt.
In einigen Fällen wird auch die Klasse StringBuffer verwendet.
Falls diese in späteren Phasen der Lehrveranstaltung von Ihnen benötigt
wird, so werden Ihnen Ihre Dozenten die Handhabung zeigen.

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 70
Aggregierte Datentypen in Java – Strings
Einführungsbeispiel zur Vereinbarung von Strings
// Vereinbarung einer Variablen
// vom Typ String
String s1 = "Erna";
// Ausgabe eines mit + verketteten
// Strings
System.out.println("Hallo " + s1);

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 71
Aggregierte Datentypen in Java – Klassen
Vereinbarung von Instanzen einer Klasse
// Wenn der Instanz bei der Erzeugung
// keine Parameter uebergeben werden ...
KlassenName nameRefVariable = new KlassenName();
// Erzeugung einer Instanz mit Parameteruebergabe
KlassenName nameRefVariable = new KlassenName(parameter ...);

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 72
Aggregierte Datentypen in Java – Klassen
Einfaches Beispiel einer Klasse: HelloMessages/Teil 1
1 public class HelloMessages {
2
3 String nachricht; // eine Objektvariable
4
5 // Standard-Konstruktor (immer parameterlos)
6 HelloMessages(){
7 nachricht="Moin";
8 }
9
10 // voll qualifizierter Konstruktor: setzt Instanzvariablen
11 HelloMessages(String nachricht) {
12 this.nachricht = nachricht;
13 } // ... weiter naechste Seite

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 73
Aggregierte Datentypen in Java – Klassen
Einfaches Beispiel einer Klasse: HelloMessages/Teil 2
14 // ... Fortsetzung von der letzten Seite
15 // einfache Methode
16 void hello() {
17 System.out.println(nachricht);
18 } // end method
19
20 } // end class

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 74
Aggregierte Datentypen in Java – Klassen
Einfaches Beispiel einer Klasse: HelloMain/Teil 1
1 public class HelloMain {
2
3 public static void main(String[] args) {
4
5 // Variable vom Referenztyp HelloMessages
6 // Erzeugung Arbeitsobjekt mit Standardkonstruktor
7 HelloMessages worker1 = new HelloMessages();
8
9 // Variable vom Referenztyp HelloMessages
10 // Erzeugung Arbeitsobjekt mit voll qual. Konstruktor
11 HelloMessages worker2 = new HelloMessages("Guten Tag!");
12 // ... Fortsetzung auf der naechsten Seite

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 75
Aggregierte Datentypen in Java – Klassen
Einfaches Beispiel einer Klasse: HelloMain/Teil 2
13 // ... Fortsetzung von der vorherigen Seite
14 // Methodenaufruf bei den Arbeitsobjekten
15 worker1.hello(); // Gibt Standardnachricht aus
16 worker2.hello(); // Gibt uebergebene Nachricht aus
17
18 } // end method main()
19 } // end class
Ausgabe:
moin
Guten Tag!

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 76
Aggregierte Datentypen in Java – null-Referenz
Das Literal null bedeutet:
Variable ist noch nicht mit einer gültigen Adresse initialisiert!
Wird immer dort zur Initialisierung verwendet, wo erst später
entschieden wird, was genau zugewiesen wird.
null ist also ein „Default-Wert“ für einen Referenz-Wert.

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 77
Aggregierte Datentypen in Java – null-Referenz
Beispiel zur null-Referenz: Versuch 1
1 public class NullReferenzVersuch1 {
2
3 public static void main(String[] args) {
4 int [] array;
5
6 array[0] = 5; // Compilerfehler
7
8 } // end method
9 } // end class
nicht initialisiert!
Zuweisung funktioniert nicht – Compilerfehler!

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 78
Aggregierte Datentypen in Java – null-Referenz
Beispiel zur null-Referenz: Versuch 2
1 public class NullReferenzVersuch2 {
2
3 public static void main(String[] args) {
4 int [] array = null;
5
6 array[0] = 5;
7
8 } // end method
9 } // end class
Referenz ist jetzt mit null initialisiert!
Compiler sagt zwar: OK!
Es entsteht jedoch ein Laufzeitfehler beim Start des Programms, da der
Variablen immer noch keine gültige Speicheradresse zugewiesen wurde.

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 79
Aggregierte Datentypen in Java – null-Referenz
Beispiel zur null-Referenz: Versuch 3 / Teil 1
1 import java.util.Scanner;
2
3 public class NullReferenzVersuch3 {
4
5 public static void main(String[] args) {
6 int [] array = null;
7 Scanner eingabe = new Scanner(System.in);
8
9 System.out.print("Anzahl Elemente? ");
10 int anzahl = eingabe.nextInt();
Referenz ist jetzt mit null initialisiert!
Rest auf der nächsten Folie ...

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 80
Aggregierte Datentypen in Java – null-Referenz
Beispiel zur null-Referenz: Versuch 3 / Teil 1
11 // Achtung: anzahl <= 0 wurde nicht abgefangen!
12 array = new int [anzahl];
13
14 if (array != null) {
15 array [0] = -99;
16 } // end if
:Referenzvariable array wird auf null getestet, bevor der
Speicherplatz an Position 0 belegt wird!

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 81
Zusammenfassung zur null-Referenz
Die null-Referenz wird verwendet ...
... um Referenzvariablen (z.B. Arrays, Referenzen auf Objekte einer
Klasse, etc.) zu initialisieren, sofern die echte Initialisierung später
stattfinden soll.
null wird auch häufig von Methoden zurückgegeben, deren
Rückgabetyp ein Referenzdatentyp ist: Dann, wenn ihnen eine
Erzeugung der Referenzvariablen mit new fehlgeschlagen ist. Dazu
später mehr!

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 82
Bereits bekannte arithmetische Operatoren aus Python ...
... sehen in Java genau gleich aus!
Python-Operator Java-Operator Erläuterung
+ + Addition
- - Subtraktion
* * Multiplikation
/ / Division
% % Division mit Rest
+= -= *= /= %= += -= *= /= %= Zuweisungsoperatoren für arithmetische Operationen

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 83
Neu eingeführte arithmetische Operatoren in Java
Inkrement- und Dekrement-Operatoren
Operator Erläuterung
++ Inkrement-Operator: Zählt eine Variable um 1 hoch
-- Dekrement-Operator: Zählt eine Variable um 1 herunter

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 84
Neu eingeführte arithmetische Operatoren in Java
Inkrement- und Dekrement-Operatoren
Grundform Inkrement/Dekrement
1 int i=22;
2 int j=100;
3
4 i++; // i hat nach dieser Anweisung den Wert 23
5 j--; // j hat nach dieser Anweisung den Wert 99

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 85
Neu eingeführte arithmetische Operatoren in Java
Inkrement- und Dekrement-Operatoren
Pre-Inkrement und -Dekrement
: Erst die Inkrement-/Dekrement-Anweisung ausführen, danach die
Zuweisung:
1 int i=22;
2 int j=100;
3
4 // Nach diesem Statement: m hat den Wert 23;
5 // i hat den Wert 23
6 int m = ++i;
7
8 // Nach diesem Statement: n hat den Wert 99;
9 // j hat den Wert 99
10 int n = --j;

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 86
Neu eingeführte arithmetische Operatoren in Java
Inkrement- und Dekrement-Operatoren
Post-Inkrement und -Dekrement
: Erst die Zuweisung ausführen, danach die
Inkrement-/Dekrement-Anweisung:
1 int i=22;
2 int j=100;
3
4 // Nach diesem Statement: m hat den Wert 22;
5 // i hat den Wert 23
6 int m = i++;
7
8 // Nach diesem Statement: n hat den Wert 100;
9 // j hat den Wert 99
10 int n = j--;

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 87
Operatoren in Kontrollstrukturen
Für die Abfragen der Bedingungen innerhalb von Fallunterscheidungen und
Schleifen benötigen wir:
Vergleichsoperatoren
logische Operatoren

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 88
Bereits bekannte Vergleichsoperatoren aus Python ...
... sehen in Java genau gleich aus!
Python-Vergleichsoperator Java-Vergleichsoperator Erläuterung
a < b a < b kleiner
a <= b a <= b kleiner gleich
a == b a == b gleich
a != b a != b ungleich
a >= b a >= b grösser gleich
a > b a > b grösser

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 89
Bereits bekannte, logische Operatoren aus Python ...
... sehen in Java etwas anders aus:
Python-Operator Java-Operator Erläuterung
a or b a || b Oder (In Java: Kurzschlussoperator; b wird nur ausgewertet,
wenn a false ist.)
a or b a | b Oder
a and b a && b Und (In Java: Kurzschlussoperator; b wird nur ausgewertet,
wenn a true ist.)
a and b a & b Und
not a !a Negation

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 90
Bereits bekannte Bitoperatoren aus Python ...
... sehen in Java fast gleich aus!
Python-Bitoperation Java-Bitoperation Erläuterung
a & b a & b Bitweises Und von zwei
Ganzzahl-Variablen
a | b a | b Bitweises Oder von zwei
Ganzzahl-Variablen
a ^ b a ^ b Bitweises Exklusiv-Oder
zweier Ganzzahl-Variablen
~a ~a Bitweise Negation (Einerkomplement) einer
Ganzzahl-Variablen

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 91
Bereits bekannte Bitoperatoren aus Python ...
... sehen in Java fast gleich aus!
Python-Bitoperation Java-Bitoperation Erläuterung
a >> n a >> n Vorzeichenerhaltender
Rechtsshi von a um n Bits
a << n a << n Linksshi von a um n Bits
nicht vorhanden a >>> n Vorzeichenloser Rechtsshi von a um n Bits (es
werden immer 0en nachgeschoben) :gibt es nur in
Java, nicht in Python

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 92
Typkonvertierung in Java
Begri Typkonvertierung / Typecast
Wir haben gelernt: In Java erfolgt die Typisierung von Variablen explizit.
Bisher: Verwendung von Operatoren nur bei gleichtypigen Operanden.
Frage: Was, wenn wir beispielsweise einen double-Operanden mit
einem int-Operanden multiplizieren müssen?

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 93
Typkonvertierung in Java
Zwei Arten der Typkonvertierung
Implizite Typkonvertierung: Wird von Java automatisch durchgeführt.
Nur möglich, wenn wir von klein :groß konvertieren.
Explizite Typkonvertierung: Hier geben wir den gewünschten Datentyp
einer Variablen bei der Operation oder Zuweisung an.

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 94
Typkonvertierung in Java
Beispiel 1: erweiternder impliziter Typecast
1 short var1 = 20000;
2 short var2 = 5;
3
4 int var3 = var1 * var2;
:Produkt übersteigt Wertebereich von short!
:Hier: Kein Problem, da var3 vom Typ int.
:Ergebnis wird vor der Zuweisung automatisch nach int konvertiert.
Beide Operanden werden vor der Multiplikation nach
int konvertiert!

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 95
Typkonvertierung in Java
Beispiel 2: erweiternder impliziter Typecast
1 int var1 = 20000;
2 short var2 = 5;
3
4 int var3 = var1 * var2;
:var2 wird vor der Multiplikation automatisch nach int konvertiert.
:Ergebnis wird vor der Zuweisung automatisch nach int konvertiert – OK!

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 96
Typkonvertierung in Java
Beispiel 3: fehlerhaer impliziter Typecast
1 short var1 = 20000;
2 short var2 = 5;
3
4 // Klappt nicht: var1 * var2 liefert int-Ergebnis!
5 short var3 = var1 * var2;
:Compiler bricht mit Fehlermeldung ab!
:Wir haben hier versucht, ein int - Ergebnis an einen short zuzuweisen!

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 97
Wichtigste erweiternde, implizite Konvertierungsregeln
Ergebnisse von Operationen mit
arithmetischen Operatoren,
Vorzeichenoperatoren,
bitweisen logischen Operatoren
Bitmanipulationsoperatoren
werden implizit in int konvertiert, sofern der oder die Operanden char, byte,
short oder int sind.

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 98
Wichtigste erweiternde, implizite Konvertierungsregeln
Datentyp Kann auch zugewiesen werden an ...
byte
short, int, long, float, double
short
int, long, float, double
int
long, float, double
long
float, double
char
int, long, float, double
float
double

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 99
Explizite Typecasts
Syntax expliziter Typecasts
Wir schreiben explizit vor den zu konvertierenden Ausdruck oder vor die zu
konvertierende Variable, welchen Datentyp wir wünschen:
variable = (GewuenschterTyp) variable2;
oder
oder variable = (GewuenschterTyp) ausdruck;

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 100
Explizite Typecasts
Beispiel für explizite Typecasts
1 short a=50;
2 short b=70;
3 short c=1000;
4
5 // Expliziter Typecast des Ergebnisses
6 // a * b von int --> short
7 // ergebnis1 = 3500 --> OK!
8 short ergebnis1 = (short )(a * b);
9
10 // Expliziter Typecast des Ergebnisses
11 // b * c von int --> short; b * c = 70000
12 // ABER: ergebnis2 = 4464!!!! -- Warum??
13 short ergebnis2 = (short )(b*c);

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 101
Sichtbarkeit von Variablen in Java – Teil 1
Variablen sind ...
... innerhalb ihres Gültigkeitsbereiches sichtbar.

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 102
Sichtbarkeit von Variablen – Teil 1
Was ist ein Gültigkeitsbereich?
Gültigkeitsbereich einer Variablen
=
Codebereich, in dem die Variable verwendbar ist.

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 103
Gültigkeitsbereiche von Variablen in Java
In Java unterscheiden wir
Instanzvariablen (Objektvariablen)
- „global“ bekannt innerhalb aller Methoden eines Objektes
- Wird für mit new erzeugte Objekt dieser Klasse neu angelegt.
- n Objekte : n Variablen-Instanzen
Klassenvariablen
- Modifizierer static (später!)
- „global“ bekannt innerhalb aller Methoden einer Klasse
- Existiert nur einmal gemeinsam für alle mit new erzeugten Objekte dieser Klasse.
- n Objekte : 1 Variablen-Instanz
lokale Variablen
- nur innerhalb der Methode bekannt, in der sie definiert wurden.
- : außerhalb der Methode nicht verwendbar!

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 104
Beispiel: Objektvariablen vs. lokale Variablen
public class Variablen2 {
// Objektvariable: wirkt innerhalb der Methoden dieser Klasse "global"
int variable=100;
void methode1(int variable) {
// lokale Variable!
variable = 5000;
System.out.println("variable: "+variable);
}
void methode2() {
// lokale Variable!
int variable = -2;
System.out.println("variable: "+variable);
}
void methode3() {
// Zugriff auf Objektvariable oben!
System.out.println("variable: "+variable);
}
} // end class

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 105
Beispiel: Objektvariablen vs. lokale Variablen
public class Variablen2 {
// Objektvariable: wirkt innerhalb der Methoden dieser Klasse "global"
int variable=100;
void methode1(int variable) {
// lokale Variable!
variable = 5000;
System.out.println("variable: "+variable);
}
void methode2() {
// lokale Variable!
int variable = -2;
System.out.println("variable: "+variable);
}
void methode3() {
// Zugriff auf Objektvariable oben!
System.out.println("variable: "+variable);
}
} // end class

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 106
Beispiel: Objektvariablen vs. lokale Variablen
public class Variablen2 {
// Objektvariable: wirkt innerhalb der Methoden dieser Klasse "global"
int variable=100;
void methode1(int variable) {
// lokale Variable!
variable = 5000;
System.out.println("variable: "+variable);
}
void methode2() {
// lokale Variable!
int variable = -2;
System.out.println("variable: "+variable);
}
void methode3() {
// Zugriff auf Objektvariable oben!
System.out.println("variable: "+variable);
}
} // end class

Einstieg in Java Variablen, Datentypen und Operatoren Prof. Dr. Ute Matecki 107
Beispiel: Objektvariablen vs. lokale Variablen
public class Variablen2Main {
public static void main(String [] args) {
Variablen2 worker = new Variablen2();
worker.methode1(42);
worker.methode2();
worker.methode3();
} // end method main()
} // end class
Zum selber Ausprobieren: Was wird hier ausgegeben? Warum?

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 108
Bereits bekannte Kontrollstrukturen aus Python
Wir kennen bereits
Fallunterscheidung mit if – elif – else
Kopfgesteuerte Schleife mit while
Kopfgesteuerte Schleife mit for

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 109
Verfügbare Kontrollstrukturen in Java
Java stellt bereit
Fallunterscheidung mit if – else if – else
Fallunterscheidung mit switch – case
Kopfgesteuerte Schleife mit while
Kopfgesteuerte Schleife mit for
Fußgesteuerte Schleife mit do – while

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 110
Fallunterscheidung mit if – else if – else
Wird für kompliziertere Abfragen verwendet, beispielsweise:
Größenvergleiche
Wertebereichsabfragen
Bereichsüberprüfungen bei Strings
...

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 111
Fallunterscheidung mit if – else if – else
Syntax if – else if – else
1 if (bedingung1) {
2 anweisung1;
3 // ...
4 }
5 else if (bedingung2) {
6 anweisungN;
7 // ...
8 }
9 // ... weitere else if()-Bedingungen
10 else {
11 anweisungM;
12 // ...
13 }

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 112
Fallunterscheidung mit if – else if – else
Beispiel if – else if – else – Teil 1
1 import java.util.Scanner;
2
3 public class Fallunterscheidung1 {
4
5 public static void main(String[] args) {
6
7 // "Werkzeug" fuer Tastatureingaben
8 Scanner eingabe = new Scanner(System.in);
9
10 // Eingabe vom Nutzer anfordern
11 System.out.print("Bitte eine Ganzzahl eingeben: ");
12 int wert = eingabe.nextInt(); // naechste Seite ..

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 113
Fallunterscheidung mit if – else if – else
Beispiel if – else if – else – Teil 2
13 // Fallunterscheidung: Wertebereiche der Eingabe
14 if (wert >= 0 && wert <= 5) {
15 System.out.println("Wert liegt zwischen 0 und 5");
16 } // end if
17 else if (wert >= 6 && wert <= 10) {
18 System.out.println("Wert liegt zwischen 6 und 10");
19 } // end else if
20 else {
21 System.out.println("Ausserhalb der beiden Bereiche!");
22 } // end else
23 } // end method main()
24 } // end class

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 114
Fallunterscheidung mit if – else if – else
Beispiel if – else if – else – Eingabeszenario
Bitte eine Ganzzahl eingeben: 4
Wert liegt zwischen 0 und 5

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 115
Fallunterscheidung mit switch–case
Wird für einfachere Abfragen verwendet:
Vergleich mit konstanten Werten
Wertebereiche können durch „Fall-through“ (Weglassen der
break-Anweisung) abgefragt werden.
Wertebereiche werden jedoch o einfacher durch eine if-Konstruktion
abgefragt.

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 116
Fallunterscheidung mit switch–case
Syntax switch–case – Grundform
1 switch(wert) {
2 case konstantWert1: anweisungen1; break;
3 case konstantWert2: anweisungen2; break;
4 // .. weitere case-Anweisungen
5 case konstantWertN: anweisungenN; break;
6 default: anweisungAndereWerte; break;
7 }

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 117
Fallunterscheidung mit switch–case
Beispiel switch–case – Teil 1
1 import java.util.Scanner;
2
3 public class Fallunterscheidung2 {
4
5 public static void main(String[] args) {
6
7 // "Werkzeug" fuer Tastatureingaben
8 Scanner eingabe = new Scanner(System.in);
9
10 // Eingabe vom Nutzer anfordern
11 System.out.print("Bitte eine Ganzzahl eingeben: ");
12 int wert = eingabe.nextInt();

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 118
Fallunterscheidung mit switch–case
Beispiel switch–case – Teil 2
13 // switch-case ueberprueft auf einzelne, konstante
14 // Werte
15 switch (wert) {
16 case 1: System.out.println("Eingabe 1!"); break;
17 case 2: System.out.println("Eingabe 2!"); break;
18 case 3: System.out.println("Eingabe 3!"); break;
19 case 4: System.out.println("Eingabe 4!"); break;
20 default: System.out.println("Was anderes!"); break;
21 } // end switch
22
23 } // end method main()
24 } // end class

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 119
Fallunterscheidung mit switch–case
Besonderheit fall-trough
//
// ...
// Eingabe vom Nutzer anfordern
System.out.print("Bitte eine Ganzzahl eingeben: ");
int wert = eingabe.nextInt();
// Fallunterscheidung
switch (wert) {
case 1: System.out.println("Erste Ausgabe!");
case 2: System.out.println("Zweite Ausgabe!");
case 3: System.out.println("Dritte Ausgabe!"); break;
case 4: System.out.println("Vierte Ausgabe"); break;
default: System.out.println("Was anderes!"); break;
} // end switch

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 120
Fallunterscheidung mit switch–case
Besonderheit fall-trough – Eingabeszenario 1
Bitte eine Ganzzahl eingeben: 1
Erste Ausgabe!
Zweite Ausgabe!
Dritte Ausgabe!
case 1 wird durchlaufen – tri zu. Er wird aber nicht mit break beendet.
Daher:
Danach werden cases 2 und 3 durchlaufen, ehe die break-Anweisung in
case 3 die switch-Anweisung abbricht.

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 121
Fallunterscheidung mit switch–case
Besonderheit fall-trough – Eingabeszenario 2
Bitte eine Ganzzahl eingeben: 2
Zweite Ausgabe!
Dritte Ausgabe!
case 1 wird nicht durchlaufen – tri nicht zu.
case 2 wird durchlaufen – tri zu und wird aber nicht mit break
beendet.
Daher wird auch case 3 durchlaufen, ehe break die switch-Anweisung
abbricht.

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 122
Kopfgesteuerte Schleife mit while
Für kompliziertere Wiederholungsanweisungen mit z.B.
Größenvergleichen
Wertebereichsabfragen
Bereichsüberprüfungen bei Strings
Stringvergleichen
...

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 123
Kopfgesteuerte Schleife mit while
Syntax von while
1 while (bedingung) {
2 zuWiederholendeAnweisung1;
3 zuWiederholdendeAnweisung2;
4 // ...
5 zuWiederholendeAnweisungN;
6 }

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 124
Kopfgesteuerte Schleife mit while
Beispiel while – Teil 1
1 import java.util.Scanner;
2
3 public class SchleifeWhile1 {
4
5 public static void main(String [] args) {
6
7 // "Werkzeug" fuer Tastatureingaben
8 Scanner eingabe = new Scanner(System.in);
9
10 // Eingabe vom Nutzer anfordern
11 System.out.print(
12 "Bitte eine Zahl zwischen 1 und 10 eingeben: ");
13 int zahl = eingabe.nextInt();

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 125
Kopfgesteuerte Schleife mit while
Beispiel while – Teil 2
14 // Schleife laeuft, so lange die eingetippte Zahl
15 // zwischen 1 und 10 liegt
16 while (zahl >= 1 && zahl <= 10) {
17 System.out.print("Noch eine Zahl zwischen 1 und 10: ");
18 zahl = eingabe.nextInt();
19 } // end while
20
21 System.out.println(
22 "Letzte Zahl war nicht mehr zwischen 1 und 10!");
23
24 } // end method main()
25 } // end class

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 126
Kopfgesteuerte Schleife mit while
Eingabeszenario while
Bitte eine Zahl zwischen 1 und 10 eingeben: 5
Noch eine Zahl zwischen 1 und 10: 3
Noch eine Zahl zwischen 1 und 10: 66
Letzte Zahl war nicht mehr zwischen 1 und 10!
Sofern der erste eingegebene Wert zwischen 1 und 10 liegt: Einstieg in
den Schleifenrumpf
Schleife wird durchlaufen, so lange der letzte eingegebene Wert
zwischen 1 und 10 liegt.
Schleifenrumpf fordert eine weitere Nutzereingabe an.
Sobald ein Wert außerhalb des geforderten Intervalls eingegeben
wurde: Schleife ist beendet.

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 127
Kopfgesteuerte Schleife mit for
Wird verwendet für
Zählschleifen (z.B. Durchlauf von 1 bis n)
Iterationsschleifen über Arrays oder iterierbare Listen (foreach-Schleife)

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 128
Kopfgesteuerte Schleife mit for
Syntax von for als Zählschleife
1 for (startInitialisierung; bedingung; iterationsAnweisung) {
2 zuWiederholendeAnweisung1;
3 zuWiederholdendeAnweisung2;
4 // ...
5 zuWiederholendeAnweisungN;
6 }

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 129
Kopfgesteuerte Schleife mit for
Beispiel for als Zählschleife – Teil 1
1 import java.util.Scanner;
2
3 public class SchleifeFor1 {
4
5 public static void main(String [] args) {
6
7 // "Werkzeug" fuer Tastatureingaben
8 Scanner eingabe = new Scanner(System.in);
9
10 // Eingabe vom Nutzer anfordern
11 System.out.print("Bitte einen Endwert eingeben: ");
12 int zahl = eingabe.nextInt();

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 130
Kopfgesteuerte Schleife mit for
Beispiel for als Zählschleife – Teil 2
13 // Schleife laeuft, bis i den Wert zahl erreicht
14 for (int i=1; i<= zahl; i++) {
15
16 System.out.println("i: " + i);
17
18 } // end for
19
20 System.out.println("Schleife zu Ende!");
21
22 eingabe.close(); // Scanner schliessen
23
24 } // end method main()
25 } // end class

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 131
Kopfgesteuerte Schleife mit for
Syntax von for als Iterationsschleife
1 // Statt eines Arrays kann auch eine Liste (zB. ArrayList)
2 // durchlaufen werden!
3 for (datentyp laufvariable : array) {
4 zuWiederholendeAnweisung1;
5 zuWiederholdendeAnweisung2;
6 // ...
7 zuWiederholendeAnweisungN;
8 }

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 132
Kopfgesteuerte Schleife mit for
Beispiel for als Iterationsschleife
1 public class SchleifeFor2 {
2 public static void main(String [] args) {
3
4 int [] zahlen = {32, 11, -12, -10};
5
6 // Variable wert leauft ueber alle Elemente im Array
7 for (int wert : zahlen) {
8 System.out.println("wert ist jetzt: "+wert);
9 } // end for
10
11 } // end method main()
12 } // end class

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 133
for-Schleife: Ein Matrixalgorithmus
Problemstellung
Ganzzahlige Matrix einer bestimmten Größe erzeugen.
Diese Matrix mit einem „Schachbrettmuster“ befüllen:
- Wert 0: schwarz
- Wert 1: weiss
Die Matrix zurückgeben.
Die Werte „matrixförmig“ ausgeben.

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 134
for-Schleife: Ein Matrixalgorithmus

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 135
for-Schleife: Ein Matrixalgorithmus
Methode zur Erzeugung der Schachbrettmatrix – Teil 1
1 public class MatrixExample1 {
2
3 // creates a matrix filled with chessboard pattern
4 public static int [][] chessMatrix(int rows, int cols){
5 final int black=0;
6 final int white=255;
7 // create matrix
8 int [][] mat = new int [rows][cols];

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 136
for-Schleife: Ein Matrixalgorithmus
Methode zur Erzeugung der Schachbrettmatrix – Teil 2
9 for (int i=0; i<rows; i++) {
10 for (int j=0; j<cols; j++) {
11 if ((i%2==0 && j%2==0) || (i%2==1 && j%2==1)) {
12 mat[i][j]=black; // black cells
13 }
14 else {
15 mat[i][j] = white; // white cells
16 }// end else
17 } // end for j (columns)
18 } // end for i (colums)
19 return mat;
20 } // end method chessMatrix()

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 137
for-Schleife: Ein Matrixalgorithmus
Methode zur Ausgabe der Matrix
21 public static void printMatrix(int [][] mat) {
22 // mat.length: number of rows
23 for (int i=0; i<mat.length; i++) {
24 for(int j=0; j<mat[i].length; j++) {
25 // TAB after each number
26 System.out.print(mat[i][j]+"\t");
27 } // end for j (columns)
28 System.out.println(); // line break
29 } // end for i (rows)
30 } // end method printMatrix
31 } // end class

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 138
for-Schleife: Ein Matrixalgorithmus
Aufruf der beiden Methoden in einer main()-Klasse
0 public class MatrixMain {
1
2 public static void main(String[] args) {
3 int rows = 3, cols=5;
4 // Erzeugung der Matrix
5 int [][] matr = MatrixExample.chessMatrix(rows, cols);
6
7 // Ausgabe der Matrix
8 MatrixExample.printMatrix(matr);
9
10 } // end main()
11 } // end class

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 139
Fußgesteuerte Schleifen – wozu?
Verwendung immer dann, wenn ...
... mindestens ein Schleifendurchlauf stattfinden soll.
Sprachen, die keine fußgesteuerten Schleifen anbieten, müssen für
derartige Algorithmen immer „doppelten“ Code mitführen.

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 140
Fußgesteuerte Schleifen – wenn es sie nicht gibt
Beispielproblem – Teil 1:
import java.util.Scanner;
public class SchleifeWhile1 {
public static void main(String [] args) {
// "Werkzeug" fuer Tastatureingaben
Scanner eingabe = new Scanner(System.in);
int zahl; // Variable fuer Zahleneingabe
// Eingabe vom Nutzer anfordern
System.out.print("Bitte eine Zahl zwischen 1 und 10 eingeben: ");
zahl = eingabe.nextInt();

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 141
Fußgesteuerte Schleifen – wenn es sie nicht gibt
Beispielproblem – Teil 2:
// Schleife laeuft, so lange die eingetippte
// Zahl zwischen 1 und 10 liegt
while (zahl >= 1 && zahl <= 10) {
// Eingabe vom Nutzer anfordern
System.out.print("Bitte eine Zahl zwischen 1 und 10 eingeben: ");
zahl = eingabe.nextInt();
} // end while
System.out.println(
"Letzte Zahl war nicht mehr zwischen 1 und 10!");
} // end method main()
} // end class

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 142
Fußgesteuerte Schleife mit do – while
Syntax von do – while
1 // Mindestens EIN Durchlauf, bevor die Durchfuehrungs2 // bedingung am FUSS der Schleife geprueft wird!
3 do {
4 zuWiederholendeAnweisung1;
5 zuWiederholdendeAnweisung2;
6 // ...
7 zuWiederholendeAnweisungN;
8 } while (wiederholungsBedingung);

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 143
Fußgesteuerte Schleife mit do – while
Beispielproblem mit do – while – Teil 1
import java.util.Scanner;
public class SchleifeDoWhile1 {
public static void main(String [] args) {
// "Werkzeug" fuer Tastatureingaben
Scanner eingabe = new Scanner(System.in);
int zahl; // Variable fuer Zahleneingabe

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 144
Fußgesteuerte Schleife mit do – while
Beispielproblem mit do – while – Teil 2
do {
// Eingabe vom Nutzer anfordern
System.out.print("Bitte eine Zahl zwischen 1 und 10 eingeben: ");
zahl = eingabe.nextInt();
} while (zahl >= 1 && zahl <= 10);
System.out.println(
"Letzte Zahl war nicht mehr zwischen 1 und 10!");
} // end method main()
} // end class

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 145
Fußgesteuerte Schleife mit do – while
Beispielproblem mit do – while – Teil 2
do {
// Eingabe vom Nutzer anfordern
System.out.print("Bitte eine Zahl zwischen 1 und 10 eingeben: ");
zahl = eingabe.nextInt();
} while (zahl >= 1 && zahl <= 10);
System.out.println(
"Letzte Zahl war nicht mehr zwischen 1 und 10!");
} // end method main()
} // end class

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 146
Zusammenfassung Kontrollstrukturen
Wann welche Fallunterscheidung?
Fallunterscheidung mit if – else if immer dann, wenn
kompliziertere logische Abfragen notwendig sind (Wertebereiche, etc.)
Fallunterscheidung mit switch – case immer dann, wenn konstante
Werte unterschieden werden.

Einstieg in Java Kontrollstrukturen Prof. Dr. Ute Matecki 147
Zusammenfassung Kontrollstrukturen
Wann welche Schleife?
Kopfgesteuerte Schleife mit while immer dann, wenn von Beginn an
der Durchlauf verhindert werden soll, falls das Durchführungskriterium
nicht erfüllt ist.
Kopfgesteuerte Zählschleife mit for immer dann, wenn ein
Laufzähler im Schleifenablauf inkrementiert oder dekrementiert
werden soll.
Kopfgesteuerte Iterationsschleife mit for immer dann, wenn die
Elemente eines Arrays oder einer Liste durchlaufen werden sollen.
Fußgesteuerte Schleife mit do – while immer dann, wenn der
Schleifenrumpf mindestens einmal durchlaufen werden soll.

Einstieg in Java Methoden in Java Prof. Dr. Ute Matecki 148
Im vergangenen Semester: Funktionen in Python
Funktionen in Python: wir erinnern uns ...
In Python konnten Funktionen innerhalb und ausserhalb von Klassen
vereinbart werden.
Funktionen innerhalb von Klassen werden auch als Methoden
bezeichnet.

Einstieg in Java Methoden in Java Prof. Dr. Ute Matecki 149
Im vergangenen Semester: Funktionen in Python
Wir erinnern uns: Syntax von Funktionsdefinitionen in Python
def funcName(param1, param2, ...):
Anweisung1
Anweisung2
# ...
AnweisungN
: Typisierung von Parametern und Rückgabewert erfolgte implizit!

Einstieg in Java Methoden in Java Prof. Dr. Ute Matecki 150
In diesem Semester: Methoden in Java
Methoden in Java
Methoden beinhalten in sich abgeschlossene Unteraufgaben innerhalb
einer Klasse.
In Java können Funktionen nur innerhalb von Klassen vereinbart
werden.
Daher heißen in Java unsere Funktionen immer Methoden.
: Typisierung von Parametern und Rückgabewert erfolgt explizit!

Einstieg in Java Methoden in Java Prof. Dr. Ute Matecki 151
Methoden in Java: Vereinbarungssyntax
Erste Variante: vereinfachte Vereinbarungssyntax
returnTyp methodenName(typ1 param1, typ2 param2, ...) {
Anweisung1;
Anweisung2;
// ...
AnweisungN;
}

Einstieg in Java Methoden in Java Prof. Dr. Ute Matecki 152
Methoden in Java: Vereinbarungssyntax
Erste Variante: vereinfachte Vereinbarungssyntax
returnTyp methodenName (...)
datenTyp variablenName ;
: Syntax für die Vereinbarung von Methodenköpfen ist sehr ähnlich der
Syntax zur Vereinbarung von Variablen!

Einstieg in Java Methoden in Java Prof. Dr. Ute Matecki 153
Methoden ohne Rückgabe
Methode gibt nichts zurück: Rückgabetyp void
1 void sagHallo(String name) {
2 System.out.println("Hallo " + name);
3 }
: void-Methoden haben am Ende der Methode keine return-Anweisung!

Einstieg in Java Methoden in Java Prof. Dr. Ute Matecki 154
Methoden mit Rückgabe
Methode gibt ein Ergebnis zurück: Rückgabetyp und return-Statement
1 int altersBerechnung(int alter) {
2 int ergebnis = alter - 18;
3 return ergebnis;
4 }
: Methoden mit Rückgabetyp haben am Ende der Methode zwingend
eine return-Anweisung!
Der Typ des zurückgegebenen Wertes muss dem im Kopf angegebenen
Rückgabetyp (oben: returnTyp) entsprechen!

Einstieg in Java Methoden in Java Prof. Dr. Ute Matecki 155
Methoden in Java: Signatur einer Methode ...
... ist der Methodenkopf ohne Angabe des Rückgabetyps
int methodenKopf(float param1, String param2) {...}
: Dieser Begri wird später in der OOP beim Überladen von Methoden
benötigt!

Einstieg in Java Methoden in Java Prof. Dr. Ute Matecki 156
Parameterübergabe: Formale und aktuelle Parameter
public class Methoden1 {
void hello1(String name) {
System.out.println("Hallo " + name );
} // end hello1()
public static void main(String [] args) {
// Arbeitsobjekt DIESER Klasse anlegen
Methoden1 test = new Methoden1();
test.hello1("Obelix");
} // end method main()
} // end class

Einstieg in Java Methoden in Java Prof. Dr. Ute Matecki 157
Parameterübergabe: Formale und aktuelle Parameter
Merke: Methodendefinition vs. Methodenaufruf
Bei der Methodendefinition sind formale Parameter angegeben. Sie
spezifizieren, welche Übergaben die Methode überhaupt erwartet. Ohne
deren Namen könnte der Methodenrumpf nicht auf übergebene Daten
zugreifen.
Beim Methodenaufruf werden die tatsächlich im Programm
entstandenen Daten durchgereicht. Dies sind die aktuellen Parameter.

Einstieg in Java Methoden in Java Prof. Dr. Ute Matecki 158
Parameterübergabe: Call-by-value vs. Call-by-reference
public class Methoden2 {
void testMethode1(Person pers) {
pers.ausgabe();
} // end testMethode0()
double testMethode2(double m, double x, double b) {
double y = m*x + b;
return y;
} // end testMethode2()

Einstieg in Java Methoden in Java Prof. Dr. Ute Matecki 159
Parameterübergabe: Call-by-value vs. Call-by-reference
public static void main(String [] args) {
Person p1 = new Person("Erna Etepetete");
double mNeu = 2.0;
double xNeu = 1.5;
double bNeu = 0.5;
// Arbeitsobjekt DIESER Klasse anlegen
Methoden2 test = new Methoden2();
test.testMethode1(p1);
test.testMethode2(mNeu, xNeu, bNeu);
} // end method main()
} // end class Methoden2

Einstieg in Java Methoden in Java Prof. Dr. Ute Matecki 160
Parameterübergabe: Call-by-value vs. Call-by-reference
Genaue Betrachtung der Parameterübergabe beim Aufruf
Die Variablen elementaren Datentyps liegen in main() auf dem dortigen
lokalen Speicherbereich (auf dem Stack von main()).
Die Referenz auf das Personen-Objekt liegt ebenfalls auf dem Stack von
main().
Das mit new angelegte Objekt vom Typ Person liegt dagegen auf dem
Freispeicherbereich oder Heap des Programms.
Bei der Übergabe der Variablen elementaren Typs wird eine Kopie der
Werte auf dem Stack von testMethode2() abgelegt. Mit diesen Kopien
arbeitet unsere Methode bei ihrer Berechnung.
Diese Art Methodenaufruf heisst Call-by-value.

Einstieg in Java Methoden in Java Prof. Dr. Ute Matecki 161
Parameterübergabe: Call-by-value vs. Call-by-reference
Genaue Betrachtung der Parameterübergabe beim Aufruf
Bei der Übergabe der Referenzvariablen wird nur die Referenz – also
die Adresse der Variablen kopiert.
Das Personen-Objekt existiert weiterhin nur einmal.
Diese Art Methodenaufruf wird o ungenauer Weise als
Call-by-reference bezeichnet.
Dies ist nicht ganz richtig: In Java wird hier ebenfalls ein Wert
übergeben – nämlich der Adreßwert des Objektes!
Andere Programmiersprachen kennen eine speziell gekennzeichnete
Referenz-Übergabe: Sie wird wirklich als call-by-reference bezeichnet.

