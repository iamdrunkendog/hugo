---
title: "GitHub Pages(github.io) 커스텀 도메인 연결"
date: 2021-06-02T22:06:19+09:00
categories:
- DEV
- GitHub
tags:
- GitHub
- GitHub Pages
- custom domain
- github.io
keywords:
- tech
# draft: true
#thumbnailImage: //example.com/image.jpg
---
# Github Pages에 도메인을 연결하자

무려 12년째 보유하고 있는 개인 도메인이 이메일 주소 유지 용도로만 연명하다가, 최근 다시 학습 및 개발에 불을 붙이면서 점점 활용도가 늘어나고 있다. 최근 이들에 대한 아카이빙, 의견 공유, 프로젝트에의 활용 등을 목적으로 구글 도메인에서 마음에 드는 도메인을 구매했는데, 이를 GitHub Pages에 연결해봤다.

drunkendog라는 github id가 이미 선점당했기 때문에 어쩔 수 없이 iamdrunkendog라는 계정을 생성했는데, GitHub Pages가 {userid}.github.io의 형식으로만 URL을 발급해주기 때문에 어쩌다보니 매우 긴(?) 주소를 갖게되어 이를 줄이는 것이 목적이다.

### 준비물

1. 개인 도메인

    자신이 보유하고 있는 도메인에 대해서만 설정이 가능하다. 나는 [구글 도메인](https://domains.google.com)에서 최근에 구입한 도메인으로 진행하고자 한다. 생각보다 다양한 종류의 도메인이 있는데, 본인 개성과 취향과 지갑 사정(?)을 종합적으로 고려해보자.

# 커스텀 도메인 연결 방법

## 1) Repository > Settings > Pages 에서 커스텀 도메인 설정

![/post/github-pages-custom-domains/_2021-05-28__3.29.13.png](/post/github-pages-custom-domains/_2021-05-28__3.29.13.png)

원하는 주소를 작성하고 SAVE버튼을 누르면 github에서 연결이 가능한 상태인지 확인한다. 기존에 도메인 세팅이 되어있지 않은 상태라면 아래와 같은 메시지를 볼 수 있다.

메시지에서는 도메인의 CNAME 레코드를 iamdrunkendog.github.io로 지정하라고 안내한다.

## 2) 도메인 CNAME 변경

본인의 도메인을 관리할 수 있는 곳으로 이동하자. 도메인을 구입했던 기관에서 해당 기능을 제공하기도 하고, [dnsever](http://dnsever.com)같은 사이트에 내 도메인을 등록해서 자유롭게 관리할 수도 있다. 저렴한 곳에서 도메인을 구매했지만 기타 설정이 불가하다면 해당 서비스 이용을 고려해볼 수 있다. 원래 무료로 서비스를 제공했지만 현재는 도메인당 월 500원의 가격으로 서비스를 제공하는 중.

나는 [구글 도메인](https://domains.google.com)을 통해 도메인을 구입 및 관리하고 있기 때문에 이를 기준으로 진행했다.

### (구글 도메인) 도메인설정 > DNS > 맞춤 리소스 레코드

![/post/github-pages-custom-domains/_2021-05-28__3.49.56.png](/post/github-pages-custom-domains/_2021-05-28__3.49.56.png)

TTL(Time to Live)는 기본값이 1h로 되어있다. TTL이 길 수록 전파되는 속도가 느려지며 반대로 TTL이 짧을 수록 DNS서버의 부하가 커지게 된다. 적당한 값을 써주자. ~~(구글을 믿자)~~

### (dnsever) 도메인정보 > 도메인 별명(CNAME) 관리

![/post/github-pages-custom-domains/Untitled.png](/post/github-pages-custom-domains/Untitled.png)

dnsever의 경우 다음과 같이 설정할 수 있다. 이외 다른 서비스나 도메인 제공 업체에서도 유사하게 해당 기능을 제공하고 있으니 설정하도록 하자.

## 3) 기다린다

도메인 설정을 바꾸게 되면 여유를 갖는 습관이 생기게 된다. 미리 용도를 지정해두고 세팅해두면 이 시간을 줄일 수 있다.

![/post/github-pages-custom-domains/_2021-05-28__3.55.52.png](/post/github-pages-custom-domains/_2021-05-28__3.55.52.png)

DNSCHECKER라는 사이트에서 DNS의 전파 현황을 알 수 있으니 답답하다면 어느 지역에서 아직 전파가 안되었는지 눈으로 확인하며 답답해보자.

사실, 구글 도메인의 경우 48시간까지 소요될 수 있다고 안내하지만 생각보다는 빠르게 반영이 된다. 내 경우도 10분 안쪽으로 작업이 완료.

## 4) 완료

![/post/github-pages-custom-domains/_2021-05-28__3.58.12.png](/post/github-pages-custom-domains/_2021-05-28__3.58.12.png)

설정이 완료되었다면 GitHub Pages 설정에서 내가 지정한 도메인으로 사이트가 배포되었다는 안내를 볼 수 있다.

![/post/github-pages-custom-domains/_2021-05-28__3.59.32.png](/post/github-pages-custom-domains/_2021-05-28__3.59.32.png)

이후 해당 주소로 접속해보면 기존 사이트가 연결된 것을 확인할 수 있다.