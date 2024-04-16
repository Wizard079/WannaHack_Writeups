
# Themer2

## Description
```
Someone told me the previous website was broken :(((

Anyways I made it again :)

http://ctf.copsiitbhu.co.in:21339/
```
## Writeup

Upon analyzing the source code:
```py
@app.route('/')
def index():
    safe_theme = request.args.get("theme", "themes/theme1.css")
    if safe_theme[0] == "/":
        safe_theme = safe_theme[1:-1]
    safe_theme = safe_theme.replace("../", "")
    f = open(safe_theme, "r")
    theme = f.read()
    f.close()
    return render_template('index.html', css=theme)
```

We can see that this time they implemented user input sanitization, but it's still vulnerable to path traversal. They are removing:

```
"../" -> ""
```
Additionally, for the previous payload, they are removing the first and last index of the string:

```py
     if safe_theme[0] == "/":
        safe_theme = safe_theme[1:-1]
```

So, we can send a payload like //flag.txt9, so /9 will be removed and we get flag.txt.

## Flag

##  COPS{path_traversal_yay_291}
