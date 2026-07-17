# Skript-Rohtext: Die Klasse String (Skript S. 233–260)

2
• © Prof. Dr. Ute Matecki
Fakultät Informatik
Programmierung 2
Die Klasse String

Die Klasse String Prof. Dr. Ute Matecki 233
Vorwort
Einstieg in Java
Einstieg in die OOP: Klassen und Objekte/Instanzen
Die Klasse String
Grundlagen Strings
Stringoperationen
Wichtigste Methoden der Klasse String
Eigenschaen von Strings abfragen
Graphische Darstellung von Klassen mit der UML – Teil 1

Die Klasse String Prof. Dr. Ute Matecki 234
Vererbungsbeziehungen
Exceptions
Einstieg Streams

Die Klasse String Grundlagen Strings Prof. Dr. Ute Matecki 235
Grundlagen Zeichen und Strings
Der Datentyp char
Der Datentyp char ist in Java ein 16-Bit-Datentyp.
In String-Objekten werden Zeichenfolgen, bestehend aus
Unicode-Zeichen gekapselt.
Die Klasse String stellt eine Reihe von String-Verarbeitungs- Methoden
zur Verfügung, z.B.
- Ausschneiden von Teilstrings,
- Suchen nach Teil-Zeichenketten,
- Splitten nach „Trenner“, uvm.
- Siehe hierzu auch die oizielle API-Seite
https://docs.oracle.com/javase/8/docs/api/java/lang/String.html

Die Klasse String Grundlagen Strings Prof. Dr. Ute Matecki 236
Grundlagen Zeichen und Strings
Variablen vom Typ char und vom Typ String
1 char x = 'M'; // einfaches Zeichen
2
3 // String mit Zuweisung des Literals
4 String s = "Erna Etepetete";
5
6 // String mit Konstruktor
7 String t = new String("Hugo Helmchen")
Die Literale einfacher Zeichen werden mit einfachen
Anführungsstrichen 'M' vereinbart!
Die Literale von Strings werden mit doppelten Anführungsstrichen
"abc" vereinbart!

Die Klasse String Stringoperationen Prof. Dr. Ute Matecki 237
Stringoperationen
Verkettung (Konkatenation) von Strings mit +
1 String s1 = "Hallo Mitglieder ";
2 String s2 = "der Lehrveranstaltung Prog ";
3
4 // Konkatenierungsoperator:
5 // Haengt s1 und s2 und die Zahl 2 aneinander
6 String s3 = s1 + s2 + 2;

Die Klasse String Stringoperationen Prof. Dr. Ute Matecki 238
Stringoperationen
Verkettung (Konkatenation) von Strings mit +=
1 String s1 = "Hallo Mitglieder ";
2 String s2 = "der Lehrveranstaltung Prog ";
3
4 // Konkatenierungsoperator +=: Haengt an s1
5 // die Strings s1, gefolgt von der Ziffer 2
6 // aneinander
7 s1 += s2 + 2;

Die Klasse String Stringoperationen Prof. Dr. Ute Matecki 239
Stringoperationen
Vergleich von Strings – erster Versuch mit ==
1 String s = "Erna";
2 String t = "Erna";
3
4 if (s == t) {
5 System.out.println("gleich!");
6 }
7 else {
8 System.out.println("ungleich!");
9 } // end else
Ausgabe lautet:
gleich!
:Die Strings s und t scheinen gleich zu sein!

Die Klasse String Stringoperationen Prof. Dr. Ute Matecki 240
Stringoperationen
Vergleich von Strings – zweiter Versuch mit ==
1 String s = "Erna";
2 String t = new String("Erna");
3
4 if (s == t) {
5 System.out.println("gleich!");
6 }
7 else {
8 System.out.println("ungleich!");
9 } // end else
Ausgabe lautet nun:
ungleich!
:Die Strings s und t scheinen trotz gleichem Inhalt nicht gleich zu sein!

Die Klasse String Stringoperationen Prof. Dr. Ute Matecki 241
Stringoperationen
Vergleich von Strings – Erklärung des ersten Versuchs mit ==
1 String s = "Erna"; Erna
2 String t = "Erna";
3
4 if (s == t) {
5 // ...
6 }
Erklärung:
Die Variablen s und t enthalten eine Referenz auf die gleiche
Speicherstelle!
Das Objekt mit dem Inhalt "Erna" existiert nur einmal!
Bei der zweiten Zuweisung an t wird kein neues Objekt mehr erzeugt.
Der ==-Operator vergleicht hier nur zwei (gleiche) Adressen.

