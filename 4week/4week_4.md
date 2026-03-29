# SQL_BASIC 4주차 정규 과제 

📌SQL_BASIC 정규과제는 매주 정해진 분량의 `초보자를 위한 BigQuery(SQL) 입문` 강의를 듣고 간단한 문제를 풀면서 학습하는 것입니다. 이번주는 아래의 **SQL_Basic_4th_TIL**에 나열된 분량을 수강하고 `학습 목표`에 맞게 공부하시면 됩니다.

**4주차 과제부터는 강의 내용을 정리하는 것과 함께, 프로그래머스에서 제공하는 SQL 문제를 직접 풀어보는 실습도 병행합니다.** 강의에서는 **배운 내용을 정리하고 주요 쿼리 예제를 정리**하며, 프로그래머스 문제는 **직접 풀어본 뒤 풀이 과정과 결과, 배운 점을 함께 기록**해주세요. 완성된 과제는 Github에 업로드하고, 링크를 스프레드시트 'SQL' 시트에 입력해 제출해주세요.

**👀(수행 인증샷은 필수입니다.)** 

## SQL_BASIC_4th

### 섹션 4. 쿼리 잘 작성하기, 쿼리 작성 템플릿 및 오류를 잘 디버깅하기

### 3-4. 오류를 잘 디버깅하는 방법



## 섹션 5. 데이터 탐색 - 변환

### 4-1. INTRO

### 4-2. 데이터 타입과 데이터 변환(CAST, SAFE_CAST)

### 4-3. 문자열 함수(CONCAT, SPLIT, REPLACE, TRIM, UPPER)

### 4-4. 날짜 및 시간 데이터 이해하기(1) (타임존, UTC, Millisecond, TIMESTAMP/DATETIME)



## 🏁 강의 수강 (Study Schedule)

| 주차  | 공부 범위              | 완료 여부 |
| ----- | ---------------------- | --------- |
| 1주차 | 섹션 **1-1** ~ **2-2** | ✅         |
| 2주차 | 섹션 **2-3** ~ **2-5** | ✅         |
| 3주차 | 섹션 **2-6** ~ **3-3** | ✅         |
| 4주차 | 섹션 **3-4** ~ **4-4** | ✅         |
| 5주차 | 섹션 **4-4** ~ **4-9** | 🍽️         |
| 6주차 | 섹션 **5-1** ~ **5-7** | 🍽️         |
| 7주차 | 섹션 **6-1** ~ **6-6** | 🍽️         |

<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 개념정리

## 3-4. 오류를 디버깅하는 방법

~~~
✅ 학습 목표 :
* 오류의 정의에 대해 설명할 수 있다. 
* 오류 메시지를 보고 디버깅이라는 과정을 수행할 수 있다. 
~~~

오류: 정확하거나 잘못된 행동
길잡이 역할 + 문제 진단의 역할

대표적인 오류: 문법 오류

SELECT list must no be empty at[10:1]
: 밑줄 앞이나 뒤에 오류가 있을 가능성이 높음

오류 디버깅을 위해 1.구글 검색 2.챗지피티 사용 

Number of arguments doest no match for aggregate function of COUNT
: count() 안의 인자 수 일치 x

오류메시지 해결의 핵심
: 오류 메시지 번역/해석해서 오류 메시지 검색해서 해결한다.



## 4-2. 데이터 타입과 데이터 변환(CAST, SAFE_CAST)

~~~
✅ 학습 목표 :
* 데이터 타입의 종류를 설명할 수 있다. 
* 데이터 타입을 변환하는 방법을 설명할 수 있다. 
~~~

SELECT 문에서 데이터를 변환시킬 수 있음
데이터의 타입에 따라 유형이 있음

### 데이터 타입
숫자, 문자, 시간, 날짜, 부울(Bool) - 참/거짓

데이터 타입이 중요한 이유
: 보이는 것과 저장된 것의 차이가 존재

### 자료 타입 변경하기
CAST 함수

SELECT
    CAST(1 AS STRING)


수학 함수는 수학 연산(평균, 표준편차, 코사인 등)이 존재
나누기를 할 경우 X/Y 대신 SAFE_DIVIDE 함수 사용


## 4-3. 문자열 함수(CONCAT, SPLIT, REPLACE, TRIM, UPPER)

~~~
✅ 학습 목표 :
* 문자열 함수들의 종류를 이해하고 어떠한 상황에서 사용하는지 설명할 수 있다. 
~~~

