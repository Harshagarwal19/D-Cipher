README for CS251 - A9 (Substitution Cipher)

DURGESH AGRAWAL (170262) and HARSH AGARWAL (170287)

The code is divided into three parts : Frequency analysis, Random Swap from Dictionary and Fitness check

How to use: In ghci, call `prime k "string to decode"` to print the decoded output. `k` will be 1 if cipher has only small letters mapped to random chars. It will be 2 if cipher has both small and capital letters, where small letters are mapped to other small letters, and capital letters are mapped to other capital letters.

Call `fitness "decoded string"` to check the fitness of output. Note that the actual fitness will alomost always be more than the answer, since the dictionary being used (10k words) may not contain all words in the passage.

1) Frequency Analysis :

decipher -> main function, calls `mapping`, `subDecipher` and `randomSwap`.

parser -> cleans up the input for easy analysis (punctuations, etc.)

mapping -> creates a mapping from char to char, based on the frequency analysis of characters, and default frequency data extracted from `letterfrequency.org`.

subDecipher -> replaces letters in input by the mapping created by `mapping` function.

2) Random Swap :

randomSwap -> Swaps to letters with close frequency TWICE, if the resulting output is a better fit, then uses the new output, else retains the previous one. Random numbers are chosen from the list of tuples `randData`.

randomSing -> Identical to `randomSwap`, except that it replaces close letters only once in each iteration.

binS -> binary search in the dictionary

3) Fitness :

fitness -> Returns the ratio of words matched in dictBig to total words.