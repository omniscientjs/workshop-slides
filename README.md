# omniscient-workshop
Omniscient Workshop for Booster2015 - [Slides](https://omniscientjs.github.io/workshop-slides)

## Description sent to booster

Let us bring back the days where we could write declarative representations of how we want our UI components to work. We should be able to read our code from top to bottom and intuitively know what the output will be, just like the good old HTML. We should be able to write composable, testable and reproducible components and be free to choose what kind of dependency management we want to use, or how to structure our code.

What if we take inspiration from the functional world and create a UI where we have pure and referentially transparent components; components with no side-effects and predictable output? If we coupled this with immutable data and components with single responsibilities, can we get a blazing fast and smart way to build UIs? It turns out we can!

In this workshop we start by looking at how we can use a virtual DOM and functional cursors of immutable data to isolate components, and making them pure. Once we've grasped the general concepts, we introduce an architecture for doing unidirectional top-down rendering, with very little architectural overhead. After this workshop, you should be able to understand and use unidirectional UI components to build testable and easy-to-reason-about web applications. Technologies used will be Facebook's React and Immutable.js, and Omniscient.js. This workshop is intended for developers who have some experience with frontend development.

Outline
The outline is described somewhat in the abstract as well, but we will start by introducing the concept of Virtual DOM and see examples of more "traditional" components and elements with the Virtual DOM. After we've grasped the general concept, we'll go through some influences we can take from the functional programming paradigm and see how we can make UI reasoning easier and having components much like we used to write HTML, but with additional functionality. The end goal is to have made a not-too-contrived example application or part of application by the end of the workshop.

We plan on having the workshop split into three parts, with exercises between each part. Roughly like the following:

Part 1: 

- Virtual DOM and Components
- Exercises
- Break

Part 2:

- Immutable data structures and inspiration from Functional Programming
- Exercises
- Break

Part 3 (Longer part):

- Unidirectional UI with Immutable data
- Exercises/Case 
