## Lesson 03

### JavaScript Fundamentals: Syntax, Data Types, and Data Structures

#### Introduction (5 minutes)
We've learned about binary and Boolean logic in our previous lessons. Now we'll learn the building blocks of JavaScript - think of this as learning the vocabulary and grammar of our new programming language.

#### JavaScript Syntax Basics (15 minutes)

1. **Variables and Constants**
   ```javascript
   // Variables can change
   let score = 0;
   score = 10;
   
   // Constants can't change
   const playerName = "John";
   
   // Avoid using 'var' (old way)
   var oldWay = "don't use this";
   ```

2. **Basic Operators**
   ```javascript
   // Math operators
   let sum = 5 + 3;          // 8
   let difference = 10 - 4;   // 6
   let product = 6 * 2;      // 12
   let quotient = 15 / 3;    // 5
   let remainder = 17 % 5;   // 2 (modulus/remainder)
   let power = 2 ** 3;       // 8 (exponential)

   // Combining operators
   let result = (5 + 3) * 2;  // 16

   // Shorthand operators
   let number = 5;
   number += 3;  // same as: number = number + 3
   number -= 2;  // same as: number = number - 2
   number *= 2;  // same as: number = number * 2
   ```

3. **Comparison Operators**
   ```javascript
   // Comparing values
   let isEqual = 5 === 5;        // true
   let isNotEqual = 5 !== '5';   // true
   let isGreater = 6 > 5;        // true
   let isLessOrEqual = 4 <= 4;   // true

   // Common mistake: using = instead of ===
   let x = 5;         // assignment
   let y = x === 5;   // comparison
   ```

4. **Logical Operators**
   ```javascript
   // AND (&&): both must be true
   let canDrive = age >= 16 && hasLicense;

   // OR (||): at least one must be true
   let canEnter = isEmployee || hasInvitation;

   // NOT (!): reverses true/false
   let isNotValid = !isValid;
   ```

#### Data Types (15 minutes)

1. **Numbers**
   ```javascript
   // Whole numbers
   let age = 25;
   let temperature = -5;
   
   // Decimal numbers
   let price = 19.99;
   let pi = 3.14159;
   
   // Math operations
   let total = price * 2;
   let average = (10 + 20 + 30) / 3;
   ```

2. **Strings (Text)**
   ```javascript
   // Different ways to create strings
   let name = "Alice";
   let message = 'Hello there';
   
   // Modern way (template literals)
   let greeting = `Hello, ${name}!`;
   
   // String operations
   let length = name.length;              // 5
   let uppercase = name.toUpperCase();    // "ALICE"
   let substring = name.slice(0, 2);      // "Al"
   ```

3. **Booleans**
   ```javascript
   let isRaining = true;
   let isSunny = false;
   
   // Common boolean operations
   let isWeekend = true;
   let isHoliday = false;
   let canSleepIn = isWeekend || isHoliday;  // true
   ```

4. **null and undefined**
   ```javascript
   // undefined: variable declared but not assigned
   let notDefined;
   console.log(notDefined);  // undefined
   
   // null: intentionally empty
   let empty = null;
   ```

#### Data Structures (20 minutes)

1. **Arrays**
   ```javascript
   // Creating arrays
   let fruits = ['apple', 'banana', 'orange'];
   let numbers = [1, 2, 3, 4, 5];
   let mixed = ['text', 42, true, null];
   
   // Accessing elements (starts at 0)
   console.log(fruits[0]);     // 'apple'
   console.log(fruits[1]);     // 'banana'
   
   // Modifying arrays
   fruits.push('grape');       // Add to end
   fruits.pop();              // Remove from end
   fruits.unshift('kiwi');    // Add to start
   fruits.shift();           // Remove from start
   
   // Useful array methods
   let length = fruits.length;
   let includesBanana = fruits.includes('banana');
   let position = fruits.indexOf('orange');
   ```

2. **Objects**
   ```javascript
   // Creating an object
   let person = {
       name: "Bob",
       age: 30,
       hobbies: ['reading', 'gaming'],
       address: {
           city: "New York",
           zip: "10001"
       }
   };
   
   // Accessing object properties
   console.log(person.name);           // Dot notation
   console.log(person['age']);         // Bracket notation
   console.log(person.address.city);   // Nested properties
   
   // Modifying objects
   person.age = 31;
   person.email = "bob@example.com";   // Add new property
   delete person.email;                // Remove property
   ```

