# Skript-Rohtext: Exceptions (Skript S. 409–435)

2
• © Prof. Dr. Ute Matecki
Fakultät Informatik
Programmierung 2
Exceptions

Exceptions Prof. Dr. Ute Matecki 409
Vorwort
Einstieg in Java
Einstieg in die OOP: Klassen und Objekte/Instanzen
Die Klasse String
Graphische Darstellung von Klassen mit der UML – Teil 1
Vererbungsbeziehungen
Exceptions

Exceptions Prof. Dr. Ute Matecki 410
Was sind Exceptions?
Exceptions selbst erzeugen und werfen – throw und throws
Exceptions fangen – try – catch – finally
Einstieg Streams

Exceptions Was sind Exceptions? Prof. Dr. Ute Matecki 411
Was sind Exceptions?
In Objektorientierten Programmiersprachen sind Exceptions ...
... Objekte spezieller Klassen, die in Fehler- oder
Ausnahmebehandlungs-Situationen des Programms erzeugt werden.
Sie
- enthalten Informationen darüber, wo im Code der Fehler / die Ausnahmesituation
entstanden ist, und
- können sehr schnell an die oberste Aufruf-Ebene des Programm-Codes
durchgereicht werden.
Sie erlauben es den Programmcode aufzuteilen in
- korrekt abgelaufenen Standard-Code (try-Klausel)
- Code, der nur im Fehlerfall zum Abfangen des Fehlers durchlaufen wird
(catch-Klausel)
- Code, der immer durchlaufen wird, gleichgültig, ob ein Fehler aufgetreten ist oder
nicht (finally-Klausel)

Exceptions Was sind Exceptions? Prof. Dr. Ute Matecki 412
Was sind Exceptions?
Exceptions können in Java ...
... als Objekte vorgefertigter Exception-Klassen selbst erzeugt werden,
oder ...
... als Objekte eigener, selbst definierter Exception-Klassen erzeugt
werden.
Ein Exception-Objekt an den Aufrufer einer Methode weiterreichen heißt
in der OOP auch „Eine Exception werfen“.
Dies geschieht in Java mit throw.
Eine Java-Methode kann auch ein in ihr entstandenes Exception-Objekt
einfach an ihren Aufrufer weiterreichen. Dies wird an ihrem Kopf
kenntlich gemacht mit der Klausel throws

Exceptions Was sind Exceptions? Prof. Dr. Ute Matecki 413
Was sind Exceptions?
Einige sehr bekannte, vorgefertigte Exception-Klassen in Java Exception
RuntimeException
IllegalArgumentException
NumberFormatException
NullPointerException IndexOutOfBoundsException
ArrayIndexOutOfBoundsException StringIndexOutOfBoundsExceptions
IOException
FileNotFoundException
Ausschnitt aus dem Klassenzoo der StandardExceptions von Java

Exceptions Exceptions selbst erzeugen und werfen – throw und throws Prof. Dr. Ute Matecki 414
Exceptions selbst erzeugen und werfen – throw
Syntax von throw
1 // Exception-Objekt erzeugen: Dem Konstruktor wird eine
2 // moegliche Fehlernachricht mit uebergeben.
3 ExceptionType1 myException =
4 new ExceptionType1("Exception-Nachricht ...");
5
6 // Exception werfen
7 throw myException;

Exceptions Exceptions selbst erzeugen und werfen – throw und throws Prof. Dr. Ute Matecki 415
Methoden, in denen Exceptions geworfen werden, ...
... benötigen die throws-Klausel
Syntax von throws
1 returnType methodName(typ1 param1, typ2 param2,...)
2 throws ExceptionType1,ExceptionType2,...
3 {
4 // Code der Methode ...
5 ExceptionType1 ex1 = new ExceptionType1("Fehler 1");
6 throw ex1;
7 // weiterer Code ... weiterer throw ...
8 // ggf. return-Statement
9 }

