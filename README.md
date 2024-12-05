# Machine Learning Project
Machine Learning Project A.Y 2023-2024

# Malicious URL Classifiation
Dataset used: https://www.kaggle.com/datasets/naveenbhadouria/malicious/data
Link to the Google Colab notebook: https://colab.research.google.com/drive/1Ibgc_atJnMncGq7BC806vc8tixyqjqr2

## Preprocessing
The dataset is composed of 651,191 URLs, out of which 428,103 benign or safe URLs, 96,457 defacement URLs, 94,111 phishing URLs, and 32,520 malware URLs:
* __Bening__: safe to browse URLs
* __Defacement__: Defacement URLs are generally created by hackers with the intention of breaking into a web server and replacing the hosted website with one of their own, using techniques such as code injection, cross-site scripting, etc. Common targets of defacement URLs are religious websites, government websites, bank websites, and corporate websites.​
* __Phishing__: By creating phishing URLs, hackers try to steal sensitive personal or financial information such as login credentials, credit card numbers, internet banking details, etc.​
* __Malware__: These type of URLs inject malware into the victim’s system once he/she visit such URLs.​

The extracted features are:
* url_length
* n_letters
* n_digits
* n_special_chars
* region: identifies the region of the URL, initially represented by a string, but then represented by an integer number
* https: tells if a URL relies either on HTTPS (1) or HTTP (0) 
* shortened: tells whether the URL has been shortened with a URL shortening service
* abnormal_url
* have_ip
* root_domain

## Classifiers
First the __Stochastic Gradient Descent (SGD)__ and __Random Forest__ classifiers are used, then a Dense Neural Network (DNN) has been built. 
### SGD and RF
The dataset has been split with K-fold (with K=10)
For each classifier, and for each split, there is a training phase (fit the model), a test phase (predict) and the some evaluation metrics have been computed.
### Dense Neural Network
It is compesed of three hidden layers, each of which apply an affine linear transformation to the incoming data.
Then it applies the ReLU (Rectified Linear Unit) function element-wise.
Finally, applies the Softmax function which rescales the input tensor so that the elements of the n-dimensional output Tensor lie in the range [0,1] and sum to 1.


First, the dataset has been split: 20% test, 80% train
While training the network (10 epochs), Cross Entropy Loss has been computed, and the Adam optimizer has been used.
Then the model has been tested, obtaining predictions.
Finally, as in the case of classifiers, some evaluation metrics have been computed.

### Evaluation Metrics
* Average Accuracy
* Average Precision
* Average F1-Score
* Confusion Matrix
