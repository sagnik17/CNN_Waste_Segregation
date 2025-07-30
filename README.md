### **Report your findings about the data**

1. The dataset contained **7,625 images** classified into **7 classes** ['Cardboard', 'Food_Waste', 'Glass', 'Metal', 'Other', 'Paper', 'Plastic'].
2. There is a **class imbalance**, where the **"Plastic"** class had **more than 2,000 images**, while all other classes had **1,000 or fewer**.
3. All images were of dimensions **256 × 256** pixels.
4. All images resized to 128x128 to improve computational efficiency.
5. Dataset is split into 80% traning and 20% validation 
    - Training dataset size: 6100 images
    - Validation dataset size: 1525 images


### **Report model training results**

**Model Architecture**
- 3 **convolutional layers** with batch normalization, max pooling, and increasing dropout rates (0.2, 0.3, 0.4, 0.5).
- **Input size:** 128x128x3 RGB images.
- **Optimizer:** Adam (learning rate 0.0005).
- **Total parameters:** ~270K.
    - Total params: 269,767
    - Trainable params: 269,319
    - Non-trainable params: 448
- Fully connected output layer with softmax activation for 7 classes.

**Model Training**
- **Early stopping** and **learning rate reduction** callbacks helped prevent overfitting and stabilized training.
- Training and validation accuracy/loss plotted for monitoring.
- Model trained on 6,100 images, validated on 1,525 images.

**Evaluation**
- The CNN model achieved **70% accuracy** in classifying waste materials into seven categories.
- Accuracy and loss reported for both training and validation sets.
- The model performed best on "Cardboard" and "Metal" classes, with f1-scores above 0.74, while "Other" and "Paper" classes had lower scores, indicating room for improvement.
- Class imbalance was observed, with the "Plastic" class dominating the dataset. This affected the recall and precision for minority classes such as "Other" and "Paper".
- Classification report and confusion matrix generated for detailed performance analysis & future improvements.

```
Classification Report:
              precision    recall  f1-score   support

   Cardboard       0.82      0.80      0.81       122
  Food_Waste       0.71      0.75      0.73       209
       Glass       0.65      0.67      0.66       163
       Metal       0.82      0.67      0.74       196
       Other       0.58      0.58      0.58       194
       Paper       0.61      0.63      0.62       195
     Plastic       0.73      0.76      0.75       446

    accuracy                           0.70      1525
   macro avg       0.70      0.69      0.70      1525
weighted avg       0.70      0.70      0.70      1525
```
