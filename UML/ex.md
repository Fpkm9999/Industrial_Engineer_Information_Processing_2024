https://simuing.tistory.com/entry/2021-%EC%A0%95%EB%B3%B4%EC%B2%98%EB%A6%AC%EA%B8%B0%EC%82%AC-%ED%95%84%EA%B8%B0%EC%9A%94%EC%95%BD-UML


UML (Unified Modeling Language) 예시를 제공하기 위해, 다양한 UML 다이어그램 중에서 가장 널리 사용되는 **클래스 다이어그램**과 **유스케이스 다이어그램**의 간단한 예시

### 1. 클래스 다이어그램 예시

클래스 다이어그램은 시스템의 구조적 측면을 모델링하는 데 사용됩니다. 여기에는 클래스 간의 관계, 각 클래스의 속성 및 메서드가 포함됩니다. 다음은 온라인 쇼핑 시스템의 간단한 클래스 다이어그램 예입니다:

- **클래스**: `Product`, `Customer`, `ShoppingCart`
- **관계**:
  - `Customer`와 `ShoppingCart` 사이에는 연관 관계가 있습니다. 즉, 한 명의 고객은 하나의 쇼핑카트를 가질 수 있습니다.
  - `ShoppingCart`와 `Product` 사이에는 집합 관계가 있습니다. 쇼핑카트는 여러 상품을 포함할 수 있습니다.

```plaintext
[Customer]---->[ShoppingCart]
[ShoppingCart]<>->[Product]
```

- **Customer 클래스 속성**: `customerID`, `customerName`, `customerAddress`
- **Customer 클래스 메서드**: `addProductToCart(Product)`, `removeProductFromCart(Product)`

### 2. 유스케이스 다이어그램 예시

유스케이스 다이어그램은 시스템의 행위적 측면을 사용자의 관점에서 보여 줍니다. 이 다이어그램은 시스템이 수행해야 할 기능과 외부 액터(사용자)의 상호작용을 표현합니다. 다음은 온라인 쇼핑 시스템의 유스케이스 다이어그램 예입니다:

- **액터**: `Customer`, `Admin`
- **유스케이스**:
  - `Customer`는 `Browse Products`, `Add Product to Cart`, `Checkout`을 할 수 있습니다.
  - `Admin`은 `Add Product`, `Remove Product`, `Update Product`을 관리할 수 있습니다.

```plaintext
[Customer] -- (Browse Products)
[Customer] -- (Add Product to Cart)
[Customer] -- (Checkout)
[Admin] -- (Add Product)
[Admin] -- (Remove Product)
[Admin] -- (Update Product)
```

이 예시들은 UML 다이어그램을 사용하여 시스템의 다양한 측면을 어떻게 모델링할 수 있는지 보여 줍니다. 각 다이어그램은 개발자와 이해 관계자 간의 통신을 촉진하고, 설계 결정을 명확히 하는 데 중요한 역할을 합니다.

**Q1**: 다이어그램을 설계할 때 고려해야 할 주요 원칙은 무엇인가요?

**Q2**: 클래스 다이어그램과 유스케이스 다이어그램을 통합하는 방법에는 어떤 것들이 있을까요?

**Q3**: 복잡한 시스템을 위한 UML 모델링에서 흔히 저지르는 실수는 무엇이며, 이를 어떻게 방지할 수 있을까요?