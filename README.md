# finda
핀다 리뷰 데이터 분석  

### 핀다 소개

핀다는 대출중계 플랫폼으로서 금융사과 고객의 중간에서 다양한 대출 정보들을 고객이 파악할 수 있도록 서비스를 제공하고 있습니다.
핀다에서 제공하는 서비스들은 다음과 같습니다.  

1) 고객이 대출할 수 있는 금융사들을 한번에 조회하여 고객에 맞는 대출 상품을 찾아준다.  
2) 현재 대출을 하고 있는 고객은 현재 이용하고 있는 상품보다 더 적은 금리의 상품을 찾아, 대환할 수 있도록 정보를 제공한다.  
3) '나의 대출 관리' 서비스를 통해 현재 대출 현황을 파악하여 상환할 수 있도록 돕고 있다.  

### 문제 정의

현재 고객들의 이탈을 방지하고 더 많은 신규 고객 유입을 위해서는 지속적인 서비스 발전 및 개선이 필요합니다.

서비스를 발전/개선시키기 위해서 가치 있는 인사이트를 얻는 방법은 아래와 같습니다.

1) 플랫폼을 이용하는 고객들의 로그 데이터 분석
2) 홈페이지 문의글 또는 앱 스토어에 남긴 리뷰들을 분석

물론 이외에도 다양한 방법이 존재하겠지만 여기서는 2가지 방법을 소개합니다.  
이번 프로젝트에서는 구글 플레이 스토어에 남겨진 핀다의 리뷰들을 통해 사용 고객들의 만족도 및 니즈를 파악하기 위한 분석을 실시합니다.  

### 데이터 분석 프로세스
 
핀다 리뷰 데이터 분석 프로세스는 다음과 같습니다.

1) 구글 플레이 스토어에서 핀다 앱에 대한 리뷰를 스크래핑한다. (데이터 수집은 2022년 07월 21일 기준으로 수집하였음)  
   코드 : https://github.com/taesoocho/finda/blob/main/code/review_scraping.ipynb
2) 키워드 분석을 통해 비정형 데이터를 정제한다.
3) 분석 과정을 통해 얻어낸 정보를 시각화하여 정리한다.  
   코드 : https://github.com/taesoocho/finda/blob/main/code/visualization.ipynb

### 데이터 시각화

#### 1. 핀다 앱 이용자의 평가점수 시각화
<img src= https://user-images.githubusercontent.com/50400392/180953492-9590216a-18b9-4e02-8352-8b4c4d406332.png : width="600" height="600"/>

현재 안드로이드를 통해 서비스를 이용하는 고객들은 4명중 3명이 서비스에 매우 만족하고 있습니다.  
또한, 리뷰점수를 1점으로 평가한 고객들은 약 14%의 비중을 갖으며 2번째로 많았습니다.  

