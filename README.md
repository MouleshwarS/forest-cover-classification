# Forest Cover Classification
Implemented some popular classification algorithms to predict the type of forest cover. (Extensive improvements were carried out later)

## Dataset Description
The dataset contains data from `4` areas of the Roosevelt National Forest in Colorado. It includes information on tree type, shadow coverage, distance to nearby landmarks (roads etc.), soil type, and local topography for `7` different types of forest cover.
* Title: Forest Cover Type Dataset
* URL: https://www.kaggle.com/datasets/uciml/forest-cover-type-dataset

<table>
  <thead>
    <tr>
      <th align="center" colspan="2">Generic Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center">Number of samples</td>
      <td align="center"><code>5,81,012</code></td>
    </tr>
    <tr>
      <td align="center">Number of attributes</td>
      <td align="center"><code>55</code></td>
    </tr>
    <tr>
      <td align="center">Input features</td>
      <td align="center"><code>54</code></td>
    </tr>
    <tr>
      <td align="center">Target variable</td>
      <td align="center">Cover_Type (<code>1</code> to <code>7</code>)</td>
    </tr>
  </tbody>
</table>

The dataset was split into a training set and a test set, with `75%` being used for training and `25%` being used for testing. Before being used, the data in both subsets was normalized using StandardScaler. Additionally, for the neural network model, the training set was further split into training and validation subsets, with `75%` being used for training and `25%` being used for validation.

For all the models except the K Nearest Neighbour Classifier and the neural network, the optimal hyperparameters were found using halving grid search with `5`-fold cross validation.

Finally, confusion matrices and bar graphs were plotted to visualize the results for each model.

## K Nearest Neighbours (KNN Classifier)
For the KNN classifier, the accuracy rates were computed for different values of K for the training as well as test datasets.
* Best Value of K (= `1`)
  <table>
  <thead>
    <tr>
      <th align="center"></th>
      <th align="center">Accuracy (in %)</th>
      <th align="center">Precision (in %)</th>
      <th align="center">Recall (in %)</th>
      <th align="center">F1 Score (in %)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center"><code>100.000</code></td>
      <td align="center"><code>100.000</code></td>
      <td align="center"><code>100.000</code></td>
      <td align="center"><code>100.000</code></td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center"><code>93.446</code></td>
      <td align="center"><code>93.469</code></td>
      <td align="center"><code>93.466</code></td>
      <td align="center"><code>93.467</code></td>
    </tr>
  </tbody>
  </table>

* Other Values of K
  <table>
  <thead>
    <tr>
      <th align="center">Value of K</th>
      <th align="center"></th>
      <th align="center">Accuracy (in %)</th>
      <th align="center">Precision (in %)</th>
      <th align="center">Recall (in %)</th>
      <th align="center">F1 Score (in %)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center" rowspan="2"><strong><code>3</code></strong></td>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center"><code>96.811</code></td>
      <td align="center"><code>96.807</code></td>
      <td align="center"><code>96.811</code></td>
      <td align="center"><code>96.807</code></td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center"><code>93.151</code></td>
      <td align="center"><code>93.134</code></td>
      <td align="center"><code>93.151</code></td>
      <td align="center"><code>93.139</code></td>
    </tr>
    <tr>
      <td align="center" colspan="6"></td>
    </tr>
    <tr>
      <td align="center" rowspan="2"><strong><code>5</code></strong></td>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center"><code>95.475</code></td>
      <td align="center"><code>95.466</code></td>
      <td align="center"><code>95.475</code></td>
      <td align="center"><code>95.467</code></td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center"><code>92.723</code></td>
      <td align="center"><code>92.702</code></td>
      <td align="center"><code>92.723</code></td>
      <td align="center"><code>92.705</code></td>
    </tr>
    <tr>
      <td align="center" colspan="6"></td>
    </tr>
    <tr>
      <td align="center" rowspan="2"><strong><code>10</code></strong></td>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center"><code>93.418</code></td>
      <td align="center"><code>93.398</code></td>
      <td align="center"><code>93.418</code></td>
      <td align="center"><code>93.387</code></td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center"><code>91.605</code></td>
      <td align="center"><code>91.569</code></td>
      <td align="center"><code>91.605</code></td>
      <td align="center"><code>91.566</code></td>
    </tr>
  </tbody>
  </table>

