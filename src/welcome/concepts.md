# Concepts

Worldsmith Studio is a fairly large program, and it will inevitably use terminology that is unfamiliar. To this end, this chapter attempts to introduce you to various [concepts](#concepts) used by the program.

## Directory

Computers use the words directory and folder interchangeably, to describe a section of your computer's filesystem where files and subdirectories or sub-folders are stored.

Throughout this book, we will adopt the Mac OS X and *x terminology and use the word directory, despite Windows using the word Folder.

## Dart

Worldsmith Studio, as well as its accompanying package [worldsmith](https://pub.dev/packages/worldsmith) are both written in [Dart](https://dart.dev/). This is a programming language created by Google.

Any scripting of your game will also be done with Dart.

## Project

A project refers to the overall [directory](#directory) on your computer where your world file and assets are stored.

A project consists of a few things:

### Project File

This is a single file which is stored as [JSON](https://www.json.org/). It holds the information about your world.

You can open this file in any standard text editor, although you are entirely responsible for any damage to your project arising from making edits to it.

### Assets Directory

This is the directory where your sound files will be encrypted and stored.

It will contain sequentially numbered files and directories.

### Game Directory

If you have used the `worldsmith build` command, you will additionally have a game directory, where generated [source code](#dart) will reside.

If you are running under Windows, this directory will also contain a .exe file which you can use to play your game without needing Dart installed.

## World

A world is the game you are creating. This includes all [zones](../projects/settings/../zones.md), and [commands](../projects/commands.md).

## Asset Store

An asset store is like a directory. It contains 0 or more [assets](#assets).

Worldsmith defines several asset stores which are used for specific things in your world. You can read more about these in the [asset stores](../projects/asset_stores.md) section.

## Assets

An asset is an encrypted file which you can use in your world.

Assets are stored in [asset stores](#asset-store).

They can represent either a single file or a directory.

Each asset is encrypted using Dart's [encrypt](https://pub.dev/packages/encrypt) package, and each one uses a randomly generated encryption key, so no two are the same.

Please note that while Worldsmith Studio does encrypt assets, no guarantees are given about the security of any assets you bundle with your [world](#world). The encryption keys for all assets are stored in plain text in your [project file](#project-file), and the encryption key for the encrypted world file is stored in plain text in the generated [source code](#game-directory). As such, if you give either the project file, or the generated source code to another person, they will be able to decrypt your world and its assets.

Worldsmith Studio attempts to mitigate this by generating a new encryption key and re-encrypting your world file every time you build your world, but you are fully responsible for any content created with this program.
