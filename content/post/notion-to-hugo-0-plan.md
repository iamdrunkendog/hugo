---
title: "[notion-to-hugo] 노션으로 작성한 글을 Hugo 포스트로 변환해주는 프로젝트"
date: 2021-06-03T19:32:00+09:00
categories:
- Projects
- notion-to-hugo
tags:
- Hugo
- Notion
- Python
- notion-to-hugo
keywords:
- tech
#thumbnailImage: //example.com/image.jpg
---
이 포스트는 Notion으로 작성한 게시글을 정적 사이트 생성기(SSG, Static Site Generator) Hugo의 Post로 컨버팅해주는 **notion-to-hugo**의 개발 일지입니다.

프로젝트의 진행 상황, 관련 정보는 [**notion-to-hugo**의 GitHub Repo](https://github.com/iamdrunkendog/notion-to-hugo)에서 확인하실 수 있습니다.
***
## 노션으로 작성한 글을 더 쉽게 배포할 수 없을까?

노션으로 작성한 페이지는 마크다운(Markdown, .md) 형태로 쉽게 내려받을 수 있다. Jekyll, Hexo, Hugo 등 인기 많은 SSG서비스들이 기본적으로 마크다운 기반이기도 하고, 뼈대 굵은 카카오의 티스토리도 마크다운 형식을 지원하기 시작했다. 내가 노션무새가 될 정도로 노션 자체는 정말 강력한 서비스이지만 개인적으로 웹 사이트나 블로그를 대체하기에는 부족하다고 판단했다. 그렇기 때문에 oopy결제 직전에 GitHub Pages와 Hugo를 이용한 블로그를 만들기도 했고.

그런데 마크다운 기반의 서비스를 이용한다고 해서 매일 VS Code를 띄워놓고 ~~일하는 척~~ 포스팅을 한다거나, 모르는 마크다운 문법을 검색하기 위해 Chrome Surfer가 되기 보다는 쓰던 대로 글을 쓰는 것이 더 편하니까. 또, 노션 자체로 굉장히 훌륭한 Editor이기 때문에 굳이 안쓰던 방식으로 포스팅을 할 필요는 없다고 생각했다. 

그래서 노션에서 쓴 글을 md로 export하여 테스트 해봤는데 생각보다 그 과정이 편하진 않았다.

1. 압축을 풀고,
2. hugo new [blahblah]로 글을 만들고,
3. 만들어진 .md파일에 Export한 내용을 복붙하고
4. 제목, 카테고리, 날짜 등을 받아적고
5. 첨부파일을 Static폴더로 옮긴 뒤에
6. 본문의 첨부파일 URL을 모조리 수정해야 했다 (Command + H)

> 개발자는 더 게을러지기 위해 부지런히 개발을 한다.

최근 블로그 구축을 위해 많은 개발자 선후배 친구들 블로그를 돌아다니며 뇌리에 박힌 구문이다. 맞다, 매일 같이 위와 같은 과정을 반복하려면 차라리 마크다운에 익숙해지는 편이 더 나아보인다. ~~VS Code 마크다운 Extension이 매우 훌륭해보이긴 하던데.~~ 그래서 개인적인 용도로, 이 과정을 간소화해주는 간단한 코드를 작성해보고자 한다.

## 프로젝트 계획

### 개발 환경

- Python
- Mac / Windows

사실 Hugo가 Go언어 기반으로 작성되어있기 때문에 관련 프로젝트도 Go로 만들면 좋지 않을까 생각했지만, 아직 Node.js도 익숙하지 않은 나에겐 너무 가혹하다. 그리고 사실, 그렇게 복잡한 로직이 필요하지도 않기 때문에 (적어도 아직은?) 딱히 Python으로 진행하면 안될 이유도 없다.

### 세부 개발 계획

1. CLI 기반 
    - 자동 압축 해제
    - Archetypes/default.md 형식에 맞는 형태로 변환
    - 제목, 내용, 카테고리, 태그 등의 자동 입력
    - Contents, Static 디렉토리에 각각 업로드
    - 위 과정의 자동화
2. GUI Application 제작
    - Drag & Drop 한방에 변환해버리는 자동화머신 제작

개발 환경에 굳이 Windows와 Mac을 병기한 이유는 향후 GUI Application까지 제작할 계획을 가지고 있기 때문이다. 뭐 그때까지 지속할 수 있을지는 모르겠지만, 이왕 계획한 것 공부삼아 진행해보고자 한다. PyQt에 익숙해질 필요가 있을 듯하다. 다음 포스트부터는 세부적인 진행 현황을 기록해봐야지.


