bootstrap-xxs
=============

This project provides support for handling smaller screen sizes with Bootstrap 3 (CSS version only).<br>
The new breakpoints are
* bootstrap-xxs.css: `xxs` at 480px
* bootstrap-xxs-tn.css: `xxs` at 480px and `tn` at 384px

New classes are:
* `col-xxs-[1-12]` with corresponding `-pull-`, `-push-` and `-offset-`
* `hidden-xxs`
* `visible-xxs`, `visible-xxs-block`, `visible-xxs-inline`, `visible-xxs-inline-block`
* Same for `-tn-` (only included in `xxs-tn` version)

### Installation

1. Download the tarball or install with package managers (recommanded)
  - `bower install bootstrap-xxs`
  - or `npm install bootstrap-xxs`

2. Include [bootstrap-xxs-tn.css](https://raw.githubusercontent.com/auipga/bootstrap-xxs/master/bootstrap-xxs-tn.css) or [bootstrap-xxs.css](https://raw.githubusercontent.com/auipga/bootstrap-xxs/master/bootstrap-xxs.css) in your project. This will handle all functions, but visible-xs* and hidden-xs classes.

3. For full support you need to patch your `bootstrap.css` with one of these methods OR use [bootstrap-patched.css](https://raw.githubusercontent.com/auipga/bootstrap-xxs/master/bootstrap-patched.css) or [bootstrap-patched.min.css](https://raw.githubusercontent.com/auipga/bootstrap-xxs/master/bootstrap-patched.min.css)
  * Method 1: Use Regex to search and replace in bootstrap.css/bootstrap.min.css<br>
search for `@media \(max-width: ?767px\)( ?\{\n? *.(visible|hidden))`<br>
replace with `@media (min-width: 480px) and (max-width: 767px)$1`<br>
Should be 5 matches.
  * Method 2: Apply [bootstrap.css.patch](https://raw.githubusercontent.com/auipga/bootstrap-xxs/master/bootstrap.css.patch) (unminified only)

### Usage

Same usage as for `xs`, `sm`, `md` or `lg`.

### Testing
There is a small (and ugly) script, which shows the recognised device size, browser width and calculates the difference to the next breakpoints. It requires jQuery (tested only with v1.11.1). Include [bsdebug.min.js](https://raw.githubusercontent.com/auipga/bootstrap-xxs/master/bsdebug.min.js) in your project (after jQuery), reload.<br>
Now resize your browser and watch the overlay.<br>
![](https://raw.githubusercontent.com/auipga/bootstrap-xxs/master/doc_images/bsdebug_1.png)<br>
![](https://raw.githubusercontent.com/auipga/bootstrap-xxs/master/doc_images/bsdebug_2.png)

Alternative: Use this bookmarklet. Create a new bookmark with target:
```javascript
javascript:(function%20(){var%20n=document.createElement('script');n.setAttribute('language','JavaScript');n.setAttribute('src','http://manueltransfeld.de/js/bsdebug_bookmarklet.min.js');document.body.appendChild(n);})();
```
