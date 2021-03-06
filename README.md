##How to use gist-embed to spice up code snippets on your blog

#### Include jQuery and gist-embed src:

```html
  <head>
    <script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.min.js"></script>
    <script type="text/javascript" src="gist-embed.js"></script>
  </head>
```

#### Add a code element to your page with a data attribute in the following format, where `<gist-id>` should be replaced with the id of your gist:

```html
  <code data-gist-id="<gist-id>"></code>
```

####Examples
See http://blairvanderhoof.com/gist-embed/ for all possible ways to use gist-embed:
* Including a single gist
* Including individual files from a gist
* Including specific line numbers from a gist
* Removing all line numbers from a gist
* Removing the footer from a gist

####Notes about line number ranges:
* You can put a single number like `"1"`, a range like `"2-5"`, single line numbers separated with commas like `"11,20"`, or a mix of both like `"2-5,11,10-14,20"`

###Change log

####Version 1.2 (March 22, 2013)
* **Breaking change**:
  * Removed code elements with id attributes of `gist-` from being parsed.  You must use `data-gist-id` and specify an integer specifying the id of your gist.
  * Do not use `gist-` for the value of `data-gist-id`, only the value of the gist id is needed.
  * Rewrote the data attribute names.  Now all attributes are using a `data-gist-` namespace for all attributes. Please see example.html for options.
  * Do not point directly to gist-embed from github.  Host your own version so that if breaking changes are introduced, your websites won't be affected.

####Version 1.1 (March 20, 2013)
* **Breaking change**:
 * Using the id attribute of your code element to specify the gist id is **no longer accepted**.  You must now use a data attribute to specify the gist id.  See above for an example.
  * The reason for this change is that it is not proper HTML markup to have multiple DOM elements with the same id attribute on the same page and that it could lead to conflicts when including the same gist in multiple areas.
  * For the meantime, I will allow for both methods so anyone using this code from github directly won't have broken gists on their page.  I plan to deprecate this in the next month.
* Other changes:
 * Cleaned up example.html to include all possible ways to use gist-embed.
 * Thanks to https://github.com/kashif-umair for providing a way to remove the gist footer, remove all line numbers, and specify line number ranges.
