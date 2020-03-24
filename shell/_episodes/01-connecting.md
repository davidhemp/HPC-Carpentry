---
title: "Connecting to the remote HPC system"
teaching: 20 
exercises: 10
questions:
- "How do I open a terminal?"
- "How do I connect to a remote computer?"
objectives:
- "Connect to a remote HPC system."
keypoints:
- "To connect to a remote HPC system using SSH: `ssh yourUsername@remote.computer.address`"
---

## Opening a Terminal

Connecting to an HPC system is most often done through a tool known as "SSH" (Secure SHell) and
usually SSH is run through a terminal. So, to begin using an HPC system we need to begin by opening
a terminal. Different operating systems have different terminals, none of which are exactly the same
in terms of their features and abilities while working on the operating system. However each time you connect to the same remote system with a new terminal the experience will be identical as each will faithfully present
the same experience of using that system.

Here is the process for opening a terminal in each operating system.

### Linux

There are many different versions (aka "flavours") of Linux and how to open a terminal window can
change between flavours. A quick search on the Internet for "how to open a terminal window in" with your
particular Linux flavour appended to the end should give you the directions you need.

A very popular version of Linux is Ubuntu. There are many ways to open a terminal window in Ubuntu
but a very fast way is to use the terminal shortcut key sequence: Ctrl+Alt+T.

### Mac

Macs have had a terminal built in since the first version of OS X (now macOS) as it is
built on a UNIX-like operating system, leveraging many parts from BSD (Berkeley Systems Designs).
The terminal can be quickly opened through the use
of the Searchlight tool. Hold down the command key and press the spacebar. In the search bar that
shows up type "terminal", choose the terminal app from the list of results (it will look like a
tiny, black computer screen) and you will be presented with a terminal window. Alternatively, you
can find Terminal under "Utilities" in the Applications menu.

### Windows

If you are using Windows, you should have installed Git Bash as part of the [setup for this course](../setup/) which includes
an SSH client you can use in the same way as for Linux and Mac. Open the Git Bash program to 
get terminal access.

## Logging onto the system

With all of this in mind, let's connect to a remote HPC system. In this workshop, we will connect to
{{ site.workshop_host }} --- an HPC system located at the {{ site.workshop_host_location }}. Although it's unlikely
that every system will be exactly like {{ site.workshop_host }}, it's a very good example of what you can expect from
an HPC installation. To connect to our example computer, we will use SSH.

SSH allows us to connect to UNIX computers remotely, and use them as if they were our own. The
general syntax of the connection command follows the format `ssh yourUsername@some.computer.address`
Let's attempt to connect to the HPC system now:

```
ssh yourUsername@{{ site.workshop_host_login }}
```
{: .language-bash}

```{.output}
{% include /snippets/01/login_output.{{ site.workshop_host_id }} %}
```

If you've connected successfully, you should see a prompt like the one below. This prompt is
informative, and lets you grasp certain information at a glance. (If you don't understand what these things are,
don't worry! We will cover things in depth as we explore the system further.)

```{.output}
{{ site.workshop_host_prompt }}
```

## Telling the Difference between the Local Terminal and the Remote Terminal

You may have noticed that the prompt changed when you logged into the remote system using the
terminal (if you logged in using PuTTY this will not apply because it does not offer a local
terminal). This change is important because it makes it clear on which system the commands you type
will be run when you pass them into the terminal. This change is also a small complication that we
will need to navigate throughout the workshop. Exactly what is reported before the `$` in the
terminal when it is connected to the local system and the remote system will typically be different
for every user. We still need to indicate which system we are entering commands on though so we will
adopt the following convention:

- `[local]$` when the command is to be entered on a terminal connected to your local computer
- `{{ site.workshop_host_prompt }}` when the command is to be entered on a terminal connected to the remote system
- `$` when it really doesn't matter which system the terminal is connected to.

> ## Being certain which system your terminal is connected to
>
> If you ever need to be certain which system a terminal you are using is connected to then use the
> following command: `$ hostname`.
{: .callout}

> ## Keep two terminal windows open
>
> It is strongly recommended that you have two terminals open, one connected to the local system and
> one connected to the remote system, that you can switch back and forth between. If you only use
> one terminal window then you will need to reconnect to the remote system using one of the methods
> above when you see a change from `[local]$` to `{{ site.workshop_host_prompt }}` and disconnect when you see the
> reverse.
{: .callout}
