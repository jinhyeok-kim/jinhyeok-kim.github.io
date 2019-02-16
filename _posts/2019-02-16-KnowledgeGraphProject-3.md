---
title: "지식 그래프(KnowledgGraph) 프로젝트 - Before 3. 온톨로지 & RDF & OWL"
sidebar:
  title: "Sidebar"
  nav: sidebar-sample
readtime: true
toc: true
last_modified_at : 2019-02-16 16:48:08 #2019-02-15 17:54:18
categories:
  - 지식그래프
tags:
  - kgproject
  - owl
  - rdf
  - ontology

---

오늘은 저번 지식그래프 프로젝트 - Before 2 에서 이야기했듯이 온톨로지에 대해서 이야기하고 이해해보도록 하겠다. <br>

이전 포스팅 : [지식 그래프(KnowledgGraph) 프로젝트 - Before 2. 시맨틱 웹](https://jinhyeok-kim.github.io/%EA%B0%9C%EB%B0%9C/KnowledgeGraphProject-2/)

# 온톨로지(Ontology)란?
--- 
## 온톨로지(Ontology)의 정의

위키백과에서는 온톨로지에 대해 다음과 같이 설명하고 있다.

> 온톨로지(Ontology)란 사람들이 세상에 대하여 **보고 듣고 느끼고 생각하는 것**에 대하여 서로 간의 토론을 통하여 합의를 이룬 바를, **개념적이고 컴퓨터에서 다룰 수 있는 형태로 표현한 모델**로,...중략...<br><br>
> 온톨로지는, 정보시스템의 대상이 되는 **자원의 개념을 명확하게 정의**하고 **상세하게 기술**하여 보다 **정확한 정보를 찾을 수 있도록** 하는데 목적이 있다.<br><br>
> 온톨로지는 시맨틱 웹을 구현할 수 있는 도구로서, **지식개념을 의미적으로 연결할 수 있는 도구**로서 RDF, OWL, SWRL 등의 언어를 이용해 표현한다.
> <figcaption>출처 : 온톨로지 위키백과</figcaption>

<br>
위키백과에서 거창하게 이야기하고 있지만, 온톨로지의 핵심은 **지식개념을 의미적으로 연결할 수 있는 도구**라는 점이 중요하다.  
이 것이 왜 중요한지 필요성을 살펴보자.

## 온톨로지(Ontology)의 필요성
<br>
board의 속성에  
'눈'이 있으면 '스노보드'  
'음식'이 있으면 '식탁'  
'인터넷'이 있으면 '온라인 게시판'  
<br>
이렇게 같은 단어라도 문맥에 따라서 뜻이 달라지는데, 이렇게 문맥에 따라달라지는 것을 기계(컴퓨터)가 이해하기 위해 단어의 의미를 연결 해주는 도구가 온톨로지(Ontology)다.  
온톨로지는(Ontology)는 세상의 모든 사물들 간의 관계를 나타내는 것으로 쓰인다.
<br><br>
지금부터는 온톨로지를 표현하기 위한 언어인 RDF와 OWL에 대해서 알아보자.
<br><br><br>
# RDF(Resource Description Franework)란?

> Resourcse : URI를 갖는 모든 것 (웹 페이지, 이미지, 동영상 등) <br>
> Description : 자원(Resource)들의 속성, 특성, 관계 <br>
> Framework : 위의 것들을 기술하기 위한 모델,언어, 문법

- **웹**에 있는 **Resource**에 대한 정보를 표현하기 위한 **언어**
- 특히, **웹 Resource에 대한 Metadata를 표현**하기 위함.


## RDF(Resource Description Franework) 데이터 모형
<br>
RDF 데이터 모형은  
정보자원(Resource) : Subject    
속성 유형(Property Type) : Predicate  
속성값(Value) : Object  

위와 같이 구분 할 수 있으며 아래 그림과 같이 표현 할 수 있다.

<figure style="width: 500px" class="align-center">
  <img src="https://user-images.githubusercontent.com/18658656/52896851-c0fa3780-3210-11e9-847e-5a1e4a8bd2b6.png" alt="">
  <figcaption>Triple Model</figcaption>
</figure> 

## RDF(Resource Description Franework) 예시

```
<?xml version="1.0>

<RDF>
  <Description about="http://jinheyok-kim.github.io">
    <author>Jinhyeok Kim</author>
    <homepage>JINHYEOK BLOG</homepage>
  </Description>
</RDF>
```
<figure style="width: 500px" class="align-center">
  <img src="https://user-images.githubusercontent.com/18658656/52896850-be97dd80-3210-11e9-8299-93369bb3f8c1.png" alt="">
  <figcaption>Triple Model</figcaption>
</figure>

<br><br><br>
# OWL(Web Ontology Language)란?

RDF는 데이터 모델에 대한 간단한 의미론을 제공하고, RDFS는 RDF 자원의 속성과 클래스를 표현할 수 있는 어휘로서, 속성과 클래스 일반화 계층 구조에 대한 의미론을 제공하지만 RDF와 RDFS 둘 다 **의미들 간의 관계**에 대해 설명하지 못한다.  
OWL(Web Ontology Language)에서는 DFS에서 만들어진 **Class간의 관계를 정의**할 수 있다.
  
일종의 RDF의 확장판이라고 볼 수 있다.  


## OWL(Web Ontology Language) 문법

OWL은 온톨로지를 위한 언어이므로 모든 문법을 설명하기엔 내용이 길고, 문법을 몇 개만 간단히 소개하도록 하자.  

- owl:allValuesFrom : 부모는 모두 Human이다.
  
```
<owl:Restriction>
  <owl:onProperty rdf:resource="#hasParent" />
  <owl:allValuesFrom ref:resource="#Human" />
</owl:Restriction>
```
<figure style="width: 500px" class="align-center">
  <img src="https://user-images.githubusercontent.com/18658656/52897303-361c3b80-3216-11e9-83cd-e44394714b21.png" alt="">
  <figcaption>부모는 모두 Human이다.</figcaption>
</figure>


- owl:someValuesFrom : 부모 중 적어도 한 명은 Physician이다.

```
<owl:Restriction>
  <owl:onProperty rdf:resource="#hasParent" />
  <owl:someValuesFrom ref:resource="#Physician" />
</owl:Restriction>
```
<figure style="width: 500px" class="align-center">
  <img src="https://user-images.githubusercontent.com/18658656/52897304-361c3b80-3216-11e9-80f8-0f1f66a80b6b.png" alt="">
  <figcaption>부모 중 적어도 한 명은 Physician이다.</figcaption>
</figure>

더 많은 문법 및 OWL에 대한 설명은 아래 링크에서 확인 할 수 있다.<br>
<http://www.w3c.or.kr/Translation/REC-owl-features-20040210/#s3.1>

# 마무리

이번 포스팅으로 대략적으로 이론적인 부분을 마무리한 것 같다. 물론 프로젝트를 진행해가면서 더 많은 이론적인 부분, 실습적인 부분들이 많이 필요 할 것으로 생각된다. 천천히 진행해나가면서 배운 것들을 정리하면서 올려보도록 할 예정이다.
<br>

**블로그 내용 중 문제가 되거나 잘못 이야기한 내용이 있으면 언제든 연락 부탁드립니다.**

---

참고 및 출처  
> - [온톨로지 위키백과](https://ko.wikipedia.org/wiki/%EC%98%A8%ED%86%A8%EB%A1%9C%EC%A7%80)
> - [자원 기술 프레임워크 위키백과](https://ko.wikipedia.org/wiki/%EC%9E%90%EC%9B%90_%EA%B8%B0%EC%88%A0_%ED%94%84%EB%A0%88%EC%9E%84%EC%9B%8C%ED%81%AC)
> - [온톨로지 개념 및 표현언어 - 김동범](https://www.slideshare.net/barambi/ss-1514567)
> - [RDF 개념 및 구문 소개 - 김동범](https://www.slideshare.net/barambi/rdf)