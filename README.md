## ๐๊ฒ์ํ ํ ์ด ํ๋ก์ ํธ
----------------------------------------------
### 1. ์ ์ ๊ธฐ๊ฐ & ์ฐธ์ฌ ์ธ์
* 2022๋ 12์ 23์ผ ~ 2023๋ 1์ 27์ผ
* ๊ฐ์ธ ํ๋ก์ ํธ


### 2. ์ฌ์ฉ ๊ธฐ์ 
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


### 3. ํต์ฌ๊ธฐ๋ฅ
----------------------------------------------
์ด ์๋น์ค์ ํต์ฌ ๊ธฐ๋ฅ์ ๊ฒ์๊ธ์ CRUD์ ๊ฒ์ ๊ธฐ๋ฅ์๋๋ค.

์ฌ์ฉ์๋ ๊ฒ์๊ธ์ ๋ฑ๋กํ๊ณ , ์กฐํํ๊ณ , ์์ ํ๊ณ , ์ญ์ ํ  ์ ์์ต๋๋ค.

๊ทธ๋ฆฌ๊ณ  ์ฌ์ฉ์๋ ์์ ์ด ์ด ๊ธ์ ๊ฒ์ํด๋ณผ ์ ์์ต๋๋ค.


### 3-1. ์ ์ฒด ํ๋ฆ


<img width="634" alt="ํ๋ฉด ์บก์ฒ 2023-03-05 162245" src="https://user-images.githubusercontent.com/95980754/222947426-7fb73b64-e1d2-44ca-88cb-adfea0aa70c1.png">

<img width="632" alt="ํ๋ฉด ์บก์ฒ 2023-03-04 205645" src="https://user-images.githubusercontent.com/95980754/222906550-7fba8268-ef7e-4e90-890f-73c68e37d1f1.png">

<img width="634" alt="ํ๋ฉด ์บก์ฒ 2023-03-04 205701" src="https://user-images.githubusercontent.com/95980754/222906551-cb43b4f9-f048-4f06-adb3-15b218462334.png">

<img width="606" alt="ํ๋ฉด ์บก์ฒ 2023-03-05 162742" src="https://user-images.githubusercontent.com/95980754/222953134-44de6852-e1b3-4fa6-b258-6f322a7c474c.png">



### 3-2. ๊ฒ์ํ CRUD ๊ธฐ๋ฅ
 
<details>
<summary>๊ฒ์ํ CRUD ๊ธฐ๋ฅ ์ค๋ช ํผ์น๊ธฐ</summary>
<div markdown="1">

### 1. ๊ฒ์๊ธ ๋ฑ๋ก
 
<img width="734" alt="register" src="https://user-images.githubusercontent.com/95980754/222907874-3d775e74-983b-4813-bf26-7f6ec2e800e4.png">
  
* ์ฌ์ฉ์๊ฐ /register ํ์ด์ง์์ ๊ฒ์๊ธ์ ํฌ์คํํ๋ฉด BoardDTO์ ํํ๋ก BoardController์ ์ ๋ฌ๋ฉ๋๋ค. ๐[BoardController](src/main/java/org/zerock/b01/controller/BoardController.java)
* @Vaild๋ฅผ ํตํด ์๋ฒ์ชฝ์์๋ ๋ฐ์ดํฐ์ ์ ํจ์ฑ์ ํ์ธํ  ์ ์์ต๋๋ค. 

<img width="367" alt="ํ๋ฉด ์บก์ฒ 2023-03-04 233500" src="https://user-images.githubusercontent.com/95980754/222908453-e5c7e0d6-ace2-43e3-a7ee-190080ed6c40.png"> 
  
* BoardServiceImpl์์ register๋ก ์๋น์ค ๋ก์ง์ ์ฒ๋ฆฌํฉ๋๋ค. ๐[BoardServiceImpl](src/main/java/org/zerock/b01/service/BoardServiceImpl.java)
* ์ง์  SQL์ ๋ค๋ฃจ๋ ๋์  JPA์ ์ฌ์ฉ์ผ๋ก Entity ๊ฐ์ฒด์ธ Board ํด๋์ค๋ฅผ ํตํด ๊ฐ์ฒด์งํฅ์ ์ผ๋ก ๋ฐ์ดํฐ๋ฅผ ๋ค๋ฃฐ ์ ์๊ฒ ๋ฉ๋๋ค. ๐[์ฝ๋ ํ์ธ1](src/main/java/org/zerock/b01/repository/BoardRepository.java) ๐[Board](src/main/java/org/zerock/b01/domain/Board.java)
* ๊ฒ์๊ธ ๋ฑ๋ก ํ /list๋ก redirect ๋ฉ๋๋ค.

