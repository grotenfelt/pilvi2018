# pilvi2018
Excercise 1:

1. Fix the code so it prints out the alphabet A-Z in the console.

2. Cannot:
	- Have **any** global variables at all
	- Delete or combine any function declarations
	- Create any new functions (except IIFEs -- hint!)
	- Rearrange the order of declarations

3. Can/must:
	- Declare extra variables (as long as they're not global)
	- Modify (in-place) function declaration/initialization
	- Add/remove statements/expressions (IIFEs, return, params, etc)
	- Make the fewest changes possible
  
  Excercise 2: 
  1. In this exercise, you will modify existing code for a simple note taking app. You will not add/remove functionality per se, but instead organize the code into a more proper module design and make it more flexible/reusable.

2. Using what you learned about closure and the module pattern, modify your previous code to wrap all the functionality up into a simple object (call it "NotesManager" or something appropriate), with a simple API, consisting of:
  - an `init()` method, which you will call from the outside when jQuery's `document.ready` event is fired, and pass in the data from the "database".
  - a public method to add in notes "in bulk" after retrieval from the "database". hint: this can/should be called **before** you run the "init" method.

3. Make sure you have a "private" storage of the `notes` data list inside your module. Why is it a good idea to keep the data "private" inside the module?

4. What do you notice about the structure of this code as it relates to the DOM access and the usage of jQuery? Would it make sense to "generalize" this code so that the module didn't have hardcoded into it the various DOM elements it would operate on? Explore how you would modify the code in this fashion. What are the benefits and tradeoffs?

Excercise 3:
1. In this exercise, you will revisit your work from exercise 2 (the note taking app). You will need to copy in your fixed code from "ex2.js" (or "ex2-fixed.js") into the "ex3.js" file, as your starting point.

2. Using what you learned about `prototype` to construct an object instance, modify your previous code to not use module/encapsulation pattern, but instead create a `this` based object. Your public API should stay the same from exercise 2 (although everything will be public now). The main difference will be that you have a constructor function called "NotesManager" (or whatever), and then you will need to create an instance of that object, and can call it something useful, like "myNotes".

3. Pay particular attention to your event handlers and what we learned about how `this` gets reassigned. What have we learned about how to fix that?

4. Because a `this` based object does not have "private" (encapsulated) data, your data will be publicly available on the instance, as well as all your helper methods. How does this change the maintainability and robustness of your code and implementation?

5. What benefits do you see to structuring your code this (`prototype`-based) way? What are the tradeoffs?

Excercise 4: 
1. In this exercise, you will practice what you learned about creating an object that "inherits from" (aka, "delegates its behavior to") another object. The "ex4.js" file provides you a simple definition for a `Widget` object, as well as the start of a `Button` object.

2. Finish out the definition of the `Button` object:
  - define `Button` so that it "inherits from" (aka "delegates to") `Widget`.
  - the Button constructor should have a `width`, `height`, and `label` parameter passed to it.
  - uncomment the Button's `render` and `onClick` function shells, and correctly define them.
  - make the `onClick` handler print with the console "Button ___ clicked!", where "___" is that particular button's label

3. Uncomment the `$(document).ready(..)` handler at the bottom of the file, and correct the instantiations of the two button objects, so that they create buttons with 2 different sizes and labels.

4. BONUS: The code given to you is clearly in the "old style" function/constructor/new style of defining objects and "inheritance". Using what we learned about OLOO-style code with `Object.create()`, rewrite the code using behavior delegation and OLOO-style. Hint: don't think of parent/child, think of two peer objects, one who delegates to the other.

Excercise 5:
1. This exercise calls for you to write some async flow-control code to more properly handle the provided callback mess as shown in "ex5.js".

2. Expected behavior:
	- Request all 3 files at the same time (in "parallel").
	- Render them ASAP (don't just blindly wait for all to finish loading)
	- BUT, render them in proper (obvious) order: "file1", "file2", "file3".
	- After all 3 are done, output "Complete!".

3. Use either native promises, the *asynquence* lib (provided), or your own favorite async/promises library/utility.
