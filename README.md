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

<details>
<summary>핵심 기능 설명 펼치기</summary>
<div markdown="1">

### 3-1. 전체 흐름


<img width="634" alt="화면 캡처 2023-03-04 225718" src="https://user-images.githubusercontent.com/95980754/222906620-169da318-f300-4610-89df-366a2a1e6138.png">

<img width="632" alt="화면 캡처 2023-03-04 205645" src="https://user-images.githubusercontent.com/95980754/222906550-7fba8268-ef7e-4e90-890f-73c68e37d1f1.png">

<img width="634" alt="화면 캡처 2023-03-04 205701" src="https://user-images.githubusercontent.com/95980754/222906551-cb43b4f9-f048-4f06-adb3-15b218462334.png">

### 3-2. 게시글 등록
 
<img width="734" alt="register" src="https://user-images.githubusercontent.com/95980754/222907874-3d775e74-983b-4813-bf26-7f6ec2e800e4.png">
  
* 사용자가 /register 페이지에서 게시글을 포스팅하면 BoardDTO의 형태로 BoardController에 전달됩니다. 📌[코드 확인](src/main/java/org/zerock/b01/controller/BoardController.java)
* @Vaild를 통해 서버쪽에서도 데이터의 유효성을 확인할 수 있습니다. 

<img width="367" alt="화면 캡처 2023-03-04 233500" src="https://user-images.githubusercontent.com/95980754/222908453-e5c7e0d6-ace2-43e3-a7ee-190080ed6c40.png"> 
  
* BoardService register에서 서비스 로직을 처리합니다. 📌[코드 확인](src/main/java/org/zerock/b01/service/BoardServiceImpl.java)
* 직접 SQL을 다루는 대신 JPA의 사용으로 Entity 객체인 Board 클래스를 통해 객체지향적으로 데이터를 다룰 수 있게 됩니다. 📌[코드 확인1](src/main/java/org/zerock/b01/repository/BoardRepository.java) 📌[코드 확인2](src/main/java/org/zerock/b01/domain/Board.java)
* 게시글 등록 후 /list로 redirect 됩니다.

### 3-3. 게시글 수정
  
<img width="595" alt="화면 캡처 2023-03-05 001559" src="https://user-images.githubusercontent.com/95980754/222914103-2b31b892-fbfd-411b-b290-4aca48a9a3b5.png">
  
* 사용자가 게시글을 수정하면 PageRequestDTO 형태로 BoardController에 전달됩니다. 📌[코드 확인](src/main/java/org/zerock/b01/controller/BoardController.java)
  
<img width="458" alt="image" src="https://user-images.githubusercontent.com/95980754/222914499-43e9e4cd-1d6e-4bef-9e2a-82ff4e695589.png">
  
* BoardService modify에서 서비스 로직을 처리합니다. 📌[코드 확인](src/main/java/org/zerock/b01/service/BoardServiceImpl.java)
* 직접 SQL로 데이터를 수정하는 대신 JPA의 사용으로 change 메서드를 통해 데이터를 수정하고 save 메서드로 저장 할 수 있습니다. 📌[코드 확인](src/main/java/org/zerock/b01/domain/Board.java)
  
### 3-4. 게시글 삭제
  
<img width="533" alt="image" src="https://user-images.githubusercontent.com/95980754/222914852-2ae5faa3-6c3f-4c5a-b1ed-06e1ccedf44f.png">

* 사용자가 게시글을 삭제하면 Long bno로 게시글 번호를 통해 BoardController에 전달됩니다. 📌[코드 확인](src/main/java/org/zerock/b01/controller/BoardController.java)
  
<img width="230" alt="화면 캡처 2023-03-05 003543" src="https://user-images.githubusercontent.com/95980754/222915019-3881b1d2-45ae-431a-bb85-e0989521fffe.png">

* 직접 SQL로 데이터를 삭제하는 대신 JPA의 사용으로 deleteById 메서드를 통해 객체지향적으로 데이터를 삭제 할 수 있습니다. 📌[코드 확인](src/main/java/org/zerock/b01/service/BoardServiceImpl.java)

### 3-5. 게시글 조회

<img width="484" alt="화면 캡처 2023-03-05 000934" src="https://user-images.githubusercontent.com/95980754/222913735-275ef613-e3e8-4ca1-a461-59bac8076c41.png">

* 사용자가 /list 페이지에서 게시글을 포스팅하면 PageRequestDTO 형태로 BoardController에 전달됩니다. 📌[코드 확인](src/main/java/org/zerock/b01/controller/BoardController.java)
* attribute 메서드를 통해 model에 데이터를 담아 view로 데이터를 전달합니다.

### 3-6. 게시글 검색  
  
<img width="578" alt="화면 캡처 2023-03-05 005222" src="https://user-images.githubusercontent.com/95980754/222915831-d5e3f19a-6c49-461b-8969-35beb23e8748.png">

  
</div>
</details>
