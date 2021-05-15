# mnist_tutorial
A tutorial for MNIST handwritten digit classification using sklearn, PyTorch and Keras.

# Code structure
* [`numpy_matplotlib_sklearn.ipynb`](numpy_matplotlib_sklearn.ipynb): for numpy, matplotlib and sklearn.
* [`pytorch.ipynb`](pytorch.ipynb): for pytorch.
* [`keras.ipynb`](keras.ipynb): for keras.
* Reference solution: (not published yet)
    * [`numpy_matplotlib_sklearn_solution.ipynb`](numpy_matplotlib_sklearn_solution.ipynb)
    * [`pytorch_solution.ipynb`](pytorch_solution.ipynb)
    * [`keras_solution.ipynb`](keras_solution.ipynb)

# Requirements
Code tested on following environments, other version should also work:
* linux system (ubuntu 16.04) 
* python 3.6.3
* numpy 1.13.3
* matplotlib 2.1.0
* sklearn 0.19.1
* pytorch 0.4.1
* keras 2.1.2

# For students from SJTU
Please read [HEAR](EE369.md).



# my Accuracies
* Q1:  
    * Training accuracy: 97.35%  
    * Testing accuracy: 87.40%  
    * (因为要求默认参数，所以报了警告iteraions reached limit)  
* Q2:  
    * Training accuracy: 81.88%  
    * Testing accuracy: 81.70%  
* Q3:  
    * Training accuracy: 97.78%  
    * Testing accuracy: 85.50%  
    * (报了iterations reached limit)  
* Q4:  
    * Training accuracy: 93.63%  
    * Testing accuracy: 89.50%  
    * (更改了参数 C=0.03(默认1), max_iter=106(默认1000))  
* Q5:  
    * Training accuracy: ['98.90%', '84.76%', '84.83%', '84.81%', '84.86%', '84.77%', '84.84%', '84.81%', '84.89%', '84.85%']  
    * Testing accuracy: ['100.00%', '98.44%', '100.00%', '100.00%', '99.22%', '98.44%', '100.00%', '97.66%', '100.00%', '99.22%']  



# Q5使用的深度框架
conv1 - relu - conv2 - relu - maxpooling - (flatten) - fc1 - fc2 - softmax  
optimizer为SGD，损失函数为cross entropy  
  
conv1的输入channel=1，输出channels=32，kernel_size=3，padding=1  
conv2的输入channels=32，输出channels=64，kernel_size=3，padding=1  
maxpooling的kernel_size=2  
fc1的输入channels=9216($64\times12\times12$)，输出channels=64  
fc2的输入channels=64，输出channels=10  



# referrences
* 深度框架参考了https://blog.csdn.net/lzj50002801/article/details/108743100
相较于源代码，没有做dropout，用softmax代替了log_softmax
* 定义simpleNet参考了大作业（对抗攻防）的wide_resnet.py
* 训练和测试参考了大作业（对抗攻防）的normal_train.py和eval_model.py