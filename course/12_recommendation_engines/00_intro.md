# Recommendation engines

THey can be divided in three main categories:
 * Knwoledge based: let the user to input specific filters (e.g. a movie's genre or a house minimum size), but does not rely on the user's history of purchases or any other profile-related data
 * Content based: include a user's data to improve the filtering
 * Collaborative filtering based: understand what a similar user might like by looking at another user's data

Ultimately, recommendation systems look at 4 main parts of a business. They are checked against:
 * Relevance
 * Novelty
 * Serendipity
 * Increase diversity


## Collaborative filtering based
this will be part of this chapter.
 * Neighborhood Based Collaborative Filtering: uses similarity and distance metrics to correlate recommendations targets
 * Model Based Collaborative Filtering: uses machine learning methods to correlate recommendations targets

### Neighborhood Based Collaborative Filtering

We need to look at ways to measure how similar two items are, therefore we rely on neighbourhood. We can look at:

Neighbourhood similarity (range -1 to 1, where 1 means similar):
 * Pearson's correlation coefficient: linear correlation
 * Spearman's correlation coefficient: non-parametric correlation (does not rely on how data is distributed)
 * Kendall's Tau: non-parametric correlation (does not rely on how data is distributed), less variant on large amount of data

Neighbourhood distance (range 0 to max_d, where 0 means close; note: these are sensible to the measure scale!):
 * Euclidean distance
 * Manhattan distance

If we want to recommend a movie to a user, a pretty standard to-do steplist would be:
 1. Remove movies our user has already seen.
 2. Find ratings of the neighbors that are high.
 3. Recommend movies to each user where both 1 and 2 above hold.

Recommendation targets can be:
 * User-related: the focus are users (e.g. since you watched these movies, you might also like.. - based on other users)
 * Item-related: the focus are items (e.g. if you bought this, then you might like that.. - based on items similarity)




![](img\00_recommendation.PNG)

