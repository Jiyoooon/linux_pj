# linux_project
[go to site](https://jiyoooon.github.io/linux_pj/)

## 개념
- WEB
  > static resource를 응답하는 웹 서버<br>
  > 방화벽 밖에 위치(보안이 좋지 않음)<br>
  > 종류 : NginX, Apache
- WAS
  > dynamic resource를 응답하는 웹 애플리케이션 서버<br>
  > 방화벽 안에 위치(보안에 좋음)<br>
  > 종류 : Tomcat, Weblogic

<br><br>
## 1. Apache-Tomcat 연동 후 app deploy
<iframe width="560" height="315" src="https://www.youtube.com/embed/h65JuyhiAFs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### 과정
- Apache2 설치
  > WAS 서버(Tomcat)로 넘길 요청 url을 설정해줌(JkMount `url 패턴` `요청을 넘겨줄 WAS 서버 worker`)
- Tomcat9 설치
  > Web Server(Apache)로부터 넘어오는 요청을 받기 위해 8009 port 열어줌
- Connector 설치
  > Web Server(Apache)에 WAS 서버(Tomcat) 정보 저장
- App deploy
  > tomcat `/webapps` 폴더 내에 sample.war 배포 후 `localhost/sample`로 접속

<br><br>
## 2. Oracle Weblogic 설치 및 app deploy
<iframe width="560" height="315" src="https://www.youtube.com/embed/QPO1R8YKk7I" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### 과정
- Oracle에서 java & weblogic 설치
  > weblogic 실행 후 `localhost:7070/console`로 접속
- App deploy
  > `deployments` 탭에서 sample.war 파일 선택해 배포 후 `localhost:7070/sample`로 접속

<br><br>
## 3. Apache-Tomcat 연동 후 app deploy(Google Cloud Platform VM)
<iframe width="560" height="315" src="https://www.youtube.com/embed/CtuN9Czg4W8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### 과정
- Google Cloud에서 VM 인스턴스 생성
  > 8080 송수신 포트 방화벽 설정
- Apache2 설치
  > WAS 서버(Tomcat)로 넘길 요청 url을 설정해줌(JkMount `url 패턴` `요청을 넘겨줄 WAS 서버 worker`)
- Tomcat9 설치
  > Web Server(Apache)로부터 넘어오는 요청을 받기 위해 8009 port 열어줌
- Connector 설치
  > Web Server(Apache)에 WAS 서버(Tomcat) 정보 저장
- App deploy
  > tomcat `/webapps` 폴더 내에 sample.war 배포 후 `public IP/sample`로 접속
