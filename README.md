# Data Exploration of the Aprendemos Student Data Set

***By Doug Dahl***


## Overview

Aprendemos is a web application (https://www.aprendemos.io/info) that I developed during my time as a Teach for America corps member. About 200 students from grades 7-10 used this application, with a frequency ranging from roughly bi-weekly to consistent, daily use. Students used this application to complete entrance and exit tickets during their math classes. As they completed their assignments those students also submitted self-report questionnaires about their emotional states while the platform collected some rudimentary behavioral data. 

In this dataset, I will be working with features representing academic performance indicators, self-reported emotional status, frequency of app usage, and more. The dataset spans a collection period of ~10 months, and is comprised of 2367 entries.


## Purpose

Aprendemos was originally made with the purpose of providing teachers proactive notifications when a student had a behavioral and emotional profile that was likely to precede an acute behavioral or emotional event during the school day. These notifications were intended to improve proactivity and trust in student-teacher relationships, and consequently reduce teacher bias in discipline. 

While Aprendemos did include a feature that allowed teachers to record behavioral or emotional incidents that students were involved in throughout the day, the feature was not often used, which puts a limit on the data relevant to my original goal of understanding the antecedents to increased student behavioral and emotional needs. Additionally, the number of data entries per student was large for some groups of students, while others only used the platform a handful of times beginning halfway through the year. Because of this, the data are likely to be biased towards trends in those early adopter classrooms than trends overall. Furthermore, the early adopter classrooms were all in title 1 school districts in Houston, TX, and so the data can only claim to represent trends relevant to the demographics of those first few pilot classrooms. Despite these limitations, the data that was collected with Aprendemos has still proven to be a great resource in better understanding the the emotional worlds of the platform's student users, as well as the potential impact of these emotions on academic outcomes. As more daily emotional student data is collected, the findings here should provide a valuable foundation for future exploration.

In this notebook specifically, I will conduct data ingestion, visualization, and introductory analysis using typical Python packages such as Matplotlib and Seaborn for data visualization, as well as Scipy, and Pandas for data manipulation and introductory analysis. In an upcoming notebook, I will analyze these data further in an attempt to identify patterns or clusters relating to students' self-reporting habits, academic success, and fundamental behavioral markers.

In the subsequent sections of this report, I will discuss the data ingestion process, followed by detailed data visualization and interpretation. In the final part, I will outline potentially interesting features for the upcoming cluster identification.


## What You'll Learn!

Clear expectations are one of the fundamental parts of a good lesson plan! Through this introductory data analysis, you can expect to explore the following questions (and more!):

   - Does student performance vary throughout the week?
   - Do student emotions influence one another? 
   - Does student performance vary based on their self-reported emotional state?
   - How do different students approach formative assessments?
   - How do different students behave when asked to self-report emotions?
   
   

# Conclusion:

I have put a lot of effort into working on Aprendemos over the past two years. This was a project that I built and piloted while also working full-time as a teacher, and neither my effort nor the project itself would have been possible without the students that inspired me in the first place. My overarching aim, beyond this project, continues to be empowering proactivity, trust, and insight in student support. I'm employing my experience from this project and continuing to work towards this mission with my current venture at Abloom (www.abloomai.com).


### Key findings

There are a few key takeaways from the exploration of the Aprendemos data:

1. Based on Aprendemos' entrance and exit ticket data, it looks like the best performing day of the week is Wednesday, and the worst is Tuesday.

2. Motivation and confidence have the most statistically significant relationship of all the emotions measured with an r of 0.642 and a p-val < 0.05. The relationship between motivation and confidence was ~5-10% stronger than that of the other emotions. 

3. Based on Aprendemos data, confidence seems to be the emotion with the most significant relationship to academic performance. With that said, the relationship isn't a high strength one. (Confidence and academic performance are correlated with a coefficient of:  0.16 and a p-val of:  4.52e-15)

4. Based on Aprendemos data, the average amount of time a student spends on an entrance and exit ticket is moderately positively correlated to average performance on entrance and exit tickets. This relationship exists without any constraints on time, but is strongest for students who spend up to, but not more than, 10 minutes on their entrance and exit tickets. (The average time a student spent on their quiz and the average score for that student are correlated with a coefficient of  0.49  and a confidence of p =  2.44e-09  when we exclude the top quartile of time taken on the quiz)

5. A student's average academic performance and their variance in self reported mood have a weak-to-moderate negative correlation. This relationship is strengthened when excluding the top 25% of mood variance cases from the observation. (Academic performance is correlated to variance in self reported mood with a coefficient of  -0.21 and a confidence of  0.02)

6. All self-report metrics have a moderate-to-strong correlation with one another, and all self-report metrics are strongly skew left. Self report mood has a slightly less skewed distribution.

### Interpretations

1. The fact that the observed relationship between motivation and confidence was stronger than the other inter-emotion relationships could speak to a change in motivation brought on by increased confidence, or vice versa. Students with high confidence are more likely to want to complete the day's work, and students who are intrinsically motivated might also have higher confidence in class as a result of their mindset on learning.

2. It seems likely that students who spent more time on their assignments on average were also completing those assignments more carefully. This also makes sense when given the cutoff mark of 10 minutes for an assignment. Students who spent longer than 10 minutes on an assignment on average could potentially have been putting off doing their work or could also have been exhibiting a lack of confidence in their subject knowledge.

3. Variance in mood's negative correlation to academic performance is particularly interesting. The relationship between emotional well-being and academic success is discussed often, but largely anecdotal (at least in the discussions I've been a part of). Finding a significant relationship here is a really encouraging signal towards further exploration of the relationships between emotions and academic outcomes. This also offers some measure of internal validity to the self report metrics generally, since their variance can (at least in the case of self-reported mood) be shown to correlate somewhat to some behavioral metrics.

