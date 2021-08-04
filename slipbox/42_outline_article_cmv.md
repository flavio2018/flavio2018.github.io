## Introduction
The purpose of the research is to study dynamic of opinion changing analyzing interaction data from Reddit's forums CMV and AskReddit.

Research questions: given that behaviour change is defined as change in SP Subreddits which a user participates to;
- **RQ1**: does participation to CMV alone lead to greater change in user behaviour, compared to participation to AR?
- **RQ2**: does assigning a Delta in CMV lead to greater change in user behaviour, compared to participating to CMV and *not* assigning a Delta?
- **RQ3**: Does assigning a Delta lead to a *predictable* change in behavior?

## Methods
### Data collection and sampling
- Description of the dataset: submissions with profiles
	- definition of profiles: built on comments; 2 versions, boolean & n.comments based
- Temporal window of data
- Subreddits considered for the posts (CMV & AskRreddit)
- Subreddits considered for the comments used to build profiles (SP profiles)
- Stratified sampling for the control group: activity & participation to SP subreddits
- General statistics about the dataset

[55_article_cmv_data_collection](55_article_cmv_data_collection.md)

### RQ1
*Does participation to CMV alone lead to greater change in user behaviour, compared to participation to AR?*
- RQ1.1: behaviour change, defined both as Subreddits joined and left, is more frequent in participants in CMV than in AskReddit; Binomial test.
- RQ1.2: behaviour change, directed in particular towards SP Subreddits, happens more often in CMV than in AR; Binomial test.
- RQ1.3: behaviour change defined as the variation of the number of comments written in SP subreddits is in general stronger in CMV than in AskReddit; t-test + plot.

### RQ2
*Does assigning a Delta in CMV lead to greater change in user behaviour, compared to participating to CMV and *not* assigning a Delta?*
- RQ2.1: behaviour change, defined both as Subreddits joined and left, is more frequent in participants in CMV Delta than in CMV not-Delta; tested with a Binomial test.
- RQ2.2: behaviour change, directed in particular towards SP Subreddits, happens more often in CMV Delta than in CMV not-Delta; Binomial test.
- RQ2.3: behaviour change defined as the variation of the number of comments written in SP subreddits is in general stronger in CMV Delta than in CMV not-Delta; t-test + plot.

### RQ3
*Are posts on CMV where a user assigned a Delta useful to predict the Subreddits the user will start participating to?*
- structure of the classifier
- structure(s) of the input
- evaluation method and metrics, plots (micro-averaged AveP, PR-curves)

## Results

## Conclusions