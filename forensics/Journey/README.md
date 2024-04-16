
# Journey 

## Description

```
Are you ready to start the journey?

Follow the instructions in instructions.mp3

given file : chall instructions.mp3
```

## Writeup

Firstly, by checking the metadata using exiftool, we extracted the following information from the chall.png file:

```
exiftool chall
ExifTool Version Number         : 12.76
File Name                       : chall
Directory                       : .
File Size                       : 143 kB
File Modification Date/Time     : 2024:04:14 09:16:00+05:30
File Access Date/Time           : 2024:04:14 09:16:37+05:30
File Inode Change Date/Time     : 2024:04:14 09:16:11+05:30
File Permissions                : -rw-r--r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 500
Image Height                    : 500
Bit Depth                       : 8
Color Type                      : RGB with Alpha
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Comment                         : COPS{f1rst_
Warning                         : [minor] Trailer data after PNG IEND chunk
Image Size                      : 500x500
Megapixels                      : 0.250

```

In the instructions.mp3 file, it's mentioned that there are three parts. After examining the chall.png file, we discovered that the password is "journey_xxxx," indicating that we need to input this password somewhere.

Upon running binwalk on the provided image, we found a 5E70.zip file, which is, as expected, locked. Therefore, we need to employ brute force to unlock it.

We generated a wordlist using Crunch:

```
crunch 12 12 -t journey_%%%% > journey.txt
```
Then, employing fcrackzip led us to the password:

```
> fcrackzip -u -D -p ../journey.txt 5E70.zip -v
found file '.hidden.png', (size cp/uc 118500/122338, flags 1, chk 2a8f)


PASSWORD FOUND!!!!: pw == journey_1503
```

This yielded a .hidden.png file, from which we performed strings extraction and found:

```
> strings -n 10 .hidden.png
Z`+sM @m}=X
N'}	CmoY?G
pYZEGyS}d=
`oS<Ce%Zt+e
Fi:p1CNuj^
definitely not
czNjMG5kXw==
;tEXtComment
```
The base64 encoded string czNjMG5kXw== decoded to:

```
> echo "czNjMG5kXw==" | base64 -d
s3c0nd_
```
Further examination using foremost on .hidden.png revealed another PNG containing the third part:
```
th1rd_696}

```
## Flag

## COPS{f1rst_s3c0nd_th1rd_696}