Exceptions Exceptions selbst erzeugen und werfen – throw und throws Prof. Dr. Ute Matecki 416
Exceptions selbst erzeugen und werfen
Unterschied throw und throws
throw wir ein konkretes Exception-Objekt innerhalb des
Methodenrumpfes
throws ist dagegen eine Deklaration am Methodenkopf: Sie macht
kenntlich, dass innerhalb dieser Methode bestimmte Typen von
Exceptions geworfen werden können.

Exceptions Exceptions selbst erzeugen und werfen – throw und throws Prof. Dr. Ute Matecki 417
Exceptions selbst erzeugen und werfen – Beispiel
Klasse Zahlenformat – Teil 1
1 public class ZahlenFormat {
2
3 public int returnZahlWert(char ziffer)
4 throws NumberFormatException {
5 // gib entsprechenden int-Wert
6 // zwischen 0 und 9 zurueck
7 if( ziffer >= '0' && ziffer <= '9'){
8 return ziffer - '0';
9 }
Methode gibt den Zahlenwert einer übergebenen Zier zurück

Exceptions Exceptions selbst erzeugen und werfen – throw und throws Prof. Dr. Ute Matecki 418
Exceptions selbst erzeugen und werfen – Beispiel
Klasse Zahlenformat – Teil 2
10 // ansonsten wirf Exception-Objekt
11 else {
12 NumberFormatException myExcept =
13 new NumberFormatException(
14 "Keine Ziffer!");
15 throw myExcept ;
16 } // end else
17 } // end method
18 } // end class
Falls das übergebene Zeichen keine Zier war: Methode wir Exception
vom Typ NumberFormatException

Exceptions Exceptions selbst erzeugen und werfen – throw und throws Prof. Dr. Ute Matecki 419
Exceptions selbst erzeugen und werfen – Beispiel
main()-Klasse MainEx1 – Teil 1
1 import java.util.Scanner;
2
3 public class MainEx1 {
4
5 public static void main(String[] args)
6 throws NumberFormatException {
7
8 Scanner tastatur = new Scanner(System.in);
9
10 ZahlenFormat worker = new ZahlenFormat();
Da die main()-Methode später eine Methode aufru, die eine
NumberFormatException werfen kann, so muss sie diese ebenfalls
verarbeiten – hier mit throws.

Exceptions Exceptions selbst erzeugen und werfen – throw und throws Prof. Dr. Ute Matecki 420
Exceptions selbst erzeugen und werfen – Beispiel
main()-Klasse MainEx1 – Teil 2
11 // Eingabe anfordern
12 System.out.print(
13 "Bitte Ziffer zwischen 0-9 eingeben: ");
14
15 // Tastatureingabe entgegennehmen
16 String s = tastatur.next();
17 // Erstes Zeichen aus Eingabe abfragen
18 char c = s.charAt(0);
Hier erfolgt die Nutzereingabe. Ihr erstes Zeichen wird abgefragt.

Exceptions Exceptions selbst erzeugen und werfen – throw und throws Prof. Dr. Ute Matecki 421
Exceptions selbst erzeugen und werfen – Beispiel
main()-Klasse MainEx1 – Teil 3
20 // Versuche, Zeichen in Zahl zu konvertieren
21 int wert = worker.returnZahlWert(c);
22
23 // Rueckmeldung an Nutzer ausgeben
24 System.out.println(
25 "Eingabe erfolgte mit Wert: " + wert);
26
27 } // end main
28 } // end class
Dieser Methodenaufruf
kann eine NumberFormatException werfen!

Exceptions Exceptions selbst erzeugen und werfen – throw und throws Prof. Dr. Ute Matecki 422
Exceptions selbst erzeugen und werfen – Beispiel
Compilierung und Start des Programms mit ...
javac ZahlenFormat.java
javac MainEx1.java
java MainEx1
... oder innerhalb von Eclipse ...

Exceptions Exceptions selbst erzeugen und werfen – throw und throws Prof. Dr. Ute Matecki 423
Exceptions selbst erzeugen und werfen – Beispiel
Erster Start: Eingabe der Zier 5
Bitte Ziffer zwischen 0-9 eingeben: 5
Eingabe erfolgte mit Wert: 5

