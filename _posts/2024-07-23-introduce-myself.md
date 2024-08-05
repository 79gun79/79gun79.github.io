---
layout: post
title: 안녕! 난 재건이야!
subtitle: 건블로그에 오신 것을 환영합니다!
author: Jaegeon. LEE.
categories: etc
banner:
  video: "assets/videos/piano1.mp4"
  loop: true
  volume: 0.8
  start_at: 8.5
  image: "assets/images/banners/piano.jpg"
  opacity: 0.618
  background: "#000"
  height: "100vh"
  min_height: "40vh"
  heading_style: "font-size: 4.25em; font-weight: bold; text-decoration: none"
  subheading_style: "color: gold; font-weight: bold;"
tags: 시작 성공
top: 1
sidebar: []
---

안녕하세요! 이재건입니다. 성공적으로 드디어 `블로그`를 만들었습니다!<br>
저는 시흥사는 25세 남성이고요~ 여러분에게 저를 마음껏 뽐내고 싶습니다<br>
앞으로, 저의 일상과 프로그래밍 관련 세상을 마음껏 펼칠 계획이니 지켜봐주세요!<br>

인스타그램 : [j_gun2](https://www.instagram.com/j_gun2/)

## 17179. 케이크 자르기

해당 코드는 알고리즘 코드입니다. 앞으로 많이 풀겠습니다!

```python
import sys
input = sys.stdin.readline

N, M, L= map(int, input().split())
s = []
for _ in range(M):
    s.append(int(input()))
s.append(L)

for _ in range(N):
    q = int(input())
    res = 0
    l = 0
    r = s[M - 1]

    while l <= r:
        mid = (l+r) // 2
        cnt = 0
        tmp = 0

        for i in range(M+1):
            if s[i] - tmp >= mid:
                cnt += 1
                tmp = s[i]

        if cnt > q:
            l = mid + 1
            res = max(res, mid)
        else:
            r = mid - 1

    print(r)
```

## 7576. 토마토

해당 코드도 알고리즘 코드입니다. 앞으로 많이 풀겠습니다!!

```python
import sys
input = sys.stdin.readline
from collections import deque

m, n = map(int, input().split())
tomato = []
for _ in range(n):
    tomato.append(list(map(int, input().split())))

dx = [0,0,-1,1]
dy = [1,-1,0,0]

q = deque()
def BFS():

    while q:
        x, y = q.popleft()
        for d in range(4):
            nx = x + dx[d]
            ny = y + dy[d]

            if 0 <= nx < n and 0 <= ny < m and tomato[nx][ny] == 0:
                    tomato[nx][ny] = tomato[x][y] + 1
                    q.append((nx, ny))

for i in range(n):
    for j in range(m):
        if tomato[i][j] == 1:
            q.append((i, j))

BFS()
res = 0
for t in tomato:
    for ti in t:
        if ti == 0:
            print(-1)
            exit(0)
        elif ti > res:
            res = ti
print(res - 1)
```
