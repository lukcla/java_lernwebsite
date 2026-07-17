# Skript-Rohtext Teil 2: Generics – Wildcards bei der Typisierung (Skript S. 600–626)

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 600
Wildcards bei der Typisierung von Generics
Wildcards bei Generics – was ist das und wozu wird’s gebraucht?
Bisher: Wenn wir eine generische Methode mit einem nicht näher
typisierten Übergabeparameter T hatten, so war die zugehörige Klasse
ebenfalls generisch mit T:
1 public class MyGeneric <T> {
2
3 public void foo( ArrayList<T> var) {
4 // Ihr Code ...
5 }
6 }

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 600
Wildcards bei der Typisierung von Generics
Wildcards bei Generics – was ist das und wozu wird’s gebraucht?
Bisher: Wenn wir eine generische Methode mit einem nicht näher
typisierten Übergabeparameter T hatten, so war die zugehörige Klasse
ebenfalls generisch mit T:
1 public class MyGeneric <T> {
2
3 public void foo( ArrayList<T> var) {
4 // Ihr Code ...
5 }
6 }
Manchmal wollen wir aber einer „normalen“, also nicht generischen
Klasse eine Methode hinzufügen, die beispielsweise eine ArrayList oder
ein Couple mit Elementen beliebigen Typs übergeben bekommt.

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 601
Wildcards bei der Typisierung von Generics
Wildcards bei Generics – was ist das und wozu wird’s gebraucht?
O ist von so einem generischen Übergabeparameter zum
Programmierzeitpunkt einfach nicht bekannt, welchen Typ von Daten er
in <> enthält.

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 601
Wildcards bei der Typisierung von Generics
Wildcards bei Generics – was ist das und wozu wird’s gebraucht?
O ist von so einem generischen Übergabeparameter zum
Programmierzeitpunkt einfach nicht bekannt, welchen Typ von Daten er
in <> enthält.
„Holzhammerlösung“ wäre hier:
void foo(Generic<Object> x)

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 601
Wildcards bei der Typisierung von Generics
Wildcards bei Generics – was ist das und wozu wird’s gebraucht?
O ist von so einem generischen Übergabeparameter zum
Programmierzeitpunkt einfach nicht bekannt, welchen Typ von Daten er
in <> enthält.
„Holzhammerlösung“ wäre hier:
void foo(Generic<Object> x)
Problem: Der Übergabeparameter ist aber nicht Object, sondern einfach
zum Programmierzeitpunkt der Methode unbekannt.

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 601
Wildcards bei der Typisierung von Generics
Wildcards bei Generics – was ist das und wozu wird’s gebraucht?
O ist von so einem generischen Übergabeparameter zum
Programmierzeitpunkt einfach nicht bekannt, welchen Typ von Daten er
in <> enthält.
„Holzhammerlösung“ wäre hier:
void foo(Generic<Object> x)
Problem: Der Übergabeparameter ist aber nicht Object, sondern einfach
zum Programmierzeitpunkt der Methode unbekannt.
:Es soll nicht möglich sein, falsche Objektarten in den Generic
einzusetzen.

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 602
Wildcards bei der Typisierung von Generics
Wildcards: Syntax in der Grundform
1 public class MyClass {
2
3 public void foo( Generic<?> list){
4 // Ihr Code
5 }
6 }

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 602
Wildcards bei der Typisierung von Generics
Wildcards: Syntax in der Grundform
1 public class MyClass {
2
3 public void foo( Generic<?> list){
4 // Ihr Code
5 }
6 }
? fungiert hier als Wildcard für einen beliebigen Referenzdatentyp

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 603
Wildcards bei der Typisierung von Generics
Syntax Beschreibung
Generic<?> Generic kann Objektreferenzen beliebigen
Typs enthalten

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 603
Wildcards bei der Typisierung von Generics
Syntax Beschreibung
Generic<?> Generic kann Objektreferenzen beliebigen
Typs enthalten
Generic<? extends Clazz>
Generic kann Objektreferenzen von Clazz
oder von deren Kindklassen (abgeleiteten
Klassen) enthalten.

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 603
Wildcards bei der Typisierung von Generics
Syntax Beschreibung
Generic<?> Generic kann Objektreferenzen beliebigen
Typs enthalten
Generic<? extends Clazz>
Generic kann Objektreferenzen von Clazz
oder von deren Kindklassen (abgeleiteten
Klassen) enthalten.
Generic<? super Clazz>
Generic kann Objektreferenzen von Clazz
oder von deren Elternklassen (Superklassen) enthalten.

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 604
Wildcards bei der Typisierung von Generics: Beispieldaten
Person
-vorname: String
-nachname: String
+Person(vorname: String, nachname: String)
+getVorname(): String
+setVorname(vorname: String): void
+getNachname(): String
+setNachname(nachname: String): void
+toString(): String
RennTeilnehmer
-zeit: double
-strecke: int
+RennTeilnehmer(vorname: String, nachname: String, zeit: double, strecke: int)
+getZeit(): double
+getStrecke(): int
+toString(): String
BobbyCarTeilnehmer
-bobbyCarKlasse: int
+BobbyCarTeilnehmer(vorname: String, nachname: String, gelaufeneZeit: double, gelaufeneStrecke: int, bobbyCarKlasse: int)
+getBobbyCarKlasse(): int
+setBobbyCarKlasse(bobbyCarKlasse: int): void
+toString(): String
Jockey
-namePferd: String
+Jockey(vorname: String, nachname: String, gelaufeneZeit: double, gelaufeneStrecke: int, namePferd: String)
+getNamePferd(): String
+setNamePferd(namePferd: String): void
+toString(): String

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 605
Wildcards bei der Typisierung von Generics: Generic zum Testen
Wir erinnern uns an unsere erste Generic: Couple
1 public class Couple<T> {
2
3 private T member1;
4 private T member2;
5
6 public Couple(T member1, T member2) {
7 this.member1 = member1;
8 this.member2 = member2;
9 } // end constructor

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 606
Wildcards bei der Typisierung von Generics: Generic zum Testen
Wir erinnern uns an unsere erste Generic: Couple
13 public T getMember1() { return member1; }
14
15 public T getMember2() {return member2; }
16
17 public void setMember1(T member1) {
18 this.member1=member1; }
19
20 public void setMember2(T member2) {
21 this.member2 = member2; }

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 607
Wildcards bei der Typisierung von Generics: Generic zum Testen
Wir erinnern uns an unsere erste Generic: Couple
13 public void print() {
14 System.out.println("Member 1: " + member1.toString());
15 System.out.println("--------------------------------");
16 System.out.println("Member 2: " + member2.toString());
17 System.out.println("===============================");
18 } // end method print()
19 } // end class

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 608
Wildcards bei der Typisierung von Generics
Beispiel1: Einfache Zuweisungen
1 RennTeilnehmer lauf1 =
2 new RennTeilnehmer("Asterix","x.",12.5,100);
3 RennTeilnehmer lauf2 =
4 new RennTeilnehmer("Obelix","x.",10.5,100);
5 RennTeilnehmer lauf3 =
6 new RennTeilnehmer("Methusalix","x.",11.5,100);
7 RennTeilnehmer lauf4 =
8 new RennTeilnehmer("Majestix","x.",14.5,100);
Zunächst 4 Objekte erzeugen

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 609
Wildcards bei der Typisierung von Generics
Beispiel1: Einfache Zuweisungen
9 // Typisiert mit RennTeilnehmer
10 Couple<RennTeilnehmer> wettkampfTeam1 =
11 new Couple<RennTeilnehmer>(lauf1,lauf2);
12
13 // Typisiert mit Wildcard -- hier wird aber
14 // die Referenz vom Typ Couple<RennTeilnehmer> zugewiesen
15
16 Couple<?> wettkampfTeam2 = wettkampfTeam1;
Die Typisierung der Inhalte von wettkampeam2 ist mit ? unbekannt!
Die Zuweisung eines typisierten Couple funktioniert aber!

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 610
Wildcards bei der Typisierung von Generics
Beispiel1: Einfache Zuweisungen
17 // Das funktioniert: RennTeilnehmer austauschen
18 // Hier wird in Couple<RennTeilnehmer> eine Objektreferenz
19 // vom Typ RennTeilnehmer ausgetauscht.
20 wettkampfTeam1.setMember1(lauf3);
21
22 // Das funktioniert nicht! lauf4 ist vom Typ RennTeilnehmer
23 wettkampfTeam2 .setMember1( lauf4 );
Die Typisierung der Inhalte von wettkampeam2 ist mit ? unbekannt!
Daher funktioniert das Setzen hier nicht!

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 611
Wildcards bei der Typisierung von Generics
Beispiel2: Wildcard im Übergabeparameter einer Methode
9 public class ProcessData2 {
10
11 public void gibAus( Couple<?> c ) {
12 String s1= c.getMember1().toString();
13 String s2 = c.getMember2().toString();
14 System.out.println(s1);
15 System.out.println(s2);
16 } // end method gibAus()
Methode gibAus() bekommt ein Couple mit unbekanntem Inhaltstyp
übergeben.

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 612
Wildcards bei der Typisierung von Generics
Beispiel2: Wildcard im Übergabeparameter einer Methode
9 public static void main(String [] args) {
10 RennTeilnehmer lauf1 =
11 new RennTeilnehmer("Asterix","x.",12.5,100);
12 RennTeilnehmer lauf2 =
13 new RennTeilnehmer("Obelix","x.",10.5,100);
14 // Inhaltstyp bekannt
15 Couple<RennTeilnehmer> wettkampfTeam1 =
16 new Couple<RennTeilnehmer>(lauf1,lauf2);
17
18 // Inhaltstyp unbekannt, aber bekannt in
19 // zugewiesener Objektreferenz
20 Couple<?> wettkampfTeam2 = wettkampfTeam1;
Anlegen von 2 Couples, die eigentlich eines sind ...

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 613
Wildcards bei der Typisierung von Generics
Beispiel2: Wildcard im Übergabeparameter einer Methode
17 // Ok: Hier wird ein Objekt vom Typ Couple<Laeufer>
18 // uebergeben
19 worker.gibAus(wettkampfTeam1);
20
21 // Ok: Hier wird ein Objekt vom Typ Couple<?>
22 // uebergeben.
23 worker.gibAus(wettkampfTeam2);
24
25 } // end method main()
26 } // end class ProcessData2
Beide Couples können an die Methode gibAus() übergeben werden!

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 614
Wildcards bei der Typisierung von Generics
Upper-bounded Wildcard für den Lesezugri auf Objekte
Problem: Eine Methode
void foo(ArrayList<?> list) möchte die Inhalte der übergebenen
Liste verarbeiten – z.B. deren getter aufrufen.

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 614
Wildcards bei der Typisierung von Generics
Upper-bounded Wildcard für den Lesezugri auf Objekte
Problem: Eine Methode
void foo(ArrayList<?> list) möchte die Inhalte der übergebenen
Liste verarbeiten – z.B. deren getter aufrufen.
Hier muss sichergestellt werden, dass die Generic (hier: ArrayList) mit
den richtigen Objektreferenzen gefüllt ist – z.B. Personen.

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 614
Wildcards bei der Typisierung von Generics
Upper-bounded Wildcard für den Lesezugri auf Objekte
Problem: Eine Methode
void foo(ArrayList<?> list) möchte die Inhalte der übergebenen
Liste verarbeiten – z.B. deren getter aufrufen.
Hier muss sichergestellt werden, dass die Generic (hier: ArrayList) mit
den richtigen Objektreferenzen gefüllt ist – z.B. Personen.
Dies stellen wir sicher mit:
void foo(ArrayList<? extends Person> list)

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 614
Wildcards bei der Typisierung von Generics
Upper-bounded Wildcard für den Lesezugri auf Objekte
Problem: Eine Methode
void foo(ArrayList<?> list) möchte die Inhalte der übergebenen
Liste verarbeiten – z.B. deren getter aufrufen.
Hier muss sichergestellt werden, dass die Generic (hier: ArrayList) mit
den richtigen Objektreferenzen gefüllt ist – z.B. Personen.
Dies stellen wir sicher mit:
void foo(ArrayList<? extends Person> list)
In diesem Beispiel erwartet foo() eine ArrayList, die mit Objektreferenzen
vom Typ Person oder einer Kindklasse vonPerson befüllt ist.

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 615
Wildcards bei der Typisierung von Generics
Beispiel3: Upper-bounded Wildcard für den Lesezugri auf Objekte
1 public class ProcessData3 {
2
3 // wird so nicht compiliert!
4 public void printPersons1( ArrayList<?> candidates ) {
5 // Nicht ok: Inhaltstyp ist unbekannt!
6 // Hier muesste Object verwendet werden
7 for ( Person p : candidates) {
8 // .. weiterer Code
9 } // end for
10 } // end method printPersons1
Datentyp in candidates könnte theoretisch auch String oder Integer sein
– ist hier noch völlig unbekannt! Compiler verweigert die Arbeit!

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 616
Wildcards bei der Typisierung von Generics
Beispiel3: Upper-bounded Wildcard für den Lesezugri auf Objekte
11 public void printPersons2(
12 ArrayList<? extends Person> candidates ) {
13 for (Person p: candidates) {
14 String ausgabe = p.getVorname();
15 ausgabe += " " + p.getNachname();
16 System.out.println(ausgabe);
17 } // end for
18 } // end method printPersons2()
Datentyp in candidates ist hier vom Typ Person oder einer Kindklasse
von Person. Compiler sagt hier: ok!

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 617
Wildcards bei der Typisierung von Generics
Beispiel3: Upper-bounded Wildcard für den Lesezugri auf Objekte
19 public static void main(String [] args) {
20
21 Person pers1 = new Person("Asterix","x.");
22 RennTeilnehmer lauf2 =
23 new RennTeilnehmer("Obelix","x.",10.5,100);
24 RennTeilnehmer lauf3 =
25 new RennTeilnehmer("Methusalix","x.",11.5,100);
26 RennTeilnehmer lauf4 =
27 new RennTeilnehmer("Majestix","x.",14.5,100);
28 ProcessData3 worker = new ProcessData3(); // Arbeitsobjekt
Anwendende main()-Methode erzeugt einige Personen-Objekte

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 618
Wildcards bei der Typisierung von Generics
Beispiel3: Upper-bounded Wildcard für den Lesezugri auf Objekte
31 ArrayList<Person> teil1 =
32 new ArrayList<Person>();
33 teil1.add(pers1);
34 teil1.add(lauf2);
35
36 ArrayList<RennTeilnehmer> teil2 =
37 new ArrayList<RennTeilnehmer>();
38 teil2.add(lauf3);
39 teil2.add(lauf4);
... danach 2 ArrayList-Objekte für Objekte vom Typ Person oder
Kindklasse

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 619
Wildcards bei der Typisierung von Generics
Beispiel3: Upper-bounded Wildcard für den Lesezugri auf Objekte
40 // ArrayList, typisiert auf String
41 ArrayList<String> teil3 =
42 new ArrayList<String>();
43 teil3.add("Erna");
44 teil3.add("Hugo");
... und noch eine ArrayList mit String-Inhalt

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 620
Wildcards bei der Typisierung von Generics
Beispiel3: Upper-bounded Wildcard für den Lesezugri auf Objekte
46 // Uebergabe von ArrayList<Person>: Ok
47 worker.printPersons2(teil1);
48
49 // Uebergabe von ArrayList<RennTeilnehmer>: Ok
50 worker.printPersons2(teil2);
51
52 // Uebergabe von ArrayList<String>: NICHT Ok
53 worker.printPersons2(teil3);
54 } // end method main()
55 } // end class
Methode printPersons2() akzeptiert die ArrayList<String> nicht!

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 621
Wir fassen zur Upper-Bound-Wildcard zusammen:
Die Upper-bound-Wildcard wird immer verwendet, wenn der Inhalt
eines generischen Übergabeparameters gelesen werden soll.

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 621
Wir fassen zur Upper-Bound-Wildcard zusammen:
Die Upper-bound-Wildcard wird immer verwendet, wenn der Inhalt
eines generischen Übergabeparameters gelesen werden soll.
Beim formalen Parameter einer Methode wird sie formuliert mit:
void foo(Generic<? extends Clazz> var)

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 621
Wir fassen zur Upper-Bound-Wildcard zusammen:
Die Upper-bound-Wildcard wird immer verwendet, wenn der Inhalt
eines generischen Übergabeparameters gelesen werden soll.
Beim formalen Parameter einer Methode wird sie formuliert mit:
void foo(Generic<? extends Clazz> var)
Das bedeutet: Der aktuelle Parameter muss mit Typ Clazz oder einer
Kindklasse von Clazz typisiert sein.

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 622
Wildcards bei der Typisierung von Generics
Beispiel4: Lower-bounded Wildcard für den Schreibzugri auf Objekte
1 public class ProcessData4 {
2 public void addCandidatesNotOk1(
3 ArrayList<? extends RennTeilnehmer> chosenCandidates ,
4 ArrayList<? extends RennTeilnehmer> newCandidates,
5 double hoechstZeit) {
6 for (RennTeilnehmer l : newCandidates) {
7 if (l.getZeit() <= hoechstZeit) {
8 chosenCandidates.add(l); // funktioniert nicht!
9 } // end if
10 } // end for
11 } // end method
Nicht ok! extends reicht nicht, um die Liste zu beschreiben!

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 623
Problem mit der Upper-bound-Wildcard hier:
extends reicht beim Beschreiben der übergebenen ArrayList nicht aus.
Person RennTeilnehmer
Jockey = BobbyCarTeilnehmer

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 623
Problem mit der Upper-bound-Wildcard hier:
extends reicht beim Beschreiben der übergebenen ArrayList nicht aus.
Es könnte geschehen, dass hier versucht wird, Objekte des falschen
Datentyps einzufügen.
Person RennTeilnehmer
Jockey = BobbyCarTeilnehmer

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 624
Wildcards bei der Typisierung von Generics
Beispiel4: Lower-bounded Wildcard für den Schreibzugri auf Objekte
12 public void addCandidatesOk(
13 ArrayList<? super RennTeilnehmer> chosenCandidates ,
14 ArrayList<? extends RennTeilnehmer> newCandidates,
15 double hoechstZeit) {
16 for (RennTeilnehmer l : newCandidates) {
17 if (l.getZeit() <= hoechstZeit) {
18 chosenCandidates.add(l); // So funktioniert's
19 } // end if
20 } // end for
21 } // end method
So ok! super verwenden, um die Liste zu beschreiben!

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 625
Wildcards bei der Typisierung von Generics
Beispiel4: Lower-bounded Wildcard für den Schreibzugri auf Objekte
12 public void printCandidates(
13 ArrayList<? super RennTeilnehmer> chosenCandidates ) {
14 // Lesen
15 for (RennTeilnehmer l : chosenCandidates) {
16 String s=l.toString();
17 System.out.println(s);
18 } // end for
19 } // end method
Nicht ok! super funktioniert nicht für Lesezugri!

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 626
Problem mit der Lower-bound-Wildcard hier:
super bewirkt: Es wird RennTeilnehmer oder eine ihrer Superklassen als
Typisierung für chosenCandidates verlangt.

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 626
Problem mit der Lower-bound-Wildcard hier:
super bewirkt: Es wird RennTeilnehmer oder eine ihrer Superklassen als
Typisierung für chosenCandidates verlangt.
Im Schleifenkopf for (RennTeilnehmer l : chosenCandidates)
wird die Laufvariable l als RennTeilnehmer typisiert.

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 626
Problem mit der Lower-bound-Wildcard hier:
super bewirkt: Es wird RennTeilnehmer oder eine ihrer Superklassen als
Typisierung für chosenCandidates verlangt.
Im Schleifenkopf for (RennTeilnehmer l : chosenCandidates)
wird die Laufvariable l als RennTeilnehmer typisiert.
In der ArrayList chosenCandidates könnten aber auch Elemente einer
Superklasse von RennTeilnehmer stecken.

Generische Klassen (Generics) Wildcards bei der Typisierung von Generics Prof. Dr. Ute Matecki 626
Problem mit der Lower-bound-Wildcard hier:
super bewirkt: Es wird RennTeilnehmer oder eine ihrer Superklassen als
Typisierung für chosenCandidates verlangt.
Im Schleifenkopf for (RennTeilnehmer l : chosenCandidates)
wird die Laufvariable l als RennTeilnehmer typisiert.
In der ArrayList chosenCandidates könnten aber auch Elemente einer
Superklasse von RennTeilnehmer stecken.
Hier wäre die Typisierung von l nicht mehr korrekt!

