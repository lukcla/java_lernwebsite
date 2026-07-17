# Skript-Rohtext Teil 2: Threads (Skript S. 714–774)

Programmierung 2
Threads

Threads Prof. Dr. Ute Matecki 714
Vorwort
Programmieren im Großen – Packages (Pakete)
Einstieg Streams
Generische Klassen (Generics)
Annotationen
Threads
Threads vs. Prozesse
Threads in Java

Threads Prof. Dr. Ute Matecki 715
Thread-Synchronisation mit dem Monitor-Konzept in Java

Threads Threads vs. Prozesse Prof. Dr. Ute Matecki 716
Threads vs. Prozesse
Wir wissen aus früheren Vorlesungen
Ein Prozess ist ein Programm in Ausführung.

Threads Threads vs. Prozesse Prof. Dr. Ute Matecki 716
Threads vs. Prozesse
Wir wissen aus früheren Vorlesungen
Ein Prozess ist ein Programm in Ausführung.
Wenn ein Programm auf einem Mehrprozess-Betriebssystem mehrfach
gestartet wird: Mehrere Prozesse ein- und desselben Programms :jeder
mit eigener Prozess-ID (PID).

Threads Threads vs. Prozesse Prof. Dr. Ute Matecki 716
Threads vs. Prozesse
Wir wissen aus früheren Vorlesungen
Ein Prozess ist ein Programm in Ausführung.
Wenn ein Programm auf einem Mehrprozess-Betriebssystem mehrfach
gestartet wird: Mehrere Prozesse ein- und desselben Programms :jeder
mit eigener Prozess-ID (PID).
Diese Prozesse können parallel oder quasi-parallel (je nach Anzahl der
Prozessoren) ablaufen.

Threads Threads vs. Prozesse Prof. Dr. Ute Matecki 716
Threads vs. Prozesse
Wir wissen aus früheren Vorlesungen
Ein Prozess ist ein Programm in Ausführung.
Wenn ein Programm auf einem Mehrprozess-Betriebssystem mehrfach
gestartet wird: Mehrere Prozesse ein- und desselben Programms :jeder
mit eigener Prozess-ID (PID).
Diese Prozesse können parallel oder quasi-parallel (je nach Anzahl der
Prozessoren) ablaufen.
Prozesse können um Betriebsmittel konkurrieren – hier muß auf
gegenseitige Ausschlußverfahren geachtet werden (Mehr dazu in
Betriebssysteme & Co.)!

Threads Threads vs. Prozesse Prof. Dr. Ute Matecki 717
Threads vs. Prozesse
Threads
Eine Thread ist ein parallel/quasi-parallel ausführbarer Bestandteil
eines Prozesses.

Threads Threads vs. Prozesse Prof. Dr. Ute Matecki 717
Threads vs. Prozesse
Threads
Eine Thread ist ein parallel/quasi-parallel ausführbarer Bestandteil
eines Prozesses.
Ein Prozess kann also möglicherweise mehrere Threads gleichzeitig
steuern.

Threads Threads vs. Prozesse Prof. Dr. Ute Matecki 717
Threads vs. Prozesse
Threads
Eine Thread ist ein parallel/quasi-parallel ausführbarer Bestandteil
eines Prozesses.
Ein Prozess kann also möglicherweise mehrere Threads gleichzeitig
steuern.
Anwendungsbeispiele:

Threads Threads vs. Prozesse Prof. Dr. Ute Matecki 717
Threads vs. Prozesse
Threads
Eine Thread ist ein parallel/quasi-parallel ausführbarer Bestandteil
eines Prozesses.
Ein Prozess kann also möglicherweise mehrere Threads gleichzeitig
steuern.
Anwendungsbeispiele:
- Ein Server-Prozess, der mehrere Clients gleichzeitig bedienen will, erzeugt für jede
Client-Anfrage eine Server-Thread zur Bedienung des Clients.

Threads Threads vs. Prozesse Prof. Dr. Ute Matecki 717
Threads vs. Prozesse
Threads
Eine Thread ist ein parallel/quasi-parallel ausführbarer Bestandteil
eines Prozesses.
Ein Prozess kann also möglicherweise mehrere Threads gleichzeitig
steuern.
Anwendungsbeispiele:
- Ein Server-Prozess, der mehrere Clients gleichzeitig bedienen will, erzeugt für jede
Client-Anfrage eine Server-Thread zur Bedienung des Clients.
- Ein Prozess, der eine (riesen-)große Bildmatrix verarbeiten muss, gibt an jeden
Thread eine Kachel des Bildes zum Bearbeiten.

Threads Threads vs. Prozesse Prof. Dr. Ute Matecki 717
Threads vs. Prozesse
Threads
Eine Thread ist ein parallel/quasi-parallel ausführbarer Bestandteil
eines Prozesses.
Ein Prozess kann also möglicherweise mehrere Threads gleichzeitig
steuern.
Anwendungsbeispiele:
- Ein Server-Prozess, der mehrere Clients gleichzeitig bedienen will, erzeugt für jede
Client-Anfrage eine Server-Thread zur Bedienung des Clients.
- Ein Prozess, der eine (riesen-)große Bildmatrix verarbeiten muss, gibt an jeden
Thread eine Kachel des Bildes zum Bearbeiten.
- Ein Prozess erzeugt mit einer oder mehreren Threads Datensätze, die von Threads
eines anderen Prozesses abgefragt werden, sobald sie benötigt werden.

Threads Threads in Java Prof. Dr. Ute Matecki 718
Threads in Java
... können sein:
von der Java VM automatisch erzeugte Threads (z. B. für Event-Handling
oder Garbage-Collector)

Threads Threads in Java Prof. Dr. Ute Matecki 718
Threads in Java
... können sein:
von der Java VM automatisch erzeugte Threads (z. B. für Event-Handling
oder Garbage-Collector)
von selbstgeschriebenen Programmen erzeugte Threads.

Threads Threads in Java Prof. Dr. Ute Matecki 718
Threads in Java
... können sein:
von der Java VM automatisch erzeugte Threads (z. B. für Event-Handling
oder Garbage-Collector)
von selbstgeschriebenen Programmen erzeugte Threads.
Threads in Java sind Objekte ...
- ... der Klasse Thread oder
- ...Objekte einer Klasse, die das Interface Runnable implementiert.

