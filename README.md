# Editor.md




**Table of Contents**

[TOCM]

[TOC]

#Задание А
```python
a = input()
print("Hello, ", a, "!", sep='')
```
#Задание B
```python
import calendar
a = (calendar.isleap(int(input())))
if a == True:
 print("YES")
else:
 print("NO")
```
#Задание C
```python
a=int(input(""))
k = ("Fizz"* (not a.__mod__(3)) + "Buzz" * (not a.__mod__(5)) + "Pozz" * (not a.__mod__(7)) or "Nedelizz")
print(k)
```
#Задание D
```python
a,b = map(int,(input(),input()))
x = [int(input()) for f in range(a*b)]
x.sort()
i=0
for f in range(a):
    for f in range(b):
        print(x[i],end=' ')
        i+=1
    print()
```
#Задание E
```python
k = int(input())
x = [input() for i in range(k)]
print(*(x[int(input())] for i in range(k)))
```
#Задание F
```python
N = int(input())
E = input().split()
x = [E]+[E + E[i::-1] for i in range(len(E))]
for i in x:
    if i == i[::-1]:
        print(len(i)-N)
        if i[N:]:
            print(*i[N:])
        break
```
#Задание G
```python
a = [int(input()) for i in range(int(input()))]
print(max(a, key=a.count))
```
#Задание H
```python
a = -1
b = 0
while a != 0:
    a = int(input())
    if a % 2 == 0:
        b = max(a,b)
print(b)
```
#Задание I
```python
n,m=map(int,input().split())
if 9*m<n or n<m:
    print('impossible',end='')
else:
    a=[1]*m
    n-=m
    i=-1
    while n>8:
        a[i]+=8
        n-=8
        i-=1
    a[i]+=n
    print(*a,sep='')
```
#Задание J
```python
n = int(input())
l = [[0] * n for i in range(n)]
for i in range(n):
    k = list(map(int, input().split()))
    for x in range(n):
        l[x][n - i - 1] = k[x]
for i in range(n):
    print(*l[i])
```
#Задание K
```python
N = int(input())
x = list(map(int,input().split()))
x.sort(reverse=1)
y = [0]
def korova(N):
    return all(N%f for f in range(2,int(N**0.5) + 1))
for i in range(len(x)):
    for j in range(i+1,len(x)):
        if korova(x[i]+x[j]):
            y.append(x[i]+x[j])
print(max(y))
```
#Задание L
```python
x1,y1,x2,y2 = map(int,input().split())
xA,yA = map(int,input().split())
r = lambda x:'%.5f'%x
if x1 == x2:
    print(xA+2*(x1-xA),yA)
elif y1 == y2:
    print(xA,yA+2*(y1-yA))
else:
    k1 = ((y1-y2)/(x1-x2))
    b1 = (y1-x1*k1)
    k2 = (-1/k1)
    b2 = (yA-k2*xA)
    x0 = ((b1-b2)/(k2-k1))
    y0 = (x0*k2+b2)
    xB = r((xA+2*(x0-xA)))
    yB = r((yA+2*(y0-yA)))
    print(xB,yB)
```
#Задание M
```python
a,b,c = [set(map(int,input().split())) for i in range(3)]
x = sorted(k for k in b if k in c if k not in a)
print(*x)
```
#Задание N
```python
n,m,k,x = (int(input()) for i in range(4))
if m<n:
    print('NO')
elif (m-k<=x and k<m):
    print('NO')
else:
    print('YES')
```
#Задание O
```python
x = input()
while '[]' in x or '{}' in x or '()' in x:
    x = x.replace('{}', '')
    x = x.replace('[]', '')
    x = x.replace('()', '')
if x:
    print('NO')
else:
    print('YES')
```
#Задание P
```python
x = list(map(int,input().split()))
n = int(input())
def inside(x,n,i):
    if len(x) == 1:
        if x[0] == n:
            print(i)
        else:
            print(-1)
    else:
        if x[len(x)//2] < n or x[len(x)//2] == n:
            inside(x[len(x)//2:], n, i+len(x)//2)
        else:
            inside(x[:len(x)//2], n, i)
inside(x, n, 1)
```
#Задание Q
```python
#undefinedvoidnullNone0
n,b = map(int,input().split())
a = [[i,input().split()] for i in range(n)]
a = [[i,k,int(v)] for i,[k,v] in a]
m = int(input())
d = 0
for i in range(m):
    if len(a)==1:
        break
    i=(i-d)%len(a)
    if a[i][2]:
        if b==0:
            del a[i]
            d+=1
    else:
        b=int(not b)
        if b:
            a[i][2]=1
print(*('%s %s'%tuple(i[1:]) for i in a), sep='\n' )
```
#Задание R
```python
#votpovezlo
def z_func (s: str):
    n = len(s)
    z = [0] * n
    i = 1
    l = 0
    r = 0
    while i < n:
        if i <= r:
            z[i] = min(r - i + 1, z[i - l])
        while i + z[i] < n and s[z[i]] == s[i + z[i]]:
            z[i] += 1
        if i + z[i] - 1 > r:
            l = i
            r = i + z[i] - 1
        i += 1
    return z
s = input()
c = s + "#" +s[::-1]
print(*z_func(c)[::-1][:len(s)])
```
#Задание S
```python
n = int(input())
x = list(map(int,input().split()))
k = int(input())
y = k * [0]
for i in range(k):
    a,b = map(int,input().split())
    y[i]=max(x[a:b+1])
print(*y)
```
#Задание T
```python
x = input()
y = 0
for i in x:
    if i == 'v':
        y += 1
    if i == '<':
        y += 10
    if i == '.':
        y = y* 60
print(y)
```

