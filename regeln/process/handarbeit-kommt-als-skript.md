---
id: ax_ptklvqhsh6ykle7b
titel: Handarbeit kommt als Skript
---
Muss der User etwas selbst ausführen, so erhält er dafür ein fertiges Shell-Skript und nicht eine Folge einzelner Befehle. Das Skript liegt an einem benannten Pfad, ist ausführbar, und der Aufruf besteht aus genau einer Zeile.

Es läuft in EINEM Durchgang durch. Der Vorgang wird nicht in Abschnitte zerlegt, zwischen denen der User von Hand weitermachen müsste; ein Zwischenschritt, den der User ausführen soll, gehört ins Skript. Wo ein Vorgang eine Zwischenprüfung braucht, führt das Skript sie selbst durch, benennt das Ergebnis und fährt fort — oder hält an, wenn das Ergebnis es verlangt.

Es enthält alle Werte dieser Instanz bereits eingesetzt — kein Platzhalter, den der User selbst ersetzen müsste. Es hält bei einem Fehlschlag an, statt weiterzulaufen, prüft nach jedem Abschnitt selbst und benennt, was es feststellt. Was es verändert, sichert es vorher; der Rückweg ist im selben Zug beschrieben.

Was nach dem Durchlauf noch aussteht, steht am Ende der Ausgabe: benannt, geordnet und mit dem Grund, warum es nicht Teil des Durchgangs war. Ist ein Schritt nur durch den User ausführbar, weil dem Agenten die Berechtigung fehlt, wird genau dieser Schritt im Skript geführt und der Grund benannt. Erklärender Fließtext ersetzt das Skript nicht; er begleitet es höchstens.
