# text-summariser
automatic  extractive text summariser

FOR SUMBASIC SUMMARIZATION
STEP-1: first with the use of web scraping and beautifulsoup tool we get the desired article from wikipedia or from any other reliable site which provides documentaries along with the max length and sentence after that user enters a topic from wikipedia
STEP 2 : PreProcessing (removing stop words, non letter characters, turning to lower case letters) This was the first stage in the algorithm in which the entire text was converted in lower case letters to maintain uniformity and non alphabet characters were removed. Along with that stop words (a, an etc) were also removed from the text using nltk’s stopwords list. Stop words are words like ‘is’,’and’,’or’ etc. which are not of much importance.
STEP-3) now after running the cleaning function and finishing preprocessing we tokenize and calculate probability and store in probability dictionary these probabilities will be used for calculating average sentence weights and the words with highest sentence probabilities are used to finally generate summary
	

TEXTRANK ALGORITHM	
Textrank is a graph-based approach of extractive text summarisation. Our program works like this:-
The program first parses through the online ‘.html’ page containing both the document and the summary. Both are extracted and stored in the program.
The summary(let’s call it  model summary) is then stored in a text file to be later used as the ‘ground truth’ and help in calculating the ROUGE scores. 
The input document is then tokenised into sentences. Each sentence is then cleaned(i.e, removed of any extra unwanted text for e.g, website links, extra whitespaces, non-alphanumeric characters) before being further divided. 
After cleaning the sentences, only the text to be processed remains. Sentences are further split upto words, which are lemmatized. All the  stopwords(set of commonly used words) are then removed so that the algorithm can focus on the more important words.
A sentence similarity matrix of size N x N  is then formed, where ‘N’ is the number of cleaned sentences. 
The cleaned sentences are converted into vectors using Glove embeddings, and using a similarity metric(here, we have used cosine similarity) we compare all the sentences with each other and store the calculated result in the matrix.
A graph is created where all the sentences are vertices, and there are edges between sentences which each represent the similarity between them .
Over a large number of iterations,we evaluate the pagerank score for each vertex/sentence which is used to assign the importance of the sentence/vertex in the graph. 
We iterate till we reach convergence(i.e, the sentence scores do not change much, and are within the range of acceptable error. ) 
The top k sentences are then extracted, sorted according to their position in the actual document and then joined again.
The generated summary(let’s call it system summary) is then compared with the model summary and then are evaluated together to form ROUGE scores.



![image1](https://user-images.githubusercontent.com/48548360/112428010-8c96c500-8d60-11eb-8d2a-a885cf1e9001.png)
![image3](https://user-images.githubusercontent.com/48548360/112428007-8c96c500-8d60-11eb-8c3f-c09468132aaa.png)
![image5](https://user-images.githubusercontent.com/48548360/112428008-8c96c500-8d60-11eb-9288-ecd69edd9071.png)
![image6](https://user-images.githubusercontent.com/48548360/112428009-8c96c500-8d60-11eb-8e07-687c768ce907.png)
![image8](https://user-images.githubusercontent.com/48548360/112428006-8c96c500-8d60-11eb-957d-cae567b3de69.png)



