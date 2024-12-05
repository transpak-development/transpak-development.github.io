---
layout: page
title: Command Line Tools
---

# Command line tools

*in the beginning was the command line*

Modern developers, somewhat ironically, use the venerable command line every day along with their favorite IDE. In this section we will help you install and configure an opinionated set of tools enabling a modern and effective command line workflow to augment the capabilities of your IDE. There are certainly other terminals, shells, and IDEs out there to choose from but we think the options presented here make the most sense for experienced Windows users dedicated to the platform.

In addition to enabling efficient workflows, these command line tools also make following along with a guide like this one a lot simpler. There is nothing more frustrating than referring to dozens of screenshots filled with red markup and yellow highlights that inevitably go a little more out-of-date with each UI update.

> **Note:** The remainder of this guide assumes you have Windows Terminal and Winget installed and that you are using PowerShell to run the commands provided throughout.

## **Windows terminal**

We are going to be spending a lot of time on the command line so before we do anything else let's first install Windows Terminal via the Microsoft Store app. It is lightyears ahead of the venerable windows console and can be [customized ](https://www.hanselman.com/blog/how-to-make-a-pretty-prompt-in-windows-terminal-with-powerline-nerd-fonts-cascadia-code-wsl-and-ohmyposh)to your [heart's content](https://www.hanselman.com/blog/my-ultimate-powershell-prompt-with-oh-my-posh-and-the-windows-terminal).

> **Note**: Windows Terminal is installed by default on Windows 11!

[Install Windows Terminal](https://aka.ms/terminal)

## **Winget**

We are also going to need a package manager. What is a package manager you ask? Well, it's an application you use from the command line to install, upgrade, and remove applications. If you have heard of chocolatey it's like that but made by Microsoft. If you come from the Mac world you can think of it as a Windows version of homebrew.

To install `winget` browse to its release page on GitHub, download the latest **.msixbundle** file, then double-click it. Make sure the version you download is marked **latest release** and isn't an old or preview release.

> **Note**: WinGet is installed by default on Windows 11!

[Download WinGet](https://github.com/microsoft/winget-cli/releases)

> **Note:** You can update any app installed with winget to the latest version with the command `winget upgrade <package>`
>
> The command `winget list <package>` will report the version currently installed and whether an upgrade is available. You can also run `winget list` without specifying a package to check if upgrades are available for any installed package.

## **PowerShell**

Finally, we need to decide on a shell to use within our terminal environment. Since this guide assumes you are using Windows we will stick with Microsoft's default PowerShell environment for now. Other options available include Microsoft's Windows Subsystem for Linux (WSL) and the version of the classic Linux BASH shell installed along with Git. These other options all involve additional setup, however, and come with various limitations and caveats in addition to the advantages they provide in some scenarios.

### Update PowerShell

An older version of *PowerShell* called, confusingly, *Windows PowerShell* is included by default when Windows is installed and can not be upgraded or uninstalled. It is also locked-down by default as it is intended only for system administration. You can use this version if you prefer but to do so and follow along with this guide you will need to loosen these restrictions for the current user by executing the command `Set-ExecutionPolicy RemoteSigned -Scope CurrentUser`

To use the latest release version of PowerShell you can install it using winget :

`winget install Microsoft.PowerShell`

### Update the default PowerShell profile

While there are some amazingly functional and visually appealing ways to [customize your PowerShell prompt](https://www.hanselman.com/blog/my-ultimate-powershell-prompt-with-oh-my-posh-and-the-windows-terminal) we are going to simply update ours using a small script that will display the Git branch associated with the current directory if it is under source control. This will help us determine at a glance if we are working in the correct branch. 

`Invoke-WebRequest -Uri "https://git.io/JXGyz" -OutFile $PROFILE`

### Shell and terminal defaults

To load the latest version of PowerShell by default and / or configure Windows Terminal as your default terminal application navigate to the *Settings* tab in Windows Terminal using the shortcut `Ctrl-,` and set the following values:

![img](/assets/WindowsTerminal-Defaults.png)

[NEXT : Git and GitHub](/git)