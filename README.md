#Semantic FontAwesome Sass
'semantic-fa-sass' is a fork of ['font-awesome-sass'](https://github.com/FortAwesome/font-awesome-sass), which focuses on the use of semantic class names. For example, instead if writing this:

```html
Connection Status: <i class="fa fa-times"></i>
```

You can instead write:

```html
ConnectionStatus: <i class="connection-status inactive"></i>
```

## Usage

To use Semantic FontAwesome icons, you simply use the following mixin:

```scss
.connection-status {
    .active {
        @include s-fa-icon(signal);
    }
    .inactive {
        @include s-fa-icon(times);
    }
}
```

This will then compile to:

```scss
...
.connection-status .active, .connection-status .inactive {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  transform: translate(0, 0);
}
...
.connection-status .inactive:before {
  content: "";
}

.connection-status .active:before {
  content: "";
}
...
```

This also has the added benefit of only rendering the css for icons you actually use!

If you want to use other font-awesome classes, such as `fa-spin`, `fa-5x`, `fa-border` etc, you simply add them in the mixin:

```scss
.foo {
    @include s-fa-icon(mobile 5x spin border right)
}
```

## Installation

Please see the appropriate guide for your environment of choice:

* [Ruby on Rails](#a-ruby-on-rails).
* [Compass](#b-compass-without-rails) not on Rails.

### a. Ruby on Rails

In your Gemfile include:

```ruby
gem 'semantic-fa-sass', '~> 1.0'
```

And then execute:

```sh
bundle install
```

Import the FontAwesome styles in your `app/assets/stylesheets/application.css.scss`. The `font-awesome-sprockets` file
includes the sprockets assets helper Sass functions used for finding the proper path to the font file.

```scss
@import "font-awesome-sprockets";
@import "font-awesome";
```


### b. Compass without Rails

Install the gem

```sh
gem install semantic-fa-sass
```

If you have an existing Compass project:

```ruby
# config.rb:
require 'semantic-fa-sass'
```

Import the FontAwesome styles

```scss
@import "font-awesome-compass";
@import "font-awesome";
```
