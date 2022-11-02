# boxgrid

A really simple CSS grid layout. I wanted this to be as simple as possible.
Using the standard `display: grid` CSS rule and just a few `row` and `col` classes.

## Demo

https://ant-on-io.github.io/boxgrid/

## Setup

Copy the `boxgrid.css` into your project and load it in your html:

```html
<link rel="stylesheet" href="boxgrid.css"/>

```
The base class for the grid system is `row`.
There are two ways of adding columns to a row:

## Equal-width columns

Add `c2` class for two columns, `c3` for three columns, etc:

```html
<div class="row c3">
  <div>first column</div>
  <div>second column</div>
  <div>third column</div>
</div>
```
## Regular twelve-column grid

Add column classes to the children of the `row` container.
Use `col-2` for a div spanning 2 out of 12 columns.
Use `col-4` for a div spanning 4 columns.
Combine column sizes until 12 columns are filled:

```html
<div class="row">
  <div class="col-4">first</div>
  <div class="col-8">third</div>
</div>

<div class="row">
  <div class="col-2">first</div>
  <div class="col-6">second</div>
  <div class="col-4">third</div>
</div>
```

## Empty spaces

If a column needs to start at a particular location, simply insert an empty div like this:

```html
<div class="row">
  <div class="col-5">first</div>
  <div class="col-2"></div>
  <div class="col-5">second</div>
</div>
```

## Column gaps

The default gap between columns is at `0.25rem`.
For a different gap value you can add `g4` to the `row` class (4 times larger gap: `1rem`) or any value between `g0` (no gap) to `g12` (`3rem`):

```html
<div class="row c2 g4">
  <div>one</div>
  <div>two</div>
</div>
```

The `g0` to `g12` classes apply only to that particular row.
But you can also change the gap value globally by adding this rule in your page css:


```css
.row {
  gap: 1px;
  margin-bottom: 1px;
}
```

## Forms

The `row` container does not need to be a div, it can be anything.
For example, the boxgrid system is particularly useful for forms:

```html
<form class="row">
  <input type="text" class="col-6" name="firstName" placeholder="first name"/>
  <input type="text" class="col-6" name="lastName" placeholder="last name"/>
  <input type="text" class="col-9" name="street" placeholder="street"/>
  <input type="text" class="col-3" name="number" placeholder="number"/>
  <input type="text" class="col-3" name="zip" placeholder="zip code"/>
  <input type="text" class="col-9" name="city" placeholder="city"/>
</form>
```

## Nested grids

Every column can be a `row` by itself, so it's easy to nest grids within grids:

```html
<div class="row">
  <div class="col-2">left</div>
  <div class="col-8 row c3"> <!-- nested -->
    <div>1</div>
    <div>2</div>
    <div>3</div>
  </div>
  <div class="col-2">right</div>
</div>
```

## License

This project is licensed under the terms of the MIT license.
