<pre>
░█░█░█▀█░█░█░█▀█░░░░█▀▄░█▀▄
░█▀▄░█▀█░█▀▄░█▀█░░░░█▀▄░█▀▄
░▀░▀░▀░▀░▀░▀░▀░▀░▀░░▀░▀░▀▀░
</pre>

* https://github.com/mcfiredrill/kaka.rb

## DESCRIPTION:

fork of libcaca ruby extensions.

## SYNOPSIS

```
require 'caca'
c = Caca::Canvas.new(20,10)
c.put_str(2,3, "plop!")
c.draw_thin_polyline([[0,0],[0,2], [5,2], [0,0]])
d = Caca::Display.new(c)
d.title= "Test !"
d.refresh
```

## FEATURES/PROBLEMS:

The API is kind of awkward right now with regards to user input. The original
docs from the libcaca repo recommending doing something like this:

```
#Redefine Event::Key#quit? so that q, Q, and Esc become exit keys
module Caca
  class Event::Key
    def quit?
      "qQ^[".split('').member?(@ch.chr)
    end
  end
end
```

This didn't scale terribly well when I tried to make a text art editor => 
https://github.com/mcfiredrill/dirbird/blob/master/lib/events.rb

I'd like to see if there's another way to do this besides just monkeypatching
the event class in your application.

## REQUIREMENTS:

* libcaca

## INSTALL:

* gem install kaka

## DEVELOPERS:

After checking out the source, run:

  $ rake

This will compile the c extension and run the tests.

## NOTE ABOUT TESTS

It doesn't quite work out when you are running your tests in the same terminal
that libcaca is using for its display. I suggest using the X11 driver when
running the display tests.

`export CACA_DRIVER=x11`

## LICENSE:

            DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE
                    Version 2, December 2004

 Copyright (C) 2004 Sam Hocevar

 Everyone is permitted to copy and distribute verbatim or modified
 copies of this license document, and changing it is allowed as long
 as the name is changed.

            DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE
   TERMS AND CONDITIONS FOR COPYING, DISTRIBUTION AND MODIFICATION

  0. You just DO WHAT THE FUCK YOU WANT TO.

