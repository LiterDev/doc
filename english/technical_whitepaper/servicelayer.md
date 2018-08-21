# Service Layer
This document is a technical whitepaper of LITER platform - Service Layer.
Components of this document is the same as below:

  - Web Client
  - Web API
  - Blockchain RPC API
  - App Client (To be scheduled)
  - Oauth2 Service (To be scheduled)
  - Road Map

## Web Client
Web Client layer of LITER platform
Considering the scalability and investigating its reference, react is determined as most suitable for LITER Web Client.
Developing the web client with optimized bilateral binding using WebSocket etc, is the target goal.

  - `React` Web Client
  - react Version : 16.4
  - redux, redux saga
  - boilerplate : next.js

## [Web API](https://github.com/LiterDev/liter-web-api)
Web API server layer of LITER platform
Spring Boot 5 : functional endpoint structure based on webflux
Developing based on non-blocking serivce with reactive style to apply micro service readily is the target goal.

  - `spring boot` based REST API
  - java 1.8
  - boilerplate : spring boot 2.0.3
  - persistent : mongodb, spring data jpa
    * Domain for relational serivce will use mysql.
    * Mass log data will be processed with mongodb which supports non-blocking with reactive style and has the most abundant reference among mongodb,redis, and cassandra.
    * Data which does not require permanance, and cashing will be process with redis.
    
  - spring 5
  - JWT based AUTH
    * Develop stateless auth, and develop app(ios, android) compatible version
    * accessToken : expired time (short), refreshable(O), user auth token, review modification/delete authority, re-issuance is valid using refreshToken
    * refreshToken : expired time (long), refreshable(X), auth-token/re-issuance token
    * walletToken : expired time (very short), refreshable(X), wallet transaction feature
    * ownerToken : expired time (very short), refreshable(X), view/modify user data
  
  - webflux
    * supports from spring 5 version
    * supports reactive based non-blocking 
    * functional endpoint : netty based fuctional router substitutes the traditioanl dispatcher servlet.
    * Domain design which considers transaction reactive environment, is required.
    * Easy to structure test environment


## Blockchain RPC API
EOS based blockchain communication API layer of LITER platform.
The target goal is to provide compatible EOS node and interface to Java based DAPP web service providers.
Using references below, java based Web API module is restructured.
(Reference 1 : [Plactal EosCommander](https://github.com/plactal/EosCommander), Reference 2 : [eosjs](https://github.com/EOSIO/eosjs))

  - `spring boot` based REST API
  - java 1.8
  - boilerplate : spring boot 2.0.3
  - substitute features of cleos partly
    * wallet create
    * wallet import
    * account create
    * get chain info
    * push transactoin 
    * get transactions
    * get table rows
    * get currency balance
    * abi json to bin
    * get code

  - Security check required