Threads Threads in Java Prof. Dr. Ute Matecki 719
Threads in Java
Die Klasse Thread und das Interface Runnable
java.lang.Thread
+ Thread( in target: java.lang.Runnable)
+ Thread()
+ run()
+ start()
+ sleep()
+ wait()
+ join()
+ yield()
+ notify()
«Interface»
java.lang.Runnable
+ run()

Threads Threads in Java Prof. Dr. Ute Matecki 720
Threads in Java
Beispielszenario: Spaghetti-Hütte
Zwei Arten von Personen können eine Hütte betreten: Köche und
Gäste.Die Personen werden durch Threads repräsentiert.

Threads Threads in Java Prof. Dr. Ute Matecki 720
Threads in Java
Beispielszenario: Spaghetti-Hütte
Zwei Arten von Personen können eine Hütte betreten: Köche und
Gäste.Die Personen werden durch Threads repräsentiert.
Die Gäste können essen, die Köche können kochen.

Threads Threads in Java Prof. Dr. Ute Matecki 720
Threads in Java
Beispielszenario: Spaghetti-Hütte
Zwei Arten von Personen können eine Hütte betreten: Köche und
Gäste.Die Personen werden durch Threads repräsentiert.
Die Gäste können essen, die Köche können kochen.
Jeder Koch kann einen Topf mit einer gewissen Menge Spaghetti
hinstellen.

Threads Threads in Java Prof. Dr. Ute Matecki 721
Threads in Java
Beispielszenario: Spaghetti-Hütte
Jeder Gast kann einen Topf leer essen.

Threads Threads in Java Prof. Dr. Ute Matecki 721
Threads in Java
Beispielszenario: Spaghetti-Hütte
Jeder Gast kann einen Topf leer essen.
Im Anfangsszenario drängeln sich alle in der Hütte ... sie wird also nicht
vor Zugrien von mehreren Threads zu einer Zeit geschützt!

Threads Threads in Java Prof. Dr. Ute Matecki 721
Threads in Java
Beispielszenario: Spaghetti-Hütte
Jeder Gast kann einen Topf leer essen.
Im Anfangsszenario drängeln sich alle in der Hütte ... sie wird also nicht
vor Zugrien von mehreren Threads zu einer Zeit geschützt!
(frei nach dem sehr alten und sehr anschaulichen Iglu-Szenario von [? ])

Threads Threads in Java Prof. Dr. Ute Matecki 722
Threads in Java
Beispielszenario: Spaghetti-Hütte
T3
T2
T1
T4
Alle Threads (Personen) drängeln sich um 2 Töpfe in der Hütte ..

Threads Threads in Java Prof. Dr. Ute Matecki 723
Threads in Java: Beispiel 1 Spaghetti-Hütte
Erster Ansatz: Koch und Gast von Thread ableiten + Thread( target: java.lang.Runnable)
 + Thread()
 + join()
 + notify()
 + sleep()
 + start()
 + wait()
 + yield()
 + run()
Gast
 - nameGast: String
 + Gast( huette: ArrayList<Integer>, nameGast: String)
 + run()
Koch
 - grammSpaghetti: int
 - nameKoch: String
 + Koch( huette: ArrayList<Integer>, grammSpaghetti: int, nameKoch: String)
 + run()
- huette: ArrayList<Integer>
- huette: ArrayList<Integer>
java.lang.Thread
Attribute werden nicht gezeigt
«Interface»
java.lang.Runnable
 + run()
Wird in diesem Entwurf
noch nicht verwendet.
Koch und Gast überschreiben die run()-Methode der Klasse 
Thread. Methode run() enthält nun den parallel zu 
startenden Code (also kochen bzw. essen).

Threads Threads in Java Prof. Dr. Ute Matecki 724
Threads in Java: Beispiel 1 Spaghetti-Hütte
Thread-Klasse Gast
1 import java.util.ArrayList;
2 public class Gast extends Thread {
3
4 private ArrayList<Integer> huette;
5 private String nameGast;
Klasse ist von Thread abgeleitet – kann also keine andere Superklasse
mehr haben.
Referenzvariable huette wird möglicherweise von mehreren Threads
gleichzeitig betreten – Chaos!

Threads Threads in Java Prof. Dr. Ute Matecki 725
Threads in Java: Beispiel 1 Spaghetti-Hütte
Thread-Klasse Gast
6 // Gast bekommt Schluessel zur Huette
7 public Gast (ArrayList<Integer> huette, String nameGast) {
8 this.huette = huette;
9 this.nameGast = nameGast;
10 } // end constructor

Threads Threads in Java Prof. Dr. Ute Matecki 726
Threads in Java: Beispiel 1 Spaghetti-Hütte
Thread-Klasse Gast
11
12 @Override
13 public void run() { // parallel laufender Code
14 if (!huette.isEmpty()) {
15 int spaghetti =huette.remove(0); // Spaghetti essen
16 System.out.println(this.nameGast +
17 ": Ich esse " +spaghetti +"g Spaghetti ");
18 }// end if
19 } // end method
20
21 } // end class
Gast isst Spaghetti – falls er einen Topf bekommt. Er kann auch
unkontrolliert aus der Hütte fliegen – Exception!

Threads Threads in Java Prof. Dr. Ute Matecki 727
Threads in Java: Beispiel 1 Spaghetti-Hütte
Thread-Klasse Koch
1 import java.util.ArrayList;
2 public class Koch extends Thread {
3
4 private ArrayList<Integer> huette;
5 private int grammSpaghetti;
6 private String nameKoch;
Klasse ist von Thread abgeleitet – kann also keine andere Superklasse
mehr haben.
Referenzvariable huette wird möglicherweise von mehreren Threads
gleichzeitig betreten – Chaos!

Threads Threads in Java Prof. Dr. Ute Matecki 728
Threads in Java: Beispiel 1 Spaghetti-Hütte
Thread-Klasse Koch
7 // Koch bekommt Schluessel zur Huette und bringt
8 // seine eigenen Spaghetti mit.
9 public Koch (ArrayList<Integer> huette,
10 int grammSpaghetti, String nameKoch) {
11 this.huette = huette;
12 this.grammSpaghetti = grammSpaghetti;
13 this.nameKoch = nameKoch;
14 } // end constructor

Threads Threads in Java Prof. Dr. Ute Matecki 729
Threads in Java: Beispiel 1 Spaghetti-Hütte
Thread-Klasse Koch
7
8 @Override
9 public void run() { // parallel laufender Code
10 System.out.println(this.nameKoch+": "
11 + "Koche " + grammSpaghetti
12 + "g Spaghetti");
13 huette.add(grammSpaghetti);
14 } // end method
15
16 } // end class
Koch kocht Spaghetti. Er kann auch unkontrolliert aus der Hütte fliegen
– Exception!

