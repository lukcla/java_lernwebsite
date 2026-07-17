# Skript-Rohtext Teil 2: Annotationen (Skript S. 686–713)

Programmierung 2
Annotationen

Annotationen Prof. Dr. Ute Matecki 686
Vorwort
Programmieren im Großen – Packages (Pakete)
Einstieg Streams
Generische Klassen (Generics)
Annotationen
Threads

Annotationen Prof. Dr. Ute Matecki 687
Wir erinnern uns an die erste Semesterhäle ...
Was ist eine Annotation?
Metainformation (über die Modifizierer hinaus) zu Deklarationen von
- Klassen,
- Methoden,
- Attributen
- uvm.

Annotationen Prof. Dr. Ute Matecki 687
Wir erinnern uns an die erste Semesterhäle ...
Was ist eine Annotation?
Metainformation (über die Modifizierer hinaus) zu Deklarationen von
- Klassen,
- Methoden,
- Attributen
- uvm.
Beginnt immer mit dem Zeichen @, gefolgt von dem Annotationsnamen

Annotationen Prof. Dr. Ute Matecki 687
Wir erinnern uns an die erste Semesterhäle ...
Was ist eine Annotation?
Metainformation (über die Modifizierer hinaus) zu Deklarationen von
- Klassen,
- Methoden,
- Attributen
- uvm.
Beginnt immer mit dem Zeichen @, gefolgt von dem Annotationsnamen
Werden von einem Bestandteil des Compilers ausgewertet

Annotationen Prof. Dr. Ute Matecki 687
Wir erinnern uns an die erste Semesterhäle ...
Was ist eine Annotation?
Metainformation (über die Modifizierer hinaus) zu Deklarationen von
- Klassen,
- Methoden,
- Attributen
- uvm.
Beginnt immer mit dem Zeichen @, gefolgt von dem Annotationsnamen
Werden von einem Bestandteil des Compilers ausgewertet
Unterschied zu Modifizierern: In Java können auch eigene Annotationen
implementiert werden

Annotationen Prof. Dr. Ute Matecki 687
Wir erinnern uns an die erste Semesterhäle ...
Was ist eine Annotation?
Metainformation (über die Modifizierer hinaus) zu Deklarationen von
- Klassen,
- Methoden,
- Attributen
- uvm.
Beginnt immer mit dem Zeichen @, gefolgt von dem Annotationsnamen
Werden von einem Bestandteil des Compilers ausgewertet
Unterschied zu Modifizierern: In Java können auch eigene Annotationen
implementiert werden
Das tun wir jetzt!

Annotationen Prof. Dr. Ute Matecki 688
Zusammensetzung von Annotationen
Eine Annotation wird definiert über ...
ein eigenes Interface, welches den Namen der gewünschten Annotation
bekommt – z.B. MySweetAnnotation

Annotationen Prof. Dr. Ute Matecki 688
Zusammensetzung von Annotationen
Eine Annotation wird definiert über ...
ein eigenes Interface, welches den Namen der gewünschten Annotation
bekommt – z.B. MySweetAnnotation
Das Interface beginnt mit dem Schlüsselwort @interface – daran
erkennen Sie, dass es sich um ein Annotations-Interface und nicht um
ein normales Interface handelt.

Annotationen Prof. Dr. Ute Matecki 688
Zusammensetzung von Annotationen
Eine Annotation wird definiert über ...
ein eigenes Interface, welches den Namen der gewünschten Annotation
bekommt – z.B. MySweetAnnotation
Das Interface beginnt mit dem Schlüsselwort @interface – daran
erkennen Sie, dass es sich um ein Annotations-Interface und nicht um
ein normales Interface handelt.
Dieses Interface kann auch Methoden (ähnlich getter()-Methoden)
enthalten, die Attibutwerte der Annotation liefern können.