### 2. ๊ฒ์๊ธ ์์ 
  
<img width="595" alt="ํ๋ฉด ์บก์ฒ 2023-03-05 001559" src="https://user-images.githubusercontent.com/95980754/222914103-2b31b892-fbfd-411b-b290-4aca48a9a3b5.png">
  
* ์ฌ์ฉ์๊ฐ ๊ฒ์๊ธ์ ์์ ํ๋ฉด PageRequestDTO ํํ๋ก BoardController์ ์ ๋ฌ๋ฉ๋๋ค. ๐[BoardController](src/main/java/org/zerock/b01/controller/BoardController.java)
  
<img width="458" alt="image" src="https://user-images.githubusercontent.com/95980754/222914499-43e9e4cd-1d6e-4bef-9e2a-82ff4e695589.png">
  
* BoardServiceImpl์ modify๋ก ์๋น์ค ๋ก์ง์ ์ฒ๋ฆฌํฉ๋๋ค. ๐[BoardServiceImpl](src/main/java/org/zerock/b01/service/BoardServiceImpl.java)
* ์ง์  SQL๋ก ๋ฐ์ดํฐ๋ฅผ ์์ ํ๋ ๋์  JPA์ ์ฌ์ฉ์ผ๋ก change ๋ฉ์๋๋ฅผ ํตํด ๋ฐ์ดํฐ๋ฅผ ์์ ํ๊ณ  save ๋ฉ์๋๋ก ์ ์ฅ ํ  ์ ์์ต๋๋ค. ๐[Board](src/main/java/org/zerock/b01/domain/Board.java)
  
### 3. ๊ฒ์๊ธ ์ญ์ 
  
<img width="533" alt="image" src="https://user-images.githubusercontent.com/95980754/222914852-2ae5faa3-6c3f-4c5a-b1ed-06e1ccedf44f.png">

* ์ฌ์ฉ์๊ฐ ๊ฒ์๊ธ์ ์ญ์ ํ๋ฉด Long bno๋ก ๊ฒ์๊ธ ๋ฒํธ๋ฅผ ํตํด BoardController์ ์ ๋ฌ๋ฉ๋๋ค. ๐[BoardController](src/main/java/org/zerock/b01/controller/BoardController.java)
  
<img width="230" alt="ํ๋ฉด ์บก์ฒ 2023-03-05 003543" src="https://user-images.githubusercontent.com/95980754/222915019-3881b1d2-45ae-431a-bb85-e0989521fffe.png">

* ์ง์  SQL๋ก ๋ฐ์ดํฐ๋ฅผ ์ญ์ ํ๋ ๋์  JPA์ ์ฌ์ฉ์ผ๋ก deleteById ๋ฉ์๋๋ฅผ ํตํด ๊ฐ์ฒด์งํฅ์ ์ผ๋ก ๋ฐ์ดํฐ๋ฅผ ์ญ์  ํ  ์ ์์ต๋๋ค. ๐[BoardServiceImpl](src/main/java/org/zerock/b01/service/BoardServiceImpl.java)

### 4. ๊ฒ์๊ธ ์กฐํ

<img width="484" alt="ํ๋ฉด ์บก์ฒ 2023-03-05 000934" src="https://user-images.githubusercontent.com/95980754/222913735-275ef613-e3e8-4ca1-a461-59bac8076c41.png">

* ์ฌ์ฉ์๊ฐ /list ํ์ด์ง์์ PageRequestDTO ํํ๋ก ๋ฐ์ดํฐ๋ฅผ BoardController์ ์ ๋ฌ๋ฉ๋๋ค. ๐[BoardController](src/main/java/org/zerock/b01/controller/BoardController.java)
* PageReqestDTO์ ๊ฐ์ด ์๋ค๋ฉด @Builder.Default๋ฅผ ํตํด ์ด๊ธฐ๊ฐ์ ์ด์ฉํด์ ์ฒซ ํ์ด์ง๋ฅผ ๋ณด์ฌ์ค๋๋ค. ๐[PageRequestDTO](src/main/java/org/zerock/b01/dto/PageRequestDTO.java)
* addattribute ๋ฉ์๋๋ฅผ ํตํด model์ PageResponseDTO๋ฅผ ๋ด์ view๋ก ๋ฐ์ดํฐ๋ฅผ ์ ๋ฌํฉ๋๋ค.

<img width="577" alt="ํ๋ฉด ์บก์ฒ 2023-03-05 144442" src="https://user-images.githubusercontent.com/95980754/222943776-f3fc5f85-769a-453f-bb6c-8d85d945eab6.png">

