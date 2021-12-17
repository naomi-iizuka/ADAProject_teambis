<p style='text-align: justify;'> </p>
<p align="center">
</p>

# Introduction

## Motivation

<p style='text-align: justify;'> 
  It is not news to anyone that gender inequalities persist in modern society. This is due to centuries of oppression of the "weaker sex" in western cultures, by systematically denying women political, economic and intellectual power. Women have been stereotyped as caring and nurturing by nature to be relegated to housework and childcare, while men had access to higher education and financial independence. Although Women's Rights Movements have greatly improved women's conditions, inequalities subsist. Men still occupy most positions of power, whether it be in politics or private companies. This can be explained not only by the huge difference in the number of women versus men pursuing higher education (very noticeable even at EFPL) but also by implicit bias, through which women are seen as less competent than their male counterpart. </p>

<p style='text-align: justify;'> 
  As differential treatment and stereotypes lead to differences in self-assessment and behavior, it is no surprise that researchers have found women tend to underestimate their abilities more than men and frequently experience "Imposter Syndrome", wherein they feel as though they are not qualified for their position and fear they will be discovered as such. </p>

<p style='text-align: justify;'> 
  We are interested in the difference in self-confidence between men and women. Have oppression and stereotypes lead to women being less confident? If so, is this asymmetry noticeable through the way people express themselves? Furthermore, we would like to see how being a public figure such as politician, making a living by speaking in front of crowds, would influence self-confidence. Does being of a specific gender influence the percieved confidence of politicians? </p>

## Method

<p style='text-align: justify;'> 
  We used the <a href = "https://zenodo.org/record/4277311#.Ybt4w33MK3J"> Quotebank </a> dataset from the year 2020,  which consists of quotes taken from English language newspaper articles and web domains, with the speaker attributed to the quote by the Quobert framework. Our self-confidence metric is based on <a href="https://www.researchgate.net/publication/26877357_Verbal_Expressions_of_Confidence_and_Doubt">"Verbal Expressions of Confidence and Doubt"</a>, a psychology paper published in 2009, which rated the percieved self-confidence of speakers through their expression. The personal information of quoted persons such as their gender, birth year and occupation was retrieved from Wikidata. </p>

### Some statistics on the speakers:

<p style='text-align: justify;'> 
  Let's start by looking at the gender distribution of speakers: </p>
  
  <p align="center">
  <img src = "https://user-images.githubusercontent.com/57099519/146407324-36aafbcd-88af-4979-b1bc-b17186b46d66.png" alt = "gender distribution among speakers" >
  </p>
  
<p style='text-align: justify;'>
  We can see above that a vast majority of the speakers are females and males (these categories include cis-gender and unspecified females and males), even though there are still more male than female speakers. Speakers of other genders figure in the dataset as well, but in negligeable numbers compared to the leading categories. </p>
  
### Some statistics on the quotes: 

 <p style='text-align: justify;'> 
  Not all speakers are quoted the same amount. Let's look at the distribution of quotes per speaker: </p>
  
  <p align="center">
  <img src = 'https://user-images.githubusercontent.com/57099519/146403563-0ad30ce1-36a6-49e7-890c-d30cf2015127.png' alt = 'quotes per speaker'>
  </p>
  
<p style='text-align: justify;'>  
  As we can see above, it's clear not all the speakers have the same representation in the media, and thus our dataset. Although most speakers have less than 1000 quotes in the data set, some are quoted disproportionately.  Let's now take a look at the number of quotes by speakers of each gender: </p>
  
  <p align="center">
  <img src = 'https://user-images.githubusercontent.com/57099519/146404691-20accc2c-a576-4c3b-9db1-0654f76d1fff.png' alt = "number of quotes per gender">
  </p>
<p style='text-align: justify;'>  
  We can see a significant change in the distribution. By looking at the percentage of quotes by each gender, we notice that men represent over 70% of the quotes present in our dataset, while gender minorities representation is negligeable.. We will focus on the male and female gender from here on out. </p> 
  
  <p align="center">
  <img src = 'https://user-images.githubusercontent.com/57099519/146407136-ed8b97ef-3c81-4fc5-82e3-06342a1c07c3.png' alt = 'percentage male vs female'>
  </p>

