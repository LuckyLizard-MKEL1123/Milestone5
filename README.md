# Milestone5

# Introduction
Keyword spotting systems work by enabling a hands-free speech recognition experience through the detection of a trigger phrase that is used to initiate interaction with a device. The inventor can decide which utterances or words will serve as triggers and what to do when they are recognised. This keyword spotting models only search for a few selected words, and this makes it less energy consuming to the device. In this project, we are using two selected words which is “Help” and “Kills” to mimic a danger situation in a room.  

In this project also we were using an STM32 microcontroller as it can support up to 32-bit data which is very suitable to this project. Besides, we are using the Edge Impulse to train our STM32 microcontroller to detect these two specific words. 

# Literature Review
Interconnected devices are gaining popularity as a means of integrating physical information and making them more accessible for further research. The growing number of sensors necessitates massive bandwidth and processing capacity on the cloud. Furthermore, the constant transfer of data to a distant server would jeopardize privacy. Deep Neural Network (DNN) is proving to be extremely successful for cognitive tasks and is simple to install on edge devices. [2].   

For fine-tuning feature weights, the NN-based models use arithmetic-intensive gradient descent calculations. To balance the contradiction between performance and accuracy, the weights must be adjusted using a large number of system-wide parameters known as hyperparameters[3]. Given that these components, as well as their complicated controls, are inherent in the NN paradigm, energy efficiency has remained a challenge[2], [4]. 

The earliest keyword spotting(KWS) classification algorithms introduced in the late 1970s relied on MFCCs for feature extraction since the coefficients generated had a relatively low dimensionality when compared to the raw input data at the time [2]. It was further shown that, when compared to other audio extraction approaches like close prediction coding coefficients (LPCCs) and perceptual linear production (PLP), MFCCs perform much better with increasing background noise and low SNR [2], [5]. 

Later it was proven that Recurrent Neural Networks (RNNs) outperform HMMs but suffer from operational delay as the issue grows, yet RNNs still have quicker run-times than HMM pipelines as they do not need a decoder method. Deep Neural Networks (DNN) was utilized to minimise latency since they consume less memory and operate faster than HMMs[6]. Common DNN optimization strategies like pruning, encoding, and quantization contribute to accuracy decreases in KWS applications[2], [5]. 


# Methodology
## Software
### Edge Impulse
#### Flow Chart for setting up the edge impulse 
Edge Impulse is a machine learning model development and deployment platform for embedded devices such as microcontrollers. It includes an entire workflow for gathering, processing, and analysing sensor data, as well as tools for training and deploying machine learning models at the edge. Figure shows the overall flow for training model on Edge Impulse
<p align="center">
  <img src="https://github.com/LuckyLizard-MKEL1123/Milestone5/blob/main/PICS/5.png">
</p>
1.	On Edge Impulse, a new project was created and "Keyword Spotting" was chosen as the application type. This option add the essential blocks and settings to newly created project for keyword spotting.
2.	In order to record audio data, laptop is chosen as the recording device. A new data acquisition task was created to acquire the training data.
3.	The data acquisition task was set up. The label and duration of each recording is chosen as a start. The data was split into training and testing sets, with a default split of 80/20. Since this project will use 2 keywords, 4 separate labels are used when recording. The mentioned labels are ‘help’, ‘kill’, ‘unknown’ and ‘noise’. Additional label of ‘unknown’ and ‘noise’ were created to further increase the accuracy of trained model.
<p align="center">
  <img src="https://github.com/LuckyLizard-MKEL1123/Milestone5/blob/main/PICS/6.png">
</p>
4.	After each recording, the data saved can be examined and curated to ensure its quality and correctness. Each recording was replayed and if necessary, change its label. Any recordings that are of poor quality or have been mislabelled were erased.
<p align="center">
  <img src="https://github.com/LuckyLizard-MKEL1123/Milestone5/blob/main/PICS/7.png">
