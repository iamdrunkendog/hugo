---
title: "Windows Git Bash에서 tree 명령어 사용하기"
date: 2021-06-04T02:46:00+09:00
categories:
- Dev
- Tips
tags:
- Windows
- bash
- git
- git bash
- tree
#thumbnailImage: //example.com/image.jpg
---
## 1. tree.exe 다운로드

아래의 링크에서 tree를 다운받는다.

[http://gnuwin32.sourceforge.net/packages/tree.htm](http://gnuwin32.sourceforge.net/packages/tree.htm)

나의 경우 Binaries zip파일을 다운받아 압축을 풀어 `/bin/tree.exe`를 사용했다.

## 2. git bash가 설치된 디렉토리에 tree.exe 복사

git bash가 설치되어있는 경로의 `usr\bin\` 디렉토리에 tree.exe를 복사한다

기본 설치 경로는 `C:\Program Files\Git\usr\bin\` 이다.

## 3. 완료 및 테스트

```bash
$ tree
.
|-- README.md
|-- __init__.py
|-- config.json
`-- notion2hugo.py

0 directories, 4 files
```

해당 디렉토리에서 `tree` 명령어를 입력하면 문제 없이 동작한다.

### 참고 사이트

[https://beemiel.tistory.com/7](https://beemiel.tistory.com/7)