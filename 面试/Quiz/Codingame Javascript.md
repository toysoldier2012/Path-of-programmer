
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




# Game

^88610c

### Image searching

#### Goal

Find a pattern in an image.

#### Rules

You are given 2 images: a base image and a pattern which may appear somewhere on this image.

Each image is represented by an array of strings, where each element of the array represents a row of pixels of the image, and each character represents one pixel. Understanding this encoding is not necessary to solve this problem, but for your information, a detailed explanation is provided below.

You must return the position x, y of this pattern in the image, or [-1, -1] if the pattern is not found. If the pattern appears multiple times, return the position of the highest one (the smallest y), and in case of equality, the leftmost one (the smallest x).

The position of the pattern is represented by the coordinates x, y of its top-left corner. x represents the column, y represents the row, and the coordinates [0, 0] represents the top-left corner.

#### Implementation

Implement the function `solve(imageWidth, imageHeight, image, patternWidth, patternHeight, pattern)` where the parameters are:

- imageWidth: the image width
- imageHeight: the image height
- image: the image as an array of strings, where each character represents a pixel
- patternWidth: the pattern width
- patternHeight: the pattern height
- pattern: the pattern as an array of strings, where each character represents a pixel

and which should return:

- if the pattern is present in the image: the position x, y, as an array of 2 integers, representing the top-left corner of the first pattern, going from top to bottom and left to right.
- if the pattern is not present in the image: [-1, -1]

Victory Conditions

- The pattern is indeed located at coordinates x, y.
- If the pattern appears multiple times, return the position of the highest one (the smallest y), and in case of equality, the leftmost one (the smallest x).

Defeat Conditions

- The inner image that starts at coordinates x, y doesn't match the pattern.
- You take longer than 1 second to anwser.
- There's another matching pattern above or on the left.

#### Constraints

1 ≤ imageWidth ≤ 400

1 ≤ imageHeight ≤ 400

1 ≤ patternWidth ≤ 400

1 ≤ patternHeight ≤ 400

Response time ≤ 1s

#### Encoding details

An image is initially a 2D-array of integers, where each integer represents a pixel (using RGB notation). All our images contain less than 62 different colors, so that we're able to encode each integer as a character among 0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ. We basically transformed the image into an array of strings, where the 1st string in the array is the 1st row of the image, etc.

For example, this 3x3 image:

