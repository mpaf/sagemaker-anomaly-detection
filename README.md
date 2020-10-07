# SageMaker Continuous Anomaly Detection

SageMaker algorithms:
https://docs.aws.amazon.com/sagemaker/latest/dg/algos.html

## Questions about the data

- *"I want to group current and prospective customers into 10 groups based on their attributes. How should I group them?"* For this type of question, SageMaker provides the **K-Means Algorithm**

- *"What are the attributes that differentiate these customers, and what are the values for each customer along those dimensions."* For this type of question, SageMaker provides the **Principal Component Analysis (PCA) Algorithm** algorithm

## Random Cut Forest (RCF) Algorithm

https://docs.aws.amazon.com/sagemaker/latest/dg/randomcutforest.html

Amazon SageMaker Random Cut Forest (RCF) is an unsupervised algorithm for detecting anomalous data points within a data set.

**Particularly suited for continuous learning**, an improvement over Isolation Forest algorithm and developed for anomaly detection. Defers difficult computation to the simulation or 'inference' phase while keeping updates simple.

From: https://opendistro.github.io/for-elasticsearch/blog/odfe-updates/2019/11/random-cut-forests/:

*"There is a drawback, however, to the approach of combining a powerful partition rule with a simple inference rule: trees in an RF model cannot be updated dynamically and have to be rebuilt in order to accommodate changes to the training data set. This comes to the fore in the context of continually evolving data streams. While micro-batch or mini-batch forest rebuilding strategies are reasonable for large static data sets, continually evolving streams have a premium on recency that necessitates continuous learning. Continuous learning in this scenario decomposes into an update phase, in which the model data structures are updated with new data, and an inference phase."**

*Random Cut Forests (RCF) are organized around this central tenet: updates are better served with simpler choices of partition. More advanced algorithms in the inference phase can compensate for simpler updates. There are two immediate benefits of following this tenet. First, it provides a general purpose framework that enables continuous learning over data streams. RCFs serve as sketches or synopses of evolving data streams and multiple different scoring functions or even different types of forests are supported with the same set of trees.*
