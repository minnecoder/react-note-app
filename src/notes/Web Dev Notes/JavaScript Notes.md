# JavaScript Notes

**<u>Escape Sequences in Strings</u>**

**Code  Output**

`\'`   single quote 

`\"`  double quote 

`\\`  backslash 

`\n` newline 

`\r` carriage return 

`\t` tab 

`\b` backspace 

`\f` form feed 

## Array methods

`.push()` adds something to the end of an array 

`.pop()` removes the last item of an array 

`.shift()` removes the first item in an array 

`.unshift()` adds an item to the beginning of an array 

A variable that is used with var are created in the global scope 

i.e. `for(i=0;i<array.length;i++)`  IS NOT GOOD TO DO!! 

To create a random number between 0 and another number we use. Where X is the number the max limit of the random number `Math.floor(Math.random() * 10);` 

To round down a number to the nearest whole number - `Math.floor()` 


The following code will make a random number between 2 numbers that are passed into it 

`Math.floor(Math.random()* (myMax - myMin+1)) + myMin;` 

## JS Getters and Setters Example 

``` js
var Bike = function() { 

  var gear = 1; 

  this.setGear = function(newGear){ 
    gear = newGear; 
  }; 

  this.getGear = function(){ 
    return gear; 
  }; 
}; 
```

## Iterate over an array with map 

The map method will iterate through every element of the array, creating a new array with values that have been modified by the callback function, and return it. Note that it does not modify the original array. 

``` js
var oldArray = [1,2,3,4,5]; 
var newArray = oldArray.map(function(val){ 
  return val += 3; 
}); 
```

The reduce function 

The array method reduce is used to iterate through an array and condense it into one value. 

To use reduce you pass in a callback whose arguments are an accumulator (in this case, previousVal) and the current value (currentVal). 

The accumulator is like a total that reduce keeps track of after each operation. The current value is just the next element in the array you're iterating through. 

reduce has an optional second argument which can be used to set the initial value of the accumulator. If no initial value is specified it will be the first array element and currentVal will start with the second array element. 

``` js
var array = [4,5,6,7,8]; 
var singleVal = 0; 

singleVal = array.reduce(function(singleVal,currentVal){ 
  return singleVal + currentVal; 
}); 
```

## The filter method 

The filter method is used to iterate through an array and filter out elements where a given condition is not true. 

filter is passed a callback function which takes the current value as an argument. 

Any array element for which the callback returns true will be kept and elements that return false will be filtered out. 

``` js
var oldArray = [1,2,3,4,5,6,7,8,9,10]; 
var newArray = oldArray.filter(function(val){ 
  return val < 6; 
}); 
```

## The sort function 

This is a function that will sort an array. Returning a-b will sort small to large and returning b-a will sort from large to small 

``` js
var array = [1, 12, 21, 2]; 
array.sort(function(a,b){ 
  return b-a; 
}); 
```

## Array Slice 

var args = Array.prototype.slice.call(arguments); 

This will take an array like object i.e. [[1,2,3,4,5],7,8] and remove the array from this array to the arr variable. The arguments will be placed in the args variable. 

Example 

``` js
function destroyer(arr){ 
  var args = Array.prototype.slice.call(arguments); 
  for (var i=0;i<arr.length;i++){ 
    for(var j=0;j<args.length;j++){ 
      if(arr[i] === args[j]){ 
      delete arr[i]; 
      } 
    } 
  } 
return arr.filter(Boolean) ; 
} 

destroyer([1, 2, 3, 1, 2, 3], 2, 3); 
```

# ES6

## String/Template Literals

String literals make the task of concating multiple words into a sentence easier. Before ES6 the way that this would be done is:

``` js
let fName = "Sean";
let lName = "Parkin";
const fullName = fName + " " + lName;
```

But with ES6 and string literals the fullName variable can be set the following way:
``` js
let fullName = `${fName} ${lName}`; 
```

- When using string literals, all of the veriables need to use the backtick instead of single or double quotes 

Another that is able to do with string literals is that if there is a need to make a sentence appear on multiple lines, all that needs to make the change within the variable like below:

``` js
let fullName = `${fName} 
${lName}`; 
```

## Destructuring Objects

If there is an object that is being used within a program like the one below

``` js
const personalInformation = {
  firstName = "Sean",
  lastName = "Parkin",
  city = "Cottage Grove",
  state = "Minnesota"
};
```

Normally, one piece of the object would be accessed by typing `personalInformation.firstName;` but with the ability to destruct objects, this can be changed. The code below will show object destructuring

``` js
const {firstName, lastName} = personalInformation;
```

After this all that would have to called is the `firstName` or `lastName` varibles. There is also the option to take this one step further and give a new name to the variables like is shown below

``` js
const {firstName: fn, lastName: ln} = personalInformation;
```

Now all that we need to be called is the variables `fn` or `ln`

## Destructuring Arrays

Destructuring arrays is a lot like what can be done with objects. If we are given a array like 

``` js
let name = ["Billy","Bob","Burns"];
```

Now to destructure this array we would add the names for each element of the array before the equals like below

``` js
let [firstName, middleName, lastName] = ["Billy","Bob","Burns"];
```

If there was a need to change one of the elements in an array, this can be done by setting that element to something like below

``` js
lastName = "Roberts";
```

## For Of Loop

When there is an array where the goal is to total up all of the items in an array like below

``` js
let incomes = [62000,67000,75000];
let total = 0;
```

The for of loop can be ran to get the total of all of the elements. An example of a for of loop is below

``` js
for (const income of incomes) {
  total += income;
}
```

A for of loop can be done on anything that is iterable. Another example is a for of loop can be done on a string.

- the for of loop can not be used to modify the data within the iterable object


