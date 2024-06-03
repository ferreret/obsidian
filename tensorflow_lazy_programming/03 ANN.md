Artificial neural networks

## Feedforward neural networks

Forward propagation

**relu** it's the default activation function for hidden layers

### Clasificación binaria
```python
tf.keras.layers.Dense(1, activation='sigmoid')
```

### Multiclassification

Ultima capa:
```python
tf.keras.layers.Dense(K, activation='softmax')
```
