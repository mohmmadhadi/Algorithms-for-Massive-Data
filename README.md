# Algorithms-for-Massive-Data-Project

Online review platforms accumulate millions of short, noisy texts that often contain duplicated or near–duplicated content. Detecting such redundancy is useful for downstream analytics (e.g., opinion mining, recommendation, and quality control), and it is also a classical testbed for large–scale similarity search. In this project, I study near–duplicate detection on the Amazon Books Reviews dataset using a distributed pipeline built with PySpark, Spark NLP, and MinHashLSH.

The technical goal is to retrieve pairs of reviews that are highly similar in content without performing an infeasible all–pairs comparison. To that end, I first apply light normalization and tokenization, then construct tri–gram shingles to capture local phrase structure. Each review is embedded as a sparse, binary vector via the hashing trick (HashingTF), and candidate pairs are retrieved with MinHash locality–sensitive hashing. Jaccard similarity is used as the target measure; Spark returns Jaccard distance from the LSH join, which I convert to similarity as 1-distance.

Code is fully available here on Github as a colab notebook.
