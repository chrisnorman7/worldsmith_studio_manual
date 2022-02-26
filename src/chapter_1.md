# Chapter 1

## Outline

Worldsmith Studio is a fairly large program, and it will inevitably use terminology that is unfamiliar. To this end, this chapter attempts to introduce you to various [concepts](#concepts) used by the program.

## Concepts

### Directory

Computers use the words directory and folder interchangeably, to describe a section of your computer's filesystem where files and subdirectories or sub-folders are stored.

Throughout this book, we will adopt the Mac OS X and *x terminology and use the word directory, despite Windows using the word Folder.

### Dart

Worldsmith Studio, as well as its accompanying package [worldsmith](https://pub.dev/packages/worldsmith) are both written in [Dart](https://dart.dev/). This is a programming language created by Google.

Any scripting of your game will also be done with Dart.

### Project

A project refers to the overall [directory](#directory) on your computer where your world file and assets are stored.

A project consists of a few things:

#### Project File

This is a single file which is stored as [JSON](https://www.json.org/). It holds the information about your world.

You can open this file in any standard text editor, although you are entirely responsible for any damage to your project arising from making edits to it.

#### Assets Directory

This is the directory where your sound files will be encrypted and stored.

It will contain sequentially numbered files and directories.

#### Game Directory

If you have used the `worldsmith build` command, you will additionally have a game directory, where generated [source code](#dart) will reside.

If you are running under Windows, this directory will also contain a .exe file which you can use to play your game without needing Dart installed.
