It's important to remember that marking a variable as private only prevents other contracts from accessing it. State variables marked as private and local variables are still publicly accessible. 
변수를 private으로 선언하는것은 오직 다른 컨트랙트가 해당 변수에 접근하는것을 방지할 뿐이에요. private으로 선언된 상태변수들과 지역 변수들은 여전히 공개적으로 노출된다는 점을 꼭 기억하세요.

데이터의 프라이버시를 보장하고 싶다면, 블록체인에 저장되기 전에 먼저 반드시 암호화 되어야 해요. 이 경우에 절대 복호화 키가 온체인으로 전송되어서는 안돼요. 모든 사람이 복호화 키를 확인할 수 있게 되니까요. [zk-SNARKs](https://blog.ethereum.org/2016/12/05/zksnarks-in-a-nutshell/)와 같은 기술을 이용할 수도 있는데, 이는 누군가가 특정 값을 노출시키지 않고도, 해당 값을 알고 있다는 것을 증명할 수 있는 방법을 제공해요.