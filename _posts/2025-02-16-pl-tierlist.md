---
layout: post
title: "The final Judgement on your Programming Language"
categories: posts
date: 2025-02-16
---

Everyone has their opinion on which programming language is the best. But only my opinion is the objectively correct one.
If your god and me disagree your god is wrong. So lets see whether your favorite language belongs in the dumpster or not.
All languages are in no particular order.

## Java

Java is one of the best known languages out there. And most opinions on it are quite negative. "Slow", "outdated", "overly complicated" etc.
But here is the thing: this isn't really Javas fault. Regarding performance, sure it can't quite compete with C, 
but the JVM does a lot of optimizations at runtime. This includes just-in-time compilation to generate native machine code.
Longer-running JVM programs can therefore actually perform quite well. And while older languages don't come with all the latest
bells and whistles I think this is a feature. A dumb language means you spent more time reading explicitly written code than
mentally inferring what the language does at this point. 
This point will be brought up a few more times over this post and is something I value highly.

Now, don't get me wrong. I'd rather jump out of the window head first than to work with an older Java codebase. 
But this isn't because of Java as a language and rather because of the mindset of people using Java. 
Inheritance all over the place, getters and setters and this mania to reach the highest level of abstraction in an
`AbstractFooFactoryFactoryConfig` instead of just using a goddamn `switch`. OO really has been brainrot we can only hope to recover from.
Also, the build systems for Java **SUCK**!

So yeah, the language itself is a 4/10 but the code written in it is a solid 0/10.

