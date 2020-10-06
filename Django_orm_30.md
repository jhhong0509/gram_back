# 장고 ORM 30개 사용
## SELECT
1. User.objects.all()
    - User의 모든 데이터를 출력한다.
2. User.objects.get(조건)
    - 조건은 where처럼 사용하면 된다.
    - 조건에 맞는 데이터를 가져와 준다.
    - 조건에 맞는 데이터가 없다면 DoesNotExist란 오류를 보낸다.
3. User.objects.first()
    - 첫 데이터를 가져온다.
4. User.objects.last()
    - 마지막 데이터를 가져온다.
5. User.objects.filter(조건)
    - SQL의 where처럼 조건에 맞는 데이터를 전부 가져온다.
    - 동일한 명령어로 objects.all().filter()가 있다.
6. User.objects.order_by(기준)
    - 컬럼을 기준으로 오름/내림차순 할 수 있다.
    - 기준 앞에 -를 붙이면 내림차순, 그냥 쓰면 오름차순이다.
7. User.objects.values(컬럼)
    - 해당 컬럼들을 전부 가져온다.
        - ex)User.objects.values('title')은 모든 title을 가져옴.
    - 컬럼을 비우면 모든 데이터를 출력한다.
        - all과는 다르게 정말 데이터를 하나하나 가져온다.
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
11. filter을 이용
    - 