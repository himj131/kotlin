# [Data types](https://hyperskill.org/learn/step/4388)

## What is a data type?
여러분은 경험을 통해서 숫자가 텍스트와 같지 않다는 것을 잘 알고있습니다. 숫자에서는 산술연산(곱셈과 같은)이 가능하지만 텍스트에서는 불가능 합니다. Kotlin에서도 마찬가지입니다. 모든 변수에는 가능한 연산과 저장할 수 있는 값을 판별하는 타입이 존재합니다.

## Variable types
변수의 타입은 선언 될 때 설정됩니다 :
```kotlin
val text = "Hello, I am studying Kotlin now."
val n = 1
```
이 경우 Kotlin은 텍스트가 문자열이고 n이 숫자라는 것을 알고 있습니다. Kotlin은 두 변수의 타입을 자동으로 결정합니다. 이 메커니즘을 `타입추론` 이라고합니다.

타입 추론을 사용하는 선언의 형식은 다음과 같습니다.
```kotlin
val/var identifier = initialization
```

선언 할 때 변수의 유형을 지정할 수 있습니다.
```kotlin
val/var identifier: Type = initialization 
```
> ※형식의 이름은 항상 대문자로 시작합니다.
위 예제와 동일한 변수를 선언하면서 타입을 지정해보도록 하겠습니다.
```kotlin
val text: String = "Hello, I am studying Kotlin now."
val n: Int = 1
```
Int 유형은 변수가 정수 (0, 1, 2, ..., 100_000_000, ...)를 저장한다는 것을 의미합니다. 문자열 유형은 변수가 문자열("Hello", "John Smith")을 저장한다는 것을 의미합니다.
이 두 가지 형식은 모두 실제로 자주 사용됩니다. 타입추론을 사용하는 형식은 코드를 보다 간결하고 읽기 쉽게 만듭니다. 그러나 경우에 따라 형식을 지정하는 것이 더 나을 수 있습니다. 예를 들어 변수를 선언하고 나중에 초기화 해야하는 경우 타입추론을 사용 할 수 없습니다.
```kotlin
val greeting // error
greeting = "hello"
```
위의 코드는 올바르지 않습니다. 왜냐하면 Kotlin은 변수가 선언 되었을 때 변수의 유형을 추론 할 수 없으며 모든 변수에 타입이 주어져야합니다. 타입이 정의된 아래 코드는 잘 작동합니다.
```kotlin
val greeting: String // ok
greeting = "hello"
```

## Type mismatch
데이터 유형의 가장 중요한 기능 중 하나는 부적절한 값을 변수에 할당하지 못하게 하는 것입니다. 예를 들어 다음 코드는 작동하지 않습니다.
```kotlin
val n: Int = "abc" // Type mismatch: inferred type is String but Int was expected
```
따라서  타입불일치 오류가 나면 변수에 적합하지 않은 값을 지정했음을 의미합니다. 타입추론을 사용해 선언한 변경 가능한 변수에 부적합한 값을 할당하려고 하면 같은 문제가 발생합니다.
```kotlin
var age = 30 // the type is inferred as Int
age = "31 years old" // Type mismatch
```
이번장에서 기억할 부분입니다.  
**변수는 만들어질 때 타입이 정해지며, 그 타입은 나중에 변경할 수 없습니다.**
