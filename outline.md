# react intro

# passing props

## easy mental model

##  Assignment

- Creating components (classes)
- Assignment: Passing props to component

# composable components

## Assignments
 - Composing components (children)

# virtual DOM

## Assignments

 - Render twice to update view using setTimeout.
 - Render a clock using setInterval
 - Advanced: Some advanced task

---

Setup:
 - react component state change causes re-render
 - state gets out of hand

# functional paradigm

## referential transparency

Property of parts of computer programs. An expresssion is referentially transparent if it can be replaced with its value without changing the behavior of the program.

In other words, given the same input, the program has the same effects and outputs - Side effect free.

`42 + 42 => 84`

`var global = 42; global + 42 => ???`

For programs to be interesting we actually need state and side effects!

Common examples include the dom, ajax communcation, logging etc.

## mental model

Why do we strive for principles of functional programming?
Easier mental model, easier to write, modular programs,
decompose problems into parts

## higher order functions

The glue. Primary building block of functional programming.

Functions as values. Functions can take functions as arguments.
Functions can return functions.

```
var adder = function (add) {
  return /*solution function (x) {
    return add + x;
  };*/
};
var add2 = adder(2);
add2(4); // 6
```
[run](http://omniscientjs.github.io/playground/#var%20adder%20%3D%20function%20(add)%20%7B%0A%20%20return%20function%20(x)%20%7B%0A%20%20%20%20return%20add%20%2B%20x%3B%0A%20%20%7D%3B%0A%7D%3B%0Avar%20add2%20%3D%20adder(2)%3B%0Ait('adds%202'%2C%20()%20%3D%3E%20add2(4).should.equal(6))%3B)

## assignments

- map
```
var list = [1, 2, 3];
var square = function (n) {
  /*solution return n * n;*/
};
it('squares numbers', function () {
  list.map(square).should.eql([1, 4, 9])
});
```
[run](http://omniscientjs.github.io/playground/#var%20list%20%3D%20%5B1%2C%202%2C%203%5D%3B%0Avar%20square%20%3D%20function%20(n)%20%7B%0A%20%20return%20n%20*%20n%3B%0A%7D%3B%0Ait('squares%20numbers'%2C%20function%20()%20%7B%0A%20%20list.map(square).should.eql(%5B1%2C%204%2C%209%5D)%0A%7D)%3B)

- filter
```
var numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
var isFizzOrBuzz = function (n) {
  /*solution return n % 5 == 0 || n % 3 == 0;*/
};
it('keeps fizzbuzz numbers', function () {
  numbers.filter(isFizzOrBuzz).should.eql([3, 5, 6, 9, 10])
});
```
[run](http://omniscientjs.github.io/playground/#var%20numbers%20%3D%20%5B1%2C%202%2C%203%2C%204%2C%205%2C%206%2C%207%2C%208%2C%209%2C%2010%5D%3B%0Avar%20isFizzOrBuzz%20%3D%20function%20(n)%20%7B%0A%20%20return%20n%20%25%205%20%3D%3D%200%20%7C%7C%20n%20%25%203%20%3D%3D%200%3B%0A%7D%3B%0Ait('keeps%20fizzbuzz%20numbers'%2C%20function%20()%20%7B%0A%20%20numbers.filter(isFizzOrBuzz).should.eql(%5B3%2C%205%2C%206%2C%209%2C%2010%5D)%0A%7D)%3B)

- reduce
```
var numbers = [1, 2, 3, 4, 5];
var multiply = function (acc, n) {
  return acc * n;
}
it('multiplies numbers', function () {
  numbers.reduce(multiply, 1).should.equal(120);
});
```
[run](http://omniscientjs.github.io/playground/#var%20numbers%20%3D%20%5B1%2C%202%2C%203%2C%204%2C%205%5D%3B%0Avar%20multiply%20%3D%20function%20(acc%2C%20n)%20%7B%0A%20%20return%20acc%20*%20n%3B%0A%7D%0Ait('multiplies%20numbers'%2C%20function%20()%20%7B%0A%20%20numbers.reduce(multiply%2C%201).should.equal(120)%3B%0A%7D)%3B)

- transform data
```
var episodes = [
  { name: "Cartman Gets an Anal Probe" },
  { name: "Weight Gain 4000" },
  { name: "Volcano" },
  { name: "Big Gay Al's Big Gay Boat Ride" },
  { name: "An Elephant Makes Love to a Pig" },
  { name: "Death" },
  { name: "Pinkeye" },
  { name: "Starvin' Marvin" },
  { name: "Mr. Hankey, the Christmas Poo" },
  { name: "Damien" },
  { name: "Tom's Rhinoplasty" },
  { name: "Mecha-Streisand" },
  { name: "Cartman's Mom Is a Dirty Slut" }];

function asName (obj) {
  return obj.name;
}

it('maps episodes => name', function () {
  episodes.map(asName)[0].should.equal("Cartman Gets an Anal Probe");
  episodes.map(asName)[1].should.equal("Weight Gain 4000");
});
```
[run](http://omniscientjs.github.io/playground/#var%20episodes%20%3D%20%5B%0A%20%20%7B%20name%3A%20%22Cartman%20Gets%20an%20Anal%20Probe%22%20%7D%2C%0A%20%20%7B%20name%3A%20%22Weight%20Gain%204000%22%20%7D%2C%0A%20%20%7B%20name%3A%20%22Volcano%22%20%7D%2C%0A%20%20%7B%20name%3A%20%22Big%20Gay%20Al's%20Big%20Gay%20Boat%20Ride%22%20%7D%2C%0A%20%20%7B%20name%3A%20%22An%20Elephant%20Makes%20Love%20to%20a%20Pig%22%20%7D%2C%0A%20%20%7B%20name%3A%20%22Death%22%20%7D%2C%0A%20%20%7B%20name%3A%20%22Pinkeye%22%20%7D%2C%0A%20%20%7B%20name%3A%20%22Starvin'%20Marvin%22%20%7D%2C%0A%20%20%7B%20name%3A%20%22Mr.%20Hankey%2C%20the%20Christmas%20Poo%22%20%7D%2C%0A%20%20%7B%20name%3A%20%22Damien%22%20%7D%2C%0A%20%20%7B%20name%3A%20%22Tom's%20Rhinoplasty%22%20%7D%2C%0A%20%20%7B%20name%3A%20%22Mecha-Streisand%22%20%7D%2C%0A%20%20%7B%20name%3A%20%22Cartman's%20Mom%20Is%20a%20Dirty%20Slut%22%20%7D%5D%3B%0A%0Afunction%20asName%20(obj)%20%7B%0A%20%20return%20obj.name%3B%0A%7D%0A%0Ait('maps%20episodes%20%3D%3E%20name'%2C%20function%20()%20%7B%0A%20%20episodes.map(asName)%5B0%5D.should.equal(%22Cartman%20Gets%20an%20Anal%20Probe%22)%3B%0A%20%20episodes.map(asName)%5B1%5D.should.equal(%22Weight%20Gain%204000%22)%3B%0A%7D)%3B)

- string
```
var name = 'bob';

it('returns new strings', function () {
  /*solution var names = name + ' & alice';*/

  names.should.equal('bob & alice');
  name.should.equal('bob');
});
```

Note that while operations like map, filter, reduce etc. return new lists,
the content of these lists may well be the same object references you
started out with.

# immutability

vi får
alt er ikke mutable, lett å miste oversikt, noen endrer noe som
fryse objekt - immutable
hva når vi vil bruke det igjen? kopiere den?
hvordan kan vi få til det?
kan vi kopiere alt hele tiden?
to helt like,tar det ikke dobbelt så mye plass?

dele strukturer

## (immutable.js)

smart nerdete type på facebook som har jobbet med dette lee byron

clojure - vis frem en datastrukt, kodesnutt
mori
clojurescript

fordi data er immutable, kan data deles, fordi det aldri endres
sub-trær i den større strukturen kan dele informasjon

js idiomatisk api (i motsetning til feks mori)

### assignments
- Check equality of structures.

- list: create, push, indexOf, remove
- map: create, get, set, merge

vise større struktur

- toJS, fromJS
- updateIn, men hele strukturen blir oppdatert

### assignments

- map
- filter
- reduce
- transform data
- string

- range
- repeat

## cursors

peke inn i en struktur, sende referanse videre, og bruker kan oppdatere data på denne plassen,
men du får ut en ny cursor som igjen peker til den delen av strukturen

### assignments

## Immstruct

gamle referanser til en en helt annen plass i treet
oppdatere den
men ikke påvirke dem andre delene av treet

lytte på endring, reagere på endring - swap
skikkelig enkelt å rendre på nytt hele tiden!

### assignments

- render on swap

men er det noe lurt da?

---

# React sin shouldComponentUpdate

## assignments

- egenskrevet mixin
- bare rendre på nytt hvis tall er oddetall?

kan man ikke bare sende immutable datastrukturer og gjøre en enkel reference equal sjekk? istedet for en deep equal for å sjekke om noe har endret seg? JO!

## assignments

fint for små komponenter
hva når datastrukturer blir store
må alle komponenetene vite om hele strukturen
kan sende referansene til hvor du finner data - cursors

immutable data har vært vanskelig i js, om gjør det
har kommet flere i det siste, flux gjør det, men mye mer overhead i arkitektur

vi syns det mangler for javascript

# omniscient

syntaktisk sukker
rettningslinjer til hvordan du kan lage funksjonelle grensesnitt
hjelper deg å følge disse

kan oppnå akkurat det samme med ren react og immutable js
ender med å implementere noe som ligner på immstruct og omniscient
mindre battle tested løsning

kan bruke state - i blant trenger man det - selvfølgelig er det mulig

## assignments
- react with omniscients should component update

endrer fokusområdet til content first
alt en komponent trenger å være er innhold
composability
render funksjon som er lett å ressonnere over
tar inn argument og jobber bare med det
referencial transparency
higher order components

## assignments
- pass props
- pass cursors
- effective re-render
- render loop

av og til trenger man ekstra funksjonalitet
lagt opp til at den er enkel på å dele via mixins (traits)
legge funksjonene utenfor komponentene

## assignments

- legge til én mixin
- legge til flere mixins
- legge til react life cycle mixins (alle er garantert til å bli utført, hvis det finnes flere)

Assignments:
 - Creating updatable omniscient components (render loop)

Extras:
 - Remote data?
