# Blockchain Layer
This is the core layer of LITER blockchain. This layer will record all LITER PATRON’s activities including responses, and manage everything related to LITER CUBE and LITER COIN or any other crypto currency that may be involved on the LITER ecosystem in the future. This layer will be constructed to match LITER ecosystem’s characteristics by comparing and analyzing concepts and hypotheses of smart contract based blockchains such as Ethereum or EOS.

## Why EOS?
LITER will develop and operate blockchain nodes based on EOS after evaluation of suitability of LITER platform to EOS.

### Blockchain that suits LITER platform requires:
1.	Fast transaction and confirm speed since LITER is user-driven service platform.
2.	Able to transfer policies and rights to users after centralized governance ends, which LITER plans to do at the beginning of the service launch in order to stabilize the service.
3.	Reward policies can be changeable. As LITER is incentivized platform, reward policy may be updated due to changes of economic and systemic circumstances.
4.	Separation between core contract and application contract.

Considering above requirements, it is concluded that DPOS algorithm suits LITER and planned to develop [graphene](https://objectcomputing.com/resources/publications/sett/march-2017-graphene-an-open-source-blockchain) based blockchain that was also used in bitshare and steemit while researching other capable blockchains.

### Introduction of EOS DAWN 3.0
1. Separation between block generation and block operation policies through bio contract enables policy updates or modifications without hard fork, which is very similar to what LITER blockchain required, the separation between core contract and application contract.
2. 0.5 sec per block generation enables actual user responses to be stored on chain without failover, and it is fast enough to be comparable to centralized service operation.

#### From the evaluation results, EOS with DPOS algorithm, fast transaction speed, and easy operation of own nodes is the optimized blockchain for LITER at the beginning of its service. 

## Irreversible Data
Data that cannot be changed and is to be stored on blockchain 

  - LITER defines Irreversible Data satisfying following conditions:
    * Does data require trust?
    * Should be disclosed for transparency
    * Does it contain value to be passed down through generations?

   
  - Irreversible Data in LITER
    * Liter Cube transaction
    * Liter Coin transaction
    * Reivew Generation Information
    * User response transaction
    * Reward transaction

## Smart Contract Layer
In case of developing LITER blockchain based on EOS blockchain, list of smart contracts and its definition

  - bios contract : Distribute selected core contracts of EOS based on necessary functions of LITER platform
    * eosio.token : token issuance and tranfer feature
    * eosio.msig : multi signature feature
    * eosio.system : eos node policy implementation (Setup BP, RAM resource management etc)

  - Liter application contract
    * Review : Using Persistence API, records review creation data
      - create : create review and record data
      - update : record modified date and cumulative data when review is modified
      - add like : record like history & count++
      - sub like : record cancel-like history & count--
      - add report : record abusing report & count++
      - sub report : record cancel-abusing-report & count--
      - lock : lock all functions of review
      - unlock : unlock all functions of review
      - isClaim : record reward history and update reward status

    * Engagement : record user engagement
      - add like : record like 
      - sub like : record cancel-like 
      - add report : record abusing report
      - sub report : record cancel-abusing-report

      
    * Evaluation/Reward : Evaluation based on review and engagement on the review, and distribution of reward accordingly
      - review claim : distribute reward upon reviewer's claim request
      - engagement claim : distribute reward upon engaged user's claim request
      - lock review
      - unlock review
      - isClaim	review

    * Liter Coin : Create constract of liquid asset (Liter)
      - issue : transferred amount of LiterCube will be issued on requester's wallet with distinguished ratio. (concept of multi sig of Liter wallet owner and requester need to be developed)
      - transfer : transaction feature (minimum transaction need to be determined)
      - lock
      - unlock


    * Liter Cube : Create contract of fixed asset (Liter token)
      - create : initial issuance
      - issue : issuance multi sig requires the approval of BP and all Liter wallet owners to be performed
      - transfer : transaction feature (Only Liter wallet owner can perform feature)
      - LiterCube is a fixed asset, but it requires issuance or transaction feature to be distributed as a reward. To prevent from repeated issuance of LiterCube, LiterCube transaction feature must be perform with limited conditions.
      
## Node Operation Plan     
Based on EOS blockchain operation policy, LITER ecosystem adds additional operation policies on applicable EOS blockchain operation policies. 

  - Initially, LITER operates nodes based on EOS BIOS Boot Sequence.
  - Initial BP will be defined by LITER; as the magnitude and stability of ecosystem expands, LITER internal node operation protocol transforms into decentralized node operation protocol sequentially.
  - Transformation process will be executed sequenctially after concensus of ecosystem participants and ecosystem scenario test.
  - Mainnet and Beta service will be operated simutaneously; internal and external bug fix on mainnet and LITER service will applied. 
  - EOS의 version freezing 
