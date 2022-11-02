# boxgrid

A really simple CSS grid layout. I wanted this to be as simple as possible. Using the standard `display: grid` CSS rule and just a few `row` and `col` classes.

## Demo

...

## Setup

Copy the `boxgrid.css` into your project and load it in your html:

```
<link rel="stylesheet" href="/css/boxgrid.css"/>

```
The base class for the grid system is `row`. There are two ways of adding columns to a row:

## Equal-width columns

Add `c2` class for two columns, `c3` for three columns, etc:

```
<div class="row c3">
  <div>first column</div>
  <div>second column</div>
  <div>third column</div>
</div>
```
## Regular twelve-column grid

Add column classes to the children of the `row` container. Use `col-2` for a div spanning 2 out of 12 columns.
Use `col-4` for a div spanning 4 columns.
Combine column sizes until 12 columns are filled:

```
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

```
<div class="row">
  <div class="col-5">first</div>
  <div class="col-2"></div>
  <div class="col-5">second</div>
</div>
```

## Column gaps

The default gap between columns is at `0.25rem`. For a different gap value you can add `g4` to the `row` class (4 times larger gap: `1rem`) or any value between `g0` (no gap) to `g12` (`3rem`):

```
<div class="row c2 g4">
  <div>one</div>
  <div>two</div>
</div>
```

## License

This project is licensed under the terms of the MIT license.
