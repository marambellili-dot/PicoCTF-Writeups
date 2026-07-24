# Specialer - picoCTF

## Category

General Skills

## Difficulty

Medium

## Description

The challenge provides access to a restricted Linux shell where many common commands are unavailable. The objective is to explore the filesystem using the remaining shell features and recover the hidden flag.

---

## Tools Used

- pwd
- cd
- Bash loops (`for`)
- if / elif
- echo
- printf

---

## Solution

### Step 1 - Explore the Environment

After connecting to the challenge instance, most common Linux commands such as `ls` and `cat` were unavailable.

The commands `pwd` and `cd` were still functional, allowing basic navigation through the filesystem.

---

### Step 2 - Enumerate Files Without `ls`

Since directory listing commands were restricted, a Bash loop was used to identify files and directories.

```bash
for file in *
do
    if [ -d "$file" ]; then
        echo "$file is a directory."
    elif [ -f "$file" ]; then
        echo "$file is a file."
    fi
done
```

This revealed several directories:

- abra
- ala
- sim

---

### Step 3 - Explore Each Directory

Navigate through every directory and inspect its contents.

A second Bash script was used to display the content of every file.

```bash
for folder in abra ala sim
do
    cd "$folder"

    for file in *
    do
        if [ -f "$file" ]; then
            echo "$folder/$file:"
            printf "%s " $(<$file)
            printf "\n\n"
        fi
    done

    cd ..
done
```

The output revealed the hidden flag.

---

## Final Flag

```text
picoCTF{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_a8567b6f}
```

---

## What I Learned

- Working in restricted Linux environments.
- Using Bash scripting when standard commands are unavailable.
- Enumerating files with shell loops.
- Identifying files and directories using Bash conditions.
- Reading file contents without relying on `cat`.

---

## Skills

- Linux
- Bash Scripting
- Command Line
- File Enumeration
- Problem Solving

---

## Key Commands

Current directory:

```bash
pwd
```

Change directory:

```bash
cd directory_name
```

Loop through files:

```bash
for file in *
do
    echo "$file"
done
```

Check whether an entry is a file or directory:

```bash
[ -f filename ]
[ -d directory ]
```

Display file contents using input redirection:

```bash
printf "%s " $(<filename)
```

---

## Notes

This challenge demonstrates that even when common Linux utilities are restricted, Bash built-in features remain powerful enough to explore the filesystem and automate repetitive tasks. Understanding shell scripting is an essential skill for Linux system administration and cybersecurity.