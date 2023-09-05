Retrieval models have risen in prominence across a wide range of disciplines, including information retrieval, recommendation systems, and question-answering systems. These models, however, often lack transparency and interpretability, making it difficult for users to comprehend why particular results are produced. Counterfactual explanations are a valuable strategy for dealing with this dilemma since they provide alternate situations that may have resulted in different outcomes.
The primary objective of this research is to develop a model capable of generating counterfactual explanations for retrieval models, thereby enhancing transparency and interpretability. Retrieval models play a crucial role in identifying relevant documents for a given query. However, understanding why a particular document received a high or low ranking can be challenging. Counterfactual explanations have the potential to overcome this challenge by offering clear and interpretable explanations of how the model's ranking would change if specific elements were altered.
# Pyserini
Pyserini is a Python toolkit for reproducible information retrieval research with sparse and dense representations. Retrieval using sparse representations is provided via integration with our group's Anserini IR toolkit, which is built on Lucene. Retrieval using dense representations is provided via integration with Facebook's Faiss library.

# DiCE - ml
 DiCE is based on recent research that generates CF explanations for any ML model. The core idea is to setup finding such explanations as an optimization problem, similar to finding adversarial examples. The critical difference is that for explanations, we need perturbations that change the output of a machine learning model, but are also diverse and feasible to change.

## install

```
pip install pyserini 
```
```
pip install dice-ml
```
```
pip install faiss-cpu --no-cache 
```
```
pip install numpy
```
Dependencies:

- [pytorch](https://pytorch.org) <3
- [numpy](https://numpy.org/install/) <3
- [pandas](https://pandas.pydata.org/docs/getting_started/install.html) <3
-  `Pyserini` for information retrieval <3 (to load Lucene searchers)
-  `sklearn` for preprocesing datasets <3
-  `DiCE-ml` for counterfactual explaination  <3


## quick start

If you are not a deep learning professional and you just want to feel the magic and get your feet wet, the fastest way to get started is to train a character-level GPT on the works of Shakespeare. First, we download it as a single (1MB) file and turn it from raw text into one large stream of integers:

Download and load the prebuilt index for msmarco-v1-passage dataset using Lucene searcher.
```
Lsearcher = LuceneSearcher.from_prebuilt_index('msmarco-passage')
```
Download and load the prebuilt index for msmarco-v1-passage-unicoil dataset using Lucene impact searcher.
```
LIsearcher = LuceneImpactSearcher.from_prebuilt_index('msmarco-v1-passage-unicoil','castorini/unicoil-msmarco-passage')
```

# K Number of documents to retrieve
```
hits = searcher.search(query, k)
documents = [(hit.docid, hit.raw, hit.score) for hit in fetchs]
```
# Extract the raw document texts
```
document_texts = [searcher.doc(hit.docid).raw() for hit in fetchs]
```
# Create a TF-IDF vectorizer
```
vectorizer = TfidfVectorizer(max_features=10000, token_pattern=r'\b[A-Za-z]+\b', stop_words=stop_words)
```
# Print the classified documents
```
  for doc_id, doc_text, doc_score, classification in classified_documents:
    print(f"\nDocument ID: {doc_id} Document score: {doc_score} Classification: {classification}")
```
# Output for Query "what is the color of amber urine"
```
Document ID: 8077666 Document score: 15.093400001525879 Classification: 1

Document ID: 8077670 Document score: 14.685600280761719 Classification: 1

Document ID: 1794262 Document score: 14.173999786376953 Classification: 1

Document ID: 6398884 Document score: 14.064599990844727 Classification: 1

Document ID: 266682 Document score: 13.404800415039062 Classification: 0

Document ID: 1794263 Document score: 13.379799842834473 Classification: 0

Document ID: 817614 Document score: 13.322199821472168 Classification: 0

Document ID: 7653670 Document score: 13.297800064086914 Classification: 0

Document ID: 8703497 Document score: 13.166899681091309 Classification: 0

Document ID: 1838949 Document score: 13.154399871826172 Classification: 0
```
# Sckit learn tool train_test_split creates x_train, x_test, y_train, y_test split` in that dataset.
```
  x_train, x_test, y_train, y_test = train_test_split(datasetX,
                                                      target,
                                                      test_size=0.2,
                                                      random_state=0,
                                                      stratify=target)
```


## acknowledgements
@INPROCEEDINGS{Lin_etal_SIGIR2021_Pyserini,
   author = "Jimmy Lin and Xueguang Ma and Sheng-Chieh Lin and Jheng-Hong Yang and Ronak Pradeep and Rodrigo Nogueira",
   title = "{Pyserini}: A {Python} Toolkit for Reproducible Information Retrieval Research with Sparse and Dense Representations",
   booktitle = "Proceedings of the 44th Annual International ACM SIGIR Conference on Research and Development in Information Retrieval (SIGIR 2021)",
   year = 2021,
   pages = "2356--2362",
}

@inproceedings{mothilal2020dice,
        title={Explaining machine learning classifiers through diverse counterfactual explanations},
        author={Mothilal, Ramaravind K and Sharma, Amit and Tan, Chenhao},
        booktitle={Proceedings of the 2020 Conference on Fairness, Accountability, and Transparency},
        pages={607--617},
        year={2020}
}
