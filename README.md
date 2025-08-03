# 🔁 Deep Learning Workflow for Signature Verification System

---

### Phase-11️⃣ Data Collection & Organization(Completed✅)

- Use publicly available datasets: **CEDAR(Testing)**, **GPDS(Training)**.(Completed✅)
- Organize data person-wise and within a person's directories, two sub directories, one for original and one for forged
(Completed✅)
- Organize data into pairs: (image_1, image_2, label)(Completed✅)
label = 1: Positive Pair
label = 0: Negative Pair
- Saved Image Pairs To Pickle Files.(Completed✅)

---

### Phase-2️⃣ Preprocessing(Completed✅)

- Converted images to grayscale.(Completed✅)
- Resized to fixed dimensions (256x256).(Completed✅)
- Normalized pixel values to [0, 1].(Completed✅)

---

### 3️⃣ Model Architecture

- Use a **Siamese Network** with shared CNN encoder.
- CNN extracts embeddings from each input image.
- Compute L1 or Euclidean distance between embeddings.
- Final layer: Dense → Sigmoid to output match probability.
- CNN backbone: **MobileNetV2**, **ResNet-18**, or a custom small CNN.

---

### 4️⃣ Training

- Train on image pairs with **Contrastive Loss** or **Binary Cross-Entropy**.
- Optimizer: **Adam** (learning rate ≈ 0.0001).
- Epochs: 20–50.
- Monitor: accuracy, loss, FAR, FRR during training.

---

### 5️⃣ Evaluation

- Evaluate on both clean and noisy test sets.
- Key metrics:
  - **Accuracy**
  - **Precision**, **Recall**
  - **FAR** (False Acceptance Rate)
  - **FRR** (False Rejection Rate)
  - **ROC-AUC Curve**

---

### 6️⃣ Explainability

- Use **Grad-CAM** or **Integrated Gradients** on CNN layers.
- Generate heatmaps to highlight signature regions that influence the decision.
- Return visual explanations with predictions.
