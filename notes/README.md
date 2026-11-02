# Tutorate Lukas Brickmann
## Termine
* Do 8:15–9:45 Uhr, Raum 051-03-026

* Do 10:15–11:45 Uhr, Raum 051-00-006


## Links
* [Forum](https://git.proglang.de/2026WS-EidP/forum/issues)
* [Homepage der Vorlesung](https://proglang.github.io/teaching/26ws/eidp.html)
* [Abgaberegeln](https://proglang.github.io/teaching/26ws/eidp/rules.html)


## Korrektur Blatt01  
* Ich konnte 35 Studi-Repos pullen; in 29 davon befand sich tatsächlich eine Abgabe.

* 8-mal wurden Flake8-Fehler gemeldet.

* 8-mal wurde sich nicht an die Formatierung der NOTES.md gehalten.

* Insgesamt kam es dadurch zu **12 Abgaben, die wegen des Builds mit Null Punkten bewertet wurden**.

## Aktuelles

* Die Korrektur von Blatt01 gibt Anlass zu folgender Bemerkung: Unter Linux kann man – sofern flake8 installiert ist – mit dem Befehl
  ```bash
  flake8 --ignore=E501,E704,E731,W5,C901 *.py
  ```
  alle Python-Dateien im aktuellen Arbeitsverzeichnis auf genau die von unserer VSC-Extension berücksichtigten Meldungen prüfen.

* Beim ersten Blatt wurden manche Builds fälschlicherweise als fehlgeschlagen markiert.

* Die Abgaberegeln wurden aktualisiert (siehe Top-Level-Statements).

* Die Zuteilung der Übungsgruppen aus HISinOne sollte jetzt synchron mit unserer Plattform sein.
