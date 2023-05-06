# JSModulePattern
JavaScript Module Pattern encapsulate functionality private data and expose public data.

```JS
const FriendList = (function() {
  
  let friends = [];
  let MaleFriends = 10;
  let FemaleFriends = 10;
  
  const femaleFriendsList = function( age, city ) {
    
    let friend = friends.push({ age, city });
    console.log(`I have a ${FemaleFriends} female friends age ${age} live at ${city} city ` );
    
  }
 
  const maleFriendsList = function() { 
  
    console.log(`This is a private method!` );
    
  }

  // Expose public data 
  return {
   femaleFriendsList,
   friends 
  }
 
 })();

 FriendList.femaleFriendsList( 18 , 'Saint Bernard');
 // Result: I have a 10 female friends age 18 live at Saint Bernard city 

 // [ THIS IS A PRIVATE METHOD THIS IS NOT EXPOSE TO THE PUBLIC ]
 FriendList.maleFriendsList();
 // Result: caught TypeError: FriendList.maleFriendsList is not a function
 
 // [ THIS IS A PRIVATE METHOD THIS IS NOT EXPOSE TO THE PUBLIC ]
 console.log(FriendList.maleFriendsList());
 // Result: caught TypeError: FriendList.maleFriendsList is not a function 

 /* This property is not expose to the public, 
 simply it exclude to the return value from module pattern or function above 
 This means this property is PRIVATE! */
 console.log(FriendList.FemaleFriends);
 // Result: Undefined 
 ```

```JS
 // Console.log(FriendList);
 // Result 
 {friends: Array(1), femaleFriendsList: ƒ}
  femaleFriendsList : ƒ ( age, city )
    arguments : null
    caller : null
    length : 2
    name : "femaleFriendsList"
 prototype : 
   constructor : ƒ ( age, city )
 [[Prototype]] : 

 Object 
 [[FunctionLocation]] : 
 [[Prototype]] :  ƒ ()
 [[Scopes]] :  Scopes[3]
 friends : Array(1)
   0 :
   age: 18 
   city : "Saint Bernard"
 [[Prototype]] : 
  Object
  constructor : ƒ Object()
  hasOwnProperty : ƒ hasOwnProperty()
  isPrototypeOf : ƒ isPrototypeOf()
  propertyIsEnumerable : ƒ propertyIsEnumerable()
  toLocaleString : ƒ toLocaleString()
  toString : ƒ toString()
  valueOf : ƒ valueOf()
__defineGetter__ :  ƒ __defineGetter__()
__defineSetter__ : ƒ __defineSetter__()
__lookupGetter__ : ƒ __lookupGetter__()
__lookupSetter__ : ƒ __lookupSetter__()
__proto__ : 
(...)
get __proto__ :  ƒ __proto__()
set __proto__ :  ƒ __proto__()
 length : 1
[[Prototype]] : 
Array(0)
[[Prototype]] : 
Object
```

```JS
 // Setter and Getter 
 const FriendList = (function() {
  
  let newFriendName;
  let name;
  let lastName;
  
  // Custom constructor or setter !
  const init = function(x, y) {
  
    name = x;
    lastName = y;

  }
  
  const getNF = function() { 
    return name +' : '+lastName; 
  }

  // Expose public data 
  return {
    init,
    getNF
  }
 
 })();

 FriendList.init('John', 'Doe');
 console.log(FriendList.getNF());
 // Result: John : Doe

 console.log(FriendList);
 // Result
{init: ƒ, getNF: ƒ} getNF :  ƒ ()
  init :  ƒ (x, y)
 [[Prototype]] :  Object
 constructor : ƒ Object()
  assign : ƒ assign()
  create : ƒ create()
  defineProperties : ƒ defineProperties()
  defineProperty :  ƒ defineProperty()
  entries : ƒ entries()
  freeze : ƒ freeze()
  fromEntries : ƒ fromEntries()
  getOwnPropertyDescriptor : ƒ getOwnPropertyDescriptor()
  getOwnPropertyDescriptors : ƒ getOwnPropertyDescriptors()
  getOwnPropertyNames : ƒ getOwnPropertyNames()
  getOwnPropertySymbols : ƒ getOwnPropertySymbols()
  getPrototypeOf : ƒ getPrototypeOf()
  hasOwn : ƒ hasOwn() 
  is : ƒ is() 
  isExtensible : ƒ isExtensible()
  isFrozen : ƒ isFrozen()
  isSealed : ƒ isSealed()
  keys : ƒ keys()
  length :  1
  name : "Object"
  preventExtensions :  ƒ preventExtensions()
 
  prototype :  {constructor: ƒ, __defineGetter__: ƒ, __defineSetter__: ƒ, hasOwnProperty: ƒ, __lookupGetter__: ƒ, …}
  seal : ƒ seal()  
  setPrototypeOf : ƒ setPrototypeOf()
  values : ƒ values()
  arguments : 
  (...)
  caller : 
  (...)
  [[Prototype]] : ƒ ()
[[Scopes]]: 
Scopes[0] 
 hasOwnProperty: ƒ hasOwnProperty()
 isPrototypeOf : ƒ isPrototypeOf()
 propertyIsEnumerable : ƒ propertyIsEnumerable()
 toLocaleString : ƒ toLocaleString()
 toString : ƒ toString()
 valueOf : ƒ valueOf()
__defineGetter__ : ƒ __defineGetter__()
__defineSetter__ : ƒ __defineSetter__()
__lookupGetter__ : ƒ __lookupGetter__()
__lookupSetter__ : ƒ __lookupSetter__()
__proto__ : 
(...)
get __proto__ :  ƒ __proto__()
set __proto__ : ƒ __proto__()
```