Threads Threads in Java Prof. Dr. Ute Matecki 730
Threads in Java: Beispiel 1 Spaghetti-Hütte
main()-Klasse TesteHuetteEinfach
1 import java.util.ArrayList;
2 public class TesteHuetteEinfach {
3
4 public static void main(String[] args) {
5
6 ArrayList<Integer> huette = new ArrayList<Integer>();
7
8 Gast [] gaeste = new Gast[4];
9 Koch [] koeche = new Koch[4];
10
ArrayList ist nicht thread-sicher! Chaos beim Betreten der Hütte ist
möglich!
2 Arrays für je 4 Threads!

Threads Threads in Java Prof. Dr. Ute Matecki 731
Threads in Java: Beispiel 1 Spaghetti-Hütte
main()-Klasse TesteHuetteEinfach
11 gaeste[0] = new Gast(huette, "Emil");
12 gaeste[1] = new Gast(huette, "Erna");
13 gaeste[2] = new Gast(huette,"Rita");
14 gaeste[3] = new Gast(huette,"Herbert");
15
16 koeche[0] = new Koch(huette,2000,"Michi");
17 koeche[1] = new Koch(huette,1500, "Ina");
18 koeche[2] = new Koch(huette,2500, "Marie");
19 koeche[3] = new Koch(huette,2300,"Thomas");
4 Gast-Threads und 4 Koch-Threads. Achtung: Die Thread-Objekte sind
hier bis jetzt nur erzeugt – sie laufen noch nicht!

Threads Threads in Java Prof. Dr. Ute Matecki 732
Threads in Java: Beispiel 1 Spaghetti-Hütte
main()-Klasse TesteHuetteEinfach
20 for (Koch k: koeche) {
21 k.start();
22 } // end for
23
24 for (Gast g: gaeste) {
25 g.start();
26 } // end for
27 } // end method main()
28 } // end class
Erst die ererbte start()-Methode startet den in run() implementierten
Code als Nebenläufigkeit in der Java-VM!

Threads Threads in Java Prof. Dr. Ute Matecki 733
Threads in Java: Beispiel 1 Spaghetti-Hütte
Mögliche Ausgabe aus Beispiel 1
1 Exception in thread "Thread-0" Exception in thread "Thread-2"
2 Ina: Koche 1500g Spaghetti
3 Marie: Koche 2500g Spaghetti
4 java.lang.NullPointerException
5 at Gast.run(Gast.java:23)
6 java.lang.NullPointerException
7 at Gast.run(Gast.java:23)
8 Michi: Koche 2000g Spaghetti
9 Thomas: Koche 2300g Spaghetti
10 Herbert: Ich esse 2000g Spaghetti
11 Erna: Ich esse 2000g Spaghetti
Gäste haben versucht, auf nicht vorhandene Inhalte der Hütte
zuzugreifen!

Threads Threads in Java Prof. Dr. Ute Matecki 734
Threads in Java: Fazit aus Beispiel 1
Schlecht gelöst waren u.a.:
1 Architektur: Wir mussten beide Arten von Personen vollständig
implementieren und konnten keine Superklasse Person bauen – die
Superklassenbeziehung wurde für Thread benötigt.

Threads Threads in Java Prof. Dr. Ute Matecki 734
Threads in Java: Fazit aus Beispiel 1
Schlecht gelöst waren u.a.:
1 Architektur: Wir mussten beide Arten von Personen vollständig
implementieren und konnten keine Superklasse Person bauen – die
Superklassenbeziehung wurde für Thread benötigt.
2 Der Zugri auf die Hütte (hier: ArrayList mit Spaghetti-Portionen) war
katastrophal – Threads konnten hier „einbrechen“, wann sie wollten und
haben ggf. auf null zugegrien, wenn gerade nichts in die ArrayList
eingestellt war.

Threads Threads in Java Prof. Dr. Ute Matecki 735
Threads in Java: Beispiel 2
... löst Vererbungsproblematik. Bisherige Architektur ... + Thread( target: java.lang.Runnable)
 + Thread()
 + join()
 + notify()
 + sleep()
 + start()
 + wait()
 + yield()
 + run()
«Interface»
java.lang.Runnable
 + run()
Gast
 - nameGast: String
 + Gast( huette: ArrayList<Integer>, nameGast: String)
 + run()
Koch
 - grammSpaghetti: int
 - nameKoch: String
 + Koch( huette: ArrayList<Integer>, grammSpaghetti: int, nameKoch: String)
 + run()
- huette: ArrayList<Integer>
- huette: ArrayList<Integer>
java.lang.Thread
Attribute werden nicht gezeigt
Wird in diesem Entwurf
noch nicht verwendet.
nicht gut gelöst: name und huette sind bei Koch und Gast in
der Klasse vorhanden. Könnte über Vererbung gelöst werden ...

Threads Threads in Java Prof. Dr. Ute Matecki 736
Threads in Java: Beispiel 2
... wird abgelöst von folgender Architektur:
 + run()
java.lang.Thread
 + Thread( in target: java.lang.Runnable)
 + Thread()
 + join()
 + notify()
 + sleep()
 + start()
 + wait()
 + yield()
 + run()
Person
 - name: String
 + Person( name: String)
 + getName(): String
Gast
+ Gast( name: String, huette: ArrayList<Integer>)
 + run()
Koch
 - grammSpaghetti: int
+ Koch( name: String, huette: ArrayList<Integer>, grammSpaghetti: int)
 + run()
