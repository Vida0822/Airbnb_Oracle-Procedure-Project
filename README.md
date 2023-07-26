# :pushpin: Procedure를 활용한 Airbnb 기능구현 

> Oracle의 PLSQL(Procedure)을 활용한 에어비엔비 기능 구현 (데이터베이스 기반 프로그래밍) 

</br> 

### 목차

1. 제작기간 & 참여 인원  <br>
2. 사용 기술  <br>
3. 프로젝트 개요<br>
4. 개발단계 및 일정  <br>
5. 요구분석 : Use-case Diagram 설계  
6. DB 모델링 : ERD / EXERD 설계    <br>
8. 핵심기능 코딩 <br>
9. 트러블 슈팅  <br>
10. 발표영상 (본인 발표) 
11. 프로젝트 회고 <br>

</br></br>



## 1. 제작 기간 & 참여 인원 

👩‍👧‍👧 팀 프로젝트 (7인)<br>

📆 2023 3월 31일 ~ 4월 10일 (10일)  <br>

</br>

## 2. 사용 기술  

- PL/SQL <br>
- 툴 : Oracle Database 19c (sql plus) / SQL Developer    <br>

</br>



## 3. 프로젝트 개요

​	이 프로젝트는 데이터베이스 기반 프로그래밍으로 구현한 sql 프로젝트이다. 프론트앤드와 백앤드 기술 없이, 즉 화면 구현 및 서버 코딩을 하지 않고 특정 기능을 실행했을 때 발생하는 db의 변화(쿼리 실행결과)만 확인한다. 세계 최대의 숙박 공유 서비스, 'airbnb'의 웹 사이트를 주제로 선정하였으며 요구분석을 바탕으로 DB를 설계한 후 해당 기능을 수행하는 쿼리를 작성했다. 프로젝트 쿼리는 Oracle의 pl/sql(procedure)로만 작성되었다.

</br>

pl/sql이란? 



## 4. 개발단계 및 일정 

​	 이번 데이터베이스 기반 기능구현을 위해, 우리는 개발 단계 및 업무를 크게 3가지로 나누었다.  <br>

1. 요구분석  <br>

2. DB 모델링  <br>

3. CRUD 기능구현  <br> </br>

   

<details>
<summary><b> 개발단계 3 steps 상세</b></summary>
<div markdown="1">

**1st step : [요구분석]** <br>

1. **핵심 업무 프로세스 파악** : 사이트 전체적인 흐름 파악 => 액터 도출  <br>
2. **디테일한 기능 파악** : 각 액터별&기능별 상세한 기능/화면구성 파악  <br>
3. **요구분석서 작성** : 팀원들과 충분한 논의 후 최종적인 요구분석 취합본 작성 <br> </br>


**2nd step : [DB 모델링]** (**다같이)*<br>

1) **개념적 DB 모델링**<br>

    : 1-개체(entity) 추출 2-속성(Attribute)추출 3-관계(R)정의 => ERD *<br>

2) **논리적 DB 모델링** <br>

   1- ERD를 보고 1:1로 매칭시키는 매핑규칙(mapping rule)에 따라 스키마를 설계 => eXERD * <br>

   2- 정규화 <br>

   3- 사용할 DBMS 결정 	<br>

3) **물리적 DB 모델링** : 자료형, 크기, 역정규화 <br>

   - 컬럼 확정: 타입, 크기 <br>

   - 데이터의 사용량 분석해서 효율적인 데이터베이스가 될 수 있도록 역정규화 작업 <br>

   - 성능위해 인덱스 처리 <br>

 4) **DB 구축** : 테이블 생성 및 데이터 입력 <br>

    * 설계한 스키마에 따라 테이블을 생성한다</br>

      

**3rd step : [쿼리 작성: CRUD 기능구현]** (**3팀으로 나눠서 분담작업)*  <br>

: 데이터 처리 과정  (**상세한 요구분석 바탕**으로 실제로 그 작업을 쿼리로 구현)  <br>

* **데이터 조회** : 프로세스상 중요한 필수 표시 페이지를 구현, 데이터를 조회한다 - **SELECT** <br>

* **데이터 입력** : 각 스키마에 맞는 데이터를 입력하여 테이블을 채운다 -**INSERT** <br>

* **데이터 수정** : 변경사항을 반영하는 기능을 구현한다 - **UPDATE**  <br>

* **데이터 삭제** : 등록한 데이터들을 다시 삭제하는 기능을 구현한다 - **DELETE** <br>

* **권한 처리** : 각 사용자에 따라 권한(사용가능한 기능)을 설정해 부여한다 - **기능 구현 후 권한설정코딩 추가**<br>

</div>
</details>

</br>

<details>
<summary><b> 개발일정 펼치기</b></summary>
<div markdown="1">

​	위의 개발 단계 및 각 업무 내용을 기반해 개발일정을 다음과 같이 수립했다. 

**03/31 (금)** 각자 전반적인 프로세스 파악 후 요구분석 양식 채워오기 

**04/01 (토)** 요구분석 완료 

**04/02 (일)** 요구분석서 취합본 작성  

------------- *요구분석(서)* ----------------- 

**04/03 (월)** 개념적 DB 모델링 (ERD 작성) 

**04/04 (화)** 물리적 DB 모델링 (eXERD 작성) 

