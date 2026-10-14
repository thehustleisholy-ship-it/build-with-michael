# 003: Where you stand changes what a path means

Here's a detail I'm paying attention to: a relative path depends on where I'm starting.

Take `../reports`. It's easy to read that as "go to the reports folder" and leave it there. But which reports folder?

These are example paths for the lesson:

| Where I'm starting | Path I use | Where it points |
| --- | --- | --- |
| `/tmp/example-lab/scripts` | `../reports` | `/tmp/example-lab/reports` |
| `/tmp/example-lab` | `../reports` | `/tmp/reports` |

Same path typed. Different starting place. Different destination.

## What the pieces mean

`pwd` tells me my current working directory. That's a useful first check when I'm trying to understand where a relative path will lead.

An absolute path, such as `/tmp/example-lab/reports`, starts at the filesystem root. For ordinary shell commands, a relative path usually starts from the current working directory.

`..` means the parent directory. It doesn't automatically know where my project begins.

## Why this matters when I write a script

I need to decide where the script should put its output. Should that location depend on where I run the command, or on where the script itself lives?

Either behavior can make sense. I want to choose deliberately and explain it. Running the script from another directory is a way to check whether it behaves as intended.

## A quick check

If I'm in `/tmp/example-lab/scripts`, where would `./reports` point?

It points to `/tmp/example-lab/scripts/reports`. The single dot means the current directory.

I plan to bring the inventory script into a later entry and show its actual behavior from two different locations. For this note, the example is just a way to make the path rule visible.

[What helped this click for you?](https://github.com/thehustleisholy-ship-it/build-with-michael/discussions)
