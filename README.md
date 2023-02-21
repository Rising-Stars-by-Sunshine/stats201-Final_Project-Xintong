# The Daily Volume of OpenSea platform: Security Vulnerabilities in the NFT Marketplace
## Project information
- **Author**: Xintong Wu, Computation and Design / digital media, Class of 2025, Duke Kunshan University
- **Instructor**: Prof. Luyao Zhang, Duke Kunshan University
- **Disclaimer**: Submissions to the Problem Set 2 for STATS201 Introduction to Machine Learning for Social Science, 2023 Spring Term (Seven Week - First) instructed by Prof. Luyao Zhang at Duke Kunshan University.
- **Acknowledgments**: I would like to express my sincere gratitude to Prof. Luyao Zhang for her guidance in machine learning methods for data interpretation and prediction. Prof. Luyao Zhang provided constructive comments on the feasibility of my research questions and data collection, which prompted me to continuously improve and enhance.
- **Project Summary**: In 2022, the global NFT market was dismal and a bear market in the crypto market arrived. In June, the global market traded for only $1.04 billion, down 74% MoM from the $4 billion traded in May, marking the largest drop in global NFT trading. ("Marketplaces Archives" 2023). On June 1, Nate Chastain, a former product manager at the world's largest NFT trading platform, OpenSea, was arrested by U.S. law enforcement authorities on charges of wire fraud and money laundering related to insider trading in NFT. (U.S. Attorney's Office 2022). This significant event reflects the widespread security vulnerabilities in the NFT trading market. The impact of NFT security events on the daily trading volume of Ethereum is the focus of this study. This study processes and analyzes the daily trading volume (in Ethereum) on OpenSea 2022 on Dune Analytic through a machine learning method of prediction. ("OpenSea Daily Volume (Ethereum) in ETH" 2023). The study found that the security breach hit the platform's trading volume, leading to a market downturn for at least the next two months. The research highlights the significant impact of long-standing security breaches on industry growth and contributes to the analysis of NFT's market direction. It also provides future directions for improvement and optimization in the Blockchain and crypto-sphere market. The criteria for NFT security attributes should be more accurately defined in the future. 


## Table of Contents
- [Data](https://github.com/Xintong1122/stats201-PS2-Exlanation-Prediction-Xintong/tree/main/data)
- [Code](https://github.com/Xintong1122/stats201-PS2-Exlanation-Prediction-Xintong/tree/main/code)
- [Spotlight](https://github.com/Xintong1122/stats201-PS2-Exlanation-Prediction-Xintong/tree/main/spotlight)
- References


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
| [literature.csv](https://github.com/Xintong1122/stats201-PS2-Exlanation-Prediction-Xintong/blob/main/data/NLP/literature.csv)  | Title  | titles of 15 journals  | None  | None  | str  |
|   | Abstract  | abstract of 15 journals  | None  | None  | str  |
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

| Explaination  | Prediction |
| ------------- | ------------- |
| [NLP NFT Challenge](https://github.com/Xintong1122/stats201-PS2-Exlanation-Prediction-Xintong/blob/main/code/NLP_NFT_Challenge.ipynb)  | [Process Data](https://github.com/Xintong1122/stats201-PS2-Exlanation-Prediction-Xintong/blob/main/code/Pre_Process_Data.ipynb)  |
|   | [Analyze Data](https://github.com/Xintong1122/stats201-PS2-Exlanation-Prediction-Xintong/blob/main/code/Pre_Analyze_Data.ipynb)  |


## Spotlight
![image](https://github.com/Xintong1122/stats201-PS2-Exlanation-Prediction-Xintong/blob/main/spotlight/figures/figure1_word_cloud.png)

#### Figure No.1. “NFT Challenge” journal topic’s word cloud.

In Google Scholar, by searching for relevant articles with the keywords: "NFT", and "Challenge", I got the titles and abstracts of 15 journals. The word cloud was generated by NLP, and we found that "Blockchain", "Risk", and "Secure" appeared more frequently. This indicates that the security and privacy issues regarding blockchain are the main factors that cause NFT challenges at present. (insightsoftware 2022).

*Figure No.1. data source: [literature](https://github.com/Xintong1122/stats201-PS2-Exlanation-Prediction-Xintong/tree/main/data/NLP)
created by [design-principle-blockchain/code](https://github.com/sunshineluyao/design-principle-blockchain)
explain source: insightsoftware. 2022. “Visualizing Text Analysis Results with Word Clouds.” Insightsoftware. May 4, 2022. https://insightsoftware.com/blog/visualizing-text-analysis-results-with-word-clouds/.*



![image](https://github.com/Xintong1122/stats201-PS2-Exlanation-Prediction-Xintong/blob/main/spotlight/figures/figure2_linear_reg.png)

#### Figure No.2. Linear regression prediction histogram of 2022 OpenSea Daily Volume (Ethereum) in ETH

This histogram was obtained by collecting data on the daily volume of OpenSea Ethereum in 2022, using the linear regression prediction method in machine learning. The blue part represents the real data and the green part represents the data predicted by linear regression. It can be noticed that the predicted data in the latter part of the horizontal coordinate is larger than the actual data. ("Regression Analysis-ArcGIS Insights | Documentation" 2022). In other words, the forecasted volume based on the first half of 2022 is larger than the actual volume; the actual volume was affected by an event that led to a significant decrease. The June 2022 event affected at least the June, July, and August volumes.

*Figure No.2. data source: [OpenSea daily volume (Ethereum) in ETH](https://dune.com/queries/1164276/1989727) 
created by [Linear Regression](https://scikit-learn.org/stable/modules/linear_model.html#logistic-regression)
explain source:“Regression Analysis—ArcGIS Insights | Documentation.” 2022. Doc.arcgis.com. January 2022. https://doc.arcgis.com/en/insights/2022.1/analyze/regression-analysis.htm.*


![image](https://github.com/Xintong1122/stats201-PS2-Exlanation-Prediction-Xintong/blob/main/spotlight/figures/whimsical.png)

#### Figure No.3. predicted graphic of cut off event.

This graphic shows the predicted effect of the cut off event, Including the research question, alogrithm, the cut off event, two hypothesises, and the continuity assumption.

*Figure No.3. created by [Whimsical](https://whimsical.com)*

## References

### Data Source
- [OpenSea daily volume (Ethereum) in ETH](https://dune.com/queries/1164276/1989727)

### Code Source
- Explaination [design-principle-blockchain/code](https://github.com/sunshineluyao/design-principle-blockchain)
- Prediction [stats201-tutorial-prediction/code](https://github.com/Rising-Stars-by-Sunshine/stats201-tutorial-prediction)

### Articles

[Marketplaces Archives 2023](https://www.theblockresearch.com/data/nft-non-fungible-tokens/marketplaces)

[Former Employee of NFT Marketplace Charged in First Ever Digital Asset Insider Trading Scheme](https://www.justice.gov/usao-sdny/pr/former-employee-nft-marketplace-charged-first-ever-digital-asset-insider-trading-scheme)

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

