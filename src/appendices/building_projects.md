# Appendix 3: Building Projects

To build the projects, you will first need the `worldsmith` command line program. If you haven't already got that installed, see the [Installing Worldsmith](installing_worldsmith.md) section.

Building projects has only been tested under Windows. If you have problems with other operating systems, please [submit an issue](https://github.com/chrisnorman7/worldsmith_studio_manual/issues/new).

## Gather Tools

The primary tools you need are [Dart](https://dart.dev/get-dart) and [worldsmith](https://pub.dev/packages/worldsmith). If either of these aren't installed or on your path, please refer to the section on [installing worldsmith](installing_worldsmith.md).

### Windows Extras

By default, when building an EXE from a dart file under WIndows, a console window is opened when running the resulting EXE file. For a game, this is undesirable.

The `worldsmith` build command gets around this by calling a program called `editbin`. If you want this to happen automatically, ensure `editbin` is installed and available on your path.

<!-- According to [this page](https://developercommunity.visualstudio.com/t/find-package-that-contains-the-specfied-tool/943074#T-N943843), this is achieved by installing [Visual Studio](https://visualstudio.microsoft.com/), and including the [MSVC Command Line Toolset](https://docs.microsoft.com/en-us/cpp/build/building-on-the-command-line). -->

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
