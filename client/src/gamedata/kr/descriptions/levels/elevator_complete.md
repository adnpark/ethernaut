의도치 않은 상태 변경을 방지하고 싶다면 인터페이스에 `view` 함수 변경자(modifier)를 추가할 수 있어요. `pure` 변경자 또한 상태 변경을 막을 수 있어요.
이 [솔리디티 문서](http://solidity.readthedocs.io/en/develop/contracts.html#view-functions)를 읽고 여러 주의사항을 확인해보세요.

이 레벨을 풀 수 있는 또 다른 방법은 상태를 변경하지는 않지만, 입력 데이터에 따라 다른 결과를 반환하는 view 함수를 구현하는거에요. 예를 들어, `gasleft()` 를 활용할 수 있어요.
