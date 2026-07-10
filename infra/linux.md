---
description: 1991년 리누스 토르발스가 개발한 유닉스 기반의 오픈소스 운영체제(OS)
---

# Linux



### 서버 배포시 리눅스를 사용하는 이유?











***

## 우분투 Ubuntu

> 커널을 바탕으로 운영체제의 목적에 맞게 만들어진 소프트웨어+기능 배포판\
> 우분투 외에도 센토스, 레드햇, 데비안 등이 있다.



{% hint style="info" %}
맥은 SSH 를 기본 지원하기에 서버배포시에는 가상머신을 설치할 필요 없이 터미널로 바로 리눅스를 사용할 수 있었지만, 특정 서버 없이 그냥 리눅스(우분투)를 써보고 싶다면 가상머신이 필요하다.<br>

방법1. 가상머신 `Ubuntu ARM64(aarch64)`  설치 추천 -> 우분투 설치

방법2. docker desktop 이 깔려있다면 docker 를 실행시킨 후&#x20;
{% endhint %}



### 우분투 명령어

{% tabs %}
{% tab title="우분투 설치" %}
#### 운영체제: 💻 mac m4 air 기준



*   <mark style="color:red;">**`docker run -it ubuntu:24.04`**</mark>

    : 우분투 설치 명령어, 24.04 는 버전 이름



* 추가 설치 명령어
  * <mark style="color:red;">**`apt install sudo`**</mark> : sudo 명령어를 사용할 수 있도록 설치한다
  * <mark style="color:red;">**`sudo apt update`**</mark> : 설치 가능한 프로그램 목록을 최신으로 가져온다
  * <mark style="color:red;">**`sudo apt upgrade -y`**</mark> : 현재 설치된 프로그램 목록을 최신으로 업그레이드 한다
  * <mark style="color:red;">**`sudo apt install -y git curl wget vim unzip zip build-essential`**</mark>\
    : 개발에 자주 사용하는 기본 프로그램들을 설치한다

<table data-search="false"><thead><tr><th width="211.6640625">프로그램</th><th>용도</th></tr></thead><tbody><tr><td>git</td><td>소스코드 버전 관리 (GitHub 사용)</td></tr><tr><td>curl</td><td>URL 로 데이터를 다운로드 하거나 API 호출</td></tr><tr><td>wget</td><td>파일 다운로드</td></tr><tr><td>vim</td><td>터미널에서 사용하는 텍스트 편집기</td></tr><tr><td>unzip</td><td>ZIP 압축해제</td></tr><tr><td>zip</td><td>ZIP 압축 생성</td></tr><tr><td>build-essential</td><td>C/C++ 컴파일러 와 빌드 도구 모음 (gcc, g++, make 등)</td></tr></tbody></table>


{% endtab %}

{% tab title="기본 명령어" %}
* <mark style="color:red;">**`cd ~`**</mark> : 경로 표시를 \~ 로 변경하기
* <mark style="color:red;">**`sudo`**</mark> : 일반 사용자가 일시적으로 관리자 권한을 가질 수 있도록 허용하는 명령어&#x20;



* <mark style="color:red;">**`docker run -it --name`**</mark>**` `**<mark style="color:$warning;">**`컨테이너명`**</mark> : 새 컨테이너를 생성
* <mark style="color:red;">**`docker rename`**</mark>**` `**<mark style="color:$success;">**`boring_chatterjee`**</mark>**` `**<mark style="color:$warning;">**`새컨테이너명`**</mark> : 기본 컨테이너명을 변경
* <mark style="color:red;">**`docker ps -a`**</mark> : 생성된 컨테이너 목록 확인
* <mark style="color:red;">**`docker start`**</mark>**` `**<mark style="color:$warning;">**`컨테이너명`**</mark> : 터미널 -> 우분투, 컨테이너 다시 시작
* <mark style="color:red;">**`docker exec -it`**</mark>**` `**<mark style="color:$warning;">**`컨테이너명`**</mark>**` `**<mark style="color:red;">**`bash`**</mark> : 터미널 -> 우분투, 컨테이너에 다시 접속
{% endtab %}

{% tab title="사용자 권한" %}
*   리눅스에서는 프롬프트 끝 문자가 사용자 권한을 나타냄

    * <mark style="color:red;">**`#`**</mark> : 관리자(root) 권한 , 시스템의 모든 파일을 수정할 수 있음
    * <mark style="color:red;">**`$`**</mark> : 일반 사용자 권한


*   <mark style="color:red;">**`adduser 사용자명`**</mark> : 새 일반 사용자 생성하기

    * <mark style="color:red;">**`su - 사용자명`**</mark> : 일반 사용자로 전환 (\~$)
    * <mark style="color:red;">**`groups 사용자명`**</mark> : 사용자의 권한 확인하기


* <mark style="color:red;">**`exit`**</mark> : 로그아웃, 관리자 권한으로 돌아감
* <mark style="color:red;">**`sudo usermod -aG sudo 사용자명`**</mark> : 일반 사용자에게 관리자 권한 부여



* 일반 계정에서 root 권한을 얻는 방법
  * <mark style="color:red;">**`sudo su`**</mark> :&#x20;
  * <mark style="color:red;">**`sudo -i`**</mark> : 터미널을 root 계정으로 전환
  * <mark style="color:red;">**`su -root 비밀번호`**</mark> :
{% endtab %}
{% endtabs %}