Annotationen Prof. Dr. Ute Matecki 688
Zusammensetzung von Annotationen
Eine Annotation wird definiert über ...
ein eigenes Interface, welches den Namen der gewünschten Annotation
bekommt – z.B. MySweetAnnotation
Das Interface beginnt mit dem Schlüsselwort @interface – daran
erkennen Sie, dass es sich um ein Annotations-Interface und nicht um
ein normales Interface handelt.
Dieses Interface kann auch Methoden (ähnlich getter()-Methoden)
enthalten, die Attibutwerte der Annotation liefern können.
Die Datentypen dieser Attributwerte sind etwas eingeschränkt – später
mehr dazu!

Annotationen Prof. Dr. Ute Matecki 689
Zusammensetzung von Annotationen – Vorgehensmuster
1 public @interface MySweetAnno {
2 String name();
3 }
1 public class ExampleClass {
2
3 @MySweetAnno(name="Hugo")
4 public void hello() {
5 System.out.println("Hello!");
6 } // end method
7 } // end class

Annotationen Prof. Dr. Ute Matecki 690
Einfachst mögliche Annotation
Eine Annotation, die nichts tut und nur so da ist ...
1 public @interface SoDa {
2 // Diese Annotation steht nur "so da"
3 }
Vereinbarung einer (leeren) Marker-Annotation

Annotationen Prof. Dr. Ute Matecki 691
Einfachst mögliche Annotation
Verwendung einer Annotation, die nichts tut und nur so da ist ...
1 @SoDa
2 public class TesteSoDa {
3
4 @SoDa
5 public void hallo() {
6 System.out.println(
7 "Ich bin einfach so da!");
8 } // end method
9 } // end class
Anwendungskontext der Annotation war nicht begrenzt – sie kann hier
am Klassenkopf und am Methodenkopf angebracht werden!

Annotationen Prof. Dr. Ute Matecki 692
Attribute von Annotationen ...
...sind in ihrer Typisierung eingeschränkt. Erlaubt sind hier:
String
Elementare Datentypen (keine Wrapper – also z.B.: int aber nicht Integer)
Class
Annotationen (:führt zu verschachtelten Annotationen)
Aufzählungsdatentypen (Enum)
Eindimensionale Arrays der o.g. Datentypen

Annotationen Prof. Dr. Ute Matecki 693
Weitere Eigenschaen von eigenen Annotationen ...
...können mit folgenden API-Annotationen definiert werden:
API-Annotation Erklärung
@Documented Nutzerdefinierte Annotation soll in der OnlineDokumentation (Javadoc) angezeigt werden.

Annotationen Prof. Dr. Ute Matecki 693
Weitere Eigenschaen von eigenen Annotationen ...
...können mit folgenden API-Annotationen definiert werden:
API-Annotation Erklärung
@Documented Nutzerdefinierte Annotation soll in der OnlineDokumentation (Javadoc) angezeigt werden.
@Inherited
Wenn eine nutzerdefinierte Annotation mit @Inherited
gekennzeichnet ist, so wirkt sie nicht nur auf die Klasse,
bei der sie angebracht wird, sondern auch auf deren abgeleitete Klassen.

Annotationen Prof. Dr. Ute Matecki 693
Weitere Eigenschaen von eigenen Annotationen ...
...können mit folgenden API-Annotationen definiert werden:
API-Annotation Erklärung
@Documented Nutzerdefinierte Annotation soll in der OnlineDokumentation (Javadoc) angezeigt werden.
@Inherited
Wenn eine nutzerdefinierte Annotation mit @Inherited
gekennzeichnet ist, so wirkt sie nicht nur auf die Klasse,
bei der sie angebracht wird, sondern auch auf deren abgeleitete Klassen.
@Retention
Gibt an, ob die Annotation nur zum Compile-Zeitpunkt
wirkt, oder auch zur Laufzeit.

