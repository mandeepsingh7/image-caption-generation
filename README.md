# Image Caption Generation

This project focuses on generating captions for images using a combination of a pre-trained EfficientNetV2M model for image encoding and an LSTM-based decoder for generating captions.

## Overview

- **Data Augmentation**: Applied to images before sending them to the encoder.
- **Vocabulary Building**: Built using training captions with a specified vocabulary size and frequency threshold.
- **Image Encoding**: Used a pre-trained EfficientNetV2M model to encode images.
- **Caption Generation**: Used LSTM decoder, trained with encoded images and corresponding captions.

## Dataset

- **Dataset Used**: Flickr8k
- **Vocabulary Size**: 20,000
- **Threshold Frequency**: 5
- **Batch Size**: 16

## Project Structure

- **cnn_lstm.ipynb**: Contains the code for creating the vocabulary and the Encoder-Decoder architecture.
- **kaggle_dl.ipynb**: We use Kaggle's GPU resources to train the model. This notebook shows the training process using Kaggle's platform and displays generated captions for random images after 10, 20, 30, and 40 epochs.

## Methodology

1. **Data Augmentation**:
   - Performed on images to improve the robustness of the model.

2. **Vocabulary Creation**:
   - Built a vocabulary class to numericalize and denumericalize captions.
   - Only included words that appeared at least 5 times in the training captions.

3. **Image Encoding**:
   - Used EfficientNetV2M as the encoder.
   - Extracted feature vectors from the images.

4. **Caption Generation**:
   - Used LSTM to decode the encoded image features along with the numericalized captions.
   - During inference, the embedded image feature vector is fed into the LSTM.
   - The output from the LSTM is recursively used as input to the next LSTM cell to generate captions sequentially.

## Training

- **Training Process**:
  - Encoded images and numericalized captions are used as inputs to the LSTM decoder.
  - The model is trained to generate captions word-by-word.

- **Evaluation**:
  - In the `kaggle_dl.ipynb` file, captions generated for random images are displayed after 10, 20, 30, and 40 epochs to show the progression of the model's learning.


## Conclusion

This project demonstrates the process of image caption generation using a combination of CNN (EfficientNetV2M) for image encoding and LSTM for caption generation. The generated captions improve as the training progresses, highlighting the effectiveness of the Encoder-Decoder architecture for this task.