</p>
5.	Once data are acquired and curated, the create impulse step is completed and proceed to pre-process the obtained data for training. In case of keyword spotting, the Mel Frequency Cepstral Coefficients (MFCC) algorithm is extracted from the audio samples. MFCC is particularly effective in capturing the spectral characteristics of an audio signal, which is important for distinguishing different sounds. The technique involves several steps[7]:
<br> - Pre-emphasis: This step amplifies the high-frequency components of the audio signal, which improves the signal-to-noise ratio.
<br> - Framing: The audio signal is divided into frames, typically lasting around 20-30 milliseconds each. Overlapping frames are often used to ensure continuity between frames.
<br> - Windowing: A window function, such as a Hamming or Hanning window, is applied to each frame to reduce spectral leakage.
<br> - FFT (Fast Fourier Transform): The FFT is applied to each frame to obtain the frequency spectrum of the signal.
<br> - Mel Filtering: The frequency spectrum is passed through a bank of filters that are spaced according to the Mel scale. This scale is a non-linear scale that better approximates the human auditory system's perception of frequency [8].
<br> - Logarithmic compression: The output from each filter is transformed to a logarithmic scale.
<br> - Discrete Cosine Transform: The DCT is applied to the log-filterbank outputs to obtain the MFCC coefficients.
<p align="center">
  <img src="https://github.com/LuckyLizard-MKEL1123/Milestone5/blob/main/PICS/8.png">
</p>
6.	After MFCCs were extracted, the machine learning model is trained by classifier step. This step will shows the confusion matrix between the audio samples separated by labels. In this step, the accuracy of the trained model is determined which helps in making decision of either to record more data or just proceed based on the model accuracy.
<p align="center">
  <img src="https://github.com/LuckyLizard-MKEL1123/Milestone5/blob/main/PICS/9.png">
</p>
7.	Once high accuracy of model is obtained, the model is deployed by choosing CMSIS-pack as target since the project will be programmed and build using STM32 Cube IDE platform.
<p align="center">
  <img src="https://github.com/LuckyLizard-MKEL1123/Milestone5/blob/main/PICS/10.png">
</p>
### STM32 Cube IDE <br>

## Hardware
### STM32F411RE Board

### INMP441 MEMS

### Buzzer

### LEDs

### Circuit Connection

# Result
<link youtube>

# Conclusion & Recommendation
In short, the project objectives were achieved. However, in future this project can be improved by using high volume data to produce more accurate output. This is because, in this project we only manually train our data up to 4 minutes data only even thought the data accuracy is already 90%. If this train data is up to 1 hour, the accuracy will also be increased up to almost 100%. Next, another project improvement is by using the amplifier in the hardware connection to increase the input data sensitivity. 
# References
[1]     	M. N. Miah and G. Wang, “Keyword Spotting with Deep Neural Network on Edge Devices,” in 2022 IEEE 12th International Conference on Electronics Information and Emergency Communication (ICEIEC), Jul. 2022, pp. 98–102. doi: 10.1109/ICEIEC54567.2022.9835061.
<br> [2]     	J. Lei et al., “Low-power audio keyword spotting using tsetlin machines,” Journal of Low Power Electronics and Applications, vol. 11, no. 2, Jun. 2021, doi: 10.3390/jlpea11020018.
<br> [3]     	S. Yin et al., “A 141 UW, 2.46 PJ/Neuron Binarized Convolutional Neural Network Based Self-Learning Speech Recognition Processor in 28NM CMOS,” in 2018 IEEE Symposium on VLSI Circuits, Jun. 2018, pp. 139–140. doi: 10.1109/VLSIC.2018.8502309.
<br> [4]     	R. Shafik, A. Yakovlev, and S. Das, “Real-Power Computing,” IEEE Transactions on Computers, vol. 67, no. 10, pp. 1445–1461, Oct. 2018, doi: 10.1109/TC.2018.2822697.
<br> [5]     	B. Liu et al., “An Ultra-Low Power Always-On Keyword Spotting Accelerator Using Quantized Convolutional Neural Network and Voltage-Domain Analog Switching Network-Based Approximate Computing,” IEEE Access, vol. 7, pp. 186456–186469, 2019, doi: 10.1109/ACCESS.2019.2960948.
<br> [6]     	G. Chen, C. Parada, and G. Heigold, “Small-footprint keyword spotting using deep neural networks,” in 2014 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP), May 2014, pp. 4087–4091. doi: 10.1109/ICASSP.2014.6854370.
<br> [7]     	Huang, T., Zhang, X., & Li, J. (2018). Keyword Spotting for Speech Recognition Using Convolutional Neural Network. In 2018 IEEE International Conference on Systems, Man, and Cybernetics (SMC) (pp. 1918-1922). IEEE. doi: 10.1109/smc.2018.00328.
<br> [8]     	Palit, A. K., & Pandya, A. (2019). Keyword Spotting using MFCC and Convolutional Neural Network. In 2019 IEEE International Conference on Computational Intelligence and Knowledge Economy (ICCIKE) (pp. 54-58). IEEE. doi: 10.1109/iccike.2019.8883658.
