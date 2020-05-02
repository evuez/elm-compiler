# Elm, with infix functions.

Elm has infix functions, but only core developers can use them in core packages.

With this fork, everyone can use them!

`MyInfix.elm`
```
module MyInfix exposing ((<$>))

infix left 4 (<$>) = maybemap

maybemap = Maybe.map
```

`Main.elm`
```
module Main exposing (..)

import MyInfix exposing ((<$>))

reverse : Maybe String -> Maybe String
reverse str = String.reverse <$> str
```

```
elm make src/Main.elm
elm repl

> import Main exposing (reverse)
> reverse (Just "gnirts a")
Just ("a string")
```

🎉

# Install

Just run `stack install`.
