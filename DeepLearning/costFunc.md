# Cost Functions and Optimizations

### Mean absolute error
$\frac{1}{n}\sum_i^n|\hat{y}_i - y_i|$
- Insensitive to outliers.
- Isn`t differentiable at Zero point.

### Mean square error
$\frac{1}{n}\sum_i^n(\hat{y}_i - y_i)^2$
- Very sensitive to outliers.

### Root mean square error
$\sqrt{\frac{1}{n}\sum_i^n(\hat{y}_i - y_i)^2}$

- Less sensitive to outliers than RMSE.

### Root mean square logarithmic error
$\sqrt{\frac{1}{n}\sum_i^n(\log(\hat{y}_i + 1) - \log(y_i + 1))^2}$

- Less sensitive to outliers than RMSE

### Optimization

SGD, RMSprop, Adam.
