---
id: ax_k4s2i37rmnnox7j7
titel: Die Auslieferungskette und ihre Stufen
---
Jede KI-gestuetzte Implementierung laeuft durch dieselbe Kette. Wer implementiert, muss sie kennen — sonst entwirft er Loesungen, die an ihr vorbeigehen.

DIE STUFEN, IN DIESER REIHENFOLGE

  preflight      Zustand des Auftrags feststellen: schon implementiert? Zweig vorhanden? Steht die
                 Stapelspitze? Hier wird gehalten, wenn die Spitze eines anderen Auftrags gescheitert
                 ist oder eine unbeantwortete Rueckfrage offensteht.
  implement      Die Arbeit. Sie entsteht auf einem eigenen Zweig je Auftrag, der von der aktuellen
                 Stapelspitze abzweigt, und wird dorthin veroeffentlicht.
  deliver-dev    Bauen, auf der Dev-Maschine installieren, und BEWEISEN dass es laeuft (Einheit aktiv
                 UND Port belegt). Dies ist die Stelle, an der Konsistenz nachgewiesen wird.
  publish        Den ausgelieferten Stand als Lieferung eintragen.
  pull-request   Den Pull Request oeffnen, mit Frist zur automatischen Zusammenfuehrung.
  merge          Zusammenfuehren in den Standard-Zweig.
  production     Auf den Produktions-Rechner ausliefern und dort beweisen.
  historisieren  Erst nach der Produktions-Auslieferung gilt der Auftrag als abgeschlossen.

WAS DARAUS FOLGT

Ab dem Pull Request gilt Stapelvaliditaet: Konsistenz ist durch deliver-dev bereits bewiesen. Eine
gescheiterte Produktions-Auslieferung aendert deshalb nichts am Stapel — sie ist eine Sache fuer sich.

Eine Stufe, die scheitert, haelt die folgenden an. Der Auftrag wird damit zur Stapelspitze und der
Stapel waechst nicht weiter, bis er geloest oder zurueckgebaut ist.

HINDERNISSE WERDEN GENEHMIGT, NICHT UMGANGEN

Braucht die Kette eine Entscheidung oder ein Recht, das ihr fehlt, geht der Auftrag in Blocked und
stellt dort die konkrete Frage — mitsamt der Befehlsfolge, die die Genehmigung ausfuehren wuerde.
Der Mensch genehmigt im Blocked-Tab, die Befehlsfolge laeuft, und der Auftrag macht an derselben
Stelle weiter. Es wird KEIN Nebenweg um die Kette herum gebaut. Ein Entwurf, der eine Stufe
ueberspringt, umordnet oder verdoppelt, um an einem Hindernis vorbeizukommen, ist falsch: das
Hindernis gehoert genehmigungsfaehig gemacht, nicht umgangen.

Root-Rechte sind der Musterfall. Die Kette schreibt niemals selbst ein Skript, das als root laeuft —
das waere Selbst-Erhoehung. Sie legt den genauen Inhalt vor, an seine Pruefsumme gebunden, und der
Mensch genehmigt ihn.

DIE KETTE FUEHRT ZUSAMMEN, NICHT DIE HAND

Das Zusammenfuehren ist eine Stufe der Kette und gehoert ihr allein. Lieferungen stapeln sich: Der
Pull Request einer Lieferung steht auf dem Zweig ihres Vorgaengers, nicht auf dem Standard-Zweig.
Deshalb wird EINER je Durchgang zusammengefuehrt und sein Zweig danach geloescht — erst das Loeschen
setzt den nachfolgenden Pull Request auf den Standard-Zweig um. Mehrere auf einmal von Hand
zusammenzufuehren laesst jeden ausser dem ersten in den veralteten Zweig seines Vorgaengers fallen:
Der Pull Request meldet sich als zusammengefuehrt, sein Inhalt erreicht den Standard-Zweig nie.

Daraus folgt dreierlei. Ein Pull Request, der in einen anderen als den Standard-Zweig zusammengefuehrt
wurde, gilt NICHT als geliefert; das Lieferungsbuch darf das nicht behaupten. Vor jedem Eingriff an
einem Pull Request ist seine Basis zu lesen, nicht anzunehmen. Und die Kette weist Inhalt zurueck, der
nicht aus einer eingetragenen Lieferung stammt — dieses Urteil wird nie von Hand ueberschrieben,
sondern durch einen Auftrag beantwortet, der den Inhalt ordentlich ausliefert.

GEMESSEN WIRD VOR DEM AUTOMATISIEREN

Eine Schleife ueber mehrere Gegenstaende setzt voraus, dass sie voneinander unabhaengig sind. Diese
Annahme ist zu pruefen, bevor die Schleife geschrieben wird, nicht danach. Wer eine Eigenschaft
abfragt, fragt die ab, von der die Handlung abhaengt — Vollstaendigkeit der Messung entscheidet, nicht
ihre Menge.
