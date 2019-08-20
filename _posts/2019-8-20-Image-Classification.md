---
layout: posts
title: "Image Classification with FastAI"
date: 2019-08-20
tags: ["fastai"]
---

After learning the history and the building blocks of GOFAI in 6.034, I decided to see what the state of the art was. After looking around, going through a of Andrew Ng's Coursera videos, Geoff Hinton's videos, and eventually looking to Twitter, I found [fast.ai](fast.ai).

FastAI has a MOOC called "Practical Deep Learning for Coders," which I thought would be a good introduction to deep learning, as I had also looked through Goodfellow's <i>Deep Learning</i> and found it hard to understand without concrete working examples.

The first homework is image classification. Given a labelled data set, that is each image has a label associated with it, we want to train a classifier such that we can feed it images and it produces the correct label for the input image. This is an example of supervised learning. I decided to use the cards from one of my favorite childhood games, Wizard101.

<h2>Data Collection</h2>

First, I had to scrape and label all the cards in the game. You can find more details [here](/projects/93-wizard101/) under scraping.

Beginning the program, I imported the relevant module and checked to see if my program could see the card images.

```python
from fastai.vision import *

path = Path('cards/')

fnames = get_image_files(path/'death')
fnames[:5]
```

This produced WindowsPath objects that referenced the cards, so that part was good.

<h2>Setup</h2>

Next, I created an ImageDataBunch from the cards. An ImageDataBunch is a class that holds your images. In order, it gets passed where the training set is, what percentage of the data to use for validation, what kind of transforms we should apply to the data, and what it should regularize the size to. We also create a convolutional nerual net (CNN) [ResNET learner](https://arxiv.org/abs/1512.03385) from the data.

```python
data = ImageDataBunch.from_folder(path, train='.', valid_pct=.2,
        ds_tfms=get_transforms(), size=224, num_workers=0).normalize(imagenet_stats)
learn = cnn_learner(data, models.resnet34, metrics=error_rate)
```

<h2>Visualization</h2>

Next, we view the data to make sure the transformations are what we want.

```python
data.show_batch(rows=3, figsize=(7,8))
```

This yields the following:

<img src="/assets/img/posts/2019-8-20-Image-Classification/transformed-images.jpg">

Looks good! Next, we want to train our model.

<h2>Training</h2>

We run five epochs, meaning we feed our CNN each of the images once. The output is in the image, and our final error rate is .16, so we already have 84% of the data classified correctly.

```python
learn.fit_one_cycle(5)
```

<img src="/assets/img/posts/2019-8-20-Image-Classification/epochs.jpg">

Next, we fine-tune the model. Looking at the loss vs. learning rate, we want the lowest point. Therefore we do ```python learn.fit_one_cycle()``` again, passing the max learning rate of around 1e-02.

```python
learn.recorder.plot()
```

<img src="/assets/img/posts/2019-8-20-Image-Classification/learner.jpg">

After fine, tuning, we get 94% of the data classified correctly.

<h2>Interpret</h2>

Finally, we want to see the confusion matrix: which categories get mixed up with which the most.

```python
interp = ClassificationInterpretation.from_learner(learn)
interp.plot_confusion_matrix(figsize=(12,12), dpi=60)
```

<img src="/assets/img/posts/2019-8-20-Image-Classification/confusion-matrix.jpg">

<h2>Conclusion</h2>

Now we can pass in an image to our model and receive the category.

<img src="/assets/img/posts/2019-8-20-Image-Classification/image-cat.jpg">

Finished! Now this card school recognizer can be used in more of my Wizard101 automation projects.
