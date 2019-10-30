# Recommendation validation

**Online testing**

A metric could be used to validate a recommendation system, and then running an A/B test on it.


**Offline testing**

We want to test out our recommendations in a training-testing environment prior to deploying them. <br/>
It would be great if we have an idea of how much each user would like each item using a predicted rating. Then we can compare this predicted rating to the actual rating any individual gives to an item in the future. We can use MSE (mean squared error) or MAE (mean absolute error) to assess the performance. Finally, this tackles the problem of the impossibility to test if a user actually like a movie if he/she hasn't seen it. And the user might never see that movie, making our assessment impossible through online testing.

**User groups**

An alternative would be to select user groups to give feedbacks on recommendation. The problem here is to sample such groups to correctly represent the broader customers pool.