Die Klasse String Stringoperationen Prof. Dr. Ute Matecki 242
Stringoperationen
Vergleich von Strings – Erklärung des zweiten Versuchs mit ==
1 String s = "Erna"; Erna
2
3 String t = new String("Erna"); Erna
4
5 if (s == t) // ...
Erklärung:
Die Variablen s und t enthalten Referenzen auf verschiedene
Speicherstellen
Es existieren durch die new-Operation zwei Objekte mit gleichartigem
Inhalt!
Der ==-Operator vergleicht hier zwei unterschiedliche Adressen.
Daher sind die Variablen s und t ungleich!

Die Klasse String Stringoperationen Prof. Dr. Ute Matecki 243
Stringoperationen
Wir merken uns: Stringvergleiche mit ==
... sind keine gute Idee!
Der ==-Operator vergleicht nur die Adressen der Strings, nicht aber die
Inhalte!
Ebenso führt der !=-Operator nur einen Vergleich der Adressen durch,
nicht aber die Inhalte!

Die Klasse String Stringoperationen Prof. Dr. Ute Matecki 244
Stringoperationen
Wie machen wir aber nun Inhaltsvergleiche mit Strings?!!!
Möglichkeit 1: Verwendung der equals()-Methode der Klasse String.
Möglichkeit 2: Verwendung von switch-case , sofern ein String mit
konstanten Literalen verglichen werden soll.

Die Klasse String Stringoperationen Prof. Dr. Ute Matecki 245
Stringoperationen
Stringvergleich mit equals()
1 String s = "Erna"; Erna
2 String t = new String("Erna"); Erna
3
4 if (s.equals(t)) {
5 System.out.println("gleich!");
6 }
7 else {
8 System.out.println("ungleich!");
9 } // end else
Ausgabe lautet: gleich!
Die Strings s und t haben den gleichen Inhalt!
Daher gibt s.equals(t) den Wert true zurück!

Die Klasse String Stringoperationen Prof. Dr. Ute Matecki 246
Stringoperationen
Auch der folgende Vergleich mit equals() funktioniert:
1 String t = new String("Erna"); Erna
2
3 if (t.equals("Erna")) {
4 System.out.println("gleich!");
5 }
6 else {
7 System.out.println("ungleich!");
8 } // end else
Ausgabe lautet auch hier: gleich!
Der Inhalt von t wird direkt mit dem Inhalt eines String-Literals
verglichen.
Auch hier ist der Inhalt gleich : equals() gibt true zurück.

Die Klasse String Stringoperationen Prof. Dr. Ute Matecki 247
Stringoperationen
Stringvergleich mit switch-case
1 String t = new String("Erna");
2
3 switch (t) {
4 case "Emil": System.out.println("Hallo Emil!");
5 break;
6 case "Erna": System.out.println("Hallo Erna!");
7 break;
8 case "Hugo": System.out.println("Hallo Hugo!");
9 break;
10 default: System.out.println("nichts davon!");
11 } // end switch
Ausgabe lautet hier: Hallo Erna!

Die Klasse String Stringoperationen Prof. Dr. Ute Matecki 248
Stringoperationen
Stringvergleich mit switch-case
Seit Java 7 gilt:
Der Stringvergleich mit switch-case ist äquivalent zum Vergleich mit Hilfe
der equals()-Methode!
In den cases werden jeweils String-Literale abgefragt.

Die Klasse String Wichtigste Methoden der Klasse String Prof. Dr. Ute Matecki 249
Wichtigste Methoden der Klasse String
Eigenschaen von Strings abfragen
RückgabetypMethode
char charAt(int pos)
gibt das Zeichen an Position pos zurück
boolean endsWith(String substr)
prü, ob der String mit dem übergebenen substr endet.
boolean isEmpty()
prü, ob der String leer ist.
int length()
gibt die Länge des Strings zurück.
boolean startsWith(String substr)
prü, ob der String mit dem übergebenen substr beginnt.

Die Klasse String Wichtigste Methoden der Klasse String Prof. Dr. Ute Matecki 250
Methoden der Klasse String
Eigenschaen von Strings abfragen – Position eines Zeichens
1 String s1 = new String("Hallo");
2
3 // gibt 'a' zurueck
4 char c = s1.charAt(1);

Die Klasse String Wichtigste Methoden der Klasse String Prof. Dr. Ute Matecki 251
Methoden der Klasse String
Eigenschaen von Strings abfragen – Länge
1 String s1 = new String("Hallo");
2 int [] arr = {44,-55,12,8};
3
4 // gibt 5 zurueck
5 int laengeString = s1.length();
6
7 // gibt 4 zurueck
8 int laengeArray = arr.length;
Achtung:
Die Länge eines Strings wird mit seiner Methode length() abgefragt.
Die Länge eines Arrays wird mit seiner Variablen length abgefragt.

