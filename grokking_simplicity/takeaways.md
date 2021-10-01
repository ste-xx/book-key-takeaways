![cover](cover.jpg)

### Grokking Simplicity: Taming Complex Software With Functional Thinking

#### Actions, Calculations, Data

Actions:
Relevant WANN und WIEOFT die function aufgerufen wird.

Calcuations: 
Kann beliebig oft aufgerufen werden, es ändert nichts am Zustand.
Pure function. Lassen sich super testen.

Data: 
Fakten über Events.

Kernidee in "Simplicity" ist es, die Actions "nach außen" zu ziehen und die "Calculations" aus den Actions zu extrahieren.

Ebenso wird auf implizite/explizites Input/Output eingegangen (implizit === globale Variable). 
In dem Buch wird empfohlen den globalen state zu reduzieren.


#### Immutable in einer Mutable Sprache
Viele tipps und kniffe wie man es schaft in einer Sprache wie Javascript/Java immutablity einzuführen.
Vorallem über den copy-by-write weg.

zum Beispiel:
```javascript
const setOnPosition = (arr, idx, cb) => {
  const copy = [...arr];
  copy[idx] = cb(copy[idx]);
  return copy;
};
```
oder

```javascript
const setObject = (object, key, value) => ({
  ...object,
  [key]: value,
});
```
```javascript
function nestedUpdate(object, keys, modify) {
    if(keys.length === 0)
        return modify(object);
    var key1 = keys[0];
    var restOfKeys = drop_first(keys);
    return update(object, key1, function(value1) {
        return nestedUpdate(value1, restOfKeys, modify);
    });
}
```

#### Stratified Design
So wird dann "Stratified Design", was nichts anderes heißt, als mit solchen funktionen, Layer einzuführen die aufeinander aufbauen.
Dabei sollte man achten, das die Layer beim referenzieren keine Ebenen überspringen oder auf die gleiche Ebene referenzieren.
