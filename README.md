# WERD_V3_TopicModel
Welcome! This repository provides researchers and analysts access to the results of a topic model analysis of education reform descriptions extracted from the World Education Reform Database (WERD, V3). The goal of this project is to help researchers uncover linguistic patterns, trends, and key themes in global education reforms by applying natural language processing (NLP) techniques.

This repository aims to provide a comprehensive, user-friendly resource for researchers interested in using the topic model method. All materials are available for free use under an open license, and contributions to improve the analysis or extend the project are welcome.
* INCLUDE A REQUEST TO CITE?
* For questions and inqueries - tomnacht@stanford.edu

Feel free to explore the data, replicate the analysis, or use the insights for your own research projects. 

Details about the topic model:
* Dataset: Education reform descriptions between 1960-2021 from WERD V3 (https://werd.stanford.edu/database). See more details about the structure of WERD V3 in: Bromley, P., Kijima, R., Overbey, L., Furuta, J., Choi, M., Santos, H., Song, J., Nachtigal, T., and Yang, M. 2024. World Education Reform Database (WERD), Harvard Dataverse, V3.
* Algorithm used: STM (structural topic modeling) package (R) (Roberts, Stewart & Tingley, 2019). The code includes in-line comments to clarify decisions that have been made throughout to facilitate replication.
* Number of topics: 30.
* Licenses used: Used Google Translate API to translate non-English reforms, see: Google. (N.D). Cloud Translation - Google Cloud, Retreived from https://cloud.google.com/translate. To run this section of the code, be sure to obtain appropriate API. The dataset included here includes the English version of all reforms included in our analysis.
  
Features:
* Preprocessed Data: RDA files of cleaned and tokenized descriptions of education reforms from WERD, ready for topic modeling.
* Topic Model Results: Outputs of the STM, including:
  1) Key of topics (temporary Google Doc link: https://docs.google.com/document/d/1eeXTWaGu8Qs5aA858ksR7Iamc6r-0rTzQaP0A4izLyY/edit): Table listing the topics in decreasing order by topic prevalence across the database (i.e., the most commonly discussed topic to the least discussed), including the most probably words associated with every topic, the most unique words to every topic, and 3 of the most associated reforms with every topic.
    Note: we do not specify our qualitative labels, as they are subject to researcher discretion.
  2) Topic scores (CSV): a dataset of education reforms with topic scores, such that for each reform, the model assigns a score for each topic, indicating the prevalence of the topic for the given reform.
  3) Plot of topic prevalence (RDA file).
* Code (RMarkdown file): R code used to preprocess the data, train the topic model, and generate its outputs, allowing researchers to reproduce or adapt the analysis for their own work.

How to use the generated topics?
* To use topic scores as content-based indicators:
  1) Analysis of the content - we recommend starting with qualitative analysis of the topics using the Key of topics table. You can learn about the content of each topic by examining the keywords that aremost associated with it or are most unique to it. We also provide in this table 3 most associated reforms, which are the reforms that have the largest probability of including words associated with the topic. Note that each reform is likely to include more than one topic (not mutually exclusive).
  2) Select indicators of interest for quantitative analysis (e.g., if you're interested in topic 1, focus on the column "topic 1" in the topic scores csv file).
  3) Use selected columns as reform-level indicators. 
* To run the code and recreate the topic model:
  1) Download all the files included in this repository, including the RMarkdown with the code itself, into one directory on your machine.
  2) Run each section of the code separately, follow the comments to make sure that you are working with the correct R object (e.g., verify that the number of reforms included in the R object for each step corresponds with the number of reforms indicated in the comments).
  3) Follow the comments to run the code, feel free to adjust or reach out with questions.
  Note: we provide here a topic model with K = 30 because we found it to provide the good balance of topics' semantic coherence and exclusivity, but the code allows you to change K and explore other models that could be more helpful for different analytical purposes.
     
Usage Examples and Interpretation Guidance: Guidance on how to interpret and use the results for further research, including suggestions for how to map topics to education reform themes.

* The topic model assigns each education reform 30 topic scores for each of the topics created by the model (the most prevalent sets of co-occuring words across the reforms in the dataset). These topic scores indicate the relevance or association of each reform with the identified topics in the model. Here's how to interpret and use these scores effectively:

1. Understanding Topic Scores:
Each reform is assigned a topic score for all 30 topics, where each score represents the proportion or degree of association between that reform and a particular topic. These scores range from 0 to 1, with the sum of scores across all topics for a given reform typically summing to 1.

High Topic Score: A high score (closer to 1) for a particular topic means that the reform has many words that are associated with the topic.

Low Topic Score: A low score (closer to 0) means that the reform has little to no association with that topic.

Balanced Scores: If a reform has balanced scores across several topics, it indicates that the reform spans multiple themes or topics identified in the model.

2. Using Topic Scores for Analysis

* Identifying Thematic Trends: By analyzing the topic scores across a large set of reforms, you can identify thematic trends in education reform across different countries and against different variables (e.g., country-level variables may include economic productivity or growth, political regime type, membership in global organizations, human rights indicators, etc). For example, if Topic 12 (e.g., “early childhood education”) is consistently scoring high for a range of recent reforms, this could indicate a global or regional trend toward prioritizing early childhood education.

* Clustering Reforms by Topics: Reforms can be clustered based on their topic scores. This can help identify similar reforms that address the same themes, which might be useful for comparative policy analysis.

* Tracking Topic Evolution Over Time: If the database includes reforms from different time periods, you can track how the prevalence of certain topics evolves over time. For example, you might observe a shift in focus from traditional education topics (e.g., curriculum changes) to modern ones (e.g., digital education) by analyzing the topic scores for reforms enacted in different years. (see, e.g., Bromley et al., 2024).

* Cross-national Comparisons: By comparing the topic scores of reforms from different countries, you can gain insights into how different nations are addressing similar educational challenges or focusing on specific themes.

3. Creating and Interpreting Topic Labels

* The topics themselves are generated based on statistical patterns in the text of the reform descriptions. Therefore, while topics may often be labeled by the most prominent words associated with them, it’s important to review the list of words associated with each topic to fully understand its scope. Each topic typically includes a set of "top words" that help define its theme (e.g., “teacher,” “training,” “development” for a topic on teacher training).

Key Considerations:

* Topic Overlap: Some reforms may address multiple themes, and the topic scores reflect this overlap. It is common for reforms to have moderate scores across several topics, rather than being exclusively tied to one.
* Dynamic Nature of Topics: Topics in the model are not predefined but are emergent from the reform descriptions. Therefore, they may sometimes represent nuanced or hybrid themes that require careful interpretation.
* Limitations: While topic scores provide valuable insights, they are based on text data and may not capture all policy details or nuances. It is often useful to combine topic model results with expert knowledge for more accurate interpretations.


