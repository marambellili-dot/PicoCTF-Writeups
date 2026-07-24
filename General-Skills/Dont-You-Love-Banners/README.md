# Don't You Love Banners - picoCTF

## Category

General Skills

## Difficulty

Medium

## Description

The challenge demonstrates how information exposed through service banners can reveal useful credentials. The objective is to analyze the banner, authenticate to the remote machine, answer a few verification questions, and retrieve the flag.

---

## Tools Used

- telnet
- ssh
- ls
- cd
- cat

---

## Solution

### Step 1 - Inspect the Banner

Connect to the service using Telnet.

```bash
telnet <host> <port>
```

The banner displays information that includes a password.

---

### Step 2 - Connect via SSH

Use the recovered credentials to connect to the remote machine.

```bash
ssh <username>@<host> -p <port>
```

When prompted, enter the password obtained from the banner.

---

### Step 3 - Answer the Questions

After logging in, the system asks several cybersecurity-related questions.

Example:

- Largest cybersecurity conference
- Famous hacker associated with phone phreaking

Providing the correct answers grants access to the user account.

---

### Step 4 - Locate the Flag

Navigate through the filesystem.

```bash
pwd
ls
cd
```

The flag file is located inside the `/root` directory.

---

### Step 5 - Retrieve the Flag

After obtaining the required privileges, read the flag.

```bash
cat /root/flag.txt
```

---

## Final Flag

```text
picoCTF{...}
```

Replace the dots with the flag you obtained.

---

## What I Learned

- Understanding service banners.
- Gathering information during enumeration.
- Connecting to remote systems with SSH.
- Basic Linux navigation.
- The importance of avoiding sensitive information leakage in banners.

---

## Skills

- Linux
- SSH
- Telnet
- Information Gathering
- Enumeration
- Command Line

---

## Key Commands

Connect with Telnet:

```bash
telnet host port
```

Connect with SSH:

```bash
ssh username@host -p port
```

Display current directory:

```bash
pwd
```

List files:

```bash
ls
```

Change directory:

```bash
cd
```

Read a file:

```bash
cat filename
```

---

## Notes

Service banners may unintentionally reveal sensitive information such as software versions, usernames, passwords, or configuration details. In penetration testing, banner grabbing is often one of the first enumeration techniques performed because it can provide valuable information before any exploitation attempt.