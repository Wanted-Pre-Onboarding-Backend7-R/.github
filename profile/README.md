![원티드 프리온보딩 백엔드 인턴십 (2023.10~11)](https://static.wanted.co.kr/images/events/3178/58ac3248.jpg)

# Intro
<div align="center">

| name | role | github | email |
|------|------|--------|-------|
| 강석원 | 팀원 | [@piopoi](https://github.com/piopoi) | kangsw1988@gmail.com |
| 모장현 | 팀원 | [@mojh7](https://github.com/mojh7) | mjh79017901@gmail.com |
| 박준승 | 팀원 | [@OldRabbit736](https://github.com/OldRabbit736) | junseung736@gmail.com |
| 이소현 | 팀원 | [@sohyuneeee](https://github.com/sohyuneeee) | sohyuney@naver.com |
| 정준희 | 팀장 | [@JoonheeJeong](https://github.com/JoonheeJeong) | jeonggoo75@gmail.com |

</div>
</br>

안녕하세요. 

원티드에서 진행하는 <large>**백엔드 프리온보딩 인턴십 (2023.10.23~2023.11.17) R팀**</large>입니다.

저희가 과제 수행 시에 사용한 언어 및 환경, 수행해야 할 과제 정보 및 진행 현황, 프로젝트를 진행하고 지키고자 협약한 규칙에 대한 내용이 정리된 다음의 목차를 클릭하시면 원하시는 내용을 확인할 수 있습니다.

</br>

* [Environments](#environments)
* [Projects](#projects)
* [Conventions](#conventions)
    * [Git](#git)
    * [Code](#code)

</br>

---
## Environments
</br>
<div align="center">
  
  ![Java](https://img.shields.io/badge/Java-%2017%20-lightcoral.svg?&style=flat&logo=Java&logoColor=white&labelColor=red&cacheSeconds=3600$logoWidth=60)
  ![Spring Boot](https://img.shields.io/badge/SpringBoot-%203.1.5%20-lightgreen.svg?&style=flat&logo=SpringBoot&logoColor=white&labelColor=44A833&cacheSeconds=3600$logoWidth=60)

</div>
</br>

---
## Projects

</br>

---
## Conventions
> ### Code
- 변수명: boolean인 경우 형용사, 그 외 명사
- 함수명: 동사 현재형으로 시작
- 클래스명: 명사
- if, for 중괄호 한 줄이라도 항상 치기
- 커밋하기 전에
    - import 정리: `ctrl + alt(option) + o`
    - line formatting: `ctrl(command) + alt(option) + l`
    - 마지막 빈 줄 추가
    ```java
    /** 예시 **/
    public class Clazz {

        public int addCountIfValid(int count, boolean isValid) {
            if (isValid) {
                return count + 1;
            }
            return count;
        }
    }
    // 마지막 빈 줄
    ```
    
 - Optional 줄바꿈
   ```java
   Member member = memberRepository.findByEmail(dto.getEmail())
         .orElseThrow(NotFoundMemberByEmailException::new);`
   ```
- 객체 생성 규칙
  - 외부에서 직접적인 new 지양하고 내부적으로 활용 `@Builder` 및 정적 팩토리 메서드 활용
    - 정적 팩토리 메서드 이름은 단일 인자일 경우 `from`, 다중 인자일 경우는 `of`로 명명 
  - Bean 제외 DTO, Entity들은 `@All-/@Required-ArgsContructor` 활용 제한, 직접 코드로 생성자 작성 및 private/protected 등으로 잠그기
  - 목적: 같은 타입의 필드 연속될 때 다른 값을 집어넣는 human error 방지 및 가독성을 위한 작성법 통일을 위하여
  ```java
   @Getter
   @NoArgsConstructor(access = AccessLevel.PROTECTED)
   @EqualsAndHashCode(of = "accountName", callSuper = false)
   @Entity
   public class Member extends BaseEntity {
   
       @Column(nullable = false, unique = true)
       private String accountName;
   
       @Column(nullable = false)
       private String email;
   
       @Column(length = 60, nullable = false)
       private String password;
   
       @Column(length = 6, nullable = false)
       private String approvalCode;
   
       @Column(nullable = false)
       private Boolean isApproved;
   
       @Enumerated(EnumType.STRING)
       private Authority authority;
   
       @Builder
       private Member(String accountName, String email, String password, String approvalCode, Boolean isApproved) {
           this.accountName = accountName;
           this.email = email;
           this.password = password;
           this.approvalCode = approvalCode;
           this.isApproved = isApproved;
           authority = Authority.ROLE_USER;
       }
   
       public static Member of(MemberJoinRequest dto, String encodedPassword, String approvalCode) {
           return builder()
                   .accountName(dto.getAccountName())
                   .email(dto.getEmail())
                   .password(encodedPassword)
                   .approvalCode(approvalCode)
                   .isApproved(false)
                   .build();
       }
   }

  ```

> ### Git
* git commit rules
  
  | type     | description |
  |----------|-------------|
  | feat     | 새로운 기능 추가 |
  | fix      | 버그 및 로직 수정 |
  | refactor | 기능 변경 없는 코드 구조, 변수/메소드/클래스 이름 등 수정 |
  | style    | 코드 위치 변경 및 포맷팅, 빈 줄 추가/제거, 불필요한 import 제거 |
  | test     | 테스트 코드 작성 및 리팩토링 |
  | setup    | build.gradle, application.yml 등 환경 설정 |
  | docs     | 문서 작업 |

  ```bash
  # commit title format
  git commit -m "{커밋 유형} #{이슈번호}: #{내용}"

  # example of git conventions
  git commit -m "refactor #125: `ChatService` 중복 로직 추출

  예외 압축
  메소드 위치 변경
  메소드 이름 변경
  "
  ```

* git branch rules
  ```bash
  # branch name format
  git checkout -b "feat/#{이슈번호}-{내용}"
  ```
