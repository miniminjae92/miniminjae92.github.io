---
layout: post
title: "우아한테크코스 프리코스과정 1,2주차 통합 회고"
---

# 1주차 회고

# 시작하며
---

## How to start?
우연한 기회에 우아한테크코스 입학설명회를 시청하게 됐어요.

왜 성장하고 싶은가요? 남들을 따라서 하고 있나요?
생각에 대한 생각을 자주하시나요?

평소 가지고 있던 몰입, 메타인지, 집단지성, 명시적 논리적 글쓰기라는 키워드들에 꽂혀있던 저에게 설명회는 큰 파문으로 찾아왔어요.

"그래! 프리코스는 누구나 참여 가능한데 한 번 도전해보자"란 생각으로 아무것도 모르지만 뛰어 들었답니다.

우아한테크코스의 모토가 정말 마음에 들었어요.
특히 뛰어난 사람들과 같이 협업을 할 기회가 생긴다는 것이 너무 탐이 났죠.
시간이 지날수록 기대하고 욕심이 나는 것이 저뿐이 아니겠죠?
그러면 처음해보는 1주차 회고를 시작해 보겠습니다.
## 1주차를 진행하며

### 개발 과정 요구 사항
과제 진행, 기능, 프로그래밍 요구 사항 세 가지 모두 충족하기
기능 구현 전 기능 목록을 만들기
기능 단위로 커밋하는 방식으로 진행하기
기능 요구 사항에 기재되지 않은 내용은 스스로 판단하여 구현하기
- Git
- IntellJ
- Java JDK 21
- README.md 마크 다운 다루기
- AngularJS Git Commit Message Conventions
- 자바 코드 컨벤션 (Java Style Guide)

