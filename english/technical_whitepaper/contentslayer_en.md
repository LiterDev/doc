# Contents Layer

This document is a technical whitepaper of LITER platform - Contents Layer. Components of this document is the same as below:

  - Definition of Contents
  - Data Storage Operation Plan
  - Centralized Data Storage
  - InterPlanetary File System (IPFS)
  - Storing Review
  - Road Map

## Definition of Contents
In the LITER platform, content is defined as digital contents created by users such as'image', 'video', 'document' etc

## Data Storage Operation Plan
1. Initially, for the high availability of the service, data will be stored at centralized data storage.
2. Simultaneously, data will be stored at IPFS to test its applicability with high availability.
3. As technical verification is finished, IPFS protocol replaces centralized data storage sequentially.

## Centralized Data Storage
To achieve user-efficient service processing speed and its stability, centralized data storage will be initially used.
  - AWS s3
  - AWS cloud front for global service
  - Image : 3 types of definition (mobile, tablet, desktop - optimized definition)
  - Video : need to determine whether uploading video feature will use self-operating streaming service or API from streaming serivce such as youtube, vimeo etc. (Initial service will use URL link from pre-existing streaming service)

## InterPlanetary File System (IPFS)
For the permanence of contents, LITER targets to apply IPFS.
  - IPFS protocol : among IPFS technologies, swam, storj etc - which is currently in use by Steemit, Dtube etc - will be applied to LITER platform.
  - To solve availability issue of p2p storage(such like loss of node), IPFS will be operated and tested with self-operating nodes.
  - <https://ipfs.io/>

## Storing Review
  1. User uploads contents
  2. Content will be transmitted to Liter web api server
  3. Using AWS api, content will be uploaded to s3, and it returns link.
  4. Using IPFS api, content will be stored, and it returns hash number.
  5. Value received from [3], [4], will be stored at mongodb in form of string, and it returns representing key value of string.
  6. Key value from [5] will be stored at mongodb with review information.
  7. UUID returned from [6] will be recorded at on-chain through review contract.

```
To minimize the usage of EOS RAM, priority information which must be permanent, need to be classified.
To reach fully decentralized service, recording review information and IPFS mapping hash number on-chain is ideal, but in reality, overloading node and RAM usage cost constrains from recording all data on-cahin.
Investigation on technical limitation must be proceeded, and technically available and the applicaiton of the most relevant technology must be determined.
Additionally, priority information which must be permanent, need to be classified in a perspective of blockchain developer.
```
```
Policy on setting boundary of irreversible data need to be determined.
```
## Road Map
