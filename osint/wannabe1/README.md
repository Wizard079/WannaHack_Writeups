
# wannabe1

## Description

```
This photo is the last evidence of my friend..help me find out more about him..

Whats his github username?

Flag format: COPS{username}

given file : hacker.jpg
```

## Writeup

Firstly, by checking the metadata using exiftool, we extracted the following information from the hacker.jpg file:

```
> exiftool heckr.jpg
ExifTool Version Number         : 12.76
File Name                       : heckr.jpg
Directory                       : .
File Size                       : 114 kB
File Modification Date/Time     : 2024:04:14 12:05:21+05:30
File Access Date/Time           : 2024:04:14 12:05:29+05:30
File Inode Change Date/Time     : 2024:04:14 12:05:27+05:30
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Exif Byte Order                 : Big-endian (Motorola, MM)
Make                            : Stable Diffusion
X Resolution                    : 1
Y Resolution                    : 1
Resolution Unit                 : None
Y Cb Cr Positioning             : Centered
Exif Version                    : 0232
Components Configuration        : Y, Cb, Cr, -
User Comment                    : {"0":{"concept":{"bad_concepts":[],"concept_scores":{"0":-0.049,"1":-0.072,"2":-0.047,"3":-0.056,"4":-0.081,"5":-0.056,"6":-0.039,"7":-0.044,"8":-0.075,"9":-0.129,"10":-0.074,"11":-0.081,"12":-0.041,"13":-0.101,"14":-0.108,"15":-0.109,"16":-0.099},"special_care":[],"special_scores":{"0":-0.085,"1":-0.042,"2":-0.092}},"has_nsfw_concept":false,"height":1024,"model":"turbo","output_path":"/tmp/imagecache/out-97fadb75-2d76-4bed-bf91-6352a3298c97.jpg","prompt":"Prompt: \"Display an image of a 1990s hacker, sitting at a cluttered desk filled with outdated technology such as a bulky CRT monitor, a large, boxy computer tower, and a stack of floppy disks. The hacker is wearing a baggy, plaid flannel shirt, overs","steps":4,"width":1024},"width":1024,"height":1024,"seed":42,"model":"turbo","enhance":false,"refine":false,"nologo":true,"negative_prompt":"worst quality, blurry","nofeed":false}
Flashpix Version                : 0100
Color Space                     : Uncalibrated
Author                          : Qml0Rm9yQmF0
Image Width                     : 1024
Image Height                    : 1024
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 1024x1024
Megapixels                      : 1.0
```

we got the authore name "Qml0Rm9yQmF0" by decoding it using base64 we get username as BitForBat

```
> echo "Qml0Rm9yQmF0" | base64 -d
BitForBat
```


## Flag

## COPS{BitForBat}
