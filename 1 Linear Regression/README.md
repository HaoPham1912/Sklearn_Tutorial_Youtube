![simplinnovation](https://4.bp.blogspot.com/-f7YxPyqHAzY/WJ6VnkvE0SI/AAAAAAAADTQ/0tDQPTrVrtMAFT-q-1-3ktUQT5Il9FGdQCLcB/s350/simpLINnovation1a.png)

# Basic Machine Learning Using Sklearn Tutorial

### __1. Linear Regression__ (📂[_click to go to its repo_](https://github.com/LintangWisesa/Sklearn_Tutorial_Youtube/tree/master/1%20Linear%20Regression))

[![lintang](https://img.youtube.com/vi/YwBXxmRbXzY/0.jpg)](https://www.youtube.com/watch?v=YwBXxmRbXzY)

```python

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

myData = pd.read_excel('data.xlsx')
# print(myData)

# split datasets: 90% training data & 10% test data
from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test = train_test_split(
    myData['ukuran'],
    myData['harga'],
    test_size = .1
)
print(len(x_train))
print(len(x_test))

# linear regression
from sklearn.linear_model import LinearRegression
model = LinearRegression()

# training
model.fit(myData[['ukuran']], myData['harga'])

# slope/gradient/m best fit line:
print(model.coef_[0])

# intercept/b best fit line:
print(model.intercept_)


# plot best fit line
# y = mx + b
plt.plot(
    myData['ukuran'],
    model.coef_[0] * myData['ukuran'] + model.intercept_,
    'r-'
)

# plot dataframe
plt.scatter(
    myData['ukuran'],
    myData['harga'],
    marker = 'o',
    color = 'g'
)
plt.title('Harga Rumah vs Ukuran Tanah')
plt.xlabel('Ukuran (m2)')
plt.ylabel('Harga (juta Rupiah)')
plt.grid(True)

plt.show()

# prediction: harga terbaik: 320m2, 670m2 & 3000m2 ?
print('Prediksi')
print('Prediksi harga rumah 320m2 =', model.predict([[320]]))
print('Prediksi harga rumah 670m2 =', model.predict([[670]]))
print('Prediksi harga rumah 3000m2 =', model.predict([[3000]]))

```

![lintang](./plot.png)

#

#### Lintang Wisesa :love_letter: _lintangwisesa@ymail.com_

[Facebook](https://www.facebook.com/lintangbagus) | 
[Twitter](https://twitter.com/Lintang_Wisesa) |
[Google+](https://plus.google.com/u/0/+LintangWisesa1) |
[Youtube](https://www.youtube.com/user/lintangbagus) | 
:octocat: [GitHub](https://github.com/LintangWisesa) |
[Hackster](https://www.hackster.io/lintangwisesa)