## Where to find the fantastic e-sports companies:from news to reality



## 1.Introduction

### 1.1 Background
On August 2,2011, at 3 am, Wang Sicong posted a microblog, “Strong entry, integration of e-sports(强势进入，整合电竞)”, with a picture of the logo of the IG Club which was experienceda reorganization that time. With five hundred million yuan, Wang wanted to paly a chanllenging game.
However, the post received only little discussion.The waiters have no higher expectations for this rich second generation: ordinary e-sports enthusiasts question his poaching behavior, and pessimistic predictions of the decline of the e-sports industr; 5 hunderd billion did not provoke a splash in the broader market,there was few media coverage of the incident.
People never thought about that they would pay attention to this post after seven years, and send the comments like "IG is champion" over and over again. Similarly, those who are good at analysis and calculations did not expect e-sports would grow into a eye-catching market.
Nowadays, e-sports has got into the sights of more Chinese people, while what behind the glory is a barbaric growth of the e-sports industry. A variety of e-sports companies have sprung up in various cities, launching different projects.
Meanwhile, mainstream media's attitude towards e-sports is also gradually changing. But it only pay more attention to famous players and investors.
Hence, our project is motivated by such trend and we would like to examine the development of China’s e-sports companies from two dimensions: in reality and in news. Like the city distribution of China’s e-sports-related companies, what factors may relate to them, how e-sports is reported in Chinese news and if there is any difference between the reality and news. 
  
### 1.2 Other works review
Previous works about e-sports mainly focus on e-sports players, teams and leading game companies. In terms of e-sports players, most of the forms are feature stories and in-depth reports. GQ magazine did some profiles of famous e-sports players like Sky(Li Xiaofeng) and Uzi(Jian Zihao) .
What's more, there are some reports focusing on fields related to e-sports.DT Finance focuses on e-sports consumptive places, comparing the development of e-sports hotels in Zhengzhou and Shanghai. As a result, DT Finance found that the level of development of e-sports industry is not directly related to the rise of e-sports hotels, and e-sports hotels are more matched with the consumer demands of game players in second and third-tier cities.
In terms of visualizaion, there's little reports using data visualization about e-sporsts . The paper, a new media of Shanghai, used data to explain the development of Shanghai’s e-sport industry. The sources are from industrial reports, including number of game players and revenue of big companies. 
To sum up, there's little visualized reports about e-sports field considering e-sports companies's developing trend, city distribution, what factors relate to them and how news reports them.

### 1.3 Research Questions
Based on previous work and our own interest, we come up with our research questions :
RQ1.What is the development trend of China's e-sports-related companies?
RQ2.What’s the city distribution of China’s e-sports-related companies?
RQ3.What factors may relate to e-sports-related companies?
To be more specific, when comparing two cities, what are the correlates of variation in e-sports development?
Variables maybe take into consideration: politics (policy support/tax), economy (GDP, industrial structure), technology (average network speed, Internet access costs), population (population structure), industrial clusters (ACG companies), etc.
RQ4.How news reports e-sports in China? Are there difference between the reality and news?

## 2.Method
### 2.1 Data Source
Our data source includes three parts: data of e-sports-related companies, news and data of other factors.
#### 2.1.1 Data of e-sports-related companies:
Firstly, to acquire data of e-sports companies, we thought of platforms like Tianyancha , Qichacha and qixinbao. However, the data is not open to the public.We may face legal risks with crawling commercial data that it provides, so we bought  a VIP account of Tianyancha.com to download the data we need.

When we download the data, the searching keyword is “电竞”, and we set some filters, including registered capital(over 1,000,000 RMB); Industry classification( belong to ‘Information transmission, software and information  technology services’, ‘Culture, sports and entertainment’, or ‘Business services’.)And we got a excel.