### How we rate self-confidence:

<p style='text-align: justify;'> 
  As mentioned above, we based our metric of self-confidence on a <a href="https://www.researchgate.net/publication/26877357_Verbal_Expressions_of_Confidence_and_Doubt"> sociology study</a>, in which participants were asked to read a set of sentences, and rate the confidence of a person who would use those phrases, on a scale from 0 to 7, which we've converted to a 0 to 1 scale, 0 being unconfident, 1 meaning the speaker sounds very confident in that quote. The table below is a subset of the findings of the study: 
</p>

<center>
<table>
  <tr>
    <th>Phrase</th>
    <th>Score (past tense)</th>
    <th>Score (present tense)</th>
  </tr>
  <tr>
    <td>I'm not sure, it's kind of…  </td>
    <td>0.411429</td>
    <td>0.415714</td>
  </tr>
  <tr>
    <td>Oh, I don't know, I suppose…  </td>
    <td>0.42</td>
    <td>0.431429</td>
  </tr>
  <tr>
    <td>I suppose… </td>
    <td>0.477143</td>
    <td>0.477143</td>
  </tr>
  <tr>
    <td>I'm guessing, but I would say…</td>
    <td>0.417143</td>
    <td>0.484286</td>
  </tr>
  <tr>
    <td>I'm certain…</td>
    <td>0.842857</td>
    <td>0.935714</td>
  </tr>
  <tr>
    <td>I'm positive…</td>
    <td>0.851429</td>
    <td>0.938571</td>
  </tr>
  <tr>
    <td>I'm absolutely certain…</td>
    <td>0.904286</td>
    <td>0.944286</td>
  </tr>
</table>
</center>

<p style='text-align: justify;'> 
  There are different scores associated with present tense and past tense, as it has been found that it affects percieved confidence. We searched the quotes for matches to the phrases found in the article (from here on out referred to as confidence phrases) using NLTK, and assigned the score of said phrases. For quotes in which we found multiple confidence phrases, we kept the highest score. We then averaged the scores of all quotes by the same person, which gives us the estimated confidence score of a speaker. 
</p>
<p style='text-align: justify;'>   
  Here is the distribution of scores of quotes:
</p>

<p align="center"> 
  <img src ="https://user-images.githubusercontent.com/57099519/146444320-132f2357-60a3-4cf4-9215-a877089be876.png" alt = "distribution of scores across quotes" height = "576"> 
</p>

<p style='text-align: justify;'> 
  The data set from the sociology paper did not assign scores below 0.4, so distribution ranges from 0.4 to 1.  </p>
  
<p style='text-align: justify;'>
  The distribution of scores of speakers: </p>
  
<p align="center">
  <img src = 'https://user-images.githubusercontent.com/57099519/146608835-da7d49a1-e67a-4427-8f4a-e87bb7a9bec3.png'>
</p>

<p style='text-align: justify;'>
  We can see two significant peaks, which correspond to the past and present tense scores of <i><b>I think</b></i> (respectively 0.58 and 0.66). We can also note that most of the scores are between 0.575 and 0.875. Note that the minimal associated score for the confidence phrases we used was 0.42, this is why we don't observe score under this value.
</p>
  
  

# Analysis

## Which is more confident: men or women ? 

<p style='text-align: justify;'> 
  To answer this question we compared the confidence scores of women and men. Here is the distribution of scores for men and women: </p>
  
<p align="center"> 
  <img src = 'https://user-images.githubusercontent.com/57099519/146605430-725fd089-b624-47fc-b7cb-4e70de909e7e.png' alt = 'scores men vs women'>
</p>

<p style='text-align: justify;'> 
  Confidence scores of both genders follow a similar distribution, but the peaks at around 0.58 and 0.66 are much higher among men than women. We peformed a bilateral t-test on the score mean, which showed there was a significant difference between men and women (p-value = 0.027). Since the p-value of the unilateral t-test (0.013) is less than 0.05, we reject the null hypothesis (same mean for women and men) in favo of the alternative hypothesis: women's score mean is higher than that of men.
   </p>
<p style='text-align: justify;'> 
  Given social context, we would have expected women to be less confident than men, however results seem to show the opposite! We will continue our analysis by looking into expressions most commonly used by each gender.
