# 파이썬 기초 문법 정리(점프 투 파이썬  3장)
## 제어문
#
### if문
#
-  if문은 기본적으로  
if 조건문 :  
    수행할 문장1,  
    수행할 문장2  
    .  
    .  
    .  
와 같은 방식으로 이루어 진다.
- c언어에서 {수행할 문장}처럼 묶는것과 달리 파이썬은 묶는게 없기 때문에 들여쓰기를 해야 한다.
- if문은 조건문이 참인지 거짓인지 판별하여 참이라면 : 아래의 문장을  실행하고, 거짓이라면 : 아래의 문장을 무시한다.
- 비교연산자
    - x == y x와 y가 같다.
    - x != y x와 y가 같지 않다.
    - x < y x가 y보다 크다.
    - x > y y가 x보다 크다.
    - x <= y x가 y보다 크거나 같다.
    - x >= y y가 x보다 크거나 같다.
- x==y를 예로 x와 y가 같다면 True를 반환하고 다르다면 False를 반환한다.
- python의 여러 연산자들
    - and연산자는 두 조건이 있을 때, 둘 다 참이면 True를 반환한다.
    - or연산자는 두 조건이 있을 때, 둘중 하나만 참이면 True를 반환한다.
    - not연산자는 True는 False로, False는 True로 바꾼다.
    - x in 리스트 를 했을 때, x가 리스트에 들어있으면 True를 반환한다. 튜플이나 문자열도 가능.
    - x not in 리스트 를 했을 때 x가 리스트에 안들어있으면 True를 반환한다. 튜플이나 문자열도 가능.
- elif
    - if문 하나로는 코드가 너무 복잡해서 나온 제어문이다.
    - elif 뒤에 조건문을 사용해서 만약 if가 아니라면 elif 조건문을 확인하고, True라면 실행한다.
        - 예제
            - if a == 10 :  
            &nbsp;&nbsp;&nbsp;&nbsp;print(1)  
            elif a == 20 :  
            &nbsp;&nbsp;&nbsp;&nbsp;print(2)  
            else :  
            &nbsp;&nbsp;&nbsp;&nbsp;print(3)
    - 위 코드는 만약 a가 10이라면 1을 출력, 20이라면 2를 출력, 아니라면 3을 출력하는 코드이다.
    - elif는 여러개 들어갈 수 있다. c언어의 else if와 똑같다.
- 여러가지 팁
    - 조건문의 수행할 문장을 없이 하고 싶다면 수행할 문장 대신 pass를 쓰면 된다.
    - 들여쓰기는 주로 띄어쓰기 4번과 탭으로 나뉜다. 띄어쓰기를 하자는 추세.
    - 위에 기본적인 if문 구조에서 수행할 문장 1번은 띄어쓰기 4번, 2번은 탭을 하면 서로 다른 들여쓰기라 인식되서 오류가 난다.
    - 이러한 오류는 눈에 보이지 않아 고치기 어렵다.
#
### while문
#
- 기본적인 구조는  
while 조건문 :  
&nbsp;&nbsp;&nbsp;&nbsp;수행할 문장1
&nbsp;&nbsp;&nbsp;&nbsp;수행할 문장2
- while문은 기본적으로 조건문이 참인동안 while 안의 수행할 문장을 반복해서 실행한다.
- c언어의 while과 같다.
- 루프를 강제로 나가는 break가 있다.
- 루프의 맨 위로 올라가는 continue가 있다. continue 아래의 문장은 실행되지 않는다.
- while True : 수행할 문장 을 하면 break가 없는 이상 무한히 반복한다.
#
### for문
#
- for문 구조  
    - for 변수 in 리스트 :  
    &nbsp;&nbsp;&nbsp;&nbsp;수행할 문장1  
    s수행할 문장1
    - for문은 기본적으로 리스트가 있고, 그 리스트의 값을 하나씩 꺼내와서 i에 대입하고 리스트가 끝나면 for문도 끝난다.
    - 만약 리스트 안에 튜플이 있다면 for (first,last) in a 처럼 리스트의 안의 튜플의 값을 가져올 수 있다.
- continue
    - while문과 마찬가지로 continue를 사용하면 for문 가장 위로 올라간다.
    - 하지만 while문과 달리 리스트의 내용이 다음으로 바뀐다.
- range
    - range(처음 숫자, 끝 숫자) 함수는 처음 숫자부터 끝 숫자까지 숫자 리스트를 만들어 준다.
        - (python)for i in range(1,10) = (c)for(int i = 1; i < 10; i++)
    - 처음숫자를 지정하지 않으면 0이다.
- 리스트 내포
    - 리스트 안에 for문을 포함하는 프로그램이다.
    - 구조
        - a = [1,2,3,4]  
        b = [num * 2 for num in a if num %2 == 0]
        - 대괄호 안에 실행할 문장(리스트에 들어갈 값) [for 변수 in 객체 if 조건문] 으로 구성되어 있다.
#
### 연습문제 풀이
#
- 1번
    - 1 - wife가 없다  
    2 - python은 있지만 you가 없어야 하는데 있다.  
    3 - 맞았다ㅏ
    4 - 맞는데 위에 elif문에서 나갔다
    - shirt
- 2번
    - i = 0  
    sum = 0  
    while i < 1000:  
    &nbsp;&nbsp;&nbsp;&nbsp;if i % 3 == 0:  
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;sum += i  
    &nbsp;&nbsp;&nbsp;&nbsp;i += 1  
    print(sum)
- 3번
    - i = 1   
    j = 0  
    sum = 0  
    while i < 6:  
    &nbsp;&nbsp;&nbsp;&nbsp;while j < i:  
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;print('*', end = "")  
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;j += 1  
        print()  
        i += 1  
        j = 0
- 4번
    - for i in range(1,101):
    &nbsp;&nbsp;&nbsp;&nbsp;print(i)
- 5번
    - a = [70, 60, 55, 75, 95, 90, 80, 80, 85, 100]  
    sum = 0  
    for i in a:  
    &nbsp;&nbsp;&nbsp;&nbsp;sum += i  
    print(sum / len(a))
- 6번
    -numbers = [1, 2, 3, 4, 5]  
    results = [num * 2 for num in numbers if num%2 == 1]