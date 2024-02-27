# deficient-content
처음 들어본 내용이거나 추가적인 공부가 필요한 것들에 대하여

- PWA
- 캐싱 전략 (Cache First VS Network First)
- MPA (Multi Page Application)
- 페이지 네이션
- 뷰 포트
- Tree Shaking
- SOLID
- CSRF
- 전략 패턴
- [옵저버  패턴](https://github.com/JunhOpportunity/cs/tree/main/DesignPattern)

## PWA
### 특징

- 모바일 기기의 홈 화면에 추가하여 앱처럼 접근할 수 있음
- 네이티브 앱에 버금가는 편리한 접근성과 사용자 경험 제공
- 애플리케이션의 아이콘, 이름, 시작 화면 등을 정의할 수 있는 웹 앱 매니페스트 파일 사용
- 카메라, GPS, 가속도계 등 모바일 기기의 다양한 하드웨어 기능을 활용할 수 있음
- 최신 PWA는 블루투스 장치 연결, NFC 태그를 활용하여 다양한 액션 가능

### 장점

> 접근성 및 호환성, 오프라인 접근성, 비용 및 시간 절약
> 
- 모든 브라우저 및 장치에서 접근 가능
- SEO를 통한 가시성 향상
- 별도의 앱 스토어 다운로드 없이 URL 접근으로 사용자 편의성 증대
- 서비스 워커를 통해 네트워크 연결 없이도 콘텐츠 접근 가능
- 하나의 코드 베이스로 다양한 플랫폼에서 실행
- 빠른 설치와 즉각적인 업데이트 제공

### 단점

> 기능 제한, 사용자 인식 부족, 브라우저 호환성
> 
- 네이티브 앱에 비해 일부 고급 기능 및 하드웨어 접근 제한
- 플랫폼별 최적화 기능 부족
- PWA에 대한 일반 사용자의 인식 및 이해도가 낮음
- 전통적인 앱 다운로드 경험과의 차이로 인한 초기 수용도 저하
- 모든 브라우저에서 PWA 기능의 일관된 지원 부족
- 일부 기능은 특정 브라우저에서만 제한적으로 사용 가능

### 어디에 써야 할까

- ⭕ 뉴스 사이트, 블로그, 전자상거래 플랫폼 등 다양한 장치에서 접근이 필요한 서비스
- ❌ 고급 그래픽 및 복잡한 하드웨어 기능이 필요한 게임 및 전문적 애플리케이션

## 캐싱 전략 (Cache First VS Network First)
### cache First
네트워크 요청을 보내기 전에 캐시를 먼저 확인하고 캐시가 존재한다면 해당 캐시를 사용한다.
빠른 로딩에 적합한 전략이다.

### Network First
네트워크 요청을 먼저 보내고 요청이 실패했을 경우 캐시를 사용한다.
항상 최신 콘텐츠를 제공할 때 유용한 전략이다.

## SOLID 원칙

### 단일 책임 원칙(SRP)

함수를 엄청나게 쪼개면 되는 게 아니라 각 소프트웨어 모듈은 변경의 이유가 하나여야만 한다.

- 시스템은 그것을 설계한 조직의 커뮤니케이션 구조를 반영한다.
- 설계 단계에서 부터 컴포넌트를 어떻게 관리할지에 대한 논의가 반드시 필요하다.
- 
1. 개방-폐쇄 원칙 : 기존 코드를 수정하기보다는 반드시 새로운 코드를 추가하는 방식으로 시스템의 행위를 변경할 수 있도록 설계해야 한다.
2. 의존성 역전 원칙 :

### 정리

Class란 상태와 액션을 결합하고 캡슐화하는 문법적인 도구이다.

우리가 흔히 별로라고 생각하는 도구들 조차도 코드를 작성하는 원리와 목적에 맞게만 사용한다면 좋은 결과를 낼 수 있다. 도구가 문제가 아니라 그걸 사용하는 사람의 잘못이 더 크다.

따라서 정답은 상황에 맞는 도구를 사용해야 한다는 것이다.

### SOLID

좋은 소프트웨어 시스템은 클린 코드로부터 시작한다. 좋은 벽돌을 사용하지 않으면 빌딩의 아키텍처가 좋고 나쁨은 그리 큰 의미가 없는 것과 같다. 반대로 좋은 벽돌을 사용하더라도 빌딩의 아키텍처를 엉망으로 만들 수 있다. 그래서 **좋은 벽돌로 좋은 아키텍처를 정의하는 원칙이 필요한데, 그게 바로 SOLID다.**

많은 회사의 프론트엔드 코드들이 고민 없이 순전히 단순 노동을 기반으로 만들어지고 유지보수 되고 있다.

대다수의 애플리케이션에서 유지보수성이 재사용성보다 훨씬 중요하다.

> SOLID : 객체 지향적 코드 설계의 원칙들
> 
1. **SRP : 단일 책임 원칙**
각 소프트웨어 모듈은 변경의 이유가 단 하나여야만 한다.
(하나의 함수가 하나의 동작만 하도록 설계하라)
⇒ 잘 격리되어 독립적으로 개발 가능한 컴포넌트 단위로 시스템을 분할해야 한다.
시스템은 그것을 설계한 조직의 커뮤니케이션 구조를 반영한다 - 로버트 C. 마틴
따라서 컴포넌트가 SRP를 위반하며 마구잡이로 거대해지고 있다면 그 개발 조직은 커뮤니케이션이 정상적으로 이뤄지지 않고 있을 확률이 높다.
따라서 설계 단계에서 부터 컴포넌트를 어떻게 관리할지에 대한 논의가 반드시 필요하다.

2. OCP : 개방-폐쇄 원칙
기존 코드를 수정하기보다는 반드시 새로운 코드를 추가하는 방식으로 시스템을 변경할 수 있도록 설계해야 한다.
⇒ 확장에는 열려 있고, 수정에는 닫혀 있도록 한다.
컴파운드 컴포넌트를 사용하면 이를 구현할 수 있는데, 요구 사항이 하나씩 추가될 때마다 props도 하나씩 추가되며 데이터를 받아오지 말고 다른 컴포넌트를 보여주도록 한다.
    
    ```tsx
    <Card>
    	<Card.Title>foo</Card.Title>
    	<Card.Content>bar</Card.Content>
    	{user
    		? <Card.CommentsWithAuth comments={comments} />
    		: <Card.CommentsWithAnonymous comments={comments} />
    	}
    </Card>
    ```
    
3. 🤔 LSP : 리스코프 치환 원칙
상호 대체 가능한 컴포넌트를 이용해 소프트웨어 시스템을 만들 수 있으려면 컴포넌트는 반드시 서로 치환 가능해야 한다는 계약을 지켜야 한다.
⇒ 내부 구현이 변경되더라도 외부 인터페이스와 행동은 변하지 않아야 한다.
4. ISP : 인터페이스 분리 원칙
5. DIP : 의존성 역전 원칙
고수준 정책을 구현하는 코드는 저수준 세부사항을 구현하는 코드에 절대로 의존해서는 안된다.
⇒ 필요한 정보를 구체적으로 정의하지 말고, 외부에서 추상의 형태로 주입받아 사용하라.
(구체적이며 변동성이 크다면 절대로 그 이름을 언급하지 말라)
만약 로그인 로직이 너무 구체적이라면 확장성 측면에서 문제가 있으므로 외부에서 주입받도록 변경하면 데이터의 요청 방식이 변경되거나 인증 방식이 변경되어도 그것을 요청하는 로직을 전부 바꿀 필요 없이 요청 함수만 바꿔주면 되기 때문이다.
    
    ```jsx
    // 원본
    const user = await mysql.query(`SELECT * FROM user WHERE email = ?`, [
      email,
    ]);
    
    // DIP
    const user = await userRepository.getUserByEmail(email);
    ```
    

### 실전 SOLID

IoC(Inversion of Control : 제어의 역전) : 외부로 제어권을 넘기는 것 (어떠한 구현을 최대한 나중으로 미루는 것)
- 작성한 코드가 프레임워크에 넘겨져 처리하는 것
- 고차 함수

```jsx
// IoC 미적용
const iterateArray = () => { 
	for (const a of arr) {
	  // ...
	}
}

// IoC 적용
arr.map((a) => { ... }) 
```

기존 코드에서 비즈니스 로직을 분리하고 추상화를 적용하려 함수와 컴포넌트를 나눌 수록 점차 코드의 깊이가 깊어지고 컴포넌트의 결합도가 높아져 오히려 가독성과 유지보수성을 해치는 경험을 했다면 이는 제어권의 역전을 제대로 적용하지 못했기 때문이라고 볼 수 있다.
