
# Model Performance Analysis using TOPSIS Method

## Introduction
This project evaluates the performance of several machine learning models using multiple metrics and applies the TOPSIS (Technique for Order Preference by Similarity to Ideal Solution) method to rank these models based on their performance.

## Dataset
The following models are analyzed:
- `bert-base-uncased`
- `gpt2`
- `distilbert-base-uncased`
- `facebook/bart-large`
- `microsoft/DialoGPT-medium`

Performance metrics used:
1. **Accuracy**
2. **Response Time**
3. **Perplexity**
4. **F1 Score**
5. **Memory Usage**

## Methodology
1. **Data Initialization:**
   - Random sample metrics are generated for demonstration.
   - Data is stored in a CSV file named `model_metrics.csv`.

2. **TOPSIS Analysis:**
   - Data is loaded from `model_metrics.csv`.
   - Each metric is normalized and weighted.
   - Ideal and non-ideal solutions are computed.
   - Distances to the ideal and non-ideal solutions are calculated.
   - TOPSIS scores and ranks are computed and stored in `topsis_results.csv`.

## Metric Weights
The weights assigned to each metric are:
- Accuracy: 0.3
- Response Time: 0.2
- Perplexity: 0.2
- F1 Score: 0.2
- Memory Usage: 0.1

## Results
Final rankings and TOPSIS scores are computed and saved. Visualizations for each metric and the final TOPSIS scores are also generated.

## Files Generated
- `model_metrics.csv`: Dataset containing model performance metrics.
- `topsis_results.csv`: File containing model TOPSIS scores and ranks.
- `Accuracy_chart.png`: Accuracy comparison chart.
- `Response_Time_chart.png`: Response time comparison chart.
- `Perplexity_chart.png`: Perplexity comparison chart.
- `F1_Score_chart.png`: F1 Score comparison chart.
- `Memory_Usage_chart.png`: Memory usage comparison chart.
- `TOPSIS_Score_chart.png`: TOPSIS score comparison chart.

## Visualization Function
The script includes a function `plot_metric_chart(metric_label)` that generates bar charts for each metric and saves them as PNG files.

## Example Usage
To run the analysis and visualize the results:
```python
# Generate charts for individual metrics
for metric in ['Accuracy', 'Response_Time', 'Perplexity', 'F1_Score', 'Memory_Usage']:
    plot_metric_chart(metric)

# Plot TOPSIS scores
plt.figure(figsize=(10, 6))
plt.bar(df['Model'], df['TOPSIS_Score'], color='green')
plt.xlabel('Model')
plt.ylabel('TOPSIS Score')
plt.title('Comparison of TOPSIS Scores for Models')
plt.xticks(rotation=45)
plt.tight_layout()
plt.savefig('TOPSIS_Score_chart.png')
plt.show()
```

## Conclusion
This analysis provides a systematic approach to evaluating and comparing machine learning models using the TOPSIS method, enabling informed decision-making based on multiple performance metrics.

## Requirements
- Python 3.x
- pandas
- numpy
- matplotlib

## Instructions to Run
1. Install the required packages:
   ```bash
   pip install pandas numpy matplotlib
   ```
2. Run the Python script provided to generate rankings and charts.
3. Check the generated CSV and PNG files for results.
