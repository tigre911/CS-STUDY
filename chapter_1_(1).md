## **1\. 디자인 패턴**

디자인 패턴이란 프로그램을 설계할 때 발생했던 문제점들을 객체 간의 상호 관계 등을 이용하여 해결할 수 있도록 하나의 '규약' 형태로 만들어 놓은 것을 의미한다.

#### **1.1 싱글톤 패턴**

싱글톤 패턴(singleton patter)은 하나의 클래스에 오직 하나의 인스턴스\*만 가지는 패턴이다.

보통 데이터베이스 연결 모듈에 많이 사용한다.

\* 인스턴스 : 인스턴스는 일반적으로 실행중인 임의의 프로세소, 클래스의 현재 생성된 오브젝트(객체)를 가리킨다.

하나의 인스턴스를 만들어 놓고 해당 인스턴스를 다른 모듈들이 공유하며 사용하기 때문에 인스턴스를 생성할 때 드는 비용이 줄어드는 장점이 있다. 하지만 의존성이 높아진다는 단점이 있다.

자바에서의 싱글톤 패턴

```
/* Online Java Compiler and Editor */
class Singleton{
    private static class singleInstanceHodler{
        private static final Singleton INSTANCE = new Singleton();
    }
    public static synchronized Singleton getInstance(){
        return singleInstanceHodler.INSTANCE;
    }
}

public class HelloWorld{

     public static void main(String []args){
        Singleton a = Singleton.getInstance();
        Singleton b = Singleton.getInstance();
        System.out.println(a.hashCode());
        System.out.println(b.hashCode());
        if (a==b){
            System.out.println(true);
        }
     }
}

/*
실행 결과
705927765
705927765
true
*/
```

**\- 싱글톤 패턴의 단점**

싱글톤 패턴은 TDD(Test Driven Development)를 할 때 걸림돌이 된다. TDD를 할 때 단위 테스트를 주로 하는데, 단위 테스트는 테스트가 서로 **독립적**이어야 하며 테스트를 어떤 순서로든 실행할 수 있어야 한다.

그러나 싱글톤 패턴은 미리 생성된 하나의 인스턴스를 기반으로 구현하는 패턴이므로, 각 테스트마다 '독립적인' 인스턴스를 만들기가 어렵다.

**\- 의존성 주입**

또한, 싱글톤 패턴은 사용하기가 쉽고 굉장히 실용적이지만 모듈 간의 결합을 강하게 만들 수 있다는 단점이 있다.

이때 의존성 주입(DI, Dependency Injection)을 통해 모듈간의 결합을 조금 더 느슨하게 만들어 해결 할 수 있다.

의존성이란 종속성이라고도 하며 A가 B에 의존성이 있다는 것은 B의 변경사항에 대해 A 또한 변해야 한다는것을 의미.

