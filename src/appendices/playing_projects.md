# Appendix 2: Playing Projects

It is possible to play through the projects you have created without [building](building_projects.md) them.

To do this, you need to use the `worldsmith` command line tool. If you haven't already got that installed, see the [Installing Worldsmith](installing_worldsmith.md) section.

## Getting Started

First, you'll need to know the directory where your worldsmith project has been created. Fir example, if your world file resides at `C:\Users\chris\src\RPG\project.json`, the directory you'll need is `C:\Users\chris\src\RPG`.

## Changing Directory

Begin by opening up your command prompt or terminal, and changing directories:

```shell
cd project_directory
```

Your prompt should change to alert you to the fact that your directory has changed.

### Windows Tip

If this command does not work on Windows, try the `pushd` command instead:

```shell
pushd project_directory
```

You command prompt should now show the directory you just gave.

### Playing Your Game

If you used the default filename (`project.json`) during [project creation](../projects/creating_a_project.md), it should now be enough to type `worldsmith` play.

If you chose a different filename, either rename the project file to `project.json`, or tell the `worldsmith` command what the filename is:

```shell
worldsmith play -f game.json
```

## Getting Help

To get more help from the program, type `worldsmith play -h`.
