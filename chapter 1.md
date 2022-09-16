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

[##_Image|kage@m7wAa/btrMjhvmbuO/LKAV99kquGEtilYZevgebK/img.png|CDM|1.3|{"originWidth":1280,"originHeight":449,"style":"alignCenter","width":769}_##]

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

