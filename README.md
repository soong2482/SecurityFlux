# SecurityMVC

기초적인 Spring Security를 사용한 MVC 프로젝트입니다. 이 프로젝트에서는 회원가입(SignUp), 로그인(Login), 로그아웃(Logout), 그리고 Role 권한에 따른 API 요청을 구현합니다

## 프로젝트 설정

### 1. 환경 설정(BuildGradle)
- Spring Boot Starter Security
- Spring Boot Starter Web
- MyBatis Spring Boot Starter
- Spring Boot Starter Logging
- Lombok
- MariaDB JDBC 드라이버
- MyBatis
- Spring Boot Starter Data Redis
- Spring Session Data Redis
- Spring Boot Starter Mail

### 2.메서드 소개(SignUP)
https://github.com/soong2482/SecurityMVC/blob/main/src/main/java/com/spring/SecurityMVC/SignUpInfo/Service/SignUpService.java 

#### 중복검증(아이디중복검증)
Post요청으로 
{
    "UserName" : "soong2482"
}
##### 처리 과정:
MyBatis를 통해 UserMapper에서 아이디를 조회하고, Optional<String> 형태로 반환된 데이터를 검증합니다.
여기서 검증할 데이터는 아이디의 중복 여부입니다. 존재하면 이미 사용 중인 아이디로 간주하고, 존재하지 않으면 사용 가능한 아이디로 처리합니다.



#### 이메일 검증(이메일중복검증)
Post요청으로 
{
    "Email" : "soong3899@naver.com"
}
##### 처리 과정:
MyBatis를 통해 UserMapper에서 이메일을 조회하고, Optional<String> 형태로 반환된 데이터를 검증합니다.
여기서 검증할 데이터는 이메일의 중복 여부입니다. 존재하면 이미 사용 중인 이메일로 간주하고, 존재하지 않으면 사용 가능한 이메일로 처리합니다.
