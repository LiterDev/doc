# Abusing

## Regulation to prevent from malicious actions which may ruin LITER ecosystem.

### System Report Area
### User Report Area

### Definition of Fake Review

#### Reviews which is applicable to following conditions:

#### 1. Contents
 
##### 1.1 Image
	• A.I (ex. Smart Lens)
	• Image of the product or the service is not included
	• Unidentifiably blurry image
	• Less than three images
	• Using the same image in multiple reviews(hash number)
    
##### 1.2 Text
	• Unfulfiiling context (less than 100byte)
	• Name of the product or the service is not mentioned in the review
    
##### 1.3 Video
	• Video is not uploaded
	• Using the same video in multiple reivews (hash number)
    
##### 1.4 Category
	• Product or service does not fit to the selected category
	• Review on unexperienced product or service
	• Review on non-existing product or service

#### 2. User
##### 2.1 Gender
	• Undetermined gender on the gender-specific product
	• Usage of unmatching gender-specific product(ex.feminine product)
	• Review on unmatching gender-specific product
	
##### 2.2 Age
	• Undetermined age on the age-specific product
	• Usage of unmatching age-specific product (ex.layette)

### Centralized Management System (Review)

#### Purpose
##### System initially filters fake reviews, and prevent from fake review generation or request to modify the contents

#### Stage
	• Alert (Request to fulfill the initial requirement)
	• Prevent (Fix the initial requirement for review generation) 

#### Rules
##### Text
	• Minimum number of text : More than 100byte
	• Plagiarism and context similarity test(Machine Learning)
	• Morpheme Analysis : Machine Learning 
##### Image 
	• Three images or more
	• Image similarity test (Hashing, Machine Learning)
	• Hash number
	• Machine Learning
##### Video(http://www.itworld.co.kr/print/54659)
	• One video or more
	• Video similarity test	
	• Hash number
	• Machine Learning
	• Video pattern recognition technology (widilab)
	• Review optimization(http://victorykorea.tistory.com/48?category=236135)
	• Image, text, video, image, text pattern comparison (text image text image text video)
	• Inclusion of principal keyword of the selected category

#### Methods
	• Alert unfulfilled initial requirement
	• Allow review generation, but provide review generation requirement guide
	• Prevent from review generation
	• Invalid to generate review when initial requirement is not fulfilled
	• Prevention from review generation + alert unfulfilled initial requirement
	• Partially fulfilling initial requirements + alert unfulfilled requirements
	
#### Penalties
	• Delete Review
	• Invalidation of reward
	• Removal of reward on registered review (100%)
	• Reduction of reward
	• Removal of reward per report ( 0.75 per report   1 LTR * 0.75 )
	• Reward penalty
	• Invalidation or reduction of reward on further review
	• Limited review generation
	• Limit the number of review creation during a ceratin period 
	• Limitation applies depending on the number of report received (12 / 8 / 4/ 2/ 1)


### Centralized Management System (User)
#### Purpose
##### System filters malicious users who may ruin LITER ecosystem.

#### Stage
	• Alert (Request to fulfill the initial requirement)
	• Prevent (Fix the initial requirement for review generation) 

#### Rules
	• 기간별 최소 리뷰 등록 수 
	• 한달에 최소 1개 리뷰 등록 의무 
	• 기간별 최소 반응 횟수
	• 한달에 최소 10개 리뷰 반응 의무
	• 기간별 최소 신고 횟수
	• 한달에 최소 1개 리뷰 신고 의무
	• 계정 청정 지표
	• 기간별, 기간별 컨텐츠 평균 안받은 횟수 신고 기준치 이상
	• 너무많은 신고를 한 유저

#### Methods
	• Alert message to fultill the initial requirement
	• Provide guidance for developing community
	• Encourage user to fultill the initial requirement
	• Incentive for fulfilling initial requirement
	• Penalty for unfulfilling initial requirement

#### Penalties
	• Invalidation of reward
	• Removal of reward on registered review
	• Reward penalty
	• Invalidation of reward on further review, the first review generated after receiving reports provide 25% reduced reward
	• Limit Review Generation
	• Limit the review creation during a ceratin period (a week), Limit the number of review creation (twice a month)
	• Limit activity
	• Limit activity in LITER (Limit review generation, limit voting)

### Decentralized Management System (Review)

#### Purpose
##### Decentralized consensus methodology (abusing report) manages centrally processed reviews to maintain review ecosystem

#### Reporting Scenario 
	• Reporting opposite opinion 
	• Intential report of competitor
	• Uncongenial Review
	• Fake review in purpose of getting attention 
	• Copyrights


### Decentralized Management System (User)

#### Reporting Scenario
	• Intentionally preventing reviewer's reward
	• Intention to receive reporting reward
	• Fake account

#### Solution
	• Constitute Deliberation Committee(User)
	• Deep Learning => Report Evaluation Bot 

