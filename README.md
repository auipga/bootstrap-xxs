bootstrap-xss
=============

This project provides support for handling smaller screen sizes with Bootstrap 3 (CSS version only).<br>
The new breakpoints are
* `xss` at 480px
* `tn`at 384px

New classes are:
* `col-xss-[1-12]` with corresponding `-pull-`, `-push-` and `-offset-`
* `hidden-xss`
* `visible-xss`, `visible-xss-block`, `visible-xss-inline`, `visible-xss-inline-block`
Same for `-tn-`

### Installation

1. Download and include [bootstrap-xss-tn.css](https://raw.githubusercontent.com/auipga/bootstrap-xss/master/bootstrap-xss-tn.css) in your project. This will handle most functions.

2. For full support you have to patch your `bootstrap.css` (tested only with v3.2.0)

  * Method 1: Apply patch file [bootstrap.css.patch](https://raw.githubusercontent.com/auipga/bootstrap-xss/master/bootstrap.css.patch)
  * Method 2: Use Regex to search and replace.<br>
search for `@media \(max-width: 767px\)( \{\n\ *.(visible|hidden))`<br>
replace with `@media (min-width: 480px) and (max-width: 767px)$1`<br>
Should be 5 matches. (Lines 6016, 6031, 6036, 6041, 6136)

### Usage

Same usage as for `xs`, `sm`, `md` or `lg`.

### Testing
There is a simple (=ugly) script, which provides the browser width, calculated difference to the next breakpoints and recognised size by CSS.
Just include the JS file.
![](https://raw.githubusercontent.com/auipga/bootstrap-xxs/master/doc_images/bsdebug_1.png)

![](https://raw.githubusercontent.com/auipga/bootstrap-xxs/master/doc_images/bsdebug_2.png)
