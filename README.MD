We train models that are already pre-trained by using transfer learning.
We take pre-trained model as base and fine tune that with new set of business data 

# Traditional ML: You usually decide which features to give the model, and the model learns how to combine them. - "I give you useful features; you learn how to use them."
# Neural network: You give it the data, and the neural network can learn much more complex relationships between the inputs and the price. - "I give you the data; you learn useful patterns/features and how to use them."

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
2. Build 4 programs -  
  DataCurate = 
    a. Parser.py - This will parse above data into the struture that we have defined or need in items.py
    b. items.py - This will use  for basemodel to take data from parser.py 
    c. loaders.py - Download Amazon product data → split it into chunks of 1,000 → process the chunks in parallel → remove bad/invalid records → return the cleaned items.
  DataPreProcessing = 
    d. batch.py - This will run Groq in batch mode to process 20k and 800k data in batch mode using LLM processing to create JSONL files
# Processed Data- 
# https://huggingface.co/datasets/ed-donner/items_lite
# https://huggingface.co/datasets/ed-donner/items_full
3. Baseline Models and Traditional ML - The goal of ML is to generalize to make accurate predictions on unseen data
  a. BasicPricePredictor - Some random price predictor 
  b. Linear Regress - Error rate is high 
  c. Bag of word (e.g. common words 2000) and then use NLP Linear Regresion - Error rate goes down
  d. Random forest and XGBoost - This is like running mini several decision trees and fixing errors rates - Final rate comes down
4. Neural Network and Frontier LLMs 
    Four steps of training - Tweaking the parameters of model based on training data (data is chunked in the batches) in a way that will generalize the unseen data and also tune hyperparameter (eg Epoch(iteration) and learning rate (steps))
    a. Forward Pass - Predict the output given the input
    b. Loss calculation - How different was the prediction to the ground truth. Reduce loss - Stochastic Gradient Descent
    c. Backward Pass - How should we tweak parameters to do better next time, tuning === the gradients
    d. Optimization - Update parameters a tiny step to do better next time