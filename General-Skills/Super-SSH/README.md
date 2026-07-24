# Super SSH - picoCTF

## Category

General Skills

## Difficulty

Easy

## Description

The challenge introduces the Secure Shell (SSH) protocol. The objective is to connect to a remote Linux server using the provided credentials and retrieve the hidden flag.

---

## Tools Used

- ssh
- Linux Terminal

---

## Solution

### Step 1 - Connect to the Remote Server

Use the provided username, host, and port to establish an SSH connection.

```bash
ssh <username>@<host> -p <port>
```

When prompted, enter the password provided by the challenge.

---

### Step 2 - Retrieve the Flag

After successfully connecting to the remote machine, the flag is displayed or can be accessed from the user's session.

---

## Final Flag

```text
picoCTF{...}
```

Replace the dots with the flag you obtained.

---

## What I Learned

- Understanding the purpose of the SSH protocol.
- Connecting to a remote Linux machine from the command line.
- Using the `ssh` command with a custom port.
- Authenticating with a username and password.
- Basic remote system access.

---

## Skills

- Linux
- SSH
- Remote Access
- Command Line
- Networking

---

## Key Command

Connect to a remote machine:

```bash
ssh username@hostname -p port
```

Example:

```bash
ssh maram@example.com -p 2222
```

---

## Notes

SSH (Secure Shell) is a secure protocol used to remotely access Linux and Unix systems. It encrypts communication between the client and the server, making it one of the most common tools used by system administrators, network engineers, and cybersecurity professionals.