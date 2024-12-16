## Lesson 04

### Algorithms and Problem Solving with JavaScript

#### Introduction (5 minutes)
Now that we understand JavaScript's building blocks, let's learn how to solve problems step by step using algorithms. We'll combine our Boolean logic from Lesson 2 with our JavaScript knowledge from Lesson 3 to create practical solutions.

#### What is an Algorithm? (10 minutes)

Think of an algorithm as a recipe - a set of steps to solve a problem. Let's start with a simple example:

```javascript
// Making a sandwich algorithm
function makeSandwich(ingredients) {
    // 1. Check if we have bread
    if (!ingredients.includes('bread')) {
        return "Can't make a sandwich without bread!";
    }

    // 2. Find our fillings
    const fillings = ingredients.filter(item => item !== 'bread');
    
    // 3. Describe our sandwich
    return `A sandwich with ${fillings.join(' and ')}`;
}

// Using the algorithm
const ingredients = ['bread', 'cheese', 'tomato', 'lettuce'];
console.log(makeSandwich(ingredients));
// Output: "A sandwich with cheese and tomato and lettuce"
```

#### Basic Algorithm Patterns (15 minutes)

1. **Sequential Operations**
   ```javascript
   function calculateTotal(prices) {
       let total = 0;                    // Initialize
       prices.forEach(price => {         // Process each item
           total += price;               // Add to running total
       });
       return total;                     // Return result
   }

   const prices = [10, 20, 30];
   console.log(calculateTotal(prices));  // 60
   ```

2. **Conditional Logic**
   ```javascript
   function canWatchMovie(age, movieRating) {
       // Age checks for different ratings
       if (movieRating === 'G') {
           return true;
       }
       if (movieRating === 'PG-13' && age >= 13) {
           return true;
       }
       if (movieRating === 'R' && age >= 17) {
           return true;
       }
       return false;
   }

   console.log(canWatchMovie(15, 'PG-13'));  // true
   console.log(canWatchMovie(15, 'R'));      // false
   ```

3. **Repetition (Loops)**
   ```javascript
   function findLargestNumber(numbers) {
       let largest = numbers[0];
       
       for (let number of numbers) {
           if (number > largest) {
               largest = number;
           }
       }
       
       return largest;
   }

   // Using array methods (another way)
   function findLargestNumberModern(numbers) {
       return Math.max(...numbers);
   }
   ```

#### Common Algorithm Examples (20 minutes)

1. **Search Algorithms**
   ```javascript
   // Linear Search
   function findItem(items, target) {
       for (let i = 0; i < items.length; i++) {
           if (items[i] === target) {
               return i;  // Return position if found
           }
       }
       return -1;  // Return -1 if not found
   }

   // Binary Search (for sorted arrays)
   function findItemFaster(sortedItems, target) {
       let start = 0;
       let end = sortedItems.length - 1;

       while (start <= end) {
           let middle = Math.floor((start + end) / 2);
           
           if (sortedItems[middle] === target) {
               return middle;          // Found it!
           }
           if (sortedItems[middle] < target) {
               start = middle + 1;     // Look in right half
           } else {
               end = middle - 1;       // Look in left half
           }
       }
       return -1;  // Not found
   }

   // Example usage
   const numbers = [1, 3, 5, 7, 9, 11, 13, 15];
   console.log(findItemFaster(numbers, 7));  // 3
   console.log(findItemFaster(numbers, 10)); // -1
   ```

2. **Sorting Arrays**
   ```javascript
   // Bubble Sort
   function sortNumbers(numbers) {
       const array = [...numbers];  // Create a copy
       
       for (let i = 0; i < array.length; i++) {
           for (let j = 0; j < array.length - i - 1; j++) {
               if (array[j] > array[j + 1]) {
                   // Swap elements
                   [array[j], array[j + 1]] = [array[j + 1], array[j]];
               }
           }
       }
       
       return array;
   }

   // Using built-in sort (much easier!)
   function sortNumbersEasy(numbers) {
       return [...numbers].sort((a, b) => a - b);
   }
   ```

3. **Filtering and Transformation**
   ```javascript
   // Working with a list of products
   const products = [
       { name: 'Apple', price: 1.99, category: 'Fruit' },
       { name: 'Bread', price: 2.49, category: 'Bakery' },
       { name: 'Milk', price: 3.99, category: 'Dairy' },
       { name: 'Orange', price: 0.99, category: 'Fruit' }
   ];

   function findCheapProducts(products, maxPrice) {
       return products
           .filter(product => product.price <= maxPrice)
           .map(product => product.name);
   }

   function findProductsByCategory(products, category) {
       return products
           .filter(product => product.category === category)
           .map(product => ({
               name: product.name,
               price: product.price
           }));
   }

   console.log(findCheapProducts(products, 2.00));
   console.log(findProductsByCategory(products, 'Fruit'));
   ```

#### Practical Problem Solving (20 minutes)

Let's solve a real-world problem: Building a Shopping Cart

```javascript
const shoppingCart = {
    items: [],
    
    addItem(name, price, quantity = 1) {
        // Check if item already exists
        const existingItem = this.items.find(item => item.name === name);
        
        if (existingItem) {
            existingItem.quantity += quantity;
        } else {
            this.items.push({ name, price, quantity });
        }
    },
    
    removeItem(name) {
        this.items = this.items.filter(item => item.name !== name);
    },
    
    updateQuantity(name, quantity) {
        const item = this.items.find(item => item.name === name);
        if (item) {
            item.quantity = quantity;
        }
    },
    
    getTotal() {
        return this.items.reduce((total, item) => {
            return total + (item.price * item.quantity);
        }, 0);
    },
    
    getItemCount() {
        return this.items.reduce((count, item) => {
            return count + item.quantity;
        }, 0);
    },
    
    clearCart() {
        this.items = [];
    },
    
    getSummary() {
        return this.items.map(item => 
            `${item.quantity}x ${item.name} at $${item.price} each`
        );
    }
};

// Example usage
shoppingCart.addItem('Apple', 0.99, 3);
shoppingCart.addItem('Bread', 2.49, 1);
shoppingCart.addItem('Apple', 0.99, 2);  // Adds to existing apples
console.log(shoppingCart.getSummary());
console.log(`Total: $${shoppingCart.getTotal()}`);
```

#### Exercise: Build a Task Scheduler (Remaining time)
Create a program that can:
1. Add tasks with priorities and due dates
2. List all tasks
3. List tasks due today
4. Mark tasks as complete
5. Remove old tasks

Start with this structure:
```javascript
const taskScheduler = {
    tasks: [],
    
    addTask(title, priority, dueDate) {
        // Your code here
    },
    
    getTasksDueToday() {
        // Your code here
    },
    
    markTaskComplete(taskId) {
        // Your code here
    },
    
    removeOldTasks() {
        // Your code here
    }
};
```

### Key Takeaways
- Algorithms are step-by-step solutions to problems
- Break big problems into smaller, manageable pieces
- Start simple and add complexity as needed
- Use built-in JavaScript methods when possible
- Test your solution with different inputs

### Next Lesson Preview
We'll learn about working with the DOM (Document Object Model) to make our JavaScript interact with web pages!
