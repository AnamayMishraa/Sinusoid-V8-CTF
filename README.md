# Sinusoid-V8-CTF

​
 




Sinusoid V8 | Tech Fest NIIT
https://sinusoid.in/events/captureTheFlag
 

Description:
The objective of this event is to find hidden information by overcoming various obstacles that could include vulnerabilities, or analyzing digital artifacts within a system. Participants will earn points for each challenge completed, with more difficult problems awarding more points. Each challenge is associated with a unique flag that consists of a string of text which they must find or generate by completing it. Once a flag is found, participants submit it through the competition platform. The system then verifies the flag’s correctness, and points are awarded based on the challenge’s difficulty.

 

• Category : Sanity Check
 

1. Social Sinusoid
Follow Sinusoid.nu on instagram and keep an eye out for the flag.

 




ciberNUsoid{Sh4p3_th3_V1ct0ry}

 

2. Ciber Capture
Our Ciber Chef is cooking someting !

https://pastebin.com/dN6avfx6

a8763963d25e9d8279e1e417acb0816f507a17fafebb83000b2cb6ce26361bf486c1f92cf5c553071a0181dbbf07182207323034419e4822b17b9d5fa6eb72aa -> SHA 512

9370b96a36dfa69087fe84b1045037c7 -> MD5

Y2liZXJOVXNvaWR7U2g0cDNfdGgzX1YxY3Qwcnl9 -> base64

63 69 62 65 72 4e 55 73 6f 69 64 7b 53 68 34 70 33 5f 74 68 33 5f 56 31 63 74 30 72 79 7d 

00000000 63 69 62 65 72 4e 55 73 6f 69 64 7b 53 68 34 70

00000010 33 5f 74 68 33 5f 56 31 63 74 30 72 79 7d

 

All the encodings/hashes translate to :
ciberNUsoid{Sh4p3_th3_V1ct0ry}

 

3. Recursive Decoding
file link: https://github.com/AnamayMishraa/Sinusoid-V8-CTF/blob/main/files/recursive_decoding

Vm1wR1UxTXlUWGxTYkdScVVtMTRWVmxZY0hOWFJsbDNWbFJHVG1KSGVGaFhhMXBQVkRBeFdHVkVRbFppUmtwSVYxWmFZVkl5UlhwYVJtaFRVbFJXVEZkc1pEUmpiVlp6VjI1V2FWSlViRmhVVnpWclRsWmFSMVZyV2s5V01GWXpWRlZvYzFaWFNuTmpSMmhXVmtWS2FGUldXbXRqVmtwVlZXczFUbFl6YUZkWFYzUnJZakZTY2sxWVVtRlNSa3BvV1d0V1ZrNVdWa2RTVkd4UlZWUXdPUT09

 

As the name says , recursively encoding of the flag as base64 is done.Used ChatGPT to write a script for recursive decoding.

ciberNUsoid{ba5e64_r3cur5iv3_d3cod!ng_7a9a3h1}

 

• Category : Easy
 

1. Know your Photos
Help me find the exposure time of this photograph.

Flag format : ciberNUtica{exposure_time}

File link: https://github.com/AnamayMishraa/Sinusoid-V8-CTF/blob/main/files/memeEXIF.png

 

I used exiftool to get metadata of the image.



ciberNUtica{1/800}

 

2.   K.I.S.S.
Enough with these difficult questions. Here is the flag just download it.

file link: https://github.com/AnamayMishraa/Sinusoid-V8-CTF/blob/main/files/flag_down.bat

 

Its adviced to not open any batch file before seeing its code -_-.

Opened the file on Notepad++.Reading the code it is a script which displays fake messages but turn off the system after 90 seconds.Found a random encoded string in a variable deltaflag.



It is a hexadecimal string.Using python scripting to convert it :
 

deltaFlag = "63796265724e55736f69647b656469745f6e6f745f6f70656e7d"

flag = bytes.fromhex(deltaFlag).decode('utf-8')

print("Flag:", flag)

 ciberNUsoid{edit_not_open}

 

3. Programming Mishap
It seems I forgot to put a hint for the password. Oh well, I am sure you can figure it out.

file link: https://github.com/AnamayMishraa/Sinusoid-V8-CTF/blob/main/files/flag.exe

 

Carefully looking through the disassembled code in Binary Ninja found the flag string:



