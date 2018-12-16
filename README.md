# 키스토어 만들기(임시 인증서 만들기)
https://gist.github.com/keesun/f93f0b83d7232137283450e08a53c4fd\

# HTTPS 설정하기
https://docs.spring.io/spring-boot/docs/2.1.1.RELEASE/reference/htmlsingle/#howto-configure-ssl

기본적으로 하나의 connection만 사용할 수 있어서
위 내용으로 https를 설정하게 되면 http로 접근할 수 없게 된다.

http로 접근할 수 있게 하기 위해서는 새로운 connection을 추가해 줘야 한다. 

# HTTP 커넥터 설정
https://github.com/spring-projects/spring-boot/tree/v2.0.3.RELEASE/spring-boot-samples/spring-boot-sample-tomcat-multi-connectors

# Http2 설정
https://docs.spring.io/spring-boot/docs/current/reference/html/howto-embedded-web-servers.html#howto-configure-http2
- SSL은 기본적으로 적용되어 있어야 함
- application.properties > server.http2.enabled=true 추가
- WAS마다 추가 설정이 다름
    - tomcat: 9버전부터 추가 설정이 필요없음
        - DK9와 Tomcat 9+ 추천
          그 이하는 아래 링크 참고
          https://docs.spring.io/spring-boot/docs/current/reference/html/howto-embedded-web-servers.html#howto-configure-http2-tomcat
- curl -I -k --http2 https://localhost:8443/hello          
          
