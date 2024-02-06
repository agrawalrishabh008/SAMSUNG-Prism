# SRM_23VI26_Age_gender_and_emotion_detection_from_speech
SRIB-PRISM Program <br>
# Monthly Progress
## Month 1 - 
During the first month of the project, our team analyzed various papers that can identify gender/ age/ emotion from voice data. We identified shortcomings in current approaches by conducting a thorough analysis of the literature in the domains of gender/age identification, emotion detection, and speech processing. We looked at a variety of primary and secondary speech datasets to see which ones would work best for training and testing models. We examined attributes that are critical for success, taking into account gender, age, and emotion-related subtleties in voice signals. We found a large gap in efforts to simultaneously address all three issues using a single, integrated model, as most current studies concentrate on one or two aspects. Prospective voice datasets were found by taking into account attributes including diversity, size, and annotation quality. Pitch, intonation, speech tempo, and spectral patterns are examples of important characteristics that need to be identified in order to accurately recognize age, emotion, and gender.
<br>
## Month 2 -
We carried out a thorough attribute analysis for age, gender, and emotion recognition in the second month of our study project. The following features were extracted: pitch, formant, MFCC, energy, F0 values, chroma, and spectral contrast for age; frequency, amplitude, chroma, MFCC, spectral contrast, and sentiment scores for emotion; and speaking rates, transcripts, energy, formant, MFCCs, chroma, and spectral contrast for gender. Pitch and perceived age showed a high positive correlation, according to correlation analysis, suggesting a relationship with younger age. Every team member extracted features for recognition by doing feature extraction on datasets, concentrating on CREMA and Common Voice. Outliers in emotion-related variables were revealed by dataset analysis and visualisation, especially for CREMA Dataset, suggesting possible abnormalities. Even though the CREMA-d dataset's features were successfully extracted, differences in the classification of several emotion classes were found, requiring a closer look at the annotation procedure.<br>
**Some Visualization Are Shown Below :**

![image](https://media.github.ecodesamsung.com/user/24563/files/f45f5c3b-d8a1-46b5-bedf-8ae7806c0463)
![image](https://media.github.ecodesamsung.com/user/24563/files/5f731c6c-6c35-4886-ad00-c6c0ea7024ac)
<br>
## Month 3 -
Our project made great progress in feature extraction and model development during the third month. We created a curated dataset by gathering audio corpuses from the CREMA-D and Common Voice datasets. To extract 20 MFCC features (MFCC12 and MFCC19 not included) along with the spectral centroid, bandwidth, and rolloff, a robust pipeline was built. The restricted discriminating power of some MFCC traits found in earlier investigations served as the basis for this exclusion. Convolutional neural networks (CNNs) with Conv1D for local pattern recognition, MaxPooling1D for downsampling, Flatten for data transformation, Dense layers for classification, and Concatenate for combining data from age, emotion, and gender aspects comprised the model architecture. Emotion, age, and gender were used as unifying input labels during model training, and StandardScaler was used to guarantee uniform feature scales. During training, the Adam optimizer made convergence more efficient. The model yielded a Test Loss of 3.304, Emotion Accuracy of 53.72%, Age Accuracy of 41.77%, and Gender Accuracy of 48.09% after 10 epochs of training. 
<br>
## Month 4 -
During the fourth month, we developed customised models for each of age, gender, and emotion recognition. An LSTM neural network including characteristics such as MFCCs, Root Mean Square Energy, and Zero Crossing Rate was trained on data from several datasets to recognise emotions. With a batch size of six and 100 training epochs, the model mitigated overfitting through dropout layers, achieving a validation accuracy of 90%. After 30 epochs, the gender prediction model using a compact CNN architecture attained an accuracy of 89.4% on the test set. After 100 epochs, the age prediction model using a CNN architecture was 71.25% accurate in classifying the age groups. With an emphasis on increased accuracy through enhanced architecture and feature selection, each of these distinct models demonstrates an optimised and nuanced approach to each recognition challenge.
<br>
## Month 5 -
Using the Mozilla Common Voice dataset, we experimented in the fifth month to develop a unified model for age and gender recognition, as well as a distinct model for gender and emotion detection. Spectral centroid, bandwidth, rolloff, and MFCCs were among the relevant characteristics and labels that were extracted during preprocessing for age and gender. Support Vector Machine (SVM) and Random Forest classifiers were trained and evaluated using K-Fold Cross-Validation, while feature scaling and the ANOVA statistical approach were utilised for robustness. With an accuracy of 82.7%, the SVM performed better than the Random Forest. The RAVDESS dataset, whose primary voice signal features were retrieved using Wav2Vec2FeatureExtractor, was used to assess gender and emotion. With a noteworthy accuracy of 74.57% on the test dataset, the HubertForSequenceClassification model architecture demonstrated its potential for practical applications demanding in-depth speech analysis. These tests show our continued efforts to use unified and specialised models to optimise recognition tasks.
<br>
## Month 6 -
During the sixth month, we mostly concentrated on conducting thorough research paper exploration, reading pertinent literature to strengthen the project's theoretical underpinnings.

# Steps To Run .sav as well as .h5 Models - <br>
1. Clone the repository- <br>
```
git clone https://github.ecodesamsung.com/SRIB-PRISM/SRM_23VI26_Age_gender_and_emotion_detection_from_speech.git
```
2. Navigate to the project directory- <br>
```
cd SRM_23VI26_Age_gender_and_emotion_detection_from_speech
```
3. Install dependencies-
```
pip install -r requirements.txt
```
4. Download the '.h5' or '.sav' model from the repository.
5. Run the inference script-
```
python inference_script.py --audio_path sample_audio/file.wav --model_path model_name.h5/model_name.sav
``` 
<br>

