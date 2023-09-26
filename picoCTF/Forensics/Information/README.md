# Information

## Overview
Score = 10 Point <br/>
Category = Forensic

## Description
Files can always be changed in a secret way. Can you find the flag? ```cat.jpg```

## Hint
1. Look at the details of the file <br/>
2. Make sure to submit the flag as picoCTF{XXXXX}

### Solution
1. The first step I did was to use exiftool to look at the metadata of the given image <br/> <br/>
```exiftool cat.jpg```<br/>
![image](https://github.com/G34ts/writeups/assets/126637263/9a95bb68-5623-4d50-aed4-a7fd5ed27d19)

2. For the second step, I saw a text for ```cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9``` which could be a Base64 text. Using the ```echo``` function, I will try to print it with the base64 decoder on the terminal. <br/> <br/>
```echo cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9 | base64 -d``` <br/>
![image](https://github.com/G34ts/writeups/assets/126637263/bc686705-234d-42ca-9695-4f732c36ef1d)

```flag```
```text
picoCTF{the_m3tadata_1s_modified}
```
