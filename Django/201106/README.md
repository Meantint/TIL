&nbsp;배우는 프로그래머님의 오지랖 파이썬 웹 프로그래밍을 보며 공부한 것을 토대로 작성하였습니다.

[배우는 프로그래머 유튜브](https://www.youtube.com/channel/UCoIC6Nj833OCz3J3bZrJGyg)

## 실습 파일 

- [https://github.com/Meantint/Django_Study/tree/master/prac_Django](https://github.com/Meantint/Django_Study/tree/master/prac_Django)

## 뷰(View)

- `Django`에서의 View는 기능을 담당한다(페이지 단위로)

- View 내용(함수, 클래스)은 URL이 있으면 동작한다.

- 함수형

	- `request`를 매개변수로 받는다(추가 매개변수 가능).

	- 내가 원하는대로 동작들을 설계하고 만들고 싶을 때 사용한다.

- 클래스형

	- `CRUD`(`Create`, `Read`, `Update`, `Delete`)처럼 기존에 많이 사용하는 기능을 미리 클래스로 만들어두고 상속받아서 사용한다.

	- 보통 클래스형을 많이 쓴다(`Generic View`가 편하기 때문에)

	- `Generic View`

		장고가 미리 만들어 놓은 뷰(읽기 뷰, 쓰기 뷰 등)

```python
# views.py
from django.http import HttpResponse
# 템플릿을 렌더링 해주는 것
from django.shortcuts import render


# 이 화면을 보려면 URL 주소가 필수 !
# 어떤 매개변수를 가지고 있는지 request안에 들어가 있음
# 기본 함수형 사용
def index(request):
    # 어떤 계산이나 데이터베이스 조회, 수정, 등록 작업을 하여
    # 응답 메시지를 만들어서 반환.
    # html 변수를 대신해서 템플릿을 사용할 것임(앞으로)
    html = "<html><body>Hello</body></html>"
    return HttpResponse(html)


# 실습
# 뷰의 이름은 : welcome
# 뷰의 접속 주소 : welcome/
# 내용은 : Welcome to Django.
def welcome(request):
    html = "<html><body>Welcome to Django!</body></html>"
    return HttpResponse(html)


# 템플릿 이용
def template_test(request):
    # 기본 템플릿 폴더
    # 1. admin 앱 (기본적 설치)
    # 2. 각 앱의 폴더에 있는 templates 폴더
    # 3. 우리가 설정한 폴더
    return render(request, 'test.html')


# 연습할 것
# 함수형 뷰 만들기, 템플릿 만들기, URL 연결하기, 브라우저로 접속해보기
```

## 주소(URL)

- 보통 함수, 템플릿과 주소는 일대일 대응이라고 생각하면된다.

- `from .views import index, welcome, template_test`는 현재 디렉토리의 `views.py`에서 `index`, `welcome`, `template_test`을 사용하게 해준다.

```python
# urls.py
from django.contrib import admin
from django.urls import path
from .views import index, welcome, template_test

urlpatterns = [
    path('admin/', admin.site.urls),
    # ''은 가장 넓은 범위이기 때문에 위에서 매칭이 안되면 '' path로 갈 가능성이 높기 때문에 가급적 가장 아래 두는게 좋음
    path('welcome/', welcome),
    path('test/', template_test),
    # path(주소, 뷰, 주소의 별명)   
    # index라는 뷰를 동작하게 할 것이다
    path('', index),
]
```

- `templates`를 이용하기 위해서는 `settings.py`에 등록 해주어야 한다.

```python
# in settings.py
'DIRS': [
    os.path.join(BASE_DIR, 'templates'),
],
```

- 등록 후 `templates/test.html`까지 만들면 템플릿까지 써서 뷰를 만들어보는 과정 끝!

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>Title</title>
</head>

<body>
	이것은 템플릿 연습 파일입니다.
</body>

</html>
```