# picoCTF - Secret of the Polyglot

---

## Problem Statement

The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?

---

## Hint

This problem can be solved by just opening the file in different ways

---

## Solution

Download `flag2of2-final.pdf` and first check its actual file type using:

```bash
file flag2of2-final.pdf
```

Even though the file has a `.pdf` extension, the output identifies it as a PNG image. This suggests that the file might contain data from two different formats.

Since the file is also a PNG, try opening it as an image using:

```bash
feh flag2of2-final.pdf
```
The image reveals the first part of the flag.

Now, Open the downloaded PDF directly it contain second part of the flag ,Combine both parts to get the complete flag.

---

## Screenshot

<img width="1600" height="1200" alt="WhatsApp " src="https://github.com/user-attachments/assets/98c36fd7-f67d-4d78-9d5b-bf146e1d1414" />

---

<img width="1170" height="586" alt="Screenshot 2026-11-22 152748" src="https://github.com/user-attachments/assets/8d9ac7d7-ba74-4dd1-b5bb-703d969783a1" />




