
# QCM

### Which option(s) have correct object type?
Language knowledge (20 pts)

```typescript
const settingUser = (info: InfoType): string => {
	return info.name + "__" + info.profession;
};
```

Given the `settingUser` function, which options describe the `InfoType` type?

_Choose all options that apply._

- 
```typescript
interface InfoType {
	name: string;
	profession: string;
}
```

- 
```typescript
interface InfoType = {
	name: string;
	profession: string;
}
```

- 
```typescript
type InfoType = {
	name: string;
	profession: string;
};
```

- 
```typescript
type InfoType {
	name: string;
	profession: string;
};
```

### Question about "never" type
Language knowledge (40 pts)

```typescript
const ErrorGenerator = (str: string) => {
	throw new Error(str);
};
```

What would be the **best return type** assigned to the `ErrorGenerator` function? 

- string
- void
- never
- any

### TypeScript unknown type
Language knowledge (20 pts)

What type should be used when an object does not yet have a defined type, but will do so later?

- unknown
- void
- any
- all

### Class inheritance and abstract class
Language knowledge (40 pts)

```typescript
export class NumArr extends Investigate {
	public arr: number[];
	constructor() {
		super();
		this.arr = [1, 2, 3];
	}
	public arrLength(): number {
		return this.arr.length;
	}
}
```

Based on the above code snippet, which statements are true?

_Select all the correct answers._

- `NumArr` inherits the class `Investigate`
- `Investigate` can be an abstract class
- `Investigate` can be an interface
- TypeScript will throw an error

### TypeScript union types
Language knowledge (40 pts)

Consider the code below:

```typescript
type MountainBike = { make: string };
type RoadBike = { brand: string };
```

We want to implement a `Bike` type which could correspond either to a `MountainBike` type or a  `RoadBike` type.

How would you declare this type?

- 
```typescript
type Bike = MountainBike && RoadBike
```

- 
```typescript
type Bike = MountainBike + RoadBike
```

- 
```typescript
type Bike = MountainBike | RoadBike
```

- 
```typescript
type Bike = MountainBike & RoadBike
```

- 
```typescript
type Bike = (MountainBike, RoadBike)
```

### TypeScript type that JavaScript lacks
Language knowledge (20 pts)

Which of the following types are present in TypeScript BUT NOT in JavaScript?

_Select all the answers that apply._

- Enum
- Object
- Interface
- Number
- String
- Null

### Abstract vs generic class
Language knowledge (40 pts)

```typescript
export class Sample<T> {
	public something: T;
	constructor(info: T) {
		this.something = info;
	}
}
```

Which option is correct concerning the `Sample` **class**? 

- `Sample` is an abstract class
- `Sample` is a generic class
- `Sample` implements the `T` interface
- If we don't write `super()` inside the constructor, TypeScript will return an error

### Tuple
Language knowledge (40 pts)

Which one of the following is a **tuple** in TypeScript?

- 
```typescript
type Drink = {
	x: number;
	y: number;
	z: number;
};
```

- 
```typescript
type Drink = [string, boolean, number];
```

- 
```typescript
type Drink = string[]
```

- 
```typescript
export interface Drink {
	color: string;
	isSweet: boolean;
	isSugar: boolean;
}
```

### TypeScript type assertion of unknown values
Language knowledge (20 pts)

Given the following code:

```typescript
const tree: unknown = 90;
console.log(typeof tree);
```

What will be the **output** in the console?

- number
- 90
- unknown
- null
- undefined

### Which option uses "type inference"?
Language knowledge (20 pts)

In which option is **type inference** used to determine the type of `info`?

- 
```typescript
    let info: number | string;
    info = 10;
    info = "information";
    ```
    
- 
```typescript
    let info = 10;
    ```
    
- 
```typescript
    let info: number;
    info = 10;
    ```

### TypeScript modules real world example
Language knowledge (20 pts)

In a TypeScript application, we sometimes need **external modules**. When trying to import `lodash` using:

```typescript
npm install -i lodash
```

