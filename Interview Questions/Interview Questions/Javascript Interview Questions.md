# Javascript Interview Questions

Created By: Chris Trinh
Last Edited: Jan 17, 2020 3:22 PM

- What is the difference between `null` and `undefined`?
    - Undefined means the variable is not defined. It is not a constant or keyword, its a type with exactly one value. If you assign a value to it, it does not change the type
    - Null means empty or non-existent value. Its a primitive value  and you can assign null to any variable.
    - null == undefined
- What is the difference between `==` and `===`?
    - == will not check types and === will check if both sides are the same type.
        - does implicit conversion under the hood
    - === compares types and values
        - if both sides are not the same type, answer is always false
    - When comparing objects, both variables must reference the same object
- How to compare two objects in JS?
    - Primitives (strings and numbers) are compared by values
    - Objects (arrays and dates) are compared by reference (same location in memory)
    - Check same value for property, and then check for same value

- True Lies (Tricky True False Questions)
    - Is 'false' false?
        - No, string length greater than 0. If its empty, then its false
    - 'Is '    ' false?
        - No because of whitespace
    - Is {} false?
        - True because objects can't be falsey
    - Is [ ] false?
        - No, its truthy because empty arrays are child objects
    - is new String(' ') false?
        - Creates a string object so its truthy
    - new Boolean(false) false?
        - Truthy because it creates an instance of the boolean object.
- If `[ ] is true`, then `[ ] === true` ?
    - This will convert it to "" == 1 so it will be false. Left and right side of the equality are two different types and JS can't compare directly
- ES5, How would you right a method on an instance of date which will give you the next day?
    - Create a method on the prototype of the date object, to get access to the current day, you have to use 'this'.
- How do you use `this`
    1. Call: passes in the arguments after the first context as comma list elements
    2. Apply: passes in the arguments after the context as an array of elements.
    3. Bind has two invocations than takes the context and argument, or context in one function and argument in the other; (context)(args)
- Rapid Questions!
    - What is `typeof [ ]'`
        - Object since arrays are derived from the objects
        - Checking array uses `Array.isArray(arr)`
    - What is `typeof arguments` ?
        - Objects
    - What is `2 + true`?
        - 3, plus operator and a boolean will convert it to a number.
        - `true === 1`
    - What is `'6' + 9` ?
        - 69, If one of the operands of the plus opertators are a string, then it will convert the other number to a string then concatenate
        - `'2'+true === '2true'`
- What is hoisting?
    - Where variables declared are 'hoisted' at the top of the browser and can be sued
    - This can slow down the loading of the browser if theres a lot of javascript as it stores the code globally
- What is the difference between a named function and an anonymous function?
    - Named functions are functions with names that are always available in the browser
    - Anonymous functions require being set equal to a variable to be called?
- What is the benefit of a anonymous function?
    - Since the anonymous function is not hoisted top the top, it doesn't get stored in memory and therefore doesn't store the function body until its called by the variable, speeding up the web app.
- What is a closure?
    - Function that has access to a private variable

        function Person(pName) { 
        	const _name = pName;
        	function getName() { 
        		return _name;
        	}
        }
        
        // let me = new Person('chris')
        // me.name = undefined;
        // me.getName() = 'chris'