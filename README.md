[![Roy Theunissen](Documentation~/Github%20Header.jpg)](http://roytheunissen.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-brightgreen.svg)](LICENSE.md)
![GitHub Follow](https://img.shields.io/github/followers/RoyTheunissen?label=RoyTheunissen&style=social) ![Twitter](https://img.shields.io/twitter/follow/Roy_Theunissen?style=social)

_Allows you to quickly visualize continuously changing values for debugging purposes._

## About the Project

Very often when you're working on something gameplay or animation related it's not just relevant what a variable's exact value is, but what **shape** its curve has.

Is it flat? Smooth? Spiky? I don't know about you but I find it impossible to understand that just by logging the value in the console. I need to see it.

I really just want to be able to write one throwaway line of code that graphs a value for me, that I can then immediately remove once I understand the way the value works.

That's what Value Graphing is for!

![Example](Documentation~/Example.gif)

And the syntax for making these graphs is two lines of code:

```cs
// Simple graph with just one value
Graph.Get("Simple Graph").AddValue(Mathf.Sin(Time.time * Mathf.PI));

// More advanced graph with two related values, for easy comparison
Graph.Get("Double Graph").AddValue(Mathf.Cos(Time.time * Mathf.PI) * 0.25f)
    .AddValue(Time.time.Repeat(1.0f), "A Second Value");
```

## Getting Started

- Add Value Graphing to your Unity project (tips on how to install it are in the Installation section)
- Call `Graph.Get("Name Of Your Value").AddValue(yourValue)`

***TIP**: If you want to prevent adding a using directive so you can remove it easier, try the fully qualified name instead, like so:*
`RoyTheunissen.Graphing.Graph.Get("Name Of Your Value").AddValue(yourValue)`

## Other features

The syntax is optimized for fluid, one-line creation of simple graphs. However, it also supports explicitly creating and destroying graphs and lines.

You can use `graph.GetLine` to get more advanced types of lines, such as vertical lines or horizontal lines ("thresholds").

## Compatibility

It is made for Unity 2021 and BRP, but has been tested to work with Unity 2022 and URP.

If you want my help in supporting an even earlier version, feel free to reach out.

## Feature Wishlist

- Being able to embed a graph in a canvas instead of being dynamically created

## Installation

### Package Manager

Go to `Edit > Project Settings > Package Manager`. Under 'Scoped Registries' make sure there is an OpenUPM entry.

If you don't have one: click the `+` button and enter the following values:

- Name: `OpenUPM` <br />
- URL: `https://package.openupm.com` <br />

Then under 'Scope(s)' press the `+` button and add `com.roytheunissen`.

It should look something like this: <br />
![image](https://user-images.githubusercontent.com/3997055/185363839-37b3bb3d-f70c-4dbd-b30d-cc8a93b592bb.png)

<br />
All of my packages will now be available to you in the Package Manager in the 'My Registries' section and can be installed from there.
<br />


### Git Submodule

You can check out this repository as a submodule into your project's Assets folder. This is recommended if you intend to contribute to the repository yourself.

### OpenUPM
The package is available on the [openupm registry](https://openupm.com). It's recommended to install it via [openupm-cli](https://github.com/openupm/openupm-cli).

```
openupm add com.roytheunissen.value-graphing
```

### Manifest
You can also install via git URL by adding this entry in your **manifest.json**
```
"com.roytheunissen.value-graphing": "https://github.com/RoyTheunissen/Value-Graphing"
```

### Unity Package Manager
```
from Window->Package Manager, click on the + sign and Add from git: https://github.com/RoyTheunissen/Value-Graphing
```


## Contact
[Roy Theunissen](https://roytheunissen.com)

[roy.theunissen@live.nl](mailto:roy.theunissen@live.nl)
