# ES6-Demo
Arrow functions, Default Parameters, Shortening Properties and Methods


Arrow Functions:


``` javascript
var add = (a,b) => a + b;

```
don't have to use function keyword, single line statement can have implicit return


without es6:
``` javascript
var numbers = [2,3,4,5,6,7]
var doubled = numbers.map(function(n){
  return n*2;
  })
```

with ES6:
```
var doubled = numbers.map(n => n * 2);
```
functions with a single parameter do not need parenthesis around them as seen above.

this keyword
``` javascript
var band = {
  name = "brutal kick to the face",
  hype: function(){
    console.log('${this.name}' is an above average musical experience!);
  }
}

var band = {
  name = "brutal kick to the face",
  hype: () => {
    console.log('${this.name}' is an above average musical experience that lexical scope is preventing you from hearing about);
  }
}
```
this will not work: error cannot read property name of undefined.

arrow functions have "lexical scope", informally referred to as "parent scope"

in this case, the "this" keyword is not bound to the person object, but whatever it was bound to before that.

``` javascript
var person = {
  name: 'Andy',
  hobbies:['High Levels','facial hair','bringing back that's dope'],
  showHobbies: function(){
    this.hobbies.forEach(function(hobby){
      console.log('${this.name} likes ${hobby}')
      })
  }
}
person.showHobbies();
```

this code block does not work, because the value of this changes from the first use to the second. However, with the super awesome ES6 lexical scope, this will stay bound to the original parent value

```
var person = {
  name: 'Andy',
  hobbies:['High Levels','facial hair','bringing back that's dope']
  showHobbies: function(){
    this.hobbies.forEach((hobby)=> {
      console.log('${this.name} likes ${hobby}')
      })
  }
}
person.showHobbies();
```
