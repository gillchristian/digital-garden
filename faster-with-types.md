---
date: 2020-12-26T10:44
tags:
- 🌱
---

# Faster with types

I see many people complaining about how TypeScript makes coding slower because now you have to write the types.

While it is true that you have to write some types, meaning more code, meaning it'll take longer. That's not the whole picture.

### Disclaimer

[YMMV](https://www.urbandictionary.com/define.php?term=ymmv): This is more of an empiric approach than a benchmark with measurements.
I'm not trying to say that people are wrong when they say TS makes them slower. I'm just sharing my experience which is quite the opposite and yours might be too if you give TS or any other compiled language a try.

### My ideas

Here are a few things from my experience that are different from that:

1. TypeScript has good type inference, you don't have to annotate every type all the time. Good libraries make great use of that (e.g. [fp-ts](https://github.com/gcanti/fp-ts)). What I'm trying to say is you don't have to write types all the time.
2. Most of the time I write code that interacts with other code (be it my own app or the libraries I use) and by having types that experience is much faster.
3. Even when I write stuff from scratch I'm using libraries, having the types of those libraries makes development faster.
4. The less stuff you got to keep in your head the better. Types are a great documentation and help a lot to figure out what things do. It's faster to look at the types than to Google things.
5. The more you can leverage the types system the easier to write the code is after. Type Oriented Development, Making Impossible States Impossible. We can even get the compiler to tell us what our code should be ([type wholes](https://dev.to/gcanti/type-holes-in-typescript-2lck)).
6. The classic argument that eventually when your application becomes big then types makes you more confident about your code and allow to make changes faster. I was not going to mention this one but ...
7. Having types means you unlock some editor features that make development faster. Although most of them are already available by VS Code to JavaScript (because they actually use TypeScript). It's not the same when TS tries to infer JS code.
8. Chances are you'll get things right faster (if not at once) if you leverage the compiler.
9. Faster feedback cycle than running the code. `tsc --watch --noEmit` FTW.