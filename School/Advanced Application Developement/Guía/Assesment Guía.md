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

### Celda 9
Se eligen características **numéricas** y **categóricas**
```python
numerical_features_list = X_tabular_train.select_dtypes(include=np.number).columns.tolist()

categorical_features_list = [MAIN_CATEGORICAL_FEATURE_COLUMN] if MAIN_CATEGORICAL_FEATURE_COLUMN in X_tabular_train.columns else []
```

### Celda 10
Capas densas finales:
- Son **128 neuronas** porque no son ni muchas ni pocas.
- Función de activación **relu** porque es eficiente computacionalmente.
- En **dropout 0.5** se desactiva el 50% de las neuronas para no depender tanto de ellas.
- **Softmax** se usa el output porque transforma output en distribución de probabilidades.

```python
final_dense_1 = Dense(128, activation='relu', ...)(concatenated_features)

final_dropout_1 = Dropout(0.5, ...)(final_dense_1)

output_classification_layer = Dense(num_classes, activation='softmax', ...)(final_dropout_1)
```

## knn.ipynb
### Celda 7
- Se usan **7 neighbors** porque es impar.
- Se usa **minkoski distance** porque se adapta a diferentes tipos de datos.

```python
knn_model = KNeighborsClassifier(
	n_neighbors=KNN_N_NEIGHBORS #7,
	weights=KNN_WEIGHTS #distance,
	metric=KNN_METRIC #minkowski,
	n_jobs=-1
)
```

