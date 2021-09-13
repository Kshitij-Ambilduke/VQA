# Basic Visual-Question Answering Baseline Implementation
This repository contains the implementation of a basic VQA model which was trained and tested on the Easy-VQA dataset.
The dataset contains images of different shapes in different colours and questions asked are on the similar lines where the colour or shape present in the image is questioned. The answers to these questions is one of the following: 'red', 'black', 'no', 'gray', 'circle', 'rectangle', 'brown', 'teal', 'blue', 'yellow', 'yes', 'triangle', 'green'.<br />
A simple model where the image features and the question features are concatenated and passed through a linear layer to classify answer as one among those mentioned above.
The details about the dataset can be found [here](https://github.com/vzhou842/easy-VQA).