ciberNUsoid{buffer_overflow_achieved}

 

• Category : Medium
 

1. It's me mario
We've sent the following secret message to mario. Help mario to understand the message.

flag format - ciberNUsoid{your_flag_here}

file link: https://github.com/AnamayMishraa/Sinusoid-V8-CTF/blob/main/files/SuperMario.wav

MorseCode: https://github.com/AnamayMishraa/Sinusoid-V8-CTF/blob/main/files/SuperMarioMorseCode.wav

 

A simple super mario theme song but after carefully hearing the music and comparing it with original music heard some beeping at the backgroud.

Used audacity and  found two tracks .Removing the main track,  left over was some beeping sound.After googling found that it is a morse code where short beeps are dots and long beeps are dashes.

Used online morse code translator from audio to translate it to flag:

C I B E R N U S O I D {M 0 R 5 3 C 0 D 3 F T W 9 3 7 A 6 S 3 9}

 

2. Awaaz ke peeche kya hai
file1 : https://github.com/AnamayMishraa/Sinusoid-V8-CTF/blob/main/files/Awaaz.png

file2: https://github.com/AnamayMishraa/Sinusoid-V8-CTF/blob/main/files/flag

flag3: https://github.com/AnamayMishraa/Sinusoid-V8-CTF/blob/main/files/hint.zip.zip

 

Opening the hint.zip file found a encoded string  c3RlZ2Fub2dyYXBoaWE=



Translating from base64 decoder online:

Steganographia

Awaaz.png didnt have anything unusual:

Extracting the zip file asked me password.Using the decoded base64 string as password: Steganographia

Extracted and got a txt file which had:

43 69 62 65 72 4e 55 73 6f 69 64 7b 31 6d 34 67

33 5f 53 74 33 67 34 6e 30 67 72 34 70 68 79 5f 

38 37 73 34 73 68 32 7d

Decoding to ascii

CiberNUsoid{1m4g3_St3g4n0gr4phy_87s4sh2}

 

3. Mime Records
The flag is in this file source - Truse me bro 😜

file link: https://github.com/AnamayMishraa/Sinusoid-V8-CTF/blob/main/files/Hellcat

Used file command in linux to analyze the file and found that it is a 7z archive but password protected.

Used exiftool but found nothing.

Finally tried after long time of bruteforcing it using JohnTheRipper using rockyou wordlist found the password: hashbrows



 

Extracted the zip and found a file name ' Mail With Attachment Issues '.

Using file and found it is a
MIME entity ASCII

Opening it in notepad++

The MIME had a html part and a bmp image whos data is encoded in base64 .

Now decoding the base64 data one time and writing the content in a notepad and saving it as .bmp extension

Got a .bmp file
 

CiberNUtica{D1ff1cUlt_To_F1nd_Fl4g}

 

• Category : Hard
 

1. reverseme
How can you get the cow back from beef?

file link: https://github.com/AnamayMishraa/Sinusoid-V8-CTF/blob/main/files/reverseme

 

Used file and found it is a linux ELF file .

Running the file ./reverseme:

Enter the Secret Passcode: 

Used Ghidra to disassemble the code.



Using ltrace ./reverseme



Analyzing the ltrace output and ghidra , its found that the input string's each character is xor'd with 0x45 after inputting.Also the flag values in local_68 and others are xor'd with key 0x6c.

Therefore , taking the flag parts and writing a python script to xor each character to get the final flag:

flag_parts = [

    0x1f39221e090e050f,

    0x3817080503,

    0x3f5d58,

    0x5f58383f5d,

    0x1138225f215c21

]

# Convert the hex values into byte arrays, reverse the byte order, and then XOR with 0x6c

reversed_flag_parts = []

for part in flag_parts:

    # Convert to bytes, reverse the byte order, and XOR each byte with 0x6c

    reversed_bytes = part.to_bytes((part.bit_length() + 7) // 8, 'big')[::-1]  # Reverse the byte order

    decoded_bytes = [b ^ 0x6c for b in reversed_bytes]  # Apply XOR

    reversed_flag_parts.append(decoded_bytes)

# Convert the decoded parts back to a string and join them

decoded_flag = "".join(chr(byte) for part in reversed_flag_parts for byte in part)

print("Decoded Flag:", decoded_flag)

ciberNUsoid{T41S1ST43M0M3NT}

 

​
