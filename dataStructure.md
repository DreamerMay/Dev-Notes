https://medium.com/siliconwat/data-structures-in-javascript-1b9aed0ea17c

# Data Structure
1. Stacks and Ques - array-like strucures
2. Linked Lists, Tree, and Graphs - strucrures with nodes that keep reference to
   other nodes
3. Hash Tables - depends on hash functions to save and locate data

## Stack
- `call stack` 
- follow `last in first` out portocal
* Eg : pop, push, unshift, shift()

## Queue
- event queue - enqueue `listeners`
- event loop - listen tfor registered `events`
- `listener functins` dequeue and execute only when the call stack is empty



https://medium.com/siliconwat/algorithms-in-javascript-b0bed68f4038

# Algorithm
## Arrays
### Iterations
- `for loop` - iterate through array indexes
- `while , do while` - numbers ofiteration until a condition is meet
- `for in` and `for of` loops 
- `break` to breka out
- `continue` to skip
- `indexOf, lastIndexOf, includes, fill, and join`,
- provide call back function to : `findIndex, find, filter, forEach, map, some,
  every and reduce`

* Recursive
if num is < 2 show 1, else show function
const factorial = number => {
  return number < 2 ? 1 : number * factorial(number - 1);
}