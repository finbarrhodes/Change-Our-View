## Project proposal form

Please provide the information requested in the following form. Try to provide concise and informative answers.

## Candidate numbers: 39375, 41830, 42309, 44051

**1. What is your project title?**
Change Our View: Analysis of Indicators of Topic Polarization over Time  

**2. What is the problem that you want to solve?**

Effectively persuading individuals to change opinion has been the subject of countless research, relevant to advertisement, political campaigning, and behavioural change. There seems to be a consensus that political opinion is amongst the most difficult to understand and change, notably due to lack of data. Our main research question is: "Are political views/beliefs particularly sticky and resistant to change compared to opinions on other topics, and has political polarization increased this resistance?". 
We also intend to explore the following questions: 
* How does increased political polarization reflect in language (e.g.: increased hostile language)?
* Do certain characteristics (word count, word score) of the original posters' opinion tell us anything about the probability of being convinced? 
* Do certain characteristics (word count, number of exchanges, word score) of the responses tell us anything on how to increase chances of convincing someone? 

To answer our question, we scrape Reddit Forum r/ChangeMyView as our data. ChangeMyView is an online forum where users can invite others to debate about their opinion, awarding a "delta" if they have successfully been convinced. 
Our evaluation metrics are the following: 
* Word score based features: arousal (Dull vs. excitatory), concreteness (perceptable vs. abstract), hostility (peaceful vs. violent). 
Conciseness of both the post and the responses.
* Bag of words model (word frequency)
* Metadata: average number of replies across successful debates, different topics... 


**3. What big data methodologies and tools do you plan to use?**

We intend to scrape and pre-process (stem or lemitizing) data locally, then explore using BOW and LDA models as well as train ML models in a distributed way using PySpark and MapReduce. 

**4. What dataset will you use? You may assess the suitability of the dataset for distributed computing for big data. Provide information about the dataset (size, features and labels, if applicable) and a URL for the dataset if available. If you intend to generate synthetic data, provide a description of what features you will use, whether your dataset is labelled or not (supervised versus unsupervised learning problem), how will it be generated (any functions, seed values, data ranges etc) and the expected size. When choosing or generating data, please remember to consider any aspects related to data representativeness, quality, bias and other aspects relevant to your project**

Our main data will come from scraping Reddit Forum r/changemyview (https://www.reddit.com/r/changemyview/). We will also use well established panel data on political polarization and political events to trace the change. We intend to collect as much posts as possible from the year 2020 until now. 

<characteristics of synthetic datasets>

**5. List key references (e.g. research papers) that your project will be based on. Please cite them properly and provide URLs.**

Our main article on which we rely: Tan, C., Niculae, V., Danescu-Niculescu-Mizil, C., & Lee, L. (2016). Winning arguments: Interaction dynamics and persuasion strategies in good-faith online discussions. In Proceedings of the 54th Annual Meeting of the Association for Computational Linguistics (pp. 1216–1226). Association for Computational Linguistics.

**Please indicate whether your project proposal is ready for review (Yes/No):**

**Yes**

## Feedback & approval (to be provided by the lecturer by Week 11)

[MB - 04/04/2025] The topic is relevant and adherent with a big data scenario. The dataset to be produced from Reddit is fine, and you should take into consideration the aspects discussed during office hours, such as how long/how much interactions will be considered across each entry. The topic modelling part is fine, but you need to carefully check which machine learning models can be used here and for what context; for instance, predicting view churn based on specific features. If I recall correctly, we discussed about identifying most convincing words leading to view changing. This would be a good output. Metrics are fine, but remember to include big data-related metrics; for instance, you mention latency, so it would be nice to measure local vs global training (or single vs multiple machines). Remember to emphasise any other aspects of your big data pipeline where you've put more work. 

**Approved**
 

 
