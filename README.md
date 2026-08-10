# Tùzijiā


A bunch of reusable libraries I'm writing in Lua when using [Usagi](https://usagiengine.com/).

> [!TIP]
> 兔子家: tùzijiā, /TOo-dzeu-JYA/ "Rabbit House/Family" 🐰🏠

> [!WARNING]
> Currently v0, expect breaking changes!

## Compatibility

Written during Usagi's v1.2.0 release cycle.

Uses Lua LS and LuaCATS typings (Teal isn't supported on Zed yet).

For type-checking reasons, generally requires Usagi's `meta/usagi.lua` and `.luarc.json` to be present.

## Installation




You should copy the `tuzi` folder into the root of your Usagi game folder,
e.g. as a sibling to `main.lua`.

Feel free to throw away the parts you don't need _if you know that they're not depended on by anything else_.

Then you can do:

```lua
local SomeModule = require("tuzi.somemodule")
```

> [!NOTE]
> This is not a single-file library. Some files will depend on others.

> [!WARNING]
> You might need to extend `package.path` if you put the libraries anywhere else.


## Design

Because I am iterating on the code in this library by hand-editing it during game development,
I have written a lot of it to make use of Usagi's method of handling state
(e.g. static functions acting on part of a global `State` object).

However, bits and pieces might become more OOP as things get more mature.

There is nothing wrong with using metatables and instances in your Usagi `State` tree, it's just
that if you _update_ a metatable, the hot-reload _will not catch the changes_ (as your instances'
metatables will all be pointing to a stale pre-reload definition). So this shouldn't affect
normal use of the library (just use composition over inheritence).

## Other Ecosystem Recommendations

> [!TIP]
> These are largely lifted from the Usagi Discord.

- https://codeberg.org/brettchalupa/usagi_template - the original Usagi template from the engine creator
- https://github.com/spad4/dandelion - a data-driven particle library for Usagi by spad4
- https://github.com/AxolotlGav/ritmo - an Usagi library for syncing events to the BPM of your game's music

## Acknowledgements

Special thanks to Brett Chulapa for developing Usagi and for creating
[a great shmup tutorial](https://book.usagiengine.com/02-shoot-em-up.html)
which I used as the original starting point for my own code and iterated on many times since.