* BoardServiceImpl์์ PageRequestDTO๋ฅผ ํตํด ๋ฐ์ดํฐ๋ฅผ ์ถ์ถํด์ searchAll ๋ฉ์๋๋ก DB์ SELECT์์ฒญ์ ๋ณด๋ด์ ๋ฐ์ดํฐ๋ฅผ ์กฐํํฉ๋๋ค. ๐[BoardServiceImpl](src/main/java/org/zerock/b01/service/BoardServiceImpl.java)

</div>
</details>
 
### 3-3. ๊ฒ์ํ ๊ฒ์ ๊ธฐ๋ฅ
 
<details>
<summary>๊ฒ์ํ ๊ฒ์ ๊ธฐ๋ฅ ์ค๋ช ํผ์น๊ธฐ</summary>
<div markdown="1">

### ๊ฒ์๊ธ ๊ฒ์  
  
<img width="650" alt="ํ๋ฉด ์บก์ฒ 2023-03-05 120906" src="https://user-images.githubusercontent.com/95980754/222945125-6646a3d1-bfa5-4466-ac0f-03b9827bf850.png">

* list.html์์ thymeleaf์ selected๋ฅผ ํตํด ๊ฒ์ ๊ธฐ์ค์ ๋ฐ๋ผ์ PageRequestDTO์ ๋ฐ์ดํฐ๋ฅผ ๋ด์ต๋๋ค. ๐[list.html](src/main/resources/templates/board/list.html)
 
<img width="527" alt="ํ๋ฉด ์บก์ฒ 2023-03-05 160145" src="https://user-images.githubusercontent.com/95980754/222946585-73cd343c-f5cb-46af-9cfe-3012f061b3b0.png">

* Http์ ๋น์ฐ๊ฒฐ์ฑ(Connectionless)์ ๋ฌด์ํ์ฑ(Stateless)์ผ๋ก ํ์ด์ง ์ํ๋ฅผ ์ ์งํ๊ธฐ ์ํด์, PageRequestDTO์์ ํ์ด์ง ์ ๋ณด๋ฅผ query parameter์ ๋๊ฒจ์ค๋๋ค. ๐[PageRequestDTO](src/main/java/org/zerock/b01/dto/PageRequestDTO.java)
 
 <img width="577" alt="ํ๋ฉด ์บก์ฒ 2023-03-05 144442" src="https://user-images.githubusercontent.com/95980754/222946058-4f038bdc-3133-449a-9286-30ddb3e1146c.png">

* ๊ฒ์ ํ์๊ณผ ๊ฒ์์ด, ํ์ด์ง ์ ๋ณด๋ฅผ searchAll ๋ฉ์๋์ ๋๊ฒจ์ค๋๋ค. ๐[BoardServiceImpl](src/main/java/org/zerock/b01/service/BoardServiceImpl.java)

<img width="508" alt="ํ๋ฉด ์บก์ฒ 2023-03-05 154307" src="https://user-images.githubusercontent.com/95980754/222945921-7ce38084-c9d3-4f35-bdd2-65e7eb7e62bd.png">
 
* searchAll์์ Querydsl์ Booleanbuilder๋ฅผ ์ด์ฉํด์ ๊ฒ์ ๊ธฐ์ค์ ๋ง๊ฒ Query์ OR ์กฐ๊ฑด์ ์ถ๊ฐํด์ DB์ ๊ฒ์ํ ํ ๊ฒฐ๊ณผ๋ฅผ ๊ฐ์ ธ์ต๋๋ค. ๐[BoardSearchImpl](src/main/java/org/zerock/b01/repository/search/BoardSearchImpl.java)

</div>
</details>

### 4. ๋๋์ 
----------------------------------------------
#### 4-1. ๊ธฐ๋ฐ ๊ธฐ์ ์ ๋ํ ์ดํด์ ์ค์์ฑ
* ์คํ๋ง ๋ถํธ๋ฅผ ํตํด ์น ์ ํ๋ฆฌ์ผ์ด์์ ๋ง๋ค๋ฉด์ ๋ด๋ถ๊ฐ ์ด๋ป๊ฒ ๋์๊ฐ๋์ง ์ ์ ์์ด์ ๋ต๋ตํจ์ ๋๊ผ์ต๋๋ค. ๊ทธ๋์ ์คํ๋ง์ ๊ธฐ๋ฐ ๊ธฐ์ ์ธ Http์ Servlet์ ๋ํด์ ๊ณต๋ถํ๊ธฐ ์์ํ์ต๋๋ค. ์ด๋ฅผ ํตํด์ ์คํ๋ง์ ๊ธฐ๋ฐ ๊ธฐ์ ์ธ Servlet์ด ์ด๋ค ์์ผ๋ก Http ๋ฉ์์ง๋ฅผ ์ฒ๋ฆฌํ๋์ง ์ดํดํ๊ฒ ๋์์ต๋๋ค. ์๋ฅผ ๋ค์ด์ Redirection์ ๊ฒฝ์ฐ Servlet์ ํตํด Http ์๋ต ๋ฉ์์ง์ 3XX ์๋ต์ ๊ฒฐ๊ณผ๋ฅผ ๋ฃ์ต๋๋ค. ๊ทธ๋ผ ๋ธ๋ผ์ฐ์ ๊ฐ Http ์๋ต ๋ฉ์์ง์ ์ฝ๊ณ  ๋ฆฌ๋ค์ด๋ ์์ด ์ด๋ค์ง๊ฒ ๋ฉ๋๋ค. ์ด๋ฅผ ํตํด ์คํ๋ง ๋ด๋ถ์์ ์ด๋ค ์ผ์ด ์ผ์ด๋๋์ง ๋ ๊น๊ฒ ์๊ฒ ๋์์ต๋๋ค.