1주차 과제가 진행되면서 필요한 사항들을 준비하게 되었어요.
Git 을 다루는 방법을 배우고 Github 계정을 만들었어요.	
가장 도움이 많이 된 사이트를 첨부할게요. [[Link]](https://learngitbranching.js.org/?locale=ko)

우테코에서 제공해주는 제출가이드와 각종 안내문(링크)들을 보면서 하나씩 배워갔어요. (도움이 정말 많이 됩니다. 👍)
IntellJ 설치 및 적응, Java JDK 21 로 설정
우선 JDK 가 무엇인 지 23 버전으로 나오는 것을 고치고
git command 를 배운 것을 적용해보고
README 작성을 도대체 어떻게 하는거지?!! 라면서 우선 해보고
커밋을 하고 취소하고 넘어져보고 하면서 어찌저찌 과제를 시작하게 되었어요.
디스코드에서 함께 나누기와 토론, 구글에 많은 정보들이 많은 도움이 된 것 같아요.

특히 바로 시작을 안하고 `객체지향의사실과오해` 책을 읽으면서 객체지향에 사랑에 빠진 게 된 것 같아요. (강추입니다! 책 추천 받아요 ☺️☺️)

낯설었지만 설렘을 가지고 배우다보니 점점 익숙해진 것 같아요.
아직도 많이 부족하지만 점점 좋아지겠죠?

### 과제 기능 요구 사항
>입력한 문자열에서 숫자를 추출하여 더하는 계산기를 구현한다.
- 쉼표(,) 또는 콜론(:)을 구분자로 가지는 문자열을 전달하는 경우 구분자를 기준으로 분리한 각 숫자의 합을 반환한다.
- 예: "" => 0, "1,2" => 3, "1,2,3" => 6, "1,2:3" => 6
- 앞의 기본 구분자(쉼표, 콜론) 외에 커스텀 구분자를 지정할 수 있다. 커스텀 구분자는 문자열 앞부분의 "//"와 "\n" 사이에 위치하는 문자를 커스텀 구분자로 사용한다.
- 예를 들어 "//;\n1;2;3"과 같이 값을 입력할 경우 커스텀 구분자는 세미콜론(;)이며, 결과 값은 6이 반환되어야 한다.
- 사용자가 잘못된 값을 입력할 경우 IllegalArgumentException을 발생시킨 후 애플리케이션은 종료되어야 한다.

`객체지향사실과오해`를 읽고 책임, 협력, 역할을 생각하면서 시작을 하려 했어요.
하지만 생각과 구현은 처음에는 갭이 컸어요.
자바라는 언어가 처음이고 너무 완벽하게 하려고 실수를 하면 안된다는 생각이 있었던 것 같아요.
프리코스 과정은 원래라는 건 지워버리고 부딪힘에 망설임이 없어야 한다고 생각해요. (모두 화이팅입니다!🫡)

# 본론
무엇을 해야할 지 몰라서 과제에 적힌 것을 실천하는 것에 집중을 했어요.

**과제 진행, 기능, 프로그래밍 요구 사항 세 가지 모두 충족하기**
3가지 부분들을 꼼꼼히 읽어보면서 하나씩 했어요.
그리고 책을 바탕으로 먼저 객체 메세지 흐름을 만들어봤어요.

>객체 메세지 흐름
Main -> InputHandler : 문자열 입력 받아줘
InputHandler -> Main : 입력 문자열 받아줘
Main -> Parser : 문자열 파싱해줘
Parser -> Main : 파싱된 문자열 배열 받아줘
Main -> Validator : 양수 검증해줘
Validator -> Main : 검증된 양수 배열 받아줘
Main -> Calculator : 양수 배열 합해줘
Calculator -> Main : 계산 결과 받아줘
Main -> Printer : 계산 결과 출력해줘

이것을 바탕으로 기능 목록도 작성을 하고 프로그래밍에 들어갔습니다.

>기능 목록 List
Application(main)
InputHandler
Parser
Validator
Calculator
Printer

![](https://velog.velcdn.com/images/dan_d/post/3e4df9f5-9502-466f-bbab-69962a902f8c/image.png)

---
### 1주차에서 작성한 코드


```java
package calculator;

public class Application {
    public static void main(String[] args) {
        InputHandler inputHandler = new InputHandler();
        String userInput = inputHandler.getInput();

        Parser parser = new Parser();
        String[] parsedTokens = parser.parseInput(userInput);

        PositiveNumberValidator validator = new PositiveNumberValidator();
        int[] validatedNumbers = validator.validateNumber(parsedTokens);

        SumCalculator calculator = new SumCalculator();
        int result = calculator.calculateSum(validatedNumbers);

        Printer printer = new Printer();
        printer.printResult(result);
    }
}
```
MVC 패턴에 대해서 모르는 상태에서 작성을 했어요.
빈 공백을 넣어도 되는 지 클래스 선언, 메소드 사용 등 전부 새로 배워가면서 시작했어요.
객체지향이 아니라 절차지향으로 작성이 된 것 같아요. 🥲

```java
package calculator;

import camp.nextstep.edu.missionutils.Console;

public class InputHandler {
    public String getInput() {
        System.out.println("덧셈할 문자열을 입력해 주세요.");
        return Console.readLine();
    }
}
```
화면에 처음 출력을 하면서부터 재미를 느끼기 시작했어요.

```java
package calculator;

public class Printer {
    public void printResult(int result) {
        System.out.println("결과 : " + result);
    }
}
```
최대한 단일 책임을 주려고 설계에 많은 시간을 들였어요.

```
package calculator;

import java.util.ArrayList;
import java.util.List;

public class Parser {
    //기본 구분자, 참조/내용 변경 불가능
    private final List<String> defaultDelimiters = List.of(",",":");
    //커스텀 구분자, 참조 변경 불가능
    private final List<String> customDelimiters = new ArrayList<>();

    public String[] parseInput(String input) {
        if (input.startsWith("//")){
            input = extractCustomDelimiter(input);
            String regex = String.join("|", defaultDelimiters) + "|" + String.join("|", customDelimiters);
            return input.split(regex);
        } else{
            String regex = String.join("|", defaultDelimiters);
            return input.split(regex);
        }
    }
    private String extractCustomDelimiter(String input) {
        int delimiterEndIndex = input.indexOf("\\n");

        if (delimiterEndIndex == -1)
            throw new IllegalArgumentException("Invalid delimiter: " + input);

        String customDelimiter = input.substring(2, delimiterEndIndex);

        if (!customDelimiters.contains(customDelimiter)){
            customDelimiters.add(customDelimiter);
        }

        return input.substring(delimiterEndIndex+2);
    }
}
```
private, final, 네이밍이 너무 어려웠어요.
파이썬을 조금 배워둔 것이 도움이 많이 되었어요.

```java
package calculator;

public class PositiveNumberValidator {
    public int[] validateNumber(String[] tokens) {
        // 빈 문자열 or 숫자가 없는 경우 예외 처리
        if (tokens == null || tokens.length == 1 && tokens[0].isEmpty()) {
            return new int[]{0};
        }

        int[] validatedNumbers = new int[tokens.length];

        for (int i = 0; i < tokens.length; i++) {
            try {
                int number = Integer.parseInt(tokens[i]);
                if (number > 0) {
                    validatedNumbers[i] = number;
                } else {
                    throw new IllegalArgumentException("The number must be positive: " + tokens[i]);
                }
            } catch (NumberFormatException e) {
                throw new IllegalArgumentException("Invalid number format: " + tokens[i], e);
            }
        }
        return validatedNumbers;
    }
}
```
여러 메서드를 배우고 예외를 처리하는 경험을 했어요.

```java
package calculator;

public class SumCalculator {
    public int calculateSum(int[] numbers) {
        int sum = 0;
        for (int number : numbers) {
            sum += number;
        }
        return sum;
    }
}
```

```
package calculator;

import camp.nextstep.edu.missionutils.test.NsTest;
import org.junit.jupiter.api.Test;

import static camp.nextstep.edu.missionutils.test.Assertions.assertSimpleTest;
import static org.assertj.core.api.Assertions.assertThat;
import static org.assertj.core.api.Assertions.assertThatThrownBy;

class ApplicationTest extends NsTest {
    @Test
    void 커스텀_구분자_사용() {
        assertSimpleTest(() -> {
            run("//;\\n1");
            assertThat(output()).contains("결과 : 1");
        });
    }

    @Test
    void 예외_테스트() {
        assertSimpleTest(() ->
            assertThatThrownBy(() -> runException("-1,2,3"))
                .isInstanceOf(IllegalArgumentException.class)
        );
    }

    @Override
    public void runMain() {
        Application.main(new String[]{});
    }
}
```
./gradlew clean test 를 돌리면서 수정을 할 수 있었어요.
이때 테스트에 대해서 중요성을 느끼게 됐어요.

### 예외 처리
- 입력된 문자열에서 숫자를 추출하여 더하는 계산기가 요구 사항이기때문에 숫자가 없거나 빈 문자열일 경우 0으로 가정한다.
- 사용자가 잘못된 값을 입력한 경우 IllegaArgumentException을 발생시킨 후 애플리케이션 종료
- 구분자는 잘못된 입력에서 제외로 본다.
- 음수의 경우
- 커스텀 구분자의 /// or \n\n 경우
- 숫자가 없는 경우, 커스텀구분자를 //x\n 이 있을 때 x 가 여러 개의 특수문자일 경우 하나로 볼지 여러 개로 볼지 결정.

당시 처음 예외 사항에 대해서 생각해봐서 미흡했어요.
아직도 가장 어려운 부분이 이 예외 사항인 것 같아요.
요구 사항과 예외 사항을 만족하느 것이 중요한 것 같아요.

---
## 1주차 끝나자마자 기록했던 부분
- README 작성에 대해서 공부가 필요하고 Markdown 형식에 익숙해져야한다는 것을 느꼈습니다.
- Git, Github 을 이용한 개발을 진행하면서 Mac, Window 다양한 플랫폼과 기기에서 편리하게 할 수 있는 것을 느꼈고 협업시에는 적극 활용해야겠다고 느꼈습니다.
- 새로운 IDE 및 언어에 겁을 먹지말고 적극적으로 다가감으로써 빠르게 적응할 수 있어야한다고 생각하게 되었습니다.
- 기능 목록 하나씩 구현을 하면서 테스트와 커밋에 대해서 미흡함을 느꼈습니다, 더욱 복잡한 개발을 할 때에 이런식으로 하면 어려움이 생길 것이라고 느꼈습니다.
- 객체지향의 사실과 오해를 읽으면서 객체의 메세지와 책임을 생각하며 기능 목록을 만들어보고 싶어 시간을 많이 투자를 했습니다, 다만 추상적으로 실제로 만드는 부분에서 많이 경험을 해봐야겠다고 느꼈습니다.
- 생각한 것을 구현하는데에 있어 기본 형식과 Method에 대한 공부가 부족하여 시간이 많이 지체되었습니다.
- 출력: 출력 : 정확한 요구사항 검토가 필요한 것을 느꼈습니다.
Validator, Calculator, Printer, ErrorHandler 를 기능 목록에 넣어두고 실제 구현에서는 급하고 낯설단 이유로 그대로 진행을 안했습니다, 계획대로 리팩토링하면서 본래 의도대로 진행하고 다음 과제부턴 좀 더 신경을 쓰도록 해야겠습니다.
- README 수정, git commit 등 제출해야한다는 생각에 실패를 피할려고 하는 모습이 있었고 그로인해 시간이 많이 소요되었습니다, 지금은 배우는 단계이므로 조금 더 거침없이 부딪혀가는 모습을 가지고 프리코스에 임해야겠다고 느꼈습니다.
- Markdown 들여쓰기가 원하는대로 나오질 않아 커밋을 여러 번 진행하게 되었고 그것들을 합치기 위해서 rebase, squash, push --force 를 처음 사용해봤습니다, 개인 과제라서 괜찮은 행동인 것 같지만 여러 방면으로 무엇을 조심하고 어떻게 하면 좋은지에 대해서 검색을 통해서 공부를 해야겠다고 이번 기회에 느꼈습니다. 이번 프리코스에서 느낀점같은 회고는 README 말고 다른 곳에 해야하는지에 대해선 1주차 프리코스가 끝나고 다른 동료들을 보면서 깨달아야겠습니다.
- ErrorHandler 클래스를 만들다가 전체적으로 꼬임이 발생해서 에러핸들러는 기능 목록에서 지웠다. 현재 지식이 부족하여 발생한 것으로 생각된다. 자바 책과 여러 지식을 쌓으면서 다시 회고를 통해 돌아봐야겠다. 또한 생각해보니 메인을 통한 중앙집중식으로 프로그램을 만든 것 같다는 생각이 들었다. 그래서 인풋핸들러가 파서에게 파서가 검증기, 검증기가 계산기 등 객체의 협력 구조로 바꿀려고 생각을 했다. 하지만 의존성에 대해서 아직 지식이 미비하여 무엇이 더 의존성이 낮고 여러모로 좋은지에 대해서 정확하게 모르겠어서 지금의 로직을 지키고 이것또한 회고를 통해서 꼭 다시 돌이켜 볼 예정이다.
- 클래스 인스턴스를 메인 밑에 함께 형성할 지 로직의 순서대로 형성할 지에 대해서도 고민을 하다가 위와 같은 이유로 유지를 하였다. 한편으로는 프로그램이 커지고 DI를 하게된다면 모으는 것이 보기에 좋겠단 생각을 하였다.

---
# 마무리하며

## 1차 공통 피드백
>1주 차 미션의 학습 목표는 개발 환경과 프로그래밍 언어에 익숙해지는 것이었습니다.

- 요구 사항을 정확하게 준수한다
- 기본적인 Git 명령어를 숙지한다
- Git으로 관리할 자원을 고려한다
- 커밋 메시지를 의미 있게 작성한다
- 오류를 찾을 때 출력 함수 대신 디버거를 사용한다
- 이름을 통해 의도를 드러낸다
- 축약하지 않는다
- 공백도 코딩 컨벤션이다
- 스페이스와 탭을 혼용하지 않는다
- 의미 없는 주석을 달지 않는다
- 코드 포매팅을 사용한다
- Java에서 제공하는 API를 적극 활용한다
- 배열 대신 컬렉션을 사용한다

개발 환경과 프로그래밍 언어에 익숙해지는 것이 학습 목표였어요.
요구 사항을 따르기 위해서 노력을 하다보면 자연스럽게 목표를 이룰 수 있게 과정이 잘 짜여진 것 같아요.
1차 공통 피드백에 있는 내용들이 지금 봐도 매우 중요한 부분들이라고 느껴지네요.

>일주일 동안에 많은 것을 할 수 있었고 가장 큰 것은 **자기 주도적으로 학습을 얼마든지 할 수 있다는 용기** 인 것 같아요.

결과를 떠나서 프리코스 적극 추천합니다.

# 2주차 회고

# 서론

---
## 2차 공통 피드백을 보며

<details>
  <summary> 자세히 보기 </summary>
  
2주 차 미션의 학습 목표는 함수 분리와 테스트 도구의 사용법을 익혀 보는 것이었습니다. 새로운 개념을 학습하고 미션에 적용하는 과정이 쉽지 않았을 텐데요. 특히 다른 사람과 비교하다 보면 조바심이 생길 수 있습니다. 그렇지만 다른 사람과의 비교보다는 어제의 나와 비교하며 자신의 속도에 맞추어서 마무리하는 것을 목표로 삼아 보세요. 이번 경험이 좋은 프로그래머로 성장하는 중요한 역량을 키우는 과정임을 기억해 주세요.

입학 설명회에서 설명하였듯이 메타인지를 위한 최고의 도구 중 하나는 회고입니다. 회고를 통해 우리는 학습과 경험을 그냥 지나치지 않고 반성하고 개선할 수 있습니다. 아직 중간 회고를 작성하지 않았거나 회고를 공유하고 싶다면 프리코스 커뮤니티의 회고 채널에서 공유해 주세요. 한 주 한 주 지나면서 성장하는 여러분의 모습을 기대하겠습니다. 우아한테크코스 크루들이 쓴 내용이 궁금하다면 이 링크에서 회고록을 확인할 수 있습니다.

단위 테스트와 같은 용어가 아직 낯설 수 있지만, 작은 기능부터 테스트를 작성하는 연습을 차근차근 해 나가면  빠르게 성장하실 수 있습니다. 1주 차 피드백에서 제공된 문자열 덧셈 계산기 피드백 강의에 단위 테스트를 작성하는 내용이 있으니 이를 참고해 주세요.

이번 주도 여러분에게 의미 있는 시간이 되기를 바랍니다.

공통 피드백
README.md를 상세히 작성한다
미션 저장소의 README.md는 소스 코드 이전에 프로젝트의 개요를 소개하는 문서다. 이 문서를 통해 해당 프로젝트가 어떤 프로젝트인지, 주요 기능이 무엇인지 소개할 수 있다. 효과적으로 작성하기 위해 마크다운 문법을 검색하여 학습하고, 이를 활용해 README.md를 작성해 본다.
기능 목록을 재검토한다
기능 목록을 작성할 때 클래스 설계와 구현, 메서드 설계와 구현 같은 상세한 내용은 포함하지 않는다. 클래스 이름이나 메서드 시그니처, 반환값 등은 언제든지 변경될 수 있기 때문이다. 구현해야 할 기능 목록을 중심으로 작성하되, 정상적인 경우뿐만 아니라 예외 상황도 함께 정리한다. 예외 상황은 시작 단계에서 파악하기 어려우므로, 기능을 구현하면서 지속적으로 업데이트하는 것이 좋다.
기능 목록을 업데이트한다
README.md 파일의 기능 목록은 구현 과정에서 변경될 수 있다. 시작부터 모든 기능을 완벽하게 정리해야 한다는 부담을 갖기보다는, 기능을 구현하면서 문서를 지속적으로 업데이트하는 것을 목표로 한다. 이를 통해 죽은 문서가 아닌 살아있는 문서로 유지될 수 있도록 노력해 보자.
값을 하드 코딩하지 않는다
코드 내에서 문자열이나 숫자 값을 하드 코딩하지 않는다. 대신 상수(static final)를 정의하고 의미 있는 이름을 부여하여 해당 값이 어떤 역할을 하는지 명확히 드러낸다. 구글에 "java 상수"등의 키워드로 검색하여 상수 구현 방법을 학습하고 코드에 적용해 본다.
구현 순서도 코딩 컨벤션이다
클래스는 상수, 멤버 변수, 생성자, 메서드 순으로 작성한다. 

class A {
    상수(static final) 또는 클래스 변수
    인스턴스 변수
    생성자
    메서드
}

변수 이름에 자료형은 사용하지 않는다
변수 이름에 자료형, 자료 구조 등을 포함하지 않는다. 변수 이름은 의미를 명확히 드러낼 수 있도록 하고, 자료형은 코드 작성 시점에 자연스럽게 이해될 수 있도록 한다.

String carNameList = Console.readLine();
String[] arrayString = carNameList.split(",");

한 메서드가 한 가지 기능만 담당하게 한다
함수의 길이가 길어진다면 여러 기능을 한 함수에서 처리하려는 신호일 가능성이 높다. 예를 들어, 안내 문구 출력, 사용자 입력 처리, 유효값 검증 등의 작업을 한 함수에 모두 포함하는 대신, 이를 각기 다른 함수로 분리해 본다.

public List<String> userInput() {
    System.out.println("경주할 자동차 이름을 입력하세요(이름은 쉼표(,)를 기준으로 구분).");
    String userInput = Console.readLine().trim();
    String[] splittedName = userInput.split(",");
    for (int index = 0; index < splittedName.length; index++) {
        if (splittedName.length < 1 || splittedName.length > 5) {
            throw new IllegalArgumentException("[ERROR] 자동차 이름은 1자 이상 5자 이하만 가능합니다.");
        }
    }
    return Arrays.asList(splittedName);
}

메서드가 한 가지 기능을 하는지 확인하는 기준을 세운다
여러 메서드에서 중복되는 코드가 있다면 이를 별도 메서드로 분리하는 것을 고려한다. 메서드의 길이가 길어지면 여러 기능을 포함하고 있을 가능성이 커지므로, 15라인이 넘지 않도록 구현하면 의식적으로 메서드를 분리하는 연습을 할 수 있다.
테스트를 작성하는 이유에 대해 본인의 경험을 토대로 정리해본다
테스트를 작성하면 기능의 정확성을 점검함을 넘어 코드의 즉각적인 피드백을 받을 수 있다. 테스트 작성 과정을 통해 구현한 기능의 문제를 빠르게 발견할 수 있을 뿐만 아니라, 코드의 구조와 의도를 명확히 이해하는 데도 도움을 받을 수 있다. 학습 도구로도 활용할 수 있는데, 수 많은 테스트의 장점 중 본인이 가장 공감하는 작성 이유를 작성해 본다.

학습테스트를 통해 JUnit 학습하기.pdf
처음부터 큰 단위의 테스트를 만들지 않는다
테스트의 핵심 목적 중 하나는 코드에 대해 빠르고 자주 피드백을 받는 것이다. 처음부터 큰 단위의 테스트를 작성하게 되면, 작성한 코드의 문제를 발견하기까지 시간이 오래 걸린다. 따라서 문제를 작게 나누어 핵심 기능부터 작게 테스트를 만들어 가는 것이 효과적이다.

큰 단위의 테스트
자동차 경주 게임을 시작하여, 사용자가 이름과 진행 횟수를 입력하고, 게임을 진행한 후 결과를 확인한다.

작은 단위의 테스트
무작위 값이 4 이상이면 자동차가 전진한다.
무작위 값이 3 이하이면 자동차가 전진하지 않는다.
  
</details>

>2주 차 미션의 학습 목표는 **함수 분리**와 **테스트 도구의 사용법**을 익혀 보는 것이었습니다. 새로운 개념을 학습하고 미션에 적용하는 과정이 쉽지 않았을 텐데요. 특히 **다른 사람과 비교하다 보면 조바심이 생길 수 있습니다. 그렇지만 다른 사람과의 비교보다는 어제의 나와 비교하며 자신의 속도에 맞추어서 마무리하는 것을 목표로 삼아 보세요.** 이번 경험이 좋은 프로그래머로 성장하는 중요한 역량을 키우는 과정임을 기억해 주세요.
  
어찌 이렇게 내 마음을 알았는지 깜짝 놀랐고 내가 항상 나에게 하는 말을 적어주셔서 더 감명 깊었다.
힘들 때나 조급해질 때마다 스스로에게 하는 말인데..
좋다! 마무리하는 것을 목표로 좋은 경험을 하는 것을 목표로 달려보자.
아래의 공통 피드백을 보면서 2주차 회고를 시작하려 한다.
    
- README.md를 상세히 작성한다
- 기능 목록을 재검토한다
  구현해야 할 기능 목록을 중심으로 작성하되, 정상적인 경우뿐만 아니라 예외 상황도 함께 정리한다.
- 기능 목록을 업데이트한다.
- 값을 하드 코딩하지 않는다
- 구현 순서도 코딩 컨벤션이다
  클래스는 상수, 멤버 변수, 생성자, 메서드 순으로 작성한다. 
- 변수 이름에 자료형은 사용하지 않는다
- 한 메서드가 한 가지 기능만 담당하게 한다
- 메서드가 한 가지 기능을 하는지 확인하는 기준을 세운다
- 테스트를 작성하는 이유에 대해 본인의 경험을 토대로 정리해본다
- 처음부터 큰 단위의 테스트를 만들지 않는다
  
1주차에 비해서 노력을 한 결과인지 코드 리뷰를 통한 발전때문인지 공통피드백에 있는 부분들을 상당히 신경을 쓴 편이다.
그럼에도 불구하고 부족한 부분들이 꽤나 있다.
하드 코딩 미흡, 변수 이름에 자료형을 사용하고 싶어하는 마음이 있었다.
메서드가 한 가지 기능을 하는지 확인하는 기준 세우기.
처음부터 큰 단위의 테스트를 만들지 말기!
1, 2주차 미션을 하면서 가장 어려워하는 부분이 바로 기능을 나눠서 작은 테스트와 구현을 조화롭게 사용하는 것이다.
앞으로는 작은 테스트와 구현, 커밋을 실천해보자.
  
# 본론
  
---
## 문제 요구 사항

초간단 자동차 경주 게임을 구현한다.

- 주어진 횟수 동안 n대의 자동차는 전진 또는 멈출 수 있다.
- 각 자동차에 이름을 부여할 수 있다. 전진하는 자동차를 출력할 때 자동차 이름을 같이 출력한다.
- 자동차 이름은 쉼표(,)를 기준으로 구분하며 이름은 5자 이하만 가능하다.
- 사용자는 몇 번의 이동을 할 것인지를 입력할 수 있어야 한다.
- 전진하는 조건은 0에서 9 사이에서 무작위 값을 구한 후 무작위 값이 4 이상일 경우이다.
- 자동차 경주 게임을 완료한 후 누가 우승했는지를 알려준다. 우승자는 한 명 이상일 수 있다.
- 우승자가 여러 명일 경우 쉼표(,)를 이용하여 구분한다.
- 사용자가 잘못된 값을 입력할 경우 `IllegalArgumentException`을 발생시킨 후 애플리케이션은 종료되어야 한다.

### **입출력 요구 사항**

### **입력**

- 경주할 자동차 이름(이름은 쉼표(,) 기준으로 구분)

```
pobi,woni,jun

```

- 시도할 횟수

```
5

```

### **출력**

- 차수별 실행 결과

```
pobi : --
woni : ----
jun : ---

```

- 단독 우승자 안내 문구

```
최종 우승자 : pobi

```

- 공동 우승자 안내 문구

```
최종 우승자 : pobi, jun

```

### **실행 결과 예시**

```
경주할 자동차 이름을 입력하세요.(이름은 쉼표(,) 기준으로 구분)
pobi,woni,jun
시도할 횟수는 몇 회인가요?
5

실행 결과
pobi : -
woni :
jun : -

pobi : --
woni : -
jun : --

pobi : ---
woni : --
jun : ---

pobi : ----
woni : ---
jun : ----

pobi : -----
woni : ----
jun : -----

최종 우승자 : pobi, jun

```

## 진행 과정
  
지난 미션에서 시작하기에 앞서 시간이 너무 지체된 경험이 있었다.
앞으로도 마주칠 문제들을 어떻게 하면 빠르게 파악하고 기능 목록을 작성할 수 있을까? 에 대한 고민을 가지고 있었다.
1주차 미션을 끝나고 코드 리뷰를 하면서 MVC 패턴에 대해서 알게 되었다.
그래서 나도 아키텍처 설계에 대해서 생각하고 나만의 정리를 하였다.
  
MVC 가 무엇일까?
Model, View, Controller 구나
각자가 뜻하는 바는 무엇이지?
코드 리뷰를 하면서 도메인과 서비스도 봤는데 그건 무엇일까?
모델과 도메인이 다른건가? 컨트롤러와 서비스가 다른걸까?
나의 아키텍처는 우선 어떤 방식으로 하고싶니?
이러한 사고 과정을 거쳐 다음과 같이 정해졌다.

![](https://velog.velcdn.com/images/dan_d/post/4b91c0e2-f22a-4fc8-81f7-b8d51709eff6/image.png)
  
Application -> Controller
View <- Controller -> Service -> Domain
Util, Config

이러한 형태로 구조를 최종 설계를 하였다.
  
기능 목록 작성에 대해서도 1차 미션 때 책에서 읽은 내용을 바탕으로 적용하려 했다.
처음에는 "관점을 나누어서 해야지" 라고 생각을 했다.
큰 틀은 개념(도메인)관점에서 생각하여 객체들을 정하고
명세(책임 주도 설계)관점에서 메세지들을 정리하여 기능 목록을 작성을 하려 했다.
과제가 시작되었고 절차에 맞춰서 진행해보았지만 생각처럼 진행이 매끄럽진 않았다.
좀 더 명시적인 방법이 필요했던 것 같아서 방법론에 대해서 정리를 하였다.

### 2차 수정안
1. 핵심 기능 분석 및 객체 도출 : 무엇을 해야 하는가? 프로그램의 핵심 기능을 파악, 이를 수행하기 위한 객체를 구상
2. 객체의 책임 할당 : 각 객체는 어떤 책임을 가져야 하는가? 각 객체가 자율적이고 독립적인 역할을 가질 수 있도록 책임 할당
3. 객체 간 협력 정의 : 객체들이 서로 어떻게 소통할 것인가? 협력하는 방식 (메서드 호출, 데이터 전달 등)
4. 의존성 주입(DI) 설계 : 어떻게 객체 간 결합도를 낮출 수 있을까?
5. 팩토리 클래스 구성 : 객체 생성을 한 곳에서 관리하면 어떨까?
6. 구현 및 테스트 : 이제 각 객체가 제대로 동작하는지 테스트해보자.

기능파악 -> 역할할당 -> 협력정의 -> DI 및 팩토리설계 -> 구현 및 테스트

### 구현 및 테스트 상세 단계
1. 클래스별 구현 : 각 클래스가 설계된 대로 잘 동작하는지 확인하며 코드를 작성해야 해, 단일 책임 원칙 준수
2. 단위 테스트 작성 및 수행 : 각 클래스가 개별적으로 잘 동작하는지 확인해야 해
  ex) Domain 객체에 대한 Test
3. 객체 간 통합 테스트 : 객체들끼리 협력할 때도 잘 동작하는지 검증해야 해
  ex) Service 에 대한 Test
4. UI와의 통합 테스트 : 사용자에게 보여질 결과도 올바르게 나오는지 확인해야 해
  ex) View 에 대한 Test
