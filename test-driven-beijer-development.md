# Advanced Scripting for Beijer iX Developer (and how to not loose your Object Oriented Mind)

I recently got my first experience with development for the iX platform.
This was my first time, writing C# code for an embedded system and the .NET compact framework.
Having some experience with test driven development (TDD), using Visual Studio, I natrually did not want to throw
everything over board and spent quite some time initally to find a good workflow and project setup, which I try to document in this post.
This is by no means the ultimate or only way to do TDD for .NET compact framework 3.5 in Visual Studio, it's merely what worked well for me.
If you have some additional input, I am happy to improve both, my workflow and this blog post with your suggestions :).

My experience with this setup is specific to Beijer iX Developer. It might be that parts of this post are also applicable to development for similar platforms with .NET CF 3.5 as well.

## Why do TDD and why use Visual Studio over iX Developer in the first place?

While I won't go into details on why I prefer a TDD approach as soon as the logic in the C# scripts gets more complex than mapping some UI fields to tags, here is a short list of things that will make your life so much easier as you don't have to touch the UI.

* It is probably free to use for you

* Navigation through files, auto completion

* Refactoring of Visual Studio

* Extension support, such as VsVim

* Support for dark mode :new_moon_with_face:

* You could even use JetBrains resharper

As a rough introduction and motivation for TDD I find [this presentation by Robert C. Martin](https://www.youtube.com/watch?v=qkblc5WRn-U) excellent.

## Limitations of Beijer iX Developer compared to .NET compact framework 3.5

* Beijer does not support named parameters in the IDE but happily compiles the code for you.

* Beijer does only allow auto-implemented properties if you specify both `get` and `set`. `{ get; }` alone as you would use for a `readonly` property, is not supported.

* Beijer doew not allow arrow functions.

## Setup your Visual Studio project for compact framework development

The biggest pitfall when developing your code for Beijer in Visual Studio and then compiling it in iX developer is to not setup your Visual Studio project correctly and end up using features and libraries that are not supported by the compact framework.
Officially support for .NET CF development ends with Visual Studio 2008 but there is a way to configure your project for later versions as well.
I used [this setup guide](https://gist.github.com/skarllot/4953ddb6e23d8a6f0816029c4155997a) to configure my project in Visual Studio 2019 without problems.

## How to structure your project

* Script files need to be created in iX Developer so that you have all the files.

* Try not to make changes in VS and iX simultaneously to prevent overriding uncommited changes.
From my experience so far I'd suggest to only open iX every once in a while, if you need to lookup a tag name or make UI changes.

* What is going on with internal classes in iX developer and what is generated automatically as partial classes for script files?

* Internal classes and test objects

* How to choose namespace names and class names.

* Don't name your classes like you name your files.

* Don't name your classes like you name your name spaces either.

## What to do with tags

### VariableReference

### Helper functions
