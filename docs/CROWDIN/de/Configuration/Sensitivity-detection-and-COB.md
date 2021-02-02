# Empfindlichkeitserkennung

## Sensitivitäts-Algorithmus
Aktuell gibt es 3 Modelle zur Empfindlichkeitserkennung:

* Sensitivität AAPS
* Durchschnittliche Sensitivität
* Sensitivität Oref1

### Sensitivität AAPS
Die Empfindlichkeit wird wie bei Oref1 berechnet, aber du kannst einstellen wie weit der Algorithmus in die Vergangenheit "schaut". Die minimale Kohlenhydrat-Absorption wird ausgehend von der maximalen Kohlenhydrat-Absorption, die in den Vorgaben festgelegt werden kann, berechnet.

### Durchschnittliche Sensitivität
Die Empfindlichkeit wird als gewichtetes Mittel der Schwankungen berechnet. Du kannst angeben, wie lange rückwirkend betrachtet wird. Neuere Schwankungen haben ein größeres Gewicht. Die minimale Kohlenhydrat-Absorption wird ausgehend von der maximalen Kohlenhydrat-Absorption, die in den Vorgaben festgelegt werden kann, berechnet. Dieser Algorithmus folgt Änderungen der Empfindlichkeit am schnellsten.

### Sensitivität Oref1
Sensitivity is calculated from 8h data in the past or from last site change, if it is less than 8h ago. Carbs (if not absorbed) are cut after time specified in preferences. Nur der Oref1 Algorithmus unterstützt un-announced Meals (UAM). Das heißt, Zeiten mit erkannten UAM werden bei der Sensitivitätsberechnung nicht berücksichtigt. Wenn du also SMB mit UAM verwendest, dann musst du den Oref1 Algorithmus auswählen, damit es gut läuft. Für weitere Informationen lies die [OpenAPS Oref1 Dokumentation](https://openaps.readthedocs.io/en/latest/docs/Customize-Iterate/oref1.html).

## Mehrere Mahlzeiten gleichzeitig
Es macht einen großen Unterschied, ob du AAPS/Durchschnittliche Sensititvität oder Oref1 verwendest. Die Oref Plugins gehen davon aus, dass nur die Kohlenhydrate einer einzigen Mahlzeit abgebaut werden. Das bedeutet, dass der Abbau einer zweiten Mahlzeit erst dann beginnt, wenn die erste Mahlzeit vollständig abgebaut ist. AAPS mit durchschnittlicher Sensitivität beginnt direkt nach Eingabe der Kohlenhydrate mit deren Abbau. Falls mehr als eine Mahlzeit zu berücksichtigen ist, wird der minimale KH-Abbau entsprechend der Größe der Mahlzeit und der maximalen Absorption angepasst. Die minimale Absorption wird entsprechend höher im Vergleich zu den Oref Plugins.
