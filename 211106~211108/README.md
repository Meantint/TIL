# 211106~211108 TIL

## Python

- [BOJ_11726 - 2×n 타일링](https://github.com/Meantint/Baekjoon/blob/master/Silver%20III/BOJ_11726/BOJ_11726.py)

- [BOJ_17626 - Four Squares](https://github.com/Meantint/Baekjoon/blob/master/Silver%20V/BOJ_17626/BOJ_17626.py)

## FastAPI(Backend)

> **로컬, 서버 코드(root_path가 다름)가 달라서 계속 수정해야하는 문제 수정 (dotenv 설정)**
>

- [환경변수 사용하기(.env 사용하기)](https://one-step-a-day.tistory.com/152)

서버의 `.env` 파일은 `LOCAL=""`을, 로컬의 `.env` 파일은 `LOCAL="True"`를 저장해놓았다.

```python
if os.environ.get("LOCAL") != "True":
    app = FastAPI(root_path="/backend")  # Server
else:
    app = FastAPI()  # Local
```

> **MySQL 1822 Error**
>

- [[1822] Failed to add the foreign key constraint MySQL에러](https://yusang.tistory.com/104)

## 느낀 점

서버에 백엔드 파일을 올려서 동작시키는데 로컬과 EC2 서버의 `root_path`가 달라서 서버에서 `git pull`을 받았을 때 코드를 수정해야하는 문제(귀찮음)가 발생했다. `.env` 파일을 만들어서 로컬과 서버의 경우에 `root_path` 경로가 달라지도록 만들었다.
