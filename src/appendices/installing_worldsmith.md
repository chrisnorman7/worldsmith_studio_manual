# Appendix 1: Installing worldsmith

## Introduction

In order to either [play](playing_projects.md) or [build](building_projects.md) your projects, you need the `worldsmith` command line tool. This is part of the [worldsmith](https://pub.dev/packages/worldsmith) package.

## Installing Dart

If you haven't already, ensure you have installed either [Flutter](https://docs.flutter.dev/get-started/install), or [Dart](https://dart.dev/get-dart). Flutter is recommended.

Next, make sure that the `dart` executable program is in your path. How to do this is beyond the scope of this manual.

You should now be able to open up your console (for example cmd.exe on Windows, or Terminal on Linux or OS X), and type `dart -v`, and see output like the following:

```shell
Dart SDK version: 2.16.1 (stable) (Tue Feb 8 12:02:33 2022 +0100) on "windows_x64"
```

## Installing Worldsmith

When all of this is done, you need to install the worldsmith package.

### Installing With Pub

To install with `dart pub` (the Dart package manager), use the following command:

```shell
dart pub global activate --overwrite worldsmith
```

This will install the latest version of worldsmith from [pub.dev](https://pub.dev/). There may be changes that have not yet been included into this version, in particular beta testers of Worldsmith Studio will probably want to [install from git](#installing-from-git).

### Installing From Git

To install from git, use the following command:

```shell
dart pub global activate -s git --overwrite https://github.com/chrisnorman7/worldsmith
```

Please be aware that there may be conflicts between the Git version of the worldsmith package, and the stable version of Worldsmith Studio.

## Which Version Should I Choose?

As a general rule, if you are beta testing Worldsmith Studio, install from [git](#installing-from-git). If you are using the current stable release of Worldsmith Studio, use the version from [pub](#installing-with-pub).
