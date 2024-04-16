
# Challenge 2.0.1 (Cybersleuth2)

## Description
```
One of our best covert spy mysteriously disappears without any trace...
leaving behind just a photo.. Delve into the virtual world and help us in uncovering some of his secrets..
What is the gmail address using which he uploaded a pic when he was freaked out but still had a bit of hope ..?

Wrap the answer in TechnexCTF{}
```
## Writeup
With the reference to hope, we can check the content of hope.txt, but unfortunately, we don't find any useful information there. So, let's explore the commit history of hope.txt. This leads us to a link which takes us to an image [here](https://shorturl.at/BCEU5).

Upon examining the details of the drive link, we find:
```
Abhinav Lenka : Owner
```

and email of Abhinav Lenka is : lenkaabhinav0@gmail.com (from details)
## Flag

##  TechnexCTF{lenkaabhinav0@gmail.com}
