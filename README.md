# Attention-Based Prediction and Visualization
This project utilizes a pre-trained BERT model (bert-base-uncased) to generate masked token predictions and visualize self-attention scores across different layers and heads of the model. The visualization allows insights into the relationships the attention heads learn in natural language.

## Features
* Predicts masked words using a pre-trained BERT model.
* Visualizes attention weights for each layer and attention head.
* Demonstrates linguistic relationships learned by specific attention heads.

## Usage
1. Run the script:
``` 
python mask.py
```
2. Enter a sentence containing the mask token [MASK]. For example:
```
Then I picked up a [MASK] from the table.
```
3. View the predictions generated for the [MASK] token.
4. Attention diagrams will be saved for each layer and attention head in the current directory, labeled as:
```
Attention_Layer{layer_number}_Head{head_number}.png
```

## Attention Analysis

### Example 1: Layer 2, Head 7

* **Observation**: This head often focuses on noun phrases and their determiners. For example, "the" strongly attends to the noun it modifies.
* **Examples**:
    *   Input: ``` The [MASK] cat sat on the mat ```. \
        Prediction: ```lazy``` \
        Visualization: ```The``` attends strongly to ```cat```.
    *   Input: ```A [MASK] dog barked loudly```. \
        Prediction: ```small``` \
        Visualization: ```A``` attends to ```dog```.

### Example 2: Layer 5, Head 6

* **Observation**: This head focuses on subject-verb relationships. Subjects like "he" and "she" attend strongly to their verbs.
* **Examples**:
    *   Input: ``` He [MASK] quickly to the door ```. \
        Prediction: ```ran``` \
        Visualization: ```He``` attends to ```ran```.
    *   Input: ```She [MASK] the keys on the table```. \
        Prediction: ```placed``` \
        Visualization: ```She``` attends to ```placed```.