Annotationen Prof. Dr. Ute Matecki 693
Weitere Eigenschaen von eigenen Annotationen ...
...können mit folgenden API-Annotationen definiert werden:
API-Annotation Erklärung
@Documented Nutzerdefinierte Annotation soll in der OnlineDokumentation (Javadoc) angezeigt werden.
@Inherited
Wenn eine nutzerdefinierte Annotation mit @Inherited
gekennzeichnet ist, so wirkt sie nicht nur auf die Klasse,
bei der sie angebracht wird, sondern auch auf deren abgeleitete Klassen.
@Retention
Gibt an, ob die Annotation nur zum Compile-Zeitpunkt
wirkt, oder auch zur Laufzeit.
@Target
Gibt an, auf welche Art von Quellcode-Elementen eine
Annotation angewendet werden kann (Klasse, Methoden, lokale Variablen, etc.)

Annotationen Prof. Dr. Ute Matecki 694
Beispiel für annotierte Annotationen
Eine Annotation für Klassenköpfe: ClassHeader
1 import static java.lang.annotation.ElementType.TYPE;
2 import static java.lang.annotation.RetentionPolicy.RUNTIME;
3 import java.lang.annotation.Retention;
4 import java.lang.annotation.Target;
5
6 @Retention(RUNTIME)
7 @Target(TYPE)
8 public @interface ClassHeader {
9 int version(); // Versionsnummer
10 String faculty(); // Fakultaet Autor/in
11 String university(); // Universitaet Autor/in
12 } // end annotation

Annotationen Prof. Dr. Ute Matecki 695
Beispiel für annotierte Annotationen
Eine Annotation für Klassenköpfe: ClassHeader
1 import static java.lang.annotation.ElementType.TYPE;
2 import static java.lang.annotation.RetentionPolicy.RUNTIME;
3 import java.lang.annotation.Retention;
4 import java.lang.annotation.Target;
5
6 ...
Import der Annotationen und statischen Konstanten, mit denen unsere
selbstdefinierte Annotation gekennzeichnet wird.

Annotationen Prof. Dr. Ute Matecki 696
Beispiel für annotierte Annotationen
Eine Annotation für Klassenköpfe: ClassHeader
6 //...
7 @Retention(RUNTIME)
8 @Target(TYPE)
9 public @interface ClassHeader {
10 //...
11 } // end annotation
Zur Laufzeit ist feststellbar, wo und mit welchen Parametern diese
Annotation angeheet wurde.
Die Annotation kann an Datentyp-Definitionen (z.B. Klassen) geheet
werden.

Annotationen Prof. Dr. Ute Matecki 697
Beispiel für annotierte Annotationen
Eine Annotation für Klassenköpfe: ClassHeader
7 // ...
8 public @interface ClassHeader {
9
10 int version(); // Versionsnummer
11 String faculty(); // Fakultaet Autor/in
12 String university(); // Universitaet Autor/in
13
14 } // end annotation
Attribute der Annotation – sehen ähnlich aus wie getter()- Methoden.

Annotationen Prof. Dr. Ute Matecki 698
Beispiel für annotierte Annotationen
Eine Annotation für Methodenköpfe: MethodHeader
1 import static java.lang.annotation.ElementType.METHOD;
2 import static java.lang.annotation.RetentionPolicy.RUNTIME;
3
4 import java.lang.annotation.Retention;
5 import java.lang.annotation.Target;
6
7 @Retention(RUNTIME)
8 @Target(METHOD)
9 public @interface MethodHeader {
10 String author(); // Autor der Methode
11 String lastChangeBy(); // letzte Aenderung von?
12 } // end annotation
Annotation kann an Methoden geheet werden.

