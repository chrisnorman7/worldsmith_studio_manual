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

### Using Local Copy

If you have cloned the worldsmith repository, you can add the included `bin` directory in your path. Under Windows, there is a script called `worldsmith-source`, which you can use to ensure you are always using the latest version of the command.

Unfortunately, this script has not yet been ported to other platforms.

How to modify your system path is beyond the scope of this manual.

## Which Version Should I Choose?

As a general rule, if you are beta testing Worldsmith Studio, install from [git](#installing-from-git). If you are using the current stable release of Worldsmith Studio, use the version from [pub](#installing-with-pub).

If you don't want to do either of these things, you can either use a relative path when executing the `worldsmith` command, or you can use the `worldsmith-source` script if you are running Windows.

## Installing Worldsmith Studio

## Stable Version

If you are happy to use the latest (mostly) stable version of Worldsmith Studio, you can find binaries for Windows on the [releases page](https://github.com/chrisnorman7/worldsmith_studio/releases/latest).

Other platforms can be added, probably with some help, although I have no real means of testing these.

### Running From Source

To use the latest version, ensure you have both [Dart](https://dart.dev/) and [Flutter](https://flutter.dev/) installed. You will also need the [git](https://git-scm.com/) command in your path.

For best results, use flutter from the master channel. Worldsmith Studio may work with the beta channel, but for best results, master should be used.

To update flutter to the master branch, issue the following commands:

```shell
flutter channel master
flutter upgrade
```

Also, `flutter upgrade` should be rerun periodically, to ensure Dart and Flutter are both up to date.

#### Clone Repositories

Firstly, clone the repositories for both [worldsmith](https://github.com/chrisnorman7/worldsmith) and [Worldsmith Studio](https://github.com/chrisnorman7/worldsmith_studio):

```shell
git clone https://github.com/chrisnorman7/worldsmith
git clone https://github.com/chrisnorman7/worldsmith_studio
```

It is important that both these repositories are cloned into the same directory, and that you have write access to this directory. To be sure, simply clone inside your home directory (Mac OS and Linux) or user profile directory (Windows).

#### Get Packages

Change into both directories, and get packages.

For `worldsmith`, you will need to use `dart pub get`, because it is a package. For `worldsmith_studio`, use `flutter pub get` because it is a Flutter project.

```shell
cd worldsmith
dart pub get
cd ../worldsmith_studio
flutter pub get
```

It is worth checking that your `worldsmith` repository is as up to date as it can be, since both it and Worldsmith Studio are in such a state of flux while they are so heavily under development.

You could do this with the following scripts:

##### Windows

```shell
@echo off
cd ..\worldsmith & git pull & cd ..\worldsmith_studio & git pull & flutter run -d windows
```

##### Mac OS / Linux

```shell
cd ../worldsmith && git pull && cd ../worldsmith_studio && git pull && flutter run -d <platform>
```

##### Generic

You can omit the `-d <platform>` argument from the `flutter run` command, and it should still give you a desktop app depending on your system setup.

#### Running The Program

To run the program, type `flutter run`.

If you have multiple devices connected, Flutter should show you a list. Choose the appropriate device for your platform.

If everything worked correctly, you should see output like the following:

```shell
Launching lib\main.dart on Windows in debug mode...
Building Windows application...
Syncing files to device Windows...                                 110ms

Flutter run key commands.
r Hot reload.
R Hot restart.
h List all available interactive commands.
d Detach (terminate "flutter run" but leave application running).
c Clear the screen
q Quit (terminate the application on the device).

 Running with sound null safety

An Observatory debugger and profiler on Windows is available at: http://127.0.0.1:2858/QHgqXPo4AOA=/
The Flutter DevTools debugger and profiler on Windows is available at: http://127.0.0.1:9100?uri=http://127.0.0.1:2858/QHgqXPo4AOA=/
```

#### Quitting The Program

To close Worldsmith Studio, either switch to your terminal and press the Q key as directed by the output, or simply close Worldsmith Studio normally.

Be advised that if you close Worldsmith Studio like other programs, you will see the following message:

```shell
Lost connection to device.
```

This is not a bug, it is a standard Flutter message.
