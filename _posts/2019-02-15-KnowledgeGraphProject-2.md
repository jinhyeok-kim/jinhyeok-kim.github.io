---
title: "지식 그래프(KnowledgGraph) 프로젝트 - Before 2. 시맨틱 웹"
sidebar:
  title: "Sidebar"
  nav: sidebar-sample
readtime: true
toc: true
last_modified_at : 2019-02-15 16:01:01 #2019-02-13 21:14:00
categories:
  - 지식그래프
tags:
  - kgproject
  - semanticweb

---

오늘은 저번 지식그래프 프로젝트 - Before 1 에서 이야기했듯이 시맨틱 웹과 온톨로지에 대해서 이야기하고 이해해보도록 하겠다. <br>

이전 포스팅 : [지식 그래프(KnowledgGraph) 프로젝트 - Before 1. 지식 그래프 & 시맨틱 네트워크](https://jinhyeok-kim.github.io/%EC%A7%80%EC%8B%9D%EA%B7%B8%EB%9E%98%ED%94%84/KnowledgeGraphProject-1/)

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

- 시맨틱 웹 : XML에 기반한 시맨틱 마크업 언어를 기반으로 한다. 가장 단순한 형태인 **RDF**는 **< Subject, Predicate, Object >**의 트리플 형태로 개념을 표현한다.
  - ex1) ```<urn:바나나, urn:색, urn:노랑>```
    - **urn:바나나**라는 개념은 **urn:노랑**이라는 **urn:색**을 가지고 있다는 개념을 해석하고 처리 할 수 있게 된다.
  - ex2) ```<http://daum.net , urn:wikipedia-ko:소유, http://kakaocorp.com ```
    - 다음이 카카오 소유이다.

