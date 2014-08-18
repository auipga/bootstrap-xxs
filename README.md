bootstrap-xss
=============

This project provides support for handling smaller screen sizes with Bootstrap 3 (CSS version only).<br>
The new breakpoints are
* bootstrap-xss.css: `xss` at 480px
* bootstrap-xss-tn.css: `xss` at 480px and `tn` at 384px

New classes are:
* `col-xss-[1-12]` with corresponding `-pull-`, `-push-` and `-offset-`
* `hidden-xss`
* `visible-xss`, `visible-xss-block`, `visible-xss-inline`, `visible-xss-inline-block`
* Same for `-tn-` (only included in `xss-tn` version)

### Installation

1. Download and include [bootstrap-xss-tn.css](https://raw.githubusercontent.com/auipga/bootstrap-xss/master/bootstrap-xss-tn.css) or [bootstrap-xss.css](https://raw.githubusercontent.com/auipga/bootstrap-xss/master/bootstrap-xss.css)  in your project. This will handle most functions.

2. For full support you have to patch your `bootstrap.css` (tested only with v3.2.0)
  * Method 1: Apply patch file [bootstrap.css.patch](https://raw.githubusercontent.com/auipga/bootstrap-xss/master/bootstrap.css.patch)
  * Method 2: Use Regex to search and replace in bootstrap.css/bootstrap.min.css<br>
search for `@media \(max-width: ?767px\)( ?\{\n? *.(visible|hidden))`<br>
replace with `@media (min-width: 480px) and (max-width: 767px)$1`<br>
Should be 5 matches.<br>
This will work for minimized and development version.

### Usage

Same usage as for `xs`, `sm`, `md` or `lg`.

### Testing
There is a small (and ugly) script, which provides the browser width, calculated difference to the next breakpoints and recognised size by CSS. Include the [bsdebug.js](https://github.com/auipga/bootstrap-xxs/blob/master/bsdebug.js), that's it.<br>
![](https://raw.githubusercontent.com/auipga/bootstrap-xxs/master/doc_images/bsdebug_1.png)<br>
![](https://raw.githubusercontent.com/auipga/bootstrap-xxs/master/doc_images/bsdebug_2.png)

Or use it from a bookmarklet. Create a new bookmark with target:
```javascript
javascript:(function%20(){var%20n=document.createElement('script');n.setAttribute('language','JavaScript');n.setAttribute('src','https://raw.githubusercontent.com/auipga/bootstrap-xxs/master/bsdebug_bookmarklet.js?rand='+new%20Date().getTime()'+);document.body.appendChild(n);})();
```
