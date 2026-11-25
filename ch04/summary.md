

Think of the Hugging Face Hub as GitHub for AI models. Chapter 4 teaches you to publish your trained model there so anyone can download and use it.

Why share. When someone shares a model, even a very specific one, it saves others time and compute. 
huggingface
Log in first. You need an access token with write permission. In a notebook you run notebook_login(), in a terminal you run huggingface-cli login.
Three ways to make a repo for your model: the push_to_hub API, the huggingface_hub Python library, or the web interface. 
huggingface
The easiest way is during training. Set push_to_hub=True in TrainingArguments, and the Trainer uploads your model every time it saves a checkpoint. The repo is named after your output folder, and hub_model_id lets you pick a different name. After training, call trainer.push_to_hub() for the final version. 
huggingface
huggingface
You can also push manually: model.push_to_hub("name") and tokenizer.push_to_hub("name") put both in one repo. Then open the Hub, check the Files and versions tab, and your model is live.
The model card is the README of your model. It's where you tell others what it does, and it can be generated automatically with the hyperparameters and evaluation results. 
huggingface

Exam angle: Hub, model card, tokenizer and model are shared together, and why that's useful.