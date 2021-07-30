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

## Digit Grouping
```
n = 2_000_000_000
nx = 0xFFFF_EEEE_8888
nb = 0b_0101_1101_1111

hex(nx)
bin(nb)

```