#### Advanced Data Operations (20 minutes)

1. **Working with Arrays**
   ```javascript
   const numbers = [1, 2, 3, 4, 5];
   
   // forEach - do something with each item
   numbers.forEach(function(number) {
       console.log(number * 2);
   });
   
   // map - transform each item
   const doubled = numbers.map(function(number) {
       return number * 2;
   });
   
   // filter - keep only some items
   const evenNumbers = numbers.filter(function(number) {
       return number % 2 === 0;
   });
   
   // find - get first matching item
   const firstBigNumber = numbers.find(function(number) {
       return number > 3;
   });
   
   // Using arrow functions (shorter way)
   const tripled = numbers.map(num => num * 3);
   const bigNumbers = numbers.filter(num => num > 3);
   ```

2. **Working with Objects**
   ```javascript
   const user = {
       name: 'Bob',
       age: 30,
       hobbies: ['reading', 'gaming']
   };
   
   // Getting all keys
   const keys = Object.keys(user);     // ['name', 'age', 'hobbies']
   
   // Getting all values
   const values = Object.values(user);  // ['Bob', 30, ['reading', 'gaming']]
   
   // Copying objects
   const userCopy = { ...user };       // Spread operator
   
   // Combining objects
   const moreInfo = {
       city: 'New York',
       email: 'bob@example.com'
   };
   const fullProfile = { ...user, ...moreInfo };
   ```

3. **String Operations**
   ```javascript
   const text = "Hello, World!";
   
   // Finding text
   const hasWorld = text.includes('World');    // true
   const position = text.indexOf('World');     // 7
   
   // Changing text
   const shouting = text.toUpperCase();        // "HELLO, WORLD!"
   const whispering = text.toLowerCase();      // "hello, world!"
   
   // Splitting and joining
   const words = text.split(' ');              // ['Hello,', 'World!']
   const combined = words.join('-');           // "Hello,-World!"
   ```

#### Practical Examples (20 minutes)

1. **Building a Todo List**
   ```javascript
   // Store todos in an array
   let todos = [];

   // Add a todo
   function addTodo(text) {
       todos.push({
           text: text,
           completed: false,
           created: new Date()
       });
   }

   // Mark a todo as complete
   function completeTodo(index) {
       if (index >= 0 && index < todos.length) {
           todos[index].completed = true;
       }
   }

   // Remove a todo
   function removeTodo(index) {
       todos = todos.filter((_, i) => i !== index);
   }

   // Get all incomplete todos
   function getIncompleteTodos() {
       return todos.filter(todo => !todo.completed);
   }

   // Example usage
   addTodo("Learn JavaScript");
   addTodo("Build a project");
   completeTodo(0);
   console.log(getIncompleteTodos());
   ```

2. **Score Tracker**
   ```javascript
   // Track game scores
   const gameScores = {
       scores: [],
       
       addScore(points) {
           this.scores.push(points);
       },
       
       getHighScore() {
           return Math.max(...this.scores);
       },
       
       getAverageScore() {
           if (this.scores.length === 0) return 0;
           const sum = this.scores.reduce((a, b) => a + b, 0);
           return sum / this.scores.length;
       },
       
       getLastThreeScores() {
           return this.scores.slice(-3);
       }
   };

   // Example usage
   gameScores.addScore(85);
   gameScores.addScore(92);
   gameScores.addScore(78);
   console.log(gameScores.getAverageScore());
   ```

#### Practice Exercise: Contact List (Remaining time)
Build a simple contact management system that can:
1. Add new contacts
2. Find contacts by name
3. Update contact information
4. Remove contacts
5. List all contacts

```javascript
// Start with this structure and expand it
const contactList = {
    contacts: [],
    
    addContact(name, email, phone) {
        // Your code here
    },
    
    findContact(name) {
        // Your code here
    },
    
    updateContact(name, newInfo) {
        // Your code here
    },
    
    removeContact(name) {
        // Your code here
    },
    
    listAllContacts() {
        // Your code here
    }
};
```

### Next Lesson Preview
In Lesson 4, we'll learn about algorithms - step-by-step procedures for solving problems using the JavaScript tools we've learned today!