5. 예외 및 엣지 케이스 테스트 : 모든 상황에 잘 대응하도록 예외 상황도 꼼꼼히 테스트해야 해
6. 최종 통합 테스트 및 리팩토링 : 전체 기능이 제대로 작동하는지 확인하고, 코드 개선이 필요하면 리팩토링하자
  
>2차 수정안을 위와 같이 사고의 흐름을 정해두고 흐름이 끊겨도 확인하며 절차를 진행했다.
도움이 된 것 같은데 회고를 하면서 확인한 결과 전체적인 과정을 미션이나 다른 문제들을 해결하면서 보완해야할 것 같다.
결론적으로는 큰 틀을 잡아놓고서 시작하는 것은 초보자인 나에게 네비게이션과 같이 좋은 효과를 보여준 것 같다.
어느정도 몸에 체득이 될 때까지는 이렇게 절차를 작성하는 것도 좋은 것 같다고 생각한다.

### RacingCar Code
  
```java
  public static GameController createGameController() {
  InputView inputView = new InputView();
  OutputView outputView = new OutputView();

  GameBoard gameBoard = new GameBoard();
  RaceJudge raceJudge = new RaceJudge();

  GameService gameService = new GameService(gameBoard, raceJudge);

  return new GameController(inputView, outputView, gameService);
  }
```
>의존성 주입을 하고 계속해서 의존성에 대해서 생각하다보니 누가 누구에게 의존을 하는지가 점점 보이기 시작했다.
그러면서 그렇다면 생성하고 주입하는 것을 한 곳에서 할 순 없을까? 란 생각으로 이런 설계를 하게 되었다.
이것이 좋은 것인지 나쁜 것인지는 아직까지 객관적으로는 모르지만 주관적으로 편했다.
그렇기 때문에 다음 미션에도 사용할 예정이다.

