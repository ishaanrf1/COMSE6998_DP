# PROJECT - DIFFERENTIAL PRIVACY FOR DEEP LEARNING ON THE MNIST DIGIT DATASET

---

## SOLUTION ARCHITECTURE



<img src="http://cleverhans.io/assets/pate-full.png">



## PROJECT DESCRIPTION

Differential privacy in Deep learning is the process where the concept of Differential Privacy is applied in Deep Learning models. The application of differential privacy in deep learning ensures that Deep learning models are created which are accurate and at the same time conserves user privacy.  

Differential privacy preserves privacy by introducing distortion or randomness into the data in a dataset(Local differential privacy) or in the output of a query (Global Differential privacy) in order to ensure that the dataset or the output of a query on the dataset are distorted enough to ensure that the output of a query varies slightly from the actual output hence protecting privacy and at the same time being accurate enough to represent the general trend in the dataset for any statistical analysis on the dataset.  

Global Differential privacy in Deep learning involves the use of teacher models trained on unique datasets to evaluate an unlabelled dataset which would be used to train the differentially private model.  


- In this project, Global differential privacy would be used. Global Differential privacy in Deep learning involves the use of teacher models trained on unique datasets to evaluate an unlabelled dataset which would be used to train the differentially private model.
- The labels generated by the teacher models would be evaluated through a mechanism known as PATE analysis which returns a result that indicates the trade-off between privacy and accuracy by the teacher models. The number of teacher models and the training epoch of the teacher models would be varied until a reasonable result is gotten after performing PATE analysis.
- The various labels generated for each data in the unlabelled dataset by the teacher models would then be randomized slightly by applying Laplacian noise ensuring that few data entries in the dataset would be purposely mislabeled to conserve privacy. 
- The now labeled dataset would be used to create and train a model that would be differentially private. 

---

## Results
We vary the variable epsilon to manipulate the impact of randomization on the data and to vary the privacy property of the model. This is the parameter that determine the exponential decay of the laplacian noise that we apply to the outputs of the teacher model. We experiment with multiple values of epsilon and finally settle on epsilon = 0.1. The results for a few values are shown below. 
### Epsilon = 0.3
<img src="https://github.com/ishaanrf1/COMSE6998_DP/blob/main/plots/acc_ep_3e-1.png">
<img src="https://github.com/ishaanrf1/COMSE6998_DP/blob/main/plots/loss_ep_3e-1.png">
### Epsilon = 0.7
<img src="https://github.com/ishaanrf1/COMSE6998_DP/blob/main/plots/accuracy_ep_7e-1.png">
<img src="https://github.com/ishaanrf1/COMSE6998_DP/blob/main/plots/loss_ep_7e-1.png">

### Epsilon = 0.1
<img src="https://github.com/ishaanrf1/COMSE6998_DP/blob/main/plots/accuracy_ep_1e-1.png">
<img src="https://github.com/ishaanrf1/COMSE6998_DP/blob/main/plots/loss_ep_1e-1.png">

As the value of epsilon increases, the model becomes less and less differentially private. However, as the value of epsilon decreases, so does the model performance. 
The value epsilon = 0.1 balances both of these tradeoffs to a reasonable degree. 


## References

1. [Understanding Differential Privacy](https://towardsdatascience.com/understanding-differential-privacy-85ce191e198a)

2. [Martín Abadi, Andy Chu, Ian Goodfellow, H. Brendan McMahan, Ilya Mironov, Kunal Talwar, Li Zhang. (2012). Deep Learning with Differential Privacy](https://arxiv.org/abs/1607.00133)
