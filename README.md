# jQuery Circle Menu

jQuery Circle Menu is a plugin to create HTML elements anchored to a circle.

## Basic Usage
1. Include `jQuery` and `jquery-circle-menu.js` in your document.

```html
<script src="./jQuery.js"></script>
<script src="./js/jquery-circle-menu.js"></script>
```

2. Include  `jquery.circlemenu.css` in your head.

```html
<link href="./css/jquery.circlemenu.css" rel="stylesheet" type="text/css" media="screen" />
```

3. Create elements in your HTML. The structure requires all list items need to be inside two parent containers.

```html
<div class="wheel">
  <div class="wheel__list">
    <div class="wheel__list__item">
      <span>A</span></div>
    <div class="wheel__list__item">
      <span>B</span></div>
    <div class="wheel__list__item">
      <span>C</span></div>
    <div class="wheel__list__item">
      <span>D</span></div>
    <div class="wheel__list__item">
      <span>E</span></div>
    <div class="wheel__list__item">
      <span>F</span></div>
  </div>
</div>
```

4. Initialize the plugin.

```javascript
$('.wheel').circleMenu();
```

## Options

### Default Rotation

Default value: `0`

The `defaultRotation` property determines the initial position of the first list item. 

```javascript
$('.wheel').circleMenu({
  defaultRotation: 90,
});
```

### Dragging

Default `dragMouse` value: `false`
Default `dragTouch` value: `false`
Default `dragDirection` value: `horizontal`

The `dragMouse` and `dragMouse` properties determine which event will rotate the menu. The `dragDirection` value can either be `horizontal` or `vertical`.

```javascript
$('.wheel').circleMenu({
  dragMouse: true,
  dragTouch: true, 
  dragDirection: 'vertical',
});
```

### Draw Line

Default value: `false`

The `drawLine` option will animate a line from the first list item to the focused item. The color of this can be changed with CSS.

```javascript
$('.wheel').circleMenu({
  drawLine: true,
});
```

```css
.circle-menu__circle__svg__line {
  stroke: blue;
}
```

### Lock Direction

Default value: `false`

The `lockDirection` option will lock the list items to always face up instead of outward from the circle.

```javascript
$('.wheel').circleMenu({
  lockDirection: true,
});
```

### Focus Rotate

Default value: `false`

The `focusRotate` option rotate the focused list item to the default rotation position.

```javascript
$('.wheel').circleMenu({
  focusRotate: true,
});
```

## Methods

### Focus

You are required to manually call the focus method by passing the 0 index of the list item to be focused. If the `drawLine` option is on, it will draw a line from the first list item to the focused item. If the `focusRotate` option is on, it will rotate the entire menu to anchor the focused element. 

```javascript
var index = 2;
$('.wheel').circleMenu('focus', index);
```

## License
jQuery Circle Menu is licensed under the MIT license. (http://opensource.org/licenses/MIT)
