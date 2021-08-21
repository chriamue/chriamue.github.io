---
layout: post
title: Do we still need dynamic libraries?
---

Is it a good idea to dynamically link shared libraries anymore?

[Apple](https://developer.apple.com/library/archive/documentation/DeveloperTools/Conceptual/DynamicLibraries/100-Articles/OverviewOfDynamicLibraries.html) writes in 2012:
`Using dynamic libraries instead of static libraries reduces the executable file size of an app. They also allow apps to delay loading libraries with special functionality only when they’re needed instead of at launch time. This feature contributes further to reduced launch times and efficient memory use.`

As I worked with Rust which compiles static in default, I experienced Apps of sizes less than 10MB.
As most assets are much more in size today, I guess compiled data make up only a very small part of the whole App.

When we use an external library the shared library mostly contains functionality our Apps never use.
So maybe our App starts faster because of loading the library later, but then it has to load more data which also uses more memory then.

There are some other good arguments for shared libraries. In theory, when two Apps use the same shared library, the second App has not to load the shared library
into memory, which means faster load and less memory.

But in practice, especially on windows without good package manager,
I remeber how horrible it was when the wrong library version was installed and the Apps crashed.
The Apps had to package all their needed shared libraries with them.
When they load different versions of the libraries and there is no sharing anymore.
Additionally they load all the functionalities of the library they don't use.

On server side docker helps to solve problems with different versions of linked libraries.
But sometimes it makes me wonder why the image for a node app is more than 500MB in size.

This article [Packaging a Rust web service using Docker](https://blog.logrocket.com/packaging-a-rust-web-service-using-docker/) writes a web app docker image written in rust based on rust-alpine is 16MB in size!

For the future I will research more in making software more performant and static linking is a first step.
