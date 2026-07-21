# Python



## 머신러닝 vs 딥러닝 은 무엇이 다를까?

{% hint style="info" %}
인공지능 > 머신러닝 > 딥러닝
{% endhint %}

### 머신 러닝 Machine Leaning

> 사람이 특징(Feature)을 어느정도 직접 만들어주고, 컴퓨터가 그 규칙을 학습하는 방식

* **XGboost , LightGBN , Random Forest,  s ssdsdsdacikit-learn** 등의 모델을 많이 사용한다.
* 표 형태(Tabular Data) 등에 강하다. <mark style="color:$success;">(ex: 신용평가, 집값 예측, 보험료 계산, 고객 이탈 예측)</mark>

### 딥 러닝 Deep Leaning

> 사람이 일일히 설계하지 않아도, 신경망(Neural Network)이 알아서 특징을 스스로 학습한다.

* 복잡한 데이터에 강하다. <mark style="color:$success;">(ex: ChatGPT, Claude, Gemini, 얼굴인식, 자율주행, 음성인식)</mark>



***



## 프레임워크 종류

#### FastAPI

* 매우 빠른 성능, 자동 API 문서
* 타입 힌트 기반
* AI 서버 구축에 최적화

주 사용처 : AI 모델 API, RestAPI, 마이크로 서비스, LLM 서버

<details>

<summary>딥 러닝 프레임워크</summary>

#### PyTorch

* 딥러닝 프레임워크

주 사용처: ChatGPT, 이미지 생성, 음성 AI, LLM, 객체인식

#### TensorFlow

</details>





#### Django

* 기능이 매우 많음
* 관리자 페이지 기본 제공
* ORM 내장
* 인증기능 내장

주 사용처 : 쇼핑몰, 게시판, ERP, CMS&#x20;



***

## 라이브러리 종류

<details>

<summary>데이터 전처리 과정</summary>

#### NumPy

* 모든 과학 계산의 기반&#x20;
* AI 연산 기반

#### Pandas

* 데이터 분석 라이브러리
* 한마디로 엑셀을 파이썬으로 다루는 도구
* AI 를 학습시키기 전에 데이터의 전처리과정을 맡음

#### Polars

* 대용량 처리에서 많이 사용함

</details>



<details>

<summary>RAG 구축, 연결 라이브러리</summary>

#### LangChain

* LLM 애플리케이션을 만들때 많이 사용함, RAG 연결 기능
* GPT, Cloud, Gemini, 로컬 LLM 을 연결하는 역할

#### 라마 인덱스 Llamalndex

* RAG 구축용 라이브러리

</details>



<details>

<summary>딥러닝 라이브러리</summary>

#### Keras

* TensorFlow 와 함께 제공되어 기본 딥러닝 API 역할을 하는 경우가 많다.
* TensorFlow 를 더 쉽게 사용할 수 있도록 만든 고수준의 API

</details>



<details>

<summary>머신러닝 라이브러리</summary>

#### XGboost

표(테이블)의 형태로 데이터를 높은 정확도로 학습시키는 라이브러리

</details>





***

## AI 아키텍처 종류

### RAG

**RAG(Retrieval-Augmented Generation)** : 검색을 통해 생성을 보강하는 기술

장점 : 필요한 자료를 실시간으로 찾을 수 있다.





***

## DB



### 벡터 데이터베이스 Vector Database

AI 가 단어를 숫자의 배열(숫자 벡터)로 바꾸는 것을 **임베딩(Embedding)**&#xC774;라고 한다. \
AI 는 문장을 벡터로 변환하여 데이터베이스에 저장한 후, \
사용자가 입력한 문장을 벡터 변환하여 DB 에서 가장 비슷한 벡터를 검색한다.

즉, 일반 DB 는 정확히 일치하는 값을 검색하지만, 벡터 데이터 베이스는 **가장 비슷한 의미**를 검색한다.\
⇒ 이것을 **의미 기반 검색(Sementic Search)**&#xC774;라고 한다.

#### 벡터 데이터베이스 종류

* **Chroma** : 입문용으로 가장 많이 사용. 로컬에서도 쉽게 실행 가능.
* **FAISS** : Meta에서 개발. 매우 빠른 벡터 검색 라이브러리.
* **Milvus** : 대규모 서비스용 오픈소스 벡터 DB.
* **Qdrant** : RAG 서비스에서 많이 사용하는 오픈소스 벡터 DB.
* **Pinecone** : 클라우드 기반 관리형 벡터 DB.





### Redis

> 메모리(RAM)에 데이터를 저장하는 **초고속 NoSQL 데이터 베이스**

* 빠른 조회를 목적으로 하는 **Key-Value DB**
* 만료시간 (TTL) 기능을 지원한다.

주 사용처 : 로그인 토큰 저장, 캐시, 조회수 증가, 실시간 랭킹, 채팅