java.lang.Runnable
«Interface»
Attribute werden nicht gezeigt
-huette: ArrayList<Integer> -huette: ArrayList<Integer>
In dieser Architektur nicht mehr
in der Vererbungshierarchie!
Koch und Gast sind nun von Person abgeleitet. Sie implementieren
für ihre Nebenläufigkeit das Interface Runnable!

Threads Threads in Java Prof. Dr. Ute Matecki 737
Threads in Java: Beispiel 2 Spaghetti-Hütte
Klasse Person
1 public class Person {
2 private String name;
3 public Person(String name) {
4 this.name = name;
5 } // end constructor
6
7 public String getName() {
8 return name;
9 } // end method
10 } // end class
Superklasse Person

Threads Threads in Java Prof. Dr. Ute Matecki 738
Threads in Java: Beispiel 2 Spaghetti-Hütte
Thread-Klasse Gast
1 import java.util.ArrayList;
2
3 public class Gast
4 extends Person implements Runnable {
5
6 private ArrayList<Integer> huette;
Klasse ist von Person abgeleitet – kann also keine andere Superklasse
mehr haben. Sie implementiert das Interface Runnable

Threads Threads in Java Prof. Dr. Ute Matecki 739
Threads in Java: Beispiel 2 Spaghetti-Hütte
Thread-Klasse Gast
7 // Gast bekommt Schluessel zur Huette
8 public Gast (String nameGast,
9 ArrayList<Integer> huette) {
10 super(nameGast);
11 this.huette = huette;
12 } // end constructor
Klasse ist von Person abgeleitet – Name wird über
Superklassenkonstruktor durchgereicht.

Threads Threads in Java Prof. Dr. Ute Matecki 740
Threads in Java: Beispiel 2 Spaghetti-Hütte
Thread-Klasse Gast
11
12 @Override
13 public void run() { // nebenlaeufiger Code
14 if (!huette.isEmpty()) {
15 int spaghetti=huette.remove(0);
16 System.out.println(this.getName() +
17 ": Ich esse " +spaghetti + "g Spaghetti ");
18 }// end if
19 } // end method
20
21 } // end class
Methode run() ist nun eine Implementierung der Vorgabe aus Interface
Runnable.

Threads Threads in Java Prof. Dr. Ute Matecki 741
Threads in Java: Beispiel 2 Spaghetti-Hütte
Thread-Klasse Koch
... hat sich analog zu Gast geändert:
Ist nun von Person abgeleitet.

Threads Threads in Java Prof. Dr. Ute Matecki 741
Threads in Java: Beispiel 2 Spaghetti-Hütte
Thread-Klasse Koch
... hat sich analog zu Gast geändert:
Ist nun von Person abgeleitet.
Implementiert nun das Interface Runnable und damit ...

Threads Threads in Java Prof. Dr. Ute Matecki 741
Threads in Java: Beispiel 2 Spaghetti-Hütte
Thread-Klasse Koch
... hat sich analog zu Gast geändert:
Ist nun von Person abgeleitet.
Implementiert nun das Interface Runnable und damit ...
... ist die Methode run() nun eine Implementierung der
Methodenvorgabe von Runnable.

Threads Threads in Java Prof. Dr. Ute Matecki 742
Threads in Java: Beispiel 2 Spaghetti-Hütte
In main()-Klasse TesteHuetteEinfach ändert sich:
20 for (Koch k: koeche) {
21 Thread t = new Thread(k);
22 t.start();
23 }
Koch k ist nun vom Typ Person und vom Typ Runnable. Der Konstruktor
von Thread t bekommt hier ein Runnable mit einer run()- Methode
übergeben.
Die start()-Methode von Thread t startet nun die run()-Methode von Koch
k.

Threads Threads in Java Prof. Dr. Ute Matecki 743
Threads in Java: Beispiel 2 Spaghetti-Hütte
In main()-Klasse TesteHuetteEinfach ändert sich:
24 for (Gast g: gaeste) {
25 Thread t = new Thread(g);
26 t.start();
27 }
Gast g ist nun vom Typ Person und vom Typ Runnable. Der Konstruktor
von Thread t bekommt hier ein Runnable mit einer run()- Methode
übergeben.
Die start()-Methode von Thread t startet nun die run()-Methode von Gast
g.

Threads Threads in Java Prof. Dr. Ute Matecki 744
Threads in Java: Fazit aus Beispiel 2
Was ist gelöst und was nicht?
1 Architektur: Wir mussten beide Arten von Personen vollständig
implementieren und konnten keine Superklasse Person bauen – die
Superklassenbeziehung wurde für Thread benötigt. XErledigt!

Threads Threads in Java Prof. Dr. Ute Matecki 744
Threads in Java: Fazit aus Beispiel 2
Was ist gelöst und was nicht?
1 Architektur: Wir mussten beide Arten von Personen vollständig
implementieren und konnten keine Superklasse Person bauen – die
Superklassenbeziehung wurde für Thread benötigt. XErledigt!
2 Der Zugri auf die Hütte (hier: ArrayList mit Spaghetti-Portionen) war
katastrophal – Threads konnten hier „einbrechen“, wann sie wollten und
haben ggf. auf null zugegrien, wenn gerade nichts in die ArrayList
eingestellt war. ??? Noch zu lösen!

Threads Threads in Java Prof. Dr. Ute Matecki 745
Threads in Java: Zusammenfassung Beispiele 1 und 2
Architekturen zur Thread-Erzeugung
1 Klasse wird von Thread abgeleitet:

Threads Threads in Java Prof. Dr. Ute Matecki 745
Threads in Java: Zusammenfassung Beispiele 1 und 2
Architekturen zur Thread-Erzeugung
1 Klasse wird von Thread abgeleitet:
- Überschreiben der ererbten Methode run(). Diese enthält den Code, der parallelisiert
wird.

Threads Threads in Java Prof. Dr. Ute Matecki 745
Threads in Java: Zusammenfassung Beispiele 1 und 2
Architekturen zur Thread-Erzeugung
1 Klasse wird von Thread abgeleitet:
- Überschreiben der ererbten Methode run(). Diese enthält den Code, der parallelisiert
wird.
- Die aufrufende Klasse erzeugt ein Objekt der abgeleiteten Klasse und ru deren
ererbte start()-Methode auf. Diese ru die run()-Methode als Nebenläufigkeit
innerhalb der VM auf.

