# Swift Vim Test Host

Swift Vim Test Host is a collection of examples to test out Swift Vim
functionality on "real" projects.

It includes various applications and build systems. Each project is already
setup to build `compile_commands.json` after a build: simply, run `make` in a
given example directory.

## Setup


Pull Deps

```
git submodule update --init
```

Vim code completion requires a [CompilationDatabase](https://clang.llvm.org/docs/JSONCompilationDatabase.html) which can be created from various build systems.

## Swift Package Manger Vim Example

SwiftPM examples include [a basic command line program](BasicCLISwiftPM).

```
# Build and install to /usr/local/bin
make -C SwiftCompilationDatabase install
```

The Makefile is setup to create `compile_commands.json` as part of the build.

```
cd BasicCLISwiftPM && make
```

Now, run Vim from the root of the example directory.

## Xcode Vim Examples

Xcode examples include [a basic OSX application](BasicOSX) and [a basic iOS application](BasiciOS).

```
# Build and install to /usr/local/bin
XcodeCompilationDatabase/install.sh
```

The examples are setup to create `compile_commands.json` as part of the build.

```
cd BasiciOS && make
```

or

```
cd BasicOSX && make
```

Now, run Vim from the root of the example directory.
 
