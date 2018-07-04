## blockchain layer
Liter 플랫폼의 블록체인 레이어에 대한 기술 문서 입니다 구성은 다음과 같습니다.

  - Why EOS?
  - smart contract layer
  - node 운영 방안
  - BP 선정 및 운영
  - 보안조치
  - road map

## Why EOS?
Liter 는 초기 블록체인 node를 EOS 기반으로 개발 및 운영을 하게 될 것 입니다.
왜 EOS가 Liter 서비스에 적합한지에 대한 검토 및 결정 과정에 대한 기록 입니다.

### Liter 플랫폼에 사용할 블록체인의 요건
  1. 사용자 중심의 서비스이기 때문에 빠른 트랜젝션 및 컴펌 속도 필요
  2. 초기 생태계 빌드시에는 정책 결정을 중앙화된 거버넌스나 재단에서 하지만 점차 생태계의 주체들에게 해당 권한을 이양 가능 할 것
  3. 평가 보상에 대한 정책 변경이 생태계의 결정에 따라 가변적 일 것
  4. core contract 영역과 application contract 영역을 분리 할 것

상기의 조건을 토대로 [1], [2] 번 항목을 만족 시키기 위해서는 DPOS방식이 적합하다는 결론을 내고 실제 서비스 되고있는 bitshare 와 steemit에서 사용된 
[graphene](https://objectcomputing.com/resources/publications/sett/march-2017-graphene-an-open-source-blockchain) 기반으로 자체 블록체인을 개발하기로 결정함

### EOS DAWN 3.0 의 등장
  
  1. bios contract을 통하여 블록생성 과 블록체인의 운영 정책을 분리함
  2. 0.5초의 블록생성 시간

[1]의 조치로 인하여 블록체인의 대부분의 정책 수정이 hard fork 없이 가능하게 되었고 이는 Liter 블록체인에서 정의하였던 core contract 와 application contract의 분리 구조와 매우 유사한 구조를 가지게 되었다. 
[2]는 실제 사용자들의 반응을 fail over 없이 온체인에 기록 할 수 있도록 가능하게 되었고 실제 중앙화 된 서비스와 트랜젝션 차이가 무의미 할 정도의 속도라고 판단 되었다

#### EOS의 DPOS 방식, 빠른 트랜젝션, 자체 노드운영의 용이함 떄문에 초기 서비스를 위한 최적화된 블록체인이라는 결론에 도달하였다 