Threads Threads in Java Prof. Dr. Ute Matecki 745
Threads in Java: Zusammenfassung Beispiele 1 und 2
Architekturen zur Thread-Erzeugung
1 Klasse wird von Thread abgeleitet:
- Überschreiben der ererbten Methode run(). Diese enthält den Code, der parallelisiert
wird.
- Die aufrufende Klasse erzeugt ein Objekt der abgeleiteten Klasse und ru deren
ererbte start()-Methode auf. Diese ru die run()-Methode als Nebenläufigkeit
innerhalb der VM auf.
2 Klasse implementiert Interface Runnable:

Threads Threads in Java Prof. Dr. Ute Matecki 745
Threads in Java: Zusammenfassung Beispiele 1 und 2
Architekturen zur Thread-Erzeugung
1 Klasse wird von Thread abgeleitet:
- Überschreiben der ererbten Methode run(). Diese enthält den Code, der parallelisiert
wird.
- Die aufrufende Klasse erzeugt ein Objekt der abgeleiteten Klasse und ru deren
ererbte start()-Methode auf. Diese ru die run()-Methode als Nebenläufigkeit
innerhalb der VM auf.
2 Klasse implementiert Interface Runnable:
- Implementieren der ererbten Methode run(). Diese enthält den Code, der
parallelisiert wird.

Threads Threads in Java Prof. Dr. Ute Matecki 745
Threads in Java: Zusammenfassung Beispiele 1 und 2
Architekturen zur Thread-Erzeugung
1 Klasse wird von Thread abgeleitet:
- Überschreiben der ererbten Methode run(). Diese enthält den Code, der parallelisiert
wird.
- Die aufrufende Klasse erzeugt ein Objekt der abgeleiteten Klasse und ru deren
ererbte start()-Methode auf. Diese ru die run()-Methode als Nebenläufigkeit
innerhalb der VM auf.
2 Klasse implementiert Interface Runnable:
- Implementieren der ererbten Methode run(). Diese enthält den Code, der
parallelisiert wird.
- Die aufrufende Klasse erzeugt ein Objekt i der implementierenden Klasse und ein
Objekt t der Klasse Thread.

Threads Threads in Java Prof. Dr. Ute Matecki 745
Threads in Java: Zusammenfassung Beispiele 1 und 2
Architekturen zur Thread-Erzeugung
1 Klasse wird von Thread abgeleitet:
- Überschreiben der ererbten Methode run(). Diese enthält den Code, der parallelisiert
wird.
- Die aufrufende Klasse erzeugt ein Objekt der abgeleiteten Klasse und ru deren
ererbte start()-Methode auf. Diese ru die run()-Methode als Nebenläufigkeit
innerhalb der VM auf.
2 Klasse implementiert Interface Runnable:
- Implementieren der ererbten Methode run(). Diese enthält den Code, der
parallelisiert wird.
- Die aufrufende Klasse erzeugt ein Objekt i der implementierenden Klasse und ein
Objekt t der Klasse Thread.
- t wird per Konstruktor die Referenz von i übergeben.

