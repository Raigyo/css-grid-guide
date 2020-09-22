# CSS Grid Layout Module

September 2020

\> 🔨 CSS Grid. From Udemy '[Maîtrisez CSS GRID !](https://www.udemy.com/course/maitrisez-css-grid/)'

\* * *

![exemple](_readme-img/logo.jpg)



## CSS Grid

CSS Grid Layout (aka “Grid”), is a two-dimensional grid-based layout system that aims to do nothing less than completely change the way we design grid-based user interfaces. CSS has always been used to lay out our web pages, but it’s never done a very good job of it. First, we used tables, then floats, positioning and inline-block, but all of these methods were essentially hacks and left out a lot of important functionality (vertical centering, for instance). Flexbox helped out, but it’s intended for simpler one-dimensional layouts, not complex two-dimensional ones (Flexbox and Grid actually work very well together). Grid is the very first CSS module created specifically to solve the layout problems we’ve all been hacking our way around for as long as we’ve been making websites.

## Firefox inspector

Use Firefiox to check the layout. 

It's very efficient.

![exemple](_readme-img/firefox-00.PNG)

## Terminology

### Grid Container

The element on which display: grid is applied. It’s the direct parent of all the grid items. In this example container is the grid container.

````html
<div class="container">
  <div class="item item-1"> </div>
  <div class="item item-2"> </div>
  <div class="item item-3"> </div>
</div>
````

### Grid Item

The children (i.e. direct descendants) of the grid container. Here the item elements are grid items, but sub-item isn’t.

````html
<div class="container">
  <div class="item"> </div>
  <div class="item">
    <p class="sub-item"> </p>
  </div>
  <div class="item"> </div>
</div>
````

### Grid Line

The dividing lines that make up the structure of the grid. They can be either vertical (“column grid lines”) or horizontal (“row grid lines”) and reside on either side of a row or column. Here the yellow line is an example of a column grid line.

![exemple](_readme-img/terms-grid-line.svg)



### Grid Cell

The space between two adjacent row and two adjacent column grid lines. It’s a single “unit” of the grid. Here’s the grid cell between row grid lines 1 and 2, and column grid lines 2 and 3.

![exemple](_readme-img/terms-grid-cell.svg)

### Grid Track

The space between two adjacent grid lines. You can think of them like the columns or rows of the grid. Here’s the grid track between the second and third row grid lines.

![exemple](_readme-img/terms-grid-track.svg)



### Grid Area

The total space surrounded by four grid lines. A grid area may be composed of any number of grid cells. Here’s the grid area between row grid lines 1 and 3, and column grid lines 1 and 3.

![exemple](_readme-img/terms-grid-area.svg)

### Exemple: container with items

````html
    <div class="container">
      <div class="items item1">1</div>
      <div class="items item2">2</div>
      <div class="items item3">3</div>
      <div class="items item4">4</div>
      <div class="items item5">5</div>
      <div class="items item6">6</div>
    </div>
````



````scss
.container{
  display: grid;
  grid-template-rows: 150px 150px;
  //or: grid-template-rows: repeat(2, 150px);
  grid-template-columns: 150px 150px 150px;
  //or: grid-template-columns: repeat(3, 150px);
  grid-gap: 30px;
  margin: 25px;
}

.items{
  padding: 20px;
  font-size: 30px;
  border: solid 1px;
}
````



 ![exemple](_readme-img/simple-grid.PNG)

### Fractional unit

Fraction of the free space in the grid (using the fr unit).

````scss
.container{
  display: grid;
  grid-template-rows: repeat(2, 1fr);
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 30px;
  margin: 25px;
  height: 1000px;
}
````

All the items will share the available space:

![exemple](_readme-img/fractional-unit.PNG)

## Properties: Containers

### display

Defines the element as a grid container and establishes a new grid formatting context for its contents.

Values:

- **grid** – generates a block-level grid
- **inline-grid** – generates an inline-level grid



## Properties: Items

#### grid-column-start / grid-row-start / grid-column-end / grid-row-end /  grid-area

Set were the selected item will start or end

````scss
.item1{
  grid-row-start: 2;
  grid-row-end: 3;
  grid-column-start: 2;
  grid-column-end: 3;
  background-color: pink;
}

//or

.item1{
  grid-row: 2 / 3;
  // grid-row-start / grid-row-end
  grid-column: 2 / 3;
  // grid-column-start / grid-column-end
  background-color: pink;
}

//or

.item1{
  grid-area: 2 / 2 / 3 / 3;
  // grid-row-start / grid-column-start / grid-row-end / grid-column-end
}
````

![exemple](_readme-img/grid-start.PNG)

````scss
.item1{
  grid-row: 1 / 2;
  grid-column: 1 / 4;
  background-color: pink;
}
````

The item1 take all the columns, and push the other items. Last items are reduced to fit the remaining space.

![exemple](_readme-img/grid-start-01.PNG)

"-1": means last row or column. But it will push the others items after.

## How to test

- Clone
- `npm install`
- `parcel serve index.html`
- Launch: `http://localhost:1234`


## Useful links

- [An Introduction to CSS Grid Layout (with Examples)](https://www.freecodecamp.org/news/intro-to-css-grid-layout/)
- [Getting started: CSS Grid vs Flexbox](https://medium.com/@daniaherrera/getting-started-css-grid-vs-flexbox-b3012fce6476)
- [A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)