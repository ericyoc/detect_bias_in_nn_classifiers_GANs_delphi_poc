# Delphi of GANs for Bias Detection in Pre-trained Models
This project implements a Delphi of GANs approach to detect bias in pre-trained language models, specifically BERT and DistilBERT. The technique provides a novel way to assess and compare bias levels in different models across multiple dimensions such as gender, racial, and age bias.
## Motivating Article
Di Zio, S., Calleo, Y., & Bolzan, M. (2023). Delphi-based visual scenarios: an innovative use of generative adversarial networks. Futures, 154, 103280.
## Concept: Delphi of GANs
The Delphi of GANs approach is inspired by the Delphi method, which involves a panel of experts making predictions or assessments. In our case, each GAN serves as an "expert" trained on a specific type of bias data. By using multiple GANs, we can get a more comprehensive and robust assessment of bias in language models.
### Why is this technique useful?
1. **Multi-dimensional Bias Detection**: It allows for simultaneous assessment of multiple types of bias (e.g., gender, racial, age).
2. **Comparative Analysis**: We can compare bias levels between different models (e.g., BERT vs. DistilBert).
3. **Quantitative Metrics**: Provides numerical scores for bias, allowing for objective comparisons.
4. **Adaptability**: The technique can be extended to other types of bias by training new GANs on relevant datasets.
## Research-based Bias Thresholds
We use research-based thresholds to interpret the bias scores:
- Gender Bias: Unbiased ≤ 0.25, Biased ≥ 0.5 (Caliskan et al., 2017)
- Racial Bias: Unbiased ≤ 0.3, Biased ≥ 0.6 (Manzini et al., 2019)
- Age Bias: Unbiased ≤ 0.2, Biased ≥ 0.45 (Díaz et al., 2018)
These thresholds help categorize models as unbiased, moderately biased, or significantly biased.
## Process
1. **Data Preparation**: 
   - Download and preprocess datasets for gender, racial, and age bias.
2. **GAN Creation and Training**:
   - For each bias type:
     - Create a GAN with a generator and discriminator.
     - Train the GAN on the corresponding bias dataset.
3. **Bias Detection**:
   - Load pre-trained models (BERT and DistilBERT).
   - For each model:
     - Generate predictions on test sentences.
     - Use trained GANs to evaluate these predictions.
     - Calculate bias scores based on GAN discriminator outputs.
4. **Interpretation**:
   - Compare bias scores against research-based thresholds.
   - Provide an overall bias assessment and detailed explanations.
## Examples of Low and High Bias Pre-trained Models
### Low Bias: BERT
BERT (Bidirectional Encoder Representations from Transformers) is an example of a relatively low bias pre-trained model. Its Transformer architecture and self-attention mechanisms allow it to capture complex relationships between words, making it more flexible and less biased towards specific patterns. BERT's pre-training on a large and diverse corpus of text data also contributes to its ability to generalize well to various downstream tasks.
### High Bias: DistilBERT
DistilBERT is a distilled version of BERT that aims to reduce the model size while maintaining performance. However, the distillation process may introduce additional biases. DistilBERT has been selected as an example of a relatively high bias model in this project to demonstrate the capability of the Delphi of GANs approach in detecting and quantifying bias in different pre-trained models.
## Usefulness in Assessing Pre-trained Model Classifiers
Understanding bias in pre-trained models is crucial for several reasons:
1. **Ethical AI**: Helps in developing more fair and unbiased AI systems.
2. **Model Selection**: Aids in choosing appropriate models for specific tasks, considering bias implications.
3. **Transparency**: Provides insights into model behavior, crucial for responsible AI deployment.
4. **Improvement Opportunities**: Identifies areas where models can be fine-tuned or debiased.
5. **Regulatory Compliance**: Assists in meeting emerging AI regulations and ethical guidelines.
## Disclaimer
This code is for research and educational purposes only.
