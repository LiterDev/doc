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
  3. 평가 보상에 대한 정책 변경이 생태계의 결정에 따라 가변적 이고 반영이 손쉬울 것(정책 변경에 따라 hard pork 가 일어나지 않을 것)
  4. core contract 영역과 application contract 영역을 분리 할 것

상기의 조건을 토대로 [1], [2] 번 항목을 만족 시키기 위해서는 DPOS방식이 적합하다는 결론을 내고 실제 서비스 되고있는 bitshare 와 steemit에서 사용된 
[graphene](https://objectcomputing.com/resources/publications/sett/march-2017-graphene-an-open-source-blockchain) 기반으로 자체 블록체인을 개발하기로 잠정 결정후 타 블록체인에 대한 리서치 시작

### EOS DAWN 3.0 의 등장
  
  1. bios contract을 통하여 블록생성 과 블록체인의 운영 정책을 분리함
  2. 0.5초의 블록생성 시간

[1]의 조치로 인하여 블록체인의 대부분의 정책 수정이 hard fork 없이 가능하게 되었고 이는 Liter 블록체인에서 정의하였던 core contract 와 application contract의 분리 구조와 매우 유사한 구조를 가지게 되었다. 
[2]는 실제 사용자들의 반응을 fail over 없이 온체인에 기록 할 수 있도록 가능하게 되었고 실제 중앙화 된 서비스와 트랜젝션 차이가 무의미 할 정도의 속도라고 판단 되었다

#### EOS의 DPOS 방식이 리터생테계의 운영 탈중앙화의 로드맵과 잘 부합된다고 판단 하였고, 서비스하기에 무리없는 빠른 트랜젝션, 자체 노드운영 및 구축의 용이함 떄문에 초기 서비스를 위한 최적화된 블록체인으로 판단되어 도입을 결정

## 비가역성 데이터
블록체인의 트랜젝션은 한번 기록되면 다시 되돌릴 수 없는 것을 특징으로 한다. 그리고 모은 생태계 주체로 부터 쉽게 정보에 접근이 가능해야 하고 이를 위하여 실제 블록체인에 기록되어야 하는 정보들은 생태계 주체들에게 유용하고 의미있는 정보여야 한다

  - 기준
    * 생태계 주체간 양자 또는 다자간의 신뢰에 대한 합의를 필요로 하는 데이터 인가
    * 투명성을 가지고 공개되어야 하는가
    * 세대를 거처 전달되어야 하는 가치를 담고 있는가?
   
  - 항목
    * Liter Cube transaction
    * Liter Coin transaction
    * Reivew 생성정보
    * 반응 관련 transaction
    * 평가/보상 관련 transaction

## smart contract layer
EOS를 이용한 자체 node 운영 시 개발 및 배포해야할 smart contract 목록 및 정의

  - bios contract : EOS의 core contract 중 Liter에 필요한 기능들을 선별적으로 배포
    * eosio.token : token 발행 및 전송 기능
    * eosio.msig : multi signature 를 위한 기능
    * eosio.system : eos node의 정책 기능 (BP설정, 램자원 관리등)

  - Liter application contract
    * 리뷰 : 리뷰 생성시 해당 정보를 Persistence API 를 이용하여 기록
      - create : 리뷰생성 및 정보 기록
      - update : 리뷰수정시 수정일시 누적 기록
      - add like : like 기록 및 count ++
      - sub like : like 철회 기록 및 count --
      - add report : 신고 기록 및 count ++
      - sub report : 신고 철회 기록 및 count --
      - lock : 리뷰의 모든 기능 lock
      - unlock : 리뷰의 모든 기능 unlock
      - isClaim : 보상여부 기록 및 상태 업데이트

    * 반응 : 사용자 반응을 기록
      - add like : like 기록 
      - sub like : like 철회 기록 
      - add report : 신고 기록
      - sub report : 신고 철회 기록

      
    * 평가/보상 : 리뷰와 반응 결과에 의해 평가 및 보상을 지급
      - review claim : 리뷰어가 보상 요청 시 보상 지급처리
      - engagement claim : 반응자가 보상 요청 시 보상 지급 처리
      - lock review
      - unlock review
      - isClaim	review

    * Liter Coin : Liter 의 유동자산관련 contract 작성
      - issue : 입금된 LiterCube 를 정해진 비율에 의해 LiterCoin 으로 요청자에게 발행 (Liter wallet owner 와 요청 user 의 multi sig 로 작성 검토)
      - transfer : 전송기능 (min 금액 설정여부 검토)
      - lock
      - unlock


    * Liter Cube : 부동자산으로서의 Liter token contract 작성 필요
      - create : 초기 생성
      - issue : 발행 멀티 시그를 이용하여 BP와 Liter wallet owner 가 전부 동의해야 가능하도록 구현
      - transfer : 전송 Liter wallet owner 만 가능
      - 실제 LiterCube 는 부동자산이지만 보상 지급시 발행 또는 전송 기능이 필요하다 보안상 무한 발행 이슈를 막기 위하여 한정된 자원안에서 전송기능을 사용하도록 한다
      
## node 운영 방안     
EOS blockchain 의 node 운영 정책을 기반으로 LITER 생태계 운영에 적합한 부분을 추가로 적용하여 운영정책을 세운다

  - 초기에는 EOS BIOS Boot Sequence 를 기준으로 자체 node를 운영한다
  - 초기 BP 선정은 LITER 에서 정의하고 생태계의 규모와 안정도에 따라 점차 탈중앙화된 방식으로 이관한다
  - 이관 프로세스는 생태계 주체들과 합의하여 이관 시나리오 구축 및 테스트를 통한 검증 후 단계별로 실행한다
  - 메인넷과 병행하여 베타서비스를 운영하면서 메인넷의 버그픽스 적용 및 LITER 자체적으로 발생한 버그픽스는 메인넷에 기여할 수 있도록 한다 
