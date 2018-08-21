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
	• 변화패턴코드 인식기술 (위디랩
	• 리뷰 최적화(http://victorykorea.tistory.com/48?category=236135)
	• 사진, 글, 동영상, 사진, 글 패턴 비교 (글 사진 글 사진 글 동영상)
	• 카테고리내 중요키워드 포함여부

#### 방법
	• 요구조건 미충족 알림기능
	• 리뷰 업로드는 허용하되 규정 충족 여부 가이드 메뉴 제공
	• 리뷰 등록 방지
	• 규정 충족이 안되었을 경우에는 업로드 불가
	• 리뷰 등록 방지 + 요구조건 미충족 알림기능
	• 부분적 규정 충족 + 미충족 조건 알림 가이드 제공

#### 벌칙
	• 리뷰 삭제
	• 등록 리뷰 삭제
	• 보상 무효화
	• 등록 리뷰에 대한 보상 제거 (100%)
	• 보상 감소
	• 신고 횟수 만큼 보상 제거 ( 1신고 당 0.75     1 LTR * 0.75 )
	• 보상 페널티
	• 미래에 등록될 리뷰에 대한 보상 무효화, 감소
	• 리뷰 작성 제한
	• 리뷰 작성 기간 제한, 기간별 최대 등록 횟수 제한 
	• 리포팅 당한 횟수에 따라서 (12 / 8 / 4/ 2/ 1)


### 중앙화제어 (사람)
#### 목적
##### 불량한 유저를 색출하여 잘못된 리뷰의 등록 및 LITER생태계의 건전함을 지키기 위함

#### 단계
	• 알림 (기준충족 요청)
	• 방지 (기준충족 강제) 

#### 규칙
	• 기간별 최소 리뷰 등록 수 
	• 한달에 최소 1개 리뷰 등록 의무 
	• 기간별 최소 반응 횟수
	• 한달에 최소 10개 리뷰 반응 의무
	• 기간별 최소 신고 횟수
	• 한달에 최소 1개 리뷰 신고 의무
	• 계정 청정 지표
	• 기간별, 기간별 컨텐츠 평균 안받은 횟수 신고 기준치 이상
	• 너무많은 신고를 한 유저

#### 방법
	• 요구조건 충족 권유 알림 메세지
	• 커뮤니티 발전을 위한 방향 안내
	• 요구조건 충족 부분 의무 충족 권장
	• 요구조건 충족시 인센티브
	• 요구조건 불 충족시 불이익

#### 벌칙
	• 보상 무효화
	• 등록 리뷰에 대한 보상 제거
	• 보상 페널티
	• 미래에 등록될 리뷰에 대한 보상 무효화, 신고 건 바로 뒤의 글은 보상 25% 회수
	• 리뷰 작성 제한
	• 리뷰 작성 기간 제한 (1주일) , 기간별 최대 등록 횟수 제한 (한달 최대 2건)
	• 활동 제한
	• LITER생태계 활동 제한 (글작성수 제한, 보팅 횟수 제한)

### 탈중앙화제어 (리뷰)

#### 목적
##### 중앙화제어로 처리된 리뷰를 탈중앙화방식인 신고를 통해 올바른 리뷰생태계를 유지.

#### 신고 시나리오 
	• 나와 다른 의견 
	• 경쟁 업체의 고의적 신고
	• 그냥 맘에 안드는 리뷰
	• 주목을 받기 위한 가짜 리뷰를 신고 
	• 저작권


### 탈중앙화제어 (사람)

#### 신고 시나리오
	• 작성자의 보상을 막기위해
	• 신고 보상을 위한 신고
	• 허위 계정

#### 해결방법
	• 심의 위원회 구성 (사람)
	• 딥러닝 활용 => 신고 심사 봇 