Annotationen Prof. Dr. Ute Matecki 699
Beispiel für annotierte Annotationen
Klasse an die unsere Annotationen geheet werden: ClassToAnnotate
1
2 @ClassHeader(version=1,faculty="Informatik",university="HSAS")
3 public class ClassToAnnotate {
4
5 private String name; // ein String
6
7 public ClassToAnnotate(String name) {
8 this.name = name;
9 } // end constructor
Annotation wird an den Klassenkopf geheet. Die Attribute werden wie
Übergabeparameter behandelt – allerdings mit zugewiesenen Werten.

Annotationen Prof. Dr. Ute Matecki 700
Beispiel für annotierte Annotationen
Klasse an die unsere Annotationen geheet werden: ClassToAnnotate
1
2 @MethodHeader(author="U. Matecki",lastChangeBy="H. Helmchen")
3 public String getName() {
4
5 return name;
6 } // end method
7
8 @MethodHeader(author="U. Matecki",lastChangeBy="H. Helmchen")
9 public void setName(String name) {
10
11 this.name = name;
12 } // end method
Annotation wird an den Methodenkopf geheet.

Annotationen Prof. Dr. Ute Matecki 701
Beispiel für annotierte Annotationen
Klasse an die unsere Annotationen geheet werden: ClassToAnnotate
1
2 @MethodHeader(author="U. Matecki",lastChangeBy="H. Helmchen")
3 public void sayHello(String greeting, String nameTo) {
4
5 System.out.println(greeting + " " + nameTo);
6 System.out.println("I'm " +name);
7 } // end method
8 } // end class
Annotation wird an den Methodenkopf geheet.

Annotationen Prof. Dr. Ute Matecki 702
Laufzeit-Abfrage der angeheeten Annotationen ...
... über Java-Reflections
Java-Reflections erlauben zur Laufzeit
die Abfrage von Eigenschaen zu Klassen, Klasseninhalten wie z.B.:
- Name einer Klasse
- Methoden einer Klasse
- Annotationen einer Klasse

Annotationen Prof. Dr. Ute Matecki 702
Laufzeit-Abfrage der angeheeten Annotationen ...
... über Java-Reflections
Java-Reflections erlauben zur Laufzeit
die Abfrage von Eigenschaen zu Klassen, Klasseninhalten wie z.B.:
- Name einer Klasse
- Methoden einer Klasse
- Annotationen einer Klasse
die Abfrage von Methodeneigenschaen wie
- Name einer Methode
- Parameter einer Methode
- Annotationen einer Methode

Annotationen Prof. Dr. Ute Matecki 702
Laufzeit-Abfrage der angeheeten Annotationen ...
... über Java-Reflections
Java-Reflections erlauben zur Laufzeit
die Abfrage von Eigenschaen zu Klassen, Klasseninhalten wie z.B.:
- Name einer Klasse
- Methoden einer Klasse
- Annotationen einer Klasse
die Abfrage von Methodeneigenschaen wie
- Name einer Methode
- Parameter einer Methode
- Annotationen einer Methode
viele weitere Eigenschaen

Annotationen Prof. Dr. Ute Matecki 703
Laufzeit-Abfrage der angeheeten Annotationen ...
... über Java-Reflections
Wir verwenden folgende Klassen aus den Java-Reflections:
java.lang.Class

Annotationen Prof. Dr. Ute Matecki 703
Laufzeit-Abfrage der angeheeten Annotationen ...
... über Java-Reflections
Wir verwenden folgende Klassen aus den Java-Reflections:
java.lang.Class
java.lang.reflect.Method

Annotationen Prof. Dr. Ute Matecki 703
Laufzeit-Abfrage der angeheeten Annotationen ...
... über Java-Reflections
Wir verwenden folgende Klassen aus den Java-Reflections:
java.lang.Class
java.lang.reflect.Method
Interessant sind außerdem die Klassen:
- java.lang.reflect.Constructor (Infos zu einem Konstruktor)
- java.lang.reflect.Annotation (Infos zu einer Annotation)
- java.lang.reflect.Parameter (Übergabeparameter einer Methode)
- java.lang.reflect.Field (Objekt- und Klassenvariablen)

Annotationen Prof. Dr. Ute Matecki 704
Laufzeit-Abfrage der angeheeten Annotationen ...
... über Java-Reflections
Vorgehen bei der Laufzeit-Abfrage
Jede Java-Klasse enthält eine statische Variable class vom Typ
java.lang.Class.

