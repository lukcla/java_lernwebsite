# Skript-Rohtext Teil 2: Generics – Iterierbare Generics (Skript S. 560–599)

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 560
Iterierbare Generics benötigen einen Iterator
Erna
Etepetete
Sina
Schnellschuh
12.5s
100m
Rudolf
Reindeer
5.7s
100m
iterator.next()
Iterierbare Generic (z.B. Liste)
Iterator liefert mit seiner Methode
next() bei jedem Aufruf das nächste, 
nächste, nächste Element ...
Sina
Schnellschuh
12.5s
100m

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 560
Iterierbare Generics benötigen einen Iterator
Erna
Etepetete
Sina
Schnellschuh
12.5s
100m
Rudolf
Reindeer
5.7s
100m
iterator.next()
Iterierbare Generic (z.B. Liste)
Iterator liefert mit seiner Methode
next() bei jedem Aufruf das nächste, 
nächste, nächste Element ...
Sina
Schnellschuh
12.5s
100m Dieser durchläu mit jedem .next()-Aufruf den Behälter

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 560
Iterierbare Generics benötigen einen Iterator
Erna
Etepetete
Sina
Schnellschuh
12.5s
100m
Rudolf
Reindeer
5.7s
100m
iterator.next()
Iterierbare Generic (z.B. Liste)
Iterator liefert mit seiner Methode
next() bei jedem Aufruf das nächste, 
nächste, nächste Element ...
Sina
Schnellschuh
12.5s
100m Dieser durchläu mit jedem .next()-Aufruf den Behälter
Jeder .next()-Aufruf liefert das nächste Element aus dem Behälter.

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 561
Iterierbare Generics benötigen einen Iterator
Erna
Etepetete
Sina
Schnellschuh
12.5s
100m
Rudolf
Reindeer
5.7s
100m
iterator.next()
Iterierbare Generic (z.B. Liste)
Iterator liefert mit seiner Methode
next() bei jedem Aufruf das nächste, 
nächste, nächste Element ...
Sina
Schnellschuh
12.5s
100m
for (Person p : liste) {
....
}
... bewirkt den wiederholten 
Aufruf von .next() durch einen 
Iterator!

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 561
Iterierbare Generics benötigen einen Iterator
Erna
Etepetete
Sina
Schnellschuh
12.5s
100m
Rudolf
Reindeer
5.7s
100m
iterator.next()
Iterierbare Generic (z.B. Liste)
Iterator liefert mit seiner Methode
next() bei jedem Aufruf das nächste, 
nächste, nächste Element ...
Sina
Schnellschuh
12.5s
100m
for (Person p : liste) {
....
}
... bewirkt den wiederholten 
Aufruf von .next() durch einen 
Iterator!
Eine Iterator-Schleife ru bei jedem Durchlauf durch einen Behälter die
.next()-Methode seines Iterators auf

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 561
Iterierbare Generics benötigen einen Iterator
Erna
Etepetete
Sina
Schnellschuh
12.5s
100m
Rudolf
Reindeer
5.7s
100m
iterator.next()
Iterierbare Generic (z.B. Liste)
Iterator liefert mit seiner Methode
next() bei jedem Aufruf das nächste, 
nächste, nächste Element ...
Sina
Schnellschuh
12.5s
100m
for (Person p : liste) {
....
}
... bewirkt den wiederholten 
Aufruf von .next() durch einen 
Iterator!
Eine Iterator-Schleife ru bei jedem Durchlauf durch einen Behälter die
.next()-Methode seines Iterators auf
Dieser liefert dann die nächste Objektreferenz des Behälters.

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 562
Iterierbare Generics benötigen einen Iterator
«Interface»
Iterator
«Interface»
Iterable
 + next(): T
 + hasNext():boolean
 + iterator():Iterator
Ein Iterator implementiert das Interface Iterator
Methode hasNext(): stellt fest, ob wir am letzten 
 Element angelangt sind.
Methode next(): Liefert das nächste Element,
 sofern vorhanden.
