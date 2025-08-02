# 🔁 Deep Learning Workflow for Signature Verification System

---

### 1️⃣ Data Collection & Organization

- Use publicly available datasets: **CEDAR(Testing)**, **GPDS(Training)**.(Completed✅)
- Organize data person-wise and within a person's directories, two sub directories, one for original and one for forged
(Completed✅)

---

### 2️⃣ Preprocessing

- Convert images to grayscale.(Completed✅)
- Resize to fixed dimensions (256x256).(Completed✅)
- Normalize pixel values to [0, 1].(Later⌚)
- Apply data augmentation to simulate real-world noise: (Later⌚)
  - Rotation (±10°) (Later⌚)
  - Gaussian blur (Later⌚)
  - Brightness/contrast adjustment (Later⌚)
  - JPEG compression (Later⌚)

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
