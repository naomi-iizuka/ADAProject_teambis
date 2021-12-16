<p style='text-align: justify;'> </p>
<p align="center">
</p>

# Introduction
## Motivation
<p style='text-align: justify;'> It is not news to anyone that gender inequalities persist in modern society. This is due to centuries of oppression of the "weaker sex" in western cultures, by systematically denying women political, economic and intellectual power. Women have been stereotyped as caring and nurturing by nature to be relegated to housework and childcare, while men had access to higher education and financial independence. Although Women's Rights Movements have greatly improved women's conditions, inequalities subsist. Men still occupy most positions of power, whether it be in politics or private companies. This can be explained not only by the huge difference in the number of women versus men pursuing higher education (very noticeable even at EFPL) but also by implicit bias, through which women are seen as less competent than their male counterpart. </p>

<p style='text-align: justify;'> As differential treatment and stereotypes lead to differences in self-assessment and behavior, it is no surprise that researchers have found women tend to underestimate their abilities more than men and frequently experience "Imposter Syndrome", wherein they feel as though they are not qualified for their position and fear they will be discovered as such. </p>

<p style='text-align: justify;'> We are interested in the difference in self-confidence between men and women. Have oppression and stereotypes lead to women being less confident? If so, is this asymmetry noticeable through the way people express themselves? Furthermore, we would like to see how being a public figure such as politician, making a living by speaking in front of crowds, would influence self-confidence. Does being of a specific gender influence the percieved confidence of politicians? </p>

## Method

<p style='text-align: justify;'> 
  We used the <a href = "https://zenodo.org/record/4277311#.Ybt4w33MK3J"> Quotebank </a> dataset from the year 2020, <b>ACHANGER SELON LE DATA SET QU'ON UTILISE</b> which consists of quotes taken from English language newspaper articles and web domains, with the speaker attributed to the quote by the Quobert framework. Our self-confidence metric is based on <a href="https://www.researchgate.net/publication/26877357_Verbal_Expressions_of_Confidence_and_Doubt">"Verbal Expressions of Confidence and Doubt"</a>, a psychology paper published in 2009, which rated the percieved self-confidence of speakers through their expression. </p>
<p style='text-align: justify;'> The personal information of quoted persons such as their gender, birthyear and occupation was retrieved from Wikidata. </p>

### Some statistics on the speakers:
<p style='text-align: justify;'> 
  Let's start by looking at the gender distribution of speakers: </p>
  <p align="center">
  <img src = "https://user-images.githubusercontent.com/57099519/146407324-36aafbcd-88af-4979-b1bc-b17186b46d66.png" alt = "gender distribution among speakers" >
  </p>
<p style='text-align: justify;'>
  We can see above that a vast majority of the speakers are females and males (these categories include cis-gender and unspecified females and males), even though there are still more male than female speakers. Speakers of other genders figure in the dataset as well, but in negligeable numbers compared to the leading categories. (As our analysis is mainly focused of the difference between men and women we will exclude other genders from our study.) </p>
  
<p style='text-align: justify;'> We also thought interesting to look at the age of speakers, as maturity can influence self-confidence, and common expressions change with each generation. </p>
  <p align="center">
  <img src = "https://user-images.githubusercontent.com/57099519/146066435-0893e3fb-c533-463e-81e2-e333b422b5c2.png" alt = "birth year distribution among speakers">
  </p>
<p style='text-align: justify;'>  
  We can see that the most speakers are from the generation 1950 and 1960. There are less speakers born before 1940 as there might not be as many alive recently, and very few speakers born after 2000, as they are still very young. 
</p>
  
### Some statistics on the quotes: 
 <p style='text-align: justify;'> 
  Not all speakers are quoted the same amount. Let's look at the distribution of quotes per speaker: </p>
  <p align="center">
  <img src = 'https://user-images.githubusercontent.com/57099519/146403563-0ad30ce1-36a6-49e7-890c-d30cf2015127.png' alt = 'quotes per speaker'>
  </p>
<p style='text-align: justify;'>  
  As we can see above, it's clear not all the speakers have the same representation in the media, and thus our dataset. Although most speakers have less than 1000 quotes in the data set, some are quoted disproportionately.  
  Let's now take a look at the number of quotes by speakers of each gender: </p>
  <p align="center">
  <img src = 'https://user-images.githubusercontent.com/57099519/146404691-20accc2c-a576-4c3b-9db1-0654f76d1fff.png' alt = "number of quotes per gender">
  </p>
<p style='text-align: justify;'>  
  We can see a significant change in the distribution. By looking at the percentage of quotes by each gender, we notice that men represent over 70% of the quotes present in our dataset, while gender minorities representation is minuscule.</p> 
  <p align="center">
  <img src = 'https://user-images.githubusercontent.com/57099519/146407136-ed8b97ef-3c81-4fc5-82e3-06342a1c07c3.png' alt = 'percentage male vs female'>
  </p>
<p style='text-align: justify;'>
</p>

### How we rate self-confidence:
<p style='text-align: justify;'> As mentioned above, we based our metric of self-confidence on a <a href="https://www.researchgate.net/publication/26877357_Verbal_Expressions_of_Confidence_and_Doubt"> sociology study </a>, in which participants were asked to read a set of sentences, and rate the confidence of a person who would use those phrases, on a scale from 0 to 7. The table below is a subset of the findings of the study: 
</p>
<table>
  <tr>
    <th>Phrase</th>
    <th>Score (past tense)</th>
    <th>Score (present tense)</th>
  </tr>
  <tr>
    <td>I'm not sure, it's kind of…  </td>
    <td>Tobias</td>
    <td>Linus</td>
  </tr>
  <tr>
    <td>16</td>
    <td>14</td>
    <td>10</td>
  </tr>
</table>
| Phrase      | Score (past tense)| Score (present tense) |
| :---        |    :----:   |          ---: |
| I'm not sure, it's kind of…  | 2.88    | 2.91 |
|Oh, I don't know, I suppose it's…  | 2.94       | 3.02  |
|I suppose it could be… |3.13 |3.34 |
|I'm guessing, but I would say it's… |2.92  |3.39|
|I'm certain it's…|5.90 |6.55|
|I'm positive it's…|5.96| 6.57|
|I'm absolutely certain it's…|6.33 | 6.61 |
<p style='text-align: justify;'> 
  The are different scores associated with present tense and past tense, as it has been found that it affects percieved confidence. We searched the quotes for matches to the phrases found in the article using NLTK, and assigned the score of said phrase. We then averaged out the scores of all quotes by the same person, which gives us the estimated confidence of a speaker. </p>
