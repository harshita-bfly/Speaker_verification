<h1 align="center">Speaker Verification 🗣</h1>

<h1 align="center">ECAPA-Based Speaker Verification of Virtual Assistants: A Transfer Learning Approach</h1>

<h2>What is speaker verification? 🤔</h2>

 ![image](https://github.com/harshita-bfly/Speaker_verification/assets/100403649/b637365c-7e0a-4a3e-88d0-e0a41d0d792b)
 
Speaker verification is a biometric method to confirm a person's identity based on their unique voice traits. For instance, in secure systems, a user's voiceprint is compared to a preregistered sample for access. It's commonly used in phone-based customer service, voice assistants, and security applications to enhance identity verification.

<h2>Overview of this project 😄</h2>

Speaker verification utilizes speech characteristics to validate the speaker’s identity. It has become increasingly important in security, where it is employed in several applications, including access control, monetary transactions, and safe communication, to authenticate people. This project focuses on verifying the speakers based on their voices. The speakers are the voices of famous virtual assistants:  Siri, Cortana, Google Assistant, and Alexa. Text-to-speech (TTS) technology is often used to create these virtual assistants' voices. As a result, these assistants lack the natural variances in human voices. This project applies transfer learning to the ECAPA-TDNN (SoTA model for speech verification tasks) from the SpeechBrain toolkit, recognizing synthetic sounds and verifying the speakers. Inter and intra-comparisons are done on text-dependent and independent methods, and results are obtained based on evaluation metrics: accuracy, precision, recall, and F1 score.

<h2>Introduction 📖</h2>
 
- Speaker verification utilizes speech characteristics such as pitch, formants, spectral envelope, MFCCs, and prosody characteristics.
- "Voice prints" represent a speaker's unique vocal qualities.
- There are two types of speaker verification methods: text-dependent and text-independent.
- Transfer learning employs pre-trained models to improve performance when labeled data is scarce.
- The ECAPA-TDNN model from the SpeechBrain toolkit is used in this study for transfer learning on virtual assistants.


<h2>Methodology 💻</h2>

<h3>Dataset</h3>

- A custom audio dataset was created with a subset selected for analysis.
- Organized into:
     - Intra-pair Comparisons:
         - Siri Versions (iOS 9 vs iOS 10 vs iOS 11)
         - Alexa Versions (3rd gen vs 4th gen vs 5th gen)
     - Inter-pair Comparisons:
        - Alexa
        - Siri
        - Google Assistant
        - Cortana
      
<h3>Speechbrain</h3>

- SoTA toolkit for speaker verification-related tasks.
- Has pre-trained ECAPA-TDNN model, a state-of-the-art model for speaker recognition that uses TDNN design with MFA mechanism, Squeeze-Excitation (SE), and residual blocks.
- Hyperparameters are detailed in a YAML format.
- Data Loading makes use of a PyTorch dataset interface.
- Batching includes extracting speech features like spectrograms and MFCCs.
- Brain_class() simplifies the neural model training process.

<h3>ECAPA-TDNN model</h3>

- SpeechBrain provides outputs using pre-trained models such as ECAPA-TDNN.
- Data preprocessing: Extract 80-dimensional filterbank features.
- Model initialization: 5 TDNN layers, an attention mechanism, and an MLP classifier.
- Hyperparameter setting: epochs, batch size, learning rate, etc.
- Training: Trained on the VoxCeleb2 dataset.
- Validation and Testing: Evaluate on a validation set.


<h2>Implmentation 💬</h2>

-It can be understood by the following chart👇

![image](https://github.com/harshita-bfly/Speaker_verification/assets/100403649/df4e9ab3-5956-435e-91bf-a87ca5ff15bf)

<h2>Result 👩‍💻</h2>

![image](https://github.com/harshita-bfly/Speaker_verification/assets/100403649/eb13ace2-dc68-4ce6-9228-4fafa763f7c3)

- In brief analysis 🧐
  
    - Intra-pair comparison

         - ![image](https://github.com/harshita-bfly/Speaker_verification/assets/100403649/d30c5fc8-d409-43a2-b363-0f73951403c1)

         - ![image](https://github.com/harshita-bfly/Speaker_verification/assets/100403649/745a3a63-73e7-45de-84c2-978e570171dd)

         - ![image](https://github.com/harshita-bfly/Speaker_verification/assets/100403649/1d216c10-4584-4b50-8367-6ba7111de4be)

         - ![image](https://github.com/harshita-bfly/Speaker_verification/assets/100403649/107f91c8-deb5-4fc5-bc27-891833afd9ab)

    - Inter-pair comparison

        -  ![image](https://github.com/harshita-bfly/Speaker_verification/assets/100403649/ecb208a9-0a0b-4f44-abc5-6d365d96d24f)
        -  
        -  ![image](https://github.com/harshita-bfly/Speaker_verification/assets/100403649/2ae824e7-978f-4736-b95b-9f3ff1659176)
          



<h2>Conclusion 👏</h2>

- Intra-pair TDSV analysis shows similarities among all versions, leading to potential security concerns.
- Inter-pair TDSV analysis found matches between Cortana & Google Assistant and Alexa.
- TISV has higher accuracy than TDSV due to the model's capability to differentiate different texts.
- Additional training on a broader dataset of synthetic voices is recommended for better performance.
- The study emphasizes the potential of transfer learning and SpeechBrain for speaker verification, also acknowledging challenges with synthetic voices.






