![ppt1_리뷰평가_시계열](https://user-images.githubusercontent.com/50400392/181168333-040b1c9c-d5f5-4890-b45f-69b15d78853e.png)

해당 그림은 년도별 평가점수가 어떻게 달라졌는지를 나타내었습니다. 
막대 그래프 위의 숫자는 평가점수를, 그래프 내부에 있는 텍스트는 리뷰 개수를 의미합니다.  

2018 ~ 2019년에는 리뷰 개수가 적었으며, 평가점수도 3점대를 기록하였습니다.
2020년에는 전년도 대비 리뷰 개수가 2000% 증가하였고 평가점수 또한, 1.25% 증가하였습니다.
2021년은 전년도 대비 리뷰 개수 200% 증가하였고 2022년에는 데이터 수집 날짜 기준 약 5개월의 기간이 남았음에도 불구하고 리뷰개수가 증가하는 추세이며 평가점수도 향상되었음을 알 수 있습니다.

#### 2. 긍정적 / 부정적 리뷰 동향 시각화

'핀다 앱 이용자의 평가점수 시각화'에서는 평가점수를 기준으로 관찰하였다면 이번에는 월별 리뷰의 개수를 기준으로 시각화를 진행하였습니다.  
긍정 리뷰는 리뷰 점수가 4점 이상인 경우를 뜻하고 부정 리뷰는 3점 이하인 경우를 말합니다.

![ppt2_긍정부정_시계열](https://user-images.githubusercontent.com/50400392/180953518-f1e9bb8d-f53f-43f4-8f00-b84a39fec97b.png)

2021년 04월에 '나의 대출관리' 서비스가 리뉴얼되면서 전달 대비 약 3배의 성장이 있었습니다.
2021년 09월에 대부상품을 중계 서비스를 시작한 이후, '전화'나 '스팸', '광고' 등의 부정적인 리뷰가 증가하였습니다.
서비스에 차질이 생기다보니 긍정적인 리뷰는 상대적으로 줄어들었습니다.
마지막으로 2022년 04월에 마이데이터를 연계하여 고객들에게 더 정확한 정보를 제공할 수 있게 되면서 고객들의 긍정적인 반응을 볼 수 있었습니다.

#### 3. 긍정적 / 부정적 키워드 동향 시각화

위에서 긍정적 / 부정적 '리뷰'의 동향을 살펴보았습니다.  
긍정적 / 부정적인 반응을 보이는 '키워드'는 무엇이 있을까요?

![ppt3_긍정키워드](https://user-images.githubusercontent.com/50400392/180953548-34b8bf81-dbda-4686-92f7-3a80b1ebce43.png)

긍정적인 반응에 가장 많은 빈도수를 보인 키워드는 '대출', '금리', '조회' 순으로 나타났습니다.  

'대출'에 대한 긍정적인 반응은 약 80%이며 20%는 부정적인 반응을 보였으며 리뷰에서 언급되는 횟수가 다른 키워드에 비해 월등히 높습니다.  

'금리'는 추가적인 대출을 할 때, 금리에 만족하는 경우도 있을 수 있지만 대부분 리뷰에서 '금리'는 대환 서비스에 관련된 내용으로 파악됩니다.  
'금리'를 언급한 리뷰 고객들 중 82%가 긍정적인 평가는 보였습니다.  

'조회'는 긍정적인 키워드 빈도수 3위이지만 부정적인 평가도 많은 비중을 나타낸 키워드입니다.   
여러 금융사를 한번의 조회로 다양한 정보를 얻을 수 있어서 긍정적인 평가를 받았지만 조회를 너무 과도하게한 경우, 신용점수가 하락하는 등 부정적인 반응도 많았습니다.

![ppt3_부정키워드](https://user-images.githubusercontent.com/50400392/180953557-060750b3-fd54-401d-b3ed-21034765a3cd.png)

부정적인 평가를 보인 리뷰들 중에서 많은 빈도수를 가진 키워드는 '전화'와 '광고'입니다.  
x축은 키워드의 빈도수를 나타내며 y축은 과거에서 현재까지를 나타냅니다.  
대부중계 상품을 출시한 이후 스팸이나 광고 전화를 수십통씩 받아 불편하다는 의견이 많았으나, 최근에는 서비스를 개선하여 전화가 가지 않도록 노력함에 따라 많이 줄어든 모습을 볼 수 있었습니다.  
'광고'는 스팸 전화와 관련된 내용이 있었으나 최근에는 핀다 광고(간편 대출)와의 괴리감을 느껴 부정적인 반응을 나타내고 있습니다.  

### 데이터 분석 결과

- 핀다 앱을 사용하는 고객들은 꾸준히 증가하고 있으며, 앱에 대한 평가도 긍정적인 반응이 증가하고 있습니다.
- 대부상품 중계 서비스를 시작하며 스팸(광고) 전화에 대한 이슈가 발생하였으나 이를 잘 개선한 것을 파악할 수 있었습니다.
- '대출' 키워드에 대해 80%는 만족하고 20%는 만족하지 못합니다. 대출 서비스에서 서비스의 오류로 인해 발생하는 것인지, 추가적인 대출이 불가능한 상황인지 내부 데이터를 통해 확인하고 개선하는 과정이 필요합니다.
- '조회' 키워드는 마이데이터 연계를 통해 더욱 정확하게 정보를 제공할 수 있게 됨에 따라 부정적인 반응이 많이 감소하였습니다. 하지만 조회를 과도하게 진행하여 서비스를 제대로 이용할 수 없는 고객이 발생됨에 따라, 조회를 과도하게 하지 않도록 경고 문구나 이에 대한 설명을 고객이 잘 인지할 수 있도록 UX 개선을 통한 A/B Test를 진행한다면 좋을 것으로 생각됩니다.  
- 부정적 키워드에서 '전화'는 스팸 차단 기능을 통해 해결하였습니다.  
- '광고'는 간편하게 대출이 가능하다는 광고에 부정적인 평가를 받았었다. 22년 07년 23일 기준으로 '대출을 능동적으로 활용할 수 있다.'라는 메세지를 담은 새로운 광고를 선보였다.  이전 광고와의 비교 분석하여 OKR을 달성할 수 있을지 지속적인 모니터링이 필요할 것으로 보입니다.

### 마치며

핀다 리뷰 분석 프로젝트를 진행하면서 고객분들이 직접 작성한 리뷰를 통해 서비스의 좋은 점과 문제점을 파악할 수 있었습니다.  

거시적으로는 리뷰의 수나 리뷰 평가 점수에서는 플랫폼이 성장 및 발전하고 있다는 것을 파악할 수 있었지만, 주요 서비스에서 부정적인 평가도 일정 부분 차지하고 있었고 이를 관찰함으로서 부족한 점을 알 수 있었습니다.  
또한, 부정적 키워드에 대해 관찰함으로서 서비스를 이용하면서 불편한 점을 파악할 수 있었고 시간 흐름에 따라 해당 문제점이 개선되고 있음을 파악할 수 있었습니다.  

해당 분석을 통해 서비스에 문제점을 고객이 이탈하기 이전에 파악하고 대처함으로서 이탈 방지할 수 있는 인사이트를 도출하였습니다.
