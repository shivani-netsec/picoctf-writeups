# picoCTF - RED

---

##  Problem Statement

RED, RED, RED, RED Download the image

---

##  Hints
1.The picture seems pure, but is it though?

2.Red?Ged?Bed?Aed?

3.Check whatever Facebook is called now.

---


##  Solution

Download `red.png` and inspect its metadata using:

```bash
exiftool red.png
```

The metadata contains a poem with an important clue. Looking at the first letters of its lines reveals:

```text
CHECK LSB
```

This indicates that hidden information may be stored in the image's Least Significant Bits.

Use the `zsteg` tool to analyze the PNG image:

```bash
zsteg  red.png
```
The output contains a suspicious Base64 string ,Copy the encoded string:

```text
YWNhZGVteXtyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==
```

Decode the extracted string using CyberChef The decoded output reveals the flag.

---

## Screenshot

<img width="1492" height="735" alt="image" src="https://github.com/user-attachments/assets/b5cad012-8210-4f35-aece-81d093d141c0" />