Eine iterierbare Generic implementiert das
Interface Iterable
Methode iterator(): Liefert ein lauffähiges
 Iterator-Objekt auf
 diese Generic zurück. 

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 563
Iterierbare Generics: Eine kleine Liste
SmallList1Iterator
 - list: SmallList1
 - current: int 
 + SmallList1Iterator( list: SmallList1)
 + hasNext():boolean
 + next(): T
SmallList1
 - values:Object [*]
 - noOfElements: int
 - maxElements: int 
 + SmallList1( maxElements: int)
 + add( element: T):boolean
+ get( index: int): T
 + remove( index: int): boolean
 + size(): int
 + iterator():Iterator
«Interface»
Iterator
«Interface»
Iterable
 + next(): T
 + hasNext():boolean + iterator():Iterator

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 564
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1
Implementiert das Interface Iterable

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 564
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1
Implementiert das Interface Iterable
Objektreferenzen werden in einem Array vom Typ Object untergebracht,
da
T [] values = new T[size]; vom Compiler nicht akzeptiert wird!

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 564
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1
Implementiert das Interface Iterable
Objektreferenzen werden in einem Array vom Typ Object untergebracht,
da
T [] values = new T[size]; vom Compiler nicht akzeptiert wird!
maxElements: Initiale Größe des Arrays

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 564
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1
Implementiert das Interface Iterable
Objektreferenzen werden in einem Array vom Typ Object untergebracht,
da
T [] values = new T[size]; vom Compiler nicht akzeptiert wird!
maxElements: Initiale Größe des Arrays
noOfElements: Tatsächlich abgelegte Anzahl der Objekte.

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 565
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1
Konstruktor: Legt das Array values an.

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 565
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1
Konstruktor: Legt das Array values an.
Methode add(T element): Platziert das nächste Element hinten in values.
Falls values zu klein: Es wird eine längere Kopie von values angelegt!

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 565
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1
Konstruktor: Legt das Array values an.
Methode add(T element): Platziert das nächste Element hinten in values.
Falls values zu klein: Es wird eine längere Kopie von values angelegt!
Methode get(int index): liefert aus values das Element an Position index.

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 565
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1
Konstruktor: Legt das Array values an.
Methode add(T element): Platziert das nächste Element hinten in values.
Falls values zu klein: Es wird eine längere Kopie von values angelegt!
Methode get(int index): liefert aus values das Element an Position index.
Methode remove(int index): Entfernt Element an Position index aus Liste
values. Verkürzt die Liste dabei durch „vorrücken“ der hinteren
Elemente zu Position index.

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 566
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1
Methode size(): Liefert die Anzahl der tatsächlich in der Liste abgelegten
Elemente – also noOfElements zurück.

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 566
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1
Methode size(): Liefert die Anzahl der tatsächlich in der Liste abgelegten
Elemente – also noOfElements zurück.
Erzeugt einen Iterator vom Typ SmallList1Iterator und liefert ihn zurück.

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 567
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1 – Teil 1
1 import java.util.Iterator;
2 import java.lang.Iterable;
3
4 public class SmallList1 <T>
5 implements Iterable<T>{
6
7 private Object [] values; // Werte-Array
8 private int noOfElements; // Anzahl Elemente
9 private int maxElements; // Groesse des Arrays

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 568
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1 – Teil 2
10 public SmallList1(int maxElements) {
11 values = new Object[maxElements];
12 this.maxElements=maxElements;
13
14 // noch keine Elemente eingehaengt -- 0 Elemente!
15 this.noOfElements=0;
16 } // end constructor

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 569
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1 – Teil 3
17 public boolean add(T element) {
18
19 // Falls Array voll, abbrechen ...
20 if (noOfElements >= maxElements) {
21 return false ;
22 }
23 // ... sonst haenge neues Element hinten an
24 values[noOfElements] = element;
25 noOfElements++;
26 return true ;
27 } // end method

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 570
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1 – Teil 4
28 // Liefere Element an Position index
29 // Falls dort kein gueltiges Element
30 // steht: Gib null zurueck.
31 public T get(int index) {
32 if (index < noOfElements) {
33 return (T) values[index];
34 }
35 else {
36 return null ;
37 } // end else
38 } // end method

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 571
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1 – Teil 5
39 public boolean remove(int index) {
40 // Falls index ausserhalb des Arrays --
41 // vorzeitig abbrechen
42 if (index >= noOfElements || index < 0) {
43 return false ;
44 } // end if

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 572
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1 – Teil 6
44 // Hinteren Teil des Arrays "nach vorne" ziehen
45 for (int i=index; i < noOfElements-1; i++ ) {
46 values[i]=values[i+1];
47 } // end for
48
49 noOfElements--; // Ein Element weniger!
50 return true ;
51 } // end method remove()

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 573
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1 – Teil 7
52 // Gib wirkliche Anzahl Elemente
53 // zurueck
54 public int size () {
55 return this.noOfElements;
56 } // end method size()

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 574
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1 – Teil 8
57 // Implementierung der Methode aus
58 // dem Interface Iterable
59 @Override
60 public Iterator<T> iterator() {
61
62 return new SmallList1Iterator<T>(this);
63 } // end method iterator()
64 } // end class

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 575
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1Iterator
Variable list enthält eine Referenz auf die zu durchlaufende Liste.

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 575
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1Iterator
Variable list enthält eine Referenz auf die zu durchlaufende Liste.
Variable current enthält die aktuelle Position des Iterators in der zu
durchlaufenden Liste.

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 575
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1Iterator
Variable list enthält eine Referenz auf die zu durchlaufende Liste.
Variable current enthält die aktuelle Position des Iterators in der zu
durchlaufenden Liste.
Konstruktor: reicht die Referenz auf die zu durchlaufende Liste herein.

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 575
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1Iterator
Variable list enthält eine Referenz auf die zu durchlaufende Liste.
Variable current enthält die aktuelle Position des Iterators in der zu
durchlaufenden Liste.
Konstruktor: reicht die Referenz auf die zu durchlaufende Liste herein.
Methode hasNext()): liefert true zurück, wenn current noch nicht hinter
dem letzten Element steht.

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 575
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1Iterator
Variable list enthält eine Referenz auf die zu durchlaufende Liste.
Variable current enthält die aktuelle Position des Iterators in der zu
durchlaufenden Liste.
Konstruktor: reicht die Referenz auf die zu durchlaufende Liste herein.
Methode hasNext()): liefert true zurück, wenn current noch nicht hinter
dem letzten Element steht.
Methode next(): liefert das nächste Element current und inkrementiert
current danach.

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 576
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1Iterator – Teil 1
1 import java.util.Iterator;
2
3 // Iterator: Liefert das naechste Element aus einer
4 // Liste vom Typ SmallList1
5 public class SmallList1Iterator<T>
6 implements Iterator<T> {
7
8 // Liste, die durchlaufen werden soll
9 private SmallList1<T> list;
10
11 private int current = 0; // Aktuelle Pos. in Liste

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 577
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1Iterator – Teil 2
12 // Referenz auf Liste durchreichen
13 public SmallList1Iterator(SmallList1<T> list) {
14 this.list = list;
15 }// end constructor

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 578
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1Iterator – Teil 3
16 // Implementierung der Methode aus dem Interface Iterator
17 @Override
18 public boolean hasNext() {
19 // Wenn noch ein gueltiges Element
20 // an Pos current ...
21 if (list.get(current) != null ) {
22 return true ;
23 }
24 else {
25 return false ;
26 } // end else
27 } // end method hasNext()

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 579
Iterierbare Generics: Eine kleine Liste
Klasse SmallList1Iterator – Teil 4
28 // Implementierung der Methode aus dem Interface Iterator
29 @Override
30 public T next() {
31 if(hasNext()) {
32 T element = list.get(current);
33 current ++; // Positionszaehler inkrementieren
34 return element;
35 }
36 else {
37 return null ;
38 } // end else
39 } // end method next()
40 } // end class

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 580
Iterierbare Generics: Eine kleine Liste
Anwendende main()-Klasse MainGeneric1 – Teil 1
1 public class MainGeneric1 {
2
3 public static void main(String [] args) {
4 // Liste mit 5 Plaetzen erzeugen
5 SmallList1<Person> liste = new SmallList1<Person>(5);
6
7 // 3 Objekte erzeugen
8 Person p1 = new Person("Erna","Etepetete");;
9 Laeufer l1 = new Laeufer("Emil","Eumel",12.5,100);
10 Laeufer l2 = new Laeufer("Sina","Schnellschuh",10.4,100);

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 581
Iterierbare Generics: Eine kleine Liste
Anwendende main()-Klasse MainGeneric1 – Teil 2
12 // 3 Objekte einhaengen -- Achtung: Polymorphie!
13 liste.add(p1);
14 liste.add(l1);
15 liste.add(l2);
16
17 // Die Iteration durch diese Liste wird vom
18 // Iterator aus Klasse SmallList1Iterator
19 // erledigt
20 for (Person p : liste) {
21 String s = p.toString();
22 System.out.println(s);
23 } // end for

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 582
Iterierbare Generics: Eine kleine Liste
Anwendende main()-Klasse MainGeneric1 – Teil 3
28 // Entfernung von l1 -- Emil Eumel
29 liste.remove(1);
30
31 // nochmalige Ausgabe der restlichen Liste
32 for (Person p : liste) {
33 String s = p.toString();
34 System.out.println(s);
35 } // end for
36 } // end method main()
37 } // end class

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 583
Zusammenfassung zur iterierbaren Liste SmallList1
Wir haben entwickelt:
Eine Generic in Form einer iterierbaren Liste: Klasse SmallList1
- Diese implementiert das Interface Iterable mit der Methode iterator().
- Diese Methode liefert einen neu erzeugten Iterator vom Typ SmallList1Iterator.

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 583
Zusammenfassung zur iterierbaren Liste SmallList1
Wir haben entwickelt:
Eine Generic in Form einer iterierbaren Liste: Klasse SmallList1
- Diese implementiert das Interface Iterable mit der Methode iterator().
- Diese Methode liefert einen neu erzeugten Iterator vom Typ SmallList1Iterator.
Die Klasse SmallList1Iterator.
- Diese implementiert das Interface Iterator mit den Methoden next() und hasNext().
- Mit Hilfe dieser Klasse wird die Anwendung der Iteratorschleife
for(Person p: liste) auf unsere Liste erst möglich!

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 584
Probleme bei dieser ersten Liste SmallList1
Die Liste kann nicht ...
... verlängert werden.

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 584
Probleme bei dieser ersten Liste SmallList1
Die Liste kann nicht ...
... verlängert werden.
Die Anzahl der tatsächlich eingehängten Elemente wurde zwar gezählt –
aber am Ende des Object-Arrays war Schluß

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 584
Probleme bei dieser ersten Liste SmallList1
Die Liste kann nicht ...
... verlängert werden.
Die Anzahl der tatsächlich eingehängten Elemente wurde zwar gezählt –
aber am Ende des Object-Arrays war Schluß
Verkürzbarkeit ist „unecht“ gegeben, indem die Elemente, die hinter
einem gelöschten Element liegen, „nach vorn gezogen“ werden.

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 585
Iterierbare Generics: Verlängerbare Listen
Wünschenswert wäre also:
Verlängerbarkeit der Liste. Dies kann auf mehrere Arten geschehen:

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 585
Iterierbare Generics: Verlängerbare Listen
Wünschenswert wäre also:
Verlängerbarkeit der Liste. Dies kann auf mehrere Arten geschehen:
Weg 1: Einfacher Weg: Objekte-Array bei Bedarf in längerer Form neu
instanziieren. Hierzu nehmen wir die Klasse

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 585
Iterierbare Generics: Verlängerbare Listen
Wünschenswert wäre also:
Verlängerbarkeit der Liste. Dies kann auf mehrere Arten geschehen:
Weg 1: Einfacher Weg: Objekte-Array bei Bedarf in längerer Form neu
instanziieren. Hierzu nehmen wir die Klasse
Weg 2: Arbeitsintensiverer Weg: Verkettete Liste statt eines
Objekte-Arrays
- Langsamer beim Direktzugri auf Elemente (muss „durchgeblättert“ werden)
- Schneller beim Einhängen oder Aushängen von Elementen (Es müssen keine
anderen Elemente umkopiert werden).

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 585
Iterierbare Generics: Verlängerbare Listen
Wünschenswert wäre also:
Verlängerbarkeit der Liste. Dies kann auf mehrere Arten geschehen:
Weg 1: Einfacher Weg: Objekte-Array bei Bedarf in längerer Form neu
instanziieren. Hierzu nehmen wir die Klasse
Weg 2: Arbeitsintensiverer Weg: Verkettete Liste statt eines
Objekte-Arrays
- Langsamer beim Direktzugri auf Elemente (muss „durchgeblättert“ werden)
- Schneller beim Einhängen oder Aushängen von Elementen (Es müssen keine
anderen Elemente umkopiert werden).
Bei unserem Beispiel verwenden wir Weg 1.

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 586
Iterierbare Generics: Verlängerbare Listen
Handwerkszeug zum Verlängern/Verkürzen: API-Klasse Arrays
Statische Methode(n) copyOf(): Legt eine (evtl. längere) Kopie des
bisherigen Arrays an. Die noch nicht belegten Elemente sind ...
- ... mit null -Referenzen belegt, sofern es sich um ein Array aus Objektreferenzen
handelt.
- ... mit 0 belegt, sofern es sich um ein Array mit Werten elementaren Typs handelt.

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 586
Iterierbare Generics: Verlängerbare Listen
Handwerkszeug zum Verlängern/Verkürzen: API-Klasse Arrays
Statische Methode(n) copyOf(): Legt eine (evtl. längere) Kopie des
bisherigen Arrays an. Die noch nicht belegten Elemente sind ...
- ... mit null -Referenzen belegt, sofern es sich um ein Array aus Objektreferenzen
handelt.
- ... mit 0 belegt, sofern es sich um ein Array mit Werten elementaren Typs handelt.
Statische Methode(n) copyOfRange(): dito wie copyOf(), aber es wird nur
ein Teilbereich kopiert.

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 587
Iterierbare Generics: Verlängerbare Listen
SmallList2 – Teil 1 (fast wie vorher)
1 import java.util.Arrays;
2 import java.util.Iterator;
3 import java.lang.Iterable;
4
5 public class SmallList2 <T> implements Iterable <T>{
6
7 private Object [] values;
8 private int noOfElements;
9 private int maxElements;

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 588
Iterierbare Generics: Verlängerbare Listen
SmallList2 – Teil 2 (fast wie vorher)
10 public SmallList2(int maxElements) {
11 // maxElements liefert nun nur noch
12 // die Initial-Laenge!
13 values = new Object[maxElements];
14 this.maxElements=maxElements;
15 this.noOfElements=0;
16 } // end constructor

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 589
Iterierbare Generics: Verlängerbare Listen
SmallList2 – Teil 3
17 // Element hinten anhaengen
18 public void add(T element) {
19
20 // Wenn bisherige Arraylaenge nicht reicht ..
21 if (noOfElements >= maxElements) {
22
23 // Kopiere bisherigen Inhalt und schaffe Platz
24 // fuer 1 weiteres Element
25 values = Arrays.copyOf(values, values.length+1) ;
26 } // end if
: Verwendung der copyOf()-Methode der API-Klasse Arrays

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 590
Iterierbare Generics: Verlängerbare Listen
SmallList2 – Teil 4
27 // Haenge neues Element hinten an
28 values[noOfElements] = element;
29 noOfElements++; // Elementzaehler inkrementieren
30 } // end method add()

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 591
Iterierbare Generics: Verlängerbare Listen
SmallList2 – Teil 5
31 // Element an Position index "ausschneiden"
32 public void remove(int index) {
33 // Falls index ausserhalb des Arrays -- Exception!
34 if (index >= noOfElements || index < 0) {
35 String warning=
36 "Wanted Index: "+index + " not valid!";
37
38 IndexOutOfBoundsException e =
39 new IndexOutOfBoundsException(warning);
40 throw e;
41
42 } // end if
: Index-Verletzungen werden nun durch Exceptions abgefangen!

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 592
Iterierbare Generics: Verlängerbare Listen
SmallList2 – Teil 6
43 // Referenz am gewuenschten Index null setzen
44 values[index] = null ;
45 // Hier jetzt mit API-Methoden nach vorn kopieren!
46
47 Object [] hinten =
48 Arrays.copyOfRange(values, index+1, noOfElements-1);
49 System.arraycopy(hinten, 0, values, index, hinten.length);
50
51 noOfElements--; // Ein Element weniger!
52 } // end method remove()
: Bereich hinter dem auszuschneidenden Element wird nun über
API-Methoden „nach vorn“ gezogen.

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 593
Iterierbare Generics: Verlängerbare Listen
SmallList2 – Teil 7 (wie vorher)
53 // Liefere Element an Position index
54 public T get(int index) {
55 if (index >= 0 && index < noOfElements) {
56 return (T) values[index];
57 }
58 else {
59 return null ;
60 } // end else
61 } // end method get()

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 594
Iterierbare Generics: Verlängerbare Listen
SmallList2 – Teil 8 (wie vorher)
62 // Liefere Element an Position index
63 public T get(int index) {
64 if (index >= 0 && index < noOfElements) {
65 return (T) values[index];
66 }
67 else {
68 return null ;
69 } // end else
70 } // end method get()

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 595
Iterierbare Generics: Verlängerbare Listen
SmallList2 – Teil 9 (wie vorher)
71 // Gib wirkliche Anzahl Elemente zurueck
72 public int size () {
73 return this.noOfElements;
74 } // end method size()

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 596
Iterierbare Generics: Verlängerbare Listen
SmallList2 – Teil 10 (wie vorher)
75 //Implementierung der Methode aus
76 // dem Interface Iterable
77 @Override
78 public Iterator<T> iterator() {
79
80 return new SmallList2Iterator<T>(this);
81 } // end method iterator()
82 } // end class
: Einziger Unterschied zu SmallList1: Der Iterator SmallList2Iterator
wird mit einer SmallList2 initialisiert!

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 597
Iterierbare Generics: Verlängerbare Listen
SmallList2Iterator – Teil 1 (fast wie vorher)
1 import java.util.Iterator;
2
3 // Iterator: Liefert das naechste Element aus einer
4 // Liste vom Typ SmallList1
5 public class SmallList2Iterator<T>
6 implements Iterator<T> {
7
8 // Liste, die durchlaufen werden soll
9 private SmallList2<T> list;
10
11 private int current = 0; // Aktuelle Pos. in Liste
: Einziger Unterschied zu SmallList1: Der Iterator SmallList2Iterator
wird mit einer SmallList2 initialisiert!

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 598
Iterierbare Generics: Verlängerbare Listen
SmallList2Iterator – Teil 2 (fast wie vorher)
12 // Referenz auf Liste durchreichen
13
14 public SmallList2Iterator( SmallList2<T> list ) {
15 this.list = list;
16 }// end constructor
17
18 // weitere Methoden: hasNext() und next() wie in
19 // SmallList1Iterator!
20 } // end class
: Einziger Unterschied zu SmallList1: Der Iterator SmallList2Iterator
wird mit einer SmallList2 initialisiert!

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 599
Iterierbare Generics: Verlängerbare Listen
Zusammenfassung
Eine Array-basierte Liste enthält als Grundbaustein ein Array vom Typ
Object.

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 599
Iterierbare Generics: Verlängerbare Listen
Zusammenfassung
Eine Array-basierte Liste enthält als Grundbaustein ein Array vom Typ
Object.
Dieses kann verlängert werden, indem es mit der Methode
Arrays.copyOf() reallokiert (also neu erzeugt) wird.

Generische Klassen (Generics) Iterierbare Generics Prof. Dr. Ute Matecki 599
Iterierbare Generics: Verlängerbare Listen
Zusammenfassung
Eine Array-basierte Liste enthält als Grundbaustein ein Array vom Typ
Object.
Dieses kann verlängert werden, indem es mit der Methode
Arrays.copyOf() reallokiert (also neu erzeugt) wird.
Bei der Entfernung von Objekten aus dem Array kann der hintere,
verbleibende Teil mit Arrays.copyOfRange() und System.arrayCopy()
nach vorn gezogen werden.

