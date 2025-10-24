# Image-Captioning
Deep Learning-based Image Captioning using Flickr8k Dataset with InceptionV3 and LSTM.
# Image Captioning with Flickr8k Dataset

This project implements an **Image Captioning** system using deep learning. It generates textual descriptions for images using a combination of **InceptionV3** (for image features) and an **LSTM-based sequence model** (for captions).

---

## 📌 Features

- Preprocessing of Flickr8k dataset captions.
- Extraction of image features using **InceptionV3** pretrained on ImageNet.
- Sequence-to-sequence LSTM model for caption generation.
- Beam search for generating more accurate captions.
- Test on **random dataset images** or **user-uploaded images**.
- Model checkpointing to save the best-performing model.

---

## 📂 Dataset

- **Images:** 8,092 images from [Flickr8k Dataset](https://github.com/jbrownlee/Datasets/releases/download/Flickr8k/Flickr8k_Dataset.zip)  
- **Captions:** 40,000 captions corresponding to the images ([Flickr8k_text.zip](https://github.com/jbrownlee/Datasets/releases/download/Flickr8k/Flickr8k_text.zip))  

> The dataset download is automated in the code using `wget`.

---

## 🛠️ Requirements

- Python 3.8+  
- TensorFlow 2.x  
- Numpy  
- Matplotlib  
- Pillow  
- tqdm  

Install requirements:

```bash
pip install tensorflow numpy matplotlib pillow tqdm

⚙️ Usage
1. Training the Model

Run the script to:

1.Download and unzip the dataset.

2.Preprocess captions.

3.Extract image features using InceptionV3.

4.Prepare training sequences.

5.Train the LSTM-based captioning model.

# Train the model
history = model.fit([X1, X2], y, epochs=10, batch_size=64,
                    callbacks=[checkpoint, early_stop])
.The best model is saved as best_caption_model.keras.

2. Generate Captions
a) Random Image from Dataset
test_random_image()

b) Upload Your Own Image
test_uploaded_image()


The model generates captions using beam search for better results.

📈 Model Architecture

Image Feature Extractor: InceptionV3 (2048-dim features)

Text Model:

Embedding layer (256 dims)

LSTM layer (256 units, recurrent dropout=0.3)

Decoder: Dense layers (256 units + vocab_size output)

Optimizer: Adam

Loss: Categorical Crossentropy

📝 Example Output

Random dataset image:

🖼️ Image ID: 12345
📝 Generated Caption: a person in a red and white shirt is running on a track while others watch


Uploaded image:

🖼️ Uploaded Image
📝 Generated Caption: a dog is playing with a ball in the park

🔧 Notes

Beam width in caption generation is configurable (default: 3).

You can adjust the number of images used for training (limit in feature extraction) for faster testing.

Model training may take significant time depending on dataset size and GPU availability.

📚 References

Flickr8k Dataset

Deep Learning for Image Captioning

📌 Author

G Karthik Reddy
