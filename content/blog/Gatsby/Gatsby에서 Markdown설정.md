---
title: 'Gatsby에서 Markdown설정'
date: 2021-04-18 13:03:13
category: 'Gatsby'
draft: false
---

### Gatsby가 Markdown파일을 읽어서 HTML파일로 만드는 순서
1. "gatsby-source-filesystem"로 마크다운 파일을 읽는다.
2. "gatsby-transformer-remark"로 마크다운 파일을 해석한다.
3. 해석된 데이터를 GraphQL로 가져온다.
4. 가져온 데이터를 미리 설정한 템플릿에 배치한다.
5. Gatsby의 createPageAPI를 사용하여 데이터와 템플릿을 정적 페이지로 만든다.

### 참고자료
1. https://pks2974.medium.com/gatsby-%EB%A1%9C-blog-%EB%A7%8C%EB%93%A4%EA%B8%B0-ac3eed48e068



![kakao](./images/kakao.png)