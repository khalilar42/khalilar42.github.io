---
title: What the hell is zsh?
description: Learn what a shell, terminal, and CLI are, and discover the specifics of Zsh.
date: 2026-03-25 21:05
categories: [tech]
tags: [shell]
toc: true
image:
  path: assets/img/2026-03-25-what-the-hell-is-zsh/lukas-MU8w72PzRow-unsplash.jpg
  alt: Photo by <a href="https://unsplash.com/@lukash?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Lukas</a> on <a href="https://unsplash.com/photos/a-computer-screen-with-a-lot-of-data-on-it-MU8w72PzRow?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
      
  
---

In my life I work as a QA Automation engineer, I write a lot of code to automate test cases on different platforms.

In my work I use a terminal, and I have this thing called zsh, I never knew what is it, so I decided to search a bit for it and try to understand it, and why I have to change this .zshrc file and source it.

### Okay, first things first: what is a shell?

A shell is the hard, protective outer layer (exoskeleton) created by marine mollusks, such as clams, snails, and oysters, primarily composed of calcium carbonate.. ow my bad we're not talking about these shells 🐚.

Seriously, a shell is a computer program that provides direct access to the system it runs on. It lets you talk to your computer by executing commands and scripts.

Now, let’s clear up some terms that people often confuse: shell, CLI, and terminal.
- a shell is the program that interpret/execute the commands/action you give it
- a CLI (command line interpreter/interface) is a mean to communicate with any software via commands.
- a terminal (aka terminal emulator) : is the actual window or application where you type commands, like Warp, Wezterm, Ghosty, Windows terminal, and so on.

From this definition, we can conclude that every shell is a CLI, but not every CLI is a shell.

### zsh or zeee shell

Zsh stands for Z shell. Its creator, **Paul Falstad** had a teaching assistant named *Zhong Shao*, whose username on the system was “zsh.” Paul thought it was a cool, short name for a shell, so he used it. He wrote the first version of Zsh in 1990 while he was a student at Princeton University. *Meanwhile, I was busy playing League of Legends—I hit gold or platinum for the first time, can't remember, but statistically, I was in the top 20%, so I must be proud! 😅*

So, Zsh (or Z shell) is a specific implementation of a Unix-like shell. It helps you execute programs and scripts, manage files, and interact with the system more efficiently. 

On macOS, Zsh is the default shell, other popular shells include Bash, csh/tcsh, PowerShell for Windows.

A shell has a lot of commands (programs/tools) that you can use to do multiple things you need in your everyday life, like  `cd`, `ls`, `grep`, `chmod`, etc.

But what really happens when you type `cd Desktop` or `ls Desktop` ? 

As mentioned earlier, `cd` and `ls` are just programs, but how does your shell find them? And why don't they have an extension? You know, when we have a executable windows program, it has a .exe file extension, right?

Well its because these program are not source files but precompiled files ready to be executed and saved in a specific directory depending on your operating system, how does the shell find this specific directory ?

It has something called an environment variable. One very useful env variable is PATH. This variable holds the path to the folder that contains these programs, not only the ones you use in your shell, but multiple others. For example, if I try to print its content on my computer, I get:

```shell
echo $PATH
/Users/username/.gem/ruby/3.4.1/bin:/Users/username/.rubies/ruby-3.4.1/lib/ruby/gems/3.4.0/bin:/Users/username/.rubies/ruby-3.4.1/bin:/Library/Java/JavaVirtualMachines/jdk-11.0.20.jdk/Contents/Home/bin:/Applications/AppName.app/Contents/SharedSupport/bin:/opt/homebrew/bin:/opt/homebrew/sbin:/usr/local/bin:/System/Cryptexes/App/usr/bin:/usr/bin:/bin:/usr/sbin:/sbin:/var/run/com.apple.security.cryptexd/codex.system/bootstrap/usr/local/bin:/var/run/com.apple.security.cryptexd/codex.system/bootstrap/usr/bin:/var/run/com.apple.security.cryptexd/codex.system/bootstrap/usr/appleinternal/bin:/opt/pmk/env/global/bin:/Library/Java/JavaVirtualMachines/jdk-11.0.20.jdk/Contents/Home/bin:/Users/username/.local/bin:/Applications/AppName.app/Contents/SharedSupport/bin:/Applications/AppName.app/Contents/MacOS:/Applications/AppName.app/Contents/Resources/app/bin:/Applications/AppName.app/Contents/Resources/app/bin
```

Which are a lot of directory paths separated by a `:`; so when you type in your shell `echo`, the shell will look through the programs in the different paths inside the PATH variable, and then it will run it. But what if you have multiple instances of the same program in different paths? What if echo is present in bin1 and bin2 folders?

Well, your shell will just execute the first program it finds in the path variable by order. If bin1 is the first path in the PATH variable, it will execute that one!

### what is .zshrc ?

Now if you have worked previously with a your zshell, you have for sure once in your life had to install some program that asked you to past something in your .zshrc file and save it then do the command `source .zshrc` file in your shell but why is that and what is the use of .zshrc in the first place ? 

`.zshrc` is a configuration file for your z shell, It contains settings, environment variables, and customizations that load every time you start a new shell session, 

So when you modify it you are essentially adding extra configuration to be run every time you open a new shell, and when you do the command `source .zshrc` you're reloading you configuration file and resetting your shell this way it will take into consideration the new changes on your config file.


### Conclusion

zsh, is just a specific implementation of a shell, a shell is a command-line interface (CLI) that lets you interact with your computer/operating system using commands, the terminal is the program that provides a text-based interface that lets you interact with the shell, the different commands you use are just multiple programs that are already precompiled and present in your computer (or scripts/functions defined by the user or other applications). Finally .zshrc is your shell configuration file that help you customize your z shell experience.



