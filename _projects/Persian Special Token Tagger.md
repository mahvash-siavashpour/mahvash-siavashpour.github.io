---
layout: page
title: Persian Special Token Tagger
description: Tagging tokens in a sentence with special Persian annotations called Kasr-E-Ezafeh
img: assets/img/Kasr-E-Ezafeh.png
importance: 2
category: Artificial Intelligence
---
[Link to Github](https://github.com/mahvash-siavashpour/BERT-Token-Classification-for-Persian-Kasr-e-Ezafeh) <br>
Each persion word in a sentance either has a Kasr-e Eafeh or it does not. Kas-e Ezafeh comes in 3 different forms as shown bellow:
- @e
- e 
- ve 
- y 
- ye

Using a BERT token classification model from pretrained ```HooshvareLab/distilbert-fa-zwnj-base``` enables us to train the model on this specific task. The dataset could not be published due to copyright but this is a sample of what it looks like:
```
سلسله	ye
ایرانی	O
در	O
سوادکوه	e
مازندران	O
حکومت	O
می‌کردند	O
.	O
نفوذ	e
برامکه	O
)	O
وزرای	ye
ایرانی	O
(	O
در	O
دربار	e
عباسی	O
```

Each token of the data has a label indicating its Kasr-e Ezafeh. Tokens without a tag are labeled as O .

## Training
The model is trained using the [Huggingface](https://huggingface.co/) library with a pretrained bert model from [HooshvareLab/distilbert-fa-zwnj-base](https://huggingface.co/HooshvareLab/distilbert-fa-zwnj-base) . <br>
After preprocessing the data and tokenizing, it is fed into the model. The model is trained in 3 epochs with a batch size of 16.

## Results
The results during the training phase after each epoch are shown bellow:
<br>
{% include figure.html path="assets/img/kare-ezafeh-table.png" title="table" class="img-fluid rounded z-depth-1" %}
<br>
