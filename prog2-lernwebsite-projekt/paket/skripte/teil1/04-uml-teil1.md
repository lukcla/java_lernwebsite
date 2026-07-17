# Skript-Rohtext: UML-Klassendiagramme – Teil 1 (Skript S. 261–281)

2
• © Prof. Dr. Ute Matecki
Fakultät Informatik
Programmierung 2
UML-Klassendiagramme – Teil 1

UML-Klassendiagramme – Teil 1 Prof. Dr. Ute Matecki 261
Vorwort
Einstieg in Java
Einstieg in die OOP: Klassen und Objekte/Instanzen
Die Klasse String
Graphische Darstellung von Klassen mit der UML – Teil 1
Einfache Klassendarstellungen
Klassenbeziehungen – Teil 1
Assoziation
Aggregation und Komposition

UML-Klassendiagramme – Teil 1 Prof. Dr. Ute Matecki 262
Vererbungsbeziehungen
Exceptions
Einstieg Streams

UML-Klassendiagramme – Teil 1 Einfache Klassendarstellungen Prof. Dr. Ute Matecki 263
Bisher behandelt: Klassendarstellung direkt in Java
Bisher: Klassendarstellung in Java mit ...
Klassenname und ggf. Modifier,
Attributen und deren Modifier,
Konstruktoren und sonstigen Methoden und deren Modifier
Bei Konstruktoren und Methoden ist auch sofort die Implementierung
sichtbar
:wird schnell unübersichtlich!

UML-Klassendiagramme – Teil 1 Einfache Klassendarstellungen Prof. Dr. Ute Matecki 264
Bisher behandelt: Klassendarstellung direkt in Java
Bisher:Buch-Klasse in Java – Teil 1
1 public class Buch1 {
2 private String autor;
3 private String titel;
4 private int auflage;
5
6 public Buch1(String autor, String titel, int auflage) {
7 this.autor = autor;
8 this.titel = titel;
9 this.auflage = auflage;
10 } // end constructor

UML-Klassendiagramme – Teil 1 Einfache Klassendarstellungen Prof. Dr. Ute Matecki 265
Bisher behandelt: Klassendarstellung direkt in Java
Bisher:Buch-Klasse in Java – Teil 2
10 public String getAutor () {
11 return autor;
12 } // end method
13
14 public String getTitel() {
15 return titel;
16 } // end

UML-Klassendiagramme – Teil 1 Einfache Klassendarstellungen Prof. Dr. Ute Matecki 266
Bisher behandelt: Klassendarstellung direkt in Java
Bisher:Buch-Klasse in Java – Teil 3
16 public int getAuflage() {
17 return auflage;
18 } // end method
19
20 public void setAuflage(int auflage) {
21 this.auflage = auflage;
22 } // end method
23 } // end class

UML-Klassendiagramme – Teil 1 Einfache Klassendarstellungen Prof. Dr. Ute Matecki 267
Neu: Graphische Darstellung von Klassen in der UML2
Einfache Klassendiagramme: UML-Darstellung einer Klasse Buch1
Klassenname
Attribute
Konstruktor und
übrige Methoden
Buch1
- autor: String
- titel: String
- auflage: int
+ Buch1(autor: String, titel: String, auflage: int)
+ getAutor(): String
+ getTitel(): String
+ getAuflage(): int
+ setAuflage(auflage: int): void
Modifier public
Modifier private

UML-Klassendiagramme – Teil 1 Einfache Klassendarstellungen Prof. Dr. Ute Matecki 268
Neu: Graphische Darstellung von Klassen in der UML2
Einfache Klassendiagramme: Reduzierte UML-Darstellung einer Klasse Buch1
Klassenname
Attribute
Konstruktor, getter
und setter werden
manchmal auch im
Diagramm weggelassen.
Buch1
- autor: String
- titel: String
- auflage: int
+ print()
Nur "echte" Methoden werden in dieser
Variante des Diagramms gezeigt!

