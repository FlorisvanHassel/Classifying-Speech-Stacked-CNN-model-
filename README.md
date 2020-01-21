Classifying Speach (Stacked CNN model)

This was an assignment for the course Machine Learning at my university, the assignment was to classifiy spoken words. The data consisted out of 35 classes and the spoken words were provided in the format of MFCC files (+- 100k data). 
We begin our experiment by training an MLP and fine-tune the model and then shifted to a 1D-convolutional as our based model before uploading our first submission. Another experiment was a Conv1D-LSTM based model, while we assume the first convolutional layer functions as a feature extractor for the following LSTM layer. We could see that different model has difficulty predicting classes that are similar, for instance, “three” and “tree” and “forward” and “follow”, so we added a bidirectional wrapper on the LSTM layer, assuming learning features in a reversed order might help the LSTM to learn patterns at the end of sequences better. 
Eventually we made a stacked model that had the final layer of our best evaluated models as input. We selected models based on their performance on a confusion matrix and made adjustments (we needed the models to predict different classes well). And we eventually stacked 18 different models that all performed around 95% on test data.



This type of model stacking increased the accuracy of the model from 95.0% to 96.3%. 

This code scored the second place on the learderboard of the course Machine Learning (0.003% away from first). 
