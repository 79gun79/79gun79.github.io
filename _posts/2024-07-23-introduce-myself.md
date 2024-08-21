---
layout: post
title: Hello, My World!
subtitle: My World is GunBlog!
author: Jaegeon. Lee.
categories: Etc..
banner:
  video: /assets/videos/Raindrops.mp4
  loop: true # 비디오 반복 설정
  volume: 0.5 # 비디오 볼륨(100%=1.0)
  start_at: 0 # 비디오 시작시간
  image: "assets/images/banners/piano.jpg"
  opacity: 0.75 # 배너 불투명도(100%=1.0)
  background: "#000" # 배너 배경
  height: "100vh" # 배너 기본 높이
  min_height: "40vh" # 배너 최소 높이
  heading_style: "font-size: 4.25em; font-weight: bold; text-decoration: none" # 주 제목 css
  subheading_style: "color: gold; font-weight: bold;" # 부 제목 css
tags: 시작 성공
top: 1
sidebar: []
---

안녕하세요. 한 번 삽질하면 멈추지 않는 남자, 목표 달성을 위해 사력을 다하는 남자 `이재건`입니다. <br/>
저를 보여주기 위한 Tech용 `블로그`를 만들었습니다!<br/>
저는 열정적이고 창의적인 프론트엔드 개발자가 되어 근사한 개발 업무에 참여하고 싶습니다!<br/>
프론트 뿐 아니라, 이에 국한하지 않고 앞으로 저의 일상과 프로그래밍 관련 세상을 마음껏 펼칠 계획이니 지켜봐주세요!<br/>

인스타그램 : [j_gun2](https://www.instagram.com/j_gun2/)

## 17179. 케이크 자르기

해당 코드는 알고리즘 문제 풀이 코드입니다. 앞으로 많이 풀겠습니다!

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
