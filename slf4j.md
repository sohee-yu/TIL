// SLF4J

오랜만에 사용해본 SLF4J
단순히 system.out.println 을 사용해서 로그를 찍어볼 수 있지만, 메모리를 많이 사용하고 ( 배포시 주석/삭제 필수!)
굳이 깔려 있는 SLF4J를 사용하지 않을 이유는 없었음.

사용방법이야 간단해서 '로그찍는것' 으로만 생각하고 정확하게 찾아 보지 않았는데, 이번기회에 조금 찾아보았다.

Full Name : Simple Logging Facade for Java
공식홈 : http://www.slf4j.org/

단순히 자바 파일에서
=>

import org.slf4j.Logger;
import org.slf4j.LoggerFactory;
/// 생략 ///
Logger logger = LoggerFactory.getLogger(this.getClass());
/// 생략 ///
log.info("blah blah log"+ ...)

이런 식으로 사용 하면 된다. (나는 디버그용으로 로그를 찍어볼때 사용하고, 테스트 후 주석처리하거나 삭제한다.)

물론, 처음 자바 프로젝트 생성시 패키지 매니저를 통하여 설치하거나,

Maven, gradle 무슨 방식을 사용하던 단순히 의존성 dependency 추가해서 사용하면된다.
(예전 소스가 아닌경우 slf4j 으로 검색하는 경우 이미 추가되어있을 확률 높음)

결론적으로 SLF4J 특징

1. 빠름
2. 메모리아낌
3. 업데이트 및 호환성 괜춘
4. 사용하기 쉬움

정도만 알면 될것 같은데......
더욱 궁금해질 미래의 나에게
https://enai.tistory.com/36 블로그에 설명 잘되어 있다.
물론 공식홈을 찾아본다거나 해보던가... ¯\_(ツ)\_/¯


...
- 럴수럴수 이럴 수!!!
- 이거 올린지 얼마나 됐다구 보안 취약점 이슈가 생겼다.
- Log4j의 ldap JNDI 파서를 통한 원격 코드 실행(RCE - Remote Code Execution) 취약점 때문에 문제가 발생
- JAVA를 사용하는 사람들이면 많이 사용하고, 서버 사이드 솔루션에서도 많이 사용하고 있어서 더욱 큰 사건인듯.
- 조치 방법 : log4j 를 2.15.0 이상으로 올리는 것 (JAVA 8 이상 필요)
- 내가 담당하는 프로젝트는 logback 사용이라서 다행쓰 ^^
