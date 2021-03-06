---
template: post
title: Recommender Systems
slug: /recommender-systems
draft: false
date: 2019-12-13T05:31:09.695Z
description: >-
  Recommender Systems have become an integral part to many internet businesses.
  Percentage of users preferring recommendations have been increasing in the
  e-commerce world. In this blog, we go through some of the titbits about
  recommender systems. 
category: 'Machine Learning, Data Mining'
tags:
  - Machine Learning
  - Data Mining
  - Recommender Systems
---
I was working on a project for an e-commerce company, where we need to suggest users, products that go well with the other products. Something like _Amazon's Frequently Bought Together Section._

![frequently bought together](/media/frequently-bought-together.png "Frequently Bought Together in Amazon")

In layman terms, recommendations can be broadly divided into two types in e-commerce: 

* **Substitute Product Recommendations:** Recommending products that are similar to the product of interest.
* **Complimentary** **Product** **Recommendations:** Recommending products that go well with product of interest. Strategy here is to increase cross-sales.

A recommender system has to decide between two methods for information delivery when providing the user with recommendations:

**Exploitation:** The system chooses documents similar to those for which the user has already expressed a preference.

**Exploration:** The system chooses documents where the user profile does not provide evidence to predict the user’s reaction.

Most recommender systems focus on the task of information filtering, which deals with the delivery of items selected from a large collection that the user is likely to find interesting or useful. Recommender systems are special types of information filtering systems that suggest items to users. 

Talking technically, information filtering can be divided into three types:

* **Content Based Filtering:** Content-based filtering selects items based on the similarities between the content description of an item and the user’s preferences
* **Collaborative Filtering:** Collaborative filtering select items based on the similarities between the preferences of different users
* **Hybrid Filtering:** A hybrid approach, combining collaborative filtering and content-based filtering also exists.

We'll talk about all these filtering methods more in detail.

![Colloborative Filtering vs Content Filtering](/media/recommender.jpeg "Colloborative Filtering vs Content Filtering")

## **Content Based Filtering:**

Given user preferences for items, recommend similar items based on a domain-specific notion of item content. This approach also extends naturally to cases where item metadata is available (e.g., movie stars, book authors, and music genres).

A content-based recommender works with data that the user provides, either explicitly (rating) or implicitly (clicking on a link). Based on that data, a user profile is generated, which is then used to make suggestions to the user. As the user provides more inputs or takes actions on those recommendations, the engine becomes more and more accurate.

**Advantages of Content Based Filtering**

**User** **independence**: Collaborative filtering needs other users’ ratings to find similarities between the users and then give suggestions. Instead, the content-based method only has to analyse the items and a single user’s profile for the recommendation, which makes the process less cumbersome. Content-based filtering would thus produce more reliable results with fewer users in the system.

**Transparency**: Collaborative filtering gives recommendations based on other unknown users who have the same taste as a given user, but with content-based filtering items are recommended on a feature-level basis.

**No cold start**: As opposed to collaborative filtering, new items can be suggested before being rated by a substantial number of users.

**Disadvantages of Content Based Filtering**

**Limited content analysis:** If the content doesn’t contain enough information to discriminate the items precisely, the recommendation itself risks being imprecise.

**Over-specialization:** Content-based filtering provides a limited degree of novelty, since it has to match up the features of a user’s profile with available items. In the case of item-based filtering, only item profiles are created and users are suggested items similar to what they rate or search for, instead of their past history. A perfect content-based filtering system may suggest nothing unexpected or surprising.

## Collaborative Filtering:

Collaborative filtering (CF) systems work by collecting user feedback in the form of ratings for items in a given domain and exploiting similarities in rating behavior among several users in determining how to recommend an item.

CF accumulates customer product ratings, identifies customers with common ratings, and offers recommendations based on inter-customer comparisons. It’s based on the idea that people who agree in their evaluations of certain items in the past are likely to agree again in the future. For example, most people ask their trusted friends for restaurant or movie suggestions.

![User Based CF vs Item Based CF](/media/collaborative.jpeg "User Based CF vs Item Based CF")

As you can see from the picture, it describes two types of collaborative filtering methods:

* **User-based filtering**: A one liner to explain this would be "Users similar to you were also interested in". We filter out all the users who are most similar to the target user, and recommend him, the items which majority of them were interested in , which he didn't see or rate yet.
* **Item-based filtering**: A one liner to explain this would be "Users who were interested in this item were also interested in". Well, this may sound the same as User-based filtering, but there's a lot of difference on how we arrive at generating recommendations. We find out what are the items, that were also viewed or bought along with the target item, then we recommend the user these items which he hasn't seen.

A major appeal of collaborative filtering is that it is domain free, yet it can address data aspects that are often elusive. But collaborative filtering suffers from what is called the cold start problem, due to its inability to address the system’s new products and users. In this aspect, content filtering performs much better.

Two primary areas of collaborative filtering are:

* **Neighborhood methods**: Neighborhood methods are focused on computing the relationships between items or between users. The item oriented approach evaluated a user's preference for an item based on ratings of "neighboring" items by the same user.
* **Latent factor methods (Matrix Factorization):**  Latent factors models try to break down the user-item co-occurrence matrix into user matrix, item matrix. N number of latent factors are used to explain the interests or features of  a user. The discovered factors might explain obvious features of the domain, or may also correspond to much complex features. In a single liner, matrix factorization generalizes the data by reducing the dimensionality in such way where we observe useful patterns.

![matrix factorization](/media/blah.png "matrix factorization")

There are many algorithms that are available for matrix factorization, like AlternatingLeastSquares, Stochastic Gradient Descent, Single Value Decomposition, Logistic Matrix Factorization. I will try writing more about these algorithms in detail in the future blogs.
