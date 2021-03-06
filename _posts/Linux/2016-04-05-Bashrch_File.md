---
layout: post
title: Bashrch File
subtitle: What is .bashrch File ?
category: Linux
tags: [shell, command]
permalink: /2016/04/05/Bashrch_File/
---

the following refers to <a href ="http://unix.stackexchange.com/questions/129143/what-is-the-purpose-of-bashrc-and-how-does-it-work">stackexchange</a>

.bashrc is a shell script that Bash runs whenever it get started interactively. You can put any command in that file that you could type at the command prompt.

You put commands here to set up the shell for use in your particular environment, or to custoize things to your preferences.

A common thing to put in .bashrc are aliases that you want to always be available.

.bashrc runs on every interactive shell launch. for example,

$ bash ; bash ; bash

and then hit "Ctrl+d" three times, .bashrc will run three times.

But if you say this instead :

$ bash -c exit ; bash -c exit ; bash -c exit 

then .bashrc won't run at all, since -c makes the Bash call non-interactive. the same is true when you run a shell script from a file.

Contrast .bash_profile and .profile which are only run at the start of a new login shell. 

(bash -l) You choose whether a command goes in .bashrc vs .bash_profile depending on whether you want it to run once or for every interactive shell start.

As a counterexample to ailases, which I prefer to put in .bashrc, you want to do PATH adjustments in ./bash_profile instead, since these changes are typically not idempotent :

export PATH="$PATH:/some/addition"


If you put that in .bashrc instead, every time you launched an interactive sub-shell, :/some/addition would get tacked on to the end of the PATH again, creating extra work for the shell when you mistype a command.

You get a new interactive Bash shell whenever you shell out of vi with :sh, for example.
