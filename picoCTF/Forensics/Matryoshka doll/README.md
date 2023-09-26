# Matryoshka doll

## Overview
Score = 30 Point <br/>
Category = Forensic

## Description
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: this

## Hint
1. Wait, you can hide files inside files? But how do you find them? <br/>
2. Make sure to submit the flag as picoCTF{XXXXX}

#### Solution
1. The first step I did was to look at the hint of this challenge. The hint told me that there was a secret file inside the picture given. Then we will use a tool called ```Binwalk``` to get the secret file out of this ```doll.jpg``` image.<br/> <br/>
But before doing the binwalk, I will look at some of the functions that can be used in binwalk using the ```binwalk --help all``` command. <br/> <br/>
```binwalk --help all```<br/>
![image](https://github.com/G34ts/writeups/assets/126637263/9bea908a-2c16-4563-b5fc-afd155737d7f)
And it turns out that in the extraction option there is a function in binwalk that has the same name as this challenge. It's worth a try, at the same time I will use the ```-e``` function to extract the hidden files in the image.<br/> <br/>

2. The second step is to run the binwalk command against the dolls.jpg image. The command to use is ```binwalk -eM dolls.jpg```.<br/> <br/>
```binwalk -eM dolls.jpg```<br/>
![image](https://github.com/G34ts/writeups/assets/126637263/2c3f8584-ffc3-4b91-abbd-903cdb4dbaa2)

3. And as we can see from the output, there is a ```flag.txt``` inside the ```4_c.jpg``` folder. So we will change our terminal directory to ```4_c.jpg``` and open ```flag.txt``` in that folder. <br/> <br/>
```cd _dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted```<br/>
```ls -la```<br/>
```./flag.txt``` <br/>
![image](https://github.com/G34ts/writeups/assets/126637263/37759f0b-d1c5-4f6a-a5e9-f4231155ad2b)
But as we can see, the terminal cannot open flag.txt because it does not have permission. then we will use the cat command to read this flag.txt. <br/> <br/>
```cat flag.txt```<br/>
![image](https://github.com/G34ts/writeups/assets/126637263/9a6e2c52-9244-46a9-a57f-0108b130b4b2)

```flag```
```text
picoCTF{bf6acf878dcbd752f4721e41b1b1b66b}
```


 
