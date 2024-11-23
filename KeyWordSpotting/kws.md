# Key Word Spotting
When we say "Ok Google!", the Google assistant wakes up as it was waiting for these keywords, right?
![image](https://github.com/user-attachments/assets/655b82f2-692d-4722-bd5a-321b3dbfa407)

The same goes for all of the small devices in our home.

## Challenges
1) Latency and bandwidth: We have to make sure that the device responds as early as possible and send less data to the cloud so that, it takes less bandwidth.
2) Accuracy and Personalization: We  need to make sure the result is accurate and the device avoids other noises except us.
3) Security and Privacy: When these devices are sending data to cloud, the data may get stolen. Also, the safety of the data is also a concern.
4) Battery and memory: These devices shouldn't drain much battery as well as there is memory limitations.

## How do companies use TinyML nowadays?
Assuming you are using Alexa, and you recently bought it. The Alexa is listening to you all the time. It looks for keywords. Once it finds them and the model in the device is confident that the keyword "Hey, Alexa" is used, it then sends the rest of the commands like "Play my favorite song" etc to the cloud.
![image](https://github.com/user-attachments/assets/e7c09b1f-50a3-4fe7-b558-dd672bd7e6f5)

## Keyword Spotting Application Architecture
In this reading, we will go over the high-level architecture of the application before we go deep into building the keyword spotting application (KWS).

Machine learning workflow and pipeline. Begins with collection and preprocessing of data then the design and training of a model. These steps are done in TensorFlow. Then a model is optimized, converted and deployed using TensorFlow Lite. Finally inferences are made using TensorFlow Lite Micro.
![image](https://github.com/user-attachments/assets/57bed2e7-97ba-4e3f-84fa-daf9eee57a56)

There are several steps in the ML workflow and this is what each of the stages entails for KWS.

Step 1 Data collection
For Keyword Spotting we need a dataset aligned to individual words that includes thousands of examples which are representative of real world audio (e.g., including background noise).

Step 2: Data Preprocessing
For efficient inference we need to extract features from the audio signal and classify them using a NN. To do this we convert analog audio signals collected from microphones into digital signals that we then convert into spectrograms which you can think of as images of sounds.

Step 3: Model Design
In order to deploy a model onto our microcontroller we need it to be very small. We explore the tradeoffs of such models and just how small they need to be (hint: it’s tiny)!

Step 4: Training
We will train our model using standard training techniques explored in Course 1 and will add new power ways of analyzing your training results, confusion matrices. You will get to train your own keyword spotting model to recognize your choice of words from our dataset. You will get to explore just how accurate (or not accurate) your final model can be!

Step 5: Evaluation
We will then explore what it means to have an accurate model and why your training/validation/test error may be different from the accuracy experienced by users.

Additional Topics:
We will also consider some additional topics that are unique to keyword spotting: post processing and cascade architectures.
