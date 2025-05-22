# 🧠 Explainable Sentiment Analysis Playground

A Gradio-powered, explainable NLP project that explores how **prompt engineering** and **Integrated Gradients** affect zero-shot sentiment classification using a pre-trained transformer model.

---

## 📌 Abstract

This project investigates how different prompt styles—**Direct**, **Few-Shot**, and **Chain-of-Thought**—influence the performance of a pre-trained sentiment classification model on the IMDB dataset. Beyond simple prediction, the project incorporates **Explainable AI (XAI)** techniques including **attention heatmaps** and **Integrated Gradients** to visualize which tokens influenced the model’s decision. The entire pipeline is hosted on Colab with a lightweight Gradio UI for real-time experimentation. Our results show variation in accuracy across prompt styles and provide interpretable insights into model behavior.

---

## 👥 Authors

- Jayanth (Solo contributor)

---

## 📚 Project Structure

| Component | Description |
|----------|-------------|
| `notebook.ipynb` | Main Colab notebook with UI, evaluation, and XAI |
| `README.md` | Project overview (this file) |
| `Gradio App` | Interactive app built with Gradio inside Colab |
| `examples/` | Example reviews used for testing model response |
| `screenshots/` | Screenshots and visualizations from the app (to be added) |

---

## 🧠 Methods

### 🧾 Prompt Engineering

We compare 3 prompt strategies:

- **Direct**: `"Review:\n{text}\nSentiment?"`
- **Few-Shot**: Includes 3 labeled examples followed by a new review
- **Chain-of-Thought**: `"Let's think step-by-step..."`

These are passed into a Hugging Face pipeline using `nlptown/bert-base-multilingual-uncased-sentiment`.

### 📊 Evaluation

We use a balanced test set of 200 IMDB reviews (100 pos, 100 neg) to evaluate:

- Accuracy of each prompt style
- Probability confidence distribution
- Visual comparison of model predictions

### 🧠 Explainability Tools

| Technique | Purpose |
|----------|---------|
| **Attention Heatmap** | Shows which tokens attend to others (Layer 1, Head 1) |
| **Integrated Gradients** | Measures each token’s contribution to the predicted label |

Captum’s IG method runs over the model’s input embeddings, and outputs token-level attribution spans rendered in HTML.

---

## 🔍 Gradio App Features

| Feature | Description |
|---------|-------------|
| 📥 Text input | Paste any movie review |
| 📂 Prompt style dropdown | Choose Direct, Few-Shot, or Chain-of-Thought |
| 🧾 Label output | Model’s predicted sentiment label |
| 📊 Score plot | Bar chart of model confidence across 1–5 stars |
| 🧭 Attention heatmap | Transformer attention visualization |
| 🔎 IG explanation | Highlights words that influenced the prediction |

![Screenshot](screenshots/app-preview.png)

---

## 🔬 Experiments & Results

- Direct prompts performed best on average (around ~82% accuracy)
- Few-Shot helped on tricky cases but sometimes confused shorter reviews
- Chain-of-Thought was mixed—sometimes helpful, sometimes verbose
- IG showed that tokens like *"predictable"* or *"brilliant"* often dominated predictions

---

## ✅ Deliverables Summary

| Deliverable | Status |
|------------|--------|
| Colab notebook | ✅ Done |
| Prompt style evaluation | ✅ Done |
| Accuracy chart | ✅ Done |
| Attention heatmap | ✅ Done |
| Integrated Gradients | ✅ Done |
| Gradio app | ✅ Done |
| Example prompts | ✅ Done |
| README.md | ✅ Done |
| Video demo | ⏳ To be added |
| Final screenshots | ⏳ To be added |

---

## 🚀 Try It

> ✅ Run the app in Colab:  
> [🔗 Colab Link](https://colab.research.google.com/drive/YOUR_NOTEBOOK_ID_HERE)

---

## 🔮 Future Work

- Try additional prompt types (e.g., role-based or sarcastic prompts)
- Add dynamic scoring dashboard with WandB
- Host the model on Hugging Face Spaces or Streamlit Cloud

---

## 📜 License

MIT License



![image](https://github.com/user-attachments/assets/11d740de-672b-4f85-8d9a-ef1ee118bb85)
