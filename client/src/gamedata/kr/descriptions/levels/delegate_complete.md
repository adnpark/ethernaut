`delegatecall`의 사용은 매우 큰 위험을 내포하고 있고, 역사적으로 수 많은 해킹들의 어택 벡터로 사용되어 왔어요. `delegatecall`를 사용한다는것은 마치 이렇게 말하는것과 같아요. "자 여기 내 컨트랙트의 상태를 가지고 다른 컨트랙트든 라이브러리든 마음대로 사용해". `delegatecall`은 물론 굉장히 강력한 기능이지만, 동시에 위험한 친구이기 때문에 각별한 주의를 기울여 사용해야해요.

`delegatecall`이 어떻게 3천만 달러 규모의 해킹에 활용되었는지 자세히 알아보고 싶다면 [The Parity Wallet Hack Explained](https://blog.openzeppelin.com/on-the-parity-wallet-multisig-hack-405a8c12e8f7) 글을 읽어보세요.
