# Basic Visual-Question Answering Baseline Implementation
This repository contains the implementation of a basic VQA model which was trained and tested on the Easy-VQA dataset.
The dataset contains images of different shapes in different colours and questions asked are on the similar lines where the colour or shape present in the image is questioned. The answers to these questions is one of the following: 'red', 'black', 'no', 'gray', 'circle', 'rectangle', 'brown', 'teal', 'blue', 'yellow', 'yes', 'triangle', 'green'.<br />
A simple model where the image features and the question features are concatenated and passed through a linear layer to classify answer as one among those mentioned above.
The details about the dataset can be found [here](https://github.com/vzhou842/easy-VQA).<br />
The model architecture used was as follows:
```
Combined(
  (conv1): ConvNet(
    (l1): Sequential(
      (0): Conv2d(3, 10, kernel_size=(5, 5), stride=(1, 1))
      (1): ReLU()
      (2): MaxPool2d(kernel_size=2, stride=2, padding=0, dilation=1, ceil_mode=False)
    )
    (l2): Sequential(
      (0): Conv2d(10, 20, kernel_size=(5, 5), stride=(1, 1))
      (1): ReLU()
      (2): MaxPool2d(kernel_size=2, stride=2, padding=0, dilation=1, ceil_mode=False)
    )
    (l3): Sequential(
      (0): Linear(in_features=3380, out_features=1000, bias=True)
      (1): ReLU()
      (2): Linear(in_features=1000, out_features=512, bias=True)
    )
  )
  (seq): WordEncoding(
    (embed): Embedding(31, 128)
    (seqseq): LSTM(128, 256, batch_first=True)
  )
  (opLayer1): Linear(in_features=1024, out_features=512, bias=True)
  (opLayer2): Linear(in_features=512, out_features=13, bias=True)
)
```
The question embeddings were taken as the last hidden cell of LSTM reccurent neural network and for image embeddings, a convolutional neural network was used followd by a fully connected layer. <br />
The final accuracy achieved on train set was 91.12% and that on test set was 87.60%
