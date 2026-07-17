# Skript-Rohtext Teil 2: Generics – Das Java-Collection-Framework (Skript S. 627–685)

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 627
Das Java-Collection-Framework
Was sind Java-Collections?
Spezielle Generics der Java-API

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 627
Das Java-Collection-Framework
Was sind Java-Collections?
Spezielle Generics der Java-API
Behälter bzw. Datenstrukturen, gedacht zur Verwaltung von Objekten

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 628
Das Java-Collection-Framework
Welche Arten von Collectons gibt es? (frei nach [? ],S. 668)
Listen: Elemente werden am Ende eingefügt. Zugri kann dann an
beliebiger Stelle erfolgen.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 628
Das Java-Collection-Framework
Welche Arten von Collectons gibt es? (frei nach [? ],S. 668)
Listen: Elemente werden am Ende eingefügt. Zugri kann dann an
beliebiger Stelle erfolgen.
Queues (Warteschlangen): Lineare Datenstruktur, der die Elemente
nach dem Prinzip „First In, First Out“ (FIFO) entnommen werden.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 628
Das Java-Collection-Framework
Welche Arten von Collectons gibt es? (frei nach [? ],S. 668)
Listen: Elemente werden am Ende eingefügt. Zugri kann dann an
beliebiger Stelle erfolgen.
Queues (Warteschlangen): Lineare Datenstruktur, der die Elemente
nach dem Prinzip „First In, First Out“ (FIFO) entnommen werden.
Sets (Mengen): Sie können keine Duplikate ihrer Elemente enthalten.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 628
Das Java-Collection-Framework
Welche Arten von Collectons gibt es? (frei nach [? ],S. 668)
Listen: Elemente werden am Ende eingefügt. Zugri kann dann an
beliebiger Stelle erfolgen.
Queues (Warteschlangen): Lineare Datenstruktur, der die Elemente
nach dem Prinzip „First In, First Out“ (FIFO) entnommen werden.
Sets (Mengen): Sie können keine Duplikate ihrer Elemente enthalten.
Maps: Eine Map <K,V > bezeichnet eine Datenstruktur, die Schlüssel
(Keys) auf Werte(objekte) (Values) abbildet. So könnte beispielsweise
eine Personalnummer (Schlüssel) auf ein Personen-Objekt (Wert)
abgebildet werden.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 629
Das Java-Collection-Framework
Organisation und Zugri bei Collections (frei nach [? ],S. 668)
geordnet: Eine geordnete Datenstruktur speichert ihre Elemente in der
Reihenfolge ab, in der sie abgespeichert wurden.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 629
Das Java-Collection-Framework
Organisation und Zugri bei Collections (frei nach [? ],S. 668)
geordnet: Eine geordnete Datenstruktur speichert ihre Elemente in der
Reihenfolge ab, in der sie abgespeichert wurden.
sortiert: Eine sortierte Datenstruktur ordnet ihre Elemente mit Hilfe
einer Vergleichsrelation (beispielsweise alphabetisch oder nach
Personalnummern)

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 629
Das Java-Collection-Framework
Organisation und Zugri bei Collections (frei nach [? ],S. 668)
geordnet: Eine geordnete Datenstruktur speichert ihre Elemente in der
Reihenfolge ab, in der sie abgespeichert wurden.
sortiert: Eine sortierte Datenstruktur ordnet ihre Elemente mit Hilfe
einer Vergleichsrelation (beispielsweise alphabetisch oder nach
Personalnummern)
sequentieller Zugri: Es wird (in Java mit einem Iterator) immer das
nächste, nächste, nächste ... Element geliefert.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 629
Das Java-Collection-Framework
Organisation und Zugri bei Collections (frei nach [? ],S. 668)
geordnet: Eine geordnete Datenstruktur speichert ihre Elemente in der
Reihenfolge ab, in der sie abgespeichert wurden.
sortiert: Eine sortierte Datenstruktur ordnet ihre Elemente mit Hilfe
einer Vergleichsrelation (beispielsweise alphabetisch oder nach
Personalnummern)
sequentieller Zugri: Es wird (in Java mit einem Iterator) immer das
nächste, nächste, nächste ... Element geliefert.
wahlfreier Zugri: Wir können frei auf die Elemente an einer
bestimmten Position zugreifen, ohne uns an eine Reihenfolge halten zu
müssen. Wird bei Java-Collections z.B. über eine get(int index)-Methode
realisiert.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 630
Das Java-Collection-Framework
Wichtigste Eigenschaen der Java-Collections (frei nach [? ],S. 668)
Listen
Typ Ordnung Zugri DuplikateSonstiges
ArrayList geordnet wahlfrei über
Index
ja Implementiert
List;schneller Zugri

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 630
Das Java-Collection-Framework
Wichtigste Eigenschaen der Java-Collections (frei nach [? ],S. 668)
Listen
Typ Ordnung Zugri DuplikateSonstiges
ArrayList geordnet wahlfrei über
Index
ja Implementiert
List;schneller Zugri
LinkedList
geordnet wahlfrei über
Index / sequentiell nächstes
Element
ja schnelles Einfügen;
Implementiert List
und Queue und Deque

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 630
Das Java-Collection-Framework
Wichtigste Eigenschaen der Java-Collections (frei nach [? ],S. 668)
Listen
Typ Ordnung Zugri DuplikateSonstiges
ArrayList geordnet wahlfrei über
Index
ja Implementiert
List;schneller Zugri
LinkedList
geordnet wahlfrei über
Index / sequentiell nächstes
Element
ja schnelles Einfügen;
Implementiert List
und Queue und Deque
Vector
geordnet wahlfrei über
Index
ja Implementiert List;
synchronisiert (für
Thread-Zugrie)

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 630
Das Java-Collection-Framework
Wichtigste Eigenschaen der Java-Collections (frei nach [? ],S. 668)
Listen
Typ Ordnung Zugri DuplikateSonstiges
ArrayList geordnet wahlfrei über
Index
ja Implementiert
List;schneller Zugri
LinkedList
geordnet wahlfrei über
Index / sequentiell nächstes
Element
ja schnelles Einfügen;
Implementiert List
und Queue und Deque
Vector
geordnet wahlfrei über
Index
ja Implementiert List;
synchronisiert (für
Thread-Zugrie)
Stack
geordnet sequentiell ja Last In, First Out (LIFO);
Implementiert List

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 631
Das Java-Collection-Framework
Wichtigste Eigenschaen der Java-Collections (frei nach [? ],S. 668)
Queues (Warteschlangen)
Typ Ordnung Zugri DuplikateSonstiges
LinkedList geordnet wahlfrei über
Index / sequentiell nächstes
Element
ja schnelles Einfügen;
Implementiert List
und Queue und Deque

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 631
Das Java-Collection-Framework
Wichtigste Eigenschaen der Java-Collections (frei nach [? ],S. 668)
Queues (Warteschlangen)
Typ Ordnung Zugri DuplikateSonstiges
LinkedList geordnet wahlfrei über
Index / sequentiell nächstes
Element
ja schnelles Einfügen;
Implementiert List
und Queue und Deque
PriorityQueue
sortiert sequentiell
nächstes
Element
ja Implementiert Queue

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 632
Das Java-Collection-Framework
Wichtigste Eigenschaen der Java-Collections (frei nach [? ],S. 668)
Sets (Mengen)
Typ Ordnung Zugri DuplikateSonstiges
HashSet ungeordnetwahlfrei nein schneller Zugri;
implementiert Set

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 632
Das Java-Collection-Framework
Wichtigste Eigenschaen der Java-Collections (frei nach [? ],S. 668)
Sets (Mengen)
Typ Ordnung Zugri DuplikateSonstiges
HashSet ungeordnetwahlfrei nein schneller Zugri;
implementiert Set
TreeSet
sortiert wahlfrei nein Implementiert Set

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 633
Das Java-Collection-Framework
Wichtigste Eigenschaen der Java-Collections (frei nach [? ],S. 668)
Maps
Typ Ordnung Zugri Duplikate Sonstiges
HashMap ungeordnetwahlfrei über
Schlüssel
Schlüssel: nein
Werte: ja
Implementiert
Map

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 633
Das Java-Collection-Framework
Wichtigste Eigenschaen der Java-Collections (frei nach [? ],S. 668)
Maps
Typ Ordnung Zugri Duplikate Sonstiges
HashMap ungeordnetwahlfrei über
Schlüssel
Schlüssel: nein
Werte: ja
Implementiert
Map
TreeMap
sortiert wahlfrei über
Schlüssel
Schlüssel: nein
Werte: ja
Implementiert
NavigableMap

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 634
Das Java-Collection-Framework
Java-Collections implementieren einige der folgenden Interfaces
(frei nach [? ],S. 668)
«Interface»
java.lang.Iterable «Interface»
java.util.Collection
«Interface»
java.util.Set
«Interface»
java.util.List
«Interface»
java.util.Queue
«Interface»
java.util.Map
«Interface»
SortedMap
«Interface»
java.util.SortedSet
«Interface»
java.lang.BlockingQueue
T T
T T T
T T
K
V
K
V
«Interface»
K
V
java.lang.NavigableMap
Platzhalter-Datentypen werden
in der UML als Template-Parameter in angegeben.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 635
Das Java-Collection-Framework
Wir betrachten folgende Collections genauer:
ArrayList

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 635
Das Java-Collection-Framework
Wir betrachten folgende Collections genauer:
ArrayList
HashMap

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 635
Das Java-Collection-Framework
Wir betrachten folgende Collections genauer:
ArrayList
HashMap
HashSet

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 635
Das Java-Collection-Framework
Wir betrachten folgende Collections genauer:
ArrayList
HashMap
HashSet
Vector (in Verbindung mit Threads ...)

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 636
Die Klasse ArrayList
Eigenschaen von ArrayList
Speichert die ihr übergebenen Objekte linear (geordnet) ab.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 636
Die Klasse ArrayList
Eigenschaen von ArrayList
Speichert die ihr übergebenen Objekte linear (geordnet) ab.
Ist unsortiert, kann aber mit einer Methode sortieren.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 636
Die Klasse ArrayList
Eigenschaen von ArrayList
Speichert die ihr übergebenen Objekte linear (geordnet) ab.
Ist unsortiert, kann aber mit einer Methode sortieren.
Kann Objekte hinzufügen oder entfernen

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 636
Die Klasse ArrayList
Eigenschaen von ArrayList
Speichert die ihr übergebenen Objekte linear (geordnet) ab.
Ist unsortiert, kann aber mit einer Methode sortieren.
Kann Objekte hinzufügen oder entfernen
Ist nicht Thread-sicher

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 637
Die Klasse ArrayList
Wichtigste Methoden von ArrayList
(boolean add(T element))

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 637
Die Klasse ArrayList
Wichtigste Methoden von ArrayList
(boolean add(T element))
(void clear())

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 637
Die Klasse ArrayList
Wichtigste Methoden von ArrayList
(boolean add(T element))
(void clear())
(boolean isEmpty())

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 637
Die Klasse ArrayList
Wichtigste Methoden von ArrayList
(boolean add(T element))
(void clear())
(boolean isEmpty())

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 637
Die Klasse ArrayList
Wichtigste Methoden von ArrayList
(boolean add(T element))
(void clear())
(boolean isEmpty())
(T remove(Object o))

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 637
Die Klasse ArrayList
Wichtigste Methoden von ArrayList
(boolean add(T element))
(void clear())
(boolean isEmpty())
(T remove(Object o))
(boolean remove(int index))

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 637
Die Klasse ArrayList
Wichtigste Methoden von ArrayList
(boolean add(T element))
(void clear())
(boolean isEmpty())
(T remove(Object o))
(boolean remove(int index))
(int size())

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 637
Die Klasse ArrayList
Wichtigste Methoden von ArrayList
(boolean add(T element))
(void clear())
(boolean isEmpty())
(T remove(Object o))
(boolean remove(int index))
(int size())
(void sort(Comparator<? super T> comp))

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 638
Die Klasse ArrayList
Beispielszenario: sortierbare Personenlisten
 - persnr: int
 - nachname: String
 - vorname: String
 + compareTo( pers2: Object): int
 + toString(): String
 + getPersnr(): int
 + setPersnr(persnr: int)
 + setNachname( nachname: String)
 + getNachname(): String
 + setVorname( vorname: String)
 + getVorname(): String
