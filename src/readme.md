# Translation Evaluation with Metrics

This Python script performs an evaluation of translated sentences using various language quality metrics. It assesses the quality of translations and provides scores based on multiple metrics. The code assumes that you have a reference dataset in a CSV file named "data.csv" containing two columns: a reference sentence and a target sentence for translation. The script uses Python libraries like `pandas`, `matplotlib`, and external metrics libraries such as `nist_score`, `chrf_score`, `wer_score`, `bleu_score`, `meteor_score`, and `gleu_score`.

## Usage

1. Make sure you have the necessary libraries installed. You can install them using `pip`:

   ```
   pip install pandas matplotlib tqdm
   ```

2. Place your reference dataset in a CSV file named "data.csv" in the same directory as the script. Ensure that the CSV file has two columns: one for reference sentences and another for target sentences.

3. Use the `eval_targoman` class to perform the evaluation. Here's an example of how to use it:

   ```python
   from eval_targoman import eval_targoman

   evaluator = eval_targoman(ref_col="ref_sentence", target_col="target_sentence", from_lan="fa", to_lan="en")
   evaluator.save_df()
   evaluator.show_plot()
   ```

   - The `ref_col` parameter is the name of the reference sentence column in your CSV.
   - The `target_col` parameter is the name of the target sentence column in your CSV.
   - The `from_lan` and `to_lan` parameters define the source and target languages for translation.

4. The evaluation process involves the following steps:
   - Reading the CSV file with reference and target sentences.
   - Preprocessing the data, including removing any NaN values.
   - Filtering the dataset to keep sentences with a minimum length.
   - Selecting a subset of sentences (the first 15 in this example).
   - Obtaining translations for the target sentences using the Targoman API.
   - Calculating and normalizing scores for metrics including BLEU, CHRF, WER, METEOR, NIST, and GLEU.
   - Saving the results to a CSV file.
   - Displaying a plot of the scores.

5. The class provides methods to access the results, save them to a CSV file, and display a plot of the scores.

## Disclaimer

This script is intended for translation quality evaluation and relies on external metrics libraries and a Targoman API. Make sure to comply with the terms of service and usage policies of these external services and libraries.
