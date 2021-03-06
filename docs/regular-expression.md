---
title: Regular Expression
---

On the native side, you might have seen [Str](https://reasonml.github.io/api/Str.html) in the standard library, or [ocaml-re](https://github.com/ocaml/ocaml-re). Although these are viable choices on native, on the BuckleScript side, you should use the [Js.Re](https://bucklescript.github.io/bucklescript/api/Js.Re.html) bindings, which compile to straightforward JavaScript regular expressions. Advantages:

- Better unicode support
- No library overhead
- No extra compilation output (it's all `external`s that get compiled away)
- Same performance characteristics than JS regex, since it basically compiles to it

## Creation

We have a shorthand for creating the regex:

```ocaml
let f = [%bs.re "/b/g"]
```

Output:

```js
var f = /b/g
```
