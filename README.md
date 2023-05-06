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