Annotationen Prof. Dr. Ute Matecki 704
Laufzeit-Abfrage der angeheeten Annotationen ...
... über Java-Reflections
Vorgehen bei der Laufzeit-Abfrage
Jede Java-Klasse enthält eine statische Variable class vom Typ
java.lang.Class.
Von dieser können wir alle weiteren Informationen zu dieser Klasse
erreichen:
- Infos zu Methoden – einschließlich deren Annotationen
- Infos zu Konstruktoren – einschließlich deren Annotationen
- Infos zu Annotationen (bezogen auf die Klasse)
- Infos zu Objekt- und Klassenvariablen

Annotationen Prof. Dr. Ute Matecki 705
Laufzeit-Abfrage der angeheeten Annotationen
Klasse TestOurAnnotations
1 import java.lang.reflect.Method;
2
3 public class TestOurAnnotations {
4 public static void main(String [] args) {
Einbinden der Java-Reflection-Klasse java.lang.reflect.Method zur
Abfrage von Methodeneigenschaen.
Die Klasse java.lang.Class muss nicht extra eingebunden werden – wir
haben automatisch Zugri auf sie.

Annotationen Prof. Dr. Ute Matecki 706
Laufzeit-Abfrage der angeheeten Annotationen
Klasse TestOurAnnotations
5 // Ist Testklasse ueberhaupt annotiert?
6 if (ClassToAnnotate. class .isAnnotationPresent(
7 ClassHeader.class )) {
8 // Wenn ja -- ausgeben
9 System.out.println("Annotiert mit @ClassHeader");
Class-Variable der annotierten Klasse ClassToAnnoTate
Class-Variable der selbst geschriebenenen Annotation ClassHeader

Annotationen Prof. Dr. Ute Matecki 707
Laufzeit-Abfrage der angeheeten Annotationen
Klasse TestOurAnnotations
10 // ClassHeader Annotation von Testklasse abfragen
11 ClassHeader ch =
12 ClassToAnnotate. class.getAnnotation(ClassHeader.class) ;
13
14 // Alle Annotationsparameter auslesen und ausgeben
15 System.out.println("Faculty: " + ch.faculty());
16 System.out.println("University: " + ch.university());
17 } // end if
Annotation ClassHeader von unserer Testklasse ClassToAnnotate
abfragen. Falls diese Annotation in ClassToAnnotate angeheet wurde,
so werden ihre Informationen (mit Parameterwerten) zurück geliefert.

Annotationen Prof. Dr. Ute Matecki 708
Laufzeit-Abfrage der angeheeten Annotationen
Klasse TestOurAnnotations
18 else {
19 // Melde, dass Klasse NICHT mit dieser Annotation
20 // gekennzeichnet ist.
21 System.out.println( "Klasse " +
22 ClassToAnnotate.class.getName() +
23 " Nicht annotiert mit @ClassHeader");
24 } // end else

Annotationen Prof. Dr. Ute Matecki 709
Laufzeit-Abfrage der angeheeten Annotationen
Klasse TestOurAnnotations
25 // Von allen Methoden der Testklasse die
26 // Annotationen abfragen
27 for (Method m : ClassToAnnotate.class.getMethods() ) {
28 // Wenn Methode passend annotiert ist ...
29 if ( m.isAnnotationPresent(MethodHeader.class) ) {
Methode getMethods() aus Klasse Class liefert ein Array aus
Method-Referenzen zurück. Dieses werten wir mit der Iterator- Schleife
aus.
Überprüfen, ob Methode mit MethodHeader annotiert ist

Annotationen Prof. Dr. Ute Matecki 710
Laufzeit-Abfrage der angeheeten Annotationen
Klasse TestOurAnnotations
30
31 // Annotationsdaten abfragen
32 MethodHeader mh =
33 m.getAnnotation(MethodHeader.class);
34
35 // Annotatinsdaten ausgeben
36 System.out.println("Methode " + m.getName());
37 System.out.println("Author: " + mh.author());
38 System.out.println("Last change by: " +
39 mh.lastChangeBy());
40 } // end if
Angeheete MethodHeader-Annotation der Methode mit
getAnnotation(...) aus Reflection-Klasse Method abfragen.

Annotationen Prof. Dr. Ute Matecki 711
Laufzeit-Abfrage der angeheeten Annotationen
Klasse TestOurAnnotations
28 else {
29 // Melde, dass Methode nicht mit dieser
30 // Annotation gekennzeichnet ist
31 System.out.println("Methode " + m.getName() +
32 " nicht gekennzeichnet mit @MethodHeader");
33 } // end else
34 } // end for
35 } // end method main()
36 } // end class
Abfrage des überprüen Methodennamens mit getName() aus
Reflection-Klasse Method

