# design-pattern
## 디자인패턴
분석 단계에서는 절대로 쓰면 안되고, 설계 구현 부분에서 사용하도록 하자
정답은 아니지만, 복잡한 문제들을 패턴으로 문제를 풀 수 있다.
단순한 게 복잡해질 수 도 있다.

### 디자인 패턴 정의
### 생성패턴

1. 싱글톤 패턴
    * 클래스 인스턴스가 하나만 생성된다는 것을 보장. 
    * 사용하는 경우
        * Utility클래스
        * 특정 Channel로 들어오고 나오는 기능 (예: 프린트)
2. AbstractFactory패턴
    * 문제 제시 시나리오
        * 은행에서 영역을 확장하면서 해외 고객이 점차 늘어남.. 각 국가에 맞는 객체를 생성하고 싶음
        * 클라이언트가 어떤 객체를 생성할지 결정하는 것이 아니라 Factory클래스가 객체 생성을 결정해서 Client측에 전달해준다. 책임을 위임 한다.
    * 적용
        * 객체가 생성되거나 구성 또는 표현되는 방식과 무고나하게 시스템 독립적으로 만들고자 할때
        * 여러 제품군 중 하나를 선택해서 시스템을 설정하고 한번 구성한 제품을 다른것으로 대체할 수 있을 때
        * 제품에 대한 클래스 라리브러리를 제공하고 그들의 구현이 아닌 인터페이스를 노출시키고 싶을 때
    * 참여자
        * AbstractFoctory : 개념적 제품에 대한 객체를 생성하는 연산으로 인터페이스를 정의
        * ConcreteFactory : 구체적인 제품에 대한 객체를 생성하는 연산을 구현한다.
        * AbstractProduct : 개념적 제품 객체에 대한 인터페이스를 정의한다.
        * ConcreteProduct : 구체적으로 팩토리가 생성할 객체를 정의한다.
    * 결과
        * 구체적인 클래스를 분리한다.
        * 제품군을 쉽게 대처할 수 있어야 한다.
        * 제품 사이의 일관성을 증진시킨다.
        * 새로운 종류의 제품을 제공하기 ㅇ렵다.
3. Prototype 패턴
      * 브랜드에 상관 없이 스펙을 미리 정의해놓은 TV를 찍어내는 클래스를 미리 만들어 놓고 동적 오브젝트 생성으로 만든다. clone활용.
      * 주소는 다르지만, 같은 모양의 인스턴스가 생김.
      * 전혀 다른 인스턴스 제어가 가능하다.
4. Builder 패턴

### 구조패턴

1. Composite 패턴
      - 사용하는 경우 : 
          - 부분- 집합 관계의 계층도를 표현해야 할 때
          - 복합 객체와 단일 객체 간의 사용 방법에 차이를 두고 싶지 않을 때
          - 계층관계의 요소를 쉽게 추가할 필요가 있을 때
      - 공통적인 스트럭츠를 뽑아내서 추상화 한다. 
      - 예 : 부서의 하위 부서가 얼마나 있는지 모른다. Department가 Party와 Employee와 연관이 있는 형태.
      - Company -> Party-상속[ department -> Department.. -> Employee -> Employee.. ]
      - 새롭게 PartyTime같은 클래스가 새로 생성되어도 기존의 소스는 건들지 않고 추가해서 사용이 가능해진다.
      - 또 사용하는 경우 : Word의 경우.. 텍스트, 이미지, 그래프 등을 엘리먼트의 하위로 가지고, 하위를 가질 수 있는 구조로 정의해놓으면 유용하게 쓸 수 있게 된다.
2. Proxy 패턴
      - 앞단에서 모든 것을 초기화 해놓지 않고, 필요할 때 초기화해서 사용
      - 문제가 되는 지점
           - 전체 클래스 중 성능이 저하되는 부분 식별.
           - 문제가 되는 클래스를 사용하는 클래스의 패턴을 분석한다. 
           - 객체의 생성 비용이 많이 소요되는 경우.... 
      - PrinterProxy의 역할
           - Printable의 요청에 대응 가능. 인터페이싱 역할만 해준다. Printer의 대리자의 역할.
      - PrinterProxy에게 지금 사용할 수 있는 프린터 리스트가 뭐야? 라고 물어보고 선택한 뒤에 Initialize해서 사용할 준비를 한다.
      - PrinterProxy가 내부 변수로 Printer를 가지고 있다.
      - LazyLoading의 개념
      - Wrapping하기에 좋은 패턴
3. Bridge 패턴
      - 잘 안씀
4. Decorator 패턴
      - 동적으로 객체에 서비스를 추가할 수 있다.
      - 서비스를 언제든지 제거할 수 있어야 한다.
5. Adaptor 패턴
      - Wapper할 수 있는 클래스
      - 상속을 이용한 방법, 위임을 이용한 방법 두 가지
           - 상속은 확장하기 어려울 수 있음. 위임은 확장하기 좋음
6. Facade 패턴 (아주 중요!!)
      - (찾아보자...)
7. Flyweight 패턴
      - Pool안에서만 객체에 Generate가 된다.
      - Pool의 개념은 DB Connection Pool과 굉장히 유사하다.


### 행위패턴
1. Chain of Responsibility 패턴
      - 문제 제시
         - 실제 고객의 해결되지 않은 문제들을 접수하고 있고, 해결되면 없어지는 형태의 상황
      - 솔루션 찾기
         - 책임 할당 
         - 행위적 결합도 감소
      - 방법
         - 추상화 찾기
         - 연결고리 구현하기(next: Resolver로 연결)
      - 장점
         - 핸들러 하나에 조건문이 들어가는 것을 막을 수 있음
         - 의도적으로 클래스를 나눌 수 있음
         - 핸들러는 Configure만 하면 되고, 새로운 클래스가 추가되면 핸들러에만 수정해주면 된다.
      - 적용
         - 요청을 처리할 객체 집합을 동적으로 정의할 때
2. Strategy 패턴
      - 문제 제시
         - 무역회사에서 주문관리하고 싶음. 나라마다 관세가 달라서 관세에 관련된 클래스가 생성됨. 나라가 많아진다면..? 수시로 변경도 가능한 상황.
      - 변수만 다르고 행위는 비슷한 역할을 하는 클래스들이 생겨남(환율 계산, 관세 계산)
      - TaxCalulator, CurrencyTransformer로 행위에 대해서 추상화 수행.
      - 나라별로 클래스를 쪼개는 것이 아니라 관세 별로 행위를 쪼개는 것이다.
      - 나라가 늘어나더라도 행위가 늘어나는 것이 아니라서 클래스가 새로 생겨나지 않는다.
3. Template Method 패턴
      - 자판기에서 커피, 레몬차를 판매한다.
      - 추상화 또는 일반화 하기
         - 커피랑 레몬차를 끓이는 부분에서 완전히 유사한 로직이 들어가 있다.
         - prepareRecipe() 추상화 하기. 행위 자체가 추상화 될 수 있다.
      - Hook메서드
         - 하위 클래스에서 필요한 것들을 정의
      - 참여자 
         - AbstractClass : 서브클래스들이 구현해야하는 알고리즘의 기본 연산을 정의한다.
         - ConcreteClass : 서브클래스마다 다른 알고리즘 처리 단계를 구현한다.
4. Command 패턴
5. Interpreter 패턴
6. Iterator 패턴
7. Mediator 패턴
8. Observer 패턴
      - 일대다 관련성을 갖고 있는 객체에서 유용
      - 하나의 객체의 상태가 변경되면 다른 객체에게 알릴때 유용