Threads Threads in Java Prof. Dr. Ute Matecki 745
Threads in Java: Zusammenfassung Beispiele 1 und 2
Architekturen zur Thread-Erzeugung
1 Klasse wird von Thread abgeleitet:
- Überschreiben der ererbten Methode run(). Diese enthält den Code, der parallelisiert
wird.
- Die aufrufende Klasse erzeugt ein Objekt der abgeleiteten Klasse und ru deren
ererbte start()-Methode auf. Diese ru die run()-Methode als Nebenläufigkeit
innerhalb der VM auf.
2 Klasse implementiert Interface Runnable:
- Implementieren der ererbten Methode run(). Diese enthält den Code, der
parallelisiert wird.
- Die aufrufende Klasse erzeugt ein Objekt i der implementierenden Klasse und ein
Objekt t der Klasse Thread.
- t wird per Konstruktor die Referenz von i übergeben.
- Aufruf der start()-Methode von t. der VM auf. Diese ru die run()-Methode von i als
Nebenläufigkeit innerhalb der VM auf.

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 746
Thread-Synchronisation
Problem
Mehrere Threads versuchen gleichzeitig, auf bestimmte Datenbereiche
zuzugreifen.

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 746
Thread-Synchronisation
Problem
Mehrere Threads versuchen gleichzeitig, auf bestimmte Datenbereiche
zuzugreifen.
Speziell in Java: Thread-Objekte versuchen gleichzeitig, auf ein
bestimmtes Objekt zuzugreifen.

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 746
Thread-Synchronisation
Problem
Mehrere Threads versuchen gleichzeitig, auf bestimmte Datenbereiche
zuzugreifen.
Speziell in Java: Thread-Objekte versuchen gleichzeitig, auf ein
bestimmtes Objekt zuzugreifen.
Wenn nur lesende Threads auf das Objekt zugreifen können: unkritisch.

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 746
Thread-Synchronisation
Problem
Mehrere Threads versuchen gleichzeitig, auf bestimmte Datenbereiche
zuzugreifen.
Speziell in Java: Thread-Objekte versuchen gleichzeitig, auf ein
bestimmtes Objekt zuzugreifen.
Wenn nur lesende Threads auf das Objekt zugreifen können: unkritisch.
Sobald gleichzeitig schreibende Threads versuchen, zuzugreifen:
kritisch!

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 746
Thread-Synchronisation
Problem
Mehrere Threads versuchen gleichzeitig, auf bestimmte Datenbereiche
zuzugreifen.
Speziell in Java: Thread-Objekte versuchen gleichzeitig, auf ein
bestimmtes Objekt zuzugreifen.
Wenn nur lesende Threads auf das Objekt zugreifen können: unkritisch.
Sobald gleichzeitig schreibende Threads versuchen, zuzugreifen:
kritisch!
Genau diese Problemstellung haben wir eben mit Köchen und Gästen
betrachtet! Sie haben versucht, den Inhalt eines gemeinsam
verfügbaren Objektes (Hütte) zu ändern.

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 747
Thread-Synchronisation
Mögliche Lösung
Code-Abschnitte, die vor dem gleichzeitigen Zugri mehrerer Threads
geschützt werden sollen, heißen kritische Abschnitte.

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 747
Thread-Synchronisation
Mögliche Lösung
Code-Abschnitte, die vor dem gleichzeitigen Zugri mehrerer Threads
geschützt werden sollen, heißen kritische Abschnitte.
Eine Lösungsmöglichkeit besteht darin, diese kritischen Abschnitte zu
kennzeichnen ...

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 747
Thread-Synchronisation
Mögliche Lösung
Code-Abschnitte, die vor dem gleichzeitigen Zugri mehrerer Threads
geschützt werden sollen, heißen kritische Abschnitte.
Eine Lösungsmöglichkeit besteht darin, diese kritischen Abschnitte zu
kennzeichnen ...
... und Threads, die möglicherweise auf diesen Abschnitt zugreifen
wollen, in eine Warteschlange einzustellen und durch eine
Überwachung (Monitoring) dafür zu sorgen, dass sie den kritischen
Abschnitt nur betreten, wenn er ihnen zugeteilt wird.

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 747
Thread-Synchronisation
Mögliche Lösung
Code-Abschnitte, die vor dem gleichzeitigen Zugri mehrerer Threads
geschützt werden sollen, heißen kritische Abschnitte.
Eine Lösungsmöglichkeit besteht darin, diese kritischen Abschnitte zu
kennzeichnen ...
... und Threads, die möglicherweise auf diesen Abschnitt zugreifen
wollen, in eine Warteschlange einzustellen und durch eine
Überwachung (Monitoring) dafür zu sorgen, dass sie den kritischen
Abschnitt nur betreten, wenn er ihnen zugeteilt wird.
In Java übernimmt der Programmierer die Kennzeichnung der
kritischen Abschnitte.

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 747
Thread-Synchronisation
Mögliche Lösung
Code-Abschnitte, die vor dem gleichzeitigen Zugri mehrerer Threads
geschützt werden sollen, heißen kritische Abschnitte.
Eine Lösungsmöglichkeit besteht darin, diese kritischen Abschnitte zu
kennzeichnen ...
... und Threads, die möglicherweise auf diesen Abschnitt zugreifen
wollen, in eine Warteschlange einzustellen und durch eine
Überwachung (Monitoring) dafür zu sorgen, dass sie den kritischen
Abschnitt nur betreten, wenn er ihnen zugeteilt wird.
In Java übernimmt der Programmierer die Kennzeichnung der
kritischen Abschnitte.
Die Zuteilung (Scheduling) erfolgt dann durch die Java-VM.

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 748
Thread-Synchronisation
Eine mögliche Lösung
Krit. Abschnitt
kochen()
Krit. Abschnitt
essen()
sich Köche und Gäste anstellen müssen.wird eine Warteschlange (Monitor) eingerichtet, in derDie kritischen Abschnitte werden synchronisiert: Für sie 
T3 T2 T1
Hütte mit Spaghetti-Töpfen

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 749
Thread-Synchronisation in Java
Möglichkeit 1: Synchronisation von Instanz-Methoden
1 public class HuetteEinfach {
2 // ...
3 public synchronized int kochen( ...) {
4 // geschuetzter Code
5 }
6
7 public synchronized int essen( ...) {
8 // geschuetzter Code
9 }
10 }
Sobald eine Thread eine synchronized Instanz-Methode aufru, wird sie
in die Warteschlange zur Instanz der zugehörigen Klasse (hier: Huette)
eingestellt. Das Objekt der Huette-Klasse wird zum Monitor!

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 750
Thread-Synchronisation in Java
Möglichkeit 2: Synchronisation von statischen Methoden
1 public class HuetteEinfach {
2 // ...
3 public static synchronized int kochen( ...) {
4 // geschuetzter Code
5 }
6
7 public static synchronized int essen( ...) {
8 // geschuetzter Code
9 }
10 } // end class
Sobald eine Thread eine mit synchronized gekennzeichnete, statische
Methode aufru, wird sie in die Warteschlange zu der zugehörigen
Klasse (hier: Huette) eingestellt. Die Huette-Klasse wird zum Monitor!

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 751
Thread-Synchronisation in Java
Möglichkeit 3: Synchronisation von Objektreferenzen
1 public class HuetteEinfach {
2 private Vector<Integer> herd; // wird zum Monitor!
3 public int kochen( ...) {
4
5 synchronized (herd) {
6 // geschuetzter Code
7 } // end block synchronized
8
9 } // end method
10 } // end class
Sobald eine Thread Code eines synchronized-Blocks einer
Objekt-Referenz bearbeitet, wird sie in die Warteschlange zu dieser
Referenz (hier: herd) eingereiht. Die Referenz wird zum Monitor!

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 752
Thread-Synchronisation und Java Collection Framework
Thread-sichere Klassen der Java-Collection
Die meisten Java-Collections sind nicht thread-sicher. Häufig genutzte
Ausnahmen sind:

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 752
Thread-Synchronisation und Java Collection Framework
Thread-sichere Klassen der Java-Collection
Die meisten Java-Collections sind nicht thread-sicher. Häufig genutzte
Ausnahmen sind:
Vector und

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 752
Thread-Synchronisation und Java Collection Framework
Thread-sichere Klassen der Java-Collection
Die meisten Java-Collections sind nicht thread-sicher. Häufig genutzte
Ausnahmen sind:
Vector und
ConcurrentHashMap.

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 752
Thread-Synchronisation und Java Collection Framework
Thread-sichere Klassen der Java-Collection
Die meisten Java-Collections sind nicht thread-sicher. Häufig genutzte
Ausnahmen sind:
Vector und
ConcurrentHashMap.
Mehr dazu in den API-Beschreibungen dieser beiden Klassen!

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 753
Thread-Synchronisation in Java: Beispiel 3
 + Thread( target: java.lang.Runnable)
 + Thread()
 + join()
 + notify()
 + sleep()
 + start()
 + wait()
 + yield()
 + run()
