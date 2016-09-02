# ES6-Demo
Arrow functions, Default Parameters, Shortening Properties and Methods


**************************************

## Default Params

Default function parameters allow formal parameters to be initialized with default values if no value or undefined is passed.

### Passing undefined

In the second call here, even if the second argument is set explicitly to undefined (though not null) when calling, the value of the color argument is the default one.

'''javascript
function setBackgroundColor(element, color = 'rosybrown') {
  element.style.backgroundColor = color;
}

setBackgroundColor(someDiv);            // color set to 'rosybrown'
setBackgroundColor(someDiv, undefined); // color set to 'rosybrown' too
setBackgroundColor(someDiv, 'blue');    // color set to 'blue'
'''

### Evaluated at call time

The default argument gets evaluated at call time, so unlike e.g. in Python, a new object is created each time the function is called.

'''javascript
function append(value, array = []) {
  array.push(value);
  return array;
}

append(1); //[1]
append(2); //[2], not [1, 2]
'''
