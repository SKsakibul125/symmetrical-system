--- title: Arrays slug: Learn/JavaScript/First_steps/Arrays tags: - Arrays - Article - Beginner - CodingScripting - JavaScript - Join - Learn - Pop - Push - l10n:priority - shift - split - unshift ---

{{LearnSidebar}}

{{PreviousMenuNext("Learn/JavaScript/First\_steps/Useful\_string\_methods", "Learn/JavaScript/First\_steps/Silly\_story\_generator", "Learn/JavaScript/First\_steps")}}

In the final article of this module, we'll look at arrays — a neat way of storing a list of data items under a single variable name. Here we look at why this is useful, then explore how to create an array, retrieve, add, and remove items stored in an array, and more besides.

<table><tbody><tr class="odd"><td>Prerequisites:</td><td>Basic computer literacy, a basic understanding of HTML and CSS, an understanding of what JavaScript is.</td></tr><tr class="even"><td>Objective:</td><td>To understand what arrays are and how to manipulate them in JavaScript.</td></tr></tbody></table>

## What is an array?

Arrays are generally described as "list-like objects"; they are basically single objects that contain multiple values stored in a list. Array objects can be stored in variables and dealt with in much the same way as any other type of value, the difference being that we can access each value inside the list individually, and do super useful and efficient things with the list, like loop through it and do the same thing to every value. Maybe we've got a series of product items and their prices stored in an array, and we want to loop through them all and print them out on an invoice, while totaling all the prices together and printing out the total price at the bottom.

If we didn't have arrays, we'd have to store every item in a separate variable, then call the code that does the printing and adding separately for each item. This would be much longer to write out, less efficient, and more error-prone. If we had 10 items to add to the invoice it would already be annoying, but what about 100 items, or 1000? We'll return to this example later on in the article.

As in previous articles, let's learn about the real basics of arrays by entering some examples into [browser developer console](/en-US/docs/Learn/Common_questions/What_are_browser_developer_tools).

### Creating arrays

Arrays consist of square brackets and elements that are separated by commas.

1.  Suppose we want to store a shopping list in an array. Paste the following code into the console:

        let shopping = ['bread', 'milk', 'cheese', 'hummus', 'noodles'];
        shopping;

2.  In the above example, each element is a string, but in an array we can store various data types — strings, numbers, objects, and even other arrays. We can also mix data types in a single array — we do not have to limit ourselves to storing only numbers in one array, and in another only strings. For example:

        let sequence = [1, 1, 2, 3, 5, 8, 13];
        let random = ['tree', 795, [0, 1, 2]];

3.  Before proceeding, create a few example arrays.

### Accessing and modifying array items

