# 002: A matching line is a clue

**Type:** Teaching demonstration. The sample below is fictional, not a server log.

Searching a file can answer, "Where does this word appear?" It cannot, by itself, answer, "Is this problem happening now?"

## Try it without creating a file

In Bash with grep available, run:

```bash
printf '%s\n' 'Line 1: Confirm the host.' 'Line 2: Confirm the user.' 'Line 3: Confirm the working directory.' | grep -in 'CONFIRM'
```

Expected output:

```text
1:Line 1: Confirm the host.
2:Line 2: Confirm the user.
3:Line 3: Confirm the working directory.
```

- `printf` produces the three sample lines.
- `|` sends that output to the next command.
- `grep` selects matching lines.
- `-i` ignores differences in capitalization.
- `-n` adds the input line number.

The first number comes from grep. The words "Line 1" are part of the sample text.

## Apply the lesson carefully

For a real incident, a matching line needs context: its timestamp, the source, surrounding events, and current system evidence. An old error followed by recovery may no longer describe the machine's state.

## Check your understanding

Remove `-i`. Why does uppercase `CONFIRM` no longer match `Confirm` in this sample?

**Answer:** The search becomes case-sensitive. With no matches, grep normally exits with status 1; that is different from a search error.

## Next question

What surrounding evidence would you inspect before treating a matching error line as an active fault?
