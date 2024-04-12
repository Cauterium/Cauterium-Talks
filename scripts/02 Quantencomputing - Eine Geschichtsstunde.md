---
tags:
  - done
---
# Quantencomputing: Geschichte
## Von Feynman über Shor bis zu aktueller Forschung

notes:
Hello there! Heute geht es um die Geschichte von Quantencomputern. Wir fangen an ganz am Anfang bei Richard Feynmans Formulierung vom Konzept eines Quantencomputers, gehen über einige wichtige Algorithmen, wie Peter Shors Faktorisierungsalgorithmus, die das Feld vorangebracht haben, bis hin zu aktueller Forschung zu Quantencomputern.
Das meiste in diesem Video ist aus dem zweiten Kapitel des Buchs "Quantum Computing: An Applied Approach" von Jack D. Hidary. Wer sich für Quantencomputing interessiert und einen breiten Überblick über das Feld haben will, sollte sich das Buch auf jeden Fall mal anschauen!

---
![[cc-logo.png]]
https://github.com/Cauterium/Cauterium-Talks

notes:
Alles, was ihr hier seht, sowie alle meine Skripte ist öffentlich verfügbar auf Github unter der Creative Commons Lizenz. Link ist in der Videobeschreibung. 

---

# Das Konzept von Quantencomputern
## Richard Feynman, Paul Benioff und Quanten-Turingmaschinen

notes:
Meistens wird gesagt, das Richard Feynman der erste sei, der das Konzept von Quantencomputern erfunden hat. Allerdings gab es mehrere Forscher, die schon vor ihm die Idee von Quantencomputern angeschaut haben. Einer von ihnen war Paul Benioff.
Er beschreibt, wie eine Turingmaschine mit einem quantenmechanischen System konstruiert werden kann. Turingmaschinen sind in der Informatik das grundlegendste Modell, um einen Computer zu beschreiben. Eine universelle Turingmaschine kann jeden berechenbaren Algorithmus ausführen. Das widerum heißt, dass auch alles, was eine Turingmaschine irgendwie simulieren kann, ebenfalls jeden berechenbaren Algorithmus ausführen kann.

---
### Turingmaschine

![[turing-machine.png]]

notes:
Eine Turingmaschine besteht aus 3 Teilen: Einem Band, auf dem Symbole, zum Beispiel 1 und 0 stehen können, einem Lese-/Schreibkopf, der das Symbol auf dem aktuellen Feld des Bands lesen kann und darauf schreiben kann, und dem Programm an sich, das bestimmt, in welchen Situationen, welches Symbol geschrieben wird und, wann sich der Lese-/Schreibkopf nach links oder nach rechts bewegt.
Mit diesem Modell können wir jeden Algorithmus umsetzen. Wenn wir also zeigen wollen, dass ein anderes Modell ebenfalls diese Eigenschaft hat, also ebenfalls turingmächtig ist, müssen wir nur einen Weg finden, wie wir mit dem anderen Modell alle einzelnen Aktionen einer Turingmaschine simulieren können. Paul Benioff hat genau das mit dem Modell von quantenmechanischen Systemen gemacht und damit die grundlegende Theorie von Quantencomputern beschrieben. Die mathematischen Details erspar ich euch mal.

---
### Feynmans Rede

> "Nature isn’t classical dammit ..." - Richard Feynman, 1981

notes:
Kommen wir zu Richard Feynman. Im Jahr 1981 hat er auf einer Konferenz zur Simulation von Physik mit Computern eine Rede gehalten. In seiner Rede argumentiert er, dass klassische Computer nicht in der Lage sind, die hohe Anzahl an Variablen zu handhaben, die zur Beschreibung von quantenmechanischen Systemen nötig ist. Er schlägt stattdessen die Verwendung von einem Quantencomputer vor, um Probleme der Quantenphysik zu lösen, die Forscher zuvor nicht mit klassischen Computern lösen konnten.
Er schließt seine Rede mit den Worten: "Nature isn't classical dammit, and if you want to make a simulation of nature you better make it quantum mechanical  [...]". Die Natur ist nicht klassisch, und wenn man eine Simulation der Natur machen will, macht man es besser quantenmechanisch.
Was zu diesem Zeitpunkt allerdings weder Feynman, noch die Forscher in der Physik wussten, war, wie man so eine Maschine überhaupt bauen könnte.