Source: 
企查查:https://www.qichacha.com/;
天眼查:https://www.tianyancha.com;
启信宝:https://www.qixin.com/?from=wap
Searching keywords: “电竞（e-sports）”, “电子竞技（e-sports）” ；
Crawling fields: “name”, “establishment time”, “registered capital”, “address”
Difficulties:(1) Facing legal risks with crawling commercial data that it provides. (2) It’s hard to overcome the anti-crawler limitation; 
Solutions:(1) Buy a VIP account to download the data we need. We choose Tianyancha.com to get e-sports companies list.
Searching Keyword’: ‘电竞’;’
Filter: registered capital: over 1,000,000 RMB; registered in mainland of China; Industry classification: belong to ‘Information transmission, software and information  technology services’, ‘Culture, sports and entertainment’, or ‘Business services’.

#### 2.1.2 Data of news
Secondly, we choose sina.com as the website to scrape. The reasons why we choose sina.com are that it’s an integrated news portal which collects news from media, and it has high-level searching filters. We search keywords ‘电竞’&‘电子竞技’ in financial reports.
News report: scrape news headlines
Source: https://news.sina.com.cn/
Searching keywords: “电竞(e-sports)”，“电子竞技（e-sports）”etc.
Crawling fields: headlines, date, source

#### 2.1.3 Data of other factors relating data source: 
(1) Average Network Speed: 
Source: text report in PDF version from 2013-2016
China Broadband Rate Development Report (http://www.199it.com/archives/746376.html)
China Broadband Popularization Report (http://www.199it.com/archives/733826.html)
(2) City GDP:
Source: National Bureau of Statistics (http://data.stats.gov.cn/easyquery.htm?cn=E0105)
(3) Population structure:
Beijing population structure
Source: Beijing Municipal Bureau of Statistics (http://tjj.beijing.gov.cn/nj/main/2017-tjnj/zk/indexch.htm)
Shanghai population structure
Source: Shanghai Statistical Yearbook (http://tjj.sh.gov.cn/html/sjfb/201801/1001529.html)


### 2.2 Data Acquisition
We choose sina.com as the website to scrape and the picture is a screen snapshot of the targeted webpages and “inspecting the element” window. It is a html page, and we use Beautifulsoup and request to scrape the pages. There are two major difficulties here: one is page looping and another is source split. Based on web observation, we find the rule of the page number changing. Therefore we control the page looping changing by generating sequence. Besides, we split date and source form one list；meanwhile，we split year，month and day from date. That help us a lot in data cleaning.

![webpage](https://github.com/zhuang27149/e-sport-company/blob/master/images/webpage.png)


### 2.3 Data Processing
The data processing contains two parts. One is data processing of sina.news and the other is data processing of tianyancha.
2.3.1 Data processing of sina.news
Firstly, about the data that we got from sina.news. According to the keyword ‘电竞’ and ‘电子竞技’, we got two csv.Then we merged this two csv into one and dropped the duplicated news. Meanwhile, we aim to look up news from recent 10 years so we set conditions and got news from 2009 to 2018.
 
 ![rawdataofsinanews](https://github.com/zhuang27149/e-sport-company/blob/master/images/sinanews-raw.png)
(the raw data)


![cleandataofsinanews](https://github.com/zhuang27149/e-sport-company/blob/master/images/tianyancha-clean.png)
(the clean data)


#### 2.3.2 Data processing of tianyancha
Next, we cleaned the data from tianyancha. On one hand, for the column of ‘注册资本’ is string not numeric so it’ unable to make a ranking, so we change this string into numeric and create a new list which is called ’moneylist’. And its value can be sorted.
On the other hand, we only need data of year when the e-sports companies established, however the column of ‘成立日期’ contains too much information. So we spited it and created a new list ‘years’.
The new data frame is like this.

![cleandataoftianyancha](https://github.com/zhuang27149/e-sport-company/blob/master/images/tianyancha-clean.png)

 
## 3.Results
### 3.1 The development trend of China’s e-sports-related companies
After processing of data from tianyancha, we can see the whole development trend of China’s e-sports-related companies, that it shows radical increase since 2014, especially in recent 3 years.

![developmenttrend](https://github.com/zhuang27149/e-sport-company/blob/master/images/1.developmenttrend-China.png)

 
### 3.2 The city distribution of China’s e-sports-related companies
From the distribution of e-sports companies among provinces in China, Top ten provinces which have most e-sports companies are on the chart. We can see that Hainan Province has got most e-sports companies, next is Guangdong Province.

![citydistribution](https://github.com/zhuang27149/e-sport-company/blob/master/images/2.Distribution-China.png)

To be more specific, in Guangdong Province, the total number of e-sports related companies is 273 , Shenzhen takes up 213 while there are only 15 e-sports companies in Guangzhou.
 
![citydistribution-5places](https://github.com/zhuang27149/e-sport-company/blob/master/images/2.distribution-5places.png)
 
And this chart shows how many e-sports-related companies establishing every year. The red line represents China, the blue one is Hainan which increases very rapidly.

![citydistribution-5places](https://github.com/zhuang27149/e-sport-company/blob/master/images/2.city-distribution-5placesincrease.png)

In addition, we can see the registered capital of Hainan’s e-sports companies from the scatter chart. Most clustered in 100,000,000.

![capital](https://github.com/zhuang27149/e-sport-company/blob/master/images/2.capital.png)

Obviously, Hainan Province plays an active role in e-sports companies which is quite from our former impression. 
 
 
### 3.3 How news report e-sports in China
According to the chart, the amount of news reached peak which is 377 pieces in 2017. Also, from 2016, the amount increases quickly. It shows the shifting of media attention. On the whole, the media still focus on famous inventors and big companies(such as Tencent and Blizzard), and the geographical center is Shanghai.
It is consistent with the development of e-sports companies in China to a certain extent, but there are also some abnormal situations. For example, Hainan.

![newsreport](https://github.com/zhuang27149/e-sport-company/blob/master/images/3.newsreport.png)
 

### 3.4 Factors relate to e-sports companies
In order to see what differences between them and what factors behind the phenomenon. In our analysis, we choose Hainan Province which has most number of e-sports companies, Shanghai which is a traditional advanced e-sports city in public eyes to see their differences.
In order to see what differences between them and what factors behind the phenomenon. In our analysis, we choose Hainan Province which has most number of e-sports companies, Shanghai which is a traditional advanced e-sports city in public eyes to see their differences. The chart shows the development trend of e-sports companies in this two places and Hainan surpassed Shanghai after 2017.

![shanghaivshainan](https://github.com/zhuang27149/e-sport-company/blob/master/images/4.shanghaivshainan.png)

However, when considering relating factors, Shanghai surpasses Hainan in all aspects.
 
![factorsofshanghaivshainan](https://github.com/zhuang27149/e-sport-company/blob/master/images/4.factors.png)

Besides, we find a government document《关于支持海南全面深化改革开放的指导意见(Guidance on supporting hainan in comprehensively deepening reform and opening up)》 of General Office of the State Council, PRC, which was published in April of 20018, directly guides the development of Hainan province. It is said that "We will vigorously develop new cultural consumption, such as animation and games, Internet culture and digital content, and upgrade consumption of traditional culture" and "We will explore the development of competitive sports lottery and large international competitions that open lottery,explore ways to support the development of tourism projects in terms of space planning, land supply and resource utilization".
Sports lottery is supported by the government. Considering Hainan’s poor infrastructure, they paid more attention to internet industry. And e-sports is the only field having competitive elements. That is maybe the reason why there are so many companies located in Hainan.

Reference
[1]何书瑶. (2018). 魔都不相信电竞酒店. Retrieved from                
https://mp.weixin.qq.com/s?__biz=MzA5Mzk5MDM5MA==&mid=2650826650&idx=1&sn=ce79100ee862e9fffd6d60fd5673c473&chksm=8ba1bb03bcd63215b78583e323de8aa3931699dc0fec9405b36e06109a1cb0b3bc71f5ccb06a&scene=0&xtrack=1#rd
[2] 一图到底｜上海说要打造电竞之都，现在怎么样了？_美数课_澎湃新闻-The Paper. (2018). Retrieved from https://www.thepaper.cn/newsDetail_forward_2371575
[3] 国家数据. (2018). Retrieved from http://data.stats.gov.cn/search.htm?s=%E4%B8%8A%E6%B5%B7
[4] 宽带发展联盟. (2018). 2018年Q1中国宽带速率状况报告 [Ebook] (pp. 7-9). 
Retrieved from http://www.199it.com/archives/746376.html



