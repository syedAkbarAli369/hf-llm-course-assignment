


Prepare the data. You load a dataset (the chapter uses a sentence-pair dataset called MRPC), run every sentence through the tokenizer, and use a data collator to pad each batch so all sentences in it have the same length. 

Set the rules. TrainingArguments holds the settings. The only thing you must give it is a folder to save the model and checkpoints, and everything else has working defaults. 

Load the model. You add a fresh classification head on top of the pretrained BERT body. You'll see a warning for this, and it's normal: the original head was thrown away because BERT wasn't pretrained for classifying sentence pairs. 

Train with the Trainer. You hand the Trainer the model, the data, the tokenizer and the settings, then call trainer.train().

Measure it. By default it only reports loss, which isn't very meaningful. You need to set an evaluation strategy and give it a compute_metrics function, which then reports accuracy and F1. 

The chapter then repeats the whole thing with a hand-written PyTorch training loop, and covers extra tricks like mixed precision and learning-curve reading.
