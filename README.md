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
        1.6. Short Time Fourier Transform (STFT)
        1.7. Spectral centroid
        1.8. Spectral roll off
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

A slice of the above sample lasting 2.5 - 3.5 sec. Subsequent transformations in the workbook apply to this section of the sample:
![image](https://user-images.githubusercontent.com/83005003/170720300-f4707842-7df1-49b0-9f7b-7d873fcf0128.png)

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

        1.6. Short Time Fourier Transform (STFT)

STFT shows the change of frequency in consecutive time windows:
![image](https://user-images.githubusercontent.com/83005003/170719267-769b9ad6-ec3a-4a6d-a400-f8b90ac1e6d1.png)

        1.7. Spectral centroid

The spectral centroid is a measure used in digital signal processing to characterise a spectrum. It indicates where the center of mass of the spectrum is located: [https://en.wikipedia.org/wiki/Spectral_centroid]

![image](https://user-images.githubusercontent.com/83005003/170721079-509a58d2-4193-42ea-ae54-d196087749ae.png)

        1.8. Spectral roll off
        
Roll-off is the frequency below which a certain percentage of the total spectral energy lies, such as 85% in the first example and 10% in the next one.

![image](https://user-images.githubusercontent.com/83005003/170725828-3ac8168b-7ac2-478a-8f85-d1dfa025471d.png)

![image](https://user-images.githubusercontent.com/83005003/170726333-8f121c5e-17aa-40fc-8b3a-3fa7b0325aad.png)

        1.9. Spectral flux
        
Spectral flux is a measure of how quickly the power spectrum of a signal is changing, calculated by comparing the power spectrum for one frame against the power spectrum from the previous frame.[https://en.wikipedia.org/wiki/Spectral_flux]

![image](https://user-images.githubusercontent.com/83005003/170726837-b5d00345-0850-4983-84e8-f33e2df5101c.png)

        9. MFCC

Mel Frequency Cepstral Coefficients (MFCC) are parameters widely used in speech acoustics and in the compression of audio signals. They are derived from the cepstrum of a signal represented on a scale of mel scale (mel-cepstrum)
![image](https://user-images.githubusercontent.com/83005003/170727439-754a1f8d-8c08-4a4e-af48-61e714e3880e.png)

_____________________________________________________________________________________________________________________

## 2. Machine Learning

        2.1. Data Normalization
        
        
        
 ## Description in progress...
