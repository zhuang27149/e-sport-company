## Where to find the fantastic e-sports companies:from news to reality



## 1.Introduction

### 1.1 Background
On August 2, 2011, at 3 am, Wang Sicong posted a microblog, “Strong entry, integration of e-sports(强势进入，整合电竞)”, with a picture of the logo of the IG Club which was experiencing a reorganization that time. With 500,000,000 yuan, Wang wanted to play a challenging game.
However, the post generated only little discussion. The spectators have no higher expectations for this young man who was born with a silver spoon: ordinary e-sports enthusiasts questioned his poaching behavior, and his pessimistic prediction of the decline of the e-sports industry. 5 hundred million did not provoke a splash in a broader market, when there was few media coverage of this event.
People never thought about that they would pay attention to this post after seven years, and make online comments like "IG is the champion" over and over again. Similarly, even those who were good at analysis and calculations did not expect e-sports would grow into an eye-catching market.
Nowadays, e-sports has got into the sights of more Chinese people, while what behind the glory is a barbaric growth of the e-sports industry. A variety of e-sports companies have sprung up in various cities, launching different projects.
Meanwhile, mainstream media's attitude towards e-sports is also gradually changing. But it only pays more attention to famous players and investors.
Hence, our project is motivated by such trend and we would like to examine the development of China’s e-sports companies from two dimensions: in reality and in news. We try to figure  the urban distribution of China’s e-sports-related companies, what factors may relate to it, how e-sports industry is reported in Chinese news and if there is any difference between the reality and news. 

### 1.2 Other works review
Previous works about e-sports mainly focus on e-sports players, teams and leading game companies. In terms of e-sports players, most  forms are feature stories and in-depth reports. GQ magazine did some profiles of famous e-sports players like Sky (Li Xiaofeng) and Uzi(Jian Zihao) .
Beyond the center of e-sports, there are some reports focusing on peripheral fields related to e-sports. DT Finance did a research about e-sports consumptive places, comparing the development of e-sports hotels in Zhengzhou and Shanghai. As a result, DT Finance found that the level of development of e-sports industry is not directly related to the rise of e-sports hotels, and e-sports hotels are more matched with the consuming  demands of game players in second and third-tier cities.
In terms of data mining and visualization, there's little reports about e-sports using data visualization. The paper, a new media of Shanghai, used data to explain the development of Shanghai’s e-sport industry. The sources were from industrial reports, including number of game players and revenue of big companies. 
To sum up, there's little visualized reports about e-sports field from the prospective of e-sports companies’ developing trend and urban distribution, which leaves space for our research.

### 1.3 Research Questions
Based on previous work and our own interest, we come up with our research questions:
RQ1.What is the development trend of Chinese e-sports-related companies?
RQ2.What’s the urban distribution of e-sports-related companies in China?
RQ3.What factors may relate to the development trend and urban distribution?
More specifically, what are the correlates of variation in e-sports development when comparing two cities?
Variables to be taken into consideration are as follows: politics (policy support/tax), economy (GDP, industrial structure), technology (average network speed, Internet access costs), population (population structure), industrial clusters (ACG companies), etc.
RQ4.How does Chinese news cover e-sports? Is there any difference between the reality and news?