«Interface»
java.lang.Runnable
 + run()
Gast
 - huette: HuetteEinfach 
+ Gast( nameGast: String, huette: HuetteEinfach)
 + run()
HuetteEinfach
 - anzahlToepfe: int 
 + HuetteEinfach()
«Synchronized» + kochen( name: String, grammSpaghetti: int, millisec: int): int
«Synchronized» + essen( name: String, millisec: int): int
Koch
 - huette: HuetteEinfach 
 - grammSpaghetti: int
+ Koch( nameKoch: String, huette: HuetteEinfach, grammSpaghetti: int)
 + run()
Person
 - name: String
 + Person( name: String)
 + getName(): String
Attribute werden nicht gezeigt
java.lang.Thread
- herd: Vector <Integer>
TesteHuetteEinfach
 + main( args: String[] ) «uses»
«uses»
«uses»
«uses»
«uses»
«uses»

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 754
Thread-Synchronisation in Java: Beispiel 3
Klasse HuetteEinfach
1 import java.util.Vector;
2
3 public class HuetteEinfach {
4
5 private Vector<Integer> herd;
6 private int anzahlToepfe;
7
8 public HuetteEinfach() {
9 herd = new Vector<Integer>();
10 }//end constructor
Eine Huette mit einem Herd, auf den Köche ihre Spaghetti-Töpfe stellen.

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 755
Thread-Synchronisation in Java: Beispiel 3
Klasse HuetteEinfach– synchronisierte Methode kochen()
11 public synchronized int kochen(String nameKoch,
12 int grammSpaghetti, int millisec) {
13
14 anzahlToepfe = herd.size();
15 herd.add(grammSpaghetti);
16
17 System.out.println(nameKoch +": Klapper, klapper, Topf "+
18 anzahlToepfe + " auf dem Herd mit " + grammSpaghetti +
19 "g Spaghetti! Fertig in "+ millisec + "ms");
20 return anzahlToepfe; // Toepfe auf dem Herd
21 } // end method kochen
Synchronisation: Der Herd kann zu einer Zeit nur von einem Koch
genutzt werden!

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 756
Thread-Synchronisation in Java: Beispiel 3
Klasse HuetteEinfach – synchronisierte Methode essen() – Teil 1
22 public synchronized int essen(String nameGast,
23 int millisec) {
24 int belegt = anzahlToepfe - 1;
25 if(belegt > 0) { // Wenn Toepfe auf dem Herd
26
27 // Spaghetti aufessen
28 int grammSpaghetti = herd.remove(0);
29
30 System.out.println(nameGast + ": Habe Topf " + 0 +
31 " mit " + grammSpaghetti + "g Spaghetti leer in"
32 + millisec + "ms");
Synchronisation: Nur ein Gast kann zu einer Zeit einen Topf
wegnehmen!

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 757
Thread-Synchronisation in Java: Beispiel 3
Klasse HuetteEinfach – synchronisierte Methode essen() – Teil 2
33 anzahlToepfe = herd.size(); // ein Topf weniger
34
35 return belegt; // Topf-Anzahl zu Zeit des Zugriffs
36 } // end if
37 else { // Wenn gerade kein Topf auf dem Herd
38 System.out.println(nameGast +
39 ": Ich bekomme nichts -- kein Topf auf dem Herd fertig!
40 return -1;
41 } // end else
42 } // end method essen
43 } // end class
Synchronisation: Nur ein Gast kann zu einer Zeit einen Topf
wegnehmen!

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 758
Thread-Synchronisation in Java: Beispiel 3
Klasse Person – unverändert zu Beispiel 2
1 public class Person {
2 private String name;
3 public Person(String name) {
4 this.name = name;
5 } // end constructor
6
7 public String getName() {
8 return name;
9 } // end method
10 } // end class
Superklasse Person

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 759
Thread-Synchronisation in Java: Beispiel 3
Klasse Koch
1 import java.util.Random;
2
3 public class Koch extends Person
4 implements Runnable {
5
6 private HuetteEinfach huette;
7 private int grammSpaghetti;
Klasse Koch implementiert das Interface Runnable und ist abgeleitet
von Person.

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 760
Thread-Synchronisation in Java: Beispiel 3
Klasse Koch
8 public Koch (String nameKoch, HuetteEinfach huette,
9 int grammSpaghetti) {
10 super (nameKoch);
11
12 this.huette = huette;
13 this.grammSpaghetti = grammSpaghetti;
14
15 } // end constructor
Koch hat Zugri auf Huette und bringt seine eigenen Spaghetti mit.

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 761
Thread-Synchronisation in Java: Beispiel 3
Klasse Koch – Methode run() – Teil 1
16 @Override
17 public void run() {
18 Random r = new Random();
19 int zeitMilliSec = r.nextInt(4000) + 1000;
20
21 huette.kochen(this.getName(),
22 grammSpaghetti, zeitMilliSec);
23
Vom Interface Runnable vorgegebene Methode run() simuliert den
Kochvorgang. Sie grei auf die synchronisierte Methode kochen() der
Huette zu!

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 762
Thread-Synchronisation in Java: Beispiel 3
Klasse Koch – Methode run() – Teil 2
24 try {
25 Thread.sleep(zeitMilliSec);
26 } // end try
27 catch (InterruptedException e) {
28 // Im Exception-Fall unterbrechen
29 Thread.currentThread().interrupt();
30 } // end catch
31 } // end method run()
32 } // end class
Vom Interface Runnable vorgegebene Methode run() simuliert den
Kochvorgang. Die Dauer des Kochens wird hier durch den
Thread.sleep()-Aufruf simuliert!

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 763
Thread-Synchronisation in Java: Beispiel 3
Klasse Gast
1 import java.util.Random;
2
3 public class Gast extends Person
4 implements Runnable {
5
6 private HuetteEinfach huette;
Klasse Gast implementiert das Interface Runnable und ist abgeleitet von
Person.

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 764
Thread-Synchronisation in Java: Beispiel 3
Klasse Gast
7 public Gast (String nameGast, HuetteEinfach huette ) {
8 super (nameGast);
9 this.huette = huette;
10 } // end constructor
Gast hat Zugri auf Huette.

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 765
Thread-Synchronisation in Java: Beispiel 3
Klasse Gast
7 public Gast (String nameGast, HuetteEinfach huette ) {
8 super (nameGast);
9 this.huette = huette;
10 } // end constructor
Gast hat Zugri auf Huette.

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 766
Thread-Synchronisation in Java: Beispiel 3
Klasse Gast – Methode run() – Teil 1
11 @Override
12 public void run() {
13 Random r = new Random();
14 int zeitMilliSec = r.nextInt(4000) + 1000;
15
16 huette.essen(this.getName(), zeitMilliSec);
Vom Interface Runnable vorgegebene Methode run() simuliert den
Vorgang des Essens. Sie grei auf die synchronisierte Methode essen()
der Huette zu!

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 767
Thread-Synchronisation in Java: Beispiel 3
Klasse Gast – Methode run() – Teil 2
17 try {
18 Thread.sleep(zeitMilliSec);
19 }
20 catch (InterruptedException e) {
21 // Im Exception-Fall unterbrechen
22 Thread.currentThread().interrupt();
23 } // end catch
24 } // end method run()
25 } // end class
Vom Interface Runnable vorgegebene Methode run() simuliert den
Vorgang des Essens. Die Dauer des Essens wird hier durch den
Thread.sleep()-Aufruf simuliert!

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 768
Thread-Synchronisation in Java: Beispiel 3
main()-Klasse TesteHuetteEinfach – Teil 1
1 public class TesteHuetteEinfach {
2
3 public static void main(String[] args) {
4 HuetteEinfach huette = new HuetteEinfach();
5 Gast [] gaeste = new Gast[4];
6 Koch [] koeche = new Koch[4];
Variable huette anlegen. Arrays für Gäste und Köche anlegen

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 769
Thread-Synchronisation in Java: Beispiel 3
main()-Klasse TesteHuetteEinfach – Teil 2
7 gaeste[0] = new Gast("Emil",huette);
8 gaeste[1] = new Gast("Erna",huette);
9 gaeste[2] = new Gast("Rita",huette);
10 gaeste[3] = new Gast("Herbert",huette);
Gäste erzeugen und ihnen die Referenz auf die Hütte mitgeben.

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 770
Thread-Synchronisation in Java: Beispiel 3
main()-Klasse TesteHuetteEinfach – Teil 3
11 koeche[0] = new Koch("Michi",huette,2000);
12 koeche[1] = new Koch("Ina",huette,1500);
13 koeche[2] = new Koch("Marie",huette,2500);
14 koeche[3] = new Koch("Thomas",huette,2300);
Köche erzeugen und ihnen die Referenz auf die Hütte mitgeben. Sie
bekommen außerdem ihre individuellen Spaghetti-Mengen mit.

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 771
Thread-Synchronisation in Java: Beispiel 3
main()-Klasse TesteHuetteEinfach – Teil 4
15 for (Koch k: koeche) { // erst Koeche starten
16 Thread t= new Thread(k);
17 t.start();
18 } // end for
19
20 for (Gast g: gaeste) { // dann Gaeste starten
21 Thread t = new Thread(g);
22 t.start();
23 } // end for
24 } // end method main()
25 } // end class
Threads für Köche und für Gäste starten.

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 772
Thread-Synchronisation
Fazit Beispiel 3
Wir haben den Zugri auf den Herd in einer Klasse HuetteEinfach
gekapselt.

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 772
Thread-Synchronisation
Fazit Beispiel 3
Wir haben den Zugri auf den Herd in einer Klasse HuetteEinfach
gekapselt.
Diese hatte die synchronisierten Methoden kochen() und essen()

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 772
Thread-Synchronisation
Fazit Beispiel 3
Wir haben den Zugri auf den Herd in einer Klasse HuetteEinfach
gekapselt.
Diese hatte die synchronisierten Methoden kochen() und essen()
Die zugreifenden Threads enthielten Runnables vom Typ Koch oder Gast.

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 772
Thread-Synchronisation
Fazit Beispiel 3
Wir haben den Zugri auf den Herd in einer Klasse HuetteEinfach
gekapselt.
Diese hatte die synchronisierten Methoden kochen() und essen()
Die zugreifenden Threads enthielten Runnables vom Typ Koch oder Gast.
Deren run()-Methode gri auf die synchronisierten Methoden kochen()
bzw. essen() eines HuetteEinfach-Objektes zu.

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 772
Thread-Synchronisation
Fazit Beispiel 3
Wir haben den Zugri auf den Herd in einer Klasse HuetteEinfach
gekapselt.
Diese hatte die synchronisierten Methoden kochen() und essen()
Die zugreifenden Threads enthielten Runnables vom Typ Koch oder Gast.
Deren run()-Methode gri auf die synchronisierten Methoden kochen()
bzw. essen() eines HuetteEinfach-Objektes zu.
Dieses HuetteEinfach-Objekt war der Monitor!

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 773
Thread-Synchronisation
Fazit Beispiel 3
Verbesserungspotential:

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 773
Thread-Synchronisation
Fazit Beispiel 3
Verbesserungspotential:
Scheduling war noch sehr primitiv – Gäste konnten auch leer ausgehen.

Threads Thread-Synchronisation mit dem Monitor-Konzept in Java Prof. Dr. Ute Matecki 773
Thread-Synchronisation
Fazit Beispiel 3
Verbesserungspotential:
Scheduling war noch sehr primitiv – Gäste konnten auch leer ausgehen.
Hier gibt es z.B. die Möglichkeit, mit der Thread-Methode join() auf
Threads zu warten – z. B. auf eine Koch-Thread.

Prof. Dr. Ute Matecki 774
Literatur I
[1] GOLL, J. u. a.: Java als erste Programmiersprache. 8. Teubner-Verlag,
2016
[2] OESTEREICH., B.: Analyse und Design mit der UML2.5. 11.
Oldenbourg-Verlag, 2013
[3] ORACLE: The Java-Tutorials – Language Basics.
http://download.oracle.com/javase/tutorial/java/
nutsandbolts/operators.html, 2018
[4] ULLENBOOM, Christian: Java ist auch eine Insel. 12. Rheinwerk Verlag,
