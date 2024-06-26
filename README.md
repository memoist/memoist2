> [!IMPORTANT]
>
> # Recommendation
>
> Consider using [MemoWise](https://github.com/panorama-ed/memo_wise) instead, as it is maintained, fully tested, provides thread safety guarantees, and is much, much faster.
>
> # Other Alternatives
>
> In case you need a tool with this feature set that is currently maintained, check out:
> * https://github.com/makandra/memoized
> * https://github.com/honzasterba/memoist
> * https://github.com/AlexWayfer/alt_memery

> [!TIP]  
> Seriously though, read the important note above.

> [!WARNING]  
> If you must continue - be aware that this is unmaintained software.

memoist2
========

[![Build Status](https://travis-ci.org/matthewrudy/memoist2.png?branch=master)](https://travis-ci.org/matthewrudy/memoist2)

Simple Memoization for Ruby 2.0+.

### Differences between Memoist & Memoist2

Unlike [Memoist], this is **not** a drop-in replacement for old ActiveSupport::Memoizable. Memoist will still work just fine for that if you're using Ruby 2.0+. This project, on the other hand, is just me playing using Module#prepend which makes this stuff very simple.

**[Memoist]**
  * Works on all Rubies.
  * Is quite complicated.
  * Has the exact same api as `ActiveSupport::Memoizable`.

**Memoist2**
  * Only works on `Ruby >= 2.0.0`.
  * Is deliberately much simpler.
  * Has a slightly different API that could totally change.

  [Memoist]: https://github.com/matthewrudy/memoist


Example
-------

Memoize an instance method

    class Foo
      include Memoist2
  
      def bar
        sleep 1 && 2**10
      end
      memoize :bar
    end

Memoize a class method

    class Foo
      include Memoist2
  
      def self.bar
        # something expensive
      end
      memoize_class_method :bar
    end

Licence
-------

Licensed under the MIT licence.

See the file LICENCE.
