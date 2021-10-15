+++
title = "Algorithms, Session 1, Complexity and divide and conquer"
date = 2021-10-14
description = "v1.0.0"
+++

# Complexity

## **Simple exercices**

Compute the complexity of the following functions

```python
def sequence(n):
    n = n + 1
    n = n + 4
    n = n * 4
    n = n ** 10
    n = n // 2
    return n
```

{% correction() %}

Correction:
O(1)

{% end %}

---

```python
def loop1(n):
    n = n + 1
    i = 0
    while i < n:
        i = i + 1
    n = n * n
    return n
```
---

```python
def loop2(n):
    n = n + 1
    i = 1
    while i < n:
        i = 2 * i
    n = n * n
    return n
```
---

```python
def b(t):
    n = len(t)
    for j in range(4):
        for i in range(n):
            t[i] *= t[i]
```
---

```python
def h(t):
    n = len(t)
    for i in range(n):
        t[i] = 0
        j = n
        while j > 1:
            t[i] += i*j
            j //= 2
```

## **Master theorem**

```python
def foo(n):
    if n <= 1:
        return
    doOhOne() # doOhOne() runs in O(1) time
    foo(n/2)
    foo(n/2)
```

---

```python
def foo2(n):
    if n <= 1:
        return
    doOhN() # doOhN() runs in O(n) time
    foo(n/2)
    foo(n/2)
```

---

- $T(n) = 4T(n/2) + n^2$
- $T(n) = 16T(n/4) + n$
- $T(n) = 7T(n/3) + n^2$