We get the following error:

```typescript
"library implicitly has an 'any' type".
```

![](https://static.codingame.com/work/servlet/fileservlet?id=36857053539625)

Why does this problem happen?

- The compiler can't find a declaration for the module `lodash`
- `lodash` is not compatible with TypeScript
- The syntax `import x from y` is not valid
- TypeScript doesn't support third-party libraries

### Incorrect function definition
Language knowledge (20 pts)

Which function will compile **without error**?

- 
```typescript
const sampleFunction = (x: number, y: number): string => {
	return x + y;
};
```

- 
```typescript
const sampleFunction = (a: number): void => a;
```

- 
```typescript
const sampleFunction = (a: number, b: number): string => {
	return (a + b).toString();
};
```

- 
```typescript
function sampleFunction(a: number, b: number): string {
	return a + b;
}
```

### TypeScript config file name
Language knowledge (20 pts)

It is possible to edit a file in order to create **custom configurations for the TypeScript interpreter**.

What is the name of this file?

- tsconfig.json
- typescript.ts
- tsconfig.ts
- config.js

### TypeScript type assertion
Language knowledge (20 pts)

How would you do a type assertion, to let the compiler knows that `unknownType` has the type `number`?

- 
```typescript
unknownType as number
```

- 
```typescript
unknownType = number
```

- 
```typescript
(number)unknownType
```

- 
```typescript
unknownType is number
```

### Error detection and project stage
Language knowledge (20 pts)

TypeScript helps developers to **detect errors** mainly at which stage of a project?

- During the development of the project
- During the unit/Integration testing
- During the integration of the project with the CI/CD pipeline

### tsconfig.json and compiler configuration
Language knowledge (20 pts)

By editing which file will you be able to configure the **TypeScript compiler**?

- ts.config.json
- ts.json
- tsconfig.json
- config.ts.json

### TypeScript access modifiers
Language knowledge (20 pts)

Which of the following **access modifier** IS NOT present in TypeScript?

- Private
- Public
- Protected
- Secure






# Text

### Dilemma with "this"

```typescript
const objOne = {
	firstName: "Martin",
	surName: "Piyal",
	getFullName(): string {
		return this.firstName + this.surName;
	},
};
```

If you want `this` to refer to the global object, and not to `objOne`, what type of function should you use to convert the current `getFullName`?

### Finding an optional property in an interface

```typescript
interface Info {
	name: string;
	age?: number;
	profession?: string;
	isStudent: boolean;
	isNative?: boolean;
}
```

Write the name of an optional property of `Info`.

There may be multiple optional properties. If this is the case, any of them is a valid answer, but you must write ONLY ONE of them.

### TypeScript VOID type

What return type should be given to a function that **returns nothing**?

```typescript
function process(): any {
    return;
}
```

_Type the keyword to replace `any` so that the function has its correct data return type._

# Code

### Joining point

We consider the sequence of numbers where a number is followed by **the same number plus the sum of its digits**.

For example `34` is followed by `41` (as 41 = 34 + (3 + 4)). `41` is itself followed by `46` (46 = 41 + (4 + 1)).

Two sequences which start from different numbers may **join at a given point**, for example, the sequence starting from `471` and the sequence starting from `480` share the number `519` (**the join point**) in their sequence. After the join point, the sequences are equal.

![](https://static.codingame.com/work/servlet/fileservlet?id=29075214099447)

_An example of two sequences joining at 519._ 

Implement the function `computeJoinPoint(s1: number, s2: number): number` which takes the starting points of two sequences and then returns the join point of these sequences.

Constraints:

- The given sequences always join
- 0 < `s1, s2` < 20000000
- 0 < join point < 20000000

### Loop detection

The goal of this exercise is **to find the endpoint node** of a simple network.

In this simple network, each node is linked to at most one outgoing node in a **one way** **forward** direction.

![](https://static.codingame.com/work/servlet/fileservlet?id=27057673253517)

_A simple network example_

Implement function `findNetworkEndpoint(startNodeId, fromIds, toIds)` which should return the last node id of the network found when starting from the node with id `startNodeId` and following the links of the network.

In the above example, the endpoint node when starting from node #2 (or any other node) is node #5.

`fromIds` and `toIds` are two arrays of the same length which describe the one-way links of the network (`fromIds[i]` is linked to `toIds[i]`). In the example above, `fromIds` is:

```cross
[1, 7, 3, 4, 2, 6, 9]
```

and `toIds` is:

```cross
[3, 3, 4, 6, 6, 9, 5]
```

**In case you run into a loop** when traversing the network, the function should return the id of the last node traversed **before** closing the loop.

Constraints:

- 0 < number of links < 10000
- A node cannot be directly linked to itself

### Tennis Game

Write a program which returns the current state of a tennis game.

_// REMINDER OF THE TENNIS RULES //_

A tennis game is played as follows:

- First score  = 15 points
- Second score = 30 points
- Third score = 40 points

After a player reaches 40 points, he or she can:

- Enter a **DEUCE** state if both players have scored the same number of times
- Enter an **ADVANTAGE** state if both players scored at least three times AND the player scored one time more than his or her opponent
- **WIN** the game if he or she has scored at least four times AND two times more than the other player

![](https://static.codingame.com/work/servlet/fileservlet?id=37457292922763)

Implement the function `computeGameState(nameP1, nameP2, wins)` which returns the current state of a game.

**Parameters:**

- `nameP1`, the name of the first player as a string
- `nameP2`, the name of the second player as a string
- `wins`, an array of strings listing the name of each ball's winner

**Expected Result:**

The current state of the game as a string:

- `P1 0 - P2 0` (with players' names in the same order as given in parameters)
- `P1 15 - P2 30`
- `15a` (in case of a 15-15 draw)
- `30a` (in case of a 30-30 draw)
- `P2 WINS`
- `DEUCE`
- `P1 ADVANTAGE`
- ...

**EXAMPLE:**

**Parameters**

Bob

Anna

Bob, Anna, Bob

**Result**

Bob 30 - Anna 15

### Portals

#### Objective

Your avatar is in a strange world with two inter-dimensional, bidirectional portals. Write a program that returns the coordinates of your avatar given a series of moves and the location of the portals.

![](https://static.codingame.com/work/servlet/fileservlet?id=38287530564005)

#### How it works

- The map is represented by a grid of `width` squares wide and `height` squares high.
- The top left square is located at `(0, 0)` where the first integer represents the column and the second the row.
- The initial positions of your avatar and the two portals are given by arrays of two integers `position`, `portalA`, and `portalB`.
- `moves`, is a string composed of the characters `U` (top), `D` (down), `R` (right), `L` (left).

If your avatar walks from a given square to a square with a portal, he teleports to the associated portal (and stays on that target square until he makes another move). If a movement would make your avatar move past the end of the map, he does not move nor teleport.

#### Implementation

Implement the function `computeFinalPosition(width, height, position, portalA, portalB, moves)` which:

- takes as inputs the integers `width`, `height`, the integer arrays `position`, `portalA`, `portalB`, and the string `moves` with :
    - 0 < `width` < 20
    - 0 < `height` < 20
    - 0 <= number of characters in `moves` <= 255
- and returns the final position of your avatar as an array of two integers.

#### Example

![](https://static.codingame.com/work/servlet/fileservlet?id=39297999963943)

### Simple encoding

Implement the function `encode(plainText)` which returns an encoded message.

It receives a `plainText` string parameter, for example `aaaabcccaaa`.

You must encode it by counting each consecutive sequence of a letter. e.g. in `aaaabcccaaa`, there are:

- 4 times the letter `a`
- then 1 `b`
- then 3 `c`
- then 3 `a`

Therefore you must return the string `4a1b3c3a`.

Constraints :

- `plainText` is made of lowercase letters: **a**-**z**
- `plainText` is never `null` and has a maximum length of 15000 characters

**EXAMPLES:**

**PlainText** aabaa
**EncodedText** 2a1b2a

**PlainText** aaaabcccaaa
**EncodedText** 4a1b3c3a

### Check digit computation

In order to detect errors on identification numbers, a check digit is often added at the end of that number.

Implement the function `computeCheckDigit(identificationNumber)` that takes a number (as a string) and returns the check digit, using the following algorithm:

- Sum the digits in the even-numbered positions (positions 0, 2, 4, etc.).
- Multiply the result by three.
- Add the digits in the odd-numbered positions to the result (positions 1, 3, 5, etc.).
- Take the last digit of the result.
- If it's not 0, subtract this digit from 10. Otherwise, keep it as 0.
- Return the result

_(Assuming that the first digit on the left has the position 0)_

  
**Example:**

Given the identification number `39847` :

- Sum the digits in the even-numbered positions: `3 + 8 + 7 = 18`
- Multiplied by three: `18 x 3 = 54`
- Add the digits in the odd-numbered positions: `54 + (9 + 4) = 67`
- Last digit: `7`
- Subtract 7 from 10: `10 - 7 = 3`

The expected result is `3` for `39847`.

**Constraints:**

The length of `identificationNumber` can vary from 1 to 12 characters.

### Javanais

#### Objective

Javanais, also known as "_Langue de feu_" (fire language), is a slang coding process that was used in the late 19th century by some criminals to encrypt their conversations. Write a program that returns the Javanais translation of a sentence.

#### How it works

- Before each of the following vowel (a, e, i, o, u), insert the parasitic syllable "av" ;
- Unless the vowel is preceded by another vowel.

#### Implementation

Implement the function `translate(text)` which:

- takes as input `text`, a string of fewer than 255 characters ;
- returns the Javanais translation as a string.

For simplicity, the inputs contain only lowercase letters.

#### Example

![](https://static.codingame.com/work/servlet/fileservlet?id=39072371100548)

### Check a sudoku grid (and output the first error)

You need to check whether a sudoku grid is correct and tell where the first error is found.

A sudoku consists of a 2-dimensional board, 9 cells by 9 cells. Each cell contains a digit from 1 to 9.

All the sudoku cells you get in input are already filled.

You must check all the following conditions **in the order shown**, and exit at the first error found.

- Each line must contain every digit from 1 to 9 only once. Check them from top to bottom. If a line is not correct, return `LINE <y> INVALID`, where `y` is the index of the line (counted from 0).
- Each column must contain every digit from 1 to 9 only once. Check them from left to right. If a column is not correct, return `COLUMN <x> INVALID`, where `x` is the index of the column (counted from 0).
- A sudoku is also divided into 9 regions, made up of squares of 3 cells by 3 cells. Each region must contain every digit from 1 to 9 only once. Check them from top to bottom, then from left to right. If a region is not correct, return `REGION <r> INVALID`, where `r` is the index of the region (counted from 0).

If all the conditions are fulfilled, return the text `VALID`.

![](https://www.codingame.com/work/servlet/fileservlet?id=57512436296078)

![[Pasted image 20231208145447.png]]

### Finding The Largest Profit

#### Objective

In this task, you are given an array of integers, which represent the monthly net profits of a company. The company wants you to find the range of consecutive months that had the most profit.

![[Pasted image 20231208145418.png]]

### Red envelopes

#### Objective

In Chinese culture, it is common during celebrations to give "red envelopes" (红包) containing some money. Most often, the adult generations give to the younger generations.

You want to build a WeChat app to help grandparents divide their giving budget among their grandchildren. Write a program that calculates the number of "lucky" gifts (equal to 8) based on the budget, `money`, and the number of grandchildren, `giftees`.

#### How it works

Many rules, mixing tradition and superstition, govern this gift:

- Gifts must not contain the amount 4 (四), as this sounds like "death" (死).
- It is auspicious to give an amount of 8 (八), as this sounds like "fortune" (发).
- It would be wrong to give nothing to any of the grandchildren.

So your algorithm should return the number of gifts equal to 8, following these rules:

- Spend the entire budget (unless there is enough budget to give 8 to everyone).
- Do not give any 4 (by tradition, the budget will never be 4).
- Do not give any 0 (unless there is not enough money for all giftees).
- Give a maximum amount of 8 once the above rules are met

#### Implementation

Implement the function `luckyMoney(money, giftees)` which:

- takes as input the integers `money` and `giftees` with :
    - 0 <= `money` < 100
    - 0 < `giftees` < 10
- and returns the number of donations equal to 8 as an integer.

![[Pasted image 20231208145519.png]]

### Summer Sales

It's almost the Summer Sales!

You work for a shop that wishes to give a discount of `discount%` to **the most expensive item** purchased by a given customer during the sales period. Only one product can benefit from the discount. 

You are tasked by the shop owner to implement the function `calculateTotalPrice(prices, discount)` which takes the list of prices of the products purchased by a customer and the percentage `discount` as parameters and returns the total purchase price as an integer (**rounded down** if the total is a float number).

Constraints:

- 0 ≤ `discount` ≤ 100
- 0 < price of a product < 100000
- 0 < number of products < 100

### Anagrams

An anagram of a word is a word written with the same letters (case insensitive) but not necessarily in the same order.  
  
For example "Drier" is an anagram of "Rider".

Implement the function `isAnagram(wordA, wordB)` , which should return `true` if `wordA` is an anagram of `wordB` and `false` otherwise.

The parameters `wordA` and `wordB` are two defined strings. They can be empty.

![[Pasted image 20231208145557.png]]

### Intervals

Implement the `findSmallestInterval(numbers)` function which returns the smallest positive interval between two values of the `numbers` table.

For example given the table `[1 6 4 8 2]` the smallest interval is `1` (difference between `2` and `1`)

  
**Constraints:**

- `numbers` contains at least two numbers and a maximum of 100,000 entries.
- The solutions that favor execution time on large size arrays will get the most points.
- The difference between two elements will never exceed the size of an integer for your language

![[Pasted image 20231208145620.png]]

### Duodigits

We call a integer a **"duodigit"** if its decimal representation uses **no more** than two different digits. For example, `12`, `110`, `-37333` are **duodigits**, but `102` is not.

Implement the function `isDuoDigit(number)` which returns a string:

- `y` if `number` is a duodigit
- `n` otherwise

![[Pasted image 20231208145638.png]]

### Summing based on factors

The function `computeMultiplesSum(n)` should return **the sum of all the positive multiples** of **3** or **5** or **7** strictly below  `n`.

As an example, for `n=11`, we get **3,5,6,7,9,10** as multiples and the sum of these multiples is **40**.

Implement `computeMultiplesSum(n)`.

**Constraints**:

- `0 ≤ n < 1000`

### Stock Prices

#### Objective

In this problem, you'll be given a list of daily stock prices, and you'll be asked to return the three stocks with the highest average price.

#### Implementation

Implement the function `getTopStocks(stocks, prices)` which takes as input:

- an array of strings (`stocks`), representing the considered stocks.
- an array of 2 dimensions (`prices`), representing the stock prices (inner lists) for each day (outer list). 

An example input would look like this:

```python
['AMZN', 'CACC', 'EQIX', 'GOOG', 'ORLY', 'ULTA']
```

```python
[12.81, 11.09, 12.11, 10.93, 9.83, 8.14], [10.34, 10.56, 10.14, 12.17, 13.1, 11.22], [11.53, 10.67, 10.42, 11.88, 11.77, 10.21]
```

Your `getTopStocks` function should return an array containing the names of the three stocks with the highest average value. The array should be sorted by decreasing average value. You're guaranteed that each stock will have a unique average value.

For the above example, the correct output would be:

```python
['GOOG', 'ORLY', 'AMZN']
```

### A mysterious diary

As you were wandering in a peculiar bookshop, you stumbled upon a secret diary written by the well-known mad scientist Hubert Zweistein. You are very anxious to read his writing, but it is written in a strange coded language.

You quickly make a discovery: the lines are grouped 3 by 3, and each group contains the same number of letters. By alternating the letters of the 3 lines, a message appears!

  
From the three lines of the book, alternate the letters :

- 1st letter of the 1st line,
- 1st letter of the 2nd line,
- 1st letter of the 3rd line,
- 2nd letter of the 1st line,
- 2nd letter of the 2nd line,
- ...

Uncover what the doctor Zweistein was hiding in these pages.

**Notes:** 

- Complete the given function, which must **return** the correct result.
- The result will not count if you print it on the standard output.
- You can use the standard error (stderr) for your debugs.
- The three lines given in parameters contain only uppercased letters, and have a maximal length of 15 characters.

![[Pasted image 20231208145734.png]]

### Duplicates removal

Implement the function `filterDuplicates(data)` that takes a `data` array as input and returns an array containing the values of  `data` **without the duplicates**.

The initial order of the values must be kept.

The variable `filtered_count` must be set to the size of the new array.

Example: `[7 6 4 3 3 4 9] => [7 6 4 3 9]`

Constraints:

- `data` is never `null`

### Sum Pairs

#### Objective

In this problem, you'll be given an array of positive integers and a separate integer, `k`, and tasked with finding whether there is a pair of integers in the array that sums to exactly `k`.

#### Implementation

Implement the function `findSumPair(numbers, k)` which takes as input:

- an array of positive integers (`numbers`).
- a positive integer (`k`), representing the target sum. 

For example:

- `numbers = [1, 5, 8, 1, 2]`
- `k = 13`

Your `findSumPair` function should return an array of two integers, containing the indices of a pair of integers in the array that sums to `k`. Note that:

- The first index of the array is 0. 
- The first integer you return should represent the lower index. 
- `[0, 0]` should be returned if no pair is found. 
- In the case that there are multiple possible pairs that sum to the target, return the pair whose left index is the lowest.
- In the case of two pairs having the same left index, favor the pair with the lower right index.

For the above example, the correct return value would be: `[1, 2]`.

![[Pasted image 20231208145814.png]]

### Word Filtering

#### Objective

In this problem, you'll be filtering words based on the letters that they contain. Specifically, you'll be given an input list of words (all lowercase), along with a set of lowercase letters, and asked to filter out the words that don't contain any letters in the given set.

#### Implementation

Implement the function `filterWords(words, letters)` which takes as input:

- an array of strings (`words`), with the words to filter.
- A string (`letters`), used to filter the words.

For example:

- `words = ['the', 'dog', 'got', 'a', 'bone']`
- `letters = 'ae'`

Your `filterWords` function should return an array of strings from `words` that contain at least one letter in `letters`. The returned list should maintain the same ordering as in `words`.

For the above example, the correct output would be:

```python
['the', 'a', 'bone']
```

### Word Frequencies

#### Objective

In text processing tasks, one of the first things to do is figure out how often each word appears in a given document. In this task, you will be completing a function that returns the unique word frequencies of a tokenized word document.

#### Implementation

Implement the function `countFrequencies(words)` which takes as input an array of strings (`words`), representing a tokenized word document. For example:

```python
['the', 'dog', 'got', 'the', 'bone']
```

Your `countFrequencies` function should return an array of integers containing the number of occurrences of each word sorted alphabetically.

For the above example, the correct output would be:

```python
[1, 1, 1, 2]  # bone = 1, dog = 1, got = 1, the = 2
```

### Largest wins from chaos

Implement  the function `findLargest(numbers)`, so it returns the largest number from the `numbers` array.

  
Notes:

-  `numbers` contains only integers.
-  `numbers` always contains at least one element, and never contains more than 10 elements.
- The integers are ranged from `-2^31` to `+2^31 - 1` (they always fit in a 32-bit signed integer).

![[Pasted image 20231208145913.png]]

# [[Codingame Javascript#Game|Game]]
