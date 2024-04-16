
# Challenge 2.1

## Description
```
Find the flag using the techniques covered till now!

FLAG FORMAT: COPS{}
given files : chall.zip
```
## Writeup

We are provided with a zip file, but it's password-protected. I used fcrackzip to unlock it using the rockyou.txt wordlist and found the password:

```
> fcrackzip -u -D -p /usr/share/wordlists/rockyou.txt chall.zip

PASSWORD FOUND!!!!: pw == 55yoda55
```

After unzipping it, we find 1000 text files and 1 hidden PNG file. Using zsteg on the hidden PNG file, we find the flag:

```
> zsteg .flag.png
chunk:0:IHDR        .. file: Adobe Photoshop Color swatch, version 0, 558 colors; 1st RGB space (0), w 0x1bf, x 0x806, y 0, z 0; 2nd space (65280), w 0, x 0x101, y 0, z 0xff00
b1,rgb,lsb,xy       .. text: "COPS{c0ngr4tul4t10ns}"
b2,b,msb,xy         .. text: "\r AM\tKUg"
b2,rgba,lsb,xy      .. text: "////sss/ssss"
b2,abgr,msb,xy      .. text: "S_c7g3gO"
b3,abgr,msb,xy      .. text: "yB'tB'tC7tC"
b4,r,lsb,xy         .. text: "\"33\"#332!"
b4,g,lsb,xy         .. text: "\"3EwffeVy"
b4,g,msb,xy         .. file: RDI Acoustic Doppler Current Profiler (ADCP)

```
## Flag

## COPS{c0ngr4tul4t10ns}

