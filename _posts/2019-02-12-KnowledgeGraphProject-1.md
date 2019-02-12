---
title: "지식 그래프(KnowledgGraph) 프로젝트 - Before 1. 지식 그래프 & 시맨틱 네트워크"
sidebar:
  title: "Sidebar"
  nav: sidebar-sample
readtime: true
toc: true
last_modified_at : 2019-02-12 13:11:59
categories:
  - 개발
tags:
  - kgproject
  - knowledgegraph
  - semanticnetwork
---

# 지식 그래프(Knowledge Graph)란?
--- 
## 지식 그래프(Knowledge Graph)의 정의

위키백과에서는 지식 그래프에 대해 다음과 같이 설명하고 있다.

> 지식 그래프(Knowledge Graph)는 다양한 소스로부터 축적한 **시맨틱 검색 정보**를 사용하여 검색결과를 향상시키는 것으로 구글이 사용하는 지식 베이스이다.  
> 2012년 당시, ...(중략).. 검색엔진에 입력한 검색어의 의미를 이해하는데 사용된 다른 **객체들간의 관계**를 가진 **시맨틱 네트워크**를 구축했었다.
> <figcaption>출처 : 지식 그래프 위키백과</figcaption>

위의 설명만 봐서는 지식 그래프가 어떤 역할을 하며 실제로 어떤 기능을 하는지에 대한 의미가 매우 모호하다. 실제 지식 그래프가 사용되는 예시를 먼저 보도록 하자.