+ Person( vorname: String, nachname: String, persnr: int)
«Interface»
Comparable
UseArrayList
«Interface»
Comparator
ComparePerson
 + compare( o1: T, o1: T)
 + compare( o1 : Person, o2: Person)
 + compareTo( o1: T, o1: T)
Person
T
 + print(liste: ArrayList<Person>)
 + sort(liste: ArrayList<Person>)
+ removePers2(liste: ArrayList<Person>, persnr: int)
+ removePers1(liste: ArrayList<Person>, persnr: int)
+ findPerson(liste: ArrayList<Person>, persnr: int): Person
T

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 639
Die Klasse ArrayList
Klasse Person – implementiert Comparable – Teil1
1 public class Person implements Comparable {
2 private String vorname;
3 private String nachname;
4 private int persnr;
Klasse implementiert nun eine Vergleichsmethode des Interfaces
Comparable

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 640
Die Klasse ArrayList
Klasse Person – implementiert Comparable – Teil2
5 public Person(String vorname,
6 String nachname, int persnr) {
7
8 this.vorname = vorname;
9 this.nachname = nachname;
10 this.persnr = persnr;
11 } // end constructor

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 641
Die Klasse ArrayList
Klasse Person – implementiert Comparable – Teil3
12 public String getVorname() { return vorname; }
13
14 public void setVorname(String vorname) {
15 this.vorname = vorname; }
16
17 public String getNachname() { return nachname; }
18
19 public void setNachname(String nachname) {
20 this.nachname = nachname; }
21
22 public int getPersnr() { return persnr; }
23
24 public void setPersnr(int persnr) {this.persnr = persnr;}

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 642
Die Klasse ArrayList
Klasse Person – implementiert Comparable – Teil4
25 // Aus Klasse Object ueberschrieben
26 @Override
27 public String toString() {
28 String s = vorname + " "
29 + nachname + " " + persnr;
30 return s;
31 } // end method

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 643
Die Klasse ArrayList
Klasse Person – implementiert Comparable – Teil5
32 // Aus Interface Comparable
33 @Override
34 public int compareTo(Object pers2) {
35 Person p = (Person) pers2;
36
37 return (this.persnr - p.getPersnr());
38 } // end method
39 } // end class
Klasse implementiert die Vergleichsmethode des Interfaces Comparable
wenn this.persnr < pers2.persnr: Returnwert < 0

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 643
Die Klasse ArrayList
Klasse Person – implementiert Comparable – Teil5
32 // Aus Interface Comparable
33 @Override
34 public int compareTo(Object pers2) {
35 Person p = (Person) pers2;
36
37 return (this.persnr - p.getPersnr());
38 } // end method
39 } // end class
Klasse implementiert die Vergleichsmethode des Interfaces Comparable
wenn this.persnr < pers2.persnr: Returnwert < 0
wenn this.persnr > pers2.persnr: Returnwert > 0

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 643
Die Klasse ArrayList
Klasse Person – implementiert Comparable – Teil5
32 // Aus Interface Comparable
33 @Override
34 public int compareTo(Object pers2) {
35 Person p = (Person) pers2;
36
37 return (this.persnr - p.getPersnr());
38 } // end method
39 } // end class
Klasse implementiert die Vergleichsmethode des Interfaces Comparable
wenn this.persnr < pers2.persnr: Returnwert < 0
wenn this.persnr > pers2.persnr: Returnwert > 0
wenn this.persnr == pers2.persnr: Returnwert == 0

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 644
Die Klasse ArrayList
Klasse ComparePerson – implementiert Comparator
1 import java.util.Comparator;
2 public class ComparePerson
3 implements Comparator<Person> {
4
5 // Implementiert Methode aus Comparator
6 @Override
7 public int compare(Person p1, Person p2) {
8 return p1.compareTo(p2);
9 } // end method
10 } // end class
Klasse implementiert die Vergleichsmethode des Interfaces Comparator

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 645
Die Klasse ArrayList
Klasse UseArrayList – Teil 1
1 import java.util.ArrayList;
2
3 public class UseArrayList {
4
5 public void print(ArrayList<Person> liste) {
6
7 for (Person p : liste) {
8 System.out.println(p.toString());
9 } // end for
10 System.out.println("----------------------");
11 } // end method
Einfache Ausgabemethode mit Iterator-Schleife

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 646
Die Klasse ArrayList
Klasse UseArrayList – Teil 2
12 public Person findPerson (ArrayList<Person> liste,
13 int persnr) {
14 Person result=null ;
15
16 for (Person p : liste) { // Iterator-Schleife
17 if (p.getPersnr() == persnr) { // Wenn Treffer ...
18 result = p; // ... diesen merken!
19 } // end if
20 } // end for
21 return result; // letzten Treffer zurueckgeben
22 } // end method
Um ein Objekt mit einem bestimmten Suchkriterium (Schlüssel) zu
finden, muss ggf. die gesamte Liste durchlaufen werden!

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 647
Die Klasse ArrayList
Klasse UseArrayList – Teil 3
23 public void removePers1 (ArrayList<Person> liste,
24 int persnr) {
25
26 for (Person p : liste) { // Iterator-Schleife
27 if (p.getPersnr() == persnr) { // Wenn Treffer ...
28
29 liste.remove(p); // .. diesen entfernen!
30 } // end if
31 } // end for
32 } // end method
Um ein Objekt mit einem bestimmten Suchkriterium (Schlüssel) zu
entfernen, muss ggf. die gesamte Liste durchlaufen werden!

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 648
Die Klasse ArrayList
Klasse UseArrayList – Teil 4
33 public void removePers2 (ArrayList<Person> liste,
34 int persnr) {
35
36 for (int i=0; i<liste.size(); i++) {
37 Person p = liste.get(i);
38 if (p.getPersnr() == persnr) { // Wenn Treffer ...
39 liste.remove(i) ; // ... diesen entfernen!
40 } // end if
41 } // end for
42 } // end method
Auch hier kompletter Durchlauf – wahlfrei mit get(int index) und
remove(int index).

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 649
Die Klasse ArrayList
Klasse UseArrayList – Teil 5
43 public void sort(ArrayList<Person> liste) {
44
45 liste.sort(new ComparePerson());
46
47 } // end method
48
49 } // end class
sort()-Methode von ArrayList bekommt unsere
Comparator-Implementierung übergeben. So weiß die ArrayList, nach
welchem Ordnungskriterium (hier: Personalnr.) sortiert wird.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 650
Die Klasse ArrayList
Klasse MainArrayList– Teil 1
1 import java.util.ArrayList;
2
3 public class MainArrayList {
4
5 public static void main(String[] args) {
6
7 // Ein Arbeitsobjekt
8 UseArrayList worker = new UseArrayList();

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 651
Die Klasse ArrayList
Klasse MainArrayList– Teil 1
9 // 6 Personen
10 Person p1 = new Person("Emil","Eumel",2345);
11 Person p2 = new Person("Erna","Etepetete",1245);
12 Person p3 = new Person("Hugo","Helmchen",4789);
13 Person p4 = new Person("Klaus","Kohlpfennig",2123);
14 Person p5 = new Person("Rita","Rettich",1260);
15 Person p6 = new Person("Herbert","Hacker",1349);
16
17 // Eine noch leere ArrayList
18 ArrayList<Person> liste1 = new ArrayList<>();

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 652
Die Klasse ArrayList
Klasse MainArrayList– Teil 1
19 // 4 Elemente einhaengen
20 liste1.add(p1);
21 liste1.add(p2);
22 liste1.add(p3);
23 liste1.add(p4);
24
25 // Liste unsortiert ausgeben
26 worker.print(liste1);

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 653
Die Klasse ArrayList
Klasse MainArrayList– Ausgabe Teil 1
1 Emil Eumel 2345
2 Erna Etepetete 1245
3 Hugo Helmchen 4789
4 Klaus Kohlpfennig 2123
5 ----------------------

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 654
Die Klasse ArrayList
Klasse MainArrayList– Teil 2
27 // Sortieren
28 worker.sort(liste1);
29
30 // Sortierte Liste ausgeben
31 worker.print(liste1);
32
33 // p1 entfernen
34 worker.removePers1(liste1, 2345);
35
36 // reduzierte Liste ausgeben
37 worker.print(liste1);

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 655
Die Klasse ArrayList
Klasse MainArrayList– Ausgabe Teil 2
6 Erna Etepetete 1245
7 Klaus Kohlpfennig 2123
8 Emil Eumel 2345
9 Hugo Helmchen 4789
10 ----------------------
11 Erna Etepetete 1245
12 Klaus Kohlpfennig 2123
13 Hugo Helmchen 4789
14 ----------------------
Liste ist nun nach Persnr. sortiert. Beim removePers1(...)-Aufruf wird
Emil Eumel entfernt.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 656
Die Klasse ArrayList
Klasse MainArrayList– Teil 3
38 // p4 entfernen
39 worker.removePers2(liste1, 2123);
40
41 // Weiter reduzierte Liste ausgeben
42 worker.print(liste1);

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 657
Die Klasse ArrayList
Klasse MainArrayList– Ausgabe Teil 3
15 Erna Etepetete 1245
16 Hugo Helmchen 4789
17 ----------------------
Beim removePers2(...)-Aufruf wird Klaus Kohlpfennig entfernt.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 658
Die Klasse ArrayList
Klasse MainArrayList– Teil 4
38 // 2 weitere Elemente hinzufuegen
39 liste1.add(p5);
40 liste1.add(p6);
41
42 // Nochmal sortieren und ausgeben
43 worker.sort(liste1);
44 worker.print(liste1);
45
46 } // end method main()
47 } // end class

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 659
Die Klasse ArrayList
Klasse MainArrayList– Ausgabe Teil 4
18 Erna Etepetete 1245
19 Rita Rettich 1260
20 Herbert Hacker 1349
21 Hugo Helmchen 4789
22 ----------------------
Nach dem Einfügen von Rita Rettich und Hugo Hacker wurde nochmals
nach Persnr. sortiert.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 660
Die Klasse ArrayList
Zusammenfassung
In einer ArrayList können Elemente wahlfrei (mit Index) zugegrien
werden.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 660
Die Klasse ArrayList
Zusammenfassung
In einer ArrayList können Elemente wahlfrei (mit Index) zugegrien
werden.
Über eine ArrayList können wir iterieren.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 660
Die Klasse ArrayList
Zusammenfassung
In einer ArrayList können Elemente wahlfrei (mit Index) zugegrien
werden.
Über eine ArrayList können wir iterieren.
Einer ArrayList können wir Elemente hinzufügen und sie wieder
entfernen.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 660
Die Klasse ArrayList
Zusammenfassung
In einer ArrayList können Elemente wahlfrei (mit Index) zugegrien
werden.
Über eine ArrayList können wir iterieren.
Einer ArrayList können wir Elemente hinzufügen und sie wieder
entfernen.
Eine ArrayList ist unsortiert – die Elemente werden geordnet
hinzugefügt.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 660
Die Klasse ArrayList
Zusammenfassung
In einer ArrayList können Elemente wahlfrei (mit Index) zugegrien
werden.
Über eine ArrayList können wir iterieren.
Einer ArrayList können wir Elemente hinzufügen und sie wieder
entfernen.
Eine ArrayList ist unsortiert – die Elemente werden geordnet
hinzugefügt.
Eine ArrayList kann aber sortiert werden mit ihrer Methode sort().

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 660
Die Klasse ArrayList
Zusammenfassung
In einer ArrayList können Elemente wahlfrei (mit Index) zugegrien
werden.
Über eine ArrayList können wir iterieren.
Einer ArrayList können wir Elemente hinzufügen und sie wieder
entfernen.
Eine ArrayList ist unsortiert – die Elemente werden geordnet
hinzugefügt.
Eine ArrayList kann aber sortiert werden mit ihrer Methode sort().
Diese benötigt eine Implementierung von Comparator, damit sie
weiß,nach welchem Ordnungskriterium sortiert werden soll.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 661
Die Klasse HashMap
Eigenschaen von Maps – speziell HashMap
Objekte (Values) werden nach einem Schlüssel (Key) eingeordnet.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 661
Die Klasse HashMap
Eigenschaen von Maps – speziell HashMap
Objekte (Values) werden nach einem Schlüssel (Key) eingeordnet.
Dieser Key ist innerhalb der Map nicht duplizierbar.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 661
Die Klasse HashMap
Eigenschaen von Maps – speziell HashMap
Objekte (Values) werden nach einem Schlüssel (Key) eingeordnet.
Dieser Key ist innerhalb der Map nicht duplizierbar.
Beispiel: Personen (Values) werden nach ihrer Personalnummer (Key)
eingeordnet.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 661
Die Klasse HashMap
Eigenschaen von Maps – speziell HashMap
Objekte (Values) werden nach einem Schlüssel (Key) eingeordnet.
Dieser Key ist innerhalb der Map nicht duplizierbar.
Beispiel: Personen (Values) werden nach ihrer Personalnummer (Key)
eingeordnet.
Für Value und Key gibt es jeweils einen gesonderten
Typ-Formalparameter: K und V

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 661
Die Klasse HashMap
Eigenschaen von Maps – speziell HashMap
Objekte (Values) werden nach einem Schlüssel (Key) eingeordnet.
Dieser Key ist innerhalb der Map nicht duplizierbar.
Beispiel: Personen (Values) werden nach ihrer Personalnummer (Key)
eingeordnet.
Für Value und Key gibt es jeweils einen gesonderten
Typ-Formalparameter: K und V
Beispiel: HashMap<Integer,Person> map = new HashMap<>();
Hier: K=Integer, V=Person

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 662
Die Klasse HashMap
Klasse MainHashMap– Teil 1
1 import java.util.HashMap;
2 public class MainHashMap {
3
4 public void printPersMap(
5 HashMap<Integer,Person> map,int maxKey) {
6
7 for (int i=0; i<maxKey; i++) {
8 if(map.containsKey(i)) { // Wenn key in map
9 // Objekt mit Key i abfragen und ausgeben
10 Person p = map.get(i);
11 System.out.println("Person: "+i +" " + p.toString());
12 } // end if
HashMap ist nicht iterierbar – daher Zählschleife

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 663
Die Klasse HashMap
Klasse MainHashMap– Teil 1
1 import java.util.HashMap;
2 public class MainHashMap {
3
4 public void printPersMap(
5 HashMap<Integer,Person> map,int maxKey) {
6
7 for (int i=0; i<maxKey; i++) {
8 if(map.containsKey(i)) { // Wenn key in map
9 // Value mit Key i abfragen und ausgeben
10 Person p = map.get(i);
11 System.out.println("Person: "+i +" " + p.toString());
12 } // end if
Abfragen, ob ein Value mit Key i in der Map ist.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 664
Die Klasse HashMap
Klasse MainHashMap– Teil 2
13 else {
14 // Sonst Leer-Meldung bei Key i
15 System.out.println(i+" leer");
16 }// end else
17 } // end for
18 System.out.println("---------------");
19 } // end method printPersMap()
Abfragen, ob ein Value mit Key i in der Map ist.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 665
Die Klasse HashMap
Klasse MainHashMap– Teil 3
20 public static void main(String[] args) {
21
22 // Worker-Objekt anlegen
23 MainHashMap worker = new MainHashMap();
24
25 Person p1 = new Person("Emil","Eumel",1);
26 Person p2 = new Person("Erna","Etepetete",3);
27 Person p3 = new Person("Hugo","Helmchen",5);
28 Person p4 = new Person("Klaus","Kohlpfennig",6);
29 Person p5 = new Person("Rita","Rettich",8);
30 Person p6 = new Person("Herbert","Hacker",9);
Die 6 Personen werden die Values

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 666
Die Klasse HashMap
Klasse MainHashMap– Teil 4
31 // Eine leere HashMap anlegen
32 HashMap<Integer,Person> map = new HashMap<>() ;
33
34 map.put(p1.getPersnr(), p1);
35 map.put(p2.getPersnr(),p2);
36 map.put(p3.getPersnr(),p3);
37
38 // Map ausgeben
39 worker.printPersMap(map, 10);
Aktueller Typ-Parameter K=Integer, Aktueller Typ-Parameter V=Person

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 667
Die Klasse HashMap
Klasse MainHashMap– Teil 4
31 // Eine leere HashMap anlegen
32 HashMap<Integer,Person> map = new HashMap<>();
33
34 map.put(p1.getPersnr(), p1);
35 map.put(p2.getPersnr(),p2);
36 map.put(p3.getPersnr(),p3);
37
38
39 // Map ausgeben
40 worker.printPersMap(map, 10);
Der Map werden 3 Personen hinzugefügt. Schlüssel ist jeweils die
Personalnummer.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 668
Die Klasse HashMap
Ausgabe der Klasse MainHashMap– Teil 4
1 0 leer
2 Person: 1 Emil Eumel 1
3 2 leer
4 Person: 3 Erna Etepetete 3
5 4 leer
6 Person: 5 Hugo Helmchen 5
7 6 leer
8 7 leer
9 8 leer
10 9 leer
Die 3 eingehängten Objekte werden ausgegeben.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 669
Die Klasse HashMap
Klasse MainHashMap– Teil 5
40 map.replace(3, p2, p4);
41
42 // Map ausgeben
43 worker.printPersMap(map, 10);
Bei Key=3 (Personalnr.) wird Value p2 (Etepetete) gegen p4
(Kohlpfennig) ausgetauscht. Persnr. stimmt nicht mehr mit Key überein!

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 670
Die Klasse HashMap
Ausgabe der Klasse MainHashMap– Teil 5
1 0 leer
2 Person: 1 Emil Eumel 1
3 2 leer
4 Person: 3 Klaus Kohlpfennig 6
5 4 leer
6 Person: 5 Hugo Helmchen 5
7 6 leer
8 7 leer
9 8 leer
10 9 leer
Bei Key 3 sitzt nun Kohlpfennig. Er ersetzt Etepetete.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 671
Die Klasse HashMap
Klasse MainHashMap– Teil 6
44 // Getauschten Kohlpfennig entfernen
45 map.remove(3);
46
47 // Map ausgeben
48 worker.printPersMap(map, 10);
Bei Key=3 (Personalnr.) wird Value entfernt.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 672
Die Klasse HashMap
Ausgabe der Klasse MainHashMap– Teil 6
1 0 leer
2 Person: 1 Emil Eumel 1
3 2 leer
4 3 leer
5 4 leer
6 Person: 5 Hugo Helmchen 5
7 6 leer
8 7 leer
9 8 leer
10 9 leer
Bei Key 3 wurde Kohlpfennig entfernt.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 673
Die Klasse HashMap
Klasse MainHashMap– Teil 7
49 // weitere 3 Objekte einfuegen
50 map.put(p4.getPersnr(), p4);
51 map.put(p5.getPersnr(), p5);
52 map.put(p6.getPersnr(), p6);
53
54 // nochmal komplett ausgeben
55 worker.printPersMap(map, 10);

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 674
Die Klasse HashMap
Ausgabe der Klasse MainHashMap– Teil 7
1 0 leer
2 Person: 1 Emil Eumel 1
3 2 leer
4 3 leer
5 4 leer
6 Person: 5 Hugo Helmchen 5
7 Person: 6 Klaus Kohlpfennig 6
8 7 leer
9 Person: 8 Rita Rettich 8
10 Person: 9 Herbert Hacker 9
Bei Key 6, 8 und 9 wurden neue Values hinzugefügt.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 675
Die Klasse HashMap
Klasse MainHashMap– Teil 8
56 // Pruefen, ob bestimmte Values in Liste
57 if (map.containsValue(p2)) {
58 System.out.println("Person " + p2.toString()
59 + " vorhanden!");
60 }
61 else {
62 System.out.println("Person " + p2.toString()
63 + " nicht vorhanden!");
64 } // end else
65 } // end method main()
66 } // end class

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 676
Die Klasse HashMap
Zusammenfassung
In einer HashMap können Objekte (Values) nach einem Schlüssel (Key)
eingeordnet werden.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 676
Die Klasse HashMap
Zusammenfassung
In einer HashMap können Objekte (Values) nach einem Schlüssel (Key)
eingeordnet werden.
In unserem Beispiel war der Key ein Integer-Objekt. Er kann aber auch
von einem beliebigen, anderen Referenz-Datentyp, z.B. String sein.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 676
Die Klasse HashMap
Zusammenfassung
In einer HashMap können Objekte (Values) nach einem Schlüssel (Key)
eingeordnet werden.
In unserem Beispiel war der Key ein Integer-Objekt. Er kann aber auch
von einem beliebigen, anderen Referenz-Datentyp, z.B. String sein.
Die Values einer HashMap sind duplizierbar – Erna Etepetete kann also
mehrfach vorhanden sein. Aber:

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 676
Die Klasse HashMap
Zusammenfassung
In einer HashMap können Objekte (Values) nach einem Schlüssel (Key)
eingeordnet werden.
In unserem Beispiel war der Key ein Integer-Objekt. Er kann aber auch
von einem beliebigen, anderen Referenz-Datentyp, z.B. String sein.
Die Values einer HashMap sind duplizierbar – Erna Etepetete kann also
mehrfach vorhanden sein. Aber:
Die Keys einer HashMap sind nicht duplizierbar – sie müssen eindeutig
sein.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 676
Die Klasse HashMap
Zusammenfassung
In einer HashMap können Objekte (Values) nach einem Schlüssel (Key)
eingeordnet werden.
In unserem Beispiel war der Key ein Integer-Objekt. Er kann aber auch
von einem beliebigen, anderen Referenz-Datentyp, z.B. String sein.
Die Values einer HashMap sind duplizierbar – Erna Etepetete kann also
mehrfach vorhanden sein. Aber:
Die Keys einer HashMap sind nicht duplizierbar – sie müssen eindeutig
sein.
Die 2 (unterschiedlichen) Referenzen von Erna Etepetete knnen also nur ¨
unter 2 unterschiedlichen Keys in ein- und derselben HashMap abgelegt
sein.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 677
Die Klasse HashSet
Eigenschaen von Sets – speziell HashSet
Objekte (Elements) sind innerhalb des Sets nicht duplizierbar.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 677
Die Klasse HashSet
Eigenschaen von Sets – speziell HashSet
Objekte (Elements) sind innerhalb des Sets nicht duplizierbar.
Als Duplikate werden – wenn keine andere Ordnungsrelation
implementiert wurde, die Objektreferenzen gesehen.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 677
Die Klasse HashSet
Eigenschaen von Sets – speziell HashSet
Objekte (Elements) sind innerhalb des Sets nicht duplizierbar.
Als Duplikate werden – wenn keine andere Ordnungsrelation
implementiert wurde, die Objektreferenzen gesehen.
HashSet ist iterierbar!

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 677
Die Klasse HashSet
Eigenschaen von Sets – speziell HashSet
Objekte (Elements) sind innerhalb des Sets nicht duplizierbar.
Als Duplikate werden – wenn keine andere Ordnungsrelation
implementiert wurde, die Objektreferenzen gesehen.
HashSet ist iterierbar!
Beispiel: HashSet<Person> set1 = new HashSet<>();

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 678
Die Klasse HashSet
Klasse MainHashSet– Teil 1
1 import java.util.HashSet;
2
3 public class MainHashSet {
4
5 public void printPersSet(
6 HashSet<? extends Person> personen) {
7
8 for (Person p : personen) {
9 System.out.println(p.toString());
10 } // end for
11 System.out.println("---------------");
12 } // end method printPersSet()
HashSet ist iterierbar! Daher Iteratorschleife.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 679
Die Klasse HashSet
Klasse MainHashSet– Teil 2
13 public static void main(String[] args) {
14
15 MainHashSet worker = new MainHashSet();
16
17 // 4 Personen
18 Person p1 = new Person("Emil","Eumel",1);
19 Person p2 = new Person("Erna","Etepetete",3);
20 Person p3 = new Person("Hugo","Helmchen",5);
21
22 Person p7 = new Person("Emil","X",1);
23 p7.setNachname("Eumel"); // wird Emil Eumel
24
p7 ist eine andere Referenz als p1 – enthält aber die gleichen Attribute.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 680
Die Klasse HashSet
Klasse MainHashSet– Teil 3
24 // Eine leere HashMap anlegen
25 HashSet<Person> set1 = new HashSet<>();
26
27 // 3 Personen einfuegen
28 set1.add(p1);
29 set1.add(p2);
30 set1.add(p3);
31
32 set1.add(p1); // Nochmal p1 versuchen
33
34 worker.printPersSet(set1);
Es werden nur 3 Personen ausgegeben – HashSet bemerkt den Versuch,
p1 doppelt einzufügen.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 681
Die Klasse HashSet
Ausgabe der Klasse MainHashSet– Teil 3
1 Emil Eumel 1
2 Hugo Helmchen 5
3 Erna Etepetete 3
4 ---------------
Es werden nur 3 Personen ausgegeben – HashSet bemerkt den Versuch,
p1 doppelt einzufügen.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 682
Die Klasse HashSet
Klasse MainHashSet– Teil 4
34 set1.add(p7);
35 worker.printPersSet(set1);
p7 hat die gleichen Daten, aber eine andere Referenz als p1 :wird
eingefügt! Es werden 4 Elemente ausgegeben.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 683
Die Klasse HashSet
Ausgabe der Klasse MainHashSet– Teil 4
1 Emil Eumel 1
2 Emil Eumel 1
3 Hugo Helmchen 5
4 Erna Etepetete 3
5 ---------------
p7 hat die gleichen Daten, aber eine andere Referenz als p1 :wird
eingefügt! Es werden 4 Elemente ausgegeben.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 684
Die Klasse HashSet
Klasse MainHashSet– Teil 4
36 // Danach werden nur noch 3 Elemente ausgegeben
37 set1.remove(p7);
38 worker.printPersSet(set1);
39
40 // Set leeren
41 // Danach werden keine Elemente mehr ausgegeben!
42 set1.clear();
43 worker.printPersSet(set1);
44
45 } // end method main()
46 } // end class

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 685
Die Klasse HashSet
Zusammenfassung
Objekte (Elements) sind innerhalb des Sets nicht duplizierbar.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 685
Die Klasse HashSet
Zusammenfassung
Objekte (Elements) sind innerhalb des Sets nicht duplizierbar.
Als Duplikate werden – wenn keine andere Ordnungsrelation
implementiert wurde, die Objektreferenzen gesehen.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 685
Die Klasse HashSet
Zusammenfassung
Objekte (Elements) sind innerhalb des Sets nicht duplizierbar.
Als Duplikate werden – wenn keine andere Ordnungsrelation
implementiert wurde, die Objektreferenzen gesehen.
In diesem Fall werden 2 unterschiedliche Referenzen, die jedoch
identischen Inhalt besitzen, als 2 unterschiedliche Elemente
aufgefasst.

Generische Klassen (Generics) Das Java-Collection-Framework Prof. Dr. Ute Matecki 685
Die Klasse HashSet
Zusammenfassung
Objekte (Elements) sind innerhalb des Sets nicht duplizierbar.
Als Duplikate werden – wenn keine andere Ordnungsrelation
implementiert wurde, die Objektreferenzen gesehen.
In diesem Fall werden 2 unterschiedliche Referenzen, die jedoch
identischen Inhalt besitzen, als 2 unterschiedliche Elemente
aufgefasst.
HashSet ist iterierbar!

2
• © Prof. Dr. Ute Matecki
Fakultät Informatik
