# Django-study
- [Django 설치 방법](#django-설치-방법)     
- [프로젝트](#프로젝트)
- [애플리케이션](#애플리케이션)

<br>
    
## Django 설치 방법


### 가상환경 설정
- 가상환경 생성
```
python -m venv {venv}
```

- 가상환경 실행
```
source venv/Scripts/activate
```

### django 설치
- 3.2(LTS) 버전을 설치
```
pip install django==3.2.13
```

- 설치 list 확인
```
pip list
```

### vscode에서 설치
- extention 설치     
- - django
- - Excel Viewer

- extention 설정
- - ctrl + shift + p -> Preferences: Open User Settings(JSON)
```
    // Django
    "files.associations": {
        "**/*.html": "html",
            "**/templates/**/*.html": "django-html",
        "**/templates/**/*": "django-txt",
        "**/requirements{/**,*}.{txt,in}": "pip-requirements"
        },
        "emmet.includeLanguages": {
        "django-html": "html"
    }
```

### 패키지 관리     
- 패키지 목록 생성
```
pip freeze > requirements.txt
```

<br>

## 프로젝트     

### 프로젝트 생성 방법
```
django-admin startproject {프로젝트 이름} {경로}
```

### 프로젝트 실행 방법     
```
python manage.py runserver
```

### 프로젝트 구조
- __init___.py
- asgi.py(Asynchronous Server Gateway Interface) : 비동기식 웹 서버와 연결 및 소통, 배포 시에 사용
- settings.py : 프로젝트 설정을 관리
- urls.py : url과 views를 연결
- wsgi.py(Web Server Gateway Interface) : 웹 서버와 연결 및 소통, 배포 시에 사용
- manage.py : 프로젝트를 상호작용하는 커맨드라인 유틸리티

<br>

## 애플리케이션     

### 애플리케이션 생성 방법
```
python manage.py startapp {애플리케이션 이름(복수형을 권장)}
```

### 애플리케이션 구조
- admin.py : 관리자용 페이지 설정
- apps.py : app의 정보
- models.py : 데이터에 관한 처리를 하는 곳
- test.py : 테스트 코드를 작성하는 곳
- views.py : 사용자에게 보여줄 화면을 정의하는 곳

### 애플리케이션 등록 (프로젝트에서 앱을 사용하기 위해서는 추가해 줘야 함)
- settings.py 파일에 애플리케이션 추가
```
INSTALLED_APPS = [
  '애플리케이션 이름'
]

[주의사항-1] : 반드시 애플리케이션 생성 후 등록
[주의사항-2] : Local apps, Third parth apps, Django apps 순서로 등록할 것을 권장

```

### 기타 용어 정리
- LTS(Long Term Support) : 장기 지원 버전     
- - 장기간에 걸쳐 지원하도록 고안된 소프트웨어 버전
