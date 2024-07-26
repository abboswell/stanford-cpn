# The Stanford CPN
Stanford DataSci 112 Final Project Spring 2024:

*Adam Boswell and Jay Gupta*

# Introduction
This project concerns itself with the Stanford Course Prerequisite Network (CPN) during the 2023 and 2024 academic year. Understanding the relationship between courses is very important to a University’s educational mission. We employ a range of supervised and unsupervised methods to understand and ultimately and inform the Stanford educational structure. Machine Learning was done through the scikit-learn and networkX python libraries.

# Data Collection
Data was collected via the ExploreCourses API. The API readily provided the following features: subject, title, description, repeatable, grading basis, units min, units max, final exam, and academic group.
Notably, it did not list pre-requisite courses. In effect, we inferred these prerequisites via the text description.

# Network Properties 
In theory, CPNs are classified as Directed Acyclic Graphs (DAGs) though our CPNs include erroenous cycles due to difficulty processing the description text. Empirically, CPNs have a large
connected component denoted G. They also obey the familiar rules of real-world networks. For one, they are Scale Free meaning their degree distributions follow a power law. The in-degree is markedly lower than the out-degree suggesting that courses generally require few pre-requisites but open up many other courses in the network

# Neighborhood Detection
We ran the KMeans Algorithm to detect clusters based on course features. The text was passed via TFIDF Vectorizer. K was selected using the Elbow Method.

# Identifying Bridge Courses
The Betweenness Centrality of node v is the probability that v will appear in the shortest path of two nodes s and t for all such pairs. Intuitively, nodes with large betweenness centrality scores serve as
bridges between sources and sinks.

# Link Prediction
We employ the Jaccard Similarity algorithm to infer missing links, (i.e.) prerequisites from an undirected graph

