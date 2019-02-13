---
title: "지식 그래프(KnowledgGraph) 프로젝트 - Before 2. 시맨틱 웹 & 온톨로지 & RDF & OWL"
sidebar:
  title: "Sidebar"
  nav: sidebar-sample
readtime: true
toc: true
last_modified_at : 2019-02-13 21:14:00
categories:
  - 개발
tags:
  - kgproject
  - semanticweb
  - ontologies
  - owl
  - rdf
---

오늘은 저번 지식그래프 프로젝트 - Before 1 에서 이야기했듯이 시맨틱 웹과 온톨로지에 대해서 이야기하고 이해해보도록 하겠다. <br>

이전 포스팅 : [지식 그래프(KnowledgGraph) 프로젝트 - Before 1. 지식 그래프 & 시맨틱 네트워크](https://jinhyeok-kim.github.io/%EA%B0%9C%EB%B0%9C/KnowledgeGraphProject-1/)

# 시맨틱 웹(Semantic Web)란?
--- 
## 시맨틱 웹(Semantic Web)의 정의

위키백과에서는 시맨틱 웹에 대해 다음과 같이 설명하고 있다.

> 시맨틱 웹(Semantic Web)은 '의미론적인 웹'이라는 뜻으로, 현재의 인터넷과 같은 분산환경에서 리소스(웹 문서, 각종 화일, 서비스 등)에 대한 **정보와 자원사이의 관계-의미 정보(Semanteme)**를 기계(컴퓨터)가 처리할 수 있는 **온톨로지** 형태로 표현하고, 이를 자동화된 기계(컴퓨터)가 처리하도록 하는 프레임워크이자 기술이다.
> <figcaption>출처 : 시맨틱 웹 위키백과</figcaption>

저번 포스팅을 보고나서 이번 시맨틱 웹의 정의를 보면 상대적으로 이해를 할 수 있는 부분들이 늘었다.
<br>
- **정보와 자원사이의 관계-의미정보**를 **온톨로지** 형태로 표현하고..
<br>

'정보와 자원사이의 관계-의미정보'라는 시맨틱 정보라는 것은 알겠고, '온톨로지'형태로 표현한다는 말에서 '온톨로지'라는 용어는 아직 낯설다.
<br>
온톨로지 형태는 조금이따가 알아보고 우선은 시맨틱 웹에 대해서 더 알아보자.

## 시맨틱 웹과 기존 웹의 차이

- 기존의 웹 : 기존의 HTML로 작성된 문서는 **의미정보를 해석할 수 있는 메타데이터**보다 사람의 눈으로 보기에 용이한 **시각정보에 대한 메타데이터**와 **자연어로 기술된 문장으로 가득 차 있다.
  - ex) ```<em>바나나</em>는 <em>노란색</em>이다.```

위의 예시에서 ```<em>```은 그저 바나나와 노란색을 강조하기 위해 사용되었으며, 바나나와 노란색이 어떤 관계를 가지는지는 알 수 없다. <br>

- 시멘틱 웹 : XML에 기반한 시맨틱 마크업 언어를 기반으로 한다. 가장 단순한 형태인 **RDF**는 **< Subject, Predicate, Object >**의 트리플 형태로 개념을 표현한다.
  - ex1) ```<urn:바나나, urn:색, urn:노랑>```
    - **urn:바나나**라는 개념은 **urn:노랑**이라는 **urn:색**을 가지고 있다는 개념을 해석하고 처리 할 수 있게 된다.
  - ex2) ```<http://daum.net , urn:wikipedia-ko:소유, http://kakaocorp.com ```
    - 다음이 카카오 소유이다.

![default](https://user-images.githubusercontent.com/18658656/52713340-67a8c300-2fda-11e9-8dcc-bda2811da716.png)



---

처음에 위키백과에서 가져온 지식 그래프의 정의를 살펴보면, **시맨틱 검색 정보**를 사용하고, **시맨틱 네트워크**를 구축하였다는 정보를 확인 할 수 있다.  <br>
<br>
그렇다면 시맨틱 검색 정보를 사용 할 때 활용한 시맨틱 네트워크는 무엇인가?

# 시맨틱 네트워크(Semantic Network)란?
## 시맨틱 네트워크(Semantic Network)의 정의
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
## 시맨틱 네트워크(Semantic Network)의 예시
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