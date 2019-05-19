<h1>Model</h1>

`DeepExpressions.Model` is an instance to predict the facials expressions within an image based on trained classifiers available at [DeepExpressions-models](https://github.com/deepexpressions/DeepExpressions-models).

**Arguments:**
> * **model_name:** Name of the model.
> * **custom_model:** Path to custom model saved (only *.h5 files).

```python
from DeepExpressions import Model
model = Model(model_name, custom_model=None)
```

<h3>Model Methods</h3>

<h4>predict:</h4>

Predicts facial expressions from input data.

**Arguments:**
> * **input_data:** Images to predict. It can be np.ndarray, tf.Tensor or a list of the previous types.
> * **labeled_output:** Returns predictions with names rather than one-hot-encoded.

```python
model.predict(input_data, labeled_output=True)
# [Happy, Surprise, ...]
```

---
<h4>summary:</h4>

Prints a summary representation of the model loaded.

```python
model.summary()
# Model: "ce-xception-512-256"
# _________________________________________________________________
# Layer (type)                 Output Shape              Param #   
# =================================================================
# xception (Model)             (None, 4, 4, 2048)        20861480  
# _________________________________________________________________
# global_average_pooling2d_1 ( (None, 2048)              0         
# _________________________________________________________________
# dense_3 (Dense)              (None, 512)               1049088   
# _________________________________________________________________
# dense_4 (Dense)              (None, 256)               131328    
# _________________________________________________________________
# dense_5 (Dense)              (None, 7)                 1799      
# =================================================================
# Total params: 22,043,695
# Trainable params: 10,660,559
# Non-trainable params: 11,383,136
# _________________________________________________________________
```

---
<h4>train_info:</h4>

Prints some training information about the model loaded.

```python
model.train_info()
# Model: "ce-xception-512-256"
# ________________________________________________________________________________
# Parameter                   Value  
# ================================================================================
# ConvNet                     Xception
# Dataset                     Compound Facial Expressions Database
# NN-Layers                   [512, 256]
# ________________________________________________________________________________
# Optimizer                   Adam      
# Learning rate               1e-3
# Epochs                      30      
# Epochs (fn)                 15
# ConvNet layers (fn)         100+
# ================================================================================
# * fn = fine-tunning

# ================================================================================
# https://github.com/deepexpressions/models/tree/master/models/ce-xception-512-256
# ================================================================================
```