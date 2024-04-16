
# Headers!

## Description
```
Do you remember we talked about headers?

Well, use them!

Challenge Link: http://ctf.copsiitbhu.co.in:11337/
```
## Writeup

This is a typical headers challenge where we need to manipulate HTTP headers to get the flag.
Using curl, we can change the headers and send them back to the server to get the desired response:
```
> curl  http://ctf.copsiitbhu.co.in:11337/ -H "User-Agent: Secure-Browser"
<p>Does not Accept <b>nothing</b></p>

> curl  http://ctf.copsiitbhu.co.in:11337/ -H "User-Agent: Secure-Browser" -H  "Accept: nothing"
<p>Connection not <b>secure</b></p>

> curl  http://ctf.copsiitbhu.co.in:11337/ -H "User-Agent: Secure-Browser" -H  "Accept: nothing" -H "Connection: secure"
<b>Want-Flag</b> is not <b>yes</b>

> curl  http://ctf.copsiitbhu.co.in:11337/ -H "User-Agent: Secure-Browser" -H  "Accept: nothing" -H "Connection: secure" -H "Want-Flag: yes"
COPS{headers_all_the_way}
```

Alternatively, we can use the nc command to achieve the same result:

```
> nc ctf.copsiitbhu.co.in 11337
GET / HTTP/1.1
User-Agent: Secure-Browser
Accept: nothing
Connection: secure
Want-Flag: yes

HTTP/1.1 200 OK
Server: Werkzeug/3.0.2 Python/3.10.12
Date: Tue, 16 Apr 2024 09:26:11 GMT
Content-Type: text/html; charset=utf-8
Content-Length: 26
Connection: close

COPS{headers_all_the_way}
```
## Flag

## COPS{headers_all_the_way}
