# 📘 RoNeTC: Reliable Open-Set Network Traffic Classification

> This document provides a detailed method summary of the RoNeTC model proposed in the paper:  
> **"Reliable Open-Set Network Traffic Classification"**  
> 📝 *Xueman Wang, Yipeng Wang, et al.*  
> 📚 Published in: *IEEE Transactions on Information Forensics and Security, 2025*

---

## 🚀 Overview

RoNeTC is a deep learning framework designed for **open-set network traffic classification**, which addresses two key challenges:

- Classify traffic **from known classes** accurately
- **Reject unknown traffic types** (e.g., unseen protocols or malicious flows)
- **Quantify prediction uncertainty** to improve decision reliability

---

## 🧠 Model Architecture (Fig. 3)

The overall pipeline consists of **two phases**:

- **Training Phase**
- **Classification Phase**

Each phase contains the following modules:

1. **Flow Preprocessing**
2. **Global-Local Feature Extractor**
3. **Single View Opinion Generator**
4. **Multi-View Opinion Fusion**

---

## 🔁 1. Flow Preprocessing (Fig. 4)

Each network flow is decomposed into three distinct views:

| View Type                | Description                          | Layer         |
|--------------------------|--------------------------------------|---------------|
| IP Header View           | Source IP, TTL, total length         | Network Layer |
| Transport Layer Header   | Port, window size, TCP flags         | Transport     |
| Packet Payload View      | First `N` bytes of packet payload    | Application   |

→ Each view is processed as a 2D tensor: `[num_packets × num_bytes × channels]`

---

## 🧩 2. Global-Local Feature Extractor (Fig. 5)

Each view is passed through a dual-path encoder:

| Path       | Method         | Purpose                                 |
|------------|----------------|-----------------------------------------|
| Local Path | CNN            | Extract per-packet structure            |
| Global Path| Transformer    | Model field evolution across packets    |

→ Local and global features are fused via concatenation + CNN.

---

## 🔐 3. Opinion Generator

Instead of softmax, RoNeTC uses **Dirichlet distribution** to model *second-order probability* and quantify **uncertainty**:

- Evidence vector `e = [e₁, ..., e_K]`
- Dirichlet parameters: `α_k = e_k + 1`
- Outputs:
  - **Belief**: `b_k = e_k / S`
  - **Uncertainty**: `u = K / S`, where `S = Σ (e_k + 1)`

> 📌 More evidence → high belief, low uncertainty  
> 🚫 Low evidence (e.g., for unknown classes) → high uncertainty

---

## ⚖️ 4. Opinion Fusion (Fig. 6)

Uses **Dempster-Shafer theory** to fuse multi-view outputs:

\[
b_k = \frac{1}{1 - C}(b^{(1)}_k b^{(2)}_k + b^{(1)}_k u^{(2)} + b^{(2)}_k u^{(1)}), \quad u = \frac{1}{1 - C} u^{(1)} u^{(2)}
\]

- `C` is the conflict coefficient between views
- Final decision includes:
  - Aggregated belief over classes
  - Combined uncertainty

---

## 🧪 5. Classification Phase (Fig. 7)

In the inference phase:

- Compute final uncertainty `u`
- Use **Youden index** to choose optimal threshold `σ`
- If `u ≥ σ` → classify as **unknown**
- Else → predict class with highest belief

---

## ✅ Key Contributions

| Feature                    | Description                                           |
|----------------------------|-------------------------------------------------------|
| Multi-view Representation | Exploits structural diversity of packet features      |
| Uncertainty Modeling       | Replaces softmax with Dirichlet for reliability       |
| Multi-view Fusion          | Combines beliefs via evidence theory                 |
| Open-set Capability        | Differentiates known vs. unknown traffic dynamically  |

---

## 📎 Citation

```bibtex
@article{wang2025ronetc,
  title={Reliable Open-Set Network Traffic Classification},
  author={Wang, Xueman and Wang, Yipeng and others},
  journal={IEEE Transactions on Information Forensics and Security},
  year={2025}
}
