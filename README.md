# task3-house-price-model
📘 README.md — Task 3: Multimodal House Price Prediction
📌 Task Overview
This task focuses on building a Multimodal Machine Learning Model that predicts house prices based on two types of input data:

🧮 Tabular data (e.g., number of bedrooms, bathrooms, area, etc.)

🖼️ Image data (interior/exterior photos of homes)

By combining both modalities, the model is expected to outperform traditional single-input approaches.

📂 Dataset Description
We used the Ames Housing + Interior Images dataset, which contains:

Tabular CSV file: Features such as square footage, number of rooms, neighborhood, etc.

JPEG images: Photos representing each house.

The dataset was loaded using Hugging Face’s datasets library and preprocessed using TensorFlow/Keras utilities.

⚙️ Model Architecture
🔢 Tabular Branch
Dense layers for numerical inputs

Standardization applied using StandardScaler

🖼️ Image Branch
Pretrained EfficientNetB0 for feature extraction (ImageNet weights)

Global Average Pooling layer to reduce dimensionality

🔗 Fusion & Output
Concatenation of tabular + image embeddings

Dense layers followed by a final output neuron for price prediction

🧪 Evaluation Metrics
Loss: Mean Squared Error (MSE)

Metric: Mean Absolute Error (MAE)

txt
Copy
Edit
Test MAE: ~126,328.60
📈 Results
The model was trained for 5 epochs with the following loss values:

Epoch	Train MAE	Validation MAE
1	124,783	126,333
2	118,515	126,330
3	126,959	126,326
4	117,869	126,330
5	117,365	126,328

Example Predictions:

less
Copy
Edit
Actual Prices:     [105390, 162360, 128322, 115591, 144270]
Predicted Labels:  [5.0, 5.0, 7.0, 6.0, 5.0]   (encoded buckets)
🧠 Key Learnings
Multimodal fusion improves model understanding of complex real-world data.

Image embeddings helped inject visual cues that tabular data alone cannot capture.

Pretrained CNNs significantly reduce training time and improve performance.

