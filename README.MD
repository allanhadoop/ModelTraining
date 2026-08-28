We train models that are already pre-trained by using transfer learning.
We take pre-trained model as base and fine tune that with new set of business data 

1. Curate the data 
2. Pre-process the data 
3. Baseline Models and Traditional ML 
4. Neural Networks and Frontier LLMs
5. Fine-tune Frontier LLMs
6. Fine-tune Open-Source LLM
7. Deploy Model, RAG, Agentic Product

----Data - Kaggle and Huggingface datasets(McAuley-Lab-Amazon-Reviews 2023) ------------
1. Training data - Learn patterns to make new prediction
2. Validated data - Held-out data used to evaluate how well model has generalized
3. Test data - Held-out data to confirm model prediction accuracy

The dataset is here:
https://huggingface.co/datasets/McAuley-Lab/Amazon-Reviews-2023

And the folder with all the product datasets is here:
https://huggingface.co/datasets/McAuley-Lab/Amazon-Reviews-2023/tree/main/raw/meta_categories


Model Performance Metrics -
a. Model-centric or Technical metrics (Loss)
b. Business-centric or outcome-centric 

--------Steps ---------
1. Download data from Huggingface - Amazon review 
2. Build 2 programs -  
    a. Parser.py - This will parse above data into the struture that we have defined or need in items.py
    b. items.py - This will use  for basemodel to take data from parser.py 

    