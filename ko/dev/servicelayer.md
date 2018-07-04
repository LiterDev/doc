## service layer
Liter 플랫폼의 서비스레이어에 대한 기술 문서 입니다 구성은 다음과 같습니다.

  - web client
  - web api
  - blockchain rpc api
  - app client (예정) 
  - oauth2 service (예정)
  - road map

## web client
Liter 플랫폼의 web client를 담당하는 layer입니다.
확장성과 echo system을 검토한 결과 react가 적절하다고 판단되었습니다.
추후 웹소켓 등을 이용한 양방향 바인딩에 최적화 되어있는 web client를 구축하는 것이 목적 입니다.

  - `react` 기반의 SPA
  - reat version : 16.4
  - redux
  - boilerplate : gatsby 2

## web api
Liter 플랫폼의 web api를 담당하는 server layer 입니다
Sprin Boot 5의 webflux 기반 functional endpoint 형태로 구성되어있습니다
reactive 스타일의 non-blocking 서비스를 기반으로 추후 micro servie 적용이 용이하도록 구축하는 것이 목적 입니다.

  - `spring boot` 기반의 REST API
  - java 1.8
  - boilerplate : spring boot 2.03
  - persistant : mongodb, spring data jpa
  - spring 5


## blockchain rpc api
Liter 플랫폼에서 EOS기반의 블록체인과 통신하기 위한 api layer 입니다
아래의 자료들을 참조하여 java기반의 web api 모듈로 재구성 하였습니다

  - 참조 1 : [Plactal EosCommander](https://github.com/plactal/EosCommander, "Plactal EosCommander")
  - 참조 2 : [eosjs](https://github.com/EOSIO/eosjs, "eosjs")

  - `spring boot` 기반의 REST API
  - java 1.8
  - boilerplate : spring boot 2.03
  - cleos의 일부 기능을 대체
  - 보안이슈 점검 필요