---
# Erste Quantenalgorithmen

notes:
Das hat die Forscher aber nicht davon abgehalten, sich zumindest schon mal theoretisch mit dem Konzept zu beschäftigen. Nachdem die grundlegende Theorie, wie ein Quantencomputer funktionieren sollte etabliert war, begannen verschiedene Forscher, Algorithmen für Quantencomputer zu entwickeln. Einer von ihnen war David Deutsch.

---
## Deutsch-Jozsa Algorithmus

### Das erste Beispiel für Quantenvorteil

notes:
David Deutsch entwickelte den ersten Algorithmus, der auf einem Quantencomputer eine schnellere Laufzeit hat. Er formuliert folgendes Problem: Wir haben eine Funktion, von der wir nicht wissen wie sie funktioniert.

---
### $f(x) = ~ ?$

notes:
Die Funktion nimmt als Eingabe entweder 0 oder 1 und gibt entweder 0 oder 1 zurück. Wir wollen nun wissen, ob die Funktion balanciert ist, also ob für genau die Hälfte der Eingaben die entsprechende Ausgabe 0 ist und für die andere Hälfte 1.

---
### Angenommen $f(0) = 0$
- #### $f(1) = 1$ $\rightarrow$ Balanciert
- #### $f(1) = 0$ $\rightarrow$ Nicht balanciert

notes:
Um dieses Problem klassisch zu lösen, können wir zuerst die Eingabe 0 überprüfen. Sagen wir als Beispiel, dass die Ausgabe ebenfalls 0 ist. Dann überprüfen wir die Eingabe 1. Wenn die Ausgabe hier 1 ist, ist die Funktion balanciert, ansonsten, wenn die Ausgabe 0 ist, ist sie nicht balanciert. Mit einem klassischen Computer müssen wir die Funktion also mindestens zwei mal aufrufen. Auf einem Quantencomputer mit dem von Deutsch beschriebenen Algorithmus reicht es allerdings, die Funktion nur einmal statt zwei mal aufzurufen!
Diesen Algorithmus generalisiert Deutsch später in Zusammenarbeit mit Richard Jozsa, um ihn auf Funktionen mit mehr als nur zwei möglichen Eingaben anzuwenden. Damit wurde der erste Algorithmus beschrieben, den ein Quantencomputer in der Theorie schneller ausführen kann, als ein klassischer Computer.

---
## Klingt ziemlich nutzlos, oder?

### JA, ist es auch!
### ... aber das ändert sich!

notes:
Mit diesem Algorithmus kann man allerdings noch nichts wirklich anfangen. Alles was er zeigt, ist dass Quantencomputer ein einziges speziell konstruiertes Problem, das in der Praxis allerdings keinerlei Relevanz hat, schneller lösen können. Das ändert sich, als Ethan Bernstein und Umesh Vazirani 1993 die Quanten-Fouriertransformation entwickeln.

---
## QFT und Peter Shor

notes:
Die Quanten-Fouriertransformation, kurz QFT, kann die Fouriertransformation exponentiell schneller ausführen, als die klassische Fast-Fouriertransformation. Für alle, die sich mit Informatik nicht so gut auskennen und nicht wissen, was das heißt, schauen wir uns das kurz an.

---
### Linear vs. Exponentiell
![[linear_vs_exponential.png]]

notes:
Wir haben zwei Funktionen. Die krumme Kurve, die immer schneller nach oben geht, steigt exponentiell an. Die andere Funktion, die gerade, steigt linear an. Wenn man sich jetzt vorstellt, dass wir auf den Achsen immer weiter nach rechts gehen, wird schnell offensichtlich, dass der Unterschied zwischen den beiden Funktionen sehr schnell sehr viel größer wird.
DAS ist der Unterschied zwischen der Quanten-Fouriertransformation und der klassichen Fast-Fouriertransformation. Die Laufzeit der Fast-Fouriertransformation steigt wesentlich schneller an, als die Laufzeit der Quanten-Fouriertransformation. Für große Eingaben braucht die Fast-Fouriertransformation also sehr sehr viel länger.

---
## Peter Shor