```java
private void playGame() {
	for (int i = 0; i < totalRounds; i++) {  
```
변수 i 에 대해서 round 같은 이름은 어떤가에 대해서 리뷰를 들었다.
좋은 생각이라 들면서도 정말 필요한가에 고민을 아직 하는 중이다.

```java
public void move() {
    int randomValue = RandomNumberGenerator.generate(RANDOM_MIN, RANDOM_MAX);
```
이 부분에 대해서 랜덤 값을 내부에 받는 것보다 외부에서 받는 것에 대한 고민을 구현하는 나도 했었고 지적도 받았다.
랜덤 값에 대해서는 외부에서 받는 것이 테스트하기에 좋을 것 같다는 판단이 든다.
                                        
```java
    public void initializeGame(List<String> carNames) {
        List<Car> cars = carNames.stream()
                .map(Car::new)
                .toList();
        gameBoard.setupCars(cars);                                    

```
스트림에 대해서 노션에 간단히 정리를 해보고 처음 사용을 해봤다.
  
- 배열이나 컬렉션의 요소들을 순차적으로 처리하거나 병렬 처리 가능
- Java 8에서 도입된 데이터 처리 추상화
- 메서드 체이닝 방식, 지연 연산 방식 ( 필요한 때만 데이터 처리 불필요한 중간 결과 생성 안함)
- 데이터가 배열(int[], Stirng[]) → Arrays.stream(), List, Set→ 바로.stream()
- map.keySet().stream(), map.values().stream(), map.entrySet().stream()
forEach 와 같이 많이 적용해보면서 장단점, 어떠할 때가 적시적소에 사용하기 용이한지에 대해 앞으로 배워나가야 한다.

