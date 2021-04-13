![cover](cover.jpg)

### Building Evolutionary Architectures: Support Constant Change

#### Fitness function
Im prinzip kontinuierliches automatisiertes testen von Eigenschaften die uns in dem System wichtig sind.
Zum Beispiel 
 - Payloadgrößen in Mobilapps
 - Performance ui (First meaningful paint)
 - Wenn es so etwas wie ein Publish funktion gibt: Wie lange bis veröffentlicht
 
 Dabei gibt es unterschiede zwischen
 atomic -> wie oben genannte Funktionen
 holistic -> die das System im ganzen betrachtet. Beispiel: Chaosmonkey von Netflix der das ganze system testet, ob es ausfallsicher ist.
 
Es ist ebenfalls möglich, Architekturentscheidungen (wie sollen die Koppelungen aussehen) mit fitness functions zu testen.