UML-Klassendiagramme – Teil 1 Einfache Klassendarstellungen Prof. Dr. Ute Matecki 269
Neu: Graphische Darstellung von Klassen in der UML2
Einfache Klassendiagramme
Erläuterung der UML-Elemente des Klassendiagramms
Der obere Block enthält immer den Klassennamen.
Der mittlere Block enthält die Spezifikation der Attribute der Klasse.
Der untere Block enthält die Spezifikation der Konstruktoren und der
sonstigen Methoden der Klasse.
Der Modifier public erscheint als +-Zeichen vor den Attributen bzw.
Methoden.
Der Modifier private erscheint als - - Zeichen vor den Attributen bzw.
Methoden.

UML-Klassendiagramme – Teil 1 Einfache Klassendarstellungen Prof. Dr. Ute Matecki 270
Neu: Graphische Darstellung von Klassen in der UML2
Einfache Klassendiagramme
Erläuterung der UML-Elemente des Klassendiagramms
Der Datentyp von Attributen und Parametervariablen wird – entgegen
unserer gewohnten Syntax von Java – nach Bezeichner und
Doppelpunkt angegeben mit:
variablenname : Datentyp
Auch der Rückgabetyp von Methoden wird – entgegen unserer
gewohnten Syntax von Java – nach Methodenkopf und Doppelpunkt
angegeben mit:
methodenKopf(...) : Datentyp

UML-Klassendiagramme – Teil 1 Klassenbeziehungen – Teil 1 Prof. Dr. Ute Matecki 271
Klassenbeziehungen – Teil1
Bisher: Klassen wurden einzeln dargestellt ...
... aber standen nicht in Beziehung zueinander.
In Real-World-Anwendungen gibt es nicht nur eine Klasse, sondern viele
Klassen.
Zwischen den Klassen bestehen Abhängigkeiten, wie beispielsweise
Leser besitzt Bücher (1:n-Beziehung), oder ...
Leser liest Buch(1:1-Beziehung)

UML-Klassendiagramme – Teil 1 Klassenbeziehungen – Teil 1 Prof. Dr. Ute Matecki 272
Assoziation
Einfache, ungerichtete Assoziation
Leser Buch
Welche Klasse über Attribute hier auf wen Zugri hat, ist noch nicht
ersichtlich (Richtung fehlt).
Leserichtung (Buch hat Leser, Leser liest Buch) der Beziehung ist auch
noch nicht erkennbar.
Multiplizität (1:1, 1:n, etc) fehlt noch.

UML-Klassendiagramme – Teil 1 Klassenbeziehungen – Teil 1 Prof. Dr. Ute Matecki 273
Assoziation
Einfache, ungerichtete Assoziation mit Multiplizitäten
A B
1 1..*
Multiplizität / Kardinalität: gibt an, wie viele Objekte der Klasse B ein
Objekt der Klasse A kennen kann oder muss.
- Multiplizität wird an beiden Enden der Assoziation angegeben.
- Hier: 1 Objekt der Klasse A kennt 1 bis mehrere Objekte der Klasse B.
Folgende Multiplizitäten werden an den Assoziationsenden häufig
verwendet:
- 1 steht für: 1 Objekt von Klasse X
- 1..* steht für: 1 oder mehrere Objekte von Klasse X
- 0..* steht für: 0 oder mehrere Objekte von Klasse X (also: Objekte von X können
optional vorkommen)

UML-Klassendiagramme – Teil 1 Klassenbeziehungen – Teil 1 Prof. Dr. Ute Matecki 274
Assoziation
Einfache, ungerichtete Assoziation mit Multiplizitäten
Leser Buch
1 1
+liest
Buch-Beispiel:
1 Leser liest zu einer Zeit 1 Buch
Assoziation hat einen Namen (liest)
Assoziation ist (public)

UML-Klassendiagramme – Teil 1 Klassenbeziehungen – Teil 1 Prof. Dr. Ute Matecki 275
Assoziation
Gerichtete Assoziation mit Multiplizitäten und Sichtbarkeit
Leser Buch +liest
1 1
1 Objekt der Klasse Leser grei auf 1 Objekt der Klasse Buch zu
Zugri erfolgt z. B. über ein Attribut vom Typ Buch

UML-Klassendiagramme – Teil 1 Klassenbeziehungen – Teil 1 Prof. Dr. Ute Matecki 276
Assoziation
Gerichtete Assoziation mit Multiplizitäten und Sichtbarkeit
Leser Buch +besitzt
1 0..*
1 Leser kann zu einer Zeit 0 oder mehrere Bücher besitzen
Zugri erfolgt z.B. über eine Liste von Buch-Referenzen

UML-Klassendiagramme – Teil 1 Klassenbeziehungen – Teil 1 Prof. Dr. Ute Matecki 277
Assoziation
Gerichtete Assoziation – Zugri und Leserichtung
Autor Buch
1..* 1..*
schreibt
: Offene Pfeilspitze: "hat Zugriff auf" (hier: Klasse Autor enthält eine Liste mit 
 Buch-Referenzen;
: Dreieck: Leserichtung (hier: Autor kann Bücher schreiben, aber Bücher können
 keine Autoren Schreiben)
 Klasse Buch enthält eine Liste mit seinen Autoren) 
 
Pfeilspitzen an den Enden der Assoziation beschreiben, wer auf wen
Zugri hatDreieck über der Assoziation sagt aus, in welcher Richtung die
Assoziation zu lesen ist.

UML-Klassendiagramme – Teil 1 Klassenbeziehungen – Teil 1 Prof. Dr. Ute Matecki 278
Assoziation
Gerichtete Assoziation – mehr als 2 Klassen
Buch
Bibliothekar
1..* +verwaltet
1..*
+besitzt
1
0..*
1 oder mehrere Bibliothekare verwalten 1 oder mehrere Bücher –
nämlich den Bibliotheksbestand.
- Achtung: Nach dieser Modellierung darf der Bibliotheksbestand nicht leer sein!
- :Das muss beim Entnehmen überprü werden! (Sinnvoll so???)
1 Bibliothekar kann aber privat auch 0 oder mehrere Bücher privat aus
dem Bestand der Bibliothek erworben haben (falls die Bibliothek so
etwas ermöglicht)

UML-Klassendiagramme – Teil 1 Klassenbeziehungen – Teil 1 Prof. Dr. Ute Matecki 279
Aggregation und Komposition
... sind spezielle Assoziationen.
Beide drücken aus: Objekt von Klasse A ist Bestandteil von Objekt von
Klasse B.
Auch hier sind Multiplizitäten möglich.

UML-Klassendiagramme – Teil 1 Klassenbeziehungen – Teil 1 Prof. Dr. Ute Matecki 280
Aggregation
Formale Darstellung
A B Aggregation:
- Objekt(e) von Klasse B sind Bestandteil von Klasse A
- Sie existieren aber auch noch weiter, wenn Objekt der
 Klasse A gelöscht wird.
Auto Rad 1 1..*
Beispiel 1:
- Die Räder sind Bestandteil des Autos.
- Sie existieren aber auch noch weiter, wenn das Auto in die
 Schrottpresse kommt. Sie können z. B. weiterverkau� werden.
Fabrik Maschine 1 1..*
Beispiel 2:
- Maschinen stehen im Fabrikgebäude einer Firma.
- Sie existieren aber auch noch weiter, wenn das Gebäude auf-
 gegeben wird. Sie können umplatziert oder weiterverkau� werden.

UML-Klassendiagramme – Teil 1 Klassenbeziehungen – Teil 1 Prof. Dr. Ute Matecki 281
Komposition
Formale Darstellung
A B Komposition:
- Auch hier: Objekt(e) von B sind Bestandteil von A
- Aber: Wenn aber A gelöscht wird, so existiert B ebenfalls nicht mehr,
 sondern wird ebenfalls gelöscht.
Beispiel 1:
- 1 oder mehrere Räume sind Bestandteil eines Gebäudes (z. B.
 Gebäude 210 in der Gartenstraße)
- Wenn die HS das Gebäude nicht mehr mietet, kann sie im WebUntis
 auch nicht mehr die Räume verplanen! (Sie sind also mit gelöscht)
Gebäude 1 1..* Raum
Beispiel 2:
- 1 oder mehrere Buttons sind in einem Window (z. B. Öffnen-Dialog)
 platziert.
- Wenn das Window gelöscht wird (z. B. nach dem Zuklappen), so sind
 die Buttons ebenfalls gelöscht.
Window 1 1..* Button

