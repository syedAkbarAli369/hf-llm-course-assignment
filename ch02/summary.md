

Tokenizer: A model can't read text, only numbers. The tokenizer splits your sentence into tokens (words, sub-words, punctuation) and swaps each one for an ID number. You must use the same tokenizer the model was trained with, otherwise it's like ordering in a language the kitchen doesn't speak. It gives you input_ids (the numbers) and attention_mask (1 for real tokens, 0 for padding).

Padding and attention mask: If you send two sentences of different lengths, the shorter one gets filled with zeros so they fit in one box. The attention mask tells the model "ignore those zeros".

AutoModel turns the IDs into hidden states: a big vector for every token. Its shape in the lesson was [2, 16, 768], meaning 2 sentences, 16 tokens each, 768 numbers per token. That 768 is the hidden size, the same d_model idea in your TOCI notes.

The head: The hidden states are too big to be useful on their own. The head is a few small layers that squeeze them into what you need. For sentiment, it outputs 2 numbers (one per label: positive, negative).

Postprocessing: Those 2 numbers are logits, raw scores that aren't probabilities. Softmax turns them into percentages that add up to 100, and then the model's label map turns them into POSITIVE or NEGATIVE.