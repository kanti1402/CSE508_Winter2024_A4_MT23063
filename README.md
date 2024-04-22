# CSE508_Winter2024_A4_MT23063

### Description:
This repository contains code for fine-tuning the GPT-2 language model on a custom dataset for summarization tasks and calculating ROUGE scores for generated summaries against actual summaries.

### Instructions:
1. **Setup Environment**:
   - Ensure Python is installed on your system.

2. **Fine-Tune GPT-2**:
   - Adjust hyperparameters such as learning rate, epochs, and batch size as needed.

3. **Generate Summaries**:
   - Use the `generate_summary(review_text)` function to generate summaries for input review texts.
   - Ensure the fine-tuned model directory is correctly specified in the function.

4. **Calculate ROUGE Scores**:
   - The `calculate_rouge(generated_summary, actual_summary)` function calculates ROUGE scores for generated summaries against actual summaries.
   - ROUGE scores are saved to the `rougescore.csv` file.

### Code Explanation:

1. **CustomDataset Class**:
   - Implements a custom PyTorch dataset for processing text data.
   - Tokenizes review and summary texts using the provided tokenizer.
   - Handles padding, truncation, and conversion of text data into model inputs.

2. **Fine-Tuning Loop**:
   - Fine-tunes the GPT-2 model on the custom dataset using the AdamW optimizer with a linear scheduler for learning rate warm-up.
   - Moves model and data to GPU if available.
   - Prints loss for each epoch.

3. **Generate Summary Function**:
   - Utilizes the fine-tuned GPT-2 model to generate summaries for input review texts.
   - Returns the generated summary.

4. **Calculate ROUGE Scores Function**:
   - Calculates ROUGE scores (ROUGE-1, ROUGE-2, ROUGE-L) for generated summaries against actual summaries using the `rouge` library.

5. **Main Script**:
   - Reads input CSV file containing preprocessed text data.
   - Generates summaries for each review text.
   - Calculates ROUGE scores for generated summaries against actual summaries.
   - Writes results to an output CSV file (`rougescore.csv`).
