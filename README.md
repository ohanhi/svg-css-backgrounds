# svg-css-backgrounds

Multicolor SVGs as CSS backgrounds.

[See it live](http://ohanhi.github.io/svg-css-backgrounds/)


## How to do this

1. `encodeURIComponent('<svg xmlns="http...></svg>')`
2. Make that into a background image: `url(data:image/svg+xml,%3Csvg%20xmlns%3D%22http...)`
3. (optional) Using Sass, Less or PostCSS? Replace each color occurrence with a variable for custom coloring, e.g. `...stroke%3A%23#{$icon-main-color}%3Bstroke-linecap%...`. You might also like to have a function for the icons, see below.
4. Done!


## Helper function for icons

```scss
@function icon-url($icon, $icon-main: #bada55, $icon-highlight: #fe57a1) {
  // strip off the '#'
  $icon-main-slice: str-slice("#{$icon-main}", 2);
  $icon-highlight-slice: str-slice("#{$icon-highlight}", 2);

  @if ($icon == home) {
    $urlEncoded: "%3Csvg%20xmlns%3D%22http...";
  }
  //...

  @return url(data:image/svg+xml,#{$urlEncoded});
}
```

----

Licensed under [BSD (3-clause)](LICENSE).

Made with ♥ by [@ohanhi](https://twitter.com/ohanhi).
