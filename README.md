# fixto

Fix containers to the viewport relative to an ancestor. To see it in action you can see the [demo page][demo] or development pages [development page 1][dev1], [development page 2][dev2].

[demo]: http://bbarakaci.github.com/fixto
[dev1]: http://bbarakaci.github.com/fixto/dev1.html
[dev2]: http://bbarakaci.github.com/fixto/dev2.html

## Getting Started
Download the [production version][min] or the [development version][max].

[min]: https://raw.github.com/bbarakaci/fixto/master/dist/fixto.min.js
[max]: https://raw.github.com/bbarakaci/fixto/master/dist/fixto.js

Add jQuery

    <script src="jquery.js"></script>
    
Add fixTo

    <script src="fixto.min.js"></script>

## Usage

Use it with jQuery

    $('#nav').fixTo('body');
    
You can fix multiple containers to multiple ancestors. Make sure your selectors match exactly.

    $('.sticky').fixTo('.sticky-holder');
    
Passing options

    $('#left-banner').fixTo('#left-column', {
        className : 'my-class-name',
        zIndex: 10,
        mind: '#header'
    });
    
Usage without jQuery. This is the only way to have a reference to the instance, as yet.
    
    var sticky = fixto.fixTo(domElementToFix, domElementToBeFixed, options);

## Styling

When the container is fixed, it will receive the class name `fixto-fixed`. You may use this class or you may pass any other class name as an option.

## Options

### className (String)

See above example.

### zIndex (Number)

Although you can set z-index with css, it is possible to pass a `zIndex` option. See above example.

### mind (selector)

When you have other fixed containers on a page, pass those containers as mind option to prevent overlapping.

Example

    $('#header').fixTo('body');

    $('#left-banner').fixTo('#left-column', {
        mind: '#header'
    });
    
Selector can be in any form that jQuery can handle. You can pass multiple elements. 

## Features
- Responsive

## Browser support

Modern browsers, >= ie8 are supported. Touch devices are not supported.

## Known issues

- Doesn't work on elements having `margin:auto`. You will need an additional wrapper around the element. This is because webkit differs from other browsers about reporting the computed margin values.
