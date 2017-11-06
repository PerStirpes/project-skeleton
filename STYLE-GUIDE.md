


### Working with files

* Do not end a file with any character other than a newline.
* Don't use the -a or -m flags for `git commit` for the first half of the class, since they conceal what is actually happening (and do slightly different things than most people expect).

    ```shell
    # good:
    > git add .
    > git commit
    [save edits to the commit message file using the text editor that opens]

    # bad:
    > git add .
    > git commit -m "updated algorithm"
    ```


### Opening or closing too many blocks at once

* The more blocks you open on a single line, the more your reader needs to remember about the context of what they are reading. Try to resolve your blocks early, and refactor. A good rule is to avoid closing more than two blocks on a single line--three in a pinch.

    ```javascript
    // avoid:
    _.ajax(url, {success: function(){
      // ...
    }});

    // prefer:
    _.ajax(url, {
      success: function(){
        // ...
      }
    });
    ```


### Capital letters in variable names

* Some people choose to use capitalization of the first letter in their variable names to indicate that they contain a [class](http://en.wikipedia.org/wiki/Class_(computer_science\)). This capitalized variable might contain a function, a prototype, or some other construct that acts as a representative for the whole class.
* Optionally, some people use a capital letter only on functions that are written to be run with the keyword `new`.
* Do not use all-caps for any variables. Some people use this pattern to indicate an intended "constant" variable, but the language does not offer true constants, only mutable variables.


### Minutia

* Don't rely on JavaScripts implicit global variables. If you are intending to write to the global scope, export things to `window.*` explicitly instead.

    ```javascript
    // good:
    var overwriteNumber = function(){
      window.exported = Math.random();
    };

    // bad:
    var overwriteNumber = function(){
      exported = Math.random();
    };
    ```

* For lists, put commas at the end of each newline, not at the beginning of each item in a list

    ```javascript
    // good:
    var animals = [
      'ape',
      'bat',
      'cat'
    ];

    // bad:
    var animals = [
        'ape'
      , 'bat'
      , 'cat'
    ];
    ```

### HTML

* Do not use ids for html elements. Use a class instead.

    ```html
    <!-- good -->
    <img class="lucy" />

    <!-- bad -->
    <img id="lucy" />
    ```

* Do not include a `type=text/javascript"` attribute on script tags

    ```html
    <!-- good -->
    <script src="a.js"></script>

    <!-- bad -->
    <script src="a.js" type="text/javascript"></script>
    ```
