# The Importance of Clean Code

## Summary/Motivation
* Writing code can be very confusing for learners
* Keeping code clean is a great way to avoid unnecessary confusion and weird bugs

## Script/Outline
* New lines between thoughts (just like paragraphs in text)
* Write out non-ideal code
```js
const username = 'Alice';
if (username === 'Bob') {console.log('hello Bob!');
}else{console.log(`Hi ${username}`)}
```
* Make use of the 'enter' key
```js
const username = 'Alice';

if (username === 'Bob') {
  console.log('hello Bob!');
} else {
  console.log(`Hi ${username}`)
}
```

* Complete your syntax before writing the internals
```js
const myFunc = function() {};
```
* Because I hate playing the what-do-I-need game (`)` or `})` ??)

* Proper indentation 
```js
const myFunc = function(username) {
if (username === 'Bob') {
console.log('hello Bob!');
} else {
console.log(`Hi ${username}`);
}
};
```
* Tab and cmd/ctrl + [ or ] to tab highlighted sections at a time 
```js
const myFunc = function(username) {
  if (username === 'Bob') {
    console.log('hello Bob!');
  } else {
    console.log(`Hi ${username}`);
  }
};
```

* Code folding (VS Code settings)
* Open VS Code settings and enable code folding then demonstrate  


* Review
* Writing code can be confusing
* But don't let it be the way your code is laid out that's confusing
* Clean code is easier to read, easier to reason about, and easier to update/maintain
* Coding is a team sport and we need to make sure that the other team members can understand what we're doing

## Learning Outcomes
* Understanding of clean code and some techniques to help avoid confusion

## Prerequisites
* VS Code knowledge
* Conditionals
* Functions
* Variable definition

## Position in Curriculum
* W1D1
* Prep Course
