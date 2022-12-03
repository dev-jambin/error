![image](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2F9AgUJ%2FbtrSw4JiDL7%2FYhzdiIbL4fVxo3ifwOq0l0%2Fimg.png)

```
org.springframework.boot.web.server.PortInUseException: Port 8080 is already in use
```

오늘 소개할 친구는 PortInUseException: Port 8080 is already in use 요 녀석이다.

SpringMVC를 연습하던 중 로컬을 확인하기 위해 실행하다가 만난 에러다.

사실 이전에도 한 번 만난적 있는데 생각보다 자주 만나게 되서 블로그에 남기기로 했다. 원인과 해결방법 모두 생각보다 간단하다.

## 원인

원인은 2가지 정도로 볼 수 있다.

-   이미 사용중인 포트를 다른 애플리케이션에서 사용하려고 할 때
-   IDE에서는 프로세스가 종료되었지만 실제로 프로세스가 종료되지 않고 계속해서 실행중일 때

보통 두 번째 이유때문에 해당 에러가 발생한다. 나도 IDE를 한 번 종료했다가 다시 실행시키면서 해당 에러가 발생했다.

## 해결 방법

해결방법은 간단하다. cmd에서 실행중인 포트를 종료하면 된다.

종료 방법은 OS에따라 다르기대문에 Mac과 Window로 나누어서 설명하겠다.

### Mac

1.  cmd를 열어 아래 명령어로 PID를 찾는다.

```
lsof -i : [포트 번호]
```

1.  해당 PID를 아래 명령어에 입력해 프로세스를 강제 종료한다.

```
kill -9 [PID]
```

### Window

1.  cmd를 열어 아래 명령어를 입력한다.

```
netstat -ano
```

1.  종료해야하는 포트 번호를 가진 로컬 주소의 PID를 확인한 후 아래 명령어에 입력한다.

```
taskkill /f /pid [PID]
```

필자는 Mac을 사용하고 있기 때문에 Window 이미지는 없다. 미안합니다ㅠ
