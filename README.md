# Swift Vim Test Host

Swift Vim Test Host is a collection of examples to test out Swift Vim
functionality on real projects.

It includes various Applicaitons and Build Systems

Each project is already setup to build `compile_commands.json` after a build.

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
make -C BasicCLISwiftPM
```

## Xcode Vim Examples

Xcode examples include [a basic OSX application](BasicOSX) and [a basic iOS application](BasiciOS).

First setup Xcode compilation database support via [XcodeCompilationDatabase](https://github.com/jerrymarino/XcodeCompilationDatabase).

```
# Build and install to /usr/local/bin
XcodeCompilationDatabase/install.sh
```

The examples are setup to create `compile_commands.json` as part of the build.

```
xcodebuild -project BasiciOS/Basic.xcodeproj/ -sdk iphonesimulator -scheme Basic
```

