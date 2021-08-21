---
layout: post
title: EasyImageSizer is Lenna soon!
---

[EasyImageSizer](https://sourceforge.net/projects/easyimagesizer/) was born in ages where I transfered images on floppy discs and my SD Card was 32MB in size.
I just needed a tool to compress my pictures so I was able to store more than 5 images on a floppy disc.
The first version was just a frontend for [ImageMagick](https://imagemagick.org/index.php) that allowed me to reduce 
image sizes from 250kb to 50kb without noticable quality loss.

The next versions I developed using the [QT](https://www.qt.io/) framework. The framework has much image processing functionality itself so I didn't need
the imagemagick dependency anymore.

To add more functionality the [OpenCV](https://opencv.org/) library was integrated. Changing the structure and integrating a plugin functionality, any
image processing functionality could be added.

Packaged to Windows and Linux installers, this was a nice project for me to learn whole software development workflow.

In 2021 the world has changed. In the time of internet everywhere and cloud computing, why should we take the time to install software on our computers,
which we don't know if this software next to the expected functionality harms our computer?

I wanted to learn another programming language anyways: [Rust](https://www.rust-lang.org/)!
Rust allows me to compile the sources to WebAssembly which also runs in the browser.
So no download, copy to any folder or installation is needed.
Just run the app in the browser, close to native speed.

I started the [Lenna Project](https://github.com/lenna-project) from scratch but with the functionality of EasyImageSizer in mind.
First of all the App can be used on [https://lenna.app/](https://lenna.app/) but also downloaded as [Desktop App](https://github.com/lenna-project/lenna-gui)
for Windows, Linux and also Mac now.

I hope in 2022 lenna will have all the functionality EasyImageSizer have, so please give it a try.
