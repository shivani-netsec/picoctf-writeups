# picoCTF - Flag in Flame

---

##  Problem Statement

The SOC team discovered a suspiciously large log file after a recent breach. When they opened it, they found an enormous block of encoded text instead of typical logs. Could there be something hidden within? Your mission is to inspect the resulting file and reveal the real purpose of it. The team is relying on your skills to uncover any concealed information within this unusual log. Download the encoded data here: Be prepared—the file is large, and examining it thoroughly is crucial .

---

##  Hints

Use base64 to decode the data and generate the image file.

---


##  Solution

Download the provided `logs.txt` file. Although it looks like a large collection of meaningless characters, the challenge hint suggests that the data is Base64-encoded.

Use  CyberChef  to decode it 

Base64 converts binary data into readable text. Decoding it restores the original binary data, which in this challenge is a png image.


Open `download.png`. The image contains a long hexadecimal string at the bottom.

Copy this string. It represents another encoded message.


Use CyberChef and select **From Hex** to convert the hexadecimal string into readable text.

The decoded output reveals the flag:

---

##  Screenshot

<img width="896" height="1152" alt="download" src="https://github.com/user-attachments/assets/05abe58b-8347-4e3e-9ffc-e66dc2cfc139" />

---

<img width="1503" height="815" alt="Screenshot 2026-11-17 152059" src="https://github.com/user-attachments/assets/49142f82-ae02-497f-8fea-e9282acc32da" />


