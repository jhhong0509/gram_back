# 파이썬 기초 문법 정리(점프 투 파이썬  5장)
## 심화
#
### 모듈
#
- 모듈 만들기
    - 사용할 함수나 변수 등을 선언한다.
    - .py로 만든 파일들은 모두 모듈이다.
    - 예)  
    파일이름 : module1.py  
    def add(a,b):  
    &nbsp;&nbsp;&nbsp;&nbsp;return a+b
- 모듈 불러오기
    - import 파일이름(.py 없이)
        - import module1
        - 파일 위치가 같을때만 된다.(아마)
    - 파일 맨 위에 헤더파일의 내용이 들어있는것과 같다.
        - 그래서 헤더파일에 print문이 있다면 출력이 된다.
    - from 파일이름 import 함수이름 처럼 파일 내의 함수 하나만 가져올 수 있다.
        - from 파일이름 import 함수이름, 함수이름 ... 처럼 여러개도 가능하다.
        - from 파일이름 import * 을 하면 해당 파일의 모든 함수를 임포트할 수  있다
        - from module1 import add을 하면 module1에서 add함수를 불러올 수 있다.
- if \_\_name\_\_== "\_\_main\_\_"
    - 위에서 말했듯이 헤더파일에 print가 있다면출력이 되는데, 이것을 막기 위한 것이다.
    - \_\_name\_\_는 파이썬이 내부적으로 사용하는 변수이름이다. 파일을 직접 실행할 경우 \_\_name\_\_에는 \_\_main\_\_이 저장된다.
#
### 패키지
#
- 우리가 윈도우에서 흔히 말하던 폴더 혹은 디렉토리를 개발에 편리하게 변형한게 패키지이다.
- 패키지가 다르면 모듈의 이름이 같아도 된다.(다른 패키지의 모듈을 사용할 수 없다.)
- 
#
### 예외처리
#
- 오류 예외 처리 기법
    - try, except 구문
        - try를 실행도중에 오류가 발생하면 except가 실행된다.
        - except 뒤에는 발생오류, 에러메세지가 올 수 있다.
        - 0으로 나누려 했을 때에 나는 오류인 ZeroDivisionError가 생겼을 때, 이 에러가 났을 때의 에러메세지를 저장하고 싶다면  
        try:  
        &nbsp;&nbsp;&nbsp;&nbsp;4/0  
        except ZeroDivisionError as e:  
        &nbsp;&nbsp;&nbsp;&nbsp;print(e)  
        처럼 사용할 수 있다.
        - 에러메세지를 e에 저장해서 넣어준다.
        - as e 구문은 없어도 된다.
        - except 구문은 여러개가 올 수 있다.
        - except 하나에 여러개의 오류를 넣을 수 있다.  
        except(ZeroDivisionError, IndexError) as e  
        처럼.
        - 오류가 났을 때 그냥 통과시키는 방법은 except문 안에 pass를 쓰면 된다.
    - try, finally 구문
        - try구문에서 오류가 생겼던 안생겼던 실행된다.
        - 주로 f.close()처럼 사용한 리소스를 닫을 때 주로 사용한다.
- 오류 강제로 만들기
    - raise 명령어로 강제로 오류를 만들 수 있다.
    - raise 오류이름 으로 사용할 수 있다.
- 예외 만들기
    - class 만들고 싶은 오류이름(Exception):
    &nbsp;&nbsp;&nbsp;&nbsp;내용
    - raise 오류이름 을 통해 사용할 수 있다.
