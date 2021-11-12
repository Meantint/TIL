# 211112 TIL

## 싸피 프로젝트

- OpenAPI가 사용된 외부 파일을 이용해서 백엔드 API 제작을 했다.

## 도커 인프런 강의 수강(도커 설치)

인프런 - [풀스택을 위한 도커와 최신 서버 기술](https://www.inflearn.com/course/%EC%84%9C%EB%B2%84%EA%B8%B0%EC%88%A0-%ED%92%80%EC%8A%A4%ED%83%9D-3/dashboard)

---

### Docker 설치(환경 : Ubuntu 20.04)

1. 최신 패키지 리스트 업데이트

    ```bash
    sudo apt update
    ```

2. Docker 다운로드를 위해 필요한 HTTPS 관련 패키지 설치

    ```bash
    sudo apt install apt-transport-https ca-certificates curl software-properties-common
    ```

3. Docker Repository 접근을 위한 GPG Key 설정

    ```bash
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
    ```

4. Docker Repository 등록

    ```bash
    sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu/ focal stable"
    ```

5. 등록한 Docker Repository까지 포함하여 최신 패키지 리스트 업데이트

    ```bash
    sudo apt update
    ```

6. Docker 설치

    ```bash
    sudo apt install docker-ce
    ```

7. Docker 실행 중임을 확인

    ```bash
    sudo systemctl status docker
    ```

    <img src="https://user-images.githubusercontent.com/50372451/141483014-a8ed4694-6847-4602-b445-c51b0c80e4f9.png" width="720">

    Active: active (running)을 보면 잘 동작하고 있음을 알 수 있다.

---

### sudo 명령 없이 Docker 명령어 사용하기 설정

1. 현 사용자 ID를 docker group에 포함 → 재접속한다.

    ```bash
    sudo usermod -aG docker ${USER}
    ```

2. 현재 ID가 docker group에 포함되어 있는지를 확인한다.

    ```bash
    id -nG
    ```

3. sudo 명령어 없이 docker 명령을 바로 내릴 수 있다.

    ```bash
    docker
    ```

    > **3번 이슈**
    >

    명령어를 입력해줬는데 `id -nG`를 입력하니 docker가 포함되어 있지 않았다. 근데 `docker` 명령어 입력하면 문제없이 명령어 사용이 가능한 것 같다. 뭐지?

---

### Ubuntu 20.04에서 docker-compose 설치

> **docker-compose**
>
- 상용화되는 docker는 여러개를 올려서 한번에 실행한다.
- 그렇게 사용하기 위해서 필요한 것이 docker-compose

1. 최신 버전 설치

    ```bash
    sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
    ```

2. 실행 권한 주기

    ```bash
    sudo chmod +x /usr/local/bin/docker-compose
    ```

3. 이 명령어 실행시 버전 확인이 가능하면 성공

    ```bash
    docker-compose --version
    ```

    <img src="https://user-images.githubusercontent.com/50372451/141483018-1b9ccb6f-a23a-42ae-92b6-feb1af23f246.png" width="720">

    성공

---

## 느낀 점

도커가 클라이언트/서버의 통신 개념으로 동작하는지 처음 알았다.
