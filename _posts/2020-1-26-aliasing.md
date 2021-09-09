---
layout: post
title: Revamp your CLI experience with Aliases.
description: Demystifying ZSH aliases.
---


Working with CLI is great, but writing very long or repetitive commands is somewhat exhausting. That’s why we have aliases, so that we don’t have to write long lines of commands repeatedly. 
  
We all know the Bourne shell but, in usability and customization aspect, one of the most popular options out there is the ZSH or the z-shell.

## Installation   
Starting with macOS 10.6 Catalina, Macs will use ZSH as the default login shell and interactive shell.
Follow the steps below to install it in your Linux machine. If you have already, you're good to skip this part.
  
```bash
$ sudo apt-get update
# install ZSH
$ sudo apt-get install -y zsh
# check ZSH version
$ zsh --version  
# change your current shell to ZSH
$ chsh -s $(which zsh)
```
  
  
## ZSH Aliases
  
Whether you are typing out very long commands, e.g. SSH login or be the repetitive commands such as `git status` or `git pull origin master`, we all know how daunting this it is. Aliases are a saviour here. You can create custom commands and use them as standard CLI commands. Without further adieu, let us create an alias!
  
```bash
# go home
$ cd
# open .zshrc
$ vim .zshrc
```
  
Let us create an alias to SSH login, add the following line at the end of `.zshrc` file.
  
```bash
alias quickssh='ssh username@domain'
```
  

I work with [Visual Studio Code]; it uses the [integrated shell instead of the login shell] in the IDE. For the aliases to work inside VS Code IDE, we must use the login shell instead of the integrated shell. So, add the following line at the end of `.zshrc` file and save it.
  
```bash
# for OS X users
"terminal.integrated.shellArgs.osx": [ "-l" ]
  
# for Linux users
"terminal.integrated.shellArgs.linux": ["--login"]
```
  
To refresh the shell environment, close the current terminal tab and open a new one. And now you are good to go!

## Footnotes
* [What goes into .zshenv, .zshrc, .zlogin, .zprofile, .zlogout?]
* [Alias with parameters & Global Alias Expansion.]


[What goes into .zshenv, .zshrc, .zlogin, .zprofile, .zlogout?]: https://unix.stackexchange.com/a/487889
[integrated shell instead of the login shell]: https://unix.stackexchange.com/a/46856
[Visual Studio Code]: https://code.visualstudio.com
[Alias with parameters & Global Alias Expansion.]: https://blog.lftechnology.com/command-line-productivity-with-zsh-aliases-28b7cebfdff9
<!-- vim: set tw=90 sts=-1 sw=4 et spell wrap: -->