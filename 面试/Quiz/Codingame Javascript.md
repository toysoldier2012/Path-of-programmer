
# QCM

### [JS] Prototypes
Design (60 pts)

Consider an object obj defined as follows:

```javascript
MyClass = function() {
    this.a = 'hello';
    this.b = 'world';
};
    
MyClass.prototype.a = 'john';
MyClass.prototype.c = 12;

obj = new MyClass();
```

Among the following options, which ones are true?  
  
_Multiple answers expected._

- `obj.a` returns `'hello'`
- `obj.a` returns `'john'`
- `obj.b` returns `undefined`
- `obj.b` returns `'world'`
- `obj.c` returns `undefined`
- `obj.c` returns `12`
- `obj.d` returns `null`

### const array
Language knowledge (20 pts)

Consider the following code:

```javascript
const carBrands = ['Honda', 'Hyundai', 'Kia', 'BMW', 'Mercedes'];
```

_Select all valid operations on the variable `carBrands`._

```javascript
    carBrands[2] = 'Renault';
    ```
```javascript
    carBrands = [];
    ```  
```javascript
    carBrands.push('BMW');
    ```

### [JS] References 2
Language knowledge (60 pts)

The following snippet:

```javascript
var a = {};
var b = a;

a.v = 1;
b.v = 2;

console.log(a.v);
```

Will write to the console...

- 1
- 2
- undefined
- Nothing, an error will occur

### Objects - Check Property Existence
Language knowledge (20 pts)

An object in Javascript is a list of properties, where a property is a key-value pair.

  
What is a correct way of checking if a property `prop` exists in an object `obj`?

```javascript
if (obj.prop !== 'undefined')
```
```javascript
if (obj.prop)
```
```javascript
if (obj[prop])
```
```javascript
if ('prop' in obj)
```

### [JS] String comparison
Language knowledge (60 pts)

In JavaScript, what is the output of this snippet?

```javascript
var x = "2", y = "10";
alert(x < y);
```

- true
- false
- "2<10"
- null
- A JavaScript error

### Block Scope
Language knowledge (20 pts)

Which of the following keywords provide a **block scope**?

_Select all correct answers._

- const
- let
- var

### String Methods
Language knowledge (40 pts)

Which of the following options is **not** a valid `String` method?

- indexOf
- includes
- slice
- splice
- charAt

### Function methods and properties
Language knowledge (20 pts)

Which of the following options is **not** an instance property or method of `Function`?

- .call()
- .apply()
- .toString()
- .entries()

### [JS] Events
Language knowledge (40 pts)

In JavaScript, what event is triggered when a `<button>` or `<textarea>` element loses focus?

- onblur
- onclick
- ondblclick
- onfocus
- onfocuslost

### Set object
Language knowledge (20 pts)

Which object is best suited to store unique (distinct) values in Javascript?

- Map
- Object
- Array
- Set

### [JS] Threads
Design (40 pts)

JavaScript is multi-threaded.

- True
- False

### [JS] Type conversion #1
Language knowledge (40 pts)

In JavaScript, what is the result of the following expression:  
  

```javascript
true == 1;​
```

- true
- false
- null
- undefined

### Object.entries
Language knowledge (20 pts)

Which one of the following options is true about `Object.entries()`?

- `Object.entries()` returns an array of property values from the object
- `Object.entries()` returns an array of property keys from the object
- `Object.entries()` returns an array of `[key, value]` pairs
- `Object.entries()` returns the number of properties in an object

### [HTTP] Methods
Language knowledge (20 pts)

Which of the following options are valid HTTP methods?  
  
(Multiple answers expected)

- RECEIVE
- GET
- DOWNLOAD
- POST
- UPLOAD
- SEND
- PUT

### "use strict" and ES6
Language knowledge (20 pts)

Is the following statement true or false? 

_"Using 'use strict' inside ES6 modules is unnecessary_
_because ES6 modules have a strict mode execution by default."_

- True
- False

### [JS] Comparison with ===
Language knowledge (20 pts)

In JavaScript, what is the result of the following expression?  
  

```javascript
"2" === 2;​​
```

- true
- false
- null
- undefined

### [JS] Web JS onload
Language knowledge (20 pts)

In JavaScript, what event can be used to trigger an action when the page has finished loading?

- oncomplete
- onfinished
- oninit
- onload
- onupload

### Typeof Operator
Language knowledge (20 pts)

What would be the output of the statement below? 

```javascript
console.log(typeof "2");
```

- null
- number
- string
- object

### [JS] Variables #1
Language knowledge (20 pts)

In JavaScript, how do you declare a variable with a value of 2?

```text
int myNumber = 2;
```
```text
Number myNumber = 2;
```
```text
var myNumber = 2;
```

# Text

### Suitable Array Method

While conducting a scientific experiment, Michelle comes up with an array of results:

```javascript
[0.1, 2.3, 5.6, 7.8, 10.9]
```

The professor however wants the results to be integers, not floating-point values, and suggests using `Math.floor`. 

The professor wants the **original values to be preserved as well.**

Which **array method** would you recommend her to use to come up with the integer array? 

_Answer in one word._

### [JS] Parameters

In JavaScript, which keyword is used to access the array of arguments of a function?

### [JS] Design pattern 01

```javascript
var patternClass = (function () {
    var instance;
 
    function createInstance() {
        var object = new Object("This is the instance");
        return object;
    }
 
    return {
        getInstance: function () {
            if (!instance) {
                instance = createInstance();
            }
            return instance;
        }
    };
})();
 
```

If you know the design pattern used in this piece of code, type its name in the text field (1 word only).

### [JS] Loop steps

In JavaScript, what keyword is used to skip the current step of a loop and move on to the next one ?

### Type of args

```javascript
function log(...args) {
  // Do something with args
}

log(1, 2, 3, 4);
```

What is the expected value of `typeof args` inside the `log` function?

_Answer in one word._




# Code





