## 2.Method
### 2.1 Data Source
Our data source includes three parts: data of e-sports-related companies, financial news related to e-sports and data of other factors.
#### 2.1.1 Data of e-sports-related companies:
Firstly, to acquire data of e-sports companies, we examined platforms like Tianyancha (https://www.tianyancha.com),Qichacha(https://www.qichacha.com) and Qixinbao (https://www.qixin.com). However, we found that the data on these platforms  was not open to the public, which means that we may face legal risks when crawling commercial data that it provides, so we bought a VIP account of Tianyancha.com to download the data we need.
When we collected  the data before downloading, the searching keywords were“电竞(the abbreviation of e-sports)” and “电子竞技(e-sports)”. In order to obtain accurate and valid data, we set some filters, including registered capital (over 1,000,000 RMB), industry classification ( companies belonging to “Information transmission, software and information technology services”, “Culture, sports and entertainment”, or “Business services”). After that, we got the data of e-sports-related companies that stored in excel.

#### 2.1.2 Data of e-sports financial news
Secondly, we selected Sina News as the website to scrape news. The reasons why we chose Sina News included that it was an integrated news portal which collected news from media, and that it had high-level searching filters. So, we searched for the keywords “电竞(the abbreviation of e-sports)” and “电子竞技(e-sports)” in Sina financial news reports, with the crawling fields including  headline of news, date of press release and source of news. 

#### 2.1.3 Data of other factors relating data source: 
Lastly, we wonder  if there are any other factors that relate to the developments of e-sports industry in different parts of China. To figure out this question, we collected three other dimensions of data: Average Network Speed, City GDP and Population structure. We obtain text reports of the average network speed in 2013-2016 in PDF version from China Broadband Rate Development Report (http://www.199it.com/archives/746376.html) and China Broadband Popularization Report (http://www.199it.com/archives/746376.html). As for City GDP and population structure, the source of them is National Bureau of Statistics(http://data.stats.gov.cn/easyquery.htm?cn=E0105). 

### 2.2 Data Acquisition
The picture below is one of our targeted webpages, Sina News, in inspecting mode.  We found that Sina News was built in html pages, so we used Request and Beautifulsoup modules to scrape and parse the pages. In the process of  data acquisition, we encountered two major difficulties: one was page looping and the other was source split. Financial news related to e-sports on Sina News were over 80 pages, so the address of website that we crawled was changing. Based on web observation, we found the rule of the changing page number of Sina News. Therefore, we controlled the page looping by generating a sequence of numbers that arranged in orders. 
Originanly, we decided to scrape the news pages where fields like titles and dates were structured. However, some of the news pages were deleted so we turned to crawl fields in search results pages. There was a new problem :most of the raw data were stored in the same line of code. To solve this problem, we split date and source from one list, as well as splitting year, month and day from date. After splitting data into appropriate classification, data cleaning became much easier to execute. 


![webpage](https://github.com/zhuang27149/e-sport-company/blob/master/images/webpage.png)


### 2.3 Data Processing
There are two parts of the data processing, one is data processing of Sina financial news of e-sports, and the other is data processing of e-sports related companies from Tianyancha.
#### 2.3.1 Data processing of sina.news
Firstly, the formats of data that we got from Sina News which was collected according to the keywords of “电竞”and “电子竞技” were  two CSV files. So, we merged two CSV files into one and dropped the duplicated data. Meanwhile, we aimed to look up news from the latest 10 years so we set conditions and got news from 2009 to 2018.
 
 ![rawdataofsinanews](https://github.com/zhuang27149/e-sport-company/blob/master/images/sinanews-raw.png)
(the raw data)


![cleandataofsinanews](https://github.com/zhuang27149/e-sport-company/blob/master/images/tianyancha-clean.png)
(the clean data)


#### 2.3.2 Data processing of tianyancha
Next, we cleaned the data from Tianyancha. On one hand,  the column of “注册资本(registered capital)”was string instead of numeric so it was unable to make a ranking.We transformed   the string type into numeric and created a new column called ’moneylist’, whose value can be sorted.
On the other hand, we only need data of years when the e-sports companies were established, while  the column of “成立日期(date of establishment)” contained too much information. So, we extracted the years and put them into a new list “years”.
After adjusting the column, the new data frame is as shownin this table below.


![cleandataoftianyancha](https://github.com/zhuang27149/e-sport-company/blob/master/images/tianyancha-clean.png)

 
## 3.Results
### 3.1 The development trend of China’s e-sports-related companies
After processing data from Tianyancha, as the chart below shows, the number of China’s e-sports-related companies have radically increased since 2014, especially in the last 3 years.

![developmenttrend](https://github.com/zhuang27149/e-sport-company/blob/master/images/National.svg)

 
### 3.2 The city distribution of China’s e-sports-related companies
In terms of the distribution of e-sports companies among provinces in China, Top ten provinces which have most e-sports companies are on the chart. We can see that Hainan Province has got most e-sports companies, followed by Guangdong Province.

![citydistribution](https://github.com/zhuang27149/e-sport-company/blob/master/images/Provinces.svg)

To be more specific, in Guangdong Province, the total number of e-sports-related companies is 273, among which Shenzhen takes up 213 while there are only 15 e-sports companies in Guangzhou.
 
![citydistribution-5places](https://github.com/zhuang27149/e-sport-company/blob/master/images/2.distribution-5places.png)
 
And this chart shows how many e-sports-related companies were established every year. The red line represents China and the blue one is Hainan which increases very rapidly.
In addition, we can see the registered capital of Hainan’s e-sports companies from the scatter chart. Most clustered in 100,000,000.

![capital](https://github.com/zhuang27149/e-sport-company/blob/master/images/2.capital.png)

Obviously, Hainan Province is playing an active role in e-sports industry which is quite different from our former impression. 
 
 
### 3.3 How news report e-sports in China
According to the chart, the amount of news reached peak which is 377 pieces in 2017. Also, since 2016, the amount has increased quickly. It shows the shifting of media attention. On the whole, the media still focus on famous inventors and big enterprises (such as Tencent and Blizzard), and the industrial center is Shanghai.
It is consistent with the development of e-sports companies in China to a certain extent, but there are also some abnormal situations. For example, Hainan.

![newsreport](https://github.com/zhuang27149/e-sport-company/blob/master/images/3.newsreport.png)
 

### 3.4 Factors relate to e-sports companies
Based on the above result, we find that as the flourish of the e-sports industry in China, the development gap of e-sports companies among different regions has been enlarged. We could not help wondering what factors lead to the varied degree of development of e-sports companies in different regions. In order to figure out  what differences and what factors are behind the phenomenon, we decided to select Hainan province and Shanghai as two representative regions for comparative analysis. On one hand, we chose Hainan province due to the above data results. Hainan Province unexpectedly has the largest number of e-sports companies, although in the public impression it is famous for tourism. On the other hand, we chose Shanghai, a first-tier city with a well-developed e-sports industry in public eyes. According to CNG’s report, more than 40% of e-sports competitions are held in Shanghai, as well as more than half of the top 20 well-known e-sports clubs in China have their head office in Shanghai, such as WE, iG, EDG and RNG. 
The chart shows the development trend of e-sports companies in this two places and Hainan surpassed Shanghai after 2017.

![shanghaivshainan](https://github.com/zhuang27149/e-sport-company/blob/master/images/Hainan%26Shanghai.svg)

However, when considering related factors, Shanghai surpasses Hainan in all aspects.
 
![factorsofshanghaivshainan](https://github.com/zhuang27149/e-sport-company/blob/master/images/4.factors.png)

Besides, we notice a government document《关于支持海南全面深化改革开放的指导意见(Guidance on supporting Hainan in comprehensively deepening reform and opening up)》 of General Office of the State Council, PRC, which was published in April of 20018, directly guides the development of Hainan province. It is said that “We will vigorously develop new cultural consumption, such as animation and games, Internet culture and digital content, and upgrade consumption of traditional culture” and “We will explore the development of competitive sports lottery and large international competitions that open lottery, explore ways to support the development of tourism projects in terms of space planning, land supply and resource utilization".
Sports lottery is supported by the government. Considering Hainan’s poor infrastructure, they pay more attention to Internet industry. And e-sports is the only field probably having competitive elements. That may be the reason why there are so many companies located in Hainan.

## Reference
[1]何书瑶. (2018). 魔都不相信电竞酒店. Retrieved from                
https://mp.weixin.qq.com/s?__biz=MzA5Mzk5MDM5MA==&mid=2650826650&idx=1&sn=ce79100ee862e9fffd6d60fd5673c473&chksm=8ba1bb03bcd63215b78583e323de8aa3931699dc0fec9405b36e06109a1cb0b3bc71f5ccb06a&scene=0&xtrack=1#rd
[2] 一图到底｜上海说要打造电竞之都，现在怎么样了？_美数课_澎湃新闻-The Paper. (2018). Retrieved from https://www.thepaper.cn/newsDetail_forward_2371575
[3]国家数据. (2018). Retrieved from http://data.stats.gov.cn/search.htm?s=%E4%B8%8A%E6%B5%B7
[4] 宽带发展联盟. (2018). 2018年Q1中国宽带速率状况报告(2018).[Ebook] (pp. 7-9). 
Retrieved from http://www.199it.com/archives/746376.html
[5] 伽马数据. (2018). 2018电子竞技产业报告(赛事篇). Retrieved from http://youxiputao.com/articles/15341
