# Outline

## react intro

## passing props

## easy mental model

###  Assignment

- Creating components (classes)
- Assignment: Passing props to component

## composable components

### Assignments
 - Composing components (children)

## virtual DOM

### Assignments

 - Render twice to update view using setTimeout.
 - Render a clock using setInterval
 - Advanced: Some advanced task

---

Setup: 
 - react component state change causes re-render
 - state gets out of hand

## functional paradigms

referential transparency
same input, same output

side effect free 

but we need side effects - dom, ajax, logging

## higher order functions

grunnleggende byggestener i funksjonell programmering

## metal model

### assignments

- map
- filter
- reduce
- transform data
- string

nye lister, pass på objekter i lister som kanskje kan peke til andre strukturer

## immutability 

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

## React sin shouldComponentUpdate

### assignments 

- egenskrevet mixin
- bare rendre på nytt hvis tall er oddetall?

kan man ikke bare sende immutable datastrukturer og gjøre en enkel reference equal sjekk? istedet for en deep equal for å sjekke om noe har endret seg? JO!

### assignments

fint for små komponenter
hva når datastrukturer blir store
må alle komponenetene vite om hele strukturen
kan sende referansene til hvor du finner data - cursors

immutable data har vært vanskelig i js, om gjør det
har kommet flere i det siste, flux gjør det, men mye mer overhead i arkitektur

vi syns det mangler for javascript

## omniscient

syntaktisk sukker
rettningslinjer til hvordan du kan lage funksjonelle grensesnitt
hjelper deg å følge disse

kan oppnå akkurat det samme med ren react og immutable js
ender med å implementere noe som ligner på immstruct og omniscient
mindre battle tested løsning

kan bruke state - i blant trenger man det - selvfølgelig er det mulig

### assignments 
- react with omniscients should component update

endrer fokusområdet til content first
alt en komponent trenger å være er innhold
composability
render funksjon som er lett å ressonnere over
tar inn argument og jobber bare med det
referencial transparency
higher order components

### assignments
- pass props
- pass cursors
- effective re-render
- render loop

av og til trenger man ekstra funksjonalitet
lagt opp til at den er enkel på å dele via mixins (traits) 
legge funksjonene utenfor komponentene

### assignments 

- legge til én mixin
- legge til flere mixins
- legge til react life cycle mixins (alle er garantert til å bli utført, hvis det finnes flere)

Assignments:
 - Creating updatable omniscient components (render loop)

Extras:
 - Remote data?
