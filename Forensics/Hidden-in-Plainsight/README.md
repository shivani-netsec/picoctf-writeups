# picoCTF - Hidden in Plain Sight

---

##  Problem Statement

You’re given a seemingly ordinary JPG image. Something is tucked away out of sight inside the file. Your task is to discover the hidden payload and extract the flag. Download the jpg image 

---

##  Hints

Download the jpg image and read its metadata

---

##  Solution

Download the provided image and check its file type:

```bash
file img.jpg
```

The output confirms that it is a JPEG image. Next, inspect its metadata using ExifTool:

```bash
exiftool img.jpg
```

Look at the **Comment** field. It contains a Base64-encoded string that may hold hidden instructions.



Decode the first Base64 string using Cybershef tool

The decoded output contains the word `steghide` and another Base64 string. This indicates that Steghide may have been used to hide data inside the image.

Decode the second Base64 string using cybershef

The output reveals the password:

```text
pAzzword
```

Use Steghide to check whether the image contains embedded data:

```bash
steghide --info img.jpg
```

The output confirms that hidden data is present and requires a passphrase.

Use the password obtained earlier to extract the hidden file:

```bash
steghide extract -sf img.jpg -p pAzzword
```

The command extracts a file named `flag.txt`.



Read the extracted file:

```bash
cat flag.txt
```

The file contains the  flag.

---

## Screenshots

<img width="640" height="640" alt="img" src="https://github.com/user-attachments/assets/dfed0ac6-3c0c-4a69-bf4e-1c7eb3282607" />

---

<img width="791" height="645" alt="Screenshot 2026-11-17 152507" src="https://github.com/user-attachments/assets/f71721a5-3cdb-4225-8975-188e8120bb3d" />

---

<img width="1491" height="773" alt="Screenshot 2026-11-17 152604" src="https://github.com/user-attachments/assets/7014e77b-af14-4a71-9119-1864c9218fe5" />

---

<img width="1496" height="799" alt="Screenshot 2026-11-17 152625" src="https://github.com/user-attachments/assets/cf5ed0fd-6044-4596-9e1f-a65f8ed332d5" />




