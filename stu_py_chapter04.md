# 파이썬 기초 문법 정리(점프 투 파이썬  4장)
## 입출력
#
### 함수
#
- 함수란 미리 만들어둔 어떤 일을 수행하는 코드를 통해 입력값을 넣고, 원하는 결과를 받는것을 말한다.
- 함수는 똑같은 내용을 반복해서 작성하다 보면, 매우 귀찮기도 하고 가독성도 떨어진다.하지만 함수를 통해 프로그램의 흐름을 잘 볼 수 있다.
- 함수의 구조
    - def 함수이름(매개변수):  
    &nbsp;&nbsp;&nbsp;&nbsp;수행할 문장1  
    &nbsp;&nbsp;&nbsp;&nbsp;수행할 문장2
    - def add(a,b):  
    &nbsp;&nbsp;&nbsp;&nbsp;return a+b
- 함수 선언
    - def란 c에서 function과 같은 의미로, 함수를 만들때 사용하는 예약어 이다.
    - 함수를 사용할 때엔 함수이름(입력)을 사용해야 한다.
    - add란 함수는 매개변수가 있으므로 add(1,2)와 같은 방식으로 사용해야 한다.
    - 매개변수가 없는 함수는 그냥  
    def 함수이름():  
    으로 선언할 수 있다.
- 함수 사용
    - 매개변수가 없는 함수는 함수이름()을 통해 호출할 수 있다.
    - a = add(1,2)라면 add(1,2) 대신 3을 넣어 a = 3과 똑같다.
- 매개변수
    - 매개변수에 * 을 붙이면 입력된 매개변수들을 모두 모아 튜플로 이어붙여서 준다.
    - 매개변수의 개수를 모를 때 사용할 수 있다.
    - 매개변수
- return
    - return을 통해 반환을 하는 함수는 쉽게 말해서 함수이름()이라는 구문 대신 return된 값이 들어간다고 생각하면 편하다
    - 함수에 return이 없어도 된다.
    - return 은 하나만 실행된다.
    - return의 결과는 항상 하나이다.
    - c언어처럼 아예 여러개를 못 보내는게 아니라, 여러개를 튜플로 묶어서 리턴할 수 있다.
- 매개변수 초깃값
    - 매개변수에  
    def add(num1,num2 = 10)  
     처럼 초깃값을 설정하면 초깃값을 줄 수 있다.
    - 함수를 호출할 때 add(1,2)를 해도 되지만, add(1)만 해도 num1,num2에는 각각 1,10이 들어간다.
    - def add(num1 = 10, num2)  
    에서는 오류가 나는데, 이것처럼 초깃값을 지정한 매개변수는 뒤에서부터 채워야 한다.
    - def add(num1,num2 = 10, num3 = 20)은 가능
- 함수내에서 선언한 변수
    - 함수 내에서 선언한 변수는 함수 밖에서 사용할 수 없다.(일반적인 경우)
- 함수에서 함수 밖 변수를 변경하는 방법
    - return을 통해 함수 밖의 함수에 대입한다.(a = add(1,2)처럼.)
    - 변수 앞에 global을 사용하면 함수 밖의 변수를 사용할 수 있다.(비추)
- lambda
    - 함수를 한줄로 간결하게 선언하고 싶을 때 사용한다.
    - 람다라고 읽는다.
    - 사용법
        - add = lambda a,b:a+b
    - return 없이도 결괏값을 돌려준다.
#
### 사용자 입력과 출력
#
- input
    - 사용자의 입력을 변수에 넣고싶을 때 사용한다.
    - a = input()처럼 사용할 수 있다.
    - input()은 모든것을 문자열 취급한다.
- print
    - print(출력할 내용)으로 사용할 수 있다.
    - print("asdf" "asdf")에서 큰따옴표로 둘러싸인 문자열은 +연산과 동일하게 작용해서 asdfasdf가 출력된다.
    - print("asdf","asdf")는 asdf asdf가 출력되는 것 처럼 문자열은 ,로 띄어쓰기 한다.
    - print 맨 뒤에는 기본적으로 개행을 한다.
    - 출력한 뒤에 띄어쓰기나, 개행을 안하는 등 출력한 뒤 끝 문자를 지정하려면 ,end=""처럼 하면 된다.
#
### 파일 읽고 쓰기
#
- 파일 생성
    - f = open(파일 위치, 모드)  
    를 통해 사용할 수 있다.
    - 모드
        - r - 읽기모드(수정 불가)
        - w - 쓰기모드(파일 내용 날리고 처음부터 쓰기)
        - a - 추가모드(파일 맨 뒤에 내용 추가)
    - 맨 뒤에 f.close()처럼 open에서 사용한 변수.close를 해야 오류가 나지 않는다.
- 파일에 입력
    - f.write(내용)을 통해 입력할 수 있다.
- 읽기
    - f.readline()
        - f.readline()을 통해 한줄을 읽을 수 있다.
        - 읽을때마다 다음줄을 가져온다.
    - f.readlines()
        - 파일의 모든 줄을 읽어서 가져온다.
        - 각 줄을 리스트로 가져온다.
    - read()
        - 파일 내용 전체를 문자열로 가져온다.
- 참고
    - with open("foo.txt", "w") as f:  
    f.write("Life is too short, you need python")  
    을 사용하면 파일을 다 읽고 나면 알아서 close해 줘서 편하다.
#
### 연습문제
#
- 1번
    - def is_odd(a):  
    &nbsp;&nbsp;&nbsp;&nbsp;if a%2==0:  
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return "짝수"  
    &nbsp;&nbsp;&nbsp;&nbsp;else:  
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return "홀수"
- 2번
    - def sum(*num):  
    &nbsp;&nbsp;&nbsp;&nbsp;qq = 0  
    &nbsp;&nbsp;&nbsp;&nbsp;for i in num:  
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;qq += i  
    &nbsp;&nbsp;&nbsp;&nbsp;print(qq/len(num))  
    &nbsp;&nbsp;&nbsp;&nbsp;sum(1,2,3,4)
- 3번
    - input1 = int(input("첫번째 숫자를 입력하세요:"))  
    input2 = int(input("두번째 숫자를 입력하세요:"))  
    total = input1 + input2  
    print("두 수의 합은 %s 입니다" % total)
- 4번
    - 3번. 3번만 you need python으로 사이사이에 띄어쓰기가 있다.
- 5번
    - f1 = open("test.txt", 'w')  
    f1.write("Life is too short")  
    f1.close()  
    f2 = open("test.txt", 'r')  
    print(f2.read())  
    f2.close()
- 6번
    - f1 = open("test.txt", 'a')  
    f1.write(input("문자열을 입력해 주세요."))  
    f1.write("\n")  
    f1.close()  
    f2 = open("test.txt", 'r')  
    print(f2.read())  
    f2.close()
- 7번
    - 본문에 없음. replace 문제.