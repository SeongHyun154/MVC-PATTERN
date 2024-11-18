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
