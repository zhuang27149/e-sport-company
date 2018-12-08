## Where to find the fantastic e-sports companies:from news to reality



## 1.Introduction

### 1.1 Background
In 2018, the 18th Asian Games in Indonesia made the e-sports a formal project for the first time. In November of the same year, Chinese team IG won the 2018 League of Legends World Championship, leading to an increasing attention to e-sports on Chinese mainstream media and social media, which indicates an improvement on social recognition of e-sports. With the rise and recognition of major events, e-sports is expected to cover a very large market size with a potential of growth.

In 2017, the e-sports market in China has exceeded 65 billion yuan, far exceeding other cultural and creative industries such as literature and film. The e-sports industry is in a fast-growing incremental market. Leading companies like Tencent Entertainment, Ali Sports, Bilibili, famous investors like Wang Sicong, and other investment entities have entered the field of e-sports, bringing a large amount of funds to the upstream of the industrial chain through sponsorship of clubs. The e-sports industry with a complete industrial chain has become a new outlet. At present, the core of the e-sports industry is the event industry chain, including game R&D operations in upstream, events in mid-stream, e-sports media and live broadcast platforms in downstream.

Nowadays, e-sports has got into the sights of more Chinese people, while what behind the glory is a barbaric growth of the e-sports industry. With an upward trend and policy support, the development of China's e-sports industry is wild and noisy. A variety of e-sports companies have sprung up in various cities, launching different projects. Meanwhile, driven by some factors from politics, economy, technology etc., diverse patterns of development in e-sports industry have shown in different cities.

In our research, we’d like to figure out the development trend of China’s e-sports from two dimensions: in reality and news, like the city distribution of China’s e-sports-related companies, what factors may relate to them, how news reports e-sports in China and if there’s difference between the reality and news.
  
### 1.2 Other works review
Focus on e-sports players, teams and leading game companies. The main genres are feature stories and in-depth reports. For example，there are many profiles of some famous e-sport players like Sky(Li Xiaofeng ) and Uzi(Jian Zihao) on GQ magazine.
Besides，there are several reports using data visualization, but the principle sources are industrial reports, including number of game players and revenue of big companies which has rare analysis on relationship. For example, the paper, a new media of Shanghai has pay more attention on e-sports, they use data to explain the development of Shanghai’s e-sport industry.

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



### 2.3 Data Processing
The data processing contains two parts. One is data processing of sina.news and the other is data processing of tianyancha.
2.3.1 Data processing of sina.news
Firstly, about the data that we got from sina.news. According to the keyword ‘电竞’ and ‘电子竞技’, we got two csv.Then we merged this two csv into one and dropped the duplicated news. Meanwhile, we aim to look up news from recent 10 years so we set conditions and got news from 2009 to 2018.
 
(the raw data)

 
(the clean data)

#### 2.3.2 Data processing of tianyancha
Next, we cleaned the data from tianyancha. On one hand, for the column of ‘注册资本’ is string not numeric so it’ unable to make a ranking, so we change this string into numeric and create a new list which is called ’moneylist’. And its value can be sorted.
On the other hand, we only need data of year when the e-sports companies established, however the column of ‘成立日期’ contains too much information. So we spited it and created a new list ‘years’.
The new data frame is like this.

 
## 3.Results
### 3.1 The development trend of China’s e-sports-related companies
After processing of data from tianyancha, we can see the whole development trend of China’s e-sports-related companies, that it shows radical increase since 2014, especially in recent 3 years.
 
### 3.2 The city distribution of China’s e-sports-related companies
From the distribution of e-sports companies among provinces in China, Top ten provinces which have most e-sports companies are on the chart. We can see that over 40% e-sports companies are in Hainan Province and Guangdong Province, which is quite different from our impression.

To be more specific, in Guangdong Province, the total number of e-sports related companies is 273 , Shenzhen takes up 213 while there are only 15 e-sports companies in Guangzhou.
 

And this chart shows how many e-sports-related companies establishing every year. The red line represents China, the blue one is Hainan which increases very rapidly.
In addition, we can see the registered capital of Hainan’s e-sports companies from the scatter chart. Most clustered in 100,000,000.
Obviously, Hainan Province plays an active role in e-sports companies which is quite from our former impression. 
 
### 3.3 How news report e-sports in China
According to the chart, the amount of news reached peak which is 377 pieces in 2017. Also, from 2016, the amount increases quickly. It shows the shifting of media attention. On the whole, the media still focus on famous inventors and big companies(such as Tencent and Blizzard), and the geographical center is Shanghai.
It is consistent with the development of e-sports companies in China to a certain extent, but there are also some abnormal situations. For example, Hainan.
 

### 3.4 Factors relate to e-sports companies
In order to see what differences between them and what factors behind the phenomenon. In our analysis, we choose Hainan Province which has most number of e-sports companies, Shanghai which is a traditional advanced e-sports city in public eyes to see their differences.
As you can see, Shanghai surpasses Hainan in all aspects.
 
However, we find a government document of General Office of the State Council, PRC（国务院），which directly guide the development of Hainan province. Sports lottery is supported by the government. Considering Hainan’s poor infrastructure, they paid more attention to internet industry. And e-sports is the only field having competitive elements. That is maybe the reason why there are so many companies located in Hainan.





```markdown
Syntax highlighted code block

# Hello？
## Can you hear me clearly？
### let‘s see something interesting！

- Bulleted
- List

1. Numbered
2. List

<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>ECharts</title>
    <!-- 引入 echarts.js -->
    <script src="echarts.min.js"></script>
</head>
<body>
    <!-- 为ECharts准备一个具备大小（宽高）的Dom -->
    <div id="main" style="width: 600px;height:400px;"></div>
    <script type="text/javascript">
        // 基于准备好的dom，初始化echarts实例
        var myChart = echarts.init(document.getElementById('main'));

        // 指定图表的配置项和数据
        var option = {
            title: {
                text: 'ECharts 入门示例'
            },
            tooltip: {},
            legend: {
                data:['销量']
            },
            xAxis: {
                data: ["衬衫","羊毛衫","雪纺衫","裤子","高跟鞋","袜子"]
            },
            yAxis: {},
            series: [{
                name: '销量',
                type: 'bar',
                data: [5, 20, 36, 10, 10, 20]
            }]
        };

        // 使用刚指定的配置项和数据显示图表。
        myChart.setOption(option);
    </script>
</body>
</html>

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/zhuang27149/e-sport-company/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
