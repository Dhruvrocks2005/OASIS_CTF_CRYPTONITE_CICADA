# Heads Up, Tails Down

Opened the file in notepad, then saw the fixme_to_crackme.

![image](https://github.com/user-attachments/assets/0cfc93a6-3381-4003-8554-202174db3b9f)

Then I googled how to fix a corrupted png, what a png is and how it works.

![image](https://github.com/user-attachments/assets/d709935b-0265-47c9-a2fe-c918dff6b8ba)


I found out that the PNG header has a specific format that starts with the following 8-byte signature, followed by chunks like `IHDR`, `sRGB`, `gAMA`, etc.
A valid PNG file always starts with the following 8-byte signature:

```
89 50 4E 47 0D 0A 1A 0A
```

After this signature, the first chunk, `IHDR`, follows, which contains essential information like image width, height, bit depth, etc.

```
89 50 4E 47 0D 0A 1A 0A
00 00 00 0D 49 48 44 52
```
Thus I opened the corrupted PNG file in a hex editor and replaced the first 8 bytes with the correct PNG signature:

![image](https://github.com/user-attachments/assets/31ee5e42-fdc8-411b-a32f-87d81a5e82d7)

![image](https://github.com/user-attachments/assets/f2cd714e-40bb-4732-b8eb-5394abcffa93)

When I opened the edited PNG file, I received the flag:

![W](https://github.com/user-attachments/assets/b83fe85c-1b53-4689-b74c-27d9e278ee1d)

FLag:
```
OASIS{h34d_c4rr135}
```