![default](https://user-images.githubusercontent.com/18658656/52713340-67a8c300-2fda-11e9-8dcc-bda2811da716.png)



---

설명을 통해 기존 웹과 시맨틱 웹의 차이를 알 수 있었다. <br>
그렇다면 시맨틱 웹이 뭐하는건지 알겠는데, 이 시맨틱 웹이라는 것은 어떻게 구성되어있는가<br>
시맨틱 웹에도 표준 계층 구조가 있다. 이 계층 구조를 살펴보도록 하자.

## 시맨틱 웹 기술 계층 구조

<figure style="width: 500px" class="align-center">
  <img src="https://user-images.githubusercontent.com/18658656/52841382-896f8a80-313f-11e9-8cf8-24f6467a5e29.jpg" alt="">
  <figcaption>시맨틱 웹 계층 구조</figcaption>
</figure> 
각 계층 구조의 정의는 [시맨틱 웹 : 위키백과](https://ko.wikipedia.org/wiki/%EC%8B%9C%EB%A7%A8%ED%8B%B1_%EC%9B%B9)에서 볼 수 있다.<br>

여기서는 각 계층이 어떤 역할을 하는지 조금 더 이해가 쉽게 설명해보자

- URI (Uniform Resource Identifier)
  - Resource Indentifier라는 말대로 리소스 식별자 즉 어떤 리소스를 가르키는 이름이다.
  - **"사과", "오렌지"와 같은 이름**을 예로 들 수 있다.
- IRI (International Resource Identifier with UNICODE)
  - UNICODE로 표현하여 어떤 문자든 언어와 플랫폼, 어플리케이션에 상관 없이 표현할 수 있게 해주는 표준이다.
  - "사과"를 "Apple"이라고 하지 않고 그냥 "사과"라고 표현 할 수 있게 된다.
- XML (eXtensible Markup Language)
  - HTML의 단점을 보완하고 태그를 자유롭게 생성하여, 어떤 문서나 객체를 정의 할 수 있게 해준다.
  - **"호랑이: 다리 4개, 꼬리 1개"** 등의 정의를 가능하게 해준다.
  - 단, **구조적 정의만을 제공**하며 **자원들 사이의 의미적 관계를 정의하지 못한다.**
- RDF (Resource Description Framework)
  - 웹 상에서 존재하는 자원을 XML 형태로 메타데이터를 표현하기 위한 기반이 된다.
  - Ontology에 존재하는 가장 작은 단위의 데이터 집합이다.
  - **"호랑이는 다리가 네개이다"**와 같은 문장을 정의 할 수 있게 해준다.
  - 즉, 데이터를 표현하는 문장이라고 생각하면 된다.
- RDFS
  - RDF의 Schema 정보로 경량의 온톨로지를 표현한다.
  - 여러개의 RDF를 이어서 만들어진 Class의 집합
- OWL
  - 특정 도메인에 대한 공유되는 일반적인 이해와 개념, 개념과의 관계를 표현하기 위한 언어이다.
  - RDFS에서 만들어진 Class간의 **관계를 정의**할 수 있다.
- Ontology
  - 일종의 사전과 같은 역할
  - URI로 명시된 개념/리소스들의 뜻을 **용어들의 관계성**에 의해 **컴퓨터가 찾을 수 있는 방법을 제공**해준다.
  - "아들"과 "어머니"의 관계가 역관계임을 통해 둘의 의미를 파악
  - "아들"과 "자식"의 관계가 ISA(A는 일종의 B이다)관계임을 명시하여 "자식"과 "어머니"의 뜻 또한 추론해 낼 수 있게 한다.

아래는 위키백과와 동일하다.

- SPARQL
  - RDF 질의를 위한 언어이다.
- RIF (Rule Interchange Format)
  - 규칙의 정의와 교환을 위한 계층이다.
- 로직(Logic)
  - 기존에 정의된 정보들을 바탕으로 새로운 결론을 도출하는 추론 기능 등을 의미한다.
- 증거/신뢰(Proof / Trust)
  - 웹의 정보에 대한 신뢰를 말한다.

## 시맨틱 웹 핵심기술

- 자원 서술 기술 - 명시적 메타데이터(explicit metadata)
  - RDF, XML
  - 메타데이터와 추론에 필요한 규칙등을 XML과 RDF와 같은 언어 기술을 통해 표현
  - XML을 이용하여 사용자가 **임의의 태그를 지정**하여 문서를 **구조화 가능**
  - RDF를 이용하여 **XML로 구조화된 문서**에 **의미 지정 가능**
    - RDF는 특정 대상(웹 상의 사람, 웹 문서)이 특정 속성에 대하여 특정 값을 가지고 있는 것을 표현

- 지식 서술 기술 - 온톨로지(Ontology)
  - 개념의 체계적인 규정을 의미
  - 컴퓨터가 판독이 가능하도록 용어와 용어들간의 관계를 표현하는 규정
  - 특정 주제에 관한 용어들의 집합, 용어 뿐만 아니라 **의미적 연결관계**와 **간단한 추론 규칙** 포함

- 통합 운용 기술 - 논리적 추론(logical reasoning)
  - 온톨로지와 함께 결합된 관계 정보들로부터 새로운 정보 도출해 내는 것을 가능하게 만듦

# 마무리

이번 포스팅에서 원래 시맨틱 웹과 온토로로지, RDF와 OWL에 대한 내용을 모두 포스팅 할 생각을 했지만, 생각보다 시맨틱 웹에 대한 내용이 길어지면서 다음 포스팅에서 마저 진행을 할 것 같다.
<br>
다음 포스팅에서는, 온톨로지와 RDF와 OWL에 대해서 알아보도록 하자.

 다음 포스팅 : [지식 그래프(KnowledgGraph) 프로젝트 - Before 3. 온톨로지 & RDF & OWL](https://jinhyeok-kim.github.io/%EC%A7%80%EC%8B%9D%EA%B7%B8%EB%9E%98%ED%94%84/KnowledgeGraphProject-3/)

**블로그 내용 중 문제가 되거나 잘못 이야기한 내용이 있으면 언제든 연락 부탁드립니다.**

---

참고 및 출처  
> - [시맨틱 웹 위키백과](https://ko.wikipedia.org/wiki/%EC%8B%9C%EB%A7%A8%ED%8B%B1_%EC%9B%B9)
> - [(Semantic Web) Basic of Semantic Web](https://operatingsystems.tistory.com/entry/Basic-of-Semantic-Web?category=578406)
> - 시맨틱 웹과 시맨틱 기술 - 정보검색론특강 & 전자기록물 관리특강 PPT