## Decision Tree Classifier
  <table>
  <thead>
    <tr>
      <th align="center"></th>
      <th align="center">Accuracy (in %)</th>
      <th align="center">Precision (in %)</th>
      <th align="center">Recall (in %)</th>
      <th align="center">F1 Score (in %)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center"><code>100.000</code></td>
      <td align="center"><code>100.000</code></td>
      <td align="center"><code>100.000</code></td>
      <td align="center"><code>100.000</code></td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center"><code>94.303</code></td>
      <td align="center"><code>94.302</code></td>
      <td align="center"><code>94.303</code></td>
      <td align="center"><code>94.302</code></td>
    </tr>
  </tbody>
  </table>

## Random Forest Classifier
  <table>
  <thead>
    <tr>
      <th align="center"></th>
      <th align="center">Accuracy (in %)</th>
      <th align="center">Precision (in %)</th>
      <th align="center">Recall (in %)</th>
      <th align="center">F1 Score (in %)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center"><code>100.000</code></td>
      <td align="center"><code>100.000</code></td>
      <td align="center"><code>100.000</code></td>
      <td align="center"><code>100.000</code></td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center"><code>95.691</code></td>
      <td align="center"><code>95.701</code></td>
      <td align="center"><code>95.691</code></td>
      <td align="center"><code>95.672</code></td>
    </tr>
  </tbody>
  </table>

## Gaussian Naive Bayes Classifier
  <table>
  <thead>
    <tr>
      <th align="center"></th>
      <th align="center">Accuracy (in %)</th>
      <th align="center">Precision (in %)</th>
      <th align="center">Recall (in %)</th>
      <th align="center">F1 Score (in %)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center"><code>46.011</code></td>
      <td align="center"><code>66.014</code></td>
      <td align="center"><code>46.011</code></td>
      <td align="center"><code>38.916</code></td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center"><code>45.765</code></td>
      <td align="center"><code>65.648</code></td>
      <td align="center"><code>45.765</code></td>
      <td align="center"><code>38.583</code></td>
    </tr>
  </tbody>
  </table>

## Linear SVC (Support Vector Classifier)
  <table>
  <thead>
    <tr>
      <th align="center"></th>
      <th align="center">Accuracy (in %)</th>
      <th align="center">Precision (in %)</th>
      <th align="center">Recall (in %)</th>
      <th align="center">F1 Score (in %)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center"><code>71.269</code></td>
      <td align="center"><code>70.407</code></td>
      <td align="center"><code>71.269</code></td>
      <td align="center"><code>69.673</code></td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center"><code>71.276</code></td>
      <td align="center"><code>70.299</code></td>
      <td align="center"><code>71.276</code></td>
      <td align="center"><code>69.688</code></td>
    </tr>
  </tbody>
  </table>

## Logistic Regression
  <table>
  <thead>
    <tr>
      <th align="center"></th>
      <th align="center">Accuracy (in %)</th>
      <th align="center">Precision (in %)</th>
      <th align="center">Recall (in %)</th>
      <th align="center">F1 Score (in %)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center"><code>72.448</code></td>
      <td align="center"><code>71.295</code></td>
      <td align="center"><code>72.448</code></td>
      <td align="center"><code>71.484</code></td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center"><code>72.507</code></td>
      <td align="center"><code>71.152</code></td>
      <td align="center"><code>72.507</code></td>
      <td align="center"><code>71.552</code></td>
    </tr>
  </tbody>
  </table>

## SGD (Stochastic Gradient Descent) Classifier
  <table>
  <thead>
    <tr>
      <th align="center"></th>
      <th align="center">Accuracy (in %)</th>
      <th align="center">Precision (in %)</th>
      <th align="center">Recall (in %)</th>
      <th align="center">F1 Score (in %)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center"><code>71.412</code></td>
      <td align="center"><code>69.955</code></td>
      <td align="center"><code>71.412</code></td>
      <td align="center"><code>69.913</code></td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center"><code>71.364</code></td>
      <td align="center"><code>70.015</code></td>
      <td align="center"><code>71.364</code></td>
      <td align="center"><code>69.879</code></td>
    </tr>
  </tbody>
  </table>

