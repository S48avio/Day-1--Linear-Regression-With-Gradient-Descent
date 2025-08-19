# Linear Regression and Gradient Descent

**Linear Regression** is a regression problem where we predict continuous values.  
It is a supervised learning algorithm where we train the model using a dataset and then test it on unseen data.  

The idea of Linear Regression is to find the **best fit line** that represents the training data and can make predictions on test data.

---

## Equation of a Line
The equation of a straight line is:  

$$ y = mx + c $$

- **m** = slope of the line (how much y changes when x changes by 1)  
- **c** = intercept (value of y when x = 0)  

So, our task is to learn the best values of **m** and **c**.

---

## Loss Function
We use **Mean Squared Error (MSE)** as the loss function:  

$$ J(m,c) = \frac{1}{N} \sum_{i=1}^{N} \left( y_i - (mx_i + c) \right)^2 $$  

The goal is to minimize this loss function.

---

## Gradient Descent (GD)

Gradient Descent is an optimization algorithm used to minimize the loss function.  
The idea is to start with some random values for **m** and **c**, then update them iteratively to reduce the loss.

---

### Update Rules

1. Compute gradients (partial derivatives):

$$ \frac{\partial J}{\partial m} = -\frac{2}{N} \sum_{i=1}^{N} x_i \left( y_i - (mx_i + c) \right) $$

$$ \frac{\partial J}{\partial c} = -\frac{2}{N} \sum_{i=1}^{N} \left( y_i - (mx_i + c) \right) $$

---

2. Update parameters:

$$ m := m - \alpha \cdot \frac{\partial J}{\partial m} $$

$$ c := c - \alpha \cdot \frac{\partial J}{\partial c} $$

Where **α** (alpha) is the **learning rate**, which controls the step size.  

---

### Intuition
- If gradient > 0 → decrease the parameter value.  
- If gradient < 0 → increase the parameter value.  
- Repeat until gradients are very small (close to 0).  

At that point, the model has found the **best fit line**.
