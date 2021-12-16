<p style='text-align: justify;'> </p>

# Introduction
## Motivation
<p style='text-align: justify;'> It is not news to anyone that gender inequalities persist in modern society. This is due to centuries of oppression of the "weaker sex" in western cultures, by systematically denying women political, economic and intellectual power. Women have been stereotyped as caring and nurturing by nature to be relegated to housework and childcare, while men had access to higher education and financial independence. Although Women's Rights Movements have greatly improved women's conditions, inequalities subsist. Men still occupy most positions of power, whether it be in politics or private companies. This can be explained not only by the huge difference in the number of women versus men pursuing higher education (very noticeable even at EFPL) but also by implicit bias, through which women are seen as less competent than their male counterpart. </p>

<p style='text-align: justify;'> As differential treatment and stereotypes lead to differences in self-assessment and behavior, it is no surprise that researchers have found women tend to underestimate their abilities more than men and frequently experience "Imposter Syndrome", wherein they feel as though they are not qualified for their position and fear they will be discovered as such. </p>

<p style='text-align: justify;'> We are interested in the difference in self-confidence between men and women. Have oppression and stereotypes lead to women being less confident? If so, is this asymmetry noticeable through the way people express themselves? Furthermore, we would like to see how being a public figure such as politician, making a living by speaking in front of crowds, would influence self-confidence. Does being of a specific gender influence the percieved confidence of politicians? </p>

## Method

<p style='text-align: justify;'> 
  We used the Quotebank dataset from the year 2020, <b>ACHANGER SELON LE DATA SET QU'ON UTILISE</b> which consists of quotes taken from English speaking newspaper articles and web domains, with the speaker attributed to the quote by the Quobert framework. We assigned a confidence score to speakers, using BERT text similarity to compare the quotes to a phrases taken from <a href="https://www.researchgate.net/publication/26877357_Verbal_Expressions_of_Confidence_and_Doubt">"Verbal Expressions of Confidence and Doubt"</a>, a psychology paper published in 2009, which rated the percieved self-confidence of speakers through their expression. </p>
<p style='text-align: justify;'> The personal information of quoted persons such as their gender, birthyear and occupation was retrieved from the speaker attribute files provided by TAs. </p>

### Some statistics on the speakers:
<p style='text-align: justify;'> 
  Let's start by looking at the gender distribution of speakers: </p>
  
  <img src = "https://user-images.githubusercontent.com/57099519/146407324-36aafbcd-88af-4979-b1bc-b17186b46d66.png" alt = "gender distribution among speakers" >

<p style='text-align: justify;'>
  We can see above that a vast majority of the speakers are females and males (these categories include cis-gender and unspecified females and males), even though there are still more male than female speakers. Speakers of other genders figure in the dataset as well, but in negligeable numbers compared to the leading categories. (As our analysis is mainly focused of the difference between men and women we will exclude other genders from our study.) </p>
  
<p style='text-align: justify;'> We also thought interesting to look at the age of speakers, as maturity can influence self-confidence, and common expressions change with each generation. </p>
  
  <img src = "https://user-images.githubusercontent.com/57099519/146066435-0893e3fb-c533-463e-81e2-e333b422b5c2.png" alt = "birth year distribution among speakers">
<p style='text-align: justify;'>  
  We can see that the most speakers are from the generation 1950 and 1960. There are less speakers born before 1940 as there might not be as many alive recently, and very few speakers born after 2000, as they are still very young. 
</p>
  
### Some statistics on the quotes: 
 <p style='text-align: justify;'> 
  Not all speakers are quoted the same amount. Let's look at the distribution of quotes per speaker: </p>
  <img src = 'https://user-images.githubusercontent.com/57099519/146403563-0ad30ce1-36a6-49e7-890c-d30cf2015127.png' alt = 'quotes per speaker'>
<p style='text-align: justify;'>  
  As we can see above, it's clear not all the speakers have the same representation in the media, and thus our dataset. Although most speakers have less than 1000 quotes in the data set, some are quoted disproportionately.  
  Let's now take a look at the number of quotes by speakers of each gender: </p>
  <img src = 'https://user-images.githubusercontent.com/57099519/146404691-20accc2c-a576-4c3b-9db1-0654f76d1fff.png' alt = "number of quotes per gender">
  
<p style='text-align: justify;'>  
  We can see a significant change in the distribution. By looking at the percentage of quotes by each gender, we notice that men represent over 70% of the quotes present in our dataset, while gender minorities representation is minuscule.</p> 
  <img src = 'https://user-images.githubusercontent.com/57099519/146407136-ed8b97ef-3c81-4fc5-82e3-06342a1c07c3.png' alt = 'percentage male vs female'>
<p style='text-align: justify;'>
</p>