4. The fact that there were moderate correlations between the variance of all of the self-report metrics suggests that there might be relevant student groups that could be discovered by analyzing patterns of self-report metrics. The fact that high variance in self-report mood correlated to decreased academic performance is especially interesting in this context, because it means that the student groups we might uncover through investigation of simple patterns in their self-report data could have some predictive power in areas that are extremely important to academic success. 


### Limitations

As discussed previously, there were some limitations in the alignment of Aprendemos' collected data and it's original aim of uncovering relationships between emotional state and behavioral presentation. Additionally, the data set was only representative of a small slice of classrooms in one city in the US, and didn't represent a large sample size of students (Though many of the existing users were well represented by consistent, near-daily use for stretches of time). Finally, this emotional data is limited in the sense that it was collected by a daily self-report survey that didn't change aesthetically, and the group being surveyed ranged in age from 13-16. As such, it's likely that there was a bias towards under-reporting emotions both as a result of the demographic being surveyed, and as a result of the interface of the survey itself.

### Implications

Aprendemos data has shed a preliminary light on the complex relationship between student emotions and their academic success. One striking takeaway was the far-reaching implications of student confidence, extending beyond its own realm to influence performance and emotions in several other areas. Focusing on student confidence and building them up to the idea that they can be successful is a powerful tool. It's an approach that worked well in my classroom, and I would love to offer this "confidence first" teaching mentality as an adage solidly backed by data as a result of this exploration. In reality, though, I think this data set serves mostly to begin a further and more detailed exploration into how a student's emotional well-being might impact all areas of their academic and personal success. 

I do think, however, that these introductory clues towards potential student emotional and behavioral clusters are interesting and worth exploring further. Reaching knowledge that affords some predictive power will allow us to create tools that improve proactivity in student support & truly understand the impact of student emotions on their behavior. Such tools and understandings would be invaluable in supporting student success, and I'm happy to have begun the journey here with Aprendemos.


### Future Work

Like I mentioned in the introduction, I am interested in doing a cluster analysis on this data set to see if there are any interesting groups that can be identified when it comes to student behavior, self-reporting patterns, and academic outcomes. All of this work also serves as an initial foundation for future work with Abloom, through which there will hopefully be a set of data that's much larger, more feature rich, and representative of a wider range of students. The understanding built here in this initial exploration will hopefully lower the time to activation for uncovering insights in those future data on student well-being and behavior.


### Thank You!

Thanks for taking the time to read through all of this! Like I mentioned, I'm currently (as of 8/23) working towards furthering an understanding of student emotions with my work at Abloom (www.abloomai.com). If you're interested, definitely check us out! There will hopefully be much more interesting data and much more depth of understanding to come in the near future.

