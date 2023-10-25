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

* git fork rules


* git issue rules
    