이 외에도
- 정규식 추가 공부 및 Pattern, matcher 첫 사용
- isEmpty, isBlank의 차이, strip 메소드 알게 됨
- Message, values 상수화 사용
- 메서드 호출 순서를 놓침
- @parameterizedtest 에 대한 부분
- No newline at a end of file!! ~~(일부러 지웠던 마지막 공백라인이...컴퓨터 입장을 다시 생각해보는 계기가 됐다.)~~

2주차에서 많은 것을 배울 수 있었다.
코드 리뷰 최고 👍
## 성찰
  
### 디버깅과 테스트
설계한대로 구현을 해나가며 기능 별 커밋에 신경을 썼다.
다만 테스트에 대해서는 생각을 정리를 안한 결과인지 이번 미션에서도 미흡한 부분이 컸고 숙제를 하듯이 구현을 끝낸 후에 했다.
지금 돌이켜보면 가장 부끄럽고 후회가 되는 점이다.
아직까지 디버깅보다 런을, 테스트보다 구현을
프리코스에서 요구하는 점들은 다 이유가 있다.
이유에 대해서 깊이 생각을 해봤다.
내 생각은 디버깅은 문제의 원인을 파악하는데 장점이 있는 것 같다.
그리고 테스트를 먼저 작성하는 것은 코드의 신뢰성을 높이고 명확한 요구사항 반영에 대한 장점이 있는 것 같다.
3주차에 잘 적용을 해봐야겠다.
  
