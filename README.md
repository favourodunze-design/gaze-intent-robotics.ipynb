#  Intent2Action

### Learning to **predict intention before action**

A minimal PyTorch implementation of an **intention-conditioned policy**, inspired by recent work in Vision-Language-Action (VLA) models.

This project demonstrates a key idea:

> Instead of predicting actions directly, first predict **intention**, then use it to guide actions.

---

##  Why this matters

Most models do:

> Vision → Action

This project does:

> **Vision → Intention → Action**

That extra step helps the model:

* focus on the right target
* make more consistent decisions
* generalize better to new situations

---

##  Core idea

We break the problem into two parts:

### 1. Intention Prediction

The model predicts a **gaze point (x, y)**
→ where the agent is “looking” or focusing

### 2. Action Prediction

The model then predicts an action **conditioned on that intention**

---

##  Architecture

```text
Image Features + Text
        │
        ▼
  Intention Network
   (predict gaze)
        │
        ▼
   Action Network
 (uses intention)
        │
        ▼
      Action
```

---

##  Training

The model is trained with two objectives:

* **Intention loss** → how accurate the gaze prediction is
* **Action loss** → how accurate the action is

```text
Total Loss = Action Loss + 0.1 × Intention Loss
```

---

##  Project Structure

```text
intent2action/
│
├── notebook.ipynb     # Main implementation
├── README.md
```

---

##  Run the project

```bash
git clone https://github.com/yourusername/intent2action.git
cd intent2action
pip install torch numpy
jupyter notebook notebook.ipynb
```

---

##  What’s included

* Simple synthetic dataset
* Intention prediction (2D coordinates)
* Action prediction (continuous vector)
* End-to-end training loop

---

##  What this shows

This repo is not about performance — it’s about **understanding the idea**:

* Intention can act as a **bridge** between perception and action
* Predicting intention first can improve downstream behavior
* This structure is useful for robotics, agents, and decision systems

---

##  Next steps (if you want to level it up)

* Replace synthetic data with real images
* Add a vision encoder (CNN / ViT)
* Add a language model
* Visualize attention / gaze
* Plug into a robot simulator (PyBullet, ROS)

---

##  Contributing

Open to ideas, improvements, or extensions.

---

##  License

MIT License
