# 002: A matching line is a clue

One thing I'm learning is to be careful about how much I conclude from a command's output.

With grep, I can find a line that contains a word. That's useful. But if the word is "error," I still need to find out when it happened and what's happening now.

Here's a small example to work through. The text is made up for the exercise; it isn't a server log.

## Try this

In Bash with grep available, run:

```bash
printf '%s\n' 'Line 1: Confirm the host.' 'Line 2: Confirm the user.' 'Line 3: Confirm the working directory.' | grep -in 'CONFIRM'
```

You should see:

```text
1:Line 1: Confirm the host.
2:Line 2: Confirm the user.
3:Line 3: Confirm the working directory.
```

There's a reason for each piece:

- `printf` produces the three lines.
- `|` passes that output to grep.
- `grep` finds matching lines.
- `-i` makes capitalization irrelevant to this search.
- `-n` adds the input line numbers.

That first `1:` is from grep. The words "Line 1" were already in the sample text.

## The part I want to remember

A match gives me somewhere to look more closely.

With a real log, I'd need the timestamp, the source, the lines around it, and fresh evidence from the system. There may have been a recovery after the error. There may be something else going on entirely.

That's a habit worth learning while the examples are still small.

## Change one thing

Remove the `i` from `-in`, leaving `-n`, and run it again.

There should be no matching output. Without `-i`, uppercase `CONFIRM` doesn't match `Confirm`. Grep normally returns exit status 1 when it finds no matches; that doesn't mean the search itself failed with an error.

What would you check next if this were a real error message?

[Share your approach](https://github.com/thehustleisholy-ship-it/build-with-michael/discussions).