**04/05 (수)** DB 구축 (테이블 생성&데이터 엑셀로 정리 후 임포트)  +  구현할 페이지와 기능정리 & 쿼리 역할분담 

-------------*DB 모델링* ----------------------

**04/06 (목)** 기능구현(쿼리작업) 

**04/07 (금)** 기능구현(쿼리작업) 

----------------*쿼리작업* ---------------

**04/08 (토)** 기능구현(쿼리작업완료) + 발표준비 병행 

**04/09 (일)** 발표준비

---------------*ppt+ 발표준비* ---------------- 

**04/10 (월)** 발표일! 

</div>
</details>

</br>

## 5. 요구분석 : Use-case Diagram 설계 

​	다같이 사이트를 분석한 후, 우리는 

1) 텍스트 기반의 요구사항 문서와 
2) 사용자 관점에서 시스템의 입출력만을 생각해 분석하는 블랙박스 분석을 기초로 사용자와 시스템 사이의 상호작용을 보여주는 유스케이스 다이어그램을 설계하였다. 

<details>
<summary><b> 요구사항문서 펼치기</b></summary>
<div markdown="1">

<img width="625" alt="요구분석1" src="https://github.com/Vida0822/Airbnb_Oracle-PLSQL-Project/assets/132312673/4199f32d-01ff-44a1-b1ad-e42fc912dd7c">
<img width="625" alt="요구분석2" src="https://github.com/Vida0822/Airbnb_Oracle-PLSQL-Project/assets/132312673/fb136df1-4c2b-46fd-8b7f-10a32eec5f8f">
<img width="625" alt="요구분석3" src="https://github.com/Vida0822/Airbnb_Oracle-PLSQL-Project/assets/132312673/e648d9eb-82b4-4262-b770-5d712d7458b8">
<img width="625" alt="요구분석4" src="https://github.com/Vida0822/Airbnb_Oracle-PLSQL-Project/assets/132312673/4e2428f0-a9c5-4773-814a-6e581b142df5">
<img width="625" alt="요구분석5" src="https://github.com/Vida0822/Airbnb_Oracle-PLSQL-Project/assets/132312673/306c2004-5c89-470d-a111-c6cc6ae933a9">
<img width="625" alt="요구분석6" src="https://github.com/Vida0822/Airbnb_Oracle-PLSQL-Project/assets/132312673/91c88ad9-2c0b-496e-8fa8-c82758836624">
<img width="625" alt="요구분석7" src="https://github.com/Vida0822/Airbnb_Oracle-PLSQL-Project/assets/132312673/5922653f-048c-4ea8-aa10-01e57dab9626">
<img width="625" alt="요구분석8" src="https://github.com/Vida0822/Airbnb_Oracle-PLSQL-Project/assets/132312673/863153b3-aba8-451d-9f9c-9ace24e17289">
<img width="625" alt="요구분석9" src="https://github.com/Vida0822/Airbnb_Oracle-PLSQL-Project/assets/132312673/4cb59dba-659b-4d31-81ee-6951e13001bb">
<img width="625" alt="요구분석10" src="https://github.com/Vida0822/Airbnb_Oracle-PLSQL-Project/assets/132312673/8bc11931-e3ee-4ac9-8428-954b2d38046a">
<img width="625" alt="요구분석11" src="https://github.com/Vida0822/Airbnb_Oracle-PLSQL-Project/assets/132312673/6ad4876a-769c-4a45-bb83-3792ea2d2f40">
<img width="625" alt="요구분석12" src="https://github.com/Vida0822/Airbnb_Oracle-PLSQL-Project/assets/132312673/bc013c4b-782e-4dca-8ca2-e7765d019a4b">
<img width="625" alt="요구분석13" src="https://github.com/Vida0822/Airbnb_Oracle-PLSQL-Project/assets/132312673/53183c9c-47b8-41ae-860d-9305a2c6f094">

</div>
</details>

</br>

1. 유스케이스 다이어그램이란? 



시스템과 사용자의 상호작용을 다이어그램으로 표현한 것으로 사용자의 관점에서 시스템의 서비스 혹은 기능 및 그와 관련한 외부 요소를 보여주는 것이다.

사용자(Actor)의 관점에서 시스템의 기능, 상호작용과 그들 간의 관계를 표현합니다.

 

유스케이스 다이어그램을 사용하는 이유는 다음과 같습니다.

- 제품과 상호작용하여 얻을 수 있는 목표를 자세히 설명할 수 있습니다.
- 시스템의 요구사항을 요약하고 정의할 수 있습니다.

유스케이스 다이어그램의 구성요소는 시스템(System), 액터(Actor), 유스케이스(Usecase), 관계(Relation)로 구성되어 있다

1. 시스템 (System)
2. 액터 (Actor)
3. 유스케이스 (Usecase)
4. 관계 (Relation)

~ 이젠 여긴 구현한 기능 쿼리 보면서 채워나가기 ~



<details>
<summary><b> 요구분석 펼치기</b></summary>
<div markdown="1">


</div>
</details>

</br>


## 6. DB 모델링 : ERD / EXERD 설계

<details>
<summary><b> 모델링 펼치기 </b></summary>
<div markdown="1">

### 5.1. 개체 및 속성 정리 


