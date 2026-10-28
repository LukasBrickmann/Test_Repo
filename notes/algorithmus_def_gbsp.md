# Algorithmus
## Definition
Ein Algorithmus ist eine Vorschrift zur Durchführung einer Berechnung (angegeben als Folge von einzelnen Schritten), die folgende Eigenschaften erfüllt:
* **Präzision**: Jeder Schritt ist eindeutig beschrieben.

* **Effektivität**: Jeder Schritt ist ausführbar.

* **Statische Finitheit**: Die Vorschrift ist ein endlicher Text.

* **Dynamische Finitheit**: Die Ausführung benötigt nur endlich viel Speicher.

* **Terminierung**: Die Berechnung endet für alle erlaubten Eingaben nach endlich vielen Schritten.

## Wünschenswerte Eigenschaften:
* **Determinismus**: Die Folgeschritte der Vorschrift sind immer eindeutig festgelegt.

* **Determiniertheit**: Gleiche Eingabe erzeugt gleiche Ausgabe.

* **Generalität**: Die Vorschrift kann eine Klasse von Problemen lösen.

## Gegenbeispiele:
### Präzision
```text
Male ein Haus.
```

**Bemerkung**: Determiniertheit ist (ggf.) auch verletzt.


### Effektivität
```text
x := 1 / 0
```

```text
Berechne das Maximum der natürlichen Zahlen.
```

### Statische Finitheit
```text
Gib 0 aus.
Gib 0 aus.
Gib 0 aus.
...
```

### Dynamische Finitheit

```text
x := 0
while x == 0:
    Speichere x in einer neuen Speicherzelle.
```
**Bemerkung**: Auch Terminierung ist verletzt. Bei realen Rechnern mit endlichem Speicherplatz ist irgendwann auch Effektivität verletzt.


### Terminierung

```text
while True:
    Warte eine Sekunde.
```


### Determinismus

```text
Wähle 0 oder 1.
```


### Determiniertheit

```text
Gib 0 oder 1 aus.
```

**Bemerkung**: Auch Determinismus ist verletzt.

### Generalität

```text
Berechne 7 + 35 und gib das Ergebnis aus.
```
