# Ruby Self

## Objectives

1. Use `self` within an instance method to refer to the instance.

## Outline

1. Imagine building a method to figure out if a string is a sentence

procedural implementation

```ruby
def sentence?(the_string)
  the_string.include?(".") || the_string.include?("?") || the_string.include?("!")
end
```

In object orientation, we want to encapsulate the logic into the object itself. we want to tech strings how to know if they are a sentence. So we refactor this into an instance method in a class String

```ruby
class String
  def sentence?
    the_string.include?(".") || the_string.include?("?") || the_string.include?("!")
  end
end
```

conceptually this works except for the fact that there is no longer a `the_string` argument.

`"Hello World!".sentence?("Hello World!")` makes no sense, we'd never do that, we called `sentence?` on the string already, we just need to figure out a better word for how an instance of a string can refer to itself.

```ruby
class String
  def sentence?
    self.include?(".") || self.include?("?") || self.include?("!")
  end

  def the_value_of_self
    self
  end

end
```

3. Definition of self as the object itself, always the object that received the method call, the thing before the . that sent this message.

1.the_value_of_self #=> 1
1.times(9).the_value_of_self #=> 9

http://blog.flatironschool.com/programming-postmodernism-and-rubys-self/
http://yehudakatz.com/2009/11/15/metaprogramming-in-ruby-its-all-about-the-self/
