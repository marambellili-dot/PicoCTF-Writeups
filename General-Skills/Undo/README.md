# Undo - picoCTF

## Category

General Skills

## Difficulty

Easy

## Description

The challenge provides a remote service that applies several text transformations to a flag. The objective is to reverse each transformation using Linux commands and recover the original flag.

---

## Challenge Information

- Host: foggy-cliff.picoctf.net
- Port: 61414

Connection:

```bash
nc foggy-cliff.picoctf.net 61414
```

---

## Tools Used

- nc
- base64
- rev
- tr

---

## Solution

### Step 1 - Decode Base64

The first transformation was Base64 encoding.

```bash
echo "TEXT" | base64 -d
```

---

### Step 2 - Reverse the Text

The service indicated that the text had been reversed.

```bash
echo "TEXT" | rev
```

---

### Step 3 - Replace Dashes with Underscores

The original underscores had been replaced with dashes.

```bash
echo "TEXT" | tr '-' '_'
```

---

### Step 4 - Restore Curly Braces

The original curly braces had been replaced with parentheses.

```bash
echo "TEXT" | tr '()' '{}'
```

---

### Step 5 - Decode ROT13

The final transformation was ROT13.

```bash
echo "TEXT" | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

---

## Final Flag

```text
picoCTF{Revers1ng_t3xt_Tr4nsf0rm@t10ns_5469b5d2}
```

---

## What I Learned

- Working with remote services using `nc`.
- Decoding Base64 data.
- Reversing text with `rev`.
- Replacing characters using `tr`.
- Understanding the ROT13 cipher.
- Solving chained text transformations in the correct reverse order.

---

## Skills

- Linux
- Command Line
- Text Processing
- Base64
- ROT13
- Problem Solving