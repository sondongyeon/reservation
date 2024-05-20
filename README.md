# 짧은 영상 조회수에 따른 정산 시스템

## 1. 프로젝트 개요
- 짧은 영상을 업로드, 조회수에 따라 정산을 도와주는 시스템입니다.
- 유저는 짧은 영상을 업로드하고, 각 영상의 조회수에 따라 00:00 정각에 수익 정산을 진행합니다.
- 소셜 로그인을 통한 간편한 로그인 및 회원 가입을 진행합니다.

## 팀원 
<img src="https://github.com/sondongyeon/TikTak/assets/121774504/0441f2b2-1cf9-4127-a3f3-0a5fd4184db8" width='200' height='200'/>

- 손동연 / BE 및 프로젝트 기획, 설계

## 개발환경
- Back-end : Spring Boot
- DB : Mysql
- ORM : JPA
- 버전업 & 이슈관리 : github, notion
- 서비스 배포 환경 : docker


## ERD

<details>
 
 <summary>ERD</summary>
 
 <div markdown = '1'>
  
<img src="https://github.com/sondongyeon/TikTak/assets/121774504/092d559e-5dd9-4869-8dd5-82456d4d96ec" width='600' height='400'/>

 </div>
 
</details>

## 프로젝트 구조

<details>
 
 <summary>프로젝트 구조 </summary>
 <div markdown = '2'>
 <br>

```plain text
📦src
 ┣ 📂main
 ┃ ┣ 📂generated
 ┃ ┣ 📂java
 ┃ ┃ ┗ 📂project
 ┃ ┃ ┃ ┗ 📂project
 ┃ ┃ ┃ ┃ ┣ 📂config
 ┃ ┃ ┃ ┃ ┃ ┣ 📂jwt
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜JwtProperties.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜TokenProvider.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📂oauth
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜OAuth2AuthorizationRequestBasedOnCookieRepository.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜OAuth2SuccessHandler.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜OAuth2UserCustomService.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜SchedulerConfig.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜TokenAuthenticationFilter.java
 ┃ ┃ ┃ ┃ ┃ ┗ 📜WebOAuthSecurityConfig.java
 ┃ ┃ ┃ ┃ ┣ 📂controller
 ┃ ┃ ┃ ┃ ┃ ┣ 📜StatisticController.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜TokenApiController.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜UserApiController.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜UserViewController.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜VideoApiController.java
 ┃ ┃ ┃ ┃ ┃ ┗ 📜VideoViewController.java
 ┃ ┃ ┃ ┃ ┣ 📂domain
 ┃ ┃ ┃ ┃ ┃ ┣ 📜Advertisement.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜Member.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜PlayHistory.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜RefreshToken.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜Statistics.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜Video.java
 ┃ ┃ ┃ ┃ ┃ ┗ 📜VideoAdvertisement.java
 ┃ ┃ ┃ ┃ ┣ 📂dto
 ┃ ┃ ┃ ┃ ┃ ┣ 📜CreateAccessTokenRequest.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜CreateAccessTokenResponse.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜PlayHistoryDTO.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜StatsDTO.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜TopFiveVideoDTO.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜TopFiveVideoInterface.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜UserDTO.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜VideoDTO.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜VideoListViewResponse.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜VideoResponse.java
 ┃ ┃ ┃ ┃ ┃ ┗ 📜VideoViewResponse.java
 ┃ ┃ ┃ ┃ ┣ 📂repository
 ┃ ┃ ┃ ┃ ┃ ┣ 📜AdvertisementRepository.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜PlayHistoryRepository.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜RefreshTokenRepository.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜StatisticsRepository.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜UserRepository.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜VideoAdvertisementRepository.java
 ┃ ┃ ┃ ┃ ┃ ┗ 📜VideoRepository.java
 ┃ ┃ ┃ ┃ ┣ 📂service
 ┃ ┃ ┃ ┃ ┃ ┣ 📜PlayHistoryService.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜RefreshTokenService.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜StatisticsService.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜TokenService.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜UserService.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜VideoAdvertisementService.java
 ┃ ┃ ┃ ┃ ┃ ┗ 📜VideoService.java
 ┃ ┃ ┃ ┃ ┣ 📂util
 ┃ ┃ ┃ ┃ ┃ ┣ 📜CookieUtil.java
 ┃ ┃ ┃ ┃ ┃ ┗ 📜RandomNumberGenerator.java
 ┃ ┃ ┃ ┃ ┗ 📜ProjectApplication.java
 ┃ ┗ 📂resources
 ┃ ┃ ┣ 📂static
 ┃인
- 해결 방안 : 

### 광고 영상 시청시 정상적으로 조회수 증가가 되지 않는 문제

- 문제점 :
- 원인 :
- 해결 방안 :

## 성능 개선

