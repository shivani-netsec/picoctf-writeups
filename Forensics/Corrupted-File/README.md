
# picoCTF - Corrupted File

---

##  Problem Statement

This file seems broken... or is it? Maybe a couple of bytes could make all the difference. Can you figure out how to bring it back to life?

---

##  Hints

1. Try checking the file’s header.
2. JPEG
3. Tools like xxd or hexdump can help you inspect and edit file bytes.

---

##  Solution

### Identifying the File

Open [HexEd.it](https://hexed.it/) and upload the corrupted file. HexEd.it displays the raw contents of the file in hexadecimal format.

While inspecting the file, the text `JFIF` appears in the ASCII column. JFIF (JPEG File Interchange Format) is a standard format used by JPEG images. This indicates that the file is probably a JPEG image, even though it cannot be opened normally.

### Understanding the Corrupted File Signature

Every file format has a specific signature, also called magic bytes, that helps the operating system and applications identify the file type.

A normal JPEG file starts with these four bytes:

```text
FF D8 FF E0
```

However, the provided file starts with:

```text
5C 78 FF E0
```

The first two bytes are incorrect. The remaining two bytes already match the expected JPEG signature.

Since applications use these starting bytes to recognize the file format, the incorrect header prevents the file from being identified properly as a JPEG image.

### Repairing the File

In HexEd.it, modify the first four bytes to match the correct JPEG signature:

```text
FF D8 FF E0
```

The first four bytes are part of the JPEG file header. Replacing them restores the expected starting signature, allowing image viewers to recognize the file as a JPEG.

Download the modified file and change its extension to `.jpeg`. Open the image.

The flag is displayed inside the image:

---

## Screenshots
