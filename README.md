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
### STM32 Cube IDE <br>
1. Flow chart of the STM cube IDE

2. Setup Project
<br>Firstly, a new project is created in STM32Cube IDE with the target language of C++. The selected board is NUCLEO-F411RE <br>

3. Setup Configuration

### Edge Impulse
1. Flow Chart for setting up the edge impulse 
2. Set up edge impulse 
3. Data Preparation & Data Curation
4. Feature Extraction & Model Training 
5. Model exportation and integration with STM32

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
