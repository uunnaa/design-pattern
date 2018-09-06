# design-pattern
#디자인패턴
분석 단계에서는 절대로 쓰면 안되고, 설계 구현 부분에서 사용하도록 하자
정답은 아니지만, 복잡한 문제들을 패턴으로 문제를 풀 수 있다.
단순한 게 복잡해질 수 도 있다.

11. 디자인 패턴 정의
2. 생성패턴
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
    5. Composite 패턴
          - 사용하는 경우 : 
              - 부분- 집합 관계의 계층도를 표현해야 할 때
              - 복합 객체와 단일 객체 간의 사용 방법에 차이를 두고 싶지 않을 때
              - 계층관계의 요소를 쉽게 추가할 필요가 있을 때
          - 공통적인 스트럭츠를 뽑아내서 추상화 한다. 
          - 예 : 부서의 하위 부서가 얼마나 있는지 모른다. Department가 Party와 Employee와 연관이 있는 형태.
          - Company -> Party-상속[ department -> Department.. -> Employee -> Employee.. ]
          - 새롭게 PartyTime같은 클래스가 새로 생성되어도 기존의 소스는 건들지 않고 추가해서 사용이 가능해진다.
          - 또 사용하는 경우 : Word의 경우.. 텍스트, 이미지, 그래프 등을 엘리먼트의 하위로 가지고, 하위를 가질 수 있는 구조로 정의해놓으면 유용하게 쓸 수 있게 된다.
      
          

3. 구조패턴
4. 행위패턴
