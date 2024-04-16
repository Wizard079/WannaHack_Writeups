
# Challenge 2.0.2 (CyberSleuth3)

## Description
```
One of our best covert spy mysteriously disappears without any trace...
leaving behind just a photo.. Delve into the virtual world and help us in uncovering some of his secrets..
What is the name of the author whose book he wished to read..?
Change the answer to lowercase alongwith replacing spaces with underscore and wrap the final answer in TechnexCTF{}
```
## Writeup
After a bit of searching, we found an issue created in the same GitHub repository.

Upon examining the details of the issue, we find:
```
Abhinav Lenka
    Hey man..r u sure u want that book..i mean have you even read anything
    close to that genre before?

BitForBat
    Ofc man...moreover ..Its never too late to start afresh....there must be a
    reason why I added it in a famous public gift wishlist..://
```
From this conversation, we understand that we can find the book in a famous public gift wishlist, which is none other than an Amazon wishlist. We can find it [here](https://www.amazon.com/registries?ref_=nav_cs_registry&ref_=nav_cs_registry). Search for BitForBat, and we find the book:
```
Kristin Hannah
The Women: A Novel
```

## Flag

##  COPS{kristin_hannah}
