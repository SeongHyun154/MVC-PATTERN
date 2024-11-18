# MVC 패턴 
<p align="center">
![image](https://github.com/user-attachments/assets/f5889b1a-7e33-4ab7-8b14-0f7d5d72d2c0)
</p>

---

## MVC 패턴은 무엇일까?
 - **먼저 MVC 패턴의 정의와 Model-View-Controller는 무엇인지 살펴보자.**

## 1. MVC의 핵심 구성 요소

### 1.1 Model (모델)
- **역할**:  
  - 애플리케이션의 데이터와 비즈니스 로직을 담당합니다.
  - 데이터베이스와의 상호작용이나 특정 비즈니스 규칙을 포함합니다.
  - DAO(Data Access Object) 및 DTO(Data Transfer Object)와 긴밀하게 연결됩니다.
  - DAO(Data Access Object) 및 DTO(Data Transfer Object)와 긴밀하게 연결됩니다.
- **예**:  
  - 사용자의 정보(이름, 이메일 등)를 저장하는 User 클래스.
  - 데이터베이스에서 데이터를 가져오는 DAO.

### 1.2 View (뷰)
- **역할**:  
  - 사용자에게 데이터를 보여주는 UI 요소를 담당합니다.
  - 모델에서 가져온 데이터를 화면에 표시하며, 사용자가 입력한 데이터를 컨트롤러로 전달합니다

- **예**:  
  - HTML, JSP, Thymeleaf 등으로 구현된 화면. 
  - 유저 목록, 로그인 화면, 대시보드 UI 등이 포함

 ### 1.3 Controller (컨트롤러)
- **역할**:  
  - 사용자의 요청을 받고, 이를 처리하여 응답을 반환하는 로직을 담당합니다
  - 모델과 뷰를 연결하며, 모델에서 데이터를 가져와 뷰로 전달하거나, 뷰에서 받은 데이터를 처리하여 모델에 저장합니다.
  - 

- **예**:  
  - Spring의 @Controller나 @RestController로 작성된 클래스.
  - 사용자가 전송한 로그인 정보를 받아 인증 처리 후 결과를 반환하는 컨트롤러 메서드.



## 2. MVC 패턴의 확장 요소

### 2.1 DAO (Data Access Object)

- **역할**:  
  - 데이터베이스와 상호작용하는 객체로, 주로 SQL 쿼리를 작성하거나 ORM(Object-Relational Mapping)을 통해 데이터를 CRUD(Create, Read, Update, Delete)하는 역할을 합니다.

- **예**:  
  - `UserDAO`: 사용자의 데이터를 조회하거나 수정하는 클래스.
  - Spring에서는 `@Repository` 어노테이션을 통해 DAO를 구현합니다.

```java
@Repository
public class UserDAO {
    public User findById(Long id) {
        // 데이터베이스 조회 로직 구현
        return new User("exampleUser", "example@example.com");
    }
}
```
### 2.2 DTO (Data Transfer Object)

- **역할**:  
  - 데이터를 전송하거나 교환하기 위한 객체입니다. 주로 컨트롤러와 뷰 간, 또는 서비스와 컨트롤러 간 데이터 교환을 위해 사용됩니다.
 
- **특징**:  
  - Getter/Setter만 포함된 간단한 객체입니다.
  - 데이터 유효성 검증 로직은 포함되지 않습니다.

- **예**:  

```java
public class UserDTO {
    private String username;
    private String email;

    // Getter and Setter
}```

### 2.3 Service (서비스 레이어)

- **역할**:  
  - 비즈니스 로직을 처리하는 중간 계층입니다. 컨트롤러에서 요청을 받아 DAO를 호출하거나, 특정 로직을 수행한 결과를 반환합니다.
 
- **특징**:  
  - 비즈니스 로직이 컨트롤러에 집중되지 않도록 하여 재사용성과 유지보수성을 높입니다.
  

- **예**:  

```java
@Service
public class UserService {
    private final UserDAO userDAO;

    public UserService(UserDAO userDAO) {
        this.userDAO = userDAO;
    }

    public UserDTO getUserById(Long id) {
        User user = userDAO.findById(id);
        return new UserDTO(user.getUsername(), user.getEmail());
    }
}
}```



