# WERD_V3_TopicModel
Welcome! This repository provides researchers and analysts access to the results of a topic model analysis of education reform descriptions extracted from the World Education Reform Database (WERD, V3). The goal of this project is to help researchers uncover linguistic patterns, trends, and key themes in global education reforms by applying natural language processing (NLP) techniques.

Specifications of the topic model:
* Dataset: Education reform descriptions between 1960-2021 from WERD V3 (https://werd.stanford.edu/database). See more details about the structure of WERD V3 in: Bromley, P., Kijima, R., Overbey, L., Furuta, J., Choi, M., Santos, H., Song, J., Nachtigal, T., and Yang, M. 2024. World Education Reform Database (WERD), Harvard Dataverse, V3.
* Algorithm used: STM (structural topic modeling) package (R) (Roberts, Stewart & Tingley, 2019). The code includes in-line comments to clarify decisions that have been made throughout to facilitate replication.
* Licenses used: Used Google Translate API to translate non-English reforms, see: Google. (N.D). Cloud Translation - Google Cloud, Retreived from https://cloud.google.com/translate. To run this section of the code, be sure to obtain appropriate API. The dataset included here includes the English version of all reforms included in our analysis.
  
Features:
* Preprocessed Data: Cleaned and tokenized descriptions of education reforms from WERD, ready for topic modeling.
* Topic Model Results: Outputs of the STM, including:
  1) Table listing the topics in decreasing order by topic prevalence across the database (i.e., the most commonly discussed topic to the least discussed), including the most probably words associated with every topic, the most unique words to every topic, and 3 of the most associated reforms with every topic.
  2) CSV of WERD with topic scores: for each reform, the model assigns a score for each topic, indicating the prevalence of the topic for the given reform.
  3) Plot of topic prevalence.
  Note: we do not specify our qualitative labels, as they are subject to researcher discretion.
* Code & Notebooks: RMarkdown files used to preprocess the data, train the topic model, and generate its outputs, allowing researchers to reproduce or adapt the analysis for their own work.
* Usage Examples: Guidance on how to interpret and use the results for further research, including suggestions for how to map topics to education reform themes.

This repository aims to provide a comprehensive, user-friendly resource for researchers interested in the intersection of education reforms and data science. All materials are available for free use under an open license, and contributions to improve the analysis or extend the project are welcome.

Feel free to explore the data, replicate the analysis, or use the insights for your own research projects! 
