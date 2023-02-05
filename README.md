# Milestone5

#Introduction
Keyword spotting systems work by enabling a hands-free speech recognition experience through the detection of a trigger phrase that is used to initiate interaction with a device. The inventor can decide which utterances or words will serve as triggers and what to do when they are recognised. This keyword spotting models only search for a few selected words, and this makes it less energy consuming to the device. In this project, we are using two selected words which is “Help” and “Kills” to mimic a danger situation in a room.  

In this project also we were using an STM32 microcontroller as it can support up to 32-bit data which is very suitable to this project. Besides, we are using the Edge Impulse to train our STM32 microcontroller to detect these two specific words. 

#Literature Review

#Methodology
##Software
###STM32 Cube IDE <br>
1. Flow chart of the STM cube IDE

2. Setup Project
Firstly, a new project is created in STM32Cube IDE with the target language of C++. The selected board is NUCLEO-F411RE <br>

3. Setup Configuration

###Edge Impulse
1. Flow Chart for setting up the edge impulse 
2. Set up edge impulse 
3. Data Preparation & Data Curation
4. Feature Extraction & Model Training 
5. Model exportation and integration with STM32

##Hardware
###STM32F411RE Board

###INMP441 MEMS

###Buzzer

###LEDs

###Circuit Connection

#Result
<link youtube>

#Conclusion & Recommendation
In short, the project objectives were achieved. However, in future this project can be improved by using high volume data to produce more accurate output. This is because, in this project we only manually train our data up to 4 minutes data only even thought the data accuracy is already 90%. If this train data is up to 1 hour, the accuracy will also be increased up to almost 100%. Next, another project improvement is by using the amplifier in the hardware connection to increase the input data sensitivity. 
#References
