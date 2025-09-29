<h1>Stock-Prediction-Forecasting 📈</h1>

<p>
<img src="https://img.shields.io/badge/Deep%20Learning-LSTM-blue" alt="LSTM Badge" />
<img src="https://img.shields.io/badge/Python-green" alt="Python Badge" />
</p>

<h2>Overview</h2>
<p>
<strong>Stock-Prediction-Forecasting</strong> is a deep learning project aimed at predicting future stock prices using 
<b>Recurrent Neural Networks (RNNs)</b>, specifically <b>Stacked Long Short-Term Memory (LSTM)</b> and 
<b>Bidirectional LSTM (Bi-LSTM)</b> architectures. The project explores the effectiveness of these architectures for 
univariate time series forecasting, comparing their performance on training and unseen test data.
</p>
<p>
By leveraging historical stock price data, this project provides insights into which model generalizes better and produces 
more accurate predictions, making it a practical tool for financial analysis and algorithmic trading simulations.
</p>

<h2>Features</h2>
<ul>
  <li>Forecast future stock prices using LSTM-based architectures.</li>
  <li>Compare <strong>Stacked LSTM</strong> and <strong>Bidirectional LSTM (Bi-LSTM)</strong> performance.</li>
  <li>Evaluate models using:
    <ul>
      <li>RMSE (Root Mean Squared Error)</li>
      <li>MAE (Mean Absolute Error)</li>
      <li>R² Score (Coefficient of Determination)</li>
    </ul>
  </li>
  <li>Identify overfitting and generalization issues.</li>
  <li>Fully reproducible workflow in Python using popular libraries like TensorFlow/Keras, Pandas, and NumPy.</li>
</ul>

<h2>Model Performance</h2>

<table style="width:100%; border-collapse: collapse; text-align:center;">
  <thead>
    <tr style="background-color:#2563eb; color:white;">
      <th>Model / Metric</th>
      <th>RMSE</th>
      <th>MAE</th>
      <th>R² Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Stacked LSTM (Train)</strong></td>
      <td style="background-color:#d1fae5; font-weight:bold; color:#065f46;">3.2522</td>
      <td style="background-color:#d1fae5; font-weight:bold; color:#065f46;">2.5308</td>
      <td>0.9680</td>
    </tr>
    <tr>
      <td><strong>Stacked LSTM (Test)</strong></td>
      <td style="background-color:#d1fae5; font-weight:bold; color:#065f46;">4.6305</td>
      <td style="background-color:#d1fae5; font-weight:bold; color:#065f46;">3.2944</td>
      <td style="background-color:#d1fae5; font-weight:bold; color:#065f46;">0.9094</td>
    </tr>
    <tr>
      <td>Bi-LSTM (Train)</td>
      <td>3.1669</td>
      <td>2.5081</td>
      <td style="background-color:#d1fae5; font-weight:bold; color:#065f46;">0.9696</td>
    </tr>
    <tr>
      <td>Bi-LSTM (Test)</td>
      <td>6.4757</td>
      <td>5.3480</td>
      <td>0.8229</td>
    </tr>
  </tbody>
</table>

<h2>Key Observations</h2>
<ul>
  <li><strong>Stacked LSTM outperforms Bi-LSTM on unseen test data</strong>, demonstrating superior generalization.</li>
  <li><strong>RMSE & MAE:</strong> Lower errors indicate predictions are closer to actual prices.</li>
  <li><strong>R² Score:</strong> Stacked LSTM explains ~91% of price variance vs. ~82% for Bi-LSTM.</li>
  <li><strong>Bi-LSTM Overfitting:</strong> Excellent performance on training data but poor generalization on test data suggests overfitting. Regularization techniques like dropout or early stopping could improve Bi-LSTM performance.</li>
</ul>

<h2>Recommendation</h2>
<p>
Deploy <strong>Stacked LSTM</strong> for production, as it shows better generalization on unseen data. Bi-LSTM may require additional regularization or hyperparameter tuning to prevent overfitting.
</p>

<h2>Technologies Used</h2>
<ul>
  <li>Python</li>
  <li>TensorFlow / Keras</li>
  <li>Pandas, NumPy</li>
  <li>Matplotlib / Seaborn</li>
  <li>Jupyter Notebook</li>
</ul>
