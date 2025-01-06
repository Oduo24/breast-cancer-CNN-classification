# Transfer Learning Using MobileNetV2 for Classification of Normal (N) and Invasive Carcinoma (I_C) Samples

***Transfer Learning Strategy used***

* **Pre-trained Model**  
  I used MobileNetV2 pre-trained on the ImageNet-1000 dataset. This model has already learned useful features such as edges, textures, and shapes, which can be transferred to our task.  
* **Freezing the Base Model**  
  Initially, I froze the weights of the MobileNetV2 base model which allows it to act as a feature extractor. The features learned from ImageNet were retained and firstly used without modification.  
* **Custom Classification Layer**  
  I added a custom dense layer on top of the MobileNetV2 model to adapt it to the binary classification problem of Normal vs. Invasive Carcinoma.  
* **Data Augmentation**  
  To mitigate the risk of overfitting due to the small size of the dataset (690 images for training), data augmentation techniques were applied. These include random rotations and flips to introduce diversity into the dataset and expose the model to different variations of the images.


***Fine-Tuning Strategy***

After training the model with the base model frozen, fine-tuning was attempted by unfreezing some layers of the base model. Fine-tuning the last few layers allows the model to adapt more specifically to the new dataset, improving accuracy. Freezing the first 100 layers and training the remaining layers can further increase the model’s performance.
