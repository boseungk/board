## 📌게시판 토이 프로젝트
----------------------------------------------
### 1. 제작 기간 & 참여 인원
* 2022년 12월 28일 ~ 2023년 1월 28일
* 개인 프로젝트


### 2. 사용 기술
----------------------------------------------
`Back-end`
* Java 11
* Spring Boot 2.7.7
* Gradle
* Spring Data JPA
* QueryDSL
* MariaDB

`Front-end`
* HTML
* CSS
* Bootstrap
* Thymeleaf


### 3. 핵심기능
----------------------------------------------
이 서비스의 핵심 기능은 게시글의 CRUD와 검색 기능입니다.

사용자는 게시글을 등록하고, 조회하고, 수정하고, 삭제할 수 있습니다.

그리고 사용자는 자신이 쓴 글을 검색해볼 수 있습니다.


### 3-1. 전체 흐름


<img width="634" alt="화면 캡처 2023-03-04 225718" src="https://user-images.githubusercontent.com/95980754/222906620-169da318-f300-4610-89df-366a2a1e6138.png">

<img width="632" alt="화면 캡처 2023-03-04 205645" src="https://user-images.githubusercontent.com/95980754/222906550-7fba8268-ef7e-4e90-890f-73c68e37d1f1.png">

<img width="634" alt="화면 캡처 2023-03-04 205701" src="https://user-images.githubusercontent.com/95980754/222906551-cb43b4f9-f048-4f06-adb3-15b218462334.png">

### 3-2. 게시판 CRUD 기능
 
<details>
<summary>게시판 CRUD 기능 설명 펼치기</summary>
<div markdown="1">

### 1. 게시글 등록
 
<img width="734" alt="register" src="https://user-images.githubusercontent.com/95980754/222907874-3d775e74-983b-4813-bf26-7f6ec2e800e4.png">
  
* 사용자가 /register 페이지에서 게시글을 포스팅하면 BoardDTO의 형태로 BoardController에 전달됩니다. 📌[BoardController](src/main/java/org/zerock/b01/controller/BoardController.java)
* @Vaild를 통해 서버쪽에서도 데이터의 유효성을 확인할 수 있습니다. 

<img width="367" alt="화면 캡처 2023-03-04 233500" src="https://user-images.githubusercontent.com/95980754/222908453-e5c7e0d6-ace2-43e3-a7ee-190080ed6c40.png"> 
  
* BoardServiceImpl에서 register로 서비스 로직을 처리합니다. 📌[BoardServiceImpl](src/main/java/org/zerock/b01/service/BoardServiceImpl.java)
* 직접 SQL을 다루는 대신 JPA의 사용으로 Entity 객체인 Board 클래스를 통해 객체지향적으로 데이터를 다룰 수 있게 됩니다. 📌[코드 확인1](src/main/java/org/zerock/b01/repository/BoardRepository.java) 📌[Board](src/main/java/org/zerock/b01/domain/Board.java)
* 게시글 등록 후 /list로 redirect 됩니다.

### 2. 게시글 수정
  
<img width="595" alt="화면 캡처 2023-03-05 001559" src="https://user-images.githubusercontent.com/95980754/222914103-2b31b892-fbfd-411b-b290-4aca48a9a3b5.png">
  
* 사용자가 게시글을 수정하면 PageRequestDTO 형태로 BoardController에 전달됩니다. 📌[BoardController](src/main/java/org/zerock/b01/controller/BoardController.java)
  
<img width="458" alt="image" src="https://user-images.githubusercontent.com/95980754/222914499-43e9e4cd-1d6e-4bef-9e2a-82ff4e695589.png">
  
* BoardServiceImpl에 modify로 서비스 로직을 처리합니다. 📌[BoardServiceImpl](src/main/java/org/zerock/b01/service/BoardServiceImpl.java)
* 직접 SQL로 데이터를 수정하는 대신 JPA의 사용으로 change 메서드를 통해 데이터를 수정하고 save 메서드로 저장 할 수 있습니다. 📌[Board](src/main/java/org/zerock/b01/domain/Board.java)
  
### 3. 게시글 삭제
  
<img width="533" alt="image" src="https://user-images.githubusercontent.com/95980754/222914852-2ae5faa3-6c3f-4c5a-b1ed-06e1ccedf44f.png">

