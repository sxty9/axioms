# Holistic — Axiome

Dieses Repository hält die **Daten** der Holistic-Verfassung: die Axiome, die
Implementierungsregeln und die Laufregeln. Es enthält keinen Code.

## Aufbau

| Verzeichnis | Inhalt |
|---|---|
| `axiome/` | Die Axiome, nach Kategorien geschachtelt |
| `regeln/` | Implementierungsregeln — wie implementiert wird |
| `laeufe/` | Laufregeln — wie ein automatischer Lauf sich verhält |

Ein Eintrag ist eine Markdown-Datei mit Front-Matter (`id`, `titel`, optional `quelle`)
und dem Text darunter. Die `id` ist stabil und überlebt jedes Verschieben; der Pfad ist
die Kategorie.

## Warum ein eigenes Repository

Die Code-Repositories sind auf ihrem Standard-Branch geschützt: dort ändert sich nichts
ohne Pull Request. Die Verfassung selbst ist aber Datenpflege und soll unmittelbar
wirksam werden, ohne PR-Zeremonie für jeden Satz. Deshalb liegt sie hier, in einem
Repository **ohne** Branch-Schutz, und wird von den Diensten konsumiert statt in ihnen
dupliziert.

## Änderungen

Bearbeitet wird die Verfassung über die Mercury-Oberfläche, nicht durch Direktbearbeitung
der Dateien: dort werden Einträge angelegt, geprüft, umsortiert und Läufen zugeordnet.
Dieses Repository ist die versionierte Ablage dieses Bestands.
