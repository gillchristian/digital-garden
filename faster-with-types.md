---
date: 2020-12-26T10:44
tags: [Seedling]
---

# Faster with types

Does working with an statically typed language, like TypeScript, make development slower because there's more code (ie. the types) to be typed? Does it make development slower because type errors need to be fixed?

I've seen these complaints and similar ones made when discussing if JavaScript applications should instead use any of the typed flavors (TypeScript, Flow, Elm, etc).

### My experience with TypeScript (and other typed languages)

**Disclaimer**: [YMMV](https://www.urbandictionary.com/define.php?term=ymmv). This is more of an empiric approach than an actual benchmark. I'm not trying to say that people are wrong when they say static types makes them slower. I'm only sharing my experience which is quite the opposite.

Working with statically typed languages makes development faster, for me, both on small and large projects, when starting from scratch and when maintaining an existing codebase.

The only exception I can think of is when hacking on short scripts or proofs of concept (a single less than 100 LoC file). And even then is more about being able to easily run the code (`node index.js` or `runghc main.hs`) than type types _per se_.

Here are ~~thirteen~~ a few reasons why.

#### Type inference

TypeScript has good type inference meaning you don't have to annotate every type all the time. Good libraries make great use of that (e.g. [fp-ts](https://github.com/gcanti/fp-ts)). Other languages like Haskell and Ocaml take type inference way further only requiring type annotations in an small number of cases to give the compiler a hand esolving types. In Haskell, for example, it's common (should I say best?) practice to only annotate top level function signatures.

Sadly this is not the case for all typed languages. Someone coming from a Java background will have a completely different experience. Even TypeScript feels quite verbose on the type level when compared to Elm or Haskell.

#### Types act as a documentation

Most of the time I write code that interacts with other code, be it my own app or third party libraries. Even when working on a project from scrath I will probably use a library, at least the language's standard library. By having types that experience is much faster as I'm less likely to need to check the documentation.

#### Types reduce [cognitive load](https://en.m.wikipedia.org/wiki/Cognitive_load)

The less stuff you got to keep in your head the better. Types are a great documentation and help a lot to figure out what things do. It's faster to look at the types than to Google things. Also _Go to definition_ is awesome!

#### Types help you model your problems

The more you can leverage the types system the easier and faster writing code becomes. Type Driven Development (the real TDD), [Making Impossible States Impossible](https://youtu.be/IcgmSRJHu_8). We can even get the compiler to tell us what our code should be ([type wholes](https://dev.to/gcanti/type-holes-in-typescript-2lck)).

#### Better tooling

Having types means you unlock some editor features that make development faster. Although most of them are already available by VS Code to JavaScript (because they actually use TypeScript). It's not the same when TS tries to infer JS code.

#### Getting things right on the first try

Chances are you'll get things right faster (if not at once) when leveraging the compiler.

#### Fast feedback cycle

Compiling the code is a much faster feedback cycle than running it. `ghci`, `cargo check`, `tsc --watch --noEmit` FTW! My workflow normally is: write some code, compile, fix type errors, repeat. And eventually run the code, of course. I do this even when working on frontend applications.

#### Types scale

Then there's the classic argument in favor of statically typed languages that when your application grows big then types make you more confident about your code and allow to make changes faster. Everybody knows this one.