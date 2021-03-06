# 컨텐츠 레이어
Liter 플랫폼의 컨텐츠 레이어에 대한 기술 문서 입니다 구성은 다음과 같습니다.

  - 컨텐츠의 정의
  - 저장소 운영 방안
  - 중앙화된 저장소
  - 분산 저장소
  - 리뷰 저장
  - road map

## 컨텐스의 정의
Liter 플랫폼에서 사용자들에 의하여 생성되는 `이미지`, `동영상`, `문서` 등등을 통칭한다


## 저장소 운영 방안
1. 초기에 서비스를 위한 고가용성을 보장하기 위하여 중앙화된 서버에 컨텐츠를 저장하여 서비스한다.
2. 동시에 분산저장소에도 컨텐츠를 저장하고 일부 적용 및 테스트기간을 가진다. 
3. 기술적 검증이 완료되는 시점에 분산 저장소의 서비스 비중을 높여간다.

## 중앙화된 저장소
실제 사용자단 서비스의 속도 및 안정성을 위하여 사용한다
  - aws의 s3 이용
  - 글로벌 서비스를 위한 aws cloud front 사용
  - 이미지 : 3가지 해상도(모바일, 테블릿, 데스크탑 각각 최적화된 해상도)로 저장
  - 동영상 : youtube, vimeo등의 api를 이용할 지 자체 스트리밍을 할 것인지에 대한 검토 필요 (초기 서비스에는 동영상 링크만 사용)

## 분산 저장소
컨텐츠의 영속을 위한 분산 저장 시스템 구성을 목적으로 한다.
  - IPFS 프로토콜 : swam, storj등등 분산 스토리지 기술 중 실제 steemit, dtube등에서 사용하고 있는 IPFS를 사용한다.
  - p2p 방식의 저장소다 보니 실제 노드 유실로 인한 가용성 문제를 해결하기 위하여 자체 node를 운영하면서 테스트 한다.
  - <https://ipfs.io/>

## 리뷰저장
  1. 사용자가 컨텐츠를 업로드한다
  2. Liter web api server로 전송
  3. aws api를 이용하여 s3에 업로드 후 링크를 리턴 받는다
  4. IPFS api를 이용하여 저장 후 hash값을 리턴 받는다
  5. [3], [4]에서 의 값들은 배열형태로 mongodb에 저장되고 배열의 대표 key값을 리턴한다
  6. [5]의 key를 review 정보와 함께 mongodb에 저장한다
  7. [6]에서 리턴받은 리뷰 uuid를 블록체인의 review contract를 이용하여 온체인에 기록한다

```
EOS의 램을 최대한 적게 사용하기 위하여 실제 영속성을 가져야 하는 정보들을 선별하는 작업이 선행되어야 한다.
탈중앙화에 가까운 서비스를 위하여 온체인에 review의 기본정보와 해당 컨텐츠를 매핑할 수 있는 IPFS의 hash주소를 기록하는 것이 이상적이나
실제 node의 부하 및 램자원의 가격등을 고려해보았을 때 현실적으로 온체인상에 기록 할 수 있는 정보는 제한 적일 수 밖에 없다.
현재 가진 기술적 한계를 인지하고 최대한 기술적 탈중앙화에 가까운 아키텍처를 구축하는 것을 최대 목표로 한다.
추가로 세대를 거처 영속성을 가져야만 하는 정보의 선별조차 탈중앙화 할 수 있는 방법을 기술자 관점에서 고민해봐야 할 것.
```
```
블록체인의 비가역성을 컨텐츠 레이어의 어느 영역까지 확장할 것인가에 대한 정책 논의
```
## road map