Annotationen Prof. Dr. Ute Matecki 712
Zusammenfassung zu Annotationen
Wir merken uns:
Mit Annotationen können wir Metainformation (über die Modifizierer
hinaus) an Deklarationen von Klassen, Methoden und weiteren
Quellcode-Elementen „anheen“.

Annotationen Prof. Dr. Ute Matecki 712
Zusammenfassung zu Annotationen
Wir merken uns:
Mit Annotationen können wir Metainformation (über die Modifizierer
hinaus) an Deklarationen von Klassen, Methoden und weiteren
Quellcode-Elementen „anheen“.
Es gibt jede Menge vorgefertigte Annotationen der Java-API
(beispielsweise @Override,@Target, @Retention, etc.)

Annotationen Prof. Dr. Ute Matecki 712
Zusammenfassung zu Annotationen
Wir merken uns:
Mit Annotationen können wir Metainformation (über die Modifizierer
hinaus) an Deklarationen von Klassen, Methoden und weiteren
Quellcode-Elementen „anheen“.
Es gibt jede Menge vorgefertigte Annotationen der Java-API
(beispielsweise @Override,@Target, @Retention, etc.)
Annotationen (auch selbst definierte) werden als Interfaces mit dem
Schlüsselwort @interface definiert.

Annotationen Prof. Dr. Ute Matecki 712
Zusammenfassung zu Annotationen
Wir merken uns:
Mit Annotationen können wir Metainformation (über die Modifizierer
hinaus) an Deklarationen von Klassen, Methoden und weiteren
Quellcode-Elementen „anheen“.
Es gibt jede Menge vorgefertigte Annotationen der Java-API
(beispielsweise @Override,@Target, @Retention, etc.)
Annotationen (auch selbst definierte) werden als Interfaces mit dem
Schlüsselwort @interface definiert.
Annotationen können eigene Attribute haben, die aber typmäßig
eingeschränkt sind.

Annotationen Prof. Dr. Ute Matecki 713
Zusammenfassung zu Annotationen
Wir merken uns:
Die Werte für diese Attribute werden beim „Anheen“ mit durchgereicht.

Annotationen Prof. Dr. Ute Matecki 713
Zusammenfassung zu Annotationen
Wir merken uns:
Die Werte für diese Attribute werden beim „Anheen“ mit durchgereicht.
Über die Klasse java.lang.Class und einige Klassen der
Java-Reflections-API (Package java.lang.reflect) können wir zur Laufzeit
angeheete Annotationen und deren Attribute abfragen.

Annotationen Prof. Dr. Ute Matecki 713
Zusammenfassung zu Annotationen
Wir merken uns:
Die Werte für diese Attribute werden beim „Anheen“ mit durchgereicht.
Über die Klasse java.lang.Class und einige Klassen der
Java-Reflections-API (Package java.lang.reflect) können wir zur Laufzeit
angeheete Annotationen und deren Attribute abfragen.
Nur Annotationen, die selbst mit der @Retention(RUNTIME)
gekennzeichnet sind, können zur Laufzeit abgefragt werden.

2
• © Prof. Dr. Ute Matecki
Fakultät Informatik
