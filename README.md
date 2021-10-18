# Shinhaninvest(Code : 코드 폴더)



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
#####   a. 채널 마다 variables=%7B%22id%22%3A% 이후 부분이 다름
#####   b.URL json에 다음페이지 번호있음 (js['page_info']['end_cursor'][:-2])
######    > URL을 규칙적으로 알 수 있어서 굳이 selenium 안써도 될 것 같았으나 request모듈로는 request error 발생 
######    > Viewbot 방지?
#####   c.date가 timestamp 형식으로 적혀있음
#####   d.while문 돌다가 로그인하라는 페이지 나올 수 있음 
#####     > 로그인하면 그뒤로는 계속 크롤링 가능

### E. News
#### - Web : Naver news
#### - module : Request(get), bs4
#### - Period : 17.01.03 ~ 21.07.19
#### - 특징
#####   a. 뉴스의 양이 너무 많아 파악하기 일자별 토픽을 파악하기 힘듦
######    > 기존 방향(시점별 투자선호 업종과 이슈 파악)을 위해서는 비슷한 주제 뉴스를 묶고 중요도 순으로 그룹 당 대표 뉴스 노출(분석과제)


## 2. 분석(출처 : https://ratsgo.github.io/natural%20language%20processing/2017/03/13/graphnews/)
### Graph-based News Representation(네트워크 이론기반)
#### - 가정
##### a. 중요한 뉴스 기사라면 모든 언론사가 취급하기에 비슷한 뉴스가 많을 것이다.
##### b. 중요한 기사는 제목이나 키워드가 비슷할 것이다.
#### - 방법
##### a. 연결 중심성(Degree Centrality)
##### b. 고유백터 중심성(Eigenvector Centrality)
#### - 한계
##### a. 기사 제목만으로 Clustering 했기 때문에 시점(하루)에 이슈 파악은 가능하나 내용을 기준으로 대표를 뽑은 것이 아니기에 정말로 대표할만한지..? >> 기사까지 수집한 후 중심문장 요약하는 형태가 좀 더 맞을 것 같기도...(Text Rank https://lovit.github.io/nlp/2019/04/30/textrank/)
##### b. 출처의 내용처럼 단독과 같은 특정 언론사에서 보도한 내용인 경우(알고리즘상 하위에 노출) >> 가정에 반하는 케이스
##### c. 원하는 단어 중심으로 그룹화가 가능할지..?(기업을 중심으로.., 부정 or 긍정 etc) >> 가중치..?
