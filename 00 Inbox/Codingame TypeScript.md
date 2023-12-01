
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

# Code
