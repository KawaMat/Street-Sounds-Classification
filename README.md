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
        1.5. Fast Fourier Transform
        1.6. Spectral centroid
        1.7. Spectral roll off
        1.78. Spectral roll off low,
        1.9. Spectral flux,
        1.10. MFCC

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


        1.1. Zero crossing rate
        
The zero-crossing rate (ZCR) is the rate at which a signal changes from positive to zero to negative or from negative to zero to positive.

Zero crossing rate values for all frames:
![image](https://user-images.githubusercontent.com/83005003/170715547-15a35432-9538-4559-a61a-b57f4256a6cf.png)

        1.2. Change sign number
        
A value that tells how many times the signal has passed through the 0 value during the entire sample. In the case of this sample it is 1038 times


        1.3. Energy
 
 ![image](https://user-images.githubusercontent.com/83005003/170716416-11662d6c-0992-4124-b99a-dc392a56f542.png)

  
        1.4. Root-mean-square energy (RMSE)
  
  
The energy  of a signal corresponds to the total magntiude of the signal. For audio signals, that roughly corresponds to how loud the signal is. The root-mean-square energy (RMSE) in a signal is defined as: [Wikipedia; FMP, p. 66]
![image](https://user-images.githubusercontent.com/83005003/170716985-129ab50b-ef5f-4d41-b6d8-a4e7a331429e.png)
In the case of the above sample, the value was: 0.18630503305459203
  
        1.5. Fast Fourier Transform
        
An FFT must be performed to determine subsequent features:        
![image](https://user-images.githubusercontent.com/83005003/170717529-16501f3c-79b1-4d1e-8542-c9304d963f9d.png)


According to Nyquist's law, in a graph in the frequency domain, values above half the sampling frequency merely mirror the waveform in the first half of the graph, so it will be truncated and stretched (just to illustrate roughly):
![image](https://user-images.githubusercontent.com/83005003/170718583-9b4a4ba1-b785-4121-9e24-62c2150a311a.png)

