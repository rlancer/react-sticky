react-sticky
============
[Demo](https://captivationsoftware.github.io/react-sticky)

Make any React component on your page sticky using inline styles or CSS classes!

## Installation
```sh
npm install react-sticky
```

## Code Example

First, you will want to wrap the element you want to be sticky with <Sticky></Sticky> tags. When the element is scrolled past the point where it would start to move off screen, the stickiness is activated.

app.jsx
```js
var React = require('react'),
  Sticky = require('react-sticky');

var Header = React.createClass({
  render: function() {
    return (
      <Sticky>
        <header>
          <nav />
        </header>
      </Sticky>
    );
  },
});

```

When the "stickiness" becomes activated, the following css style rules are applied to the Sticky element:

```css
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
```

### Props

#### stickyStyle
In the event that you wish to override the style rules applied, simply pass in the style object as a prop:

app.jsx
```js
<Sticky stickyStyle={customStyleObject}>
  <header />
</Sticky>
```

Note:
For more information on the style object see <http://facebook.github.io/react/tips/inline-styles.html>

#### stickyClass
You can also specify a class name ('sticky' by default) to be applied when the element becomes sticky:

app.jsx
```js
<Sticky stickyClass={customClassName}>
  <header />
</Sticky>
```

If you prefer to use external CSS rules instead of inline styles, you will need to pass an empty object to the stickyStyle property. Doing so will prevent the default inline styles from taking precedence over your own CSS rules. An example of how to do this is found below:

app.jsx
```js
<Sticky stickyClass="supersticky" stickyStyle={{}}>
  <header />
</Sticky>
```

#### topOffset
Sticky state will be triggered when the top of the element is `topOffset` pixels from the top of the window (0 by default). Positive numbers give the impression of a lazy sticky state, whereas negative numbers are more eager in their attachment.

app.jsx
```js
<Sticky topOffset={80}>
  <SomeChild />
</Sticky>
```

The above would result in an element that becomes sticky once its top is greater than or equal to 80px away from the top of the screen.


#### className
You can specify a class name that would be applied to the resulting element:

app.jsx
```js
<Sticky className={className}>
  <header />
</Sticky>
```

#### style
You can specify a style object that would be applied to the resulting element:

app.jsx
```js
<Sticky style={{background: 'red'}}>
  <header />
</Sticky>
```

Note: In the event that `stickyStyle` rules conflict with `style` rules, `stickyStyle` rules take precedence ONLY while sticky state is active. 

#### type
You can specify the type of element (`React.DOM.div` by default) that will be rendered:

app.jsx
```js
<Sticky type={React.DOM.header}>
  <SomeChild />
</Sticky>
```

The above would result in all sticky state attributes (class and style) being applied directly to the element you specify, rather than being wrapped in a React.DOM.div.

#### onStickyStateChange

Use the onStickyStateChange prop to fire a callback function when the sticky state changes:

app.jsx
```js
<Sticky onStickyStateChange={this.handleStickyStateChange}>
  <header />
</Sticky
```

## Contributors

Captivation Software

Aaron Goin

Alejandro Tardin

Ankit Sardesai (@amsardesai)

Josh Carr (@joshcarr)

By all means, if you see room for improvement, let us know!



## License

MIT License
