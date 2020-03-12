# Article Recommendations on IBM Watson Studio

### Overview
In this project, our objective is to increase users' interaction with an online forum. The lever we can control is the articles in the forum that we can show to users. In particular, we expect that if we show users articles that relate to their interests, then users will likely engage more with the forum. To this end, we collect data and investigate the interactions that users have with articles on IBM Watson Studio platform and then provide recommendations of articles that users may like. We will use a series of different recommending techniques that we think will fit different groups of users. 

### Dataset
Our dataset contains nearly 46,000 records of user interactions on IBM Watson Studio. For each record, we have the user email (encrypted for privacy) and information about the article that user interacted with. The first few rows of the dataset is shown below.

![alt text](/figures/user-interact.PNG "u-i")

Together with user-article interactions, we have information about articles on the forum as follows.

![alt text](/figures/articles.PNG "a")

### Recommendation System
For **new users**, we use rank-based recommendation to provide them with the most popular articles on the platform. 

For **existing users**, we provide them two different kinds of articles. The first is what their most similar colleagues like and mostly interact with (collaborative filtering). The second is based on latent features that we learn from users viewing habit (matrix factorization). The two methods should be deployed online at the same time to complement each other. While collaborative filtering is strong at finding the articles users may like, it often suggests articles that users already know about. In other words, it somehow lacks the "surprise" element in its recommending style. Matrix factorization may complement this weakness by recommending from latent features learned from users reading habit.  