Wait, I found this [amazing song](https://www.youtube.com/watch?v=yup8gIXxWDU), score gets corrected to 7/10.

## C++

-100/10. I'll explain in a separate blog post as there are too many issues with it to count.
Suffice to say, this language has so many problems that no new codebase should use it. **EVER**

## C

Finally, a really good language. It's really old and before C89 it has been an absolute mess (it still is in parts), but it's also one of the simplest
languages I have ever used. I currently use it at work and this actually was the first time I really used it. 
My productivity skyrocketed compared to before. The thing with C is that you have so few language features doing stuff for you that you just end up
writing the behavior yourself. In turn you not only see what you get but you also tend to do things only one way. C isn't a language to be smart in.
Sure, you can write really smart algorithms and data structures in C, but the way you write them is not.

I would give it a 10/10 but we will see some languages that do Cs job a bit better so I'll give it a 9/10.

## Python

Depending on whether you use this language correctly or not, you may love it or hate it. As a scripting language it is completely fine
and I would prefer it to bash scripts, simply because I can read even non-trivial Python code,
whereas bash scripts can become really cryptic really quickly. If you wanna use it for other stuff I think you deserve to suffer.
Why would you ever use a scripting language to write a web server? I'm looking at you Django. 
If you are using it to script stuff, just don't use classes. Stick to the basic types or use `@dataclass` to make them less error prone.

As long as you use Python for what it's good at: 8/10

## JS

`undefined / 10`. Wait, why the hell is that `NaN`?! JS semantics can really be the worst. But at least, I was able to just watch others
lose their mind when confronted with this mess. As long as I stay away from web dev I can avoid it. And even if I start it sometime I may just go the
TypeScript route instead to have a saner experience. Prime seems to like JSDoc so that may also be an option. 
Just give me a strong enough type system.

0/10

But if you wanna see how a "general purpose" language can be one of the most esoteric ones it's a 10/10

## Rust

Oh, this one will be fun. Lets see how many people I can piss off!

Rust, the new shiny sexy beauty on the block. No more memory safety vulnerabilities! Fearless concurrency! Rewrite all your unsafe C software in Rust!
Just dye your hair blue, get your PhD in math and CS and you are ready to go. What do you mean the method `go` could not be found for this object?
Which trait did define the method again? Jokes aside, my biggest gripe is introducing references to a module that didn't use them before.
Having to update every user of that module to carry the lifetimes of these references is annoying.

However, this may very well be the price to pay for having a system programming language that can statically enforce safe usage of references.
And this is desirable to have. The premise of Rust, to enforce memory safety statically, is a good one to have. 
It's trying to avoid the mistakes of C and C++ in regards to this. There you can just blow off your leg and if you want any kind
of help from your tools you either need to enable specific warnings for your compiler and/or use a linter/sanitizer.
But if it's not on by default it will be forgotten. And for those, who are "umm, actually you can still introduce memory leaks in safe code",
memory leaks are not a violation of memory safety. Do they allow you to make illegal accesses to memory? No? It's safe then. Not secure, but safe.

And if you know how your program should look before you start you can reap the benefits of Rust while avoiding the drawback of increased work
when refactoring. While most programming languages are just collections of existing features, with the main differences between them being
syntax and the concrete set of features, Rust truly innovated by baking the concepts of ownership and the borrow checker into the language itself.
Maybe it won't be the language of the future. But it doesn't need to be that. It already forces other languages, be they already established ones
or new, to modernize or to come with more modern design principles out of the box. And this helps everyone. 
If you want to start a new project and consider using C++, try Rust instead. I think if Rust really sticks around it will be as a replacement for C++.
C is another case and I think another language is better suited for that.

That being said, I need to take some points away because of how dependencies are managed. A few years ago this wouldn't be an issue for me
as then I would have believed in centralized package repositories. Back then I thought the way you need to handle dependencies in C and C++
was archaic and too cumbersome, preventing you from easily and quickly adding a needed package.
But my opinion has changed, as I have acquired more knowledge regarding software security. I no longer see the way CMake and Meson handle it
as a bug, but rather as a feature. It means you tend more to just do it yourself before going out for third-party code and it naturally leads
to vendored dependencies. Cargo, on the other hand, makes you go out of your way to do that. 
Adding a `crates.io` dependency is trivial but if you want to vendor a library you now need to do that much more work. If you want to learn
more about these kinds of problems, "supply chain security" is the keyword.

8/10

## Zig

Remember when I said another language would be a better replacement for C? Lets talk about the one and only true language of the future.
Zig is C if C was designed in the last decade. It's a dumb language, like C, so you only really use one way to do something.
I love these kinds of languages, as already stated above. I don't spend my time thinking. I just write down the code.
Sure, maybe I could write the same program in 50% less lines in another language with more features, but in my experience
lines of code is a meaningless metric.
Just like in C, you can be incredibly productive in Zig **because** you spend your time writing and not thinking. 
And unlike C, Zig actually has an usable standard library. No need to re-invent `ArrayList` every time. 
And the `GeneralPurposeAllocator` even checks for memory leaks while debug mode inserts a lot of runtime checks, 
giving you a lot more memory safety. Don't worry, in release build these checks go away, so your software is as fast as it can be.

Your code: Zig! Your build system: also Zig! Even the lack of error reporting of the LSP is a feature. You gotta learn the language first.
Just try to write some Zig, that immediately compiles, and when the LSP gains proper error reporting it will just be quality of life for
you and not something you depend on.

Better start learning Zig now because we are going to take over the world!

69420/10

In all seriousness, it's a great language and if you like C you will really like Zig. There is still a lot to do for Zig 1.0 but the current direction
looks very promising. C interop is also very easy in Zig, compared to other languages, as you can just invoke your C compiler via the Zig compiler.
So if you want to incrementally rewrite an existing C codebase in another language, Zig makes that process as easy as it can get.

## Scala

Ah yes, you want your code to be a piece of art. Generations will debate over the meaning of your creation 
and awe in wonder how you achieved the level of enlightenment that lead you to this code. 
Unfortunately it will not run anything significant, unless you write software, that acts as data pipelines.
In this case some companies make use of it.

While Scala is a beautifully looking language it is also very easy to become smart in it. Again, a language being dumb is a good thing!
I don't know whether I hate the massive OO abstractions of Java code more than the type-system wizardy in Scala libraries.
But I guess, at least the latter can make your code harder to use wrong as the compiler will reject code that doesn't type-check.

And just like with Java, the build system is not good in my opinion. I'm no fan of SBT.

5/10

## Malbolge

LGTM

10/10
