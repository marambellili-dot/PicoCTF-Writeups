# Time Machine - picoCTF

## Category

General Skills

## Difficulty

Easy

## Description

The challenge provides a ZIP archive containing a Git repository. The objective is to inspect the repository history and recover the hidden flag.

---

## Files

- challenge.zip

---

## Tools Used

- unzip
- ls
- cat
- git

---

## Solution

### Step 1 - Extract the Archive

Extract the ZIP file.

```bash
unzip challenge.zip
```

---

### Step 2 - Explore the Directory

List the files inside the extracted folder.

```bash
ls
```

A file named `msg.txt` provides the following hint:

```text
This is what I was working on, but I'd need to look at my commit history to know why...
```

This suggests that the flag is stored in the Git history.

---

### Step 3 - Inspect the Git Repository

Verify that the directory is a Git repository.

```bash
ls -a
```

The hidden `.git` directory confirms that Git is being used.

---

### Step 4 - View the Commit History

Display the commit history.

```bash
git log
```

The commit message contains the hidden flag.

---

## Final Flag

```text
picoCTF{t1m3m@ch1n3_186cd7d7}
```

---

## What I Learned

- Extracting ZIP archives with `unzip`.
- Exploring directories using `ls`.
- Recognizing Git repositories through the `.git` folder.
- Viewing commit history with `git log`.
- Understanding that valuable information can be stored in version control history.

---

## Skills

- Linux
- Git
- Version Control
- Command Line
- File Exploration