</p>

## What expressions do the speakers use?

<p style='text-align: justify;'> 
  Now that we've established the scores of speakers, let's take a look at what kind of phrases hide behind the values. We first looked at the most commonly used confidence phrases by speakers: </p>
  
<p align="center">
  <img src = "https://user-images.githubusercontent.com/57099519/146449246-86fa45db-778c-450e-bc2c-8279472c70cb.png" alt = "most used expressions">
</p>

<p style='text-align: justify;'> 
  Unsurprisingly, <i><b>I think</b></i> (scores for present and past tense are 0.67 and 0.58 respectively) and <i><b>I know</b></i> (scores for present and past tense, 0.92	0.87 respectively) take the top two spots, and are used over ten thousand times each. The values also correspond to the peaks visible in the score distribution of speakers shown previously. </p>

### Men vs. Women

<p style='text-align: justify;'>
  Let's compare the expressions used by men and women: 
</p>

<p align="center"> <img src = 'https://user-images.githubusercontent.com/57099519/146534724-ae065289-1126-473a-8647-a398622d563c.png' alt = 'men confence phrases'>
<img src = 'https://user-images.githubusercontent.com/57099519/146534731-f5608943-f29e-4207-9ca8-36befaafb7b1.png' alt = 'women confidence phrases'>
</p>
<p style='text-align: justify;'> We can see the top 3 expressions are the same, however after that the order changes slightly: the fourth most used expression by men is <i><b>I'm sure</b></i> (scores present & past: 0.86,	0.79), and the sixth one is <i><b>I remember</b></i> (scores present & past: 0.75,	0.74), whereas they are swapped in the women's ranking. The same can be said also for <i><b>I'm confident</b></i> and <i><b>I suppose</b></i>.
</p>

### Which expressions should you use and which should you avoid?

<p style='text-align: justify;'>As we were able to establish a confidence score of speakers, let's take a look at the expressions used by the least and most confident speakers:</p>
<p align="center"> INSERER IMAGES MOST LEAST
</p>
<p style='text-align: justify;'> </p>

## Does being a politician influence self-confidence?

<p style='text-align: justify;'> Politicians, being public figures, often have to speak in front of large crowds. This should obviously better their speech skills, but would they really be percieved as more confident than other people? </p>
<p style='text-align: justify;'> To establish this, we used a subset of our data, only keeping US citizens. We then compared the scores of US Congresspeople to that of citizens. </p>

<p style='text-align: justify;'>
  First, the distribution of scores of people in the US congress versus not:  </p>
  
<p align="center">
  <img src = 'https://user-images.githubusercontent.com/57099519/146605996-ae05d1a6-87a7-4029-a93d-3369d48d83a6.png' alt = 'congress distribution'>
</p>

<p style='text-align: justify;'> 
  The distribution of scores of Congresspeople is smoother, most speakers having scores between 0.6 at 0.75, whereas the scores of normal citizens show the same peaks as prevously. Although the distribution is different, a statistic test shows there is no significant difference in score mean between the two groups (p-value = 0.75) for a 0.05 cutoff value.  </p>
<p style='text-align: justify;'> 
  Let's take a look at whether that changes if we focus on either gender: </p>
  
<p align="center">
  <img src = 'https://user-images.githubusercontent.com/57099519/146608092-70a9c4be-fb9e-4d82-9377-033e2a761b6d.png'> 
  <img src = 'https://user-images.githubusercontent.com/57099519/146606558-65fd8a09-0766-4e71-a918-0cbdcd4d1797.png' alt = 'female congress'>
</p>

<p style='text-align: justify;'> 
  Distributions of Congressmen and Congresswomen are also smoother than their civilian counterpart. Bilateral t-test show significant difference in neither score means (p-values = 0.13 and 0.08, for men and women respectively).  </p>
  
<p style='text-align: justify;'> 
  Lastly, let's see if the score distribution across genders varies among Congresspeople: </p>

<p align="center"> 
    <img src = 'https://user-images.githubusercontent.com/57099519/146607961-ef99d44b-4d91-4957-97fa-559dae1221e6.png' alt = 'female congress'>


# Conclusion


<p style='text-align: justify;'> </p>
<p align="center">
</p>
<b> </b>
