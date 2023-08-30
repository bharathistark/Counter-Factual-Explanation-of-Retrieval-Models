# Counter-Factual-Explanation-of-Retrieval-Models
Pyserini 
Pyserini is a Python toolkit for reproducible information retrieval research with sparse and dense representations. Retrieval using sparse representations is provided via integration with our group's Anserini IR toolkit, which is built on Lucene. Retrieval using dense representations is provided via integration with Facebook's Faiss library.

Prebuilt Indices of msmarco dataset using folloing retrival models are used for information retrieval.

Traditional lexical models  using LuceneSearcher.
Learned sparse retrieval models using LuceneImpactSearcher.

Generating counterfactuals for multi-class classification and regression models
DiCE library can be used for multiclass classification and regression for scikit-learn models. You can use any method ("random", "kdtree", "genetic"), just specific it in the method argument in the initialization step. The rest of the code is completely identical. For demonstration, we will be using the genetic algorithm for CFs.

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
