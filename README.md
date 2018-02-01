Importing [`_grid.scss`](https://github.com/vetalstar/bootstrap-grid-placeholders/blob/master/scss/_grid.scss) can help you to use bootstrap v 4.0.0 grid only.
Main classes are converted to SASS placeholders, because it doesn't support `@import (reference)`, as in LESS.

## This means that:

- You are free in class naming
- Smaller size of css files

## Quick start

1. Clone the repo: `git clone https://github.com/vetalstar/bootstrap-grid-placeholders.git`
2. Run `composer install` to install bootstrap v 4.0.0
3. See [`example.scss`](https://github.com/vetalstar/bootstrap-grid-placeholders/blob/master/scss/example.scss).
 

## For example
It can be useful for [BEM](https://en.bem.info/).

##### SCSS
````
.block {
  @extend %container-fluid;

  &__wrapper {
    @extend %row;

    &_modificator {
      @extend %no-gutters;
    }
  }

  &__element {
    @extend %col-md-10;
  }

  &__element2 {
    @extend %col-md-2;
  }
}
````
##### CSS
````
.block {
  width: 100%;
  padding-right: 15px;
  padding-left: 15px;
  margin-right: auto;
  margin-left: auto; 
}
.block__wrapper {
  display: flex;
  flex-wrap: wrap;
  margin-right: -15px;
  margin-left: -15px; 
}
.block__wrapper_modificator {
  margin-right: 0;
  margin-left: 0; 
}
.block__wrapper_modificator > * {
    padding-right: 0 !important;
    padding-left: 0 !important;
}
.block__element2, .block__element {
  position: relative;
  width: 100%;
  min-height: 1px;
  padding-right: 15px;
  padding-left: 15px; 
}
...
````
##### HTML
````
<div class="block">
    <div class="block__wrapper block__wrapper_modificator">
        <div class="block__element"></div>
        <div class="block__element2"></div>
    </div>
</div>
````