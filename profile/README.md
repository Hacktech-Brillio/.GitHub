📝 **Project Documentation:** Brillio Fake Review Detection System

**GitHub Links** 📂:

- 📱 **iOS**: [AR-iOS-APP](https://github.com/Hacktech-Brillio/AR-iOS-APP)
- 🌐 **Chrome Extension**: [Chrome-Plugin](https://github.com/Hacktech-Brillio/Chrome-Plugin)
- 🤖 **PyTorch Model**: [AI-Python](https://github.com/Hacktech-Brillio/AI-Python)

---

### 📖 **Project Overview**

Our project focuses on creating a robust and versatile fake review detection system powered by an AI model. The solution spans multiple platforms 🌍 and integrates different technologies, including a machine learning model designed to detect fake reviews, an iOS app built to scan barcodes and authenticate product reviews 📱, and a Chrome extension to provide on-device fake review detection 🌐.

---

### 🧠 **1. AI Model Development**

We began by designing and training an AI model specifically built to identify fake product reviews. This model uses an LSTM neural network 🧬, which is ideal for processing text-based data. Here’s a breakdown:

- 📊 **Data Collection**: We collected a labeled dataset, categorizing each review as "OR" (legitimate) or "CG" (fake). This dataset, stored in a CSV file, provided the foundation for model training.
- 🛠️ **Preprocessing**: Using NLTK for text preprocessing, we tokenized, removed stop words, and vectorized text to ensure optimal training.
- 🔗 **Model Architecture**: The PyTorch-based LSTM model has an embedding layer, bidirectional LSTM layers, and fully connected layers for advanced contextual understanding of reviews.
- 📈 **Training and Evaluation**: Through iterative training, we fine-tuned the model’s performance, achieving over 90% accuracy in detecting fake reviews. ⚙️

**Challenges**:
  - 📝 Dealing with batch sizes larger than 1 during ONNX export generated warnings. We optimized the model export to be compatible with a batch size of 1.

---

### 🔄 **2. Model Transformation to Core ML**

To integrate the AI model into an iOS environment, we converted it to Core ML format, allowing on-device inference within Apple’s ecosystem 🍏.

- 🔄 **Conversion Process**: We used `torchvision` and `coremltools` to transform the model, adding configuration for probability-based outputs and class labels.
- 🚀 **Performance Optimization**: The conversion to Core ML ensured low latency and quick responses, ideal for mobile devices.

**Challenges**:
  - ⚠️ Core ML compatibility with LSTM layers required adjustments in input handling and metadata to ensure smooth functioning.

---

### 📲 **3. Barcode Review Authenticator iOS App**

For a real-world application, we developed an iOS app that lets users scan barcodes 📱 and verify review authenticity.

- 📐 **Architecture**: SwiftUI delivers a responsive interface, and AVFoundation powers the barcode scanning feature.
- 🤖 **Core ML Integration**: The Core ML model analyzes reviews fetched from a database, providing real-time feedback.
- 🖥️ **User Experience**: Color-coded indicators display review authenticity for quick user assessment.

**Challenges**:
  - Ensuring smooth Core ML processing for real-time feedback without impacting performance was essential.

---

### 🌐 **4. Chrome Extension for Fake Review Detection**

We also developed a Chrome extension 🌐 that allows users to identify fake reviews directly from their browser.

- ⚙️ **ONNX Model Deployment**: To maintain cross-platform compatibility, we used an ONNX model that runs entirely on-device for user privacy.
- 🌐 **Extension Workflow**: The extension analyzes reviews as users browse, offering real-time insights.
- 🖱️ **User Interaction**: Visual feedback provides clear indicators of review authenticity.

**Challenges**:
  - Ensuring lightweight model performance within the Chrome environment required optimizations, especially compared to Core ML’s mobile framework.

---

### 🚧 **Overall Challenges and Solutions**

Throughout development, we encountered several key challenges:

- 🖥️ **Model Compatibility Across Platforms**: Adapting the model for Core ML and ONNX required testing to ensure seamless performance.
- 🕒 **Performance Optimization**: Real-time feedback, especially on mobile and in-browser, demanded model size reductions and hyperparameter fine-tuning.
- 🔒 **User Privacy**: To protect privacy, both the iOS app and Chrome extension function entirely offline.

---

### 🎉 **Conclusion**

This project showcases an effective AI solution that enhances decision-making through review authenticity insights. With iOS and web integration, our system is versatile, privacy-focused, and user-friendly. Overcoming various technical challenges strengthened our skills in machine learning, cross-platform model deployment, and user-centered development 🚀.

---
