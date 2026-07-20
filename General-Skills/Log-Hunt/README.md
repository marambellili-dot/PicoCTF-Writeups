# Log Hunt

## Category
General Skills

## Goal

Find the hidden flag inside a large log file.

## Commands Used

```bash
wget <url>
ls
wc -l server.log
grep "picoCTF" server.log
grep "INFO FLAGPART" server.log
```

## Solution

The log file contained 2348 lines.

I first searched for the keyword "picoCTF" and found the first part of the flag.

Then I searched for "INFO FLAGPART" and recovered the remaining parts.

## Flag

picoCTF{us3_y0urlinux_sk1lls_cedfa5fb}

## What I Learned

- Using grep to search large files.
- Basic log analysis.
- Investigating files in Linux.