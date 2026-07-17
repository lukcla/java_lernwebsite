# Skript-Rohtext Teil 2: Generics – Übersicht & Wozu Generics? (Skript S. 544–549)

Programmierung 2
Generische Klassen (Generics)

Generische Klassen (Generics) Prof. Dr. Ute Matecki 544
Vorwort
Programmieren im Großen – Packages (Pakete)
Einstieg Streams
Generische Klassen (Generics)
Wozu Generics?
Einfache Generics und deren Anwendung
Standard-Interfaces der Java-API für Generics
Iterierbare Generics
Wildcards bei der Typisierung von Generics
Das Java-Collection-Framework

Generische Klassen (Generics) Prof. Dr. Ute Matecki 545
Annotationen
Threads

Generische Klassen (Generics) Wozu Generics? Prof. Dr. Ute Matecki 546
Generics – Behälter für Referenzvariablen
Generics – was ist das und wozu wird’s benötigt?
Behälter für beliebige Arten von Referenzvariablen, z.B.

Generische Klassen (Generics) Wozu Generics? Prof. Dr. Ute Matecki 546
Generics – Behälter für Referenzvariablen
Generics – was ist das und wozu wird’s benötigt?
Behälter für beliebige Arten von Referenzvariablen, z.B.
Klassen für beliebig verlängerbare/verkürzbare Listen (siehe ArrayList)

Generische Klassen (Generics) Wozu Generics? Prof. Dr. Ute Matecki 546
Generics – Behälter für Referenzvariablen
Generics – was ist das und wozu wird’s benötigt?
Behälter für beliebige Arten von Referenzvariablen, z.B.
Klassen für beliebig verlängerbare/verkürzbare Listen (siehe ArrayList)
Vektoren,

Generische Klassen (Generics) Wozu Generics? Prof. Dr. Ute Matecki 546
Generics – Behälter für Referenzvariablen
Generics – was ist das und wozu wird’s benötigt?
Behälter für beliebige Arten von Referenzvariablen, z.B.
Klassen für beliebig verlängerbare/verkürzbare Listen (siehe ArrayList)
Vektoren,
Mengen (Sets),

Generische Klassen (Generics) Wozu Generics? Prof. Dr. Ute Matecki 546
Generics – Behälter für Referenzvariablen
Generics – was ist das und wozu wird’s benötigt?
Behälter für beliebige Arten von Referenzvariablen, z.B.
Klassen für beliebig verlängerbare/verkürzbare Listen (siehe ArrayList)
Vektoren,
Mengen (Sets),
HashMaps,...

Generische Klassen (Generics) Wozu Generics? Prof. Dr. Ute Matecki 546
Generics – Behälter für Referenzvariablen
Generics – was ist das und wozu wird’s benötigt?
Behälter für beliebige Arten von Referenzvariablen, z.B.
Klassen für beliebig verlängerbare/verkürzbare Listen (siehe ArrayList)
Vektoren,
Mengen (Sets),
HashMaps,...
Interfaces, die Methoden für beliebige Arten von Referenzvariablen
vorgeben.

Generische Klassen (Generics) Wozu Generics? Prof. Dr. Ute Matecki 547
Generics – Behälter für Referenzvariablen
Nutzung von Generics – Beispiel ArrayList
Bereits kennen gelernt: Die ArrayList
1 ArrayList <Datentyp> liste = new ArrayList <Datentyp> ();
2
Typ-Parameter zur Typisierung der ListeVariablennameTyp-Parameter beim
Konstruktoraufruf

Generische Klassen (Generics) Wozu Generics? Prof. Dr. Ute Matecki 548
Generics – Behälterklassen für Referenzvariablen
Nutzung von Generics – Verallgemeinerte Form
Allgemeine generische Klasse nutzen
1 Generic <Datentyp> behaelter = new Generic <Datentyp> ();
2
Typ-Parameter zur
Typisierung des Behälters
VariablennameTyp-Parameter beim
Konstruktoraufruf

Generische Klassen (Generics) Wozu Generics? Prof. Dr. Ute Matecki 549
Generics – Behälterklassen für Referenzvariablen
Generics – Typ-Parameter
Bisher gewohnt: Durchreichen von Daten-Parametern über die runden
() Klammern einer Methode oder eines Konstruktors.

Generische Klassen (Generics) Wozu Generics? Prof. Dr. Ute Matecki 549
Generics – Behälterklassen für Referenzvariablen
Generics – Typ-Parameter
Bisher gewohnt: Durchreichen von Daten-Parametern über die runden
() Klammern einer Methode oder eines Konstruktors.
Bei der Nutzung eines Generics (z.B. ArrayList) wird bei der Typisierung
ein Typ-Parameter in <> übergeben:
Generic <Typ> variablenname;

Generische Klassen (Generics) Wozu Generics? Prof. Dr. Ute Matecki 549
Generics – Behälterklassen für Referenzvariablen
Generics – Typ-Parameter
Bisher gewohnt: Durchreichen von Daten-Parametern über die runden
() Klammern einer Methode oder eines Konstruktors.
Bei der Nutzung eines Generics (z.B. ArrayList) wird bei der Typisierung
ein Typ-Parameter in <> übergeben:
Generic <Typ> variablenname;
Dieser Typ-Parameter wird auch beim Konstruktoraufruf durchgereicht:
Generic <Typ> variablenname = new Generic<Typ>();

Generische Klassen (Generics) Wozu Generics? Prof. Dr. Ute Matecki 549
Generics – Behälterklassen für Referenzvariablen
Generics – Typ-Parameter
Bisher gewohnt: Durchreichen von Daten-Parametern über die runden
() Klammern einer Methode oder eines Konstruktors.
Bei der Nutzung eines Generics (z.B. ArrayList) wird bei der Typisierung
ein Typ-Parameter in <> übergeben:
Generic <Typ> variablenname;
Dieser Typ-Parameter wird auch beim Konstruktoraufruf durchgereicht:
Generic <Typ> variablenname = new Generic<Typ>();
Die runden () Klammern sind hierbei die Klammern für die
Daten-Parameter des Konstrukturs.

