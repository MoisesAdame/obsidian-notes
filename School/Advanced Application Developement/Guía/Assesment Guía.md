---
tags:
---
Date: 2025-06-10 : 12:07
***
## cnn.ipynb
### Celda 8
Esto sirve para hacer una representación numérica del texto y poder meterlo en la CNN.

```python
tokenizer = Tokenizer(num_words=VOCAB_SIZE_MAX, oov_token="<unk>")
tokenizer.fit_on_texts(texts_train)

actual_vocab_size = min(VOCAB_SIZE_MAX, len(tokenizer.word_index) + 1)

sequences_train = tokenizer.texts_to_sequences(texts_train)
sequences_test = tokenizer.texts_to_sequences(texts_test)
```
