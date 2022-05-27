# Street-sounds-classification
Feature extraction and classification of sounds collected from city streets.

This project is an example of applying ML to sound classification problems. It involves extracting features from sounds and creating a classifier model. The data comes from the Kaggle database contains 8732 labeled sound excerpts (<=4s) of urban sounds from 10 classes: 
- air_conditioner, 
- car_horn, 
- children_playing, 
- dog_bark,
- drilling,
- enginge_idling, 
- gun_shot, 
- jackhammer, 
- siren,
- street_music.

https://www.kaggle.com/datasets/chrisfilo/urbansound8k

## Chapters:

1. Feature extraction : 

        (Features extraction_Street Sounds Classification.ipynb)
        1.1. Zero crossing rate,
        1.2. Change sign number,
        1.3. Energy,
        1.4. Root-mean-square energy (RMSE),
        1.5. Spectral centroid
        1.6. Spectral roll off
        1.7. Spectral roll off low,
        1.8. Spectral flux,
        1.9. MFCC

2. Machine Learning :

        (ML_Street_Sounds_Classification.ipynb)
        2.1. Data Normalization
        2.2. Decision tree
        2.3. Random Forest Classifier
        2.4. XGBoost
        2.5. K-Means clustering
        2.6. PCA
        2.7. Simple Neural Network
____________________________________________________________________________________________________________


## 1. Feature extraction

After the data was downloaded from the site, it was necessary to proceed with the extraction of the useful features that would be used to teach the prediction models.


An example of a sound signal waveform, in this case the sound of a barking dog:
![image](https://user-images.githubusercontent.com/83005003/170708397-576f606a-f5c1-4456-aec4-0f6e3f73094b.png)
