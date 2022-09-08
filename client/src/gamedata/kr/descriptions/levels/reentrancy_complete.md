컨트랙트의 자금을 외부로 전송할 때 재진입 공격을 방지하기 위해서는 [Checks-Effects-Interactions 패턴](https://solidity.readthedocs.io/en/develop/security-considerations.html#use-the-checks-effects-interactions-pattern)을 활용하세요. `call` 메서드는 실패하더라도 컨트랙트 실행을 중단시키지 않고 오직 false값만 반환할 뿐이라는것을 명심하세요. [ReentrancyGuard](https://docs.openzeppelin.com/contracts/2.x/api/utils#ReentrancyGuard) 또는 [PullPayment](https://docs.openzeppelin.com/contracts/2.x/api/payment#PullPayment)도 이러한 공격에 대한 좋은 솔루션이에요.

`transfer` 와 `send`는 이스탄불 하드포크 이후로 컨트랙트를 망가뜨릴 수 있는 가능성이 있으므로 사용이 권장되지 않습니다. [Source 1](https://diligence.consensys.net/blog/2019/09/stop-using-soliditys-transfer-now/) [Source 2](https://forum.openzeppelin.com/t/reentrancy-after-istanbul/1742)를 참고해보세요.

항상 자금을 보내는 대상이 일반적인 사용자의 주소가 아니라 또 다른 컨트랙트의 주소일수도 있다는점을 명심하세요. 이런 컨트랙트들은 내부의 payable fallback 메서드 안에서 코드를 실행한 후 다시 여러분의 컨트랙트에 재진입(re-enter)하여 컨트랙트의 상태나 로직을 악의적으로 변형시킬 수 있어요.

재진입은 흔한 공격패턴이므로, 여러분은 항상 이 공격에 대비가 되어 있어야해요!

&nbsp;

#### The DAO Hack

매우 유명한 DAO 해킹사건에도 재진입 공격이 이용되었어요. 이 공격을 통해 해커는 컨트랙트에서 어마어마한 수량의 이더를 해킹할 수 있었어요. 자세한 내용은 [15 lines of code that could have prevented TheDAO Hack](https://blog.openzeppelin.com/15-lines-of-code-that-could-have-prevented-thedao-hack-782499e00942)를 참고해보세요.
