## Ambient Declarations

[왜 타입스크립트인가?](../../why-typescript.md) 에서 언급했듯이:

> 타입스크립트 설계의 주 목적 중 하나는 자바스크립트 라이브러리들을 타입스크립트에서 안전하고 쉽게 사용할 수 있게 하는 것입니다. 타입스크립트에서 *declaration* 이 그 역할을 합니다.

Ambient declarations 는 *유명한 자바스크립트 라이브러리들을 쉽게 사용할 수 있게* 하고, *자바스크립트/커피스크립트/자바스크립트로 컴파일 될 수 있는 다른 언어 로 만들어진 라이브러리를 타입스크립트로 점진적으로 마이그레이션 할 수 있게* 합니다.

*써드 파티 자바스크립트 코드* 의 ambient declaration 을 공부하는 것은 *당신의* 타입스크립트 코드베이스에 를 위한 연습이 될 수 있습니다. 이것이 우리가 Ambient Declarations 를 일찍 소개하는 이유입니다.