Exceptions Exceptions selbst erzeugen und werfen – throw und throws Prof. Dr. Ute Matecki 424
Exceptions selbst erzeugen und werfen – Beispiel
Zweiter Start: Eingabe des Zeichens W
Bitte Ziffer zwischen 0-9 eingeben: W
Exception in thread "main"
java.lang.NumberFormatException: Keine Ziffer!
at ZahlenFormat.returnZahlWert(ZahlenFormat.java:15)
at MainEx1.main(MainEx1.java:22)
Bei Eingabe einer Nicht-Zier: Die letzte Ausgabe von System.out.println()
erfolgt nicht mehr, da die Exception den Programmablauf vorher abbricht!

Exceptions Exceptions fangen – try – catch – finally Prof. Dr. Ute Matecki 425
Exceptions fangen try – catch – finally
Problem bei der Verarbeitung mit throw und throws
Wenn Exceptions bis auf die Ebene von main() hinauf geworfen werden,
so wird ggf. der Programm-Ablauf unerwünscht unterbrochen.
Daher will man manchmal Exceptions „an Ort und Stelle“ verarbeiten:
1 Code-Statements „probieren“ (try), bis eine Exception eintritt
2 Exception an „Ort und Stelle“ fangen und verarbeiten (catch)
3 Gleichgültig ob wir in (1) oder (2) landen: Rest-Code durchführen (finally)

Exceptions Exceptions fangen – try – catch – finally Prof. Dr. Ute Matecki 426
Methoden, in denen Exceptions geworfen werden, ...
... benötigen nicht immer die throws-Klausel!!!
Syntax von try – catch – finally
1 returnType methodName(typ1 param1, typ2 param2,...) {
2 try {
3 // Code-Statement 1; ... Code-Statement N;
4 }
5 catch(ExceptionType1 |
6 ExceptionType2 | ... | ExceptionTypeN e){
7 // Abfang-Statement1; ...
8 }
9 finally {
10 // Schluss-Statement1; ...
11 } // end finally
12 } // end method
Bei methoden-interner
Verarbeitung von Exceptions mit
try-catch können wir auf die
throws-Klausel am
Methodenkopf verzichten!

Exceptions Exceptions fangen – try – catch – finally Prof. Dr. Ute Matecki 427
Exceptions fangen – Beispiel mit neuer main()-Klasse
Klasse MainEx2 – Teil 1 – Start main()
1 import java.util.Scanner;
2
3 public class MainEx2 {
4
5 public static void main(String[] args) {
6 // Arbeitsobjekte erstellen
7 Scanner tastatur = new Scanner(System.in);
8 ZahlenFormat worker = new ZahlenFormat();
9 char c='@';
10 int wert=-1;
Methode main() legt zuerst die benötigten Arbeitsobjekte an.

Exceptions Exceptions fangen – try – catch – finally Prof. Dr. Ute Matecki 428
Exceptions fangen – Beispiel mit neuer main()-Klasse
Klasse MainEx2 – Teil 2 – try-Block
11 try{
12 // Eingabe anfordern
13 System.out.print(
14 "Bitte Ziffer zwischen 0-9 eingeben: ");
15
16 // Tastatureingabe entgegennehmen
17 String s = tastatur.next();
18 // Erstes Zeichen aus Eingabe abfragen
19 c = s.charAt(0);
20
21 // Versuche, Zeichen in Zahl zu konvertieren
22 wert = worker.returnZahlWert(c);
23 } // end try
try-Block „probiert“ die
gewünschten Statements ...

Exceptions Exceptions fangen – try – catch – finally Prof. Dr. Ute Matecki 429
Exceptions fangen – Beispiel mit neuer main()-Klasse
Klasse MainEx2 – Teil 3 – catch (Multiple Exception catch)
24 catch(NumberFormatException |
25 StringIndexOutOfBoundsException ex){
26 ex.printStackTrace();
27 } // end catch

Exceptions Exceptions fangen – try – catch – finally Prof. Dr. Ute Matecki 430
Exceptions fangen – Beispiel mit neuer main()-Klasse
Klasse MainEx2 – Teil 3 – catch (Multiple Exception catch)
Der catch-Block wird ausgeführt, wenn im try-Block eine Exception
geworfen wurde.
In diesem Fall wird der try-Block an der Stelle abgebrochen, an der die
Exception entstand.
ex.printStackTrace() ist eine von der Klasse Exception ererbte Methode.
Sie gibt aus, wo die Exception entstand.
Wenn wir mehrere Exceptions mit ein und demselben Code im
catch-Block abhandeln wollen, so geben wir sie in seinem Kopf als
Veroderung an: ExceptionType1 | ExceptionType2. Dies wird als Multiple
Exception Catch bezeichnet.

Exceptions Exceptions fangen – try – catch – finally Prof. Dr. Ute Matecki 431
Exceptions fangen – Beispiel mit neuer main()-Klasse
Klasse MainEx2 – Teil 4 – finally
28 finally {
29 System.out.println(
30 "Inhalt von wert lautet nun: " + wert);
31 } // end finally
32 } // end method main()
33 } // end class MainEx2

