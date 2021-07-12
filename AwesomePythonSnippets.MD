## Add delimiter between each char in string
```
s = "abcdefghijklmnop"
":".join(list(s)) 
```

## Add delimiter between each arbitrary number of chars in string
```
step = 2
s = "abcdefghijklmnop"
s2 = ":".join(s[i:i+step] for i in range(0, len(s), step))
```

## Random cool snippets
https://levelup.gitconnected.com/22-python-code-snippets-for-everyday-problems-4c6a216c33ae
