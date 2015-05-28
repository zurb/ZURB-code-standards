# JavaScript

## Plugin Anatomy

### IIFE

The plugin definition is wrapped in an immediately-invoked function expression, to keep variables out of the global scope. The global `Foundation` and `jQuery` objects are passed into the function.

Putting a negation operator (`!`) before a function forces it to execute, making it *slightly* more efficient, character-wise, than the other method of wrapping the function in parentheses.

```js
!function(Foundation, $) {}(Foundation, jQuery)
```

### Class

A plugin is a single class.

```js
function Plugin() {}
```

### Constructor

All plugins follow the same constructor format. It accepts an `element` parameter, which is the primary element the plugin is attached to. It also accepts an `options` object, which extends the default options object.

```js
function Plugin(element, options) {
  this.$element = element;
  this.options = $.extend({
    // Defaults
  }, options);
}
```

The constructor should also call an `_init()` method, and if needed an `_events()` method, followed by a DOM event indicating that the plugin is done being initialized.

```js
function Plugin(element, options) {
  // ...

  this._init();
  this._events();
  this.$element.trigger('init.zf.plugin');
}

### Prototype

All plugin methods should be defined in the plugin object's prototype. Private methods are prefixed with an underscore. Of course, this doesn't *actually* make them private.

```js
Plugin.prototype = {
  _init: function() {},
  doSomething: function() {}
}
```

### Initialization

A plugin should have an `_init` method that performs setup operations.

```js
Plugin.prototype = {
  _init: function() {}
}
```

### Event handling

If a plugin responds to DOM events, it should have a separate `_events()` method just for defining event listeners.

```js
Plugin.prototype = {
  _events: function() {
    this.$element.on('click', function() {});
  }
}
```

### Event naming

Custom events should be namespaced and follow the format `[eventName].zf.[pluginName]`.

More complex events should fire two events: one when the method starts, and one when the method finishes. Use an infinitive (e.g. `open`) for the start event, and past tense (e.g. `opened`) for the final event. Always trigger the event from the plugin's primary element.

```js
Reveal.prototype = {
  open: function() {
    this.$element.trigger('open.zf.reveal');
    // Code to open a modal
    this.$element.trigger('opened.zf.reveal');
  }
}
```

### Exporting

The plugin constructor is added to the global `Foundation` object, allowing it to be used programmatically.

```js
function Plugin(element, options) {}

Foundation.Plugin = Plugin;
```

### Module loaders

Specific code for module loaders is also included. This code will be ignored if a module loader is not being used.

Browserify imitates the Node style of package loading. Assign the plugin's constructor to `module.exports` to expose it to the module loader.

```js
if (typeof module !== 'undefined' && typeof module.exports !== 'undefined')
  module.exports = Plugin;
```

CommonJS uses the AMD pattern, where a module and its dependencies are defined with the `require` function. The plugin's name uses the format `foundation/[pluginName]`.

```js
if (typeof define === 'function')
  define('foundation/plugin', ['jquery'], function($) {
    return Plugin;
  });
```

## Documentation

Plugins are documented using the [JSDoc](http://usejsdoc.org/) format. The documentation is consumed by our docs generator Supercollider, which generates HTML generation from the comments.

When documenting your code, these are the hot ones to keep in mind.

### Class

Document the plugin's class using `@class`.

```js
/**
 * Creates a new instance of Plugin.
 * @class
 */
var Plugin = function() {}
```

### Methods

Document each of the plugin's methods. Use `@param` to explain each parameter in the function.

```js
/**
 * Does a thing.
 * @param {Object} thing - Thing to do.
 */
Plugin.prototype.doThing = function(thing) {}
```

### Events

Document every event that a plugin fires, above the line where the call to `$.fn.trigger()` is made. If an event is fired in more than one place in the code, just document it once, the first place it appears.

Use the `@event` tag to name the event. Use the format `[pluginName]#[eventName]`, where `[eventName]` is the same name as the DOM event itself.

```js
/**
 * Fires when something happens.
 * @event Plugin#thing
 */
this.$element.trigger('thing.zf.plugin');
```

Add the `@fires` tag to any method that triggers an event.

```js
/**
 * Does a thing.
 * @fires Plugin#thing
 */
Plugin.prototype.doThing = function() {
  this.$element.trigger('thing.zf.plugin');
}
