# AJL Team Selenium Equitable AI for Dermatology
---

### **👥 Team Members**

| Name | GitHub Handle | Contribution |
| ----- | ----- | ----- |
| Salma Bhar | @Salma-Bhar-CWRU | Built CNN model and optimizing with Vision Transformer (ViT) model |
| Iman Ikram | @ImanIkram | Built CNN model and optimizing with EfficientNetB3 model |
| Veronica Hangsan | @vhangsan | Built CNN model and optimizing with ResNet50 model |
| Adya Mohanty | @am2558 | Team Lead and Built CNN model |
| Ashley Nguyen | @ashleytln | Built CNN model and optimizing with DenseNet121 model |

---

## **🎯 Project Overview**
This project is part of the Break Through Tech AI Program and our submission to the Algorithmic Justice League (AJL) x Break Through Tech Kaggle Challenge.
- Challenge Name: Inclusive Dermatology AI Challenge
- Kaggle Competition Page: https://www.kaggle.com/competitions/bttai-ajl-2025/overview </br>

AI is transforming healthcare, but dermatology AI tools often underperform for people with darker skin tones due to a lack of diverse training data. This leads to diagnostic errors, delayed treatments, and health disparities for historically marginalized communities. </br>
Our team’s goal is to build an inclusive machine learning model that can accurately classify 21 different skin conditions across diverse skin tones using the datasets provided on Kaggle. The model's performance will be evaluated through key metrics including accuracy, F1, and precision allowing us to gauge the model's ability to handle diverse skin tones.

---

## **📊 Data Exploration**

* Dataset Source: subset of the FitzPatrick17k dataset from Kaggle
* EDA approach: Visualizations (Label and Nine Partition Label Distribution, Scatterplot)
  
During our data exploration analysis stage, we created visualizations to help understand the distribution of the different skin conditions.

![label distribution](eda_images/label_distribution.png)
* Visualization: This count plot shows the distribution of labels across the dataset and identifies the frequency of each class label.
  
![label partition](eda_images/label_partition.png)
* Visualization: This shows the distruibution of labels after partitioning the data into nine categories.
  
![scatterplot](eda_images/scatterplot.png)
* Visualization: This scatter plot provides insights into correlations between the differrent skin conditions.

---

## **🧠 Model Development**

To identify the most effective architecture for this challenge, we experimented with several deep learning models:
- Basic CNN: We implemented a custom convolutional neural network as a baseline. While it was fast and lightweight, its performance plateaued quickly and struggled with generalization, especially on rare classes.
- ResNet50: We tested a ResNet50 pretrained on ImageNet. It improved performance over the baseline CNN, but its deeper architecture took longer to train and showed signs of overfitting on our dataset.
- Vision Transformer (ViT): We explored the transformer-based ViT architecture due to its strong performance on image classification benchmarks. While it handled large-scale data well, it was the most complicated to setup.
- EfficientNetB3 (Chosen Model): Ultimately, we selected EfficientNetB3 as our final model. It provided the best balance of accuracy, generalization, and training efficiency. Its compound scaling strategy allowed us to achieve high performance.

---

## **📈 Results & Key Findings**

We trained an EfficientNet-based image classification model using TensorFlow/Keras. After 40 epochs we got the following results:
- Final Training Accuracy: 95.04%
- Validation Accuracy: 92.66%
- Loss (val/train): 0.2203 / 0.1057
- Test Accuracy: 94%
- Macro Avg F1 Score: 0.96
- Weighted Avg F1 Score: 0.93
- Confusion Matrix:
![image](https://github.com/user-attachments/assets/c22aa943-eb5b-47a0-aa00-b34996f9b7ac)

---

## **🖼️ Impact Narrative**

**AJL Challenge:**

As Dr. Randi mentioned in her challenge overview, “Through poetry, art, and storytelling, you can reach others who might not know enough to understand what’s happening with the machine learning model or data visualizations, but might still be heavily impacted by this kind of work.”

1. What steps did we take to address [model fairness](https://haas.berkeley.edu/wp-content/uploads/What-is-fairness_-EGAL2.pdf)? (e.g., leveraging data augmentation techniques to account for training dataset imbalances; using a validation set to assess model performance across different skin tones)
- Balanced Validation Strategy: We evaluated our model using a stratified validation set to ensure representation across skin tones and conditions. We analyzed performance across all 21 classes, identifying disparities in precision and recall, especially in underrepresented categories (eg: classes 3, 18, 19).
- Model Selection Strategy: We chose EfficientNetB3 not only for accuracy but also for its balanced performance across classes. Our confusion matrix and classification report helped us identify which groups the model struggled with—guiding fairness-focused tuning.

2. What broader impact could our work have?
Skin diseases often go misdiagnosed or undiagnosed for people with darker skin—leading to late treatments and poor health outcomes. Our work contributes to:
- Health Equity: By building a more inclusive AI model, we help ensure all patients regardless of skin tone receive reliable and timely diagnoses.
- Raising Awareness: Through annotated visuals and transparent documentation, we aim to educate others about algorithmic bias in healthcare AI.
- Inspiration for Others: We hope our approach, blending technical rigor with ethical reflection, inspires future projects in AI fairness—especially from emerging women and nonbinary technologists.
---

## **🚀 Next Steps & Future Improvements**

🔧 Limitations of Our Model
- Performance dropped on a few underrepresented classes (e.g., classes 3, 18, 19), showing the need for further data balancing.
- Model sometimes confused visually similar conditions—highlighting the need for more fine-grained visual features or additional context.

⏳ What We’d Do With More Time & Resources
- Collect More Diverse Data: Ideally, we’d expand the training set with additional labeled images from global skin databases covering a broader range of tones and conditions.
- Incorporate Fairness Metrics: We’d integrate tools like Aequitas or Fairlearn to track fairness quantitatively during training.
- Deploy Explainability Tools: Visualize how the model "sees" different skin conditions using Grad-CAM to evaluate bias and improve trust.

🧪 Additional Techniques to Explore
- Few-shot learning for rare condition classes.
- Transfer learning from medical-specific image datasets rather than general-purpose ones like ImageNet.
---

## **📄 Authors**
2025 Team Selenium: Salma Bhar, Veronica Hangsan, Iman Ikram, Adya Mohanty, Ashley Nguyen </br>
Thank you to our Teaching Assistant Abhijay Rane for his support and feedback during this challenge. </br>
This project was developed as part of the Break Through Tech AI Program in response to the AJL x Break Through Tech Kaggle Challenge.

---

