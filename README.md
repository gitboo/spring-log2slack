# spring-log2slack

## About
- @Log2Slack 애노테이션만 선언하면 로그 메세지를 슬랙으로 받을 수 있습니다.

## Required
- JDK 1.8+
- 스프링 프레임워크를 사용해야 합니다.
- Slack Incoming WebHooks
- 계속해서 발전해 나아가려는 프로젝트 입니다 적극적인 Pull Request 환영합니다 :) 

## How to use it
**아래 Configuration 파일 작성**
```java
@Configuration
public class Log2SlackConfiguration extends Log2SlackAppConfiguration {

}
```

**Slack Incoming WebHooks 설정**
![Image of WebHooks](/images/1.png)

**application.properties or application.yml 작성**
```yaml
# application.properties 예제
slack.web-hook-url=slack webHookUrl 주소
slack.channel=slack channel 이름
```

```yaml
# application.yml 예제
slack:
  web-hook-url: slack webHookUrl 주소
  channel: slack channel 이름
```

로그 메세지를 받고 싶은 메소드에 **@Log2Slack 애노테이션을 선언**합니다.
```java
@Log2Slack
public List<Member> getMembers() {
    List<Member> blackPink = new ArrayList<>();
    blackPink.add(new Member("지수", "치츄"));
    blackPink.add(new Member("제니", "젠득이"));
    blackPink.add(new Member("로제", "파스타"));
    blackPink.add(new Member("리사", "날라리사, 요리사, 조리사.."));
    return blackPink;
}
```

## Example Source
아래 project 는 spring-log2slack 을 사용한 example project 입니다.
- [log2slack-example](https://github.com/LawrenceAhn/log2slack-example)

## License
spring-log2slack is MIT License.