# 장고 ORM 30개 사용
## SELECT
1. Post.objects.all()
    - User의 모든 데이터를 출력한다.
2. Post.objects.get(조건)
    - 조건은 where처럼 사용하면 된다.
    - 조건에 맞는 데이터를 가져와 준다.
    - 조건에 맞는 데이터가 없다면 DoesNotExist란 오류를 보낸다.
3. Post.objects.first()
    - 첫 데이터를 가져온다.
4. Post.objects.last()
    - 마지막 데이터를 가져온다.
5. Post.objects.filter(조건)
    - SQL의 where처럼 조건에 맞는 데이터를 전부 가져온다.
    - 동일한 명령어로 objects.all().filter()가 있다.
6. Post.objects.order_by(기준)
    - 컬럼을 기준으로 오름/내림차순 할 수 있다.
    - 기준 앞에 -를 붙이면 내림차순, 그냥 쓰면 오름차순이다.
7. Post.objects.values(컬럼)
    - 해당 컬럼들을 전부 가져온다.
        - ex)User.objects.values('title')은 모든 title을 가져옴.
    - 컬럼을 비우면 모든 데이터를 출력한다.
        - all과는 다르게 정말 데이터를 하나하나 가져온다.
8. Post.objects.count()
    - 모든 데이터의 수를 가져온다
    - 만약 a = Post.objects.filter()을 통해 값을 추려냈다면, a.count()를 통해 추려내진 것의 개수를 구할 수 있다.
9. Post.objects.get_or_create(넣을 데이터)
    - 필드에 완전히 동일한 데이터가 있다면 가져오되, 없다면 생성한다.
        - 해 본 결과, 필드 내의 데이터 하나라도 다르면 생성된다.
        - insert 되는 데이터만 해당되며, 자동으로 입력되는 created_date 같은 경우에는 달라도 create가 된다.
    - create 했다면 true, 값을 가져왔다면 False를 함께 return한다.
10. Post.objects.update_or_create()
    - 이건 아무리 찾아봐도 왈도체로 번역된 글밖에 없어서 찾을수가 없다.
## Insert
8. Post(컬럼 = '데이터', 컬럼 = '데이터...).save()
    - save()를 통해 db에 저장할 수 있다.
    - Post(컬럼 = '데이터')부분은 변수에 저장해놨다 변수.save()를 해도 상관없다.
9. Post.objects.create(컬럼='데이터')
    - save()와 비슷하지만, 바로 저장된다.
## Update
10. save()를 이용
    - get을 통해 update하고싶은 데이터를 가져온 후, 변수.(원하는 컬럼) = "바꾸고싶은 값"으로 하나를 업데이터할 수 있다.
    - data = Post.objects.get(title="집가고 싶어요")  
    data.title="update_title_test"  
    data.save()
## delete
13. delete()
    - (filter 등으로 받은 데이터).delete()를 하면, 결과물 을 모두 지운다.
### 필터링 조건
1. exact
    - title__exact = '제에목'처럼 사용할 수 있다.
        - 그냥 title = '제에목'이랑 뭐가 다른지 모르겠다..
2. iexact
    - 대소문자 구분을 하지 않고 찾는다.
3. contains
    - title__contains = '잡'처럼 사용할 수 있다.
    - '집'이란 문자가 제목에 포함된 모든 데이터를 가져온다.
4. icontains
    - 마찬가지로 대소문자를 무시하고 가져온다.
    - title_icontains = "tEsT"를 하면, test가 포함된 test_create()를 가져올 수 있다.
5. in
    - title__in = ['asdf','집가고 싶다', asdf] 를 하면 저 세개중 하나라도 맞는걸 추출한다.
6. gt
   - title__gt = 'u'를 하면, 첫 글자가 u보다 뒤에 있는 것 들만 추출한다.
7. gte
    - 위와 같지만, gt는 본인을 포함하지 않고 gte는 포함한다고 한다.
        - 왜인지는 모르겠지만 gt = 'u'를 했는데 update_test라는 제목의 데이터가 출력됬다
8. startswith
    - title__startswith = 'u'를 하면 u로 시작하는 데이터들만 가져온다.
9. istartswith
    - title__istartswith = 'u'를 하면 u 또는 U로 시작하는 단어를 가져온다
    - 사실 그냥 대소문자 구문 안하는거다.
10. endswith
    - title__endswith = 't'를 하면 t로 끝나는 데이터만 가져온다.
11. iendswith
    - title__iendswith = 'u' 는 u또는 U로 끝나는 데이터만 가져온다.
12. range
    - title__range = (시작,끝)을 통해 시작과 끝 사이에 있는 모든 데이터를 가져온다.
13. year, month, week_day, hour, minute, second
    - 대표로 year을 들자면, created_date__year = 2020을 통해 2020년도에 생성된 글을 찾을 수 있다. 다른 것 들도 다 비슷비슷 하다.
    - week_day는 1을 일요일, 7을 월요일로 정해서 대응한다.
14. isnull
    - 해당 컬럼에서 데이터가 null인 모든 것을 가져온다.
    - published_date__isnull = True는 published_date가 null인 모든 데이터를 가져온다.
    - False는 null이 아닌 모든 데이터를 가져온다.
15. search
    - title__search = '집'처럼 사용한다.
    - contains와 비슷하지만, 이게 더 빠르다.
        - 근데 이거 어떻게 쓰는지 모르겠어요.. 에러나네요
16. regex / iregex
    - 이건 정규표현식인데, 전혀 모르겠어서 포기