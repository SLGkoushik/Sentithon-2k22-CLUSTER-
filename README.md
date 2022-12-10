# Sentithon-2k22-CLUSTER-
We chose the theme "Digital India" because, in the modern world, every developed country is modernizing and placing a priority on cashless trade, and at this point in the growth of our economy, digital India promotes such trade. In this sentiment analysis, we investigate all positive, negative, and neutral opinions of people on digital India.
1. **Data Collection:**

    •	Platforms are used for extracting the data – Twitter
	  Twitter is a platform where people share their opinion or views, and find out what is happening in the world right now. This makes Twitter a perfect platform to     source data for conducting research.
  
   •	Tags are used to extract the data 
	 #Digitalindia, #DigitalPayments
   
    •	APIs or libraries used to perform data extraction – Tweepy, Snscrape
	Twitter allows us to mine the data of any user using Twitter API or Tweepy. The data will be tweets extracted from the user. Snscrape is a scraper for social networking services (SNS). It 	scrapes details like user profiles, hashtags, or searches and returns the discovered items, 
  
  •	Statistics of the extracted data:
  
	- Length of data – 21352(unique)
  
	- Null values - No
  
	- 2272920 total words, with a vocabulary size of 209
  
	- Max tweet length is 285
  
	- Word cloud
  
  ![image](https://user-images.githubusercontent.com/75737889/206871587-5a553e80-7f76-491e-b6db-a887f84cb4f5.png)

•	Collected data is Noisy
	The information gathered from tweets includes stop words, hashtags, non-English languages, and mentions.
  
**2. Data Cleaning:**

The various data cleaning steps are:

•	Removing # and @ words
Since # appears in all tweets and @ is used for account names, we remove them using Regex.

•	Stop words removal
Stop words are the most common words of a language like ‘I’, ‘this’, ‘is’, and ‘in’ which do not add much value to the meaning of a document. These values are removed to decrease the dataset size and increase focus on meaningful words.

•	Lower Casing and Removing Punctuations

- In NLP, models treat words like “Goat” and “goat” differently, even if they are the same. Therefore, to overcome this problem, we convert all the letters into the same case i.e; lower.

- Punctuations are the marks in English like commas, hyphens, full stops, etc. These are important for English grammar but not for text analysis. Therefore, they need to be removed

•	Tokenization
The tokenizer simply splits words by whitespace, similar to the pythons .split() method.

•	Lemmatization
To further reduce noise in our text data, and get the most accurate frequency distributions possible, cue lemmatization. Lemmatization is the act of breaking a word token down to its root meaning.

**3. Sentiment Analysis:**

Modeling Approach – Text Blob

Text blob sentiment analyzer returns two properties for a given input sentence:

•	Polarity is a float that lies between [-1,1], -1 indicates negative sentiment and +1 indicates positive sentiment.

•	Subjectivity is also a float that lies in the range of [0,1]. Subjective sentences generally refer to opinion, emotion, or judgment.

**Why Text Blob?**

Text Blob is built on top of NLTK and Pattern also it is very easy to use and can process the text in a few lines of code. Text Blob is an open-source and free-to-use python library for processing textual data. It offers a simple API to access its methods and perform basic NLP tasks.

![image](https://user-images.githubusercontent.com/75737889/206871757-be8c72db-d120-4519-a839-04913aaed73e.png)


![image](https://user-images.githubusercontent.com/75737889/206871766-27275150-f8fc-4204-a954-63b9f0c3723f.png)

**4. Topic Modeling:**

Topic modeling is the method of extracting needed attributes from a bag of words. This is critical because each word in the corpus is treated as a feature in NLP.

Latent Dirichlet Allocation (LDA):

Latent Dirichlet Allocation (LDA) is an example of a topic model and is used to classify text in a document to a particular topic. It builds a topic per document model and words per topic model, modeled as Dirichlet distributions.

**PyLDAvis:**

The PyLDAvis library is a great way to visualize topics from a topic model.For the interactive dashboard run the pyLDAvis cell in the notebook.

Results:

![image](https://user-images.githubusercontent.com/75737889/206871833-86cdfd88-d081-466a-a636-1a2578d4795d.png)

"According to the public's perceptions, 44.1% of people are favorable towards digital India, compared to only 16% who are unfavorable and the remaining who seem neutral."

**Fitting an LDA model in Gensim :**

Here’s the output

[(0,
  '0.046*"india" + 0.036*"service" + 0.026*"app" + 0.025*"digital" + 0.021*"rt" + 0.019*"state" + 0.014*"this" + 0.011*"umang" + 0.011*"government" + 0.010*"amp"'),
  
 (1,
  '0.027*"digital" + 0.023*"india" + 0.013*"i" + 0.009*"payment" + 0.009*"bank" + 0.007*"day" + 0.007*"one" + 0.007*"transaction" + 0.006*"u" + 0.006*"amp"'),
  
 (2,
  '0.034*"we" + 0.026*"with" + 0.022*"plus" + 0.019*"india" + 0.014*"group" + 0.014*"of" + 0.013*"are" + 0.013*"based" + 0.013*"company" + 0.011*"govt"'),
  
 (3,
  '0.035*"india" + 0.029*"digital" + 0.020*"the" + 0.017*"amp" + 0.014*"ad" + 0.013*"from" + 0.011*"a" + 0.010*"to" + 0.010*"and" + 0.010*"our"'),
  
 (4,
  '0.027*"digital" + 0.015*"vle" + 0.015*"csc" + 0.008*"million" + 0.007*"certificate" + 0.007*"marketing" + 0.007*"raised" + 0.007*"story" + 0.006*"district" + 0.005*"easy"')]

The output represents 5 topics, consisting of the top keywords and associated weightage contribution to the topic.

Ex: From Eyeballing
---
1st topic may be related to the Umang app and its revolution.

2nd topic may be related to increase in the number of transactions due to the digital India initiative.

---
**pyLDAvis Output:**
![image](https://user-images.githubusercontent.com/75737889/206871951-596bf996-c6b0-4f8e-b2b5-e58bf50802cb.png)

For the interactive dashboard run the pyLDAvis cell in the notebook 
---
On the left, the topics are plotted on a 2-dimensional plane representing the distance between each topic. While the right horizontal bar chart represents the words most relevant to each topic. The chart is interactive, allowing you to select specific topics and view the related words for each topic, in the hope of inferring meaning from each topic.
---
Regards Team Cluster






