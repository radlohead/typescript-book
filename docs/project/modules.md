## Modules

### Global Module

기본적으로 새로운 타입스크립트 파일에서 코드를 입력하면 코드가 전역 네임스페이스에 있습니다. 데모파일인 `foo.ts`를 고려하십시요.

```ts
var foo = 123
```

같은 프로젝트에서 `bar.ts`라는 새로운 파일을 만들면 타입스크립트의 타입시스템에서 전역에서 사용할 수있는 것처럼 `foo`변수를 사용할 수 있게됩니다.

```ts
var bar = foo // allowed
```

전역 네임스페이스는 위험하고 불필요합니다. 그것은 당신의 코드가 전역네임스페이스와 네이밍 충돌을 야기할 것 입니다. 우리는 파일을 모듈화해서 사용하길 추천합니다.

### File Module

외부 모듈을 호출할때 만약 당신이 타입스크립트에서 `import`또는 `export`를 파일 최상단에서 생성하면 지역 스코프를 가집니다. 만약 당신이 이전에 만든 `foo.ts`를 다음과 같이 변경한다면 `export` 사용에 주의하십시요.

```ts
export var foo = 123
```

우리는 `foo` 변수가 전역 네임스페이스에 남아있지 않는다는 것을 다음 새로운 `bar.ts` 파일을 생성해봄으로써 입증할수 있습니다.

```ts
var bar = foo // ERROR: "cannot find name 'foo'"
```

만약 당신이 `foo.ts`를 `bar.ts`안에서 사용하는 확실한 방법은 다음과 같이 import를 이용해서 `bar.ts`를 업데이트 할수 있습니다.

```ts
import { foo } from './foo'
var bar = foo // allowed
```

`import`를 `bar.ts`에서 사용하면다른 파일의 내용을 가져올 수 있을뿐만 아니라 `bar.ts`파일을 module로 표시할 수 있습니다. 따라서 `bar.ts`의 선언은 전역 네임스페이스를 오염시키지 않습니다.

타입스크립트 파일은 외부 모듈을 사용하고 여기서 생성되는 자바스크립트는 `module`이라는 컴파일러 플래그에 의해 구동됩니다.
