This project rebuilds our offline Pre-Encryption Ransomware Detection RAG system using the LangChain framework (LCEL). 

It evaluates the identical 4 knowledge base files (`my_kb/`) and 8 gold-set questions (`goldset.json`) using standard document loaders, recursive text splitters, Chroma vector stores, and score-threshold retrievers. 

The goal is to compare empirical retrieval metrics, refusal discipline, and developer abstraction trade-offs between our hand-rolled implementation and the LangChain framework.
