# 기본 개발 용어 정리(얄코 유튜브)
### 디버그
- 간단 정리
    - 소프트웨어 문제 원인을 찾는것
    - 만드는 도중에도 함
    - 오류가 났을 때 필수
    - 개발중인 상태를 나타내기도 함
- 필요
    - 코드가 원하는 결과를 내지 않는 등의 오류가 있을 때 사용된다.
    - 규모가 작다면 필요 없을 수 있겠지만, 규모가 커질수록 필요해진다.
- 유래
    - 옛날 컴퓨터에 bug(벌레) 가 들어가서 오류가 났는데, 거기서 debug(벌레를 없애다)가 유래했다고 한다.
### 컴파일러와 인터프리터
- 우리의 프로그래밍 언어
    - 우리가 지금 사용하고 있는 프로그래밍 언어는, 기계들은 알아낼 수 없다.
    - 하지만 0과 1로 코딩을 하는건 너무 힘들기 때문에 우리는 우리들이 사용하기 쉬운 언어로 프로그래밍을 한다.
- 컴파일
    - 컴파일이란, 우리의 코드를 컴퓨터가 알아먹을 수 있는 언어로 번역하는 것.
    - 이걸 하는걸 컴파일러라고 부른다.
    - 이런걸 하는 언어를 컴파일 언어라고 한다.
- 인터프리터
    - 매번 다른 사람들이 들어올때마다 새로 번역하는 거를 인터프리터라고 한다.
    - 속도는 느리다.
    - 업데이트가 쉽다.
    - 코드 누출이 쉽다.
### 빌드
- 빌드란
    - 원래 수십, 수백개의 파일로 되어있는 프로젝트를, 나중에 출시할 때는 압축해서 내보낸다.
    - 이것을 빌드라고 말한다.
    - .exe 파일처럼 사용자가 바로 실행할 수 있도록 하기 위해
    - 용량 압축
- 1줄 정리
    - 출시를 위해 정리하는거
### 배포
- 배포란
    - 배포란 앱이면 플레이스토어, 웹이면 웹사이트에 다른 사용자가 사용할 수 있도록 하는것
    - 웹 배포란 웹페이지에서 바뀐 코드를 다른 사람들이 볼 수 있도록 하는것
### 환경변수
- 환경이란
    - 소프트웨어가 동작하는 환경
- 환경변수란
    - 컴퓨터마다 지정되어있는 값
- 사용
    - 어느곳에서도 하나의 코드가 잘 작동함
    - 개발을 할 때, 개발중인지 배포된건지 환경변수에서 지정할 수 있음
    - 비밀번호 같은 경우에 직접적인 비밀번호로 인해 노출 위험이 큰데, 환경변수를 사용하면 됨
### 라이브러리와 프레임워크
- 라이브러리란
    - 다른 사람 또는 내가 만들어 놓은 함수나 클래스들의 묶음을 라이브러리라고 한다.
- 프레임워크란
    - 기본적인 골격을 갖춰 둔 것.
    - 하나의 프로젝트에서 사용된면 코드의 형태가 프레임워크 형태로 바뀜
    - 골격 위에 라이브러리를 통해 프로그램을 더 쉽게 만들 수 있다.