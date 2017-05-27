# Swift Vim Test Host

Swift Vim Test Host is a Playground to test out Swift Vim functionality on real
projects.

It includes 2 Applicaitons and Xcode projects
- An OSX Application
- An iOS Application

Each project is already setup to build `compile_commands.json` after a build.

## Setup

Pull Deps

```
    git submodule update --init
```

Many semantic tools need a [CompilationDatabase](https://clang.llvm.org/docs/JSONCompilationDatabase.html)

Run `XcodeCompilationDatabase/install.sh` first. This installs
[XcodeCompilationDatabase](https://github.com/jerrymarino/XcodeCompilationDatabase)
to /usr/local/bin being on your `$PATH`. The examples won't build unless
[XcodeCompilationDatabase](https://github.com/jerrymarino/XcodeCompilationDatabase)
is on your path.

## YouCompleteMe Usage

It may be interesting to test out YouCompleteMe support.

![SwiftySwiftVimYCMPreview](https://cloud.githubusercontent.com/assets/1245820/25786944/71ddaf52-3351-11e7-96d6-a32a714e35f6.gif)

Install the [RFC branch of YCMD with Swift Support](https://github.com/Valloric/ycmd/pull/487)
into your YouCompleteMe installation.

For example, this means going into wherever you cloned YouCompleteMe and then:

```
  mv third_party/ycmd third_party/ycmd-master
  git clone  https://github.com/jerrymarino/ycmd.git

  # Checkout the RFC branch 
  git checkout remotes/origin/jmarino_swift_prototype_squashed
  git submodule update --init --recursive

  # Build with Swift support
  # ( Also, clang completer and potentially --debug-symbols )
  ./build.py  --completers --swift-completer --clang-completer
```

By default Vim does not support the `swift` filetype.

Cat this into your `.vimrc`

```
    " Force swift filetype
    autocmd BufNewFile,BufRead *.swift set filetype=swift
```

Then, assert it's set to the correct value when a `swift` file is open.

```
    :set ft?
```

## Command line Run and Debug

Run, or easily start debug sessions on an iOS simulator. See the shell script
for this in the BasiciOS example tree.

