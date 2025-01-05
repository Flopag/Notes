# Web and Text Analytics

- [Info_Retrieval_and_VSM](Slide_notes/Info_Retrieval_and_VSM.md)
- [TFIDF](Slide_notes/TFIDF.md)
- [text_classification](Slide_notes/text_classification.md)
- [RNN](Slide_notes/RNN.md)
- [Contextual_embeddings](Slide_notes/Contextual_embeddings.md)
- [Word_Embeddings](Slide_notes/Word_Embeddings.md)
- [Lecture_Intro_MT](Slide_notes/Lecture_Intro_MT.md)
- [MT_Evaluation](Slide_notes/MT_Evaluation.md)
- [Introduction_to_attention](Slide_notes/Introduction_to_attention.md)
- [Attention_Mechanism_in_NLP](Slide_notes/Attention_Mechanism_in_NLP.md)
- [LLMs](Slide_notes/LLMs.md)
- [Tranformers_from_scratch(LLaMa)](Slide_notes/Tranformers_from_scratch(LLaMa).md)

## Big summary (following [this](exam_content_notes.md))

### Document scoring

- [Jaccard index](Slide_notes/Info_Retrieval_and_VSM.md) : 
	- is overlapping of two sets : computed by counting the number of elements that appear in the two sets divided by the number of elements in the rest
	- Limitations : do not take occurrence and do not normalize documents length
- [Vector space model (VMS)](Slide_notes/Info_Retrieval_and_VSM.md) :
	- One vector per document
	- Count the number of occurrence of a word in the document (can be $0$)
	- Words are dimensions and their occurrence are the length of the vector in this dimension
- [Proximity Metric](Slide_notes/Info_Retrieval_and_VSM.md) : 
	- Measure the distance between two VMS
	- by Euclidean distance ($d_{euc} = \sqrt{\sum_{i=1}^n ( x_i - y_i )^2}$) : penalize large vectors
	- by angular distance ($\theta = \cos^{-1} {\frac {\sum_{i=1}^n x_iy_i}{||x|| \ ||y||}}$) : do not penalize large vectors, only look to relevant dimensions (words)
		- size of a vector is computed using $||x|| = \sqrt{\sum_{i=1}^n x_i^2}$

## [Term-Frequency Inverse-Document Frequency (TFIF)](Slide_notes/TFIDF.md)

- Term-frequency : the more mentions of a query is, the more relevant the document is
	- Documents with most words same as query have most values
	- Limitations : unimportant terms will grow the score (as "the")
- Inverse-Document Frequency : the less mentions of a query there is in all documents, the more relevant term is
	- Overall rare words have more values
- TFIF : combination of both
	- $TFIDF_{t, d} = tf_{t,d} \times \log \frac{N}{df_t}$
	- Where :
		- $tf_{t,d}$ is the number of occurrence of term $t$ in document $d$ (term frequency)
		- $df_t$ is the number of occurrence of term $t$ in all documents
		- $N$ is the number of documents of the collection

## Text classification

### Features selection : 

- is the process of selecting a subset of relevant features from the full set of features of the dataset
	- Feature = value given as input
- Two types of methods :
	- Linguistic methods : Identify features based on linguistic information (e.g. grammar)
	- Statical methods : Identify features based on the occurrence frequency
		- TFIDF (see above)
		- Mutual information : the amount of information that the term contains about the class (see [here](Slide_notes/text_classification.md) to get formula)
		- Chi-square : the amount of dependence between events (see [here](Slide_notes/text_classification.md) to get formula)
			- big values is big dependence