# The Effect of Non-Fungible Token (NFT) Security Incident on Market Trading Volumes - A Case Study of 2022 OpenSea's Daily Volumes on Ethereum
## General Information
- **Author**: Xintong Wu, Computation and Design / digital media, Class of 2025, Duke Kunshan University
- **Instructor**: Prof. Luyao Zhang, Duke Kunshan University
- **Disclaimer**: Submissions to the Final Project for STATS201: Introduction to Machine Learning for Social Science, 2023 Spring Term (Seven Week - First) instructed by Prof. Luyao Zhang at Duke Kunshan University.
- **Acknowledgments**:  I would like to thank Prof. Luyao Zhang for the guidance on machine learning methods for causal inference and the constructive comments on my causal inference research design. Thanks to Yiyang Zhang for her tips on my data analysis methods. Thanks to Shiran Yuan for his peer evaluation for helping me improve my work. Thanks to all STATS201 classmates for the wonderful class atmosphere this session!

## Project Summary
- **Background and Motivation**: In 2022, after a rapid growth phase in non-fungible tokens (NFTs) over the past year, the global market is beginning to transition to a stable phase, with a bear market in the crypto market. (Wood 2022). In June, the global market traded for only $1.04 billion, down 74% sequentially compared to the $4 billion traded in May, marking the largest decline in global NFT trading. (Marketplaces Archives 2023). On June 1, 2022, Nate Chastain, a former product manager at OpenSea, the world's largest NFT trading platform, was arrested by U.S. law enforcement on charges of wire fraud and money laundering in connection with insider trading in NFTs. (U.S. Attorney's Office 2022). This significant incident reflects a general security gap in the NFT trading market. 
- **Research Question**: How do reports of security incidents related to NFT privacy affect the trading volume of related platforms on Ethereum?
- **Application Scenario (Data Source)**: OpenSea platform daily trading volume on Ethereum (in ETH) on Dune Analytic in 2022. ("OpenSea Daily Volume (Ethereum) in ETH" 2023). A total of one dataset with 365 data items is involved.
- **Methodology**: The researcher applies a machine learning approach of causal inference in this study. Firstly, set a causal event according to the focus problem and draw a predictive image using a whiteboard tool. (The Visual Workspace 2023). Secondly, proposed two hypotheses about the impact of NFT security incidents on the platform's Ethereum trading volume. Finally, used Scikit-learn Regression Class to calculate and draw the graph to determine the degree of fitness and had the conclusion.
- **Results**: The study found that the omission regarding the NFT security incident did have a significant negative impact on the trading volume of the platform in question and led to a market downturn for at least the next six months.
- **Intellectual Merits and Practical impacts**: 
  - This study demonstrates that the occurrence of security incidents can harm the trading market, highlights the limitations of long-standing security breaches in the industry, and contributes to the analysis of NFT's market direction. 
  - At the same time, the study provides directions for future improvements and optimizations in the crypto-sphere market. In the future, the market should accurately define the criteria for NFT security standards, and address the user's privacy and security. 
  - The study also has limitations. Only the current year's trading volumes in 2022 are covered, and subsequent data are not further studied; the trading volume of the NFT market usually changes dramatically at the beginning of each year, so the model cannot make accurate predictions for the market conditions in subsequent years.