Die Klasse String Wichtigste Methoden der Klasse String Prof. Dr. Ute Matecki 252
Wichtigste Methoden der Klasse String
Substrings und deren Indizes
RückgabetypMethode
int indexOf(char c)
gibt die Position des erstmaligen Vorkommens von c zurück.
-1 bei Nichtvorkommen.
int indexOf(String s)
gibt die Position des erstmaligen Vorkommens von s zurück.
-1 bei Nichtvorkommen.
int indexOf(char c,int pos)
gibt die Position des erstmaligen Vorkommens von c ab Position pos zurück. -1 bei Nichtvorkommen.

Die Klasse String Wichtigste Methoden der Klasse String Prof. Dr. Ute Matecki 253
Wichtigste Methoden der Klasse String
Substrings und deren Indizes
RückgabetypMethode
int indexOf(String s,int pos)
gibt die Position des erstmaligen Vorkommens von s ab Position pos zurück. -1 bei Nichtvorkommen.
String substring(int pos1)
gibt den Teilstring ab Position pos1 zurück. Leerer String, falls
die Position nicht gültig ist. In diesem Falle wir die Methode
außerdem eine IndexOutOfBoundsException

Die Klasse String Wichtigste Methoden der Klasse String Prof. Dr. Ute Matecki 254
Wichtigste Methoden der Klasse String
Substrings und deren Indizes
RückgabetypMethode
String substring(int pos1, int pos2)
gibt den Teilstring ab Position pos1 bis vor Position
pos2 zurück. Leerer String, falls die Position nicht gültig ist. In diesem Falle wir die Methode außerdem eine
IndexOutOfBoundsException

Die Klasse String Wichtigste Methoden der Klasse String Prof. Dr. Ute Matecki 255
Methoden der Klasse String
Indizes von Strings abfragen – Beispiel 1
1 String s1 = "Beim Flachdach ist das Dach flach";
2
3 // 'A' kommt nicht vor --> pos1 = -1
4 int pos1 = s1.indexOf('A');

Die Klasse String Wichtigste Methoden der Klasse String Prof. Dr. Ute Matecki 256
Methoden der Klasse String
Indizes von Strings abfragen – Beispiel 2
1 String s1 = "Beim Flachdach ist das Dach flach";
2
3 // Ab Position 5 (von 0 an gezaehlt) beginnt das
4 // erste Vorkommen von "dach" ab Position 10
5 // --> pos2 = 10
6 int pos2 = s1.indexOf("dach", 5);

Die Klasse String Wichtigste Methoden der Klasse String Prof. Dr. Ute Matecki 257
Methoden der Klasse String
Substrings abfragen – Beispiel 1
1 String s1 = "Beim Flachdach ist das Dach flach";
2
3 // liefert den Teilstring zwischen Position
4 // 2 und vor Position 6: --> "im F"
5 String s3 = s1.substring(2,6);

Die Klasse String Wichtigste Methoden der Klasse String Prof. Dr. Ute Matecki 258
Methoden der Klasse String
Konvertierung von String – Elementare Datentypen
Zur Konvertierung Elementarer Datentyp : String: Hier gibt es die
valueOf()-Methoden der Klasse String.
Zur Konvertierung String : Elementarer Datentyp: Hier gibt es die
parse...()-Methoden der Wrapper-Klassen
- Short
- Integer
- Long
- Float
- Double
- Boolean

Die Klasse String Wichtigste Methoden der Klasse String Prof. Dr. Ute Matecki 259
Methoden der Klasse String
Beispiel 1: Konvertierung Elementarer Datentyp : String
1 int iWert = 12;
2 double dWert = 1.5;
3
4 // iString enthaelt anschliessend die Zeichenfolge "12"
5 String iString = String.valueOf(iWert);
6
7 // dString enthaelt anschliessend die Zeichenfolge "1.5"
8 String dString = String.valueOf(dWert);
Achtung:
Die valueOf...()-Methoden der Klasse String sind statisch. Daher lassen sie
sich direkt über den Klassennamen – ohne Arbeitsobjekt aufrufen.

Die Klasse String Wichtigste Methoden der Klasse String Prof. Dr. Ute Matecki 260
Methoden der Klasse String
Beispiel 2: Konvertierung String : Elementarer Datentyp mit
Wrapper-Klassen
1 String iString = "345";
2 String dString = new String("22.5");
3
4 // iWertNeu enthaelt nun den Wert 345
5 int iWertNeu = Integer.parseInt(iString);
6
7 // dWertNeu enthaelt nun den Wert 22.5
8 double dWertNeu = Double.parseDouble(dString);
Achtung:
Die parse...()-Methoden der Wrapper-Klassen sind statisch. Daher lassen sie
sich direkt über den Klassennamen – ohne Arbeitsobjekt aufrufen.

