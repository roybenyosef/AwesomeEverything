### Add delimiter between each char in string
```
s = "abcdefghijklmnop"
":".join(list(s)) 
```

### Add delimiter between each arbitrary number of chars in string
```
step = 2
s = "abcdefghijklmnop"
s2 = ":".join(s[i:i+step] for i in range(0, len(s), step))
```

### Random cool snippets
https://levelup.gitconnected.com/22-python-code-snippets-for-everyday-problems-4c6a216c33ae

### Digit Grouping
```
n = 2_000_000_000
nx = 0xFFFF_EEEE_8888
nb = 0b_0101_1101_1111

hex(nx)
bin(nb)

```

### Sum of digits

`sum_of_digits = lambda x: sum(map(int, str(x)))`

### cast items in list

`list(map(int, ['1', '2', '3']))`

### Flatten list with sublists: 

`flattened_list = [item for sublist in l for item in sublist]`

### Swap key-value in dict: 

`staff = {i:j for j, i in staff.items()}`

### python utility function retry with exponential backoff
https://keestalkstech.com/2021/03/python-utility-function-retry-with-exponential-backoff/

### Nice kata with generated functions/closures/lambdas:
https://www.codewars.com/kata/525f3eda17c7cd9f9e000b39/solutions/python

```
id_ = lambda x: x
number = lambda x: lambda f=id_: f(x)
zero, one, two, three, four, five, six, seven, eight, nine = map(number, range(10))
plus = lambda x: lambda y: y + x
minus = lambda x: lambda y: y - x
times = lambda x: lambda y: y * x
divided_by = lambda x: lambda y: y / x
```

See closures:
https://www.programiz.com/python-programming/closure