* 사용자가 게시글을 삭제하면 Long bno로 게시글 번호를 통해 BoardController에 전달됩니다. 📌[BoardController](src/main/java/org/zerock/b01/controller/BoardController.java)
  
<img width="230" alt="화면 캡처 2023-03-05 003543" src="https://user-images.githubusercontent.com/95980754/222915019-3881b1d2-45ae-431a-bb85-e0989521fffe.png">

* 직접 SQL로 데이터를 삭제하는 대신 JPA의 사용으로 deleteById 메서드를 통해 객체지향적으로 데이터를 삭제 할 수 있습니다. 📌[BoardServiceImpl](src/main/java/org/zerock/b01/service/BoardServiceImpl.java)

### 4. 게시글 조회

<img width="484" alt="화면 캡처 2023-03-05 000934" src="https://user-images.githubusercontent.com/95980754/222913735-275ef613-e3e8-4ca1-a461-59bac8076c41.png">

* 사용자가 /list 페이지에서 PageRequestDTO 형태로 데이터를 BoardController에 전달됩니다. 📌[BoardController](src/main/java/org/zerock/b01/controller/BoardController.java)
* PageReqestDTO에 값이 없다면 @Builder.Default를 통해 초기값을 이용해서 첫 페이지를 보여줍니다. 📌[PageRequestDTO](src/main/java/org/zerock/b01/dto/PageRequestDTO.java)
* addattribute 메서드를 통해 model에 PageResponseDTO를 담아 view로 데이터를 전달합니다.

<img width="577" alt="화면 캡처 2023-03-05 144442" src="https://user-images.githubusercontent.com/95980754/222943776-f3fc5f85-769a-453f-bb6c-8d85d945eab6.png">

* BoardServiceImpl에서 PageRequestDTO를 통해 데이터를 추출해서 searchAll 메서드로 DB에 SELECT요청을 보내서 데이터를 조회합니다. 📌[BoardServiceImpl](src/main/java/org/zerock/b01/service/BoardServiceImpl.java)

</div>
</details>
 
### 3-3. 게시판 검색 기능
 
<details>
<summary>게시판 검색 기능 설명 펼치기</summary>
<div markdown="1">

### 게시글 검색  
  
<img width="650" alt="화면 캡처 2023-03-05 120906" src="https://user-images.githubusercontent.com/95980754/222945125-6646a3d1-bfa5-4466-ac0f-03b9827bf850.png">

* list.html에서 thymeleaf의 selected를 통해 검색 기준에 따라서 PageRequestDTO에 데이터를 담습니다. 📌[list.html](src/main/resources/templates/board/list.html)
 
<img width="527" alt="화면 캡처 2023-03-05 160145" src="https://user-images.githubusercontent.com/95980754/222946585-73cd343c-f5cb-46af-9cfe-3012f061b3b0.png">

* Http의 비연결성(Connectionless)와 무상태성(Stateless)으로 페이지 상태를 유지하기 위해서, PageRequestDTO에서 페이지 정보를 query parameter에 넘겨줍니다. 📌[PageRequestDTO](src/main/java/org/zerock/b01/dto/PageRequestDTO.java)
 
 <img width="577" alt="화면 캡처 2023-03-05 144442" src="https://user-images.githubusercontent.com/95980754/222946058-4f038bdc-3133-449a-9286-30ddb3e1146c.png">

* 검색 타입과 검색어, 페이지 정보를 searchAll 메서드에 넘겨줍니다. 📌[BoardServiceImpl](src/main/java/org/zerock/b01/service/BoardServiceImpl.java)

<img width="508" alt="화면 캡처 2023-03-05 154307" src="https://user-images.githubusercontent.com/95980754/222945921-7ce38084-c9d3-4f35-bdd2-65e7eb7e62bd.png">
 
* Querydsl의 Booleanbuilder를 이용해서 검색 기준에 맞게 Query에 OR 조건을 추가해서 DB에서 검색한 후 결과를 가져옵니다. 📌[BoardSearchImpl](src/main/java/org/zerock/b01/repository/search/BoardSearchImpl.java)

</div>
</details>

### 4. 느낀점
----------------------------------------------
