# Printer Shares

## Category

General Skills

## Difficulty

Easy

## Description

A network printer was exposing files through an SMB share. The objective was to retrieve the hidden flag.

## Tools Used

- nc
- smbclient
- cat

## Connectivity Check

```bash
nc -vz mysterious-sea.picoctf.net 53888
```

The connection succeeded, confirming that the service was online.

## Enumerate SMB Shares

```bash
smbclient -L //mysterious-sea.picoctf.net -p 53888 -N
```

Discovered share:

```text
shares
```

## Connect to the Share

```bash
smbclient //mysterious-sea.picoctf.net/shares -p 53888 -N
```

## List Files

```bash
ls
```

Output:

```text
dummy.txt
flag.txt
```

## Retrieve the Flag

```bash
get flag.txt
exit
cat flag.txt
```

## Flag

```text
picoCTF{5mb_pr1nter_5h4re5_7a400ec3}
```

## What I Learned

- Basic SMB enumeration.
- Using smbclient to access shared resources.
- Anonymous SMB access risks.
- Importance of checking available network services.
- Difference between network connectivity testing and protocol-specific tools.

## Key Concepts

- SMB (Server Message Block)
- Network Shares
- Service Enumeration
- File Retrieval