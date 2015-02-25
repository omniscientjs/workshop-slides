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

- toJS, fromJS

fordi data er immutable, kan data deles, fordi det aldri endres
sub-trær i den større strukturen kan dele informasjon

js idiomatisk api (i motsetning til feks mori)

### assignments

- list: create, push, indexOf, remove
- map: create, get, set, merge

vise større struktur

### assignments

- map
- filter
- reduce
- transform data
- string

- range
- repeat

## cursors

Assignments:
 - Create immutable maps, list, update structure.
 - Check equality of structures.
 - Iterate over maps and transform data using `map`, `filter`, etc.
 - Test out creating cursors through immstruct
 - Print changes to cursors using immstruct.
 - Advanced: Some advanced task

---

Setup:
 - shouldComponentUpdate

Main part:
 - omniscient
 - rationale
 - render loop

Assignments:
 - Create React components with simple `shouldComponentUpdates` as mixins.
 - Creating Omniscient components, pass in a tree props (only view)
 - Creating Omniscient components with cursors as input. (only view)
 - Creating updatable omniscient components (render loop)
 - Composing components
 - Using mixins (lifecycles)?
 - Advanced: Some advanced task


Extras:
 - Reference Cursors? 
 - Remote data?