![](https://static.codingame.com/work/servlet/fileservlet?id=56649115215925)

  

is represented as a 2D integer array as:

```
[
  [0xff0000, 0x00ff00, 0x0000ff],
  [0xd3d3d3, 0x000000, 0xd3d3d3],
  [0xff0000, 0x00ff00, 0x0000ff]
]
```

which is then encoded as an array of strings as:

```
[
  "012",
  "343",
  "012"
]
```

### Interlocked Blocks - Hard

#### Objective

You make wooden toys in your woodworking shop for the enjoyment of your grandchildren. You have planned a serie of small puzzles, and you would like to automate the writing of their solutions.

#### Rules

Each puzzle is a grid, on which wooden blocks are placed. These blocks must be taken out of the game, one after the other, without colliding. You have to determine their movement sequence.

Each block is numbered with a value between 0 and 9. When you enter the number of a block and a direction, it will be moved until it is off of the grid.

If more than one block can be taken out at the same time, you can choose which one you would like to remove first.

If a block can be taken out to many directions, you can choose any one of them.

#### Implementation

Implement the function `solve(width, height, nbBlocks, grid)`. This function is executed at each round of the game and should return the number of the next block to move and its direction.

Input data of the function

- width: width of the puzzle, in number of cells.
- height: height of the puzzle, in number of cells.
- nb_blocks: number of blocks initially present in the puzzle.
- grid: a list of height elements, each of which is a string with a size equal to width.

The parameters width, height and nb_blocks do not change during the whole game.

The grid parameter represents the current situation of the puzzle. Each of its characters can take one of the following values :

- . (a dot): an empty square.
- X: a wall. They are placed on some borders of the puzzle. You cannot move these walls.
- an integer between 0 and nb_blocks-1: a square occupied by a block. The same number can be present several times in the grid, representing a single block that extends over several squares. All cells with the same block number are connected (they are never separated into several isolated groups).

Output data of the function

A string, containing two data, separated by a space:

- An integer, between 0 and nb_blocks-1, representing the number of the block you want to move.
- The direction you would like to move the block in. There are 4 possible values:
    - UP
    - RIGHT
    - DOWN
    - LEFT

You can only move one block at a time. The block is moved until it either (a) exits the board entirely or (b) collides with another block.

Output example: 1 RIGHT

Victory conditions

All blocks are out of the game.  
(There is at least one possible block removal order that will yield a solution.)

Defeat conditions

A collision occurs between the moved block and another block, or between the moved block and a wall.

#### Constraints

1 < width < 16  
1 < height < 16  
1 ≤ nb_blocks < 10

### Interlocked Blocks - Medium

#### Objective

You make wooden toys in your woodworking shop for the enjoyment of your grandchildren. You have planned a serie of small puzzles, and you would like to automate the writing of the solutions.

#### Rules

Each puzzle is a grid, on which are placed wooden blocks of various shapes. These blocks must be taken out of the game, one after the other, without colliding. You have to determine the order in which they are taken out.

Each block is numbered with a value between 0 and 9. When you enter the number of a block, it will be moved to the right until it is off of the grid.

If several blocks can be exited at the same time, you can choose which one you would like to remove first.

#### Implementation

Implement the function `solve(width, height, nbBlocks, grid)`. This function is executed at each round of the game and should return the number of the next block to move.

Input data of the function

- width: width of the puzzle, in number of cells.
- height: height of the puzzle, in number of cells.
- nb_blocks: number of blocks initially present in the puzzle.
- grid: a list of height elements, each of which is a string with a size equal to width.

The parameters width, height and nb_blocks do not change during the whole game.

The grid parameter represents the current situation of the puzzle. Each of its characters can take one of the following values :

- . (a dot): an empty square.
- X: a wall. They are placed on the first and last line, as well as on the first character of each line, to show that the only possible exit is to the right. You cannot move these walls.
- an integer between 0 and nb_blocks-1: a square occupied by a block. The same number can be present several times in the grid, representing a single block that extends over several squares. All cells with the same block number are connected (they are never separated into several isolated groups).

Output data of the function

An integer, between 0 and nb_blocks-1, representing the number of the block you want to output to the right.

You can only move one block at a time, and each move must always be to the right. A move is made until the end: either until the block is completely out, or until one block collides with another.

Victory conditions

All blocks are out of the game.  
(There is at least one possible block removal order that will yield a solution.)

Defeat conditions

A collision occurs between the block you moved and a block on the grid.

#### Constraints

1 < width < 15  
1 < height < 15  
1 ≤ nb_blocks < 10

### Transform an array using 2x2 patterns

####  Objective

As an alchemist, you are testing some formulas to transmute elements to others. You work with 8 basic types of elements, numbered from 0 to 7.

To perform a transmutation, you place some elements on a 2-dimensional grid, then by using a magical process known only by yourself, the elements transmute, according to specific rules.

You want to determine which elements you will obtain after the transmutation.  

####  Rules

Each transmutation rule is defined by a pattern (a sub-square whose size is 2 x 2 elements) and a resulting element.

For each 2 x 2 sub-square of the initial grid, find the corresponding pattern, and replace it with the unique resulting element.

You have to apply a transmutation rule to every sub-square, even when they overlap. So, the resulting grid will have a width and a height reduced by 1.

When a sub-square does not correspond to any pattern, the resulting element is the number 0 by default.

####  Example

With this initial grid :

```cross
grid = [ [1, 1, 1], [1, 1, 4], [1, 4, 6] ]
```

![](https://www.codingame.com/work/servlet/fileservlet?id=58916175200623)

and these rules :

```cross
rules = [
    {"pattern": [1, 1, 1, 1], "result": 5},
    {"pattern": [1, 1, 1, 4], "result": 6},
]
```

We extract 2 x 2 sub-squares, starting from the upper left corner of the initial grid. Elements of the sub-square are ordered: top-left, top-right, bottom-left, bottom-right.

- The first sub-square contains the elements [1, 1, 1, 1]. So the first rule applies. It will result in the element 5.
- One step right, the second sub-square contains the elements [1, 1, 1, 4]. The second rule applies. It will result in the element 6.
- We return to the left of the grid and go one step down.
- The third sub-square contains the elements [1, 1, 1, 4] as well. We get the element 6.
- One step right, the last sub-square contains the elements [1, 4, 4, 6]. There is no rule for this pattern, so the result will be the default element 0.

![](https://www.codingame.com/work/servlet/fileservlet?id=58916193210959)

Finally, the resulting grid is `[ [5, 6], [6, 0] ]`.

![](https://www.codingame.com/work/servlet/fileservlet?id=58935078002772)

The rules will never define the same pattern twice. For example, you will never have:

```cross
rules = [
    {"pattern": [1, 2, 3, 4], "result": 3},
    {"pattern": [1, 2, 3, 4], "result": 6},
]
```

####   Implementation

Implement the function `solve(grid, rules)`. This function must return a 2 D array of integers: the elements that will be on the grid after a transmutation.

The function takes 2 parameters:

- `grid`: a 2 D array of integers, representing the initial grid.
- `rules`: an array of objects, representing the set of transmutation rules. For each rule:
    - the property `pattern` specifies the 4 elements needed (in the order top-left, top-right, bottom-left, bottom-right),
    - the property `result` specifies the newly created element.

Victory conditions

Your program returns the correct grid after a transmutation.

Lose Conditions

- Your program does not return a 2 D array of integers.
- The grid returned by your function does not have the correct size: both its dimensions should be one less than the initial `grid`.
- The grid returned by your program does not contain the correct elements.

#### Constraints

- The size of `grid` is between 4 x 4 and 12 x 12
- `grid` is always a square (width=height)
- There are at most 1,000 rules in `rules`

Implementation

Function

Implement the function solve.

Parameters

grid (number[][]): The initial grid of elements

rules (Rule[]): Transmutation rules between elements

Return value

newGrid (number[][]): The final grid of elements

Constraints

4 <= length (grid) <= 12

4 <= length (grid[]) <= 12

0 <= grid[][] <= 7

length (rules) <= 1,000

0 <= rules[]. pattern[] <= 7

0 <= rules[]. result <= 7

Available RAM: 512 MB

### Robotic packages classifier

#### Objective

Sort the packages using the robotic arm of the factory.

####  Rules

You work in an automated factory and your objective is to write the function that will dispatch the packages to the correct stack, according to their volume and mass.

- A package is **bulky** if its volume (Width x Height x Length) is greater than or equal to 1,000,000 cm³ or when one of its dimension is greater or equal than 150 cm.
- A package is **heavy** when its mass is greater or equal than 20 kg.

You must dispatch the packages in the following stacks:

- STANDARD: standard packages (those which are not bulky nor heavy) can be handled normally.
- SPECIAL: packages that are either heavy or bulky can't be handled automatically.
- REJECTED: packages that are **both** heavy and bulky are rejected.

####   Implementation

Implement the function `solve(width, height, length, mass)` (units are centimeter for the dimensions and kilogram for the mass). This function must return a string: the name of the stack where the package should go.

Victory Conditions

All the packages are on the proper stack.

Lose Conditions

Your function returns a wrong answer.

#### Constraints

20 ≤ width, height, length ≤ 200

10 ≤ mass ≤ 1000

### Interlocked Blocks - Easy

####  Objective

You make wooden toys in your woodworking shop for the enjoyment of your grandchildren. You have planned a serie of small puzzles, and you would like to automate the writing of their solutions.

#### Rules

Each puzzle is a grid, on which wooden blocks are placed. These blocks must be taken out of the game, one after the other, without colliding. You have to determine the order in which they are taken out.

Each block is numbered with a value between 0 and 9. When you enter the number of a block, it will be moved to the right until it is off of the grid.

**All blocks are either horizontal rectangles or simple one-by-one sized squares.** To find a block to exit, you can select one of the numbers located on the rightmost square of the grid.

If more than one block can be taken out at the same time, you can choose which one you would like to remove first.

####  Implementation

Implement the function `solve(width, height, nbBlocks, grid)`. This function is executed at each round of the game and should return the number of the next block to move.

Input data of the function

- width: width of the puzzle, in number of cells.
- height: height of the puzzle, in number of cells.
- nb_blocks: number of blocks initially present in the puzzle.
- grid: a list of height elements, each of which is a string with a size equal to width.

The parameters width, height and nb_blocks do not change during the whole game.

The grid parameter represents the current situation of the puzzle. Each of its characters can take one of the following values :

- . (a dot) : an empty square.
- X: a wall. They are placed on the first and last line, as well as on the first character of each line, to show that the only possible exit is to the right. You cannot move these walls.
- an integer between 0 and nb_blocks-1: a square occupied by a block. The same number can be present several times in the grid, representing a single block that extends over several squares. All cells with the same block number are placed on the same line and are never separated into several isolated groups.

Output data of the function

An integer, between 0 and nb_blocks-1, representing the number of the block you want to exit to the right.

You can only move one block at a time, and each move must always be to the right. A move is made until the end: either until the block is completely out, or until one block collides with another.

Victory conditions

All blocks are out of the game.  
(There is at least one possible block removal order that will yield a solution.)

Defeat conditions

A collision occurs between the block you moved and a block on the grid.

#### Constraints

1 < width < 15  
1 < height < 15  
1 ≤ nb_blocks < 10

### Moving atoms on a grid

####  Objective

Move an atom on a grid using predefined actions.  

#### Rules

You have discovered ancient alchemical processes for transmuting matter. You can add or remove protons and neutrons from an atom.

Your atom is placed in the game area. The x-axis represents the number of protons and the y-axis the number of neutrons.

You need to list the actions to be taken so that the atom reaches the expected number of protons and neutrons.

The following 3 predefined actions are available:

- `PROTON`: adds a proton to the atom. In the game area, this is equivalent to moving it one square to the right.
- `NEUTRON`: adds a neutron, moves the atom down one square.
- `ALPHA`: removes two protons and two neutrons by alpha decay, moves the atom two squares diagonally left and up.

You must return a list of strings corresponding to the actions to be performed.

For example, if you return a list containing the words "`ALPHA`", "`PROTON`", "`PROTON`", "`PROTON`", the atom will lose two protons and two neutrons, then regain 3 protons. In the end, it will move two squares up and one square to the right.

The order of the actions is not important. There's **no need to minimize the number of actions**. You are allowed to move your atom out of the grid, even through the upper and left borders.

####  Implementation

Implement the function `solve(protonsStart, neutronsStart, protonsTarget, neutronsTarget)`. This function must return a list of strings: the successive actions to be performed to go from the supplied atom to the target atom.

The function takes 4 input parameters:

- `protonsStart` and `neutronsStart` represent the number of protons and neutrons in the initial atom.
- `protonsTarget` and `neutronsTarget` represent the number of protons and neutrons in the desired atom.

Victory conditions

Your actions list correctly moves the atom to the desired number of protons and neutrons.

Defeat conditions

- Your program indicates an invalid action.
- The actions list returned by your function does not move the atom to the correct location.
- Your list exceeds 1000 actions.

#### Constraints

- 0 ≤ protonsStart, protonsTarget < 30
- 0 ≤ neutronsStart, neutronsTarget < 20

Implementation

Function

Implement the function solve.

Parameters

protonsStart (number): The initial number of protons

neutronsStart (number): The initial number of neutrons

protonsTarget (number): The desired number of protons

neutronsTarget (number): The desired number of neutrons

Return value

recipe (string[]): an array of strings

Constraints

Available RAM: 512 MB










