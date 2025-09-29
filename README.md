<style>
.comparison-table {
width: 100%;
border-collapse: collapse;
margin: 20px 0;
font-family: 'Inter', sans-serif;
}
.comparison-table th, .comparison-table td {
border: 1px solid #ddd;
padding: 12px;
text-align: center;
}
.comparison-table th {
background-color: #f3f4f6;
color: #1f2937;
font-weight: 600;
position: sticky;
top: 0;
}
.comparison-table tr:nth-child(even) {
background-color: #f9fafb;
}
.comparison-table tr:hover {
background-color: #f1f5f9;
}
.better-result {
background-color: #d1fae5;
font-weight: bold;
color: #065f46;
}
.highlight-header {
background-color: #2563eb !important;
color: white !important;
}
h3 {
font-family: 'Inter', sans-serif;
color: #1f2937;
border-bottom: 2px solid #2563eb;
padding-bottom: 5px;
}
</style>

Stock Price Forecasting using Stacked & Bidirectional LSTMs
This project explores the use of Recurrent Neural Networks (RNNs), specifically Stacked Long Short-Term Memory (LSTM) and Bidirectional LSTM (Bi-LSTM) architectures, for univariate stock price forecasting. The goal was to compare the models' ability to generalize and accurately predict future prices based on historical data.

The models were evaluated using Root Mean Squared Error (RMSE), Mean Absolute Error (MAE), and the Coefficient of Determination (R 
2
  Score) on both training and critical unseen test data.

Model Performance Comparison
The table below summarizes the performance metrics for the two deep learning architectures:

<table class="comparison-table">
<thead>
<tr>
<th class="highlight-header">Model / Metric</th>
<th>RMSE</th>
<th>MAE</th>
<th>R² Score</th>
</tr>
</thead>
<tbody>
<tr>
<td>Stacked LSTM (Train)</td>
<td class="better-result">


3.2522

</td>
<td class="better-result">


2.5308

</td>
<td>


0.9680

</td>
</tr>
<tr>
<td>Stacked LSTM (Test)</td>
<td class="better-result">


4.6305

</td>
<td class="better-result">


3.2944

</td>
<td class="better-result">


0.9094

</td>
</tr>
<tr>
<td>Bi-LSTM (Train)</td>
<td>


3.1669

</td>
<td>


2.5081

</td>
<td class="better-result">


0.9696

</td>
</tr>
<tr>
<td>Bi-LSTM (Test)</td>
<td>


6.4757

</td>
<td>


5.3480

</td>
<td>


0.8229

</td>
</tr>
</tbody>
</table>

Analysis and Conclusion
Based on the evaluation metrics, the Stacked LSTM model is the clear choice for this specific prediction task, demonstrating superior generalization capability on unseen test data.

Stacked LSTM is the Better Model for Testing: The Stacked LSTM significantly outperformed the Bi-LSTM on the critical Testing Set across all metrics.

RMSE (4.6305 vs. 6.4757): The Stacked LSTM has a much lower RMSE, meaning its predictions are closer to the actual values and it made fewer large errors.

MAE (3.2944 vs. 5.3480): The average absolute error is lower for the Stacked LSTM, indicating that on a daily basis, its predictions are closer to the true price.

R 
2
  Score (0.9094 vs. 0.8229): The Stacked LSTM explains approximately 9% more of the price variance on the unseen test data than the Bi-LSTM (90.94% vs. 82.29%).

Overfitting/Setup Issue in Bi-LSTM:

Both models performed extremely well on the Training Set (high R 
2
 ), with the Bi-LSTM showing slightly less training error (lower RMSE/MAE).

However, the Bi-LSTM's performance dropped sharply on the Testing Set. This suggests the Bi-LSTM model, despite its theoretical advantage of processing data bidirectionally, is overfitting to the training data. It learned the noise and specific patterns of the training data too well, leading to poor generalization.

Recommendation: The Stacked LSTM architecture is recommended for deployment given its robust performance on the independent test data. If you wished to continue with the Bi-LSTM, further regularization techniques (like more dropout or early stopping) would be necessary to prevent overfitting.