Exceptions Exceptions fangen – try – catch – finally Prof. Dr. Ute Matecki 432
Exceptions fangen – Beispiel mit neuer main()-Klasse
Klasse MainEx2 – Teil 4 – finally
Der finally-Block ist optional – er kann also auch weggelassen
werden.
Wenn er vorhanden ist, wird er immer ausgeführt – auch wenn keine
Exception geworfen wurde

Exceptions Exceptions fangen – try – catch – finally Prof. Dr. Ute Matecki 433
Exceptions fangen – Beispiel mit neuer main()-Klasse
Klasse MainEx2 – Teil 3 – catch (Single Exception catch)
24 catch(NumberFormatException ex){
25 System.out.println("NumberFormatException!");
26 } // end catch NumberFormatException
27 catch(StringIndexOutOfBoundsException ex){
28 System.out.println("StringIndexOutOfBoundsException!");
29 } // end catch NumberFormatException
30 catch (Exception ex){
31 System.out.println("Andere Exception!");
32 } // end catch Exception e
Diese catch-Anweisung der allgemeinen Exception muss
als letzter catch erfolgen. Sonst Compilerfehler!!

Exceptions Exceptions fangen – try – catch – finally Prof. Dr. Ute Matecki 434
Exceptions fangen – Beispiel mit neuer main()-Klasse
Klasse MainEx2 – Teil 3 – catch (Single Exception catch)
Wenn wir mehrere Exceptions mit jeweils unterschiedlichem
Abfang-Code im catch-Block abhandeln wollen, so geben wir einzelne
getrennte catch-Klauseln an! (Single Exception Catch)
Häufig fängt man am Ende einer solchen Folge von catch-Blöcken noch
die „allgemeine“ Exception ab:
catch (Exception e) {...}
Jedes XXXException-Objekt ist gleichzeitig ein Objekt der Elternklasse
Exception. So fangen wir alle nicht spezifisch genannten, übrigen
Exceptions ab!

Exceptions Exceptions fangen – try – catch – finally Prof. Dr. Ute Matecki 435
Zusammenfassung Exceptions
Klasse MainEx2 – Teil 3 – catch (Single Exception catch)
Mit throw können wir eine selbst erzeugte Exception werfen.
Eine Methode kann eine in ihr entstandene Exception über die
throws-Klausel am Methodenkopf weiterwerfen.
Mit try–catch können Exceptions methodenintern abgearbeitet
werden. Der Methodenaufrufer bekommt davon nichts mit.
Es gibt zwei Arten einer catch-Klausel:
- Ein Single Exception Catch stellt für jede Art von Exception eine eigene
catch-Klausel mit eigener Abarbeitung bereit.
- Ein Multiple Exception Catch stellt eine einzige catch-Klausel für mehrere
möglicherweise eintretende Exceptions bereit. Sie werden durch das
Veroderungszeichen | voneinander unterschieden.

