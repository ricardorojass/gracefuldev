<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Flawless Ruby](#flawless-ruby)
  - [Very Able Variables](#very-able-variables)
    - [Top-Level Constant](#top-level-constant)
  - [I Literally Can't Even](#i-literally-cant-even)
    - [Large Integer Literals](#large-integer-literals)

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
- Ruby has its own unique take on some of these literal syntaxes. In this section, you’ll learn about how to use Ruby’s literals to make your code extra-expressive.

### Large Integer Literals
- One of the simplest forms of literal is an integer (non-fractional) number.
- In Ruby, however, there are some options in how you can choose to write out literal integer values.

Quick question: how many zeroes are in this number?

```ruby
100000000000
```

It's hard to visually identify the number of digits in a numeric literal.
For instance, in my US locale we would normally split the number into groups of three digits, with commas:

```ruby
# 100,000,000,000
```

Thankfully, we can do something similar in Ruby. So we could rewrite this number like so:

```ruby
100_000_000_000
```
