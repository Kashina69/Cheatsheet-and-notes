# Map, Filter, Reduce
```js
const array = [1,2,3,4,5,6]

let newArrayWithMaP = array.map((value, index, array)=>{
    return value + 1
})
console.log(newArrayWithMaP)
// map makes a new array by performing a certain function on the array and can take 3 argument number index and array
```
```js
let newArrayWithFilter = array.filter((value, index, array)=>{
    return value > 1
})
console.log(newArrayWithFilter)
// filter makes a new array by performing a filtering the array and can't be done with loops and also can take 3 argument number index and array
```
```js
let newArrayWithReduce = array.reduce((total, currentValue, currentIndex, arr)=>{
    return total - currentValue
},initialValue)
console.log(newArrayWithReduce);
// Reduce makes a new array by take 2 value which is the first and the second index values and then perform a calculation on it like in this case substrate and then continue it on the new ones
```

# Memory in Js
```js
// Stack (Primitive), Heap (Non-Primitive)
// stack have copy 
// heap have reference 
```

# Execution context
- ## global execution context
- ## functional execution context
- ## eval execution context

```js

```
# Lexical scoping 

```js
// Is that outer function variables are accesable to the inner function but not vice versa
// And the sibling inner functions also can't use the other sibling variable
```

# Closure

```js
function makeFunc() {
const name = "Mozilla";
function displayName() {
console.log(name);
}
return displayName;
}
I
const myFunc = makeFunc();
myFunc();

// It is about if we return a reference of a function in a function so it won't just gona give the executional contex of the returned fuction but the lexical scope of the function which means all the variable which it uses from its parent function  
```

# Object Oriented Programming 

- ## Constructor Function 
```js
// new keyword use 


```

- ## Classes
```js
 class User {
    constructor(username, email, password){
        this.username = username;
        this.email = email;
        this.password = password;
    }
    encryptPassword(){
        return `${this.password} abc`
    }
 }

 const chai = new User("prince", "princerawatemail","password123")
 ```
- ## 
- ## 

# IIFE

```js
(()=>{

})();

semicolen is necessary other vice it will give error
```










# Good to know 

- ## how return works in functions
```js
// if you use {} in forEach or map , filter, reduce or in any function then you have to use return keyword but if you are not using {} then it will automatically return
```
- ## chained functions
```js
// you can also do array1.map().map().filter()
// this is called function channing which passes the new value to the next function till the last one and then return the final value and stores it 
``` 
- ## implesit scope
```js
// its nothing but the scope created when you are doing something without {}

```