문자열 붙이기, 분리하기, 수정하기, 자르기, 대문자 변환

----문자열 붙이기 => CONCAT
SELECT
  CONCAT("안녕", "하세요") AS result;


----문자열 분리하기=> SPLIT
SELECT
  SPLIT("가, 나, 다, 라", ",") AS result;

---특정 단어 수정하기=> REPLACE
SELECT
  REPLACE("안녕하세요", "안녕", "실천") AS result;
----REPLACE(문자열 원본, 찾을 단어, 바꿀 단어)


----문자열 자르기 => TRIM
SELECT 
  TRIM("안녕하세요", "하세요") AS result;

----영어 소문자를 대문자로 변경=> UPPER
SELECT
  UPPER("abc") AS result;


## 4-4. 날짜 및 시간 데이터 이해하기(1) (타임존, UTC, Millisecond, TIMESTAMP/DATETIME)

~~~
✅ 학습 목표 :
* 날짜 및 시간 데이터 타입과 UTC의 개념을 설명할 수 있다. 
* DATE, DATETIME, TIMESTAMP 에 대해서 설명할 수 있다.
* 시간함수들의 종류와 시간의 차이를 추출하는 방법을 설명할 수 있다. 
~~~

시간-> updated_at, created_at

### 날짜 및 시간 데이터 타입 파악하기: DATE, DATETIME, TIMESTAMP

타임존: GMT. 영국 그리니치 천문대 기준
UTC: 국제적인 표준 시간

타임존이 존재한다=특정 지역의 표준 시간대

TIMESTAMP: UTC부터 경과한 시간을 나타내는 값, TIME ZONE 정보 있음


### 시간데이터 다루기- Millisecond

시간의 단위, 천 분의 1초
빠른 반응이 필요한 분야에서 사용(초보다 더 정확하게)

microsecond: 밀리세컨즈의 1/1000

millis에서 datetime으로 변환가능

### TIMESTAMP와 DATETIME 비교

TIMESTAMP에는 UTC정보가 있고(한국시간-9시간), DATETIME은 T가 나옴(TIME을 의미)

### DATETIME 함수 - CURRENT_DATETIME

EXTRACT 함수: DATETIME에서 특정 부분만 추출하고 싶은 경우

요일을 추출하고 싶은 경우: EXTRACT(DAYOFWEEK FROM 어쩌고)

DATE와 HOUR만 남기고 싶은 경우=> 시간 자르기

PARSE_DATETIME: 문자열로 저장된 DATETIME을 DATETIME 타입으로 바꾸고 싶은 경우

FORMAT_DATETIME: DATETIME 타입 데이터를 특정 형태의 문자열 데이터로 변환하고 싶은 경우 

LAST_DAY: 마지막 날을 알고 싶은 경우 - 자동으로 월의 마지막 값을 계산해서 특정 연산을 할 경우 

DATETIME_DIFF: 두 DATETIME의 차이를 알고 싶은 경우




<br>

<br>

---

# 2️⃣ 확인문제 & 문제 인증

## 프로그래머스 문제 

> 조건에 맞는 도서 리스트 출력하기
>
> **먼저 문제를 풀고 난 이후에 확인 문제를 확인해주세요**
>
> 문제 링크 
>
> :  https://school.programmers.co.kr/learn/courses/30/lessons/144853

![alt text](image.png)



## 문제 1

> **🧚Q. 프로그래머스 문제를 풀던 규서는 여러 번의 시행착오 끝에 결국 혼자 해결하기 어려워 오류 메시지를 공유하며 도움을 요청했습니다. 여러분들이 오류 메시지를 확인하고, 해당 SQL 쿼리에서 어떤 부분이 잘못되었는지 오류 메시지를 해석하고 찾아 설명해주세요.**

~~~sql
# 조건에 맞는 도서 리스트 출력하기
# 규서의 SQL 첫 번째 풀이
SELECT BOOK_ID, PUBLISHED_DATE
FROM BOOK
WHERE CATEGORY = '인문'
  AND YEAR(PUBLISHED_DATE, 2021);
  
오류 메시지 : Error: Number of arguments does not match for function YEAR
~~~



~~~
오류 메시지 해석: YEAR의 인자 개수가 일치하지 않는다. 
설명: YEAR() 함수는 인자 1개만 받게 되있음. 근데 저 SQL문에서 두개를 받고 있기 때문에 오류 발생
~~~



### 🎉 수고하셨습니다.