<img width="625" alt="개체정리1" src="https://github.com/Vida0822/Airbnb_Oracle-PLSQL-Project/assets/132312673/3b487bb8-6578-4893-a69e-6dd0eb424b88">
<img width="625" alt="개체정리2" src="https://github.com/Vida0822/Airbnb_Oracle-PLSQL-Project/assets/132312673/55ba9768-a04f-4f93-b270-05be7164b6eb">
<img width="625" alt="개체정리3" src="https://github.com/Vida0822/Airbnb_Oracle-PLSQL-Project/assets/132312673/90a26990-7e10-42d8-ad5f-1dcdb2a1db9e">

</br>



### 5.2. 개념적 모델링 : ERD 설계  

​	위와 같은 요구분석을 바탕으로, 우리는 개체 및 속성을 추출한후 개체간의 관계를 정의하는 개념적 모델링을 통해 erd를 설계했다. 개체와 속성을 필기?로 정리할 땐 테이블간 관계를 명확히 파악하기 위해 편의상 기본키 및 외래키를 PK,FK로 표시하며 모두 작성해주었고 erd는 설계 규칙에 따라 외래키를 생략하고 PK대신 밑줄로 기본키임을 나타냈다. 

![에어비앤비_DB모델링_개념적모델링(erd)](https://github.com/Vida0822/Airbnb_Oracle-PLSQL-Project/assets/132312673/98d5d17e-12c1-4607-b9c4-d28d2783b4a2)








### 5.3. 물리적, 논리적 모델링 : eXERD 설계  

​	개념적 모델링을 마친 후 설계한 ERD를 1:1로 매칭시키는 매핑규칙(mapping rule)에 따라 DBMS가 지원하는 스키마로 설계하는 정규화 과정(논리적 모델링)과 세부적인 칼럼의 종류 및 자료형과 크기를 확정하고 효율적인 데이터베이스가 되도록 역정규화하는 물리적 모델링을 진행했다. <br>

​	

- **사용 툴: eXERD**

![eXERD](https://github.com/Vida0822/Airbnb_Oracle-PLSQL-Project/assets/132312673/78875f7e-b042-4304-8b68-0eafcc9b614b)

​	






### 5.4. DB 구축 : 테이블 생성 , 데이터 임포트 

1. 테이블 생성

   exerd의 '포워드 엔지니어링' 기능을 활용해 바로 sql developer상의 계정 어쩌구에 쉽게 db를 설계해주었다

2. 데이터 임포트  

​	설계한 eXERD에 따라 실제 사이트를 바탕으로 테이블에 넣어줄 데이터들을 엑셀에 정리한 후 , sql developer의 '데이터 임포트' 기능을 활용해 정리한 데이터를 각 테이블에 맞춰 넣어주었다. 

-> 링크 : 구글 스프레드 시트 

</div>
</details>

</br>



## 7. 핵심 기능




![핵심기능](https://github.com/Vida0822/TennisCounter_Java-Interface-Project/assets/132312673/76f2e20b-0c59-4eeb-914e-828974d0aaac)

* **고객**(Actor) : 사이트 처음 방문한 사람이 숙소를 조회하고 회원가입/ 로그인하기까지의 프로세스 <br>

* **회원**(Actor): 회원으로서 가능한  회원정보관리, 탈퇴하기까지의 프로세스   <br>

* **호스트**(Actor) : 호스트 계정 등록 -> 숙소를 등록하고 손님을 받을때까지 프로세스<br>

* **게스트**(Actor) : 숙소를 예약하고 여행을 다녀온 후 후기까지 남기는 프로세스 <br>



<details>
<summary><b>핵심 기능 설명 펼치기</b></summary>
<div markdown="1">


### 7.1. 액터 : 사용자

![핵심기능](https://github.com/Vida0822/TennisCounter_Java-Interface-Project/assets/132312673/76f2e20b-0c59-4eeb-914e-828974d0aaac)

* **숙소 목록조회** :pushpin: [코드 확인](https://github.com/Vida0822/TennisCounter_Java-Interface-Project/blob/08c639b660efbea0407afeea07b35e378ce73ed1/tennis/src/tennis/TennisMain.java#L66-L75)

  - 익명 프로시저 'up_roomMainPage'의 매개변수로 '숙소 유형(rm_type)'을 전달받아 해당 숙소 유형으로 숙소사진, 숙소 이름, 숙소 위치, 1박당 요금을 조회(select)하는 cursor을 선언한다.
  - 해당 커서에서 한 레코드씩 읽어와 해당 숙소 유형에 해당하는 숙소들을 형식에 맞춰 LOOP 반복문으로 출력하며 더 이상 조회된 레코드가 없을 때 종료한다. 
  - 숙소 유형이 입력되지 않으면 예외를 발생시킨다. 

* **숙소 상세조회** :pushpin: [코드 확인](https://github.com/Vida0822/TennisCounter_Java-Interface-Project/blob/08c639b660efbea0407afeea07b35e378ce73ed1/tennis/src/tennis/TennisMain.java#L66-L75)

  - 매개변수로 전달받은 '숙소 코드(rm_code,PK)'로 해당 숙소의 편의시설목록을 조회하는 up_facility를 선언해, 해당 숙소의 편의시설 카테고리, 편의시설 이름을 cursor를 사용해 반복문으로 출력한다. 
  - 매개변수로 전달받은 '숙소 코드(rm_code,PK)'로해당 숙소의 이용규칙목록을 조회하는 up_ruleset를 선언해 게스트정원, 반려동물 동반여부, 체크인&체크아웃 시간을 cursor를 사용해 반복문으로 출력한다. 
  - 매개변수로 전달받은 '숙소 코드(rm_code,PK)'로해당 숙소의 후기 목록을 조회하는 up_review를 선언하며 선언한 총 평점, 후기개수를 구하는 함수uf_reviewavg, uf_reviewcount를 호출하여 총평점, 후기개수를 출력한 후 후기 테이블의 칼럼인 청결도, 정확성, 의사소통, 위치, 체크인, 가격대비 만족도를 cursor를 사용해 반복문으로 출력한다. 
  - 숙소 코드가 입력되지 않으면 예외를 발생시킨다. 

* **회원가입** :pushpin: [코드 확인](https://github.com/Vida0822/TennisCounter_Java-Interface-Project/blob/18b9b1124a69f585853726515a4a88d02aeb7b3b/tennis/src/tennis/TennisMain.java#L30-L64)

  - 사용자 이름, 생년월일, 이메일, 전화번호, 지역을 매개변수로 입력받아 Member 테이블에 insert한다.   
  - 전화번호를 길게 입력했을 경우 VALUE_ERROR  예외를 발생시킨다. 

* **로그인** :pushpin: [코드 확인](https://github.com/Vida0822/TennisCounter_Java-Interface-Project/blob/08c639b660efbea0407afeea07b35e378ce73ed1/tennis/src/tennis/TennisMain.java#L66-L75)

  - 사용자는 전화번호 또는 이메일로 로그인 할 수 있다. 
  - 매개변수로 전달받은 전화번호 또는 이메일로 Member 테이블에서 조회되는 레코드개수가 1이면 로그인 성공 
  - 로그인 실패시 회원가입 안내 메세지를 출력한다.  
  
  

</br>

### 7.2. 액터 : 회원

![TennisMain](https://github.com/Vida0822/TennisCounter_Java-Interface-Project/assets/132312673/c1eac4bc-5e04-463a-b47c-f44d5680cfed)



- **회원정보 수정** :pushpin: [코드 확인](https://github.com/Vida0822/TennisCounter_Java-Interface-Project/blob/18b9b1124a69f585853726515a4a88d02aeb7b3b/tennis/src/tennis/TennisMain.java#L30-L64)
  
  - 회원 기본정보인 멤버코드, 이름, 이메일, 전화번호, 주소, 계좌등을 매개변수(p-)로 전달받으며 자동으로 멤버코드를 제외한 다른 매개변수는 null을 허용한다.  
  
  - Member테이블의 칼럼들 각각을 v-형 변수로 선언하여 해당 멤버코드로 조회한 레코드의 칼럼값들을 각각의 변수들에 대입한다. 
  
  - NVL 함수를 사용해 수정 요청한 값은 입력한 값(p-)로, 요청하지 않은 값은 미리 조회한 기존의 데이터(v-)로 수정(update)한다 
  
    
  
- **회원 탈퇴** :pushpin: [코드 확인](https://github.com/Vida0822/TennisCounter_Java-Interface-Project/blob/08c639b660efbea0407afeea07b35e378ce73ed1/tennis/src/tennis/TennisMain.java#L66-L75)

  - 회원의 전화번호를 매개변수로 전달받아 해당 전화번호를 전화번호로 갖는 회원의 레코드를 삭제(delete)한다.
  
  

</br>  

### 7.3. 액터 : 호스트

![scoreBoard](https://github.com/Vida0822/TennisCounter_Java-Interface-Project/assets/132312673/7410cb17-8dad-4a06-8fbb-d95e875b0611)

- **숙소 등록** :pushpin: [코드 확인](https://github.com/Vida0822/TennisCounter_Java-Interface-Project/blob/2fb77b76e96d4afbde8e7204d4b52e4e98ddcbdb/tennis/src/tennis/ScoreCounter.java#L57-L82)

  - 기본정보인 지역, 정책, 숙소유형, 공간특징, 숙소이름, 숙소설명, 최대인원수, 1박당 가격, 위치, 침실&침대&욕실개수를 매개변수로 전달받아 숙소 테이블(Room)에 삽입(insert)한다.

  - 5장의 사진 경로를 매개변수로 전달받아 현재 가입하고 있는 숙소를 코드의 Max 값으로 조회해 해당 숙소코드(외래키)와 함께 각각의 사진 주소를 사진 테이블(photo)에 삽입(insert)한다.

  - 사진을 등록해 숙소가 등록되면 숙소 상태는 '운영정지'가 기본값으로 설정된다. 

    

- **숙소 기본정보 관리** :pushpin: [코드 확인](https://github.com/Vida0822/TennisCounter_Java-Interface-Project/blob/2fb77b76e96d4afbde8e7204d4b52e4e98ddcbdb/tennis/src/tennis/ScoreCounter.java#L85-L136)

  - 숙소명을 수정(update)할 수 있으며 입력된 숙소이름이 50자를 넘으면 VALUE_ERROR를 발생시킨다. 
  - 숙소설명을 수정(update)할 수 있으며 입력된 숙소설명이 200자를 넘으면 VALUE_ERROR를 발생시킨다. 
  - 매개변수 pupdown 로 '+'또는 '-'를 입력받아 + 또는 - 버튼을 누를때마다 즉각적으로 기존 게스트 수를 1명씩 증가/감소(update) 최대 게스트 수를 수정(update)할 수 있다.
  - 숙소주소를 입력받아 수정(update)할 수 있다.
  - 숙소유형 & 예약가능공간은 동시에 수정한 후 저장버튼을 누르면 db에 반영되는 형태이기 때문에 두개를 다 매개변수로 받아 NVL 함수를 사용해 변경 요청한 값맘ㄴ update하고 그렇지 않은 값은 기존의 데이터를 넣는다. 
  -  침실&침대&욕실 각각 +,- 버튼으로 수를 조절한 후 저장버튼을 누르는 형식이기 때문에 각각 +,-값을 누른 횟수로 매개변수 pupdown를 선언하여 기존 침실&침대&욕실 개수에 더해준다. 
  -  1박당 요금 수정: 수정하고자하는 1박당 요금을 입력받아 수정(update)을 한후, 전체 숙소의 평균가격과 비교해 입력값이 높으면 낮추라는 메세지를, 낮으면 높이라는 권고 메세지를 출력한다. 
  -  환불정책 수정 : 환불정책을 엄격, 
  - 사업자 등록번호 수정 : 사업자 등록번호를 입력받아 수정(update)할 수 있다.
  - 체크인, 체크아웃 시간 수정 : 체크인, 체크아웃 시간를 입력받아 수정(update)할 수 있다. 그러나 입력된 체크아웃 시간이 1시~7시라면 v_cannot_reserve_exception 예외를 발생시킨다. 

  

- **숙소 세부정보 관리** :pushpin: [코드 확인](https://github.com/Vida0822/TennisCounter_Java-Interface-Project/blob/2fb77b76e96d4afbde8e7204d4b52e4e98ddcbdb/tennis/src/tennis/ScoreCounter.java#L85-L136)

  - 편의시설 관리 : 편의시설 종류와 숙소코드를 매개변수로 받아 해당 편의시설 코드와  숙소 코드(외래키)로 편의시설 설정 테이블에 등록/ 삭제한다.
  - 이용규칙 관리: 이용규칙 종류와 숙소코드를 매개변수로 받아 해당 이용규칙 코드와  숙소 코드(외래키)로 편의시설 설정 테이블에 등록/ 삭제한다.
    * 이때 규칙코드(RU2)인 '반려동물 허용' 선택시 함께 입력받은 최대 허용 반려동물 수를 숙소 테이블에 update 한다.  
    * 허용안하면 최대 허용 반려동물 수를 0으로 초기화하고 추가요금 테이블에서 동물 추가해서 받던 추가요금 규칙 레코드를 삭제한다. 
  - 할인제도 관리 : 할인제도 종류와 그에 따른 할인율, 할인 적용 기준 (날짜), 그리고 숙소코드를 매개변수로 받아 해당 이용규칙 코드와  숙소 코드(외래키)로 편의시설 설정 테이블에 등록/ 수정/ 삭제한다.
    * 설정한 할인 제도가 'DC1' 인경우 해당 날짜 기준을 7일로,  'DC2' 해당 날짜 기준을 30일로 자동 설정하며, 할인제도가  DC3 또는 DC4인데 dc_basis 값이 전달되지 않은경우 v_notnull 예외를 발생시킨다. 
    * 만약 할인율을 0으로 설정하면 해당 할인제도는 할인 테이블에서 삭제한다. 
  - 추가요금 관리  : 추가요금 종류와 그에 따른 추가금액, 추가요금 적용 기준 (며칠), 그리고 숙소코드를 매개변수로 받아 해당 이용규칙 코드와  숙소 코드(외래키)로 편의시설 설정 테이블에 등록/ 수정/ 삭제한다.
    * 이용규칙 테이블에서 'RU2' 즉 반려동물 허용 규칙이 있는지 확인한 후 만약 반려동물에 대한 추가요금을 설정했는데 반려동물 허용 규칙이 없다면 해당 이용규칙을 이용규칙 테이블에 삽입(insert)한다. 
    * 추가금액을 0으로 수정하면 자동으로 해당 추가요금제도는 삭제시킨다. 
  
  
  
- **숙소 상태 수정 ** :pushpin: [코드 확인](https://github.com/Vida0822/TennisCounter_Java-Interface-Project/blob/2fb77b76e96d4afbde8e7204d4b52e4e98ddcbdb/tennis/src/tennis/ScoreCounter.java#L85-L136)

  - 호스트는 숙소상태를 운영정지, 비활성화...등으로 수정할 수 있다. 
  - 만약 숙소 상태가 이미 '비활성화' 라면 해당 숙소는 이미 조회할 수 없으므로 v_no_more_visible 예외를 발생시킨다.
  - 숙소 상태를 비활성화하면 위시리스트, 예약, 이용규칙설정, 추요금 설정 테이블 등에서 해당 숙소 코드를 갖는 레코드를 삭제한 후, 예약 테이블에선 '예약 거절'로 예약 상태를 바꾼다. 

 

</br>   


### 7.4. 액터 : 게스트

![dispScoreBoard](https://github.com/Vida0822/TennisCounter_Java-Interface-Project/assets/132312673/5f83dcb4-2c7b-4d38-894b-7446e2d8dae0)

- **위시리스트 관리** :pushpin: [코드 확인](https://github.com/Vida0822/TennisCounter_Java-Interface-Project/blob/2fb77b76e96d4afbde8e7204d4b52e4e98ddcbdb/tennis/src/tennis/ScoreCounter.java#L57-L82)
  - 위시리스트 조회 : 회원코드로 해당 회원이 등록한 위시리스트 목록을 cursor를 활용해 조회한다. 숙소 사진, 위치, 타입, 숙소 이름 , 침대 개수를 

  - 위시리스트 추가: 멤버코드와 숙소코드를 활용해 위시리스트 테이블에 삽입하며(insert), 이때 하나의 회원은 같은 숙소를 등록할 수 없게 하도록 트리거를 설정해준다. 

  - 위시리스트 삭제: 멤버코드와 숙소코드를 활용해 위시리스트 테이블에서 삭제한다(delete)


- **예약 관리** :pushpin: [코드 확인](https://github.com/Vida0822/TennisCounter_Java-Interface-Project/blob/2fb77b76e96d4afbde8e7204d4b52e4e98ddcbdb/tennis/src/tennis/ScoreCounter.java#L85-L136)
  
  - 예약 목록 조회 : 예약이 완료된 숙소의 목록을 체크인 체크아웃 시간 , 주소, 예약일, 호스트 정보와 함께 출력한다.
  - 예약 상세 조회: 상세보기를 요청한 숙소의 기본정보와 게스트 수 , 예약 번호, 환불 정책 등 추가 세부적인 정보와 함께 출력한다. 
  - 예약하기 
    * 요금산정: 기본요금에거기에 박수를 곱해 할인율 계산 함수를 활용해 도출한 할인율을 적용해 거기에 추가금액 계산함수로 도출한 추가요금을 더해 최종 가격을 도출한다.
    * 요금 및 기타 예약 정보를 예약 테이블에 삽입한 후 성공적으로 처리되면 예약 정보를 출력한다. 
    * 예약은 예약이 없는 날에만 예약이 가능하며 총인원은 최대인원을 넘을수 없고 반려동물은 최대반려동물을 넘을 수 없도록 트리거를 설정해준다. 
  - 예약 수정 :  예약 수정시 가장 최근에 update 된 할인율, 추가요금 제도 등을 반영해 다시 요금을 계산한다. 
  - 예약 삭제 : 전달받은 예약코드로 예약 테이블에서 해당 레코드를 삭제하는데 만약 이미 결제가 되어 결제 테이블에 등록되어있따면 먼저 환불을 하라는 v_no_res_cancel 예외를 발생시킨다. 
  
- **결제 관리** :pushpin: [코드 확인](https://github.com/Vida0822/TennisCounter_Java-Interface-Project/blob/2fb77b76e96d4afbde8e7204d4b52e4e98ddcbdb/tennis/src/tennis/ScoreCounter.java#L85-L136)

  - 결제 목록 조회: 해당 결제수단으로 결제한 결제 목록을 cursor를 활용해 예약코드, 숙소 이름, 결제자 이름, 결제 날짜, 카드번호, 만료 날짜, 우편번호, 결제 금액의 정보를 반복문으로 출력한다. 

  - 결제하기: 결제 지역, 카드번호 , 만료 기한 등의 결제 수단 정보를 입력받아 결제 테이블에 insert한다. 이때 예약상태가 '예정된 여행'이 아니면 결제를 할 수 없도록 트리거를 설정해준다. 

  - 결제 후에는 환불절차를 거쳐야 결제 및 예약 취소를 할 수 있기 때문에 결제 테이블에서 직접적으로 레코드를 삭제할 수 없도록 트리거를 설정해준다. 

    

- **환불 관리** :pushpin: [코드 확인](https://github.com/Vida0822/TennisCounter_Java-Interface-Project/blob/2fb77b76e96d4afbde8e7204d4b52e4e98ddcbdb/tennis/src/tennis/ScoreCounter.java#L85-L136)

  - 한 플레이어가 포인트 4점 획득했는데 1점차면 포인트 듀스가, 6게임 획득했는데 1 게임차면 게임 듀스가 발생한다.
  - 그 즉시 별개의 듀스 포인트 필드와 while문을 사용해 듀스게임을 실행한다. 

- **후기 관리** :pushpin: [코드 확인](https://github.com/Vida0822/TennisCounter_Java-Interface-Project/blob/2fb77b76e96d4afbde8e7204d4b52e4e98ddcbdb/tennis/src/tennis/ScoreCounter.java#L85-L136)

  - 한 플레이어가 포인트 4점 획득했는데 1점차면 포인트 듀스가, 6게임 획득했는데 1 게임차면 게임 듀스가 발생한다.
  - 그 즉시 별개의 듀스 포인트 필드와 while문을 사용해 듀스게임을 실행한다. 

  

</br>  



</div>
</details>

</br>

## 7. 핵심 트러블 슈팅

<details>
<summary><b>트러블 슈팅 설명 펼치기</b></summary>
<div markdown="1">


<details>
<summary><b>erd 트러블 슈팅 </b></summary>
<div markdown="1">


### 5.1. 숙소 세부정보 설정부분 erd 설계  -> 여기 또는 트러블 슈팅 

​	&nbsp;&nbsp;&nbsp;&nbsp;**인터페이스(interface)** 는 추상 클래스(미완성 설계도)와 유사하지만 일반 메서드도 포함할 수 있는 다른 일반 추상 클래스와 달리 **오로지 추상 메서드와 상수**로만 이루어진다 (※ jdk 1.8 버전부턴 'default method' 형태로 포함 가능). 즉 해당 interface 안에는 오로지 **메서드의 선언부만** 작성된다.

​	&nbsp;&nbsp;&nbsp;&nbsp;이러한 인터페이스의 특징은 다음과 같다.

1. **다형성** : 조상 타입, 즉 인터페이스 타입 참조변수로 구현된 **자손 인스턴스를 대입**하여 사용할 수 있다. 

2. **강제성**: 자손 클래스은 해당 기능에 필수적인 메서드를 **강제로 오버라이딩** 하게한다. 

3. **has-a**: 다중 상속, 즉 하나의 조상클래스만 가질 수 있는 것과 달리 **여러개의 interface를 implement** 할 수 있다.

   

​	&nbsp;&nbsp;&nbsp;&nbsp;interface의 특징을 고려해, 우리의 **인터페이스의 활용방안**은 다음 두가지였다.

1. **기본 설계도**로서의 interface 
2. **협업(분담)을 용이**하게 하는 interface 

</br>

### 5.2. 예약부분 erd 설계 

##### 2023-03

![클래스 다이어그램(팀)](https://github.com/Vida0822/TennisCounter_Java-Interface-Project/assets/132312673/a577be0c-b065-45c3-9f97-6867740cc92e)



​	&nbsp;&nbsp;&nbsp;&nbsp;*"인터페이스는 **기본 설계도**이다."*

​	&nbsp;&nbsp;&nbsp;&nbsp;세상엔 **수많은 경기 종목**이 있고 각 규칙을 하나의 클래스에서 다 고려할 순 없다. 따라서 계수기라면 포함해야할 기본적인 기능인 **득점 처리** 기능과 **점수 출력**기능을 반드시 구현하도록, 즉 **최소한의 메서드**를 Interface에 선언하고 이를 자손 클래스에서 상속받아 **각 경기 종목에 맞춰 알아서 구현**하게끔 하는 **기본 설계도**로서 기능하게 한다. 

​	&nbsp;&nbsp;&nbsp;&nbsp;따라서 우린 '계수기' 기본 설계도로 **인터페이스 I**를 선언하고 이를 상속받은 테니스 계수기인 클래스 **ScoreCounter**는 해당 두 메서드를 **테니스 규칙을 반영하여 오버라이딩**한다. 이렇게 구현한 ScoreCounter를 실제 경기(main함수)가 실행되는 **TennisMain**에서 객체로 생성해 사용하게끔 구조를 설정했다.      



</div>
</details>

</br>

### 7.1. 인터페이스 참조변수 활용

![인터페이스 손필기](https://github.com/Vida0822/TennisCounter_Java-Interface-Project/assets/132312673/961a7dc0-7ab6-48f7-87ad-3e47dbc6e300)

​	

​	&nbsp;&nbsp;&nbsp;&nbsp;메서드 선언부(*Interface I*) 구현부(*Class B*)  사용부(*Class A*) 실행부(*Main*)로 클래스를 나누었다. 이 구조의 목적은 객체지향언어의 **다형성**을 활용해 부모 클래스가 완성되어야 자손 클래스가 구현가능한 상속구조의 단점을 해결해 분업의 효율성을 높이고자 함에있다.  

​	&nbsp;&nbsp;&nbsp;&nbsp;Class A에 interface 참조변수를 통해 **빈 껍데기 뿐인 메서드**를 만들어 로직을 구현하고, 다른 팀원들은 해당 interface를 상속받은 클래스B에서 **메서드의 몸체**를 구현한다. 각자 개발을 마친 후 프로그램 실행시 Class A를 객체로 생성하고 Class A 메서드의 매개변수인 interface의 참조변수, 즉 조상 참조변수에 인터페이스를 상속받은 Class B를 객체로 생성해 자손 인스턴스를 **동적으로 주입**한다. 

​	&nbsp;&nbsp;&nbsp;&nbsp;위 구조를 우리 프로젝트에 반영하면 아래와 같다. 
</br>


![초기 클래스다이어그램](https://github.com/Vida0822/TennisCounter_Java-Interface-Project/assets/132312673/1b6384a0-cc8b-4a7b-a697-1b18fb68b6bc)



​	&nbsp;&nbsp;&nbsp;&nbsp;득점시 포인트를 올리는 pointWinner(int p)와 게임현황을 출력하는 dispScoreBoard() 두 메서드를 인터페이스 I에 선언한다. 메서드를 **구현하는 ScoreCount** 클래스와, 테니스 규칙을 반영해 **득점처리**하는 계수기, **ScoreBoard** 클래스를 작성한다. **게임이 실행**되는 TennisMain에선 경기정보를 입력받아 계수기, **ScoreBoard를 객체로 생성**하면서 게임을 세팅한다. 이후 득점자를 랜덤으로 도출하고 **인터페이스 I를 매개변수**로 갖는 pointWinner(I i), dispScoreBoard(I i) 매개변수에 **ScoreCount를 넣어 호출**하며 득점처리 및 점수출력을 실행한다. 이 과정을 게임이 끝날때까지 while문으로 반복한다. 

​	&nbsp;&nbsp;&nbsp;&nbsp;게임을 세팅, 진행하는 TennisMain에 2명, 메서드 구현부에 2명, 계수기 로직 구현에 3명으로 개발 파트를 나누었다. 인터페이스에 **메서드의 기능과 리턴타입을 명확히 선언**해 놓으니 실제로 구현이 안되었더라도 **계수기 로직 개발을 동시에 진행**할 수 있었다.

<br>

*Problem*

​	 &nbsp;&nbsp;&nbsp;&nbsp;문제는 메서드의 리턴값만으로 테니스 득점로직을 계수기 클래스(ScoreBoard)에 구현해야하는데, 포인트 점수를 다루는 메서드 구현부(ScoreCounter)와 포인트 점수, 게임, 세트 모두를 처리하는 계수기(ScoreBoard)간 **멤버변수가 중복선언** 되는 등 **기능 구분이 명확하지 않았다**. 

​	&nbsp;&nbsp;&nbsp;&nbsp;또한 **객체의 주입(DI)** 에 대한 이해부족으로 **인터페이스 참조변수**를 잘 활용하지 못해, 실행부(ScoreBoard)에서 인터페이스 참조변수로 메서드를 새롭게 선언하거나 메인 함수의 게임세팅과 연결지어 줄 때 어려움이 있었다. 즉 코딩경험 부족에 의한 기술적 한계로 **클래스간의 기능 연계**가 원활이 이루어지지 못했다. 

</br>

*Solution*

​	&nbsp;&nbsp;&nbsp;&nbsp;개발 시간이 촉박했던 시점이라 **메서드 사용클래스(ScoreBoard)를 없애고**  ScoreCounter 클래스에서 테니스 규칙을 반영하며 메서드를 구현하는 방향으로 설계를 수정했다. 실제 main함수에선 구현부인 **ScoreCounter에서 직접 메서드를 호출**하도록 했다.

​	&nbsp;&nbsp;&nbsp;&nbsp;이렇게 하니 구현자체는 편해졌지만 ScoreCounter에 계수기 로직(테니스 규칙)과 득점 처리, 출력 등 여러 기능이 섞여 객체 지향의 장점인 **모듈화**가 잘 이루어지지 않고 **코드의 가독성**이 떨어졌다. 시간적 여유가 있었다면  클래스간 기능 구분을 더 명확히 하고 그 주입, 연계관계를 통해 객체지향의 장점을 최대한 살린 체계적인 프로그램을 만들 수 있었을 것 같아 팀원들과 나도 많이 아쉬웠다. 

</br>

### 7.2. 테니스 규칙에 맞는 포인트 출력

- 계수기 메서드, 즉 scoreBoard() 함수를 구현할 때 계산의 편의 및 게임, 세트수 계산과의 로직 일치를 위해 포인트 점수를 0,1,2,3 점으로 두어 득점처리 했다. 

<details>
<summary><b>기존 코드</b></summary>
<div markdown="1">

```java
	public void pointWinner(int p) { // pointWinner 오버라이딩
		if (p == 1) {
			player1Point++;
		} else
			player2Point++;
	}

	public void scoreBoard() { // 계수기 메서드
	
		if (player1Point == 4) { //player1이 4포인트를 이겼을때
			player1Game++;
			pointReset();
		}
		if (player2Point == 4) { //player2이 4포인트를 이겼을때
			player2Game++;
			pointReset();
		}
        /* 코딩 생략 */ 
    }
```

</div>
</details>

</br>



*Problem*

- 하지만 점수판 메서드, dispScoreBoard()를 구현할 때 포인트 점수를 출력할땐 테니스 경기 규칙에 따라 0,15,30,40 점으로 출력을 해야했는데, 이 점수들은 서로 불규칙하여 득점시 고정값으로 올리는 것이 불가능했다.  
</br>

*Solution*

- 1점씩 올리는 포인트 득점처리 방식은 그대로 두되,  0,1,2,3 점으로 두었던 포인트 점수를 출력할때 테니스 경기 규칙에 맞춰 변환시킨다. 
- 점수판 메서드에서 0,15, 30, 45를 포인트 점수 배열 playerPoints로 만들고, 0,1,2,3을 배열의 index로 매칭 시켜 출력형식을 바꾸어준다.
- 이 때 듀스게임까지 가게될 경우 포인트가 4를 넘을 수 있기 때문에 ( 5점,6점 => 15점. 30점 ), 단순히 값이 0,1,2,3인 것이 아닌 아닌 값의 4로 나눈 나머지를 index로 활용했다.
- 이렇게 하니 득점처리는 그대로 로직을 유지해 계산을 편하게 할 수 있고 출력하기 전에만 형식을 일치시켜 바꿔주면되어 편리했다

<details>
<summary><b>개선된 코드</b></summary>
<div markdown="1">

```java
int[] player1Points = { 0, 15, 30, 40 }; //포인트 점수
int[] player2Points = { 0, 15, 30, 40 };
int printplayer1Point 
		= player1Points[player1Point % 4];
int printplayer2Point 
		= player2Points[player2Point % 4];
```

</div>
</details>

</br>

</div>
</details>

</br>

## 8. 회고 / 느낀점

> '좋은 팀'에 대한 고민 : https://vida0822.github.io/memory/MR_TennisMemory/		</br> 

> 그래서, 그거 코딩할 수 있어? : https://vida0822.github.io/memory/MR_TennisMemory(2)/
