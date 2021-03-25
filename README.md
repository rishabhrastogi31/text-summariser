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
![image3](https://user-images.githubusercontent.com/48548360/112428014-8dc7f200-8d60-11eb-9f93-7e156b25f767.png)
![image6](https://user-images.githubusercontent.com/48548360/112428015-8dc7f200-8d60-11eb-889d-e564a1054e59.png)
![image5](https://user-images.githubusercontent.com/48548360/112428016-8dc7f200-8d60-11eb-8e7f-24e37489bb32.png)
![image9](https://user-images.githubusercontent.com/48548360/112428017-8dc7f200-8d60-11eb-97a0-d1aa98070983.jpg)
![image8](https://user-images.githubusercontent.com/48548360/112428019-8dc7f200-8d60-11eb-9171-ad7abeaadede.png)
![image8](https://user-images.githubusercontent.com/48548360/112428020-8e608880-8d60-11eb-8aca-abb8d8330d5c.png)
![image6](https://user-images.githubusercontent.com/48548360/112428021-8e608880-8d60-11eb-9974-b3db807b3c59.png)
![image10](https://user-images.githubusercontent.com/48548360/112428022-8e608880-8d60-11eb-9d93-9348c4fd0965.png)
![image5](https://user-images.githubusercontent.com/48548360/112428024-8e608880-8d60-11eb-89db-39b0a8ddc1be.png)
![image9](https://user-images.githubusercontent.com/48548360/112428027-8ef91f00-8d60-11eb-84a1-5c0373358f47.jpg)
![image9](https://user-images.githubusercontent.com/48548360/112428028-8ef91f00-8d60-11eb-8f2e-a3a862f2f25f.jpg)
![image8](https://user-images.githubusercontent.com/48548360/112428029-8ef91f00-8d60-11eb-8010-8893a937f5de.png)
![image6](https://user-images.githubusercontent.com/48548360/112428030-8ef91f00-8d60-11eb-93f3-0ce7ef920bf5.png)
![image1](https://user-images.githubusercontent.com/48548360/112428032-8ef91f00-8d60-11eb-8388-6e7e335d99e4.png)
![image10](https://user-images.githubusercontent.com/48548360/112428033-8ef91f00-8d60-11eb-8828-cccedb668208.png)
![image10](https://user-images.githubusercontent.com/48548360/112428036-8f91b580-8d60-11eb-9b30-5d1c866e9cb4.png)
![image9](https://user-images.githubusercontent.com/48548360/112428037-8f91b580-8d60-11eb-9c76-a319c3203ac9.jpg)
![image8](https://user-images.githubusercontent.com/48548360/112428038-8f91b580-8d60-11eb-8763-92dc4473d054.png)
![image3](https://user-images.githubusercontent.com/48548360/112428039-8f91b580-8d60-11eb-9ad9-06f55acb3316.png)
![image1](https://user-images.githubusercontent.com/48548360/112428040-8f91b580-8d60-11eb-957e-4c66ffcd6549.png)
![image10](https://user-images.githubusercontent.com/48548360/112428042-902a4c00-8d60-11eb-8de4-2fdd9b3a6b2f.png)
![image1](https://user-images.githubusercontent.com/48548360/112428043-902a4c00-8d60-11eb-8458-65a4958e6bb1.png)
![image9](https://user-images.githubusercontent.com/48548360/112428044-902a4c00-8d60-11eb-90f5-95a15ac667fb.jpg)
![image5](https://user-images.githubusercontent.com/48548360/112428045-902a4c00-8d60-11eb-92a3-9e1f2504fb14.png)
![image3](https://user-images.githubusercontent.com/48548360/112428046-902a4c00-8d60-11eb-920d-8b2feb5a5013.png)
![image1](https://user-images.githubusercontent.com/48548360/112428048-90c2e280-8d60-11eb-8fc5-c0f33759e29f.png)
![image3](https://user-images.githubusercontent.com/48548360/112428049-90c2e280-8d60-11eb-9471-53e6ac21bacc.png)
![image10](https://user-images.githubusercontent.com/48548360/112428050-90c2e280-8d60-11eb-81a4-7d4675ffec48.png)
![image6](https://user-images.githubusercontent.com/48548360/112428052-90c2e280-8d60-11eb-9928-dde445d52810.png)
![image5](https://user-images.githubusercontent.com/48548360/112428053-90c2e280-8d60-11eb-804b-ef49593f0be7.png)

![image10](https://user-images.githubusercontent.com/48548360/112428071-9a4c4a80-8d60-11eb-9614-e2012c1b3c08.png)
![image9](https://user-images.githubusercontent.com/48548360/112428078-9b7d7780-8d60-11eb-96a3-124436e26b0f.jpg)


