- 인프런 Spring 강의 (무료 부분)
  - [기본 환경 및 라이브러리 간단 설명](#환경-설정-및-기본-환경)
  - [Spring 동작 설명](#thymeleaf-템플릿엔진-동작-확인)
  - [Spring Web 개발 기초](#Spring-Web-개발-기초)
    - [정적 컨텐츠](#정적-컨텐츠)
    - [MVC와 템플릿 엔진](#MVC와-템플릿-엔진)
    - [API](#API)
  - [회원 관리 예제](#회원-관리-예제)
    - [회원 Repository 테스트 케이스](#회원-Repository-테스트-케이스)
    - [회원 서비스 개발](#회원-서비스-개발)
    - [회원 서비스 테스트](#회원-서비스-테스트)
  - [Spring Bean과 의존관계](#Spring-Bean과-의존관계)
    - [컴포넌트 스캔과 자동 의존관계 설정](#컴포넌트-스캔과-자동-의존관계-설정)
    - [자바 코드로 직접 스프링 빈 등록하기](#자바-코드로-직접-스프링-빈-등록하기)
  - [회원 관리 예제(웹 MVC 개발)](#회원-관리-예제(웹-MVC-개발))
    - [회원 웹 기능(홈 화면 추가)](#회원-웹-기능(홈-화면-추가))
    - [회원 웹 기능(등록)](#회원-웹-기능(등록))
    - [회원 웹 기능(조회)](#회원-웹-기능())



# 인프런 Spring 강의 정리 (무료 ver)

# 환경 설정 및 기본 환경 
1. 인텔리제이 설치  
2. https://start.spring.io/   
Gradle Project, Java, SpringBoot 에서 뒤에 영어 붙어 있는 것 제외 가장 최신 버전 선택  
Dependency : Spring Web, Thymeleaf 다운로드 

-> 다운로드 받은 파일을 인텔리제이에서 오픈  

<p align="left"><img src="https://user-images.githubusercontent.com/48474613/134111485-c229f722-1259-468d-a9b2-eb723a61d44f.png" width="50%" height="50%"/> </p>


<p align="left"><img src="https://user-images.githubusercontent.com/48474613/134111764-3afb7d6a-7f37-41d4-9991-d902955225f4.png" width="30%" height="30%"/> </p>
gitignore이라는 폴더는 Git에 업로드시 코드만 올라가야하고 결과물 등은 올라가면 안됨. Spring에서 자체적으로 관리해주는 것


## 라이브러리 살펴보기

<p align="left"><img src="https://user-images.githubusercontent.com/48474613/134113782-fcbae00f-1a22-4be2-b767-be14ec4cc2d9.png" width="50%" height="50%"/> </p>  

**1. spring-boot-starter-web**  
 ``spring-boot-starter-tomcat`` : 톰캣 (웹서버)   
 ``spring-webmvc`` : 스프링 웹 MVC  
 
 
**2. spring-boot-starter-thymeleaf : 타임리프 템플릿 엔진(View)**  


**3. spring-boot-starter : 스프링 부트 + 스프링 코어 + 로깅**  
  ``spring-boot`` : spring-core  
  `` spring-boot-starter-logging`` : [logback, slf4j](#Logging?)   
  
  
**4. spring-boot-starter-test**  
  `` junit`` : 테스트 프레임워크     
  `` mockito`` : 목 라이브러리  
  `` assertj`` : 테스트 코드를 좀 더 편하게 작성하게 도와주는 라이브러리  
  `` spring-test`` : 스프링 통합 테스트 지원  

### Logging?
프로그램 개발 중이나 완료 후 발생할 수 있는 오류에 대해 디버깅하거나 운영 중인 프로그램 상태를 모니터링 하기 위해 필요한 정보(로그)를 기록하는 것

<p align="left"><img src="https://user-images.githubusercontent.com/48474613/134113376-49769b09-7ccb-4f57-9687-a56d104737c6.png" width="50%" height="50%"/> </p>
현업에서는 System.out.print 사용하면 안되고 log로 출력을 해야한다.  
log로 남겨야 심각한 에러들만 모아서 남겨놓거나 log를 관리할 수 있기 때문.  


# thymeleaf 템플릿엔진 동작 확인
<p align="left"><img src="https://user-images.githubusercontent.com/48474613/134116962-8b4476ff-a2fe-45b7-a4d9-bb3d9884228d.png" width="70%" height="70%"/> </p>

 - 컨트롤러에서 리턴 값으로 문자를 반환하면 뷰 리졸버가 화면을 찾아서 처리  
 - ``resources:templates/`` + {ViewName} + ``.html``


# Spring Web 개발 기초

# 정적 컨텐츠
<p align="left"><img src="https://user-images.githubusercontent.com/48474613/134121898-0a473f84-e932-4e85-9922-7212937a8b0b.png" width="30%" height="30%"/> </p>  
정적 컨텐츠는 Controller없이 html 파일을 만든 후 localhost:8080/index.html이라고 실행시켜주면 바로 실행 가능  
<p align="left"><img src="https://user-images.githubusercontent.com/48474613/134121789-c635c2fc-4664-4996-bddc-d702e56f7dac.png" width="70%" height="70%"/> </p>   

1. controller에서 index라는 것을 찾음   
2. controller에 없으면  
3. 내부에 있는 resources:static/index.html을 찾아서 반환  

# MVC와 템플릿 엔진
<p align="left"><img src="https://user-images.githubusercontent.com/48474613/134122818-06bc00ae-41a4-4bb1-8483-e94ba45134c9.png" width="70%" height="70%"/> </p>   

1. 웹 브라우저에서 hello-mvc를 넘기면 내장 톰켓 서버를 실행  
2. 톰켓 서버거 스프링에게 hello-mvc라는 것이 들어왔다고 넘겨줌  
3. spring은 controller에 해당 메소드가 매핑이 되어 있으면 호출을 함  
4. return은 hello-template, model은 name:spring이라고 넘겨줌  
5. viewResolver(화면과 관련된 해결자, view를 찾아주고 template엔진을 연결시켜주는 것)가 tmemplates/hello-template라는 것을 찾아서 Thymeleaf에게 처리해달라고 넘김  
6. Thymeleaf가 렌더링을 해서 변환을 한 html파일을 웹 브라우저에 반환

정적일때는 변환하지 않고 바로 반환, 이런 템플릿 엔진에서는 변환을 하고 반환  

### 변환?
```<p th:text="'hello ' + ${name}"></p>```  
이렇게 되어 있는 html 코드를 controller에서 받은 값을 넣어서 화면에 hello spring 이라고 변환하여 보여주는 것

# API
``` java
@Controller
public class HelloController {
 @GetMapping("hello-string")
 @ResponseBody
   public String helloString(@RequestParam("name") String name) {
   return "hello " + name;
 }
}
```

### ResponseBody?
HTTP의 body부에 데이터를 직접 넣어주겠다는 의미


```java
@Controller
public class HelloController {
 @GetMapping("hello-api")
 @ResponseBody
 public Hello helloApi(@RequestParam("name") String name) {
   Hello hello = new Hello();
   hello.setName(name);
   return hello;
 }
 static class Hello {
   private String name;
     public String getName() {
     return name;
    }
   public void setName(String name) {
     this.name = name;
   }
 }
}
```
<p align="left"><img src="https://user-images.githubusercontent.com/48474613/134125432-f52b836e-a39f-4064-8309-9e60d4dde9be.png" width="70%" height="70%"/> </p>   

1. 톰켓 서버에서 hello-api가 왔다고 spring에게 넘겨줌  
2. controller에서 hello-api가 있는 것을 확인  
3. 어노테이션에서 @ResponseBody가 있는 것을 확인하고 객체(return:hello(name:spring))가 왔으면 JSON방식으로 데이터를 만들어서 HTTP응답에 반환함  

++  
ReponseBody가 존재하면 ViewResolver대신에 HttpMessageConverter가 동작    
단순 문자라면 StringConverter가 동작 객체라면 JsonConverter가 동작  
- 기본 문자 처리 : StringHttpConverter  
- 기본 객체 처리 : MappingJackson2HttpMessageConverter (Json으로 바꿔주는 라이브러리인 Jackson)  

# 회원 관리 예제

``` java
@Override
public Optional<Member> findById(Long id) {
    return Optional.ofNullable(store.get(id));
}
```
Null일 가능성이 있다면 Optional로 감싸서 반환해야 한다.

# 회원 Repository 테스트 케이스
개발한 기능을 실행해서 테스트 할 때 자바의 Main메서드를 통해서 실행하거나 컨트롤러를 통해서 해당 기능을 실행  
이러한 방법은 준비하고 실행하는데 오래 걸리고, 반복 실행하기 어렵고 여러 테스트를 한번에 실행하기 어렵다  
자바는 JUnit이라는 프레임워크로 테스트를 실행해서 이러한 문제를 해결  


<p align="left"><img src="https://user-images.githubusercontent.com/48474613/134132171-8c7323ec-4a1c-454f-945f-d0eb0a4e2a60.png" width="70%" height="70%"/> </p>   

``Assertions.assertThat(member).isEqualTo(result);``  
- 더 직관적으로 사용 가능  
- static import를 하면 assertThat으로 바로 사용 가능  
- member와 result가 같은지 비교하는 것  

## Test케이스 clearStore
<p align="left"><img src="https://user-images.githubusercontent.com/48474613/134133809-677398e2-e67b-45b7-9c36-017c190d0f23.png" width="30%" height="30%"/> </p>   
MemoryMemberRepository에 clearStore를 만들어준 후,

<p align="left"><img src="https://user-images.githubusercontent.com/48474613/134133977-22937233-8578-4b6d-b6ff-2e3392f49a6c.png" width="50%" height="50%"/> </p>  

각각의 테스트 케이스는 순서가 없고 의존관계가 없어야하기 때문에 다른 곳에서 같은 객체에 저장하면 테스트 케이스 오류 발생  
Test하는 곳에서 afterEach를 활용하여 clearstore를 해주어야 함.  

### @AfterEach
한번에 여러 테스트를 실행하면 메모리 DB에 직전 테스트의 결과가 남을 수 있다.  
이렇게 되면 다음 이전 테스트 때문에 다음 테스트가 실패할 가능성이 있다.  
@AfterEach를 사용하면 각 테스트가 종료될 때 마다 이 기능을 실행  


# 회원 서비스 개발  
> TIP  
> Ctrl + Alt + V 단축키를 누르면 자동으로 Return 값을 적어준다.  
> ex) memberRespository.findByName(member.getName()) 작성 후 단축키 입력시 Optional<Member> 알아서 작성해줌  

- 회원가입  
조건 : 같은 이름이 있는 중복 회원 x  
```java
public Long join(Member member){
  Optional<Member> result = memberRepository.findByName(member.getName());  
  result.ifPresent(m -> {
    throw new IllegalStateException("이미 존재하는 회원입니다.");
  });
  
  memberRepository.save(member);
  return member.getId();
}
```

1. findByName으로 name을 찾아본다.  
2. 만약 result가 ifPresent (값이 존재하면)  
3. throw new IllegalStateException으로 넘겨준다    
  
옛날에는 if null이면 형식으로 코딩이 필요했으나 지금은 Optional 덕분에 바로 ifPresent 형식으로 꺼내볼 수 있다.  
Member member = result.get(); 형식으로 꺼내와도 되긴 하지만 직접 바로 꺼내는것을 권장하지는 않는다.  
 ++ result.orElseGet : 값이 존재하면 꺼내오고 존재하지 않으면 디폴트 값을 들고오도록 함.  
 
``` java
    public Long join(Member member) {
        validateDuplicateMember(member); //중복 회원 검증
        memberRepository.save(member);
        return member.getId();
    }
    private void validateDuplicateMember(Member member) { 
        memberRepository.findByName(member.getName())
                .ifPresent(m -> {
                    throw new IllegalStateException("이미 존재하는 회원입니다.");
                });
    }
```
- 어차피 memberRepository.findByName 반환값이 Optional이므로 바로 memberRespository.findByName(member.getName()).ifPresent(.... 라고 해줘도 된다.
- 변경 한 후의 코드를 보면 findByName해서 로직이 나오므로 메서드로 뽑는게 더 좋다.  

Repository는 save, findById 와 같이 데이터를 넣었다 뺐다 하는 느낌이 강한 반면  
Service는 join, findMember 등과 같이 네이밍이 비지니스적이랑 가깝다.   
Service 코드는 비지니스적에 의존적이여야 기획자 혹은 개발자가 문제 발생시에 찾기가 쉽다.  


# 회원 서비스 테스트

> TIP 
> MemberService 위에서 Ctrl + Shift + T 를 누르면 Test 생성 가능  
> Shift + F10 이전에 실행했던 코드를 다시 실행해줌  
  
Build 될 때 Test코드는 배포되지 않으므로 Test 코드는 한글로 적어도 괜찮음.  

```java
    @Test
    public void 중복_회원_예외(){
        //given
        Member member1 = new Member();
        member1.setName("spring");

        Member member2 = new Member();
        member2.setName("spring");

        //when
        memberService.join(member1);
         IllegalStateException e = assertThrows(IllegalStateException.class, () -> memberService.join(member2));
        assertThat(e.getMessage()).isEqualTo("이미 존재하는 회원입니다.");
        
        /*
        try{
            memberService.join(member2);
            fail();
        }catch (IllegalStateException e){
            assertThat(e.getMessage()).isEqualTo("이미 존재하는 회원입니다");
        }
        */
    }
```
- try catch 문 보다 assertThrows라는 문법을 사용하는 것이 더 좋음  
`` assertThrows(IllegalStateException.class, () -> memberService.join(member2)); ``  
memberSerice.join을 해서 member2를 넣으면 IllegalStateException.class 예외가 발생을 해야한다.  
만약 IllegalStateException 대신 NullPointException 실행 시 오류가 발생하게 된다.  

## DI (Dependency Injection)

- MemberService
``` java
public class MemberService {
  private final MemberRepository memberRepository = new MemberRepository();
  ....
}
```
  
- MemberServiceTest
``` java
class MemberServiceTest {
  MemberService memberService = new MemberService();
  MemoryMemberRepository memberRepository = new MemoryMemberRepository();
  ...
}
```  
  
- MemoryMemberRepository
```java
public class MemoryMemberRepository implements MemberRepository {
    private static Map<Long, Member> store = new HashMap<>();
    ...
}
```
  
Service 에서 memberRepository도 new로 객체 생성을 하고 Test에서 memberRepository도 new로 객체 생성을 한다.  
즉, 두개가 서로 다른 객체이다.  
MemoryMemberRepository에서 store이 static으로 선언되어 있기 때문에 인스턴스와 상관없이 클래스에 붙는것이기 때문에 현재는 상관없으나  
new로 다른 객체 repsository가 생성이 되면 다른 인스턴스이기 때문에 내용물이 달라질 수도 있다.  

즉, 현재에는 testservice와 service가 각각 다른 repository이기 때문에 현재 Repository에서 static이라 문제는 없으나 현재 테스트는 다른 repository로 테스트 중이다. 그렇기 때문에 같은 것으로 테스트 하도록 변경을 해주어야 한다.  
  
- MemberService
```java
public class MemberService {
    private final MemberRepository memberRepository;

    public MemberService(MemberRepository memberRepository){
        this.memberRepository = memberRepository;
    }
    ...
```
직접 new로 생성하는 것이 아닌 MemberReposiory를 외부에서 넣어주도록 바꿔줌.  
 
- MemberServiceTest
```java
class MemberServiceTest {
    MemberService memberService;
    MemoryMemberRepository memberRepository ;

    @BeforeEach
    public void beforeEach(){
        memberRepository = new MemoryMemberRepository();
        memberService = new MemberService(memberRepository);
    }
```
BeforeEach를 통해서 동작하기 전에 넣어주면 된다.  
1. MemoryMemberRepository를 생성해주고 memberRepository에 넣어주고
2. MemberService에서 memberRepository를 넣어준다 (MemberService 확인)
  
  

  # 스프링 빈과 의존관계
  
  # 컴포넌트 스캔과 자동 의존관계 설정
  
  > TIP?  
  > getter / setter / 생성자 자동 생성 : Alt + Insert
  
  
  
  
  
  
  
