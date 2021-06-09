# VDSR---tf2.0


Tensorflow 2.0 implementation of Accurate Image Super-Resolution Using Very Deep Convolutional Networks (CVPR 2016) with jupyter notebook.



# PSNR

![image](https://user-images.githubusercontent.com/71681194/103330773-3a6a3e80-4aa6-11eb-86e7-73e559810739.png)

While authors evaluate PSNR with luminance channel only, we used entire rgb channels.


## PSNR of bicubic up-sampling

||PSNR(Y)|PSNR(RGB)
|---|---|---|
|B100|29.56|28.24|
|Set5|33.66|31.77|
|Set14|30.24|28.51|
|Urban100|26.88|25.43|


Given same bicubic up-sampling, PSNR of RGB is lower than PSNR of Y channel only.
# Training
Original paper used SGD + momentum=0.9, initial learning rate=0.1 with gradient clipping. I personally found that using Adam without gradient clipping works well. Initial learning rate was set to 0.001. Data augmentation applyed(random flip and rotation).

![learning_curve](https://user-images.githubusercontent.com/71681194/103331500-984c5580-4aa9-11eb-858a-c1e547b5ef67.JPG)









#### Bicubic

![bicubic](https://user-images.githubusercontent.com/71681194/103331637-36d8b680-4aaa-11eb-80e5-47def8da1cf6.png)

#### VDSR

![fake](https://user-images.githubusercontent.com/71681194/103331639-37714d00-4aaa-11eb-89c0-9e4caefb9374.png)



#### Bicubic

![bicubic](https://user-images.githubusercontent.com/71681194/103331644-3b9d6a80-4aaa-11eb-9c54-2d246783e4c0.png)

#### VDSR

![fake](https://user-images.githubusercontent.com/71681194/103331646-3cce9780-4aaa-11eb-88ff-3cc30c9dcc58.png)



#### Bicubic

![bicubic](https://user-images.githubusercontent.com/71681194/103331650-40621e80-4aaa-11eb-8481-1b83f0a6c487.png)

#### VDSR

![fake](https://user-images.githubusercontent.com/71681194/103331653-41934b80-4aaa-11eb-900a-b132f10e636e.png)


