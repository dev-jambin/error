![](https://blog.kakaocdn.net/dn/KPLy7/btrSvezwb1V/O6vt2Y3FfLxMRv84IqBcE1/img.png)

Execution failed for task ':Application.main()'.

> Process 'command 'JDK경로/bin/java.exe'' finished with non-zero exit value 1
이번에 소개할 에러는 finishi with non-zero exit value 1 이 녀석이다.

Intellij, Gradle 환경에서 Spring 코드를 실행한 후 해당 에러를 만났다.

해결 방법
[File > Settings > Build, Excution, Deployment > Build Tools > Gradle] 이 경로로 이동
[Build and run using]과 [Run tests using]을 IntelliJ IDEA로 변경
[Gradle JVM] 버전을 현재 프로젝트 버전과 동일한 버전으로 변경
다시 실행
그래도 에러가 발생한다면 IntelliJ를 재부팅해보자
해결!
![](https://blog.kakaocdn.net/dn/bR3gBs/btrSwkF7MYi/TIvxt1gDlqKjEY1NVwCLOK/img.png)
![](https://blog.kakaocdn.net/dn/wNOOm/btrSw59gkOq/lT7iwKzgEchhExSUXY5dh0/img.png)