## Neural Network
A neural network with `5` hidden layers was implemented using different activation functions. Before using the class labels as the target variable, they were zero-indexed -> `1` to `7` were converted to `0` to `6`.
  <table>
  <thead>
    <tr>
      <th align="center">Activation Function</th>
      <th align="center"></th>
      <th align="center">Accuracy (in %)</th>
      <th align="center">Precision (in %)</th>
      <th align="center">Recall (in %)</th>
      <th align="center">F1 Score (in %)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center" rowspan="2"><strong>ReLU</strong></td>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center"><code>95.010</code></td>
      <td align="center"><code>92.683</code></td>
      <td align="center"><code>91.618</code></td>
      <td align="center"><code>92.078</code></td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center"><code>93.997</code></td>
      <td align="center"><code>90.922</code></td>
      <td align="center"><code>89.501</code></td>
      <td align="center"><code>90.138</code></td>
    </tr>
    <tr>
      <td align="center" colspan="6"></td>
    </tr>
    <tr>
      <td align="center" rowspan="2"><strong>Tanh</strong></td>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center"><code>96.864</code></td>
      <td align="center"><code>95.259</code></td>
      <td align="center"><code>93.779</code></td>
      <td align="center"><code>91.204</code></td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center"><code>95.014</code></td>
      <td align="center"><code>91.932</code></td>
      <td align="center"><code>90.576</code></td>
      <td align="center"><code>91.204</code></td>
    </tr>
    <tr>
      <td align="center" colspan="6"></td>
    </tr>
    <tr>
      <td align="center" rowspan="2"><strong>Sigmoid</strong></td>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center"><code>94.290</code></td>
      <td align="center"><code>92.100</code></td>
      <td align="center"><code>90.649</code></td>
      <td align="center"><code>91.356</code></td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center"><code>93.471</code></td>
      <td align="center"><code>90.658</code></td>
      <td align="center"><code>89.175</code></td>
      <td align="center"><code>89.896</code></td>
    </tr>
  </tbody>
  </table>

## AdaBoost Classifier
  <table>
  <thead>
    <tr>
      <th align="center"></th>
      <th align="center">Accuracy (in %)</th>
      <th align="center">Precision (in %)</th>
      <th align="center">Recall (in %)</th>
      <th align="center">F1 Score (in %)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center"><code>100.000</code></td>
      <td align="center"><code>100.000</code></td>
      <td align="center"><code>100.000</code></td>
      <td align="center"><code>100.000</code></td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center"><code>94.308</code></td>
      <td align="center"><code>94.305</code></td>
      <td align="center"><code>94.308</code></td>
      <td align="center"><code>94.306</code></td>
    </tr>
  </tbody>
  </table>

## Histogram-based Gradient Boosting Classifier
  <table>
  <thead>
    <tr>
      <th align="center"></th>
      <th align="center">Accuracy (in %)</th>
      <th align="center">Precision (in %)</th>
      <th align="center">Recall (in %)</th>
      <th align="center">F1 Score (in %)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center"><code>95.398</code></td>
      <td align="center"><code>95.403</code></td>
      <td align="center"><code>95.398</code></td>
      <td align="center"><code>95.391</code></td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center"><code>93.390</code></td>
      <td align="center"><code>93.392</code></td>
      <td align="center"><code>93.390</code></td>
      <td align="center"><code>93.378</code></td>
    </tr>
  </tbody>
  </table>

## Bagging Classifier
  <table>
  <thead>
    <tr>
      <th align="center"></th>
      <th align="center">Accuracy (in %)</th>
      <th align="center">Precision (in %)</th>
      <th align="center">Recall (in %)</th>
      <th align="center">F1 Score (in %)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center"><code>99.995</code></td>
      <td align="center"><code>99.995</code></td>
      <td align="center"><code>99.995</code></td>
      <td align="center"><code>99.995</code></td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center"><code>96.938</code></td>
      <td align="center"><code>96.933</code></td>
      <td align="center"><code>96.938</code></td>
      <td align="center"><code>96.932</code></td>
    </tr>
  </tbody>
  </table>
