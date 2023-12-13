<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Flawless Ruby](#flawless-ruby)
  - [Very Able Variables](#very-able-variables)
    - [Top-Level Constant](#top-level-constant)
  - [I Literally Can't Even](#i-literally-cant-even)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Flawless Ruby

My notes from [Flawless Ruby Course](https://graceful.dev/courses/flawless-ruby/)

## Very Able Variables

- Working with variables in Ruby

### Top-Level Constant
- Constants lookups from inside class to top-level environment.
- First looks in the class level and then in the module level.


```ruby
FLOWER = "Clover"

module Neighborhood
  FLOWER = "Dogwood"

  module Yard
    FLOWER = "Rose"

    class Parent
      FLOWER = "Mountain Laurel"
    end

    class Child < Parent
      FLOWER = "Dandelion"

      def flower
        FLOWER
      end
    end
  end
end
Neighborhood::Yard::Child.new.flower
# => "Dandelion"
```

## I Literally Can't Even