### Wie zwei Algorithmen moderne Cybersecurity zerstören

notes:
Genau diese Quanten-Fouriertransformation macht sich Peter Shor für seinen berühmten Algorithmus zunutze oder, genau genommen, seine zwei Algorithmen. Einen für Primfaktorisierung, der der weitaus bekanntere von beiden ist, und einen für die Berechnung von diskreten Logarithmen. Was die beiden Probleme sind, erkläre ich hier nicht genauer. Wichtig ist, dass beide Probleme für klassische Computer sehr schwer zu lösen sind und exponentielle Laufzeit brauchen. Deshalb werden sie in der modernen Public Key Kryptographie auch verwendet. Peter Shor zeigt allerdings in seinem Paper, dass ein Quantencomputer beide Probleme mit Hilfe der zuvor entwickelten Quanten-Fouriertransformation, in polynomieller Zeit, also exponentiell schneller lösen kann.
Spätenstens jetzt wurde klar, dass Quantencomputing ein ernst zu nehmendes Forschungsgebiet ist und Forscher begannen, neue Methoden für Kryptographie zu entwickeln, die auch Quantencomputer nicht schnell lösen können.

---
## Lov Grover
### Schnelle Suche in einer Quantendatenbank

notes:
Nach Shor, hat auch Lov Grover einen der bekanntesten Quantenalgorithmen entwickelt. Sein Algorithmus kann eine Datenbank mit Hilfe von einem Quantencomputer durchsuchen. Zwar ist er nicht exponentiell schneller, wie Shors Algorithmus, sondern nur quadratisch schneller, aber für große Datenbanken kann auch das schon einen gewaltigen Unterschied machen.

---
# Echte Quantencomputer

notes:
Damit haben wir uns die wichtigsten Entwicklungen, was Quantenalgorithmen angeht, angeschaut. Es gibt natürlich noch einige andere Algorithmen, die heute wichtig sind, aber keiner von ihnen hatte so großen Einfluss, wie die in der früheren Geschichte des Forschungsgebiets.
Parallel zu den theoretischen Entwicklungen haben sich Forscher angeschaut, wie man einen Quantencomputer in der Realität überhaupt umsetzen könnte.

---
## DiVincenzo Kriterien

1. Akkurate Repräsentation des Systems
2. Zuverlässige Zustandsvorbereitung
3. Isolation von der Umgebung
4. Akkurate Anwendung von Operationen
5. "Starke" Messbarkeit möglich

notes:
David DiVincenzo beschreibt fünf Kriterien, die ein Quantencomputer erfüllen muss, um zu funktionieren:
1. Das System muss akkurat repräsentierbar sein. Das heißt, dass wir für einen Quantencomputer genau wissen müssen, wieviele Qubits er hat, und dass wir die Qubits unterscheiden können müssen.
2. Man muss die Zustände der Qubits zuverlässig vorbereiten können, also zum Beispiel alle Qubits in den Zustand $| 0 \rangle$ setzen können.
3. Das System muss von der Umgebung isoliert sein. Das ist nötig, damit die Qubits ihren Zustand halten können. Wäre das System nicht von der Umgebung gut isoliert, würde der Zustand der Qubits von der Umgebung stark gestört werden und der Quantencomputer wäre praktisch nutzlos.
4. Man muss Sequenzen von verschiedenen Operationen auf die Qubits akkurat anwenden können. Wenn wir die Qubits nicht manipulieren können, können wir logischerweise auch keine Berechnungen mit ihnen durchführen. Außerdem müssen wir in der Lage sein Qubits miteinander zu verschränken, also so, dass der Zustand des einen Qubit den Zustand des anderen beeinflusst.
5. Und zu guter letzt müssen die Qubits "stark" messbar sein. Das bedeutet, dass Qubits bei der Messung garantiert in einen der zwei Basiszustände 0 oder 1 fallen müssen und in diesem Zustand auch bleiben müssen.

---
## Quantencomputing Technologien

- Gefangene Ionen
- Topologisches Quantencomputing
- Spin-Qubits
- Supraleiter-Qubits
- ...