## 지식 그래프의 실 사용 예시
![image](https://user-images.githubusercontent.com/18658656/52616428-d3583680-2edb-11e9-8833-0b32fcf7f07c.png)
<figcaption>구글에 '아이유'검색시 결과화면</figcaption>

위의 그림은 구글 검색창에 '아이유'를 검색하였을 때, 나타나는 결과화면이다. 위의 그림을 보고 특이한 점을 발견 할 수 있을까?  
<br>
현재 우리는 다음과 같은 결과화면에 익숙해져서 딱히 특이한 점을 발견 할 수 있지는 않을 것이다.  

![image](https://user-images.githubusercontent.com/18658656/52616598-66916c00-2edc-11e9-83f8-e7357f9c7614.png)

하지만 결과화면은 다음과 같이 구분 할 수 있다.  
현재는 구글의 지식 그래프로 만든 지식패널이 적용된 2012년으로부터 벌써 7년이 지난 2019년이기 때문에 위와 같은 결과화면이 너무 익숙해서 특이한 점을 못느꼈을 가능성이 높다.  
<br>
2012년 전 구글 검색은 왼쪽과 같은 결과화면만 나타났기 때문에 정보의 종류에 따라 다르겠지만 원하는 정보를 찾기가 상대적으로 어려웠지만 현재는 오른쪽의 지식패널(지식 그래프를 적용한 서비스 )를 통해서 원하는 정보를 조금 더 손쉽게 찾을 수 있다.  

다른 예시를 하나 더 보자

![image](https://user-images.githubusercontent.com/18658656/52617326-c1c45e00-2ede-11e9-8f20-1aa15104fef3.png)

나는 '조지 오웰'의 동물농장이라는 책의 정보를 찾고 싶어서 '동물농장'이라는 키워드를 검색하였다.  
이 때 왼쪽의 결과화면을 보면 대부분 TV동물농장에 관련된 정보를 찾아준다.  
만약 지식패널이 없었다면, 나는 왼쪽의 검색 결과들 중 내가 원하는 '동물농장'책에 대한 정보를 찾기 위해서 한참을 찾아야 했을지도 모른다.  
<br>
하지만 오른쪽 지식패널을 보면 먼저 TV동물농장에 대한 설명이 있지만, 하단에 내가 찾으려고 했던 동물 농장 책에 대한 정보를 알려준다.  

<figure class="half">
    <a href="https://user-images.githubusercontent.com/18658656/52617629-cc332780-2edf-11e9-8bdf-f2b63ad183a9.png"><img src="https://user-images.githubusercontent.com/18658656/52617629-cc332780-2edf-11e9-8bdf-f2b63ad183a9.png"></a>
    <a href="https://user-images.githubusercontent.com/18658656/52617642-d48b6280-2edf-11e9-85bf-cd8ade198aac.png"><img src="https://user-images.githubusercontent.com/18658656/52617642-d48b6280-2edf-11e9-85bf-cd8ade198aac.png"></a>
    <figcaption>왼쪽 : 동물농장 작가를 검색하였을 때 결과화면<br>오른쪽 : 동물농장 출연진을 검색하였을 때 결과화면</figcaption>
</figure>

동물농장 작가를 검색하였을 때는 알아서 책 '동물농장'의 작가인 조지 오웰을 결과로 나타내어 주고,  
동물농장 출연진을 검색하였을 때는 'TV 동물농장'에 출연하는 신동엽을 결과로 나타내어 준다.  
<br>
위와 같은 결과를 나타날 수 있게 하는 기술이 바로 **'지식 그래프(Knowledge Graph)'**인 것이다.  
<br>
<br>

**그럼 지식 그래프가 뭔지도 알겠고, 어떻게 쓰이는지도 알겠다. 그래서 지식 그래프가 어떤 원리로 이루어져있는 것인가?**

---

처음에 위키백과에서 가져온 지식 그래프의 정의를 살펴보면, **시맨틱 검색 정보**를 사용하고, **시맨틱 네트워크**를 구축하였다는 정보를 확인 할 수 있다.  <br>
<br>
그렇다면 시맨틱 검색 정보를 사용 할 때 활용한 시맨틱 네트워크는 무엇인가?

# 시맨틱 네트워크(Symantic Network)란?
## 시맨틱 네트워크(Symantic Network)의 정의
> 네트워크를 기초로 한 지식표현 방법으로, **객체(Object)**, **개념(Concepts)**, **사건(Events)**들을 표현하는 **노드(Node)**의 집합과 노드 사이의 **관계(Predicates 또는 속성)**를 표현하며 연결하는 **아크(Arc)의 집합**으로 이루어져 있다.

시맨틱 네트워크를 바로 설명하기 전, 시맨틱 정보에 대해 먼저 설명해보자
## 시맨틱 정보란?
**시맨틱 정보**는 노드(객체, 개념, 사건들을 표현)와 또 다른 노드사이의 관계를 표현하는 것이다. <br>
<br>
간단한 예시를 들어보자면
> **동물**은 **척추**를 **가지고 있다**.

여기서 **'동물'**이라는 노드와 **'척추'**라는 노드 사이에는 **'가지다'**라는 관계를 가지고 있다.<br>
<br>
이런 시맨틱 정보들을 엮어서 네트워크로 만든 것이 **시맨틱 네트워크**이며 아래와 같은 그림으로 이해 할 수 있다.
## 시맨틱 네트워크(Symantic Network)의 예시
<figure class="half">
    <a href="https://user-images.githubusercontent.com/18658656/52614271-84f36980-2ed4-11e9-894e-43a878bc6a47.png"><img src="https://user-images.githubusercontent.com/18658656/52614271-84f36980-2ed4-11e9-894e-43a878bc6a47.png"></a>
    <a href="https://user-images.githubusercontent.com/18658656/52615081-37c4c700-2ed7-11e9-8950-1d16693c47bc.png"><img src="https://user-images.githubusercontent.com/18658656/52615081-37c4c700-2ed7-11e9-8950-1d16693c47bc.png"></a>
    <figcaption>시맨틱 네트워크</figcaption>
</figure>


# 마무리

다음 포스팅에서는, 시맨틱 네트워크의 상위 개념이라고 볼 수 있는 시맨틱 웹과 온톨로지, 시맨틱 웹 언어인 RDF와 OWL에 대해서 알아보도록 하자.

---

참고 및 출처  
> - [지식 그래프 위키백과](https://ko.wikipedia.org/wiki/%EC%A7%80%EC%8B%9D_%EA%B7%B8%EB%9E%98%ED%94%84)
> - [시맨틱 네트워크 위키백과](https://ko.wikipedia.org/wiki/%EC%8B%9C%EB%A7%A8%ED%8B%B1_%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC)
> - [지식 그래프 관련 블로그](https://psyhm.tistory.com/35?category=681399)
> - [친절한 구글씨의 통합검색, '지식그래프' - BLOTER](http://www.bloter.net/archives/149183)