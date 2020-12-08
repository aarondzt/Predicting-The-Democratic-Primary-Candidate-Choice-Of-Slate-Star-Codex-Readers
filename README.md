# Predicting the Democratic primary candidate choice of Slate Star Codex readers

## Contents
* [Data source](https://slatestarcodex.com/2020/01/20/ssc-survey-results-2020/)
* [Data file](2020ssc_public.xlsx)
* [Report](Report.ipynb)
 
### Introduction
This project is a continuation of my work on the [Slate Star Codex 2020 Reader Survey](https://slatestarcodex.com/2020/01/20/ssc-survey-results-2020/). Some information on the dataset, from my [previous work](https://github.com/aarondzt/Slate-Star-Codex-voter-demographics):

Slate Star Codex (SSC) is a blog by the pseudonymous author Scott Alexander. The blog is a fixture of the "rationalist" community, an internet community that seeks to analyze difficult problems in science, culture, and politics with high standards of reason. For example, almost every SSC post features citations from peer-reviewed papers and some degree of statistical reasoning. Despite being pretty unknown to the general public, Scott's writing has a sizable impact on academics, entrepreneurs, and tech professionals across the globe. When a reporter at the New York Times threatened to dox Scott in an article about the blog, thousands, including many influential public figures, signed a [petition](https://www.dontdoxscottalexander.com/) to halt the article. Each year, Scott conducts a survey of his readers and publishes the results online. I thought it would be profitable to shed some light on the nature of this unique online community. Herein, I look at the demographics of those who participated in the 2020 survey. In particular, I am interested in the demographic breakdown of responses to the question "If you could vote in the US Democratic primary, who would you vote for?"

In my previous work, I did an exploratory data analysis, and found that:

...the readers of SSC are very unrepresentative of America, in interesting ways. Of 4361 American responders, the readers are vastly male and white. The average age is around 35. To my surprise, over a third of readers are married, though most have zero children. Most work white collar computer-related office jobs. Most identify as atheist, despite most being raised in religious environments. For the most unrepresentative statistic, the plurality voted for Andrew Yang in the Democratic Primary, with Elizabeth Warren and Bernie Sanders in second and third, and Biden in a distant sixth.

### Goals
My main goal was to learn more about this very interesting community by attempting to predict their choice of Democratic primary candidate from the very interesting features contained in this survey. Along the way, I gained more experience with feature engineering and worked with a multi-class classification problem for the first time.

### Overview

Here, I am interested in looking at the data as a multi-class classification problem, with Democratic primary candidate choice as the target. I only looked at the top six candidates, ranging from Andrew Yang in first (with 28% of the vote) to Joe Biden in sixth (with 8% of the vote. For a baseline comparison, a random guess would mean 17% accuracy, and choosing the first candidate for all predictions would mean 28% accuracy. Because many of the features are categorical, I did a lot of feature engineering to make them more informative to the classification algorithm. I ran a logistic regression with cross-validation and grid search to fine tune parameters. I then viewed the highest magnitude beta values for each candidate to examine which features were most important for classifying observations for each candidate. My model achieved a balanced accuracy of 48% in the test set. In short, if you were at a bar and you randomly met a Slate Star Codex reader, you could simply ask them a few questions regarding the features of this dataset (e.g. "how do you feel about Donald Trump?" or "how do you feel about feminism") and have roughly a 50% chance of guessing the exact candidate they voted for!

### Limitations
Obviously, because this is such an unrepresentative sample, the conclusions of this project cannot be applied to America as a whole. 

### Future directions
In the future, I would like to try other machine learning algorithms that are amenable to multi-class classification problems and compare their performance to logistic regression.

## Project Info
<pre>
Contributors : <a href=https://github.com/aarondzt>Aaron Tan</a>
</pre>

<pre>
Languages    : Python
Tools/IDE    : Anaconda
Libraries    : numpy, pandas, statsmodels, sklearn
</pre>

<pre>
Date published     : 12.08.2020
</pre>
