The library `cattle_ui` is a set of mootools classes I wrote, to use the
awesome jQueryUI-CSS without jQuery but by using MooTools.

- Version: 0.1
- Date: 2011/01/17

# State of Development: Alpha

`cattle_ui`'s API is still subject to change.

At `examples/show_off.html` you can see the different ways, how you can
build something with `cattle_ui`.

# Architecture

The css classes are 100% those from jQuery UI. That's why you are able to use
the jQueryUI Themeroller and Themes without any change.

The javascript classes are MooTools classes and follow the following rules:

* part of `cattle_ui` namespace
* implements
  * `revertDomElement()`
    - replaces the `this.dom_element` property with a valid dom element (will be
      called if no `dom_element` was given to the constructor)
  * `applyBehaviour()`
    - applies the behaviour on `this.dom_element`. Usually this is the place where
      the dom element becomes an enhanced cattle_ui element.
* extends `cattle_ui.BaseElement`, which provides
  - `initialize(dom_element, options)`
    - if `dom_element` is null, a new `dom_element` will be created
  - `getDomElement()` and `toElement()`
     - Returns dom representation of the cattle-ui Element
  - the array property `required_options`, which will be validated by
  `cattle_ui.BaseElement.assertRequiredOptions()`.
* input elements usually provide:
  - `getValue(): value`
  - `setValue(value)`

# Examples

At `examples/show_off.html` you can see the different ways, how you can
build something with `cattle_ui`.

# Changelog

- 2011/02/02
-- added cattle_ui.registerCreatorForType('yourtag', YourClass)

# License

cattle_ui is licensed under the terms of MIT. See LICENSE for more information.


