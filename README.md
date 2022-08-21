Anaconda Version: conda 4.12.0
Python Version: Python 3.9.7


Libraries required:
nltk
pandas
numpy
matplotlib
pickle
re
scikit learn
transformers 
seqeval[gpu] 
sentencepiece 
torch

NOTE: Make sure you have the following packages installed in your system in order to run the project

-----------------------------------------------------------------------------------

Q1 Workflow/steps to run:

Datasets: https://www.cfilt.iitb.ac.in/~diptesh/embeddings/monolingual/non-contextual/hi.zip
	    https://drive.google.com/file/d/1D6rYA3QpgDEZSRlVgp0qIQ6a9JdHGdYR/view?usp=sharing

1. Open the notebook and run all the cells. 
2. Extract the above datasets and make sure the folders, 'hi' and 'Word Similarity' are in the current directory
3. You will see 40 different files for different models, for different thresholds. They are:

./Q1_FastText 50d_similarity_4.csv              ./Q1_Word2Vec CBOW 100d_similarity_7.csv
./Q1_FastText 50d_similarity_5.csv              ./Q1_Word2Vec CBOW 100d_similarity_8.csv
./Q1_FastText 50d_similarity_6.csv              ./Q1_Word2Vec CBOW 50d_similarity_4.csv
./Q1_FastText 50d_similarity_7.csv              ./Q1_Word2Vec CBOW 50d_similarity_5.csv
./Q1_FastText 50d_similarity_8.csv              ./Q1_Word2Vec CBOW 50d_similarity_6.csv
./Q1_Glove 100d_similarity_4.csv                ./Q1_Word2Vec CBOW 50d_similarity_7.csv
./Q1_Glove 100d_similarity_5.csv                ./Q1_Word2Vec CBOW 50d_similarity_8.csv
./Q1_Glove 100d_similarity_6.csv                ./Q1_Word2Vec skipgram 100d_similarity_4.csv
./Q1_Glove 100d_similarity_7.csv                ./Q1_Word2Vec skipgram 100d_similarity_5.csv
./Q1_Glove 100d_similarity_8.csv                ./Q1_Word2Vec skipgram 100d_similarity_6.csv
./Q1_Glove 50d_similarity_4.csv                 ./Q1_Word2Vec skipgram 100d_similarity_7.csv
./Q1_Glove 50d_similarity_5.csv                 ./Q1_Word2Vec skipgram 100d_similarity_8.csv
./Q1_Glove 50d_similarity_6.csv                 ./Q1_Word2Vec skipgram 50d_similarity_4.csv
./Q1_Glove 50d_similarity_7.csv                 ./Q1_Word2Vec skipgram 50d_similarity_5.csv
./Q1_Glove 50d_similarity_8.csv                 ./Q1_Word2Vec skipgram 50d_similarity_6.csv
./Q1_Word2Vec CBOW 100d_similarity_4.csv        ./Q1_Word2Vec skipgram 50d_similarity_7.csv
./Q1_Word2Vec CBOW 100d_similarity_5.csv        ./Q1_Word2Vec skipgram 50d_similarity_8.csv
./Q1_Word2Vec CBOW 100d_similarity_6.csv



-----------------------------------------------------------------------------------


Q2 Workflow/steps to run:

Datasets: 
https://drive.google.com/file/d/1AqZMqkAGUK7P-X_jXB9OddDJStTTUHE2/view?usp=sharing

1. Upload the given notebook in Google Colab, choose 'GPU' in resources, and Run all the cells. 
2. It will take 10-15 minutes for the model to train and give results on the training, validation and test sets
3. The notebook can be accessed directly at https://colab.research.google.com/drive/1JIghxsUBGTXe8bmg2kuEIS2n4pmE3wtH?usp=sharing  
4. References:
	a. https://www.freecodecamp.org/news/getting-started-with-ner-models-using-huggingface/
	b. https://colab.research.google.com/github/NielsRogge/Transformers-Tutorials/blob/master/BERT Custom_Named_Entity_Recognition_with_BERT_only_first_wordpiece.ipynb
	c. https://skimai.com/how-to-fine-tune-bert-for-named-entity-recognition-ner/

-----------------------------------------------------------------------------------


Q3 Workflow/steps to run:

Datasets:https://storage.googleapis.com/ai4bharat-public-indic-nlp-corpora/indiccorp/hi.tar.xz

1. break.ipynb notebook file divides the entire dataset into smaller files of 0.25GB each and puts them in 'splits' folder.
   NOTE: Please create an empty folder called 'splits' before running this notebook and place the file,
   'hi.txt' - the original dataset(https://storage.googleapis.com/ai4bharat-public-indic-nlp-corpora/indiccorp/hi.tar.xz) ~ 22G, in the current directory

2. q3_b.ipynb reads the files in 'splits' folder, one by one and for each file, creates a dictionaries 
   of unigrams, bigrams and trigrams and stores them in the respective folders namely, [unigrams, bigrams, trigrams]. 
   After this step, for each of the n-grams, it fetches the pickle files, merges them, and outputs the top
   100 n-grams for each. These are again stores as pickle files, namely:
   1. ./top_100_bi.pkl
   2. ./top_100_uni.pkl
   3. ./top_100_tri.pkl

   One more output file is generated which contains all the unigrams and their value counts:
   - uni_all.pkl

   NOTE: This code is very time consuming, ~5-6 hours on local machine. If you wish to run this code, Please
   create three empty folders in the same directory namely: unigrams, bigrams, trigrams

3. q3_a_c.ipynb takes input the file generated in previous step, uni_all.pkl, and calculates the output as 
   specified in the question. Following pickle files are generated:

   a.
   ./top_100_bi_a.pkl      ./top_100_quard_a.pkl   ./top_100_tri_a.pkl     ./top_100_uni_a.pkl

   c. 
   ./top_100_bi_c.pkl      ./top_100_tri_c.pkl     ./top_100_uni_c.pkl

4. q3_d.ipynb reads the output files as mentioned above and checks if the frequencies follow Zipfian distribution.

-----------------------------------------------------------------------------------
-----------------------------------------------------------------------------------
-----------------------------------------------------------------------------------
AN ALTERNATE WAY TO RUN Q1, Q3-D IS USING MAKEFILE:

- Open the terminal in the directory having the Makefile and issue the command, "make run"
- For q3-d, keep closing the graphs in order to view the next graph. It can be better viewed in the corresponding notebook.

-----------------------------------------------------------------------------------
-----------------------------------------------------------------------------------
-----------------------------------------------------------------------------------

Please be patient while running the codes. This assignment involved a lot of cpu/gpu/tpu intensive processing. Thank you.