### 코드 리뷰
이제 2번째 하는 코드 리뷰지만 처음과 별다른 차이없이 어려웠다
깃이나 커밋 등 여러가지들은 차이가 느껴지는데 왜 코드리뷰는 어려울까 생각을 해봤다
1. 자바 기본 문법 및 메소드 지식 부족
2. 편한 것만 하려는 성향
어떤 코드는 술술 읽히고 어떤 사람의 코드는 의식의 흐름이 따라가질 못한다.
코드를 읽으면서 그 사람의 사고를 느낄 수 있는 것 같다는 생각을 했다.
세상에는 다양한 사람들이 많고 역지사지의 중요성을 살아가면서 느낀다.
코드 리뷰를 하면서 이러한 경험을 할 수 있는 것을 처음 알았고 상당히 힘들었다.
나와 비슷한 경우는 쉽게 읽히지만 다른 경우나 모르는 경우 어려워서 1주차 코드 리뷰에서는 대충 이런 느낌인 것만 알면 넘어갔다.
마치 내가 아는 것 처럼...
그렇게 힘든 길을 피한 결과 2주차 코드 리뷰를 할 때에도 다른 부분들보다 성장이 느렸던 것 같다.
그래서 이번엔 정면 돌파를 하기로 했고 며칠을 코드리뷰에 사용을 했다.
~~(로또 미션 얼른 해야하는데...벌써 목요일이라고오!!)~~
설명회에서 말한 **내가 모르는 것을 아는 것**이 왜 중요한지 다시 한 번 느꼈다.
그래서 빠르게 3주차 미션을 시작도 해야하지만 미뤄두고 코드리뷰에 집중을 했다. 🥲
그 결과 다른 분의 코드지만 마치 내 코드처럼 술술 읽히는 성과를 거둔 것 같다.
더불어 모르는 용법에 대해서도 재밌게 공부할 수 있었다.
앞으로 코드만 있으면 무엇이든 가능하겠다는 무서운 생각도 들긴 했다.

# 마무리
---
## 아쉬운 점
기억에 남는 것은
1. README 체크박스 만들어두고 체크를 하지 않았다...
2. 경주 게임인데 참가자가 한명일 경우를 생각 못한 것

## 다음 목표
- 체력이 곧 정신력이다. "틈날 때마다 강한 체력을 기르자!"
- 몰입, 메타인지, 집단지성, 설득(논리적글쓰기) 기존 목표를 꾸준히 각인하고 실천하기!


>마지막으로 스스로에게 하고 싶은 말이자 여러분에게도 도움이 되고자 한 마디 남기고 이번 회고를 마치겠다.  
"Do what is hard, and your life will be easy. Do what is easy and your life will be hard."
  
---
