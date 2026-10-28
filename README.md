# CSS Flexbox — Learning Notes

## What Is Flexbox?

Flexbox is a CSS layout system used to arrange elements inside a container along a row or column. It provides control over alignment, spacing, distribution, and wrapping.

## 1. Enable Flexbox

```css
.container {
  display: flex;
}
```

- The element becomes a flex container.
- Its direct children become flex items.
- The default direction is a horizontal row.

## 2. Flex Direction

The `flex-direction` property determines the main axis and the direction in which flex items are arranged.

```css
.container {
  display: flex;
  flex-direction: row;
}
```

Items are arranged horizontally.

```css
.container {
  display: flex;
  flex-direction: column;
}
```

Items are arranged vertically.

Other values:
- `row-reverse`
- `column-reverse`

## 3. Main Axis and Cross Axis

The main axis depends on `flex-direction`.

When `flex-direction: row`:
- Main axis: horizontal
- Cross axis: vertical

When `flex-direction: column`:
- Main axis: vertical
- Cross axis: horizontal

This distinction determines how alignment properties behave.

## 4. Justify Content

`justify-content` aligns and distributes flex items along the main axis.

```css
.container {
  display: flex;
  justify-content: center;
}
```

Other useful values:
- `flex-start`
- `flex-end`
- `space-between`
- `space-around`
- `space-evenly`

The exact result depends on the available space and the items' sizes.

## 5. Align Items

`align-items` controls alignment along the cross axis.

```css
.container {
  display: flex;
  align-items: center;
}
```

For a row, this typically centers items vertically within the container's cross-axis space.

For a column, this typically centers items horizontally.

Useful values:
- `flex-start`
- `flex-end`
- `center`
- `stretch`
- `baseline`

## 6. Gap

The `gap` property creates space between flex items.

```css
.container {
  display: flex;
  gap: 20px;
}
```

This creates a 20px gap between adjacent items without adding that gap to the outer edges of the container.

You can also use `row-gap` and `column-gap`.

## 7. Flexbox vs. Inline-Block

Both `display: inline-block` and `display: flex` can produce a horizontal arrangement.

However, they work differently:

- `inline-block` allows elements to participate in inline formatting while retaining properties such as width and height.
- `flex` makes the parent a flex container and gives it control over the arrangement of its direct children.

Flexbox provides dedicated controls for alignment, distribution, spacing, direction, and wrapping.

## 8. A Practical Example

HTML:

```html
<div class="container">
  <div class="item">One</div>
  <div class="item">Two</div>
  <div class="item">Three</div>
</div>
```

CSS:

```css
.container {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 20px;
}
```

This arranges the three items in a horizontal row, centers the group along the main axis, aligns the items along the cross axis, and adds 20px between adjacent items.

## 9. Responsive Direction

Flexbox can change direction at a breakpoint.

```css
.container {
  display: flex;
  flex-direction: row;
  gap: 16px;
}

@media (max-width: 600px) {
  .container {
    flex-direction: column;
  }
}
```

Above 600px, items are arranged in a row. At or below 600px, they are arranged in a column.

## 10. What to Practise

- Arrange elements horizontally and vertically.
- Change direction using `flex-direction`.
- Center items along the main and cross axes.
- Distribute available space using `justify-content`.
- Align items using `align-items`.
- Control spacing with `gap`.
- Compare Flexbox with inline-block.
- Build layouts that change direction on mobile.

## Key Takeaway

`display: flex` establishes the flex layout, `flex-direction` determines the main axis, `justify-content` operates along the main axis, `align-items` operates along the cross axis, and `gap` controls spacing between items.
