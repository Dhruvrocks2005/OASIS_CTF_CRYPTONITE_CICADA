# A Rocky Start

Got the hint from the description:

```
Sometimes, you need to overflow the memory's expectations to find a way out.
```

I realized that we needed to buffer overflow the name input field.
While experimenting with different inputs, I discovered that the score got set to the ascii value of the input when I entered around 30 of the same character.
Thus I enetered `g` 30 times in the name input field and the score got set to 103, i.e., the ASCII value of `g`.
Once I triggered the overflow with the correct payload, the score was artificially set to 103, unlocking the flag.

Flag:
```
OASIS{D0DG3_4LL_TH3_R0CK5_0R_N07}
```
