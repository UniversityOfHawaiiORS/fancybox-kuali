This is a new version of the Fancybox 1.x (http://fancybox.net/) code
base which adds a few similar features in Fancybox 2.x.

It implements the following:

* Adds an `isOpen()` function to Fancybox that functions like the
Fancybox v2 `isOpen` property.
* Adds support for beforeClose, afterClose and afterShow callbacks from
Fancybox v2.

If you are looking to downgrade a KRAD-related application from Fancybox
2 to this version, you will also need to be sure to look at the
following:

* The HTML is fairly different between these versions. Specifically,
Fancybox 1 uses "id" instead of "class" on the HTML elements. You will
also probably want to do the following if you have coded against the
CSS class names from Fancybox 2:
  * Replace any references to `.fancybox-skin` with `#fancybox-outer`
  * Replace any references to `.fancybox-wrap` with `#fancybox-wrap`
  * Replace any references to `.fancybox-frame` with `#fancybox-frame`
  * Replace any references to `.fancybox-inner` with `#fancybox-content`
* If you are opening the fancybox manually in your code, then you will
want to look at the options on both fancybox 1 and fancybox 2 and change
them as needed.

For example, in KRAD internally, Fancybox 2 was initialized like:

```
{
  fitToView: true,
  openEffect: 'fade',
  closeEffect: 'fade',
  openSpeed: 200,
  closeSpeed: 200,
  minHeight: 10,
  helpers: {
    overlay: {
      css: {
        cursor: 'arrow'
      },
      closeClick: false
    }
  }
}
```

With Fancybox 1 the following is roughly equivalent:

```
{
  autoScale: true,
  transitionIn: 'fade',
  transitionOut: 'fade',
  speedIn: 200,
  speedOut: 200,
  hideOnContentClick: false,
  padding: 0
}
```

Further documentation on the API for Fancybox 1 can be found at:

http://fancybox.net/api

And futher documentation on the API for Fancybox 2 can be found at:

http://fancyapps.com/fancybox/#docs
