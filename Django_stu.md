# 장고 모델
#
### 모델이란
#
- 장고 내의 모델은 특수한 객체로, 이 모듈에 저장하면 db에도 저장이 된다.
    - 기본 db는 SQLite db이다.
#
### 애플리케이션
#
- python manage.py startapp 이름  
으로 만들 수 있다.
    - cd를 이용해 manage.py가 있는 폴더로 이동하지 않으면 사용할 수 없다.
- 만든 장고 애플리케이션을 적용하기 위해서는 settings.py 파일에서 INSTALLED_APPS 맨 마지막에 '애플리케이션이름', 로 넣어줄 수 있다.
-  ## 모델 만들기
    - models.py 라는 파일을 열어 내용을 삭제하고 다음 코드를 입력한다.
```python
from django.conf import settings
from django.db import models
from django.utils import timezone


class Post(models.Model):
    author = models.ForeignKey(settings.AUTH_USER_MODEL, on_delete=models.CASCADE)
    title = models.CharField(max_length=200)
    text = models.TextField()
    created_date = models.DateTimeField(
            default=timezone.now)
    published_date = models.DateTimeField(
            blank=True, null=True)

    def publish(self):
        self.published_date = timezone.now()
        self.save()

    def __str__(self):
        return self.title
```
- 코드 해석
    - import
        - django의 conf에서 settings라는 것을 가지고 온다.
        - django의 db에서 models를 가지고 온다.
        - django의 utils에서 timezone을 가지고 온다.
    - 클래스
        - Post라는 클래스를 만들고, models를 상속받는다
    - 쟝고 모델 속성 정의
        - models.ForeignKey를 통해 다른 모델에 대한 링크를 정의해 준다.
        - models.CharField를 통해 글자수 제한이 있는 텍스트를 정의해준다.
        - models.DateTimeField를 통해 날짜와 시간 데이터를 정의해 준다.
        - models.TextField를 통해 글자수 제한이 없는 텍스트를 정의해 준다.
    - def publish
        - 시간을 저장하는 메서드이다.
        - 변경된 db를 저장해 준다.
    - def \_\_str\_\_
        - 문자열로 객체를 출력할 때 호출된다.
- db에 모델 추가하기
    - python manage.py makemigrations  
    으로 변경된 모델을 migrations파일로 저장하라고 시켰을 때 오류가 없다면 OK를 출력하고 파일을 만들어준다.
    - migrations 파일이 실제 sql문을 실행시켜준다.
- 관리자 페이지 만들기
    - admin.py 파일을 다음 내용으로 바꿔준다.
``` python
from django.contrib import admin
from .models import Post

admin.site.register(Post)
```
- 이렇게 하면 그냥 localhost 주소에서는 로컬 서버가, localhost 주소/admin은 장고의 관리자 페이지가 열린다.
    - 만약 관리자 화면을 한국어로 바꾸고 싶다면 settings.py에서 LANGUAGE_CODE를 ko-kr로 바꿔준다.
    - 어드민 계정 만들기
        - python manage.py createsuperuser 를 친다.
        - 아이디, 이메일, 비밀번호, 비밀번호 확인을 순서대로 해 준다.


#
### 중략(동아리시간에 공부)
#
### ORM
- ORM이란 원래 db는 SQL문을 통해 사용할 수 있는데 이러한 SQL문이 다른 언어와 맞지 않아서 파이썬은 파이썬 코드로 짜면 알아서 SQL문으로 변경해주는게 ORM이다.
- 장고쉘이란 cmd와 비슷하지만 python의 명령어를 사용할 수 있는 cmd라고 생각하면 편하다.
    - 기존 파이썬 쉘에서 더 기능이 추가된 ipython이란것도 있다.
        - pip install ipython을 통해 설치할 수 있다.
- 장고쉘 을 통해 장고 모델 조작하기
    - (이전에 Post 객체를 만들었다고 가정)
    - from (애플리케이션명).models import Post을 통해 우리가 만들었던 Post객체를 가져온다.
    - Post.objects.all()을 통해 객체(db)에 저장된 모든 데이터가 출력된다.
    - Post.objects 을 통해 db에 값을 요청해서 가져올 수 있다.
    - User.objects.get(username="유저명")을 통해 유저를 줄력할 수 있다.
    - User.objects가 너무 길다면 변수에 넣어줄 수 있다.
        - 우리는 me에 User.objects.first()를 저장한다.
    - Post.objects.create()를 통해 객체를 만들어 줄 수 있다.
        - Post.objects.create(author = me, title = '제목', text = '텍스트')
    - Post.objects.count()를 통해 객체의 개수를 셀 수 있다.
    - Post.objects.filter()를 통해 가져오는 데이터를 필터링해줄 수 있다.
        - Post.objects.filter(author=me)
        - title\_\_contains와 같이 필터의 내용에 연산자를 넣을 수 있다.(contains가 뭔지는 모르겠지만..)
    - 현재 시간을 가져오는 방법
        - from django.utils.import timezone
        - timezone.now()를 통해 현재 시간을 가져올 수 있다(UTC기준)
    - 정렬
        - Post.objects.order_by(정렬할 컬럼)을 통해 정렬할 수 있다.
        - Post.objects.order_by(-정렬할 컬럼)을 통해 내림차순으로 정렬할 수 있다.
    - 쿼리셋 체이닝
        - 말은 어려워 보이지만, 그냥 여러 ORM 함수를 연결해서 사용하는 것이다.