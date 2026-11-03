# Bemerkungen zur Korrektur
## Übungsblatt 1  
* Ich konnte 35 Studi-Repos pullen; in 29 davon befand sich tatsächlich eine Abgabe.

* 8-mal wurden Flake8-Fehler gemeldet.

* 8-mal wurde sich nicht an die Formatierung der NOTES.md gehalten.

* Insgesamt kam es dadurch zu **13 Abgaben, die wegen des Builds mit 0 Punkten bewertet wurden**.

* Das gibt Anlass zu folgender Bemerkung: Unter Linux kann man – sofern flake8 installiert ist – mit dem Befehl
  ```bash
  flake8 --ignore=E501,E704,E731,W5,C901 *.py
  ```
  alle Python-Dateien im aktuellen Arbeitsverzeichnis auf genau die von unserer VSC-Extension berücksichtigten Meldungen prüfen.
