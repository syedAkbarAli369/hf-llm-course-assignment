

Computer can't understand the human language. Natural Language Processing (NLP) is the way that computers can understand the human language. Large Language Models (LLMs) are transformer models trained on massive amount of texts and data, so one model can do many jobs like translate, summarize, answer questions instead of one model only doing one job

pipeline() function is the lazy shortcut you just need to define a task (sentiment analysis, text generation, summarization, translation, f/b) and pipeline() function loads a ready model for you that is what I did on Google notebooks

Concept of transformer started when 2017 famous papers published "Attention Is All You Need". The main idea is attention to every word. When reading a word the model looks at all the other words and decides which ones matter. Like reading "I am hungry" and knowing "I" refers to me

There are three types of transformers
a. Encoder only (BERT style): It reads the whole sentence and understands it important for classification
b. Decoder only (GPT style): predicts the next word one at a time for generating text and this is what ChatGPT models are 
c. Encoder-Decoder (T5 and BART style): reads input and then writes output good for translation and summarization

Training a model has two stages: Pretraining means the model learning language from huge amount of data by itself and Fine tuning a model is then teaching it one specific job needs to work on also called transfer learning and it saves huge cost
Limits and bias: The models learns from what is on internet so they might pick up its biases and can say wrong things confidently. That is why their is small line on each models that This chatbot can make mistakes