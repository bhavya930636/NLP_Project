# NLP_Project
## Colab notebook to generate gcn embeddings
https://colab.research.google.com/drive/1hXwVDXaZNORPKzLGCDuY-rFHdlj1G-ap#scrollTo=4CphwEueO0ih

## Reference doc
https://docs.google.com/document/d/1f4mydeBF1i8YYHRAtBxr6SRJRkVSqJkxzq9aW1gnLik/edit?tab=t.0

## Drive folder link for gcn embeddings
https://drive.google.com/drive/folders/1CxdDhPRZqcvLXDKxDfocmtVUD0YVqVxZ?usp=sharing

Catchphrases extracted using virtual environment
conda activate myenv . It uses python 3.7 and same gensim as in requirments. nltk, joblib, cudatoolkit, tensorflow may not be as in requirments 
also in the files wrap.py, models_d2v.py , annotate_docs.py, preprocessing_d2v.py, there are some changes 
New_catchphrases_140_citations has catchphrases of text where there are not duplicates 
nodes_140.csv has node and features using LegalBERT in array format
modified_new.csv has it in df format
edges_140.csv has edges 
text_catchphrase_case_embedding_140_100d.npy contains embeddings of catchphrases of cases using inLegalBERT for merging with node embeddings of metapath2vec
text_catchphrase_case_embedding_140_128d.npy contains embeddings of catchphrases of cases using inLegalBERT for merging with node embeddings of node2vec
/GNN/gat_embeddings_140_inLegalBERT.json contains embeddings of nodes using gat and embeddingsof catchphrases of cases and statutes as features in gat
/GNN/gcn_embeddings_140_inLegalBERT.json contains embeddings of nodes using gcn and embeddingsof catchphrases of cases and statutes as features in gcn

citations_raw_cases.ipynb is used to scrap citations of these cases from indiankanoon website 
which are stored in citations folder (1250+)
test folder contains 143 cases ke citations and headings_.txt contains the headings of those cases
Then Untitled.ipynb is used to make node entities of cases and citations 
(which uses headings.txt and headings_.txt) and links and citations folder and test folder
which are stored in data.json in the form of dictionary. 

data_140.json has it with no acts
data_140_withacts.json has it with acts
also it visualizes graph
Bib_Coupling_Co-citation.ipynb uses data.json to calculate these similarity scores 
Node2vec_metapath2vec.ipynb contains generation of node embeddings(using GCN,SAGE,GAT also) using
data.json and stores node embeddings in 
GCN.pkl, GCN(clustering.pkl),GAT.pkl.node2vec.pkl,meta2vec_A.pkl,meta2vec_B.pkl (4564 entries for all except meta2vec it has 5019 as metapath mein heterogeneous graph de rhe the))
node2vec_140.pkl for 140 cases with acts and not converting hetero to homo by our side

Text embeddings using doc2vec are in document_embeddings.npy
Concatenate_embeddings.ipynb uses text embeddings from document_embeddings.npy and other pkl files 
catch/1294_text contains rfc text for 1294 files
RFC.ipynb is used to find Reason for citing text from jugements
On google colab there is a file download_files_from_script.ipynb which is used to download specific files from headings.txt from RAW folder on drive 
Change default folder in settings and to not ask whether to open or save files
so the judgements corresponding to 1294 files are stored in catch_1294_cases


