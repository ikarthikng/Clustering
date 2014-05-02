Clustering using Cosine Similarity.

1. Design
The tasks are as follows
•	Separate the Id, title, body and tags from the question given in the Train3.csv file
•	Select only the title and the body of the question
•	Randomly select clusters centroid from the given records based on the input from k.
(e.g if k = 3, then select three records (questions) three centroids for initial clustering)
•	Compute the tf-idf and also the cosine similarity of all the records from the chosen initial cluster centroid.
•	Initially, which tuple has the highest cosine similarity towards the chosen clusters group that record to that particular centroid
•	Further, compute the mean of the centroid based on the cosine similarities of the tuples, thus making the cluster centroid more accurate with respect to the clustering
•	Finally, group the questionIDs to the clusterIDs which has the highest similarity after computation
2. Implementation
1.	Read to csv file containing the data. I am using an open source tool called super csv reader to read the file at much faster rate and also I can clearly separate the ID, title, body and tags for further processing. 
2.	After separating the each field, I remove all the unwanted text using stop words. After cleaning the data.
3.	The title and body of all the questions are treated as documents. Each and every document is computed for tf (term frequency) and idf (inverse term frequency). 
4.	At random, k numbers of records are chosen as cluster centroids for initial clustering. 
5.	Using the tf and idf got the initial clustering we compute the cosine similarity of all the records with respect to the cluster centroids
6.	Depending on the similarities with the clusters, the records are assigned to one of the clusters.
7.	To improve clustering the mean of the clusters centroid values are calculated and clustering values are improved
8.	Thus, all the questionIDs will belong to one or the other clusterIDs when the result.txt file is formed.
3. Evaluation
The prediction model which is used in my project is successful to a good extent and it classifies properly the questions to their respective clusters. 
4. Test
1. The zip file contains the following items
•	Cluster.java
•	CosineSimeTest.java
•	lucene-core-4.6.0.jar
•	lucene-analyzers-common-4.6.0.jar
•	commons-math3-3.2.jar
•	super-csv-2.1.0.jar
•	result.txt
2. For compiling the java file please use the following method
javac –cp super-csv-2.1.0.jar; lucene-core-4.6.0.jar; lucene-analyzers-common-4.6.0.jar; commons-math3-3.2.jar *.java (windows)
javac -cp '/<full path>/super-csv-2.1.0.jar'; '/<full path>/super-csv-2.1.0.jar'; ‘/<full path>/lucene-core-4.6.0.jar’; ‘/<full path>/commons-math3-3.2.jar’; ‘/<full path/lucene-analyzers-common-4.6.0’ *.java
3. For running the program please use the following command
java -cp super-csv-2.1.0.jar; lucene-core-4.6.0.jar; lucene-analyzers-common-4.6.0.jar; commons-math3-3.2.jar. Cluster Train3.csv 3
java -cp .: '/<full path>/super-csv-2.1.0.jar'; '/<full path>/super-csv-2.1.0.jar'; ‘/<full path>/lucene-core-4.6.0.jar’; ‘/<full path>/commons-math3-3.2.jar’; ‘/<full path/lucene-analyzers-common-4.6.0’ Cluster Train3.csv 3
4. The result.txt is formed in the respective directory where Cluster.java and CosineSimeTest.java files are present.
