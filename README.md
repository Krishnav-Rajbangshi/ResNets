# keras-resnet
Residual networks implementation using Keras-1.0 functional API, that works with 
both theano/tensorflow backend.


### Residual blocks
The residual blocks are based on the new improved scheme proposed as shown in figure (b)

![residual_block](https://user-images.githubusercontent.com/79277882/130468040-e10d5051-8071-46c8-9d33-cd943ebe9f63.png)


Both bottleneck and basic residual blocks are supported. To switch them, simply provide the block function 
### Code Walkthrough
The architecture is based on 50 layer sample (snippet from paper)

![architecture](https://user-images.githubusercontent.com/79277882/130468107-a218b5c2-8740-43c7-90ef-4cc74ddb3114.png)


There are two key aspects to note here

 1. conv2_1 has stride of (1, 1) while remaining conv layers has stride (2, 2) at the beginning of the block.
 2. At the end of the first skip connection of a block, there is a disconnect in num_filters, width and height at the merge layer.  
 For remaining cases, input is directly merged with residual block as identity.

