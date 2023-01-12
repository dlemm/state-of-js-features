# WIP state-of-js-features
This is a repo for the mentioned features from the [State of JS](https://2022.stateofjs.com/). It's a link collection for more detail information for these features. If you're like me and you have not yet heard of some of them or even all. I have you (and me) covered. 

### Table of content
1. [Nullish Coalescing](#nullish-coalescing)
2. [Top level await()](#top-level-await)
3. [String.prototype.replaceAll()](#stringprototypereplaceall)

## Nullish Coalescing

The nullish coalescing (`??`) operator is a logical operator that returns its right-hand side operand when its left-hand side operand is `null` or `undefined`, and otherwise returns its left-hand side operand. 

```js
const example = null ?? 'example string';
console.log(example);
// Expected output: "example string"

const exampleTwo = 0 ?? 42;
console.log(exampleTwo);
// Expected output: 0
```

Source: [developer.mozilla.org][1]


## Top level await()

In contrast to the `await` operator, that is used to wait for a Promise (and gets its fulfillment value) and can only be used inside an async function the top level `await` can be used at the top level of a module. The module with childs then waits for the child modules to execute before they themselves run, all while not blocking other child modules from loading.

```js
// fetch request
const names = fetch("../data/names.json").then((response) => response.json());

export default await names;
```
Source: [developer.mozilla.org][2] 

## String.prototype.replaceAll()

The method `replaceAll()` returns a new string where all matched patterns are replaced by the replacement. The pattern that should be replaced can be a string or a RegExp. The replacement itself can be a string or a function to be called for each match. 

🧐: The original string is left unchanged.

```js
replaceAll(pattern, replacement)

const p = 'The quick brown fox jumps over the lazy dog. If the dog reacted, was it really lazy?';

console.log(p.replaceAll('dog', 'monkey'));
// Expected output: "The quick brown fox jumps over the lazy monkey. If the monkey reacted, was it really lazy?"


// Global flag required when calling replaceAll with regex
const regex = /Dog/ig;
console.log(p.replaceAll(regex, 'cat'));
// Expected output: "The quick brown fox jumps over the lazy cat. If the cat reacted, was it really lazy?"

```

Source: [developer.mozilla.org][3]

[1]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Nullish_coalescing 
[2]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await
[3]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replaceAll
