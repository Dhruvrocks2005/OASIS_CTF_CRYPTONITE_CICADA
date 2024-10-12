# Comma Separated … Virus?

Went on a wild goose chase and wasted time due to misleading description:
```
Using the basics of machine learning, perform exploratory data analysis
to try and figure out a pattern. Can you find the virus among the data?
```
Thought that we need to make a histogram in descending frequency of the values on the VAL column since `O` had the highest frequency in the column.
(I have no idea why I did that. In hindsight, it is very dumb)

![74363e5f-2448-417f-978a-1a7de721228c](https://github.com/user-attachments/assets/68438b7d-a33f-4f5f-a174-058eb9419b27)
![00f96bf5-0c47-4bbe-8d55-9ff5cd6ec296](https://github.com/user-attachments/assets/ff37a8b0-17fe-4c64-bb37-4f9936e82a00)
![2f908f4f-2471-4c19-9f2a-0561e59c7cc5](https://github.com/user-attachments/assets/2937302c-f16e-4ca4-8ea3-f4fa8f3ee58e)

Gave up performing EDA and creating a machine learning model. Tried to find clues in the excel sheet itself.

Knew that the flag would be found in the `VAL` column since it was the only one which had `{` and `}`.
Thought that the `TUNE` column had something to do with it since they both had 10000 entries while the `SCORE` column had 1048575 entries.

![image](https://github.com/user-attachments/assets/bdcd8f9c-5968-402a-bc2a-ecfcf981caab)

Sorted the excel sheet by `TUNE` in ascending order and descending order and found the flag.

![image](https://github.com/user-attachments/assets/cce1d01e-750c-49ce-8218-176986180603)

Flag:
```
OASIS{TROJAN}
```
