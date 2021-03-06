# Building Node.js with Ninja

The purpose of this guide is to show how to build Node.js using [Ninja](https://ninja-build.org/), as doing so can be significantly quicker than using `make`. Please see [Ninja’s site](https://ninja-build.org/) for installation instructions (Unix only).

[Ninja](https://ninja-build.org/) is supported in the Makefile. Run `./configure --ninja` to configure the project to run the regular `make` commands with Ninja.

For example, `make` will execute `ninja -C out/Release` internally to produce a compiled release binary, It will also execute `ln -fs out/Release/node node`, so that you can execute `./node` at the project’s root.

When running `make`, you will see output similar to the following if the build has succeeded:

    ninja: Entering directory `out/Release`
    [4/4] LINK node, POSTBUILDS

The bottom line will change while building, showing the progress as `[finished/total]` build steps. This is useful output that `make` does not produce and is one of the benefits of using Ninja. Also, Ninja will likely compile much faster than even `make -j4` (or `-j<number of processor threads on your machine>`). You can still pass the number of processes to run for [Ninja](https://ninja-build.org/) using the environment variable `JOBS`. This will be the equivalent to the `-j` parameter in the regular `make`:

    JOBS=12 make

## Producing a debug build

To create a debug build rather than a release build:

    ./configure --ninja --debug && make
