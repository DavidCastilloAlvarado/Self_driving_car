## Model based on Nvidia paper "End to End for Self Driving Cars"
We adding the dropoud layer with factor 0.25, for the first five
convolutional layer and for the first full connected layer. 

## Training Process
The training process was run into a virtual machine in Google Cloud Platform
using 16GB of RAM, 8 CPU and 1 Nvidia Tesla V100.

## CallBacks
We programed callback for tensorboard and Backup trained model every 50 epochs 

## The numpy files
We got this numpy file using the data_preprocesing_train and data_preprocesing_test notebook. 

Layer (type)                 Output Shape              Param #   
=================================================================
lambda_1 (Lambda)            (None, 66, 200, 3)        0         
_________________________________________________________________
conv2d_1 (Conv2D)            (None, 31, 98, 24)        1824      
_________________________________________________________________
dropout_1 (Dropout)          (None, 31, 98, 24)        0         
_________________________________________________________________
conv2d_2 (Conv2D)            (None, 14, 47, 36)        21636     
_________________________________________________________________
dropout_2 (Dropout)          (None, 14, 47, 36)        0         
_________________________________________________________________
conv2d_3 (Conv2D)            (None, 5, 22, 48)         43248     
_________________________________________________________________
dropout_3 (Dropout)          (None, 5, 22, 48)         0         
_________________________________________________________________
conv2d_4 (Conv2D)            (None, 3, 20, 64)         27712     
_________________________________________________________________
dropout_4 (Dropout)          (None, 3, 20, 64)         0         
_________________________________________________________________
conv2d_5 (Conv2D)            (None, 1, 18, 64)         36928     
_________________________________________________________________
dropout_5 (Dropout)          (None, 1, 18, 64)         0         
_________________________________________________________________
flatten_1 (Flatten)          (None, 1152)              0         
_________________________________________________________________
dense_1 (Dense)              (None, 1164)              1342092   
_________________________________________________________________
dropout_6 (Dropout)          (None, 1164)              0         
_________________________________________________________________
dense_2 (Dense)              (None, 100)               116500    
_________________________________________________________________
dense_3 (Dense)              (None, 50)                5050      
_________________________________________________________________
dense_4 (Dense)              (None, 10)                510       
_________________________________________________________________
dense_5 (Dense)              (None, 1)                 11        
=================================================================
Total params: 1,595,511
Trainable params: 1,595,511
Non-trainable params: 0