## Table of Contents
- [Data](https://github.com/Rising-Stars-by-Sunshine/stats201-Final_Project-Xintong/blob/main/README.md#data)
- [Code](https://github.com/Rising-Stars-by-Sunshine/stats201-Final_Project-Xintong/blob/main/README.md#code)
- [Spotlight](https://github.com/Rising-Stars-by-Sunshine/stats201-Final_Project-Xintong/blob/main/README.md#spotlight)
- [More about the Author](https://github.com/Rising-Stars-by-Sunshine/stats201-Final_Project-Xintong/blob/main/README.md#more-about-the-author)
- [References](https://github.com/Rising-Stars-by-Sunshine/stats201-Final_Project-Xintong/blob/main/README.md#references)


## Data
Prediction Data Source: https://dune.com/queries/2004005

### Meta Data Infomation

| Data Files  | Data Type | Data Content |
| ------------- | ------------- | ------------- |
| [literature.csv](https://github.com/Xintong1122/stats201-PS2-Exlanation-Prediction-Xintong/blob/main/data/NLP/literature.csv)  | Queried  | 15 "NFT Challenge" journal's topic and abstract  |
| [title_bigram.csv](https://github.com/Xintong1122/stats201-PS2-Exlanation-Prediction-Xintong/blob/main/data/NLP/title_bigram.csv)  | Processed  | 15 "NFT Challenge" journal's title bigram  |
| [abstract_bigram.csv](https://github.com/Xintong1122/stats201-PS2-Exlanation-Prediction-Xintong/blob/main/data/NLP/abstract_bigram.csv)  | Processed  | 15 "NFT Challenge" journal's abstract bigram  |
| [queried_data.csv](https://github.com/Xintong1122/stats201-PS2-Exlanation-Prediction-Xintong/blob/main/data/Queried_Data/queried_data.csv)  | Queried  | 2022 OpenSea Daily Volume (Ethereum) in ETH  |
| [Regression_Train.csv](https://github.com/Xintong1122/stats201-PS2-Exlanation-Prediction-Xintong/blob/main/data/Processed_Data/Regression_Train.csv)  | Processed  | Training data for regression  |
| [Regression_Test.csv](https://github.com/Xintong1122/stats201-PS2-Exlanation-Prediction-Xintong/blob/main/data/Processed_Data/Regression_Test.csv)  | Processed  | Testing data for regression  |

### Data Dictionary

| File Name  | Variable Name | Description | Frecuency | Unit | Type |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| [literature.csv](https://github.com/Xintong1122/stats201-PS2-Exlanation-Prediction-Xintong/blob/main/data/NLP/literature.csv)  | Title  | titles of 15 journals  | 1  | None  | str  |
|   | Abstract  | abstract of 15 journals  | 1  | None  | str  |
| [title_bigram.csv](https://github.com/Xintong1122/stats201-PS2-Exlanation-Prediction-Xintong/blob/main/data/NLP/title_bigram.csv)  | bigram  | title's bigram  | None  | None  | tuple  |
|   | 	counts  | counts of each bigram  | None  | None  | int  |
| [abstract_bigram.csv](https://github.com/Xintong1122/stats201-PS2-Exlanation-Prediction-Xintong/blob/main/data/NLP/abstract_bigram.csv)  | bigram  | abstract's bigram  | None  | None  | tuple  |
|   | 	counts  | counts of each bigram  | None  | None  | int  |
| [queried_data.csv](https://github.com/Xintong1122/stats201-PS2-Exlanation-Prediction-Xintong/blob/main/data/Queried_Data/queried_data.csv)  | Date  | 365 day's in 2022  | daily  | a day  | datetime  |
|   | Daily Volume  | 2022 OpenSea daily volume (Ethereum) in ETH  | None  | eth  | float  |
| [Regression_Train.csv](https://github.com/Xintong1122/stats201-PS2-Exlanation-Prediction-Xintong/blob/main/data/Processed_Data/Regression_Train.csv)  | volume  | daily volume  | block  | eth  | float  |
|   | 	volume_past_ma10  | past 10 days' volume  | block  | eth  | float  |
| [Regression_Test.csv](https://github.com/Xintong1122/stats201-PS2-Exlanation-Prediction-Xintong/blob/main/data/Processed_Data/Regression_Test.csv)  | volume  | daily volume  | block  | eth  | float  |
|   | 	volume_past_ma10  | past 10 days' volume  | block  | eth  | float  |


## Code
Explaination Code Source: https://github.com/sunshineluyao/design-principle-blockchain

Prediction Code Source: https://github.com/Rising-Stars-by-Sunshine/stats201-tutorial-prediction

Causal Event Certification Code Source: https://numpy.org/doc/stable/reference/generated/numpy.polyfit.html

| Explaination  | Prediction | Causal Event |
| ------------- | ------------- | ------------- |
| [NLP NFT Challenge](https://github.com/Rising-Stars-by-Sunshine/stats201-Final_Project-Xintong/blob/main/code/NLP_NFT_Challenge.ipynb)  | [Process Data](https://github.com/Rising-Stars-by-Sunshine/stats201-Final_Project-Xintong/blob/main/code/Pre_Process_Data.ipynb)  |[Linear Regression](https://github.com/Rising-Stars-by-Sunshine/stats201-Final_Project-Xintong/blob/main/code/causal_event.ipynb)|
|   | [Analyze Data](https://github.com/Rising-Stars-by-Sunshine/stats201-Final_Project-Xintong/blob/main/code/Pre_Analyze_Data.ipynb)  |   |

## Spotlight

- **Poster**

![image](spotlight/figures/figure1_poster.png)

#### Figure No.1. Final Project Poster

An illustrated poster in Figure No.1. briefly describes the research project. Contents include: *Abstract*, *Background*, *Methodology*, *Result*, *Conclusion*, *References*, and *Acknowledgement*.

*Figure No.1. created by [Microsoft PowerPoint](https://www.microsoft.com/en-us/microsoft-365/powerpoint)*


- **Explaination**

![image](spotlight/figures/figure2_word_cloud.png)

#### Figure No.2. “NFT Challenge” journal topic’s word cloud.

In Google Scholar, by searching for relevant articles with the keywords: "NFT", and "Challenge", got the titles and abstracts of 15 journals. The word cloud was generated by NLP, and we found that "Blockchain", "Risk", and "Secure" appeared more frequently. This indicates that the security and privacy issues regarding blockchain are the main factors that cause NFT challenges at present. (insightsoftware 2022).

*Figure No.2. data source: [literature](https://github.com/Xintong1122/stats201-PS2-Exlanation-Prediction-Xintong/tree/main/data/NLP)
created by [design-principle-blockchain/code](https://github.com/sunshineluyao/design-principle-blockchain)
explain source: insightsoftware. 2022. “Visualizing Text Analysis Results with Word Clouds.” Insightsoftware. May 4, 2022. https://insightsoftware.com/blog/visualizing-text-analysis-results-with-word-clouds/.*


- **Prediction**

![image](spotlight/figures/figure3_linear_reg.png)

#### Figure No.3. Linear regression prediction histogram of 2022 OpenSea Daily Volume (Ethereum) in ETH

The histogram shows in Figure No.3. was obtained by collecting data on the daily volume of OpenSea Ethereum in 2022, using the linear regression prediction method in machine learning. The blue part represents the real data and the green part represents the data predicted by linear regression. It can be noticed that the predicted data in the latter part of the horizontal coordinate is larger than the actual data. ("Regression Analysis-ArcGIS Insights" 2022). In other words, the forecasted volume based on the first half of 2022 is larger than the actual volume; the actual volume was affected by an event that led to a significant decrease. The June 2022 event affected at least the June, July, and August volumes.

*Figure No.3. data source: [OpenSea daily volume (Ethereum) in ETH](https://dune.com/queries/1164276/1989727) 
created by [Linear Regression](https://scikit-learn.org/stable/modules/linear_model.html#logistic-regression)
explain source:“Regression Analysis—ArcGIS Insights | Documentation.” 2022. Doc.arcgis.com. January 2022. https://doc.arcgis.com/en/insights/2022.1/analyze/regression-analysis.htm.*


- **Causal Event**

![image](spotlight/figures/figure4_causal_event.png)

#### Figure No.4. Causal inference research design.

Figure No.4. shows the causal inference design for the impact of security incidents in the NFT market on OpenSea's daily trading volume. In 2022, the global NFT market was dismal and a bear market in the crypto market arrived. In June, the global market traded for only $1.04 billion, down 74% MoM from the $4 billion traded in May, marking the largest drop in global NFT trading. ("Marketplaces Archives" 2023). On June 1, Nate Chastain, a former product manager at the world's largest NFT trading platform, OpenSea, was arrested by U.S. law enforcement authorities on charges of wire fraud and money laundering related to insider trading in NFT. (U.S. Attorney's Office 2022). This significant event reflects the widespread security vulnerabilities in the NFT trading market. This study will use the regression discontinuity algorithm to search "How does the major security incident regarding NFT affect the OpenSea daily volumes on Ethereum?" Then, there are two hypothesises based on the research question. Hypothesis one: A major security incident regarding NFT could negatively impact the OpenSea daily volumes on Ethereum. Hypothesis two: A major security incident regarding NFT could increase the decline in OpenSea daily volumes on Ethereum.

*We don’t foresee other confounding factors that could significantly affect OpenSea daily volume on Ethereum at the cutoff date when the major security incident is happened.*

*Figure No.4. created by [Whimsical](https://whimsical.com)*


- **Result**

![image](spotlight/figures/figure5_result.png)

#### Figure No.5. Result (using Linear Regression Fit Line)

The blue dash in Figure No.5. represents the daily transaction volume of OpenSea in Ether in 2022. The red vertical line represents the NFT security event on June 1. The orange straight line represents the fitted straight line of daily trading volume before June 1, and the green straight line represents after the cut-off event. After the analysis, the trading volume on the OpenSea platform was cut off on June 1, 2022, so the security event did harm the market. Hypothesis 1 was tested. By observing the slopes of the two fitted straight lines in green and orange, we found that the trading volume on the platform is still declining after the security event, but the rate of decline does not increase; instead, the rate of decline is relatively flat. The possible reason is that the NFT market stabilized after this event, as many users who invested autonomously exited the market, leaving behind stable users and stable market sentiment. Therefore, the study rejects Hypothesis 2.

**Note:** The high trading volume on May 1, 2022, comes from the newly meta-universe project, Otherside, launched by Yuga Labs. This project launched a batch of NFT tokens on Opensea on that day, leading to a surge in daily trading volume.

*Figure No.5. code source: [numpy.polyfit](https://numpy.org/doc/stable/reference/generated/numpy.polyfit.html)
created by [Google Colab](https://colab.research.google.com/drive/1pq_ca0qBwxwhtSySja2rCzSEEteklWeT#scrollTo=QoVlnqhNmzet)

- **AI Ethics Issues**

The following are three considerations regarding the AI ethics issues from the research questions.

1. Privacy: security incidents related to NFTs may involve the disclosure of personal information, such as the true identity of the owner of the NFT. NFTs are typically obtained through cryptocurrencies and stored on decentralized networks, held through personal but often anonymous wallets. This anonymity is not as depersonalized and private as some may believe. In many cases, ownership of NFTs and associated transactions can be tied to the identity of the individuals who own, buy, and sell them. (Murphy 2022). The platform should take steps to ensure that their personal information is not compromised.

2. Security: NFT-related security incidents may also involve the theft or loss of digital assets. Platforms that conduct NFT transactions should have strong security measures in place to prevent such incidents from occurring. A new proposal would see the new ERC-721 extension use invisible addresses to mask NFT transactions on the Ethereum network. (Asmakov 2022).

3. Transparency: NFT transaction volumes are an important metric for investors, who need to be confident that reported volumes are accurate. Through the transparency of transaction history, blockchain technology provides trust, permissionless access, and proof of ownership. ("The Benefits of NFT Transaction History and Transparency" 2021). NFT trading platforms should make their transaction volumes public and take steps to prevent fraudulent trading activity.



## More about the Author
- **Bio**

Xintong Wu, a sophomore majoring in Computation and Design/digital media at Duke Kunshan University. She is now an assistant researcher at Language Learning Center (LCC). She has built up a website for a translation program with an assistant professor at LCC. She has also participated in a social community research program about Autism. Her interests are assistant technology of AI, HCI, and design work the website.

![image](spotlight/Xintong_Wu.png)

- **Final Reflection**
  - Intellectual Growth
  
  In this course, I learned and applied the research methods of machine learning. Machine learning can process large-scale and complex data to extract useful information and patterns. And make decisions based on big data to automate and optimize the decision-making process. It improves the efficiency and accuracy of task completion. Sociology and economics are complex and diverse, and machine learning can help people process and understand data better, and provide better services and decisions. This opens up huge potential and opportunities for the future of the industry. The beauty of interdisciplinarity is that it means infinite possibilities. The world is like a gorgeous kaleidoscope, all-encompassing, with everything inextricably linked to each other. Each discipline has its unique disciplinary mindset, and when people conduct interdisciplinary research, researchers use their methods to cross-fertilize and interconnect different disciplines. It may be through machine learning, computer simulation, or human-computer interaction. In interdisciplinary research, various research methods are combined and cross-applied to assist us in solving complex and diverse problems.
  
  - Professional Growth
  
  In this course, I learned a lot about leading-edge science. For example, blockchain, cryptocurrency, and machine algorithm learning. I also learned skills to help me conduct scientific and systematic research. For example, how to make GitHub pages and how to borrow resources to choose research methods on my own. Whether I want to focus on user design in the future or choose to research the needs of users in contemporary markets, the knowledge and skills I have learned will be of great benefit. In addition, through peer evaluation, I have learned how to conduct the process properly and effectively, which has enhanced my critical thinking and communication skills.
  
  - Living a Purposeful Life
  
  I want to be the founder of a new convergence media market. Media is composed of various kinds of information, and various representational data can reflect various meanings underneath the media. I will start from the data to find hidden information and explore new possibilities for the future development of digital media. If one day my achievement is recognized, I would like to quote this saying from the Analects of Confucius: "Know the subtle and know the obvious. (知微知彰。)" It will be my lifelong pursuit to know both the subtle phenomena when things are sprouting and the remarkable consequences of their development. I would like to focus on what I love, and use my strength to catch some and achieve some.

- **Sample Project**

  - [Problem Set 1](https://github.com/Rising-Stars-by-Sunshine/stats201-PS1-Xintong)
  - [Problem Set 2](https://github.com/Rising-Stars-by-Sunshine/stats201-PS2-Xintong)


## References

### Data Source
- [OpenSea daily volume (Ethereum) in ETH](https://dune.com/queries/1164276/1989727)

### Code Source
- Explaination [design-principle-blockchain/code](https://github.com/sunshineluyao/design-principle-blockchain)
- Prediction [stats201-tutorial-prediction/code](https://github.com/Rising-Stars-by-Sunshine/stats201-tutorial-prediction)
- Causal Event [Python numpy.polyfit](https://numpy.org/doc/stable/reference/generated/numpy.polyfit.html)

### Articles

[Visualizing Text Analysis Results with Word Clouds.](https://insightsoftware.com/blog/visualizing-text-analysis-results-with-word-clouds/)

[Marketplaces Archives 2023](https://www.theblockresearch.com/data/nft-non-fungible-tokens/marketplaces)

[OpenSea Daily Volume (Ethereum) in ETH.](https://dune.com/queries/1164276/1989727)

[Regression Analysis—ArcGIS Insights](https://doc.arcgis.com/en/insights/2022.1/analyze/regression-analysis.html)

[Former Employee of NFT Marketplace Charged in First Ever Digital Asset Insider Trading Scheme](https://www.justice.gov/usao-sdny/pr/former-employee-nft-marketplace-charged-first-ever-digital-asset-insider-trading-scheme)

[Non-Fungible Tokens (NFT) Global Market Analysis Report 2022: NFTs Experienced a Rapid Rise in 2021 but Growth Hasn’t Been Steady and Has Plateaued so Far in 2022 - Forecast to 2027](https://www.businesswire.com/news/home/20221206005904/en/Non-Fungible-Tokens-NFT-Global-Market-Analysis-Report-2022-NFTs-Experienced-a-Rapid-Rise-in-2021-but-Growth-Hasnt-Been-Steady-and-has-plateaued-so-Far-in-2022---Forecast-to-2027---ResearchAndMarkets.com)

[New NFT Privacy Proposal Gets Vitalik Buterin’s Attention](https://decrypt.co/107049/new-nft-privacy-proposal-gets-vitalik-buterins-attention.)

[NFTs: Privacy Issues for Consideration](https://www.jdsupra.com/legalnews/nfts-privacy-issues-for-consideration-7804114/.)

[The Benefits of NFT Transaction History and Transparency](https://about.voice.com/blog/the-benefits-of-nft-transaction-history-and-transparency/.)


### Literature

- Ali, Omar, Mujtaba Momin, Anup Shrestha, Ronnie Das, Fadia Alhajj, and Yogesh K. Dwivedi. 2023. “A Review of the Key Challenges of Non-Fungible Tokens.” Technological Forecasting and Social Change 187 (1): 122248. https://doi.org/10.1016/j.techfore.2022.122248.

- Ante, Lennart. 2022. “Non-Fungible Token (NFT) Markets on the Ethereum Blockchain: Temporal Development, Cointegration and Interrelations.” SSRN Electronic Journal, September. https://doi.org/10.1080/10438599.2022.2119564.

- Arcenegui, Javier, Rosario Arjona, and Iluminada Baturone. 2020 “Secure Management of IOT Devices Based on Blockchain Non-Fungible Tokens and Physical Unclonable Functions.” Lecture Notes in Computer Science 24–40. https://doi.org/10.1007/978-3-030-61638-0_2. 

- Arcenegui, Javier, Rosario Arjona, Roberto Román, and Iluminada Baturone. 2021. “Secure Combination of IoT and Blockchain by Physically Binding IoT Devices to Smart Non-Fungible Tokens Using PUFs.” Sensors 21 (9): 3119. https://doi.org/10.3390/s21093119.

- Bamakan, Seyed Mojtaba Hosseini, Nasim Nezhadsistani, Omid Bodaghi, and Qiang Qu. 2022. “Patents and Intellectual Property Assets as Non-Fungible Tokens; Key Technologies and Challenges.” Scientific Reports 12 (1): 2178. https://doi.org/10.1038/s41598-022-05920-6.

- Chohan, Usman W. 2021. “Non-Fungible Tokens: Blockchains, Scarcity, and Value.” SSRN Electronic Journal, no. 3. https://doi.org/10.2139/ssrn.3822743.

- Flick, Dr Catherine. 2022. “A Critical Professional Ethical Analysis of Non-Fungible Tokens (NFTs).” Journal of Responsible Technology 12 (12): 100054. https://doi.org/10.1016/j.jrt.2022.100054.

- Martinod, Nicolas J., Kambiz Homayounfar, Davi Nachtigall Lazzarotto, Evgeniy Upenik, and Touradj Ebrahimi. 2021. “Towards a Secure and Trustworthy Imaging with Non-Fungible Tokens.” Applications of Digital Image Processing XLIV.no.8.https://doi.org/10.1117/12.2598436. 

- Mazur, Mieszko. 2021. “Non-Fungible Tokens (NFT). The Analysis of Risk and Return.” SSRN Electronic Journal, October. http://dx.doi.org/10.2139/ssrn.3953535.

- Popescu, A. 2021 ‘Non-Fungible Tokens (NFT)-Innovation Beyond the Craze’. In 5th International Conference on Innovation in Business, Economics and Marketing Research 66(5): 26–30.

- Raman, Ramakrishnan, and Benson Edwin Raj. 2021. “The world of NFTs (non-fungible tokens): the future of blockchain and asset ownership.” In Enabling blockchain technology for secure networking and communications 89-108. IGI Global. DOI: 10.4018/978-1-7998-5839-3.ch005.

- Uribe, Daniel. 2020. “Privacy Laws, Non-Fungible Tokens, and Genomics.” The Journal of the British Blockchain Association 3 (2): 1–10. https://doi.org/10.31585/jbba-3-2-(5)2020.

- Valeonti, Foteini, Antonis Bikakis, Melissa Terras, Chris Speed, Andrew Hudson-Smith, and Konstantinos Chalkias. 2021. “Crypto Collectibles, Museum Funding and OpenGLAM: Challenges, Opportunities and the Potential of Non-Fungible Tokens (NFTs).” Applied Sciences 11 (21): 9931. https://doi.org/10.3390/app11219931.

- Wang, Qin, Rujia Li, Qi Wang, and Shiping Chen. 2021. “Non-Fungible Token (NFT): Overview, Evaluation, Opportunities and Challenges”. ArXiv Preprint ArXiv:2105. 07447. No.3. https://doi.org/10.48550/arXiv.2105.07447.

- Wilson, Kathleen Bridget, Adam Karg, and Hadi Ghaderi. 2021. “Prospecting Non-Fungible Tokens in the Digital Economy: Stakeholders and Ecosystem, Risk and Opportunity.” Business Horizons 65 (5). https://doi.org/10.1016/j.bushor.2021.10.007.

- Zhang, L. (Sunshine). (2022). Machine Learning for Predictions. Machine Learning for Social Science. Retrieved from https://ms.pubpub.org/pub/ml-prediction

- Zhang, L. (Sunshine). (2022). Machine Learning for Causal Inference. Machine Learning for Social Science. Retrieved from https://ms.pubpub.org/pub/causal-inference
- Zhang, L. (Sunshine). (2022). Venues for Machine Learning; Machine Learning for Social Science. Retrieved from https://ms.pubpub.org/pub/ml

- Zhang, L. (Sunshine). (2022). Computing Platforms: Set up the Workspace for Machine Learning Projects. Machine Learning for Social Science. Retrieved from https://ms.pubpub.org/pub/computing
