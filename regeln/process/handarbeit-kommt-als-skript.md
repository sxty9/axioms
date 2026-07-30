---
id: ax_ptklvqhsh6ykle7b
titel: Handarbeit kommt als Skript
---
Muss der User etwas selbst ausführen, so erhält er dafür ein fertiges Shell-Skript und nicht eine Folge einzelner Befehle. Das Skript liegt an einem benannten Pfad, ist ausführbar, und der Aufruf besteht aus genau einer Zeile.

Es enthält alle Werte dieser Instanz bereits eingesetzt — kein Platzhalter, den der User selbst ersetzen müsste. Es hält bei einem Fehlschlag an, statt weiterzulaufen, prüft nach jedem Abschnitt selbst und benennt, was es feststellt. Was es verändert, sichert es vorher; der Rückweg ist im selben Zug beschrieben.

Ist ein Schritt nur durch den User ausführbar, weil dem Agenten die Berechtigung fehlt, wird genau dieser Schritt im Skript geführt und der Grund benannt. Erklärender Fließtext ersetzt das Skript nicht; er begleitet es höchstens.
