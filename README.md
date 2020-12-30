# Info retrieval Project
Authors: Marc McCombe & Xiangyu Lu

# Program description:
A complete information retrieval system that reads a vast document collection consisting of thousands of documents. Based on an 
inputted user query the program will return a ranked list of relevant documents found in the collection.
Using the vector space retrieval model and the TF-IDF weighting scheme to create an inverted index as well as assign weights to terms
found in each document. Implemented stemming and stop word removal algorithms to group similar terms and remove unimportant terms. 
Each documents PageRank score is also calculated based on in and out links. Once completed and the inverted index and dictionary 
are finalized, the user search feature was implemented to accept multi-word queries. Based on this query it will retrieve relevant
documents based on its cosine similarity and combine these scores with their corresponding PageRank score to return a complete 
ranked list of relevant documents.

This project was done in Java utilizing nested hashmaps, algorithm optimization, file searching and data management.

# Scheme we followed to implement the pagerank score: 
● 2d array to create matrix. To store the page to page relationship <br/>
  ○ Based off of the .X section in cacm.all <br/>
● Normalize the matrix (be aware of rows with all zeros) <br/>
● a = 0.85 damping value ● The matrix * (1-a)  <br/>
● The matrix * (a/N) to get final P matrix <br/>
● Do the iteration, 15- 20 iterations for our set <br/>
● Normalized the matrix for matching the similarity score: by multiplying 10000 to each unit in the matrix. <br/>
● Use the linear combination to combine the previously calculated cosine similarity score with the PageRank score as follows:<br/> 
  score(d, q) = w1*cos-score(d, q) + w2*pagerank(d) where w1+w2=1. Note that w1 and w2 should be set as input parameters. <br/>

# How to run the project 
● Open the terminal window, then type the following; <br/>
● % javac Invert.java <br/>
● % java Invert <br/>
● Following the instruction <br/>
● Then posting.txt and dictionary.txt will be generated <br/>
● %javac Search.java <br/>
● %java Search <br/>
● User enters weight values for cosine similarity score and pagerank score <br/>
● User enters desired query term, then hit return; ranked documents with the final score will be printed out; <br/>

# Additional feautures (Generating AP and MAP values of some pre-written queries)
● %javac Eval.java <br/>
● %java Eval <br/>
● User enters the weight values for  cosine similarity score and pagerank score (w1 and w2). <br/>
● The program will give AP values of each query found in query.txt as well as the final MAP value <br/>
