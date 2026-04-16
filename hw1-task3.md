# Homework 1 Task 3

---

Answer the following questions based on exercises from *An Introduction to Statistical Learning with Applications in Python*.

## Chapter 2.4 Exercises

---

### Exercise 1 (ISLP exercise 2)

Explain whether each scenario is a **classification or regression** problem, and indicate whether we are most interested in **inference or prediction**. Finally, provide **n** (size of observation dataset) and **p** (number of predictors).

**(a)**  We collect data on 200 protected marine reserves worldwide. For each reserve we record species richness, reserve size, years since establishment, enforcement budget, and proximity to human settlements. We are interested in understanding which factors affect species richness.

> **Your Answer:**

This is a regression problem because species richness is a numeric outcome. We are modeling an actual count, not assigning reserves to categories. We are primarily interested in inference rather than prediction, since the goal is to understand which factors drive species richness, not to forecast it for new reserves. The dataset has n = 200 observations and p = 4 predictors: reserve size, years since establishment, enforcement budget and proximity to human settlements. Species richness is the response variable Y, not a predictor.

---

**(b)** A conservation agency wants to know whether a proposed habitat corridor will successfully support wildlife movement or fail to do so. They collect data on 30 previously established corridors. For each corridor they have recorded whether wildlife movement was successful or unsuccessful, corridor width, length, surrounding land use type, and eight other variables.

> **Your Answer:**

This is a classification problem because the outcome, whether proposed habitat corridor will successfully support wildlife movement or fail, is a binary category, not a number. The agency is interested in prediction, since the goal is to forecast whether a new, proposed corridor will succeed or fail, not to understand which variables drive success. The dataset has n = 30 observations (one per corridor) and p = 11 predictors: corridor width, length, surrounding land use type and eight other variables. Whether wildlife movement succeeds or fails is the response variable Y, not a predictor.

---

**(c)** We are interested in predicting weekly average ground-level ozone concentration in a coastal city. We collect weekly data for all of 2019. For each week we record average ozone concentration, sea surface temperature, wind speed, solar radiation, and atmospheric

> **Your Answer:**

This is a regression problem because weekly average ozone concentration is a continuous numeric outcome. The goal is prediction, we want to forecast ozone levels, not understand which variables drive them. The dataset has n = 52 observations (one per week across all of 2019) and p = 4 predictors: sea surface temperature, wind speed, solar radiation, and atmospheric pressure. Average ozone concentration is the response variable Y, not a predictor.

---

### Exercise 2 (ISLP exercise 5)

What are the advantages and disadvantages of a very flexible (versus a less flexible) approach for regression? Under what circumstances might a more flexible approach be preferred to a less flexible approach? When might a less flexible approach be preferred?

> **Your Answer:**

A very flexible approach for regression has the advantage of being able to fit a much wider range of shapes and patterns in the data, which means it can capture complex, nonlinear relationships that a simpler model would miss, leading to lower bias. However, the main disadvantage is that it is much harder to interpret. With methods like deep learning, it becomes nearly impossible to understand how each individual predictor is actually influencing the response. On top of that, flexible models tend to overfit the training data. They follow the noise in the data rather than the true underlying pattern, and this causes them to perform poorly when predicting new observations, which is the key trade-off. More flexibility reduces bias but increases variance. A less flexible model will sometimes give accurate predictions than the most flexible model available, which seems counterintuitive but happens because of overfitting.

A more flexible approach is preferred when the goal is prediction and interpretation does not matter. The model just needs to produce accurate forecasts, not explain how each predictor affects the response. It is also preferred when the true relationship between the predictors and the response is genuinely complex and nonlinear, because a rigid model like linear regression would be too simple to capture that pattern and would produce biased results. Finally, a more flexible approach works better when there is a large amount of data available, because with more observations the model has enough information to learn the true underlying pattern without simply following the noise in the training data.

A less flexible approach is preferred when the goal is inference rather than prediction. It shows how each individual predictor affects the response. In this case, simpler models like linear regression are much more interpretable and make it easier to draw conclusions about the relationship between the predictors and the response. A less flexible approach is also preferred when the sample size is small relative to the number of predictors, because a highly flexible model would overfit the data by chasing noise rather than capturing the true underlying pattern, and would perform poorly on new observations. Similarly, when the true relationship between the predictors and the response is approximately linear or simple in nature, adding more flexibility brings no real benefit and only increases variance without meaningfully reducing bias. In short, a less flexible approach is the safer and more sensible choice whenever interpretability matters, data is limited, or the underlying relationship is not expected to be highly complex.

---

### Exercise 3 (ISLP exercise 6)

Describe the differences between a **parametric** and a **non-parametric** statistical learning approach. What are the **advantages** of a parametric approach to regression or classification (as opposed to a non-parametric approach)? What are its **disadvantages**?

> **Your Answer:**

A parametric approach estimates the relationship between predictors and the response by first assuming a specific shape or form for that relationship, and then using the training data to find the parameters that define it. For example, assuming a linear model means only a few numbers (the coefficients) need to be estimated from the data. The advantages of this approach are that it can work well even with a small training dataset, it is computationally simpler because only a few parameters need to be estimated, and simpler functional forms make inference easier since it is clearer how each predictor relates to the response. The disadvantages are that if the assumed shape is far from the true relationship, the model will produce inaccurate predictions, and overall prediction accuracy may not be as good as more flexible approaches.

A non-parametric approach does not assume any particular shape for the relationship between the predictors and the response. Instead, it lets the data determine the form of the estimate, trying to get as close to the training observations as possible without being too rough. The difference between the two approaches is: parametric methods simplify the problem by assuming a shape and estimating a few numbers, while non-parametric methods are more flexible but need more data, are more prone to following noise in the data, and are generally harder to interpret.