[##_Image|kage@b8JgA2/btrMd7yWCNy/a8zxTsBkY77KG4lkV6B4G1/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":325,"style":"alignLeft","width":452,"height":245}_##]

앞의 그림처럼 메인 모듈이 '직접' 다른 하위 모듈에 대한 의존성을 주기보다는 중간에 의존성 주입자가 이 부분을 가로채 메인 모듈이 '간접'적으로 의존성을 주입하는 방식이다.

이를 통해 메인 모듈(상위 모듈)은 하위 모듈에 대해 의존성이 떨어지게 된다. 이를 '디커플링이 된다' 고도 한다.

[##_Image|kage@cBiiEb/btrMbAhW7Oa/0ZyYk3W0UWqSt7JilRnYT1/img.png|CDM|1.3|{"originWidth":886,"originHeight":520,"style":"floatLeft","width":296}_##]

**\- 의존성 주입의 장점**

모듈들을 쉽게 교체할 수 있는 구조가 되어 테스팅하기 쉽고 마이그레이션 하기도 수월하다.

\*마이그레이션 : 하나의 운영환경으로부터 더 나은 운영환경으로 옮아가는 과정을 뜻하는 정보통신 용어.

또한,  구현할 때 추상화 레이어를 넣고 이를 기반으로 구현체를 넣어 주기 때문에 애플리케이션 의존성 방향이 일관되고,  애플리케이션을 쉽게 추론할 수 있으며 모듈관의 관계들이 조금 더 명확해진다.

**\- 의존성 주입의 단점**

모듈들이 더욱더 분리되므로 클래스 수가 늘어나 복잡성이 증가될 수 있으며 약간의 런타임 패널티가 생기기도 한다.

**\- 의존성 주입 원칙**

의존성 주입은 "**상위 모듈은 하위 모듈에서 어떠한 것도 가져오지 않아야 한다.**" 또한, "**둘 다 추상화에 의존해야 하며, 이때 추상화는 세부 사항에 의존하지 말아야 한다.**" 라는 의존성 주입 원칙을 지켜야 한다.

#### **1.2 팩토리 패턴**

팩토리 패턴(factory patter)은 객체를 사용하는 코드에서 객체 생성 부분을 떼어내 추상화한 패턴이자 상속 관계에 있는 두 클래스에서 상위 클래스가 중요한 뼈대를 결정하고, 하위 클래스에서 객체 생성에 관한 구체적인 내용을 결정하는 패턴이다.

상위 클래스와 하위 클래스가 분리되기 때문에 느슨한 결합을 가지며 상위 클래스에서는 인스턴스 생성 방식에 대해 전혀 알 필요가 없기 때문에 더 많은 유연성을 갖게 된다. 그리고 객체 생성 로직이 따로 떼어져 있기 때문에 코드를 리팩터링 하더라도 한 곳만 고칠 수 있게 되어 유지 보수성이 증가된다.

예를 들어 라떼 레시피와 아메리카노 레시피, 우유 레시피라는 구체적인 내용이 들어 있는 하위 클래스가 상위 클래스인 공장에서 레시피를 토대로  커피우유를 생산하는 생산 공정을 생각하면 된다.

자바스크립트의 팩토리 패턴

자바스크립트에서 팩토리 패턴을 구현한다면 간단하게 new Object()로 구현할 수 있습니다.

```
const num = new Object(42)
const str = new Object('abc')

//constructor 메서드는 클래스의 인스턴스 객체를 생성하고 초기화하는 특별한 메서드입니다.
num.constructor.name; // Number
str.constructor.name; // String
```

숫자를 전달하거나 문자열을 전달함에 따라 다른 타입의 객체를 생성하는 것을 볼 수 있다.

즉, 전달받은 값에 따라 다른 객체를 생성하여 인스턴스의 타입 등을 정한다.

커피 팩토리를 기반으로 라떼 등을 생산하는 코드를 구축한 코드

```
class Latte{
    constructor(){
        this.name = "latte"
    }
}
class Espresso{
    constructor(){
        this.name = "Espresso"
    }
}

class LatteFactory{
    static createCoffee(){
        return new Latte()
    }
}
class EspressoFactory{
    static createCoffee(){
        return new Espresso()
    }
}
const factoryList = {LatteFactory, EspressoFactory}

class CoffeeFactory {
    static createCoffee(type){
        const factory = factoryList[type]
        return factory.createCoffee()
    }
}

const main = () => {
    //라떼 커피 주문
    const coffee = CoffeeFactory.createCoffee("LatteFactory")
    //커피 이름을 부른다.
    console.log(coffee.name)
}

main()

//출력 -> latte
```

CoffeeFactory 라는 상위 클래스가 중요한 뼈대(type)을 결정하고 하위 클래스의 LatteFactory가 구체적인 내용을 결정하고 있다.

참고로 이는 의존성 주입이라고도 볼 수 있다.

또한, CoffeeFactory를 보면 static으로 createCoffee() 정적 메서드를 정의한 것을 알 수 있다.

정적 메서드를 쓰면 클래스의 인스턴스 없이 호출이 가능하여 메모리를 절약 할 수 있고 개별 인스턴스에 묶이지 않으며 클래스 내의 함수를 정의할 수 있는 장점이 있다.

자바의 팩토리 패턴

```
abstract class Coffee { 
    public abstract int getPrice(); 
    
    @Override
    public String toString(){
        return "Hi this coffee is "+ this.getPrice();
    }
}

class CoffeeFactory { 
    public static Coffee getCoffee(String type, int price){
        if("Latte".equalsIgnoreCase(type)) return new Latte(price);
        else if("Americano".equalsIgnoreCase(type)) return new Americano(price);
        else{
            return new DefaultCoffee();
        } 
    }
}
class DefaultCoffee extends Coffee {
    private int price;

    public DefaultCoffee() {
        this.price = -1;
    }

    @Override
    public int getPrice() {
        return this.price;
    }
}
class Latte extends Coffee { 
    private int price; 
    
    public Latte(int price){
        this.price=price; 
    }
    @Override
    public int getPrice() {
        return this.price;
    } 
}
class Americano extends Coffee { 
    private int price; 
    
    public Americano(int price){
        this.price=price; 
    }
    @Override
    public int getPrice() {
        return this.price;
    } 
} 
public class HelloWorld{ 
     public static void main(String []args){ 
        Coffee latte = CoffeeFactory.getCoffee("Latte", 4000);
        Coffee ame = CoffeeFactory.getCoffee("Americano",3000); 
        System.out.println("Factory latte ::"+latte);
        System.out.println("Factory ame ::"+ame); 
     }
} 
/*
Factory latte ::Hi this coffee is 4000
Factory ame ::Hi this coffee is 3000
*/
```

문자열 비교 기반으로 로직이 구성됨을 볼 수 있는데, 이는 Enum 또는 Map을 이용하여 if 문을 쓰지 않고 매핑해서 할 수도 있다. 

1.3 전략 패턴

전략 패턴은 정책 패턴이라고도 하며, 객체의 행위를 바꾸고 싶은 경우 '직접' 수정하지 않고 전략이라고 부르는 '캡슐화한 알고리즘'을 컨텍스트 안에서 바꿔주면서 상호 교체가 가능하게 만드는 패턴이다.

[##_Image|kage@brbHzg/btrMkOrT2BU/3KsDcZKUH62xX4B1kzpo6K/img.png|CDM|1.3|{"originWidth":600,"originHeight":383,"style":"alignLeft","width":243}_##]

더보기

전략 패턴을 이루는 구성 요소는 다음과 같아요. 

[##_Image|kage@m7wAa/btrMjhvmbuO/LKAV99kquGEtilYZevgebK/img.png|CDM|1.3|{"originWidth":1398,"originHeight":491,"style":"alignCenter","width":769}_##]

전략 패턴의 구조

  **- 전략_(strategy)_** : 구체화된 여러 알고리즘들의 추상화로써, 변하는 부분을 담당

     **- 전략 콘크리트_(concrete strategy)_** : 여러 알고리즘의 실제 구현

  **- 전략 사용자_(context)_** : 전략을 사용하는 프로그램의 흐름으로, 변하지 않는 것

  **- 전략 제공자_(client)_** : 전략 사용자에게 실제 전략으로 사용할 전략 콘크리트 클래스를 주입하는 역할

보다시피 상황에 따라 다양한 알고리즘을 필요로 하는 경우 전략 패턴을 사용할 수 있어요. 

그러면 이런 발상을 코드로 옮기기 위해서는 어떻게 전략과 전략 콘크리트를 작성하는 게 좋을까요? 

바로 **인터페이스**와 해당 인터페이스를 구현한 **클래스**를 사용하는 것이에요!

인터페이스를 통해 **전략을 추상화** 시켜놓은 후, 적재 적소에 필요한 전략을 구현한 Class를 삽입하는 것이죠. 

**\*\*\* 전략 패턴 예시 \*\*\***

자, 이제 코드로 실제 구성 요소들이 어떻게 구현되는 지 살펴보아요. 

```
public interface ShuffleStrategy {
    List<Card> shuffle(final List<Card> cards);
}
    
public class RandomShuffleStrategy implements ShuffleStrategy {
    @Override
    public List<Card> shuffle(final List<Card> cards) {
        Collections.shuffle(cards);
        return cards;
    }
}
```

**전략_(strategy)_** 과 **전략 콘크리트****_(concrete strategy)_** 에요. 

위에서 언급했던 것 처럼, ShuffleStrategy라는 인터페이스를 만들어 Shuffle 이라는 전략을 추상화 시켰어요. 

이제 해당 인터페이스를 구현한 전략 콘크리트 클래스는, 각자 의도에 맞는 Shuffle 전략을 작성해요. 

RandomShuffleStrategy라는 클래스가 전략 콘크리트 클래스의 예시로, 

코드를 보면 매개변수로 넘겨받은 카드를 랜덤으로 섞어 반환하는 것을 볼 수 있어요. 

```
public static CardDeck make(final ShuffleStrategy shuffleStrategy) {
    final List<Card> shuffledCard = shuffleStrategy.shuffle(cards);
    return new CardDeck(shuffledCard);
}
```

**전략 사용자_(context)_** 에요. 

전략을 사용하는 프로그램의 흐름으로, 서로 다른 전략에 따른 코드의 변경이 필요 없어요. 

해당 context에서는 넘겨 받은 전략 콘크리트의 shuffle 메서드를 통해 cards를 섞어주게 되어요. 

ShuffleStrategy를 구현한 클래스는 shuffle 이라는 전략을 가지고 있다는 것을 보장하기 때문에, 

cards를 섞는 일은 전략 콘크리트 객체에게 위임할 수 있겠네요!

만일 전략 패턴이 아닌 방식으로 구현한다면 어땠을까요?

필요한 전략에 맞추어 행동하기 위해 if - else 등의 **분기문으로 구구절절** 전략들을 작성했을 거에요. 

과도한 if - else 문은 곧 메서드/객체가 **하나의 책임을 가진다는 것과 멀어진다**는 뜻이에요. 

전략 패턴을 사용해 객체 지향적인 코드 작성이 가능해 졌네요!

```
public void run() {
    final CardDeck cardDeck = CardDeckFactory.make(new RandomShuffleStrategy());
}
```

**전략 제공자_(client)_** 에요. 

여기서 전략 사용자에게 구체적인 전략 콘크리트 클래스를 주입해 줬던 것이였군요!

현재 코드에서는 바로 RandomShuffleStrategy의 객체를 생성하여 주입시켜줬지만, 

사용자의 요청에 따라 다른 전략을 사용해야 하는 경우, 

매번 다른 전략을 사용해 객체를 생성해야 하는 경우 등에서 전략 패턴의 유연함은 더 빛을 발할 거에요. 

**\*\*\* 전략 패턴의 장단점 \*\*\***

앞서 전략 패턴은 Behavioral 패턴 중에 하나로, 객체 간의 커뮤니케이션에 유연성을 부여한다고 했어요.

어떤가요? **객체 간 커뮤니케이션의 유연성**이 조금 느껴지시나요? 

마지막으로 전략 패턴의 장단점을 정리하며 포스팅 마무리 할게요. 

**\[장점\]**

  **- 전략 사용자(context)의 코드 변경 없이 새로운 전략을 추가 할 수 있다.**

      _- 이를 통해 if - else 분기를 제거할 수 있다._

      _- if - else 분기를 제거하면, 단일 책임 원칙을 준수하기 더 수월해진다._ 

  **- 확장에 유리한 코드를 작성할 수 있다.** 

      _- 새롭게 필요한 전략 콘크리트 클래스를 쉽게 만들 수 있다._ 

      _- 개방 폐쇄 원칙을 준수한 코드 작성이 가능하다._ 

  **- 런타임에 전략을 변경시킬 수 있다.** 

**\[단점\]**

  **- 어플리케이션에 들어가는 모든 전략을 알고 있어야 한다.** 

      _- 클래스로 분리한 각 전략들이 어느 상황에 사용되어야 할 지 알고 있어야 한다._

      _- 이 같은 특성이 어쩌면 유지보수를 더 힘들게 할 수도 있다._ 

  **\- 전략을 추상화한 인터페이스가 효율적이지 못할 수 있다.** 

      _- 어떤 전략 콘크리트 객체에서는 사용하지 않는 메서드들 역시 전략 인터페이스에 정의해 주어야 한다._ 

1.4 옵저버 패턴

옵저버 패턴은 주체가 어떤 객체의 상태 변화를 관찰하다가 상태 변화가 있을 때마다 메서드 등을 통해 옵저버 목록에 있는 옵저버 들에게 변화를 알려주는 디자인 패턴이다.

[##_Image|kage@bpMSY6/btrMjRpqlgb/shNRSLBX72WfgUhD0uZNYK/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":628,"style":"alignLeft","width":287}_##]

객체와 주체가 분리되어 있는 옵저버 패턴

여기서 주체란 객체의 상태 변화를 보고 있는 관찰자이며, 옵저버들이란 이 객체의 상태 변화에 따라 전달되는 메서드 등을 기반으로 '추가 변화 사항'이 생기는 객체들을 의미 한다.

---

[##_Image|kage@cqGwPz/btrMjWKZUmm/7fpYe1UCvbyqhnQ7oZaWHk/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":778,"style":"alignLeft","width":292,"height":379}_##]

객체와 주체가 합쳐진 옵저버 패턴

또한 위의 그림처럼 주체와 객체를 따로 두지 않고 상태가 변경되는 객체를 기반으로 구축하기도 한다.

옵저버 패턴을 활용한 서비스로는 트위터가 있다.

옵저버 패턴은 주로 이벤트 기반 시스템에 사용하며 MVC패턴에도 사용된다.

#### **1.5 프록시 패턴과 프록시 서버**

**\- 프록시 패턴**

프록시 패턴은 대상 객체에 접근하기 전 그 접근에 대한 흐름을 가로채 대상 객체 앞단의 인터페이스 역할을 하는 디자인 패턴이다.

[##_Image|kage@crleia/btrMvsXFDlH/3tOaGTTP0ECWtdabhrWre1/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":199,"style":"alignLeft","width":413,"height":137}_##]

이를 통해 객체의 속성, 변환 등을 보완하며 보안, 데이터 검증, 캐싱, 로깅에 사용한다.

이는 앞서 설명한 프록시 객체로 쓰이기도 하지만 프록시 서버로도 활용된다.

\*프록시 서버에서의 캐싱

캐시 안에 정보를 담아두고, 캐시 안에 있는 정보를 요구하는 요청에 대해 다시 원격 서버에 요청하지 않고 캐시 안에 있는 데이터를 활용하는 것을 말한다. 이를 통해 불필요하게 외부와 연결하지않기 때문에 트래픽을 줄일 수 있다는 장점이 있다.

**\- 프록시 서버**

프록시 서버는 서버와 클라이언트 사이에서 클라이언트가 자신을 통해 다른 네이트워크 서비스에 간접적으로 접속할 수 있게 해주는 컴퓨터 시스템이나 응용프로그램을 말한다.

#### **1.6 이터레이터 패턴**

이터레이터 패턴은 이터레이터를 사용하여 컬렉션의 요소들에 접근하는 디자인 패턴이다.

\* 이터레이터

iterate : 순환하다, 반복하다

반복적으로 하나하나 꺼내어 처리 가능한 컬렉션이나 sequence 들을 이터레이터 객체라고한다. 

ex ) List, Set, Map, Queue 등을 말한다

[##_Image|kage@mc9bB/btrMA4t0H0g/41pYQWPhNfmo06DJT1ky8K/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":450,"style":"alignLeft","width":396,"height":297}_##]

이를 통해 순회할 수 있는 여러가지 자료형의 구조와는 상관없이 이터레이터라는 하나의 인터페이스로 순회가 가능하다.

#### **1.7 노출 모듈 패턴**

노출모듈 패턴은 즉시 실행 함수를 통해 private, public 같은 접근 제어자를 만드는 패턴을 말한다. 자바스크립트는 private나 public 같은 접근제어자가 존재하지 않고 전역 범위에서 스크립트가 실행된다. 그렇기 때문에 노출모듈 패턴을 통해 private와 public 접근 제어자를 구현하기도 한다.

```
const pukuba = (() => {
    const a = 1
    const b = () => 2
    const public = {
        c : 2, 
        d : () => 3
    }
    return public 
})() 
console.log(pukuba)
console.log(pukuba.a)
// { c: 2, d: [Function: d] }
// undefined
```

a와 b는 다른 모듈에서 사용할 수 없는 변수나 함수이며 private 범위를 가진다. c와 d는 다른 모듈에서 사용할 수 있는 변수나 함수이며 public 범위를 가진다.

참고로 앞서 설명한 노출모듈 패턴을 기반으로 만든 자바스크립트 모듈 방식으로는 CJS모듈 방식이 있다.

> \- public  
> 클래스에 정의된 함수에서 접근 가능하며 자식  클래스와 외부 클래스에서 접근 가능한 범위  
> \- protected  
> 클래스에서 정의된 함수에서 접근 가능, 자식 클래스에서 접근 가능하지만 외부 클래스에서 접근 불가능한 범위  
> \- private  
> 클래스에 정의된 함수에서 접근 가능하지만 자식 클래스와 외부 클래스에서 접근 불가능한 범위  
> \- 즉시 실행 함수  
> 함수를 정의하자마자 바로 호출하는 함수, 초기화 코드, 라이브러리 내 전역 변수의 충돌 방지 등에 사용한다.

#### **1.8 MVC 패턴**

모델(Model), 뷰(View), 컨트롤러(Controller)로 이루어진 디자인 패턴이다.

[##_Image|kage@cxqsls/btrMyiNlXNE/UfjuT5L8IjKFQ1PBVtWYU0/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":296,"style":"alignLeft"}_##]

애플리케이션의 구성 요소를 세 가지 역할로 구분하여 개발 프로세스에서 각각의 구성 요소에만 집중해서 개발 할 수 있다. 재사용성과 확장성이 용이하다는 장점이 있고, 애플리케이션이 복잡해질수록 모델과 뷰의 관계가 복잡해지는 단점이 있다.

**\- 모델**

모델은 애플리 케이션의 데이터인 데이터베이스, 상수, 변수 등을 뜻한다. 

예시로 사각형 모양의 박스 안에 글자가 들어 있다면 그 사각형 모양의 박스 위치 정보, 글자 내용, 글자 위치, 글자 포맷에 관한 정보를 모두 가지고 있어야한다. 뷰에서 데이터를 생성하거나 수정하면 컨트롤러를 통해 모델을 생성하거나 갱신한다.

**\- 뷰**

뷰는 inputbox, checkbox, textarea 등 사용자 인터페이스 요소를 나타낸다. 즉, 모델을 기반으로 사용자가 볼 수 있는 화면을 뜻한다. 모델이 가지고 있는 정보를 따로 저장하지 않아야 하며 단순히 사각형 모양 등 화면에 표시하는 정보만 가지고 있어햐 한다. 또한 변경이 일어나면 이를 컨트롤러에 전달해야한다.

**\- 컨트롤러**

컨트롤러는 하나 이상의 모델과 하나 이상의 뷰를 잇는 다리 역할을 하며 이벤트 등 메인 로직을 담당한다. 또한, 모델과 뷰의 생명주기도 관리하며, 모델이나 뷰의 변경 통지를 받으면 이를 해석하여 각각의 구성 용소에 해당 내용에 대해 알려준다.

**1.9 MVP 패턴**

MVP 패턴은 MVC 패턴으로 파생되었으며 MVC 에서 C에 해당하는 컨트롤러가 프레젠터(presenter)로 교체된 패턴이다.

[##_Image|kage@VfSqu/btrMxUMDN8m/7eYGLWUkP3ePDc28qFE0DK/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":284,"style":"alignLeft","width":549,"height":260}_##]

뷰와 프레젠터는 일대일 관계이기 때문에 MVC보다 더 강한 결함을 지닌 디자인 패턴이라고 볼 수 있다.

**1.10 MVVM 패턴**

MVVM 패턴은 MVC의 C에 해당하는 컨트롤러가 뷰모델(vicw model)로 바뀐 패턴이다.

[##_Image|kage@N5aBH/btrMzQCKUJN/bKXz3WzeQBO6fcpEl80Ss1/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":162,"style":"alignLeft"}_##]

여기서 뷰모델은 뷰를 더 추상화한 개층이며 mvvm 패턴은 mvc 패턴과는 다르게 커맨드와 데이터 바인딩을 가지는 것이 특징이다. 뷰와 뷰모델 사이의 양방향 데이터 바인딩을 지원하며 UI를 별도의 코드 수정 없이 재사용할 수 있고 단위 테스팅하기 쉽다는 장점이 있다.

MVVM 패턴의 예: 뷰(Vue.js)는 반응형이 특징인 프론트엔드 프레임 워크이다.

함수를 사용하지 않고 값 대입만으로 변수가 변경되며 양방향 바인딩, html을 토대로 컴포넌트를 구축할 수 있다는 점이 특징이다. 재사용 가능한 컴포넌트 기반으로 UI를 구축할 수 있다.

[##_ImageGrid|kage@cxqsls/btrMyiNlXNE/UfjuT5L8IjKFQ1PBVtWYU0/img.jpg,kage@VfSqu/btrMxUMDN8m/7eYGLWUkP3ePDc28qFE0DK/img.jpg,kage@N5aBH/btrMzQCKUJN/bKXz3WzeQBO6fcpEl80Ss1/img.jpg|data-origin-width="600" data-origin-height="296" data-is-animation="false" width="468" height="231" style="width: 25.2427%; margin-right: 10px;" data-widthpercent="25.84" id="kEditorPhotosEditingImage-11",width="406" data-origin-width="600" data-origin-height="284" data-is-animation="false" height="192" data-widthpercent="26.94" style="width: 26.3093%; margin-right: 10px;" id="kEditorPhotosEditingImage-12",data-origin-width="600" data-origin-height="162" data-is-animation="false" width="426" style="width: 46.1224%;" data-widthpercent="47.22" id="kEditorPhotosEditingImage-13"|_##]