You can then access individual items in the array using bracket notation, in the same way that you [accessed the letters in a string](/en-US/docs/Learn/JavaScript/First_steps/Useful_string_methods#retrieving_a_specific_string_character).

1.  Enter the following into your console:

        shopping[0];
        // returns "bread"

2.  You can also modify an item in an array by giving a single array item a new value. Try this:

        shopping[0] = 'tahini';
        shopping;
        // shopping will now return [ "tahini", "milk", "cheese", "hummus", "noodles" ]

    **Note**: We've said it before, but just as a reminder — computers start counting from 0!

3.  Note that an array inside an array is called a multidimensional array. You can access an item inside an array that is itself inside another array by chaining two sets of square brackets together. For example, to access one of the items inside the array that is the third item inside the `random` array (see previous section), we could do something like this:

        random[2][2];

4.  Try making some more modifications to your array examples before moving on. Play around a bit, and see what works and what doesn't.

### Finding the length of an array

You can find out the length of an array (how many items are in it) in exactly the same way as you find out the length (in characters) of a string — by using the {{jsxref("Array.prototype.length","length")}} property. Try the following:

    shopping.length;
    // should return 5

This has other uses, but it is most commonly used to tell a loop to keep going until it has looped through all the items in an array. So for example:

    let sequence = [1, 1, 2, 3, 5, 8, 13];
    for (let i = 0; i < sequence.length; i++) {
      console.log(sequence[i]);
    }

You'll learn about loops properly later on (in our [Looping code](/en-US/docs/Learn/JavaScript/Building_blocks/Looping_code) article), but briefly, this code is saying:

1.  Start looping at item number 0 in the array.
2.  Stop looping at the item number equal to the length of the array. This works for an array of any length, but in this case it stops looping at item number 7 (this is good, as the last item — which we want the loop to include — is item 6).
3.  For each item, print it out to the browser console with `console.log()`.

## Some useful array methods

In this section we'll look at some rather useful array-related methods that allow us to split strings into array items and vice versa, and add new items into arrays.

### Converting between strings and arrays

Often you'll be presented with some raw data contained in a big long string, and you might want to separate the useful items out into a more useful form and then do things to them, like display them in a data table. To do this, we can use the {{jsxref("String.prototype.split()","split()")}} method. In its simplest form, this takes a single parameter, the character you want to separate the string at, and returns the substrings between the separator as items in an array.

**Note**: Okay, this is technically a string method, not an array method, but we've put it in with arrays as it goes well here.

1.  Let's play with this, to see how it works. First, create a string in your console:

        let myData = 'Manchester,London,Liverpool,Birmingham,Leeds,Carlisle';

2.  Now let's split it at each comma:

        let myArray = myData.split(',');
        myArray;

3.  Finally, try finding the length of your new array, and retrieving some items from it:

        myArray.length;
        myArray[0]; // the first item in the array
        myArray[1]; // the second item in the array
        myArray[myArray.length-1]; // the last item in the array

4.  You can also go the opposite way using the {{jsxref("Array.prototype.join()","join()")}} method. Try the following:

        let myNewString = myArray.join(',');
        myNewString;

5.  Another way of converting an array to a string is to use the {{jsxref("Array.prototype.toString()","toString()")}} method. `toString()` is arguably simpler than `join()` as it doesn't take a parameter, but more limiting. With `join()` you can specify different separators, whereas `toString()` always uses a comma. (Try running Step 4 with a different character than a comma.)

        let dogNames = ['Rocket','Flash','Bella','Slugger'];
        dogNames.toString(); // Rocket,Flash,Bella,Slugger

### Adding and removing array items

We've not yet covered adding and removing array items — let us look at this now. We'll use the `myArray` array we ended up with in the last section. If you've not already followed that section, create the array first in your console:

    let myArray = ['Manchester', 'London', 'Liverpool', 'Birmingham', 'Leeds', 'Carlisle'];

First of all, to add or remove an item at the end of an array we can use {{jsxref("Array.prototype.push()","push()")}} and {{jsxref("Array.prototype.pop()","pop()")}} respectively.

1.  Let's use `push()` first — note that you need to include one or more items that you want to add to the end of your array. Try this:

        myArray.push('Cardiff');
        myArray;
        myArray.push('Bradford', 'Brighton');
        myArray;

2.  The new length of the array is returned when the method call completes. If you wanted to store the new array length in a variable, you could do something like this:

        let newLength = myArray.push('Bristol');
        myArray;
        newLength;

3.  Removing the last item from the array is as simple as running `pop()` on it. Try this:

        myArray.pop();

4.  The item that was removed is returned when the method call completes. To save that item in a new variable, you could do this:

        let removedItem = myArray.pop();
        myArray;
        removedItem;

{{jsxref("Array.prototype.unshift()","unshift()")}} and {{jsxref("Array.prototype.shift()","shift()")}} work in exactly the same way as `push()` and `pop()`, respectively, except that they work on the beginning of the array, not the end.

1.  First `unshift()` — try the following commands:

        myArray.unshift('Edinburgh');
        myArray;

2.  Now `shift()`; try these!

        let removedItem = myArray.shift();
        myArray;
        removedItem;

## Active learning: Printing those products!

Let's return to the example we described earlier — printing out product names and prices on an invoice, then totaling the prices and printing them at the bottom. In the editable example below there are comments containing numbers — each of these marks a place where you have to add something to the code. They are as follows:

1.  Below the `// number 1` comment are a number of strings, each one containing a product name and price separated by a colon. We'd like you to turn this into an array and store it in an array called `products`.
2.  On the same line as the `// number 2` comment is the beginning of a for loop. In this line we currently have `i <= 0`, which is a conditional test that causes the [for loop](/en-US/docs/Learn/JavaScript/First_steps/A_first_splash#loops) to only run once, because it is saying "stop when `i` is no longer less than or equal to 0", and `i` starts at 0. We'd like you to replace this with a conditional test that stops the loop when `i` is no longer less than the `products` array's length.
3.  Just below the `// number 3` comment we want you to write a line of code that splits the current array item (`name:price`) into two separate items, one containing just the name and one containing just the price. If you are not sure how to do this, consult the [Useful string methods](/en-US/docs/Learn/JavaScript/First_steps/Useful_string_methods) article for some help, or even better, look at the {{anch("Converting between strings and arrays")}} section of this article.
4.  As part of the above line of code, you'll also want to convert the price from a string to a number. If you can't remember how to do this, check out the [first strings article](/en-US/docs/Learn/JavaScript/First_steps/Strings#numbers_versus_strings).
5.  There is a variable called `total` that is created and given a value of 0 at the top of the code. Inside the loop (below `// number 4`) we want you to add a line that adds the current item price to that total in each iteration of the loop, so that at the end of the code the correct total is printed onto the invoice. You might need an [assignment operator](/en-US/docs/Learn/JavaScript/First_steps/Math#assignment_operators) to do this.
6.  We want you to change the line just below `// number 5` so that the `itemText` variable is made equal to "current item name — $current item price", for example "Shoes — $23.99" in each case, so the correct information for each item is printed on the invoice. This is just simple string concatenation, which should be familiar to you.

###### Playable code

    <h2>Live output</h2>

    <div class="output" style="min-height: 150px;">

    <ul>

    </ul>

    <p></p>

    </div>

    <h2>Editable code</h2>

    <p class="a11y-label">Press Esc to move focus away from the code area (Tab inserts a tab character).</p>

    <textarea id="code" class="playable-code" style="height: 410px;width: 95%">
    const list = document.querySelector('.output ul');
    const totalBox = document.querySelector('.output p');
    let total = 0;
    list.innerHTML = '';
    totalBox.textContent = '';
    // number 1
                    'Underpants:6.99'
                    'Socks:5.99'
                    'T-shirt:14.99'
                    'Trousers:31.99'
                    'Shoes:23.99';

    for (let i = 0; i <= 0; i++) { // number 2
      // number 3

      // number 4

      // number 5
      let itemText = 0;

      const listItem = document.createElement('li');
      listItem.textContent = itemText;
      list.appendChild(listItem);
    }

    totalBox.textContent = 'Total: $' + total.toFixed(2);
    </textarea>

    <div class="playable-buttons">
      <input id="reset" type="button" value="Reset">
      <input id="solution" type="button" value="Show solution">
    </div>

    const textarea = document.getElementById('code');
    const reset = document.getElementById('reset');
    const solution = document.getElementById('solution');
    let code = textarea.value;
    let userEntry = textarea.value;

    function updateCode() {
      eval(textarea.value);
    }

    reset.addEventListener('click', function() {
      textarea.value = code;
      userEntry = textarea.value;
      solutionEntry = jsSolution;
      solution.value = 'Show solution';
      updateCode();
    });

    solution.addEventListener('click', function() {
      if(solution.value === 'Show solution') {
        textarea.value = solutionEntry;
        solution.value = 'Hide solution';
      } else {
        textarea.value = userEntry;
        solution.value = 'Show solution';
      }
      updateCode();
    });

    const jsSolution = 'const list = document.querySelector(\'.output ul\');\nconst totalBox = document.querySelector(\'.output p\');\nlet total = 0;\nlist.innerHTML = \'\';\ntotalBox.textContent = \'\';\n\nlet products = [\'Underpants:6.99\',\n  \'Socks:5.99\',\n  \'T-shirt:14.99\',\n  \'Trousers:31.99\',\n  \'Shoes:23.99\'];\n\nfor(let i = 0; i < products.length; i++) {\n  let subArray = products[i].split(\':\');\n  let name = subArray[0];\n  let price = Number(subArray[1]);\n  total += price;\n  let itemText = name + \' — $\' + price;\n\n  let listItem = document.createElement(\'li\');\n  listItem.textContent = itemText;\n  list.appendChild(listItem);\n}\n\ntotalBox.textContent = \'Total: $\' + total.toFixed(2);';
    let solutionEntry = jsSolution;

    textarea.addEventListener('input', updateCode);
    window.addEventListener('load', updateCode);

    // stop tab key tabbing out of textarea and
    // make it write a tab at the caret position instead

    textarea.onkeydown = function(e){
      if (e.keyCode === 9) {
        e.preventDefault();
        insertAtCaret('\t');
      }

      if (e.keyCode === 27) {
        textarea.blur();
      }
    };

    function insertAtCaret(text) {
      const scrollPos = textarea.scrollTop;
      let caretPos = textarea.selectionStart;
      const front = (textarea.value).substring(0, caretPos);
      const back = (textarea.value).substring(textarea.selectionEnd, textarea.value.length);

      textarea.value = front + text + back;
      caretPos = caretPos + text.length;
      textarea.selectionStart = caretPos;
      textarea.selectionEnd = caretPos;
      textarea.focus();
      textarea.scrollTop = scrollPos;
    }

    // Update the saved userCode every time the user updates the text area code

    textarea.onkeyup = function(){
      // We only want to save the state when the user code is being shown,
      // not the solution, so that solution is not saved over the user code
      if(solution.value === 'Show solution') {
        userEntry = textarea.value;
      } else {
        solutionEntry = textarea.value;
      }

      updateCode();
    };

    html {
      font-family: sans-serif;
    }

    h2 {
      font-size: 16px;
    }

    .a11y-label {
      margin: 0;
      text-align: right;
      font-size: 0.7rem;
      width: 98%;
    }

    body {
      margin: 10px;
      background-color: #f5f9fa;
    }

{{ EmbedLiveSample('Playable\_code', '100%', 730, "", "", "hide-codepen-jsfiddle") }}

## Active learning: Top 5 searches

A good use for array methods like {{jsxref("Array.prototype.push()","push()")}} and {{jsxref("Array.prototype.pop()","pop()")}} is when you are maintaining a record of currently active items in a web app. In an animated scene for example, you might have an array of objects representing the background graphics currently displayed, and you might only want 50 displayed at once, for performance or clutter reasons. As new objects are created and added to the array, older ones can be deleted from the array to maintain the desired number.

In this example we're going to show a much simpler use — here we're giving you a fake search site, with a search box. The idea is that when terms are entered in the search box, the top 5 previous search terms are displayed in the list. When the number of terms goes over 5, the last term starts being deleted each time a new term is added to the top, so the 5 previous terms are always displayed.

**Note**: In a real search app, you'd probably be able to click the previous search terms to return to previous searches, and it would display actual search results! We are just keeping it simple for now.

To complete the app, we need you to:

1.  Add a line below the `// number 1` comment that adds the current value entered into the search input to the start of the array. This can be retrieved using `searchInput.value`.
2.  Add a line below the `// number 2` comment that removes the value currently at the end of the array.

###### Playable code 2

    <h2>Live output</h2>
    <div class="output" style="min-height: 150px;">

    <input type="text"><button>Search</button>

    <ul>

    </ul>

    </div>

    <h2>Editable code</h2>

    <p class="a11y-label">Press Esc to move focus away from the code area (Tab inserts a tab character).</p>

    <textarea id="code" class="playable-code" style="height: 370px; width: 95%">
    const list = document.querySelector('.output ul');
    const searchInput = document.querySelector('.output input');
    const searchBtn = document.querySelector('.output button');

    list.innerHTML = '';

    let myHistory = [];

    searchBtn.onclick = function() {
      // we will only allow a term to be entered if the search input isn't empty
      if (searchInput.value !== '') {
        // number 1

        // empty the list so that we don't display duplicate entries
        // the display is regenerated every time a search term is entered.
        list.innerHTML = '';

        // loop through the array, and display all the search terms in the list
        for (let i = 0; i < myHistory.length; i++) {
          itemText = myHistory[i];
          const listItem = document.createElement('li');
          listItem.textContent = itemText;
          list.appendChild(listItem);
        }

        // If the array length is 5 or more, remove the oldest search term
        if (myHistory.length >= 5) {
          // number 2

        }

        // empty the search input and focus it, ready for the next term to be entered
        searchInput.value = '';
        searchInput.focus();
      }
    }
    </textarea>

    <div class="playable-buttons">
      <input id="reset" type="button" value="Reset">
      <input id="solution" type="button" value="Show solution">
    </div>

    html {
      font-family: sans-serif;
    }

    h2 {
      font-size: 16px;
    }

    .a11y-label {
      margin: 0;
      text-align: right;
      font-size: 0.7rem;
      width: 98%;
    }

    body {
      margin: 10px;
      background: #f5f9fa;
    }

    const textarea = document.getElementById('code');
    const reset = document.getElementById('reset');
    const solution = document.getElementById('solution');
    let code = textarea.value;
    let userEntry = textarea.value;

    function updateCode() {
      eval(textarea.value);
    }

    reset.addEventListener('click', function() {
      textarea.value = code;
      userEntry = textarea.value;
      solutionEntry = jsSolution;
      solution.value = 'Show solution';
      updateCode();
    });

    solution.addEventListener('click', function() {
      if(solution.value === 'Show solution') {
        textarea.value = solutionEntry;
        solution.value = 'Hide solution';
      } else {
        textarea.value = userEntry;
        solution.value = 'Show solution';
      }
      updateCode();
    });

    const jsSolution = 'const list = document.querySelector(\'.output ul\');\nconst searchInput = document.querySelector(\'.output input\');\nconst searchBtn = document.querySelector(\'.output button\');\n\nlist.innerHTML = \'\';\n\nlet myHistory= [];\n\nsearchBtn.onclick = function() {\n if(searchInput.value !== \'\') {\n myHistory.unshift(searchInput.value);\n\n list.innerHTML = \'\';\n\n for(let i = 0; i < myHistory.length; i++) {\n itemText = myHistory[i];\n const listItem = document.createElement(\'li\');\n listItem.textContent = itemText;\n list.appendChild(listItem);\n }\n\n if(myHistory.length >= 5) {\n myHistory.pop();\n }\n\n searchInput.value = \'\';\n searchInput.focus();\n }\n}';
    let solutionEntry = jsSolution;

    textarea.addEventListener('input', updateCode);
    window.addEventListener('load', updateCode);

    // stop tab key tabbing out of textarea and
    // make it write a tab at the caret position instead

    textarea.onkeydown = function(e){
      if (e.keyCode === 9) {
        e.preventDefault();
        insertAtCaret('\t');
      }

      if (e.keyCode === 27) {
        textarea.blur();
      }
    };

    function insertAtCaret(text) {
      const scrollPos = textarea.scrollTop;
      let caretPos = textarea.selectionStart;
      const front = (textarea.value).substring(0, caretPos);
      const back = (textarea.value).substring(textarea.selectionEnd, textarea.value.length);

      textarea.value = front + text + back;
      caretPos = caretPos + text.length;
      textarea.selectionStart = caretPos;
      textarea.selectionEnd = caretPos;
      textarea.focus();
      textarea.scrollTop = scrollPos;
    }

    // Update the saved userCode every time the user updates the text area code

    textarea.onkeyup = function(){
      // We only want to save the state when the user code is being shown,
      // not the solution, so that solution is not saved over the user code
      if(solution.value === 'Show solution') {
        userEntry = textarea.value;
      } else {
        solutionEntry = textarea.value;
      }

      updateCode();
    };

{{ EmbedLiveSample('Playable\_code\_2', '100%', 700, "", "", "hide-codepen-jsfiddle") }}

## Test your skills!

You've reached the end of this article, but can you remember the most important information? You can find some further tests to verify that you've retained this information before you move on — see [Test your skills: Arrays](/en-US/docs/Learn/JavaScript/First_steps/Test_your_skills:_Arrays).

## Conclusion

After reading through this article, we are sure you will agree that arrays seem pretty darn useful; you'll see them crop up everywhere in JavaScript, often in association with loops in order to do the same thing to every item in an array. We'll be teaching you all the useful basics there are to know about loops in the next module, but for now you should give yourself a clap and take a well-deserved break; you've worked through all the articles in this module!

The only thing left to do is work through this module's assessment, which will test your understanding of the articles that came before it.

## See also

- [Indexed collections](/en-US/docs/Web/JavaScript/Guide/Indexed_collections) — an advanced level guide to arrays and their cousins, typed arrays.
- {{jsxref("Array")}} — the `Array` object reference page — for a detailed reference guide to the features discussed in this page, and many more.

{{PreviousMenuNext("Learn/JavaScript/First\_steps/Useful\_string\_methods", "Learn/JavaScript/First\_steps/Silly\_story\_generator", "Learn/JavaScript/First\_steps")}}

## In this module

- [What is JavaScript?](/en-US/docs/Learn/JavaScript/First_steps/What_is_JavaScript)
- [A first splash into JavaScript](/en-US/docs/Learn/JavaScript/First_steps/A_first_splash)
- [What went wrong? Troubleshooting JavaScript](/en-US/docs/Learn/JavaScript/First_steps/What_went_wrong)
- [Storing the information you need — Variables](/en-US/docs/Learn/JavaScript/First_steps/Variables)
- [Basic math in JavaScript — numbers and operators](/en-US/docs/Learn/JavaScript/First_steps/Math)
- [Handling text — strings in JavaScript](/en-US/docs/Learn/JavaScript/First_steps/Strings)
- [Useful string methods](/en-US/docs/Learn/JavaScript/First_steps/Useful_string_methods)
- [Arrays](/en-US/docs/Learn/JavaScript/First_steps/Arrays)
- [Assessment: Silly story generator](/en-US/docs/Learn/JavaScript/First_steps/Silly_story_generator)
