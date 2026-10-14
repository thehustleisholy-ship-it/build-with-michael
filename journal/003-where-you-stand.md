# 003: Where you stand changes what a path means

**Type:** Teaching demonstration. These paths describe a hypothetical lab layout.

Consider a lab directory containing a `scripts` folder and a `reports` folder:

| Current working directory | Relative path | Resolves to |
| --- | --- | --- |
| `/tmp/example-lab/scripts` | `../reports` | `/tmp/example-lab/reports` |
| `/tmp/example-lab` | `../reports` | `/tmp/reports` |

The characters in the relative path have not changed. The starting location has.

## Three ideas to separate

- `pwd` tells you the current working directory.
- An absolute path starts at the filesystem root, such as `/tmp/example-lab/reports`.
- A relative path is interpreted from a starting directory, usually your shell's current directory for ordinary shell commands.

`..` means the parent directory. It does not mean "the project root."

## A useful script-design question

Should an output path be relative to the place the user launched the script, or relative to the script's own location?

Either can be intentional. The behavior should be explicit and documented. A script that locates its project directory needs to be demonstrated from more than one working directory.

## Check your understanding

Starting in `/tmp/example-lab/scripts`, where does `./reports` point?

**Answer:** `/tmp/example-lab/scripts/reports`. Here `.` means the current directory.

## Next build evidence

A future inventory-script report will show its actual path handling and two runs from different locations. This note explains the principle without claiming that demonstration is already published.
