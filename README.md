# Grixins = Grid Mixins

Two really simple Sass mixins for creating grid systems.

## How to Use

Grixins is a pair of Sass mixins, one for making rows and one for making columns. They are very easy to use.

HTML

    <section>
      <article></article>
      <figure></figure>
    </section>

SASS

    section {
      @include row();
    }
    
    article {
      @include columns(9);
    }
    
    figure {
      @include columns(3);
    }

### Row options

You can make rows nest inside of other rows by passing "nest" as an option.

SASS
    
    section {
      @include row();
        
      section {
        @include row(nest);
      }
    }

Now `<section>` tags nested inside of other `<section>` tags will not break the grid.

### Column options

The first number passed to the `columns()` mixin is the number of columns. The second number is the number of columns to offset from the left, if any.

SASS
    
    // a 6 column span
    article {
      @include columns(6);
    }
    
    // an 8 column span offset by 4 columns
    article {
      @include columns(8,4);
    }
    
    // a 6 column span offset by 3 columns
    // this is how you can center columns
    article {
      @include columns(6,3);
    }

The default number of total columns is 12. You can change this by modifying the `$total-columns` variable in `_grixins.scss`.

## Demo App

The demo app uses [Middleman](http://middlemanapp.com) to render Sass but you can use whatever you like.

To setup the demo app with Middleman:

    $ git clone git@github.com:lchamb/grixins.git
    $ cd grixins
    $ bundle install
    $ middleman server

## License

The MIT License (MIT)

Copyright (c) 2014 Luke Chamberlin

[Full License Text](http://opensource.org/licenses/MIT)
