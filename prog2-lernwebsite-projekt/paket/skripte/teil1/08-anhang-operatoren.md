# Skript-Rohtext: Anhang – Priorität von Operatoren (Skript S. 456–459)

2
• © Prof. Dr. Ute Matecki
Fakultät Informatik
Programmierung 2
Priorität von Operatoren

Priorität von Operatoren Prof. Dr. Ute Matecki 456
Priorität von Operatoren

Priorität von Operatoren Prof. Dr. Ute Matecki 457
Bei mehreren Operatoren in einem Ausdruck:
Priorität von Operatoren in Java
sagt aus, in welcher Reihenfolge Operatoren innerhalb eines Ausdrucks
ausgewertet werden.
Schulmathematik z.B.: „Punkt vor Strich“
Assoziativität: sagt aus, ob ein Operator von links nach rechts oder von
rechts nach links ausgewertet wird.

Priorität von Operatoren Prof. Dr. Ute Matecki 458
Operatorentabelle
Die Prioritäten sind folgendermaßen zu lesen:
Priorität 1: höchste Priorität
Priorität 15: niedrigste Priorität
frei nach [1], Kapitel 7.

Priorität von Operatoren Prof. Dr. Ute Matecki 459
Priorität Operatoren Bedeutung Assoziativität
1 [] Array-Index links
() Klammerung von Ausdrücken;
Klammern beim Methodenaufruf
links
. Zugri von außen auf Objektvariablen oder Methodenlinks
++ Postinkrementoperator links
-- Postdekrementoperator links
2 ++ Preinkrementoperator rechts
-- Predekrementoperator rechts
+ - Vorzeichen rechts
~ Bitweiser Negationsoperator rechts
! Logischer Negationsoperator rechts
3 (datentyp) Expliziter Typecast rechts

Priorität von Operatoren Prof. Dr. Ute Matecki 460
Priorität Operatoren Bedeutung Assoziativität
new Objekterzeugung rechts
4 * / % Multiplikationoperator, Divisionsoperator, Modulooperatorlinks
5 + - Additionsoperator, Subtraktionsoperatorlinks
+ Stringverkettungs-Operator links
6 >> >>> << Vorzeichenerhaltender
Rechtsshi, Vorzeichenloser Rechtsshi, Linksshi
links
7 < <= > >= Vergleichsoperatoren Kleiner,
Kleinergleich, Größer, Größergleich
links
instanceof Typüberprüfung eines Objekteslinks

Priorität von Operatoren Prof. Dr. Ute Matecki 461
Priorität Operatoren Bedeutung Assoziativität
8 == Gleichheitsoperator links
!= Ungleichheitsoperator links
9 & Bitweiser Undoperator links
10 ^ Bitweiser Exklusivoderoperator (ExOr)links
11 | Bitweiser Oderoperator links
12 && & Logischer Undoperator links
13 || | Logischer Oderoperator links
14 ? : Bedingungsoperator rechts
15 = Einfacher Zuweisungsoperatorrechts
+= -= *= /=
%= &= |= ^=
~= >> = >>>
<< =
Zusammengesetzte Zuweisungsoperatorenrechts

Priorität von Operatoren Prof. Dr. Ute Matecki 462