#### 4-2. ๊ฐ์ฒด์งํฅ์ ์ฅ์ ์ ๋ํ ์ดํด
* ์คํ๋ง ๋ถํธ๋ก ์น ์ ํ๋ฆฌ์ผ์ด์์ ๋ง๋ค๋ฉด์ '์ ๋ฒ๊ฑฐ๋กญ๊ฒ ์ธํฐํ์ด์ค๋ฅผ ์ด์ฉํด์ ํด๋์ค๋ฅผ ๊ตฌํํ๋ ๊ฑธ๊น?'๋ผ๋ ์๋ฌธ์ ๊ฐ์ง๊ฒ ๋์์ต๋๋ค. ์ด์ ๋ํ ๋ต์ ์ฐพ๊ธฐ ์ํด์ ์ถ๊ฐ๋ก ๊ฐ์ฒด์งํฅ์ ๋ํด ๊ณต๋ถ๋ฅผ ํ๊ฒ ๋์์ต๋๋ค. ์ข์ ๊ฐ์ฒด์งํฅ ์ค๊ณ๋ ๊ตฌ์ฒดํ์ ์์กดํ์ง ์๊ณ  ์ถ์ํ์๋ง ์์กดํฉ๋๋ค. ๋๋ถ์ ๋ถํ์ ๋ฐ๊ฟ ๋ผ์ฐ๋ฏ ํด๋์ค์ ๊ต์ฒด๊ฐ ์ฌ์์ง๋๋ค. ๋ํ ์ธํฐํ์ด์ค๋ก ๊ตฌํ๋ ํด๋์ค์ ์ถ๊ฐ์ ์ธ ์ ์ง ๋ณด์ ๋น์ฉ์ด ์ค์ด๋ญ๋๋ค. ์ด๋ฐ ์ง์์ ํตํด ์คํ๋ง์ด ๊ฐ์ฒด์งํฅ์ ์ผ๋ก ๋งค์ฐ ์ฐ์ํ ๊ธฐ์ ์ด๋ผ๋ ๊ฒ์ ์๊ฒ ๋์์ต๋๋ค.

#### 4-3. ๋ฐ์ดํฐ๋ฒ ์ด์ค์ JPA ๋ฑ ์ถ๊ฐ์ ์ธ ๊ณต๋ถ์ ํ์์ฑ
* ๊ฒ์ํ์ ๋๊ธ ๊ธฐ๋ฅ์ ์ถ๊ฐํ๊ณ  ์ถ์์ง๋ง 1:N๊ณผ ๊ฐ์ ๋ฐ์ดํฐ๋ฒ ์ด์ค ์ค๊ณ์ ๋ํ ์ดํด๊ฐ ํ์ํ์ต๋๋ค. 3ํ๋ 1ํ๊ธฐ์ ๋ฐฐ์ฐ๋ ๋ฐ์ดํฐ๋ฒ ์ด์ค ์์คํ ๊ณผ๋ชฉ์ ์๊ฐํ๊ณ  ์ถ๊ฐ์ ์ธ JPA์ ๋ํ ํ์ต์ ์งํํ  ์์ ์๋๋ค. ์ด์ธ์๋ ํ๋ก์ ํธ๋ฅผ ์งํํ๋ฉด์ TDD(ํ์คํธ ์ฃผ๋ ๊ฐ๋ฐ)์ ๋ํด์ ์๊ฒ ๋์์ต๋๋ค. ๋ค์์๋ ์ด ๋ฐฉ๋ฒ๋ก ์ ์ ์ฉ์ํค๋ฉด์ ์ถ๊ฐ์ ์ธ ํ๋ก์ ํธ๋ฅผ ์งํ ํด๋ณด๋ ค๊ณ  ํฉ๋๋ค. 

