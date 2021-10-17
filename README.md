# Shinhaninvest

## 1. 데이터 크롤링

### A. KOSPI 
#### - WEB : KRX
#### - Module : Requests(POST, GET)
#### - Period : 17.01.01 ~ 21.07.31

### B. Naver Finance
#### - WEB : NAVER Finnace
#### - Module : Requests(get), bs4
#### - Period : 01.01.03 ~ 21.07.19

### C. Eifomax
#### - Web : Eifomax
#### - Module : Selenium, bs4
#### - Period : 08.01.01 ~ 21.07.31

### D. News
#### - Web : Instagram(CNBC & Herald)
#### - module : Selenium, bs4
#### - Period : 17.01.03 ~ 21.07.19
#### - URL 특징
##### a. 채널 마다 variables=%7B%22id%22%3A% 이후 부분이 다름
##### b.URL json에 다음페이지 번호있음 (js['page_info']['end_cursor'][:-2])
###### > URL을 규칙적으로 알 수 있어서 굳이 selenium 안써도 될 것 같았으나 request모듈로는 request error 발생 
###### > Viewbot 방지?
##### c.date가 timestamp 형식으로 적혀있음
##### d.while문 돌다가 로그인하라는 페이지 나올 수 있음 
##### > 로그인하면 그뒤로는 계속 크롤링 가능

### E. News
#### - Web : Naver news
#### - module : Request(get), bs4
#### - Period : 17.01.03 ~ 21.07.19
#### - 특징
##### a. 뉴스의 양이 너무 많아 파악하기 일자별 토픽을 파악하기 힘듦
###### > 기존 방향(시점별 투자선호 업종과 이슈 파악)을 위해서는 비슷한 주제 뉴스를 묶고 중요도 순으로 그룹 당 대표 뉴스 노출(분석과제)

