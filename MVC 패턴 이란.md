# MVC 패턴 
![image](https://github.com/user-attachments/assets/f5889b1a-7e33-4ab7-8b14-0f7d5d72d2c0)
---

## MVC 패턴은 무엇일까?
 - **먼저 MVC 패턴의 정의와 Model-View-Controller는 무엇인지 살펴보자.**

## 1. MVC의 핵심 구성 요소

### 1.1 Model (모델)

- #### 역할:
&nbsp;&nbsp;&nbsp; - 애플리케이션의 데이터와 비즈니스 로직을 담당합니다. <br>
&nbsp;&nbsp;&nbsp; - 데이터베이스와의 상호작용이나 특정 비즈니스 규칙을 포함합니다.<br>
&nbsp;&nbsp;&nbsp; - DAO(Data Access Object) 및 DTO(Data Transfer Object)와 긴밀하게 연결됩니다.<br>
&nbsp;&nbsp;&nbsp; - 예: 사용자의 정보(이름, 이메일 등)를 저장하는 User 클래스. 데이터베이스에서 데이터를 가져오는 DAO.<br>

### 1.2 View (뷰)

- #### 역할:
&nbsp;&nbsp;&nbsp; - 사용자에게 데이터를 보여주는 UI 요소를 담당합니다. <br>
&nbsp;&nbsp;&nbsp; - 모델에서 가져온 데이터를 화면에 표시하며, 사용자가 입력한 데이터를 컨트롤러로 전달합니다<br>
&nbsp;&nbsp;&nbsp; - DAO(Data Access Object) 및 DTO(Data Transfer Object)와 긴밀하게 연결됩니다.<br>
&nbsp;&nbsp;&nbsp; - 예: HTML, JSP, Thymeleaf 등으로 구현된 화면. 유저 목록, 로그인 화면, 대시보드 UI 등이 포함.<br>

### Controller (컨트롤러)

- #### 역할:
&nbsp;&nbsp;&nbsp; - 사용자의 요청을 받고, 이를 처리하여 응답을 반환하는 로직을 담당합니다 <br>
&nbsp;&nbsp;&nbsp; - 모델과 뷰를 연결하며, 모델에서 데이터를 가져와 뷰로 전달하거나, 뷰에서 받은 데이터를 처리하여 모델에 저장합니다.<br>
&nbsp;&nbsp;&nbsp; - DAO(Data Access Object) 및 DTO(Data Transfer Object)와 긴밀하게 연결됩니다.<br>
&nbsp;&nbsp;&nbsp; - 예: Spring의 @Controller나 @RestController로 작성된 클래스. 사용자가 전송한 로그인 정보를 받아 인증 처리 후 결과를 반환하는 컨트롤러 메서드.<br>


