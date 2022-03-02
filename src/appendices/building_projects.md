# Appendix 3: Building Projects

To build the projects, you will first need the `worldsmith` command line program. If you haven't already got that installed, see the [Installing Worldsmith](installing_worldsmith.md) section.

Building projects has only been tested under Windows. If you have problems with other operating systems, please [submit an issue](https://github.com/chrisnorman7/worldsmith_studio_manual/issues/new).

## Gather Tools

The primary tools you need are [Dart](https://dart.dev/get-dart) and [worldsmith](https://pub.dev/packages/worldsmith). If either of these aren't installed or on your path, please refer to the section on [installing worldsmith](installing_worldsmith.md).

### Windows Extras

By default, when building an EXE from a dart file under WIndows, a console window is opened when running the resulting EXE file. For a game, this is undesirable.

The `worldsmith` build command gets around this by calling a program called `editbin`. If you want this to happen automatically, ensure `editbin` is installed and available on your path.

According to [this page](https://developercommunity.visualstudio.com/t/find-package-that-contains-the-specfied-tool/943074#T-N943843), this is achieved by installing [Visual Studio](https://visualstudio.microsoft.com/), and including the [MSVC Command Line Toolset](https://docs.microsoft.com/en-us/cpp/build/building-on-the-command-line).

In practise, Visual Studio's installer can be somewhat opaque, and it's worth installing more than you need to make sure you've got everything covered.

Next, you need to make sure `editbin` is in your path. The quickest way to do that is to go into a Microsoft Visual Studio Command Prompt (which you can find in your start menu).

Alternatively, modify your path, and include the path to the `vcvars64.bat` script. It will be located in a path like `C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Auxiliary\Build`. Then you can just type `vcvars64`. You should see output like the following:

```shell
**********************************************************************
** Visual Studio 2022 Developer Command Prompt v17.0.4
** Copyright (c) 2021 Microsoft Corporation
**********************************************************************
[vcvarsall.bat] Environment initialized for: 'x64'
```

Now the `editbin` command should work:

```shell
Microsoft (R) COFF/PE Editor Version 14.31.31104.0
Copyright (C) Microsoft Corporation.  All rights reserved.

usage: EDITBIN [options] [files]

   options:

      /ALLOWBIND[:NO]
      /ALLOWISOLATION[:NO]
      /APPCONTAINER[:NO]
      /BIND[:PATH=path]
      /DYNAMICBASE[:NO]
      /ERRORREPORT:{NONE|PROMPT|QUEUE|SEND}
      /GUARD:{CF|NO}
      /HEAP:reserve[,commit]
      /HIGHENTROPYVA[:NO]
      /INTEGRITYCHECK[:NO]
      /LARGEADDRESSAWARE[:NO]
      /NOLOGO
      /NXCOMPAT[:NO]
      /REBASE[:[BASE=address][,BASEFILE][,DOWN]]
      /RELEASE
      /SECTION:name[=newname][,[[!]{CDEIKOMPRSUW}][A{1248PTSX}]]
      /STACK:reserve[,commit]
      /SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|
                  EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|
                  NATIVE|POSIX|WINDOWS|WINDOWSCE}[,#[.##]]
      /SWAPRUN:{[!]CD|[!]NET}
      /TSAWARE[:NO]
      /VERSION:#[.#]
```

## Change Directory

Change to the directory where you project is stored. On most operating systems this is achieved with the `cd` command.

```shell
cd c:\Users\chris\src\RPG
```

This directory should have your asset stores directory, and your project's JSON file.

## Gather Libraries

In order to run, the `worldsmith` command needs at least 2 libraries:

* [synthizer](https://github.com/synthizer/synthizer/)
* [SDL2](https://libsdl.org/)
* Optionally, if you are using assets that are neither in was or MP3 format: [libsndfile](http://www.mega-nerd.com/libsndfile/) should be included.

You can find all of these libraries for your platform in the Worldsmith Studio directory.

## Performing Build

Now we can use the `worldsmith` command to build our project:

```shell
# worldsmith build
World: Untitled World
Creating directory game.
Writing world to game\world.data.
Encryption key 4fcrN6V8yi3gSS5RDG7ZCi/tcu1mUQ30QPrUkRtbQdg= written to game\world.key.
Generating dart code.
Creating game using template console-simple...

  .gitignore
  analysis_options.yaml
  CHANGELOG.md
  pubspec.yaml
  README.md
  bin\game.dart

Created project game in game! In order to get started, run the following commands:

  cd game
  dart run


Resolving dependencies in game...
+ args 2.3.0
+ asn1lib 1.1.0
+ clock 1.1.0
+ collection 1.15.0
+ convert 3.0.1
+ crypto 3.0.1
+ dart_sdl 0.8.8
+ encrypt 5.0.1
+ ffi 1.1.2
+ js 0.6.4
+ json_annotation 4.4.0
+ lints 1.0.1
+ meta 1.7.0
+ path 1.8.1
+ pointycastle 3.5.1
+ typed_data 1.3.0
+ ziggurat 0.40.2
Changed 17 dependencies in game!

Resolving dependencies in game...
+ dart_synthizer 0.7.7
+ matcher 0.12.11
+ quiver 3.0.1+1
+ stack_trace 1.10.0
+ ziggurat_sounds 0.20.0
Changed 5 dependencies in game!

Resolving dependencies in game...
Got dependencies in game!

Resolving dependencies in game...
Got dependencies in game!

Resolving dependencies in game...
+ open_url 2.0.0
+ worldsmith 0.16.0
Changed 2 dependencies in game!

Copying assets...
Assets: 0.
Info: Compiling with sound null safety
Generated: c:\users\chris\src\rpg\game\game.exe

There was an error running the `editbin` command. Ensure you have it in your path.
If you have Visual Studio installed, try locating and running the `vcvars64.bat` file.
Build complete.
Place the sdl dynamic library file inside the `game` directory.
Place the synthizer dynamic library file inside the `game` directory.
If desired, place the libsndfile dynamic library file inside the `game` directory.
When making a release, the following files must be included:
  game\assets
  game\game.exe
  game\world.data
```

You can include other files in your release, see `worldsmith build -h` for details.
