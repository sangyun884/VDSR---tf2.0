# VDSR---tf2.0

Author's site : https://cv.snu.ac.kr/research/VDSR/

Paper review : https://yun905.tistory.com/34

Tensorflow 2.0 implementation of VDSR with jupyter notebook. Dataset is from author's site above.

# Requirements
Numpy, tensorflow(>=2.0), PIL, pyplot

# Benchmark

![image](https://user-images.githubusercontent.com/71681194/103330773-3a6a3e80-4aa6-11eb-86e7-73e559810739.png)

PSNR of given dataset. The reason values are lower than original paper's is because values above are PSNRs of entire RGB channels, but only Y channel in original paper.  It is known that using whole rgb channels generates better results than using Y channel of YCbCr only. 

![image](https://user-images.githubusercontent.com/71681194/103331346-ddbc5300-4aa8-11eb-92fb-afcf14b94fd2.png)

Given same bicubic algorithm, PSNR of RGB is lower than PSNR of Y channel only.
# Training
Original paper used SGD + momentum=0.9, initial learning rate=0.1 with gradient clipping. I personally found that using Adam without gradient clipping works well. Initial learning rate was set to 0.001 with learning rate decay. Training takes less than a hour with RTX 2070 SUPER. Data augmentation applyed(random flip and rotation).

![learning_curve](https://user-images.githubusercontent.com/71681194/103331500-984c5580-4aa9-11eb-858a-c1e547b5ef67.JPG)

# Results



#### Bicubic

![bicubic](https://user-images.githubusercontent.com/71681194/103331545-cf226b80-4aa9-11eb-8254-de57c3a6cc4d.png)

#### VDSR

![fake](https://user-images.githubusercontent.com/71681194/103331546-cfbb0200-4aa9-11eb-8d0a-9af57d0cd9ee.png)



#### Bicubic

![bicubic](https://user-images.githubusercontent.com/71681194/103331606-1c064200-4aaa-11eb-9a48-35d6cf360255.png)

#### VDSR

![fake](https://user-images.githubusercontent.com/71681194/103331607-1d376f00-4aaa-11eb-8a4f-511e374b8155.png)



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


