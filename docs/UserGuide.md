# PowerShell for Visual Studio Code - User Guide

![PowerShell extension logo](../images/PowerShell_icon.png)

## Table of Contents

1. [Getting Started](#getting-started)
2. [Editor Concepts](#editor-concepts)
3. [Writing PowerShell](#writing-powershell)
4. [Debugging PowerShell](#debugging-powershell)
5. [Configuring the Extension](#configuring-the-editor-and-extension)
6. [Tips and Tricks](#tips-and-tricks)
7. [Frequently Asked Questions](#frequently-asked-questions)
8. [Troubleshooting](#troubleshooting)

## Getting Started

Welcome to the PowerShell extension for Visual Studio Code!  This extension aims to
provide a complete, high-quality development experience for PowerShell scripts, modules,
and DSC resources.  We are developing this extension as an open-source project on GitHub
so please feel free to [file an issue](https://github.com/PowerShell/vscode-powershell/issues)
if you encounter an issue or if you have any questions or feature requests.

The PowerShell extension works with both the [Stable](https://code.visualstudio.com/) and
[Insiders](https://code.visualstudio.com/insiders) releases of Visual Studio Code.  You can
learn how to install either of these releases in Visual Studio Code's [setup instructions](https://code.visualstudio.com/docs/setup/setup-overview).
Once you've installed Visual Studio Code you can install the PowerShell extension by
[following the instructions](https://github.com/PowerShell/vscode-powershell#installing-the-extension)
in our README.

If you'd like a quick and easy way to install both Visual Studio Code and the PowerShell
extension, try our [quick install script](https://github.com/PowerShell/vscode-powershell#quick-installation)!

## Editor Concepts

> NOTE: This section is currently under development.  Please feel free to
> [file issues](https://github.com/PowerShell/vscode-powershell) for any
> additional content you wish to see in this section.

The Visual Studio Code documentation site provides a [great overview](https://code.visualstudio.com/docs/editor/codebasics)
of the editor and its features.

### Files and Folders

Visual Studio Code is designed around managing projects using file system folders
instead of project files.  This enables individual language extensions to use their
own tooling to manage the experience for a "project" in the editor instead of having
an editor-specific project file.

Visual Studio Code looks for a special folder in your workspace called `.vscode`.  This
folder contains workspace-specific settings for the editor, tasks to execute for your
project (like build scripts or Pester tests) and launch configurations for debugging
your PowerShell scripts.  For best results, this folder should be checked into your
source control repository along with your project's source code.

As this time, you can only have one top-level workspace folder open in a VS Code window.
This is likely to change in the near future as the VS Code team is working on support
for [multi-folder workspaces](https://github.com/Microsoft/vscode/issues/396).

### Command Palette

The Command Palette is a searchable index of all the things you can do in Visual
Studio Code.  It filters down every command in the editor as you type so that you
can find what you're looking for with ease.  For example, typing `PowerShell` will
show you all of the commands with the word "PowerShell" in the name including those
that come with the PowerShell extension.

You can open the command palette by pressing <kbd>F1</kbd> or <kbd>Ctrl+Shift+P</kbd>
(<kbd>Cmd+Shift+P</kbd> on macOS).  You'll be presented with this UI:

![**Command Palette**](../images/Commandpalette.png)

Once you've typed enough to see the command you're looking for, you can use the arrow
keys to navigate the filtered command list.  When you've got the desired command selected
you can execute it by pressing <kbd>Enter</kbd>.

Some commands in Visual Studio Code will use the Command Palette UI to prompt you for
other things like string input or a list of selections to choose from.

**TODO: Image**

TODO: File navigation

### Activity Bar

### Source Control

### Integrated Terminal

### Tasks

### Extensions

#### Recommended Extensions

- [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
- [Vim](https://marketplace.visualstudio.com/items?itemName=vscodevim.vim)
- [Settings Sync](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync)

Check out other [popular extensions](https://marketplace.visualstudio.com/vscode) on
the Visual Studio Marketplace.

## Writing PowerShell

> NOTE: This section is currently under development.  Please feel free to
> [file issues](https://github.com/PowerShell/vscode-powershell) for any
> additional content you wish to see in this section.

### IntelliSense

### Analyzing Your Code

- Syntax analysis
- PSScriptAnalyzer
- Code fixes

### Navigating Around the Code

- Document symbols
- Workspace symbols
- Go to definition
- Find References

### Formatting Your Code

- Formatting the file
- Formatting the selection
- Formatting on save, type, paste

### Expanding Aliases

## Debugging PowerShell

> NOTE: This section is currently under development.  Please feel free to
> [file issues](https://github.com/PowerShell/vscode-powershell) for any
> additional content you wish to see in this section.

## Configuring the Editor and Extension

> NOTE: This section is currently under development.  Please feel free to
> [file issues](https://github.com/PowerShell/vscode-powershell) for any
> additional content you wish to see in this section.

Just about everything in Visual Studio Code is configurable using plain-text files in the
[JSON](https://en.wikipedia.org/wiki/JSON) format.

### User and Workspace Settings

### Editor Settings

- `editor.insertSpaces` - Spaces, not tabs!
- `editor.formatOnSave` - Format your code just before it's saved
- `editor.formatOnType` - Format your code as you type!

- `editor.fontSize`
- `editor.fontFamily`

- `terminal.integrated.fontSize` - Override `editor.fontSize in the integrated terminal
- `terminal.integrated.fontFamily` - Override `editor.fontFamily` in the integrated terminal

### PowerShell Extension Settings

### Recommended Settings

TODO: Write full descriptions

- `files.defaultLanguage`: Set the default language for files created with <kbd>Ctrl+N</kbd>
- `files.autoSave`: Save your files automatically as you edit them, very configurable

## Tips and Tricks

**Please feel free to send pull requests to add more tips and tricks to this section!**

- "Hot Exit": retains unsaved files on exit, restores on next session
- Markdown preview: <kbd>Ctrl+Shift+V</kbd>
- Zen mode: <kbd>Ctrl+K Z</kbd>
- Side by side editing: <kbd>Ctrl+\</kbd>

## Frequently Asked Questions

> NOTE: This section is currently under development.  Please feel free to
> [file issues](https://github.com/PowerShell/vscode-powershell) for any
> additional content you wish to see in this section.


### Why doesn't the debugger hit a breakpoint I added?

### Why can't I remove breakpoints from a file while I'm not debugging a script?

### Why does the integrated console steal focus when I run the current selection (F8)?

### Why can't I select more than the visible region in the integrated console?

https://github.com/Microsoft/vscode/issues/9958

## Troubleshooting

### Windows

#### IntelliSense is extremely slow on PowerShell 5.0

There is a known issue with PowerShell 5.0 which, for a small number of users, causes IntelliSense
(code completions) to return after 5-15 seconds.  The following steps *might* resolve the issue for you:

1. In a PowerShell console, run the following command: `Remove-Item -Force -Recurse $env:LOCALAPPDATA\Microsoft\Windows\PowerShell\CommandAnalysis`
2. Restart Visual Studio Code and try getting IntelliSense again.

This issue has been resolved in PowerShell 5.1.

### macOS (OS X)

#### PowerShell IntelliSense does not work, can't debug scripts

The most common problem when the PowerShell extension doesn't work on macOS is that
OpenSSL is not installed.  You can check for the installation of OpenSSL by looking for
the following files:

If installed using Homebrew:

```
/usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib
/usr/local/opt/openssl/lib/libssl.1.0.0.dylib
```

If installed by some other means:

```
/usr/local/lib/libcrypto.1.0.0.dylib
/usr/local/lib/libssl.1.0.0.dylib
```

The extension should check for these files and direct you to this documentation if you
do not have OpenSSL installed.

##### Installing OpenSSL via Homebrew

We **highly recommend** that you use [Homebrew](http://brew.sh) to install OpenSSL.  The PowerShell distribution for macOS
has built-in support for Homebrew's OpenSSL library paths.  If you install with Homebrew, you will avoid
[security concerns](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md#openssl)
around creating symbolic links in your `/usr/local/lib` path which are needed when using other means of installation.

If you don't already have Homebrew installed, you can do so by downloading and installing Homebrew via this ruby script:

````
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
````

Once Homebrew is installed, run the following command:

```
brew install openssl
```

Restart VS Code after completing the installation and verify that the extension is working correctly.

##### Installing OpenSSL via MacPorts

If you prefer to use [MacPorts](https://www.macports.org/), you can run the following command to install OpenSSL:

```
sudo port install openssl
```

You will need to take an additional step once installation completes:

```
sudo ln -s /opt/local/lib/libcrypto.1.0.0.dylib /usr/local/lib/libcrypto.1.0.0.dylib
sudo ln -s /opt/local/lib/libssl.1.0.0.dylib /usr/local/lib/libssl.1.0.0.dylib
```

Thanks to [@MarlonRodriguez](https://github.com/MarlonRodriguez) for the tip!

Restart VS Code after completing the installation and verify that the extension is working correctly.