notes:
Ok aber wie bauen wir jetzt einen Quantencomputer? Dafür gibt es viele verschiedene Ansätze. Einige der am weitesten verbreiteten sind gefangene Ionen, Topologisches Quantencomputing, Spin-Qubits und Supraleiter-Qubits. Das alles zu erklären würde sowohl meine bisherigen Kenntnisse als auch den Rahmen dieses Videos sprengen. Eventuell kommt in der Zukunft noch ein Video zu dem ein oder anderen davon.
Mit Supraleiter-Qubits wurden auf jeden Fall bisher die besten Ergebnisse erzielt und auch die Quantencomputer von IBM, die aktuell die größten sind, was Anzahl an Qubits betrifft, basieren auf dieser Technologie.

---
# Aktueller Stand

notes:
Schauen wir uns kurz noch grob den aktuellen Stand von Quantencomputing an.

---
## Quantencomputing Technologie

- Große Firmen: Google, IBM, Amazon, Microsoft, Intel, ...
- Größter Quantencomputer: IBM Condor, 1121 Qubits

notes:
Quantencomputing wird unter anderem von einigen sehr großen Firmen erforscht. Dazu gehören zum Beispiel Google, IBM, Amazon, Microsoft und Intel, aber es gibt natürlich auch einige Firmen, die sich *nur* mit Quantencomputing beschäftigen wie zum Beispiel D-Wave oder Rigetti.
Dabei werden natürlich auch verschiedene von den eben erwähnten Technologien erforscht. Aktuell führend ist IBM mit ihrem Quantencomputer Condor, der 1121 Qubits hat. Es gibt zwar auch Quantenannealer von D-Wave mit aktuell über 5000 Qubits, aber die funktionieren nochmal etwas anders und sind deshalb nicht vergleichbar, indem man sich nur die Anzahl der Qubits anschaut.

---
## Software

- Verschiedene (Python) Libraries: Qiskit, Cirq, Forest, Ocean, ...
- Quanten-Programmiersprachen: QASM, Q#, ...

notes:
Aber was, wenn wir keine Physiker oder Materialwissenschaftler, sondern Informatiker sind? Wie können wir einen Quantencomputer programmieren? Dafür gibt es verschiedene Libraries, von denen die meisten für Programmierung in Python sind. Die beiden bekanntesten und umfangreichsten sind Qiskit von IBM und Cirq von Google, aber es gibt noch einige andere wie zum Beispiel Forest von Rigetti oder Ocean von D-Wave.
Abgesehen von Libraries gibt es auch ganze Programmiersprachen, die speziell für Quantencomputing entwickelt wurden. Zwei Beispiele sind die Quantum Assembly Language, kurz QASM. Das ist eine sehr simple Sprache, die auf der Ebene von einzelnen Quanten-Gates arbeitet. Eine Programmiersprache für Quantencomputer mit höherer Abstraktionsebene wäre zum Beispiel Q# von Microsoft.

---
## Algorithmen

- https://quantumalgorithmzoo.org/
- https://quantumcomputingpatterns.org/

notes:
Auf der theoretischen Seite gibt es inzwischen massenhaft verschiedene Algorithmen und sogar Muster, die verwendet werden können, um sich neue Quantenalgorithmen quasi zusammen zu puzzeln. Wer sich einfach mal massenhaft verschiedene Quantenalgorithmen von alten Algorithmen wie Shors Algorithmus bis hin zu recht neuen anschauen will, der kann mal den Quantenalgorithmus-Zoo oben anschauen. Wer sich einige simple und einige weniger simple Muster für Quantenalgorithmen anschauen will, der kann sich die untere Website zu Quantum Computing Patterns etwas genauer anschauen.

---
# Recap

notes:
Und das wars auch schon. Wir haben uns die wichtigsten Entwicklungen im Bereich Quantencomputing angeschaut und haben etwas über die Theorie und die Praxis mit Quantencomputing Technologien und Frameworks für Programmierer gelernt.
Im nächsten Video wird es um die Grundlagen von Gate-basierten Quantencomputern gehen. Da erklär ich alles, was nötig ist, um folgende Themen wie einzelne Quantenalgorithmen besser zu verstehen. Wenn ihr mehr über Quantencomputing und andere Themen wie Produktivität oder Informatik sehen wollt, lasst gerne ein Like und ein Abo da und dann sehen wir uns im nächsten Video!