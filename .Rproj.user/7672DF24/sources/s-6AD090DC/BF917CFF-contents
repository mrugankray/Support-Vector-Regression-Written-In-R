#import the dataset
dataset = read.csv('Position_Salaries.csv')
dataset = dataset[2:3]

#fitting SVR regressor into dataset
library(e1071)
regressor = svm(formula = Salary ~ . , data = dataset , type = 'eps-regression')

#visualising the polynomial regression results
library(ggplot2)
x_grid = seq(min(dataset$Level), max(dataset$Level), 0.1)
ggplot() +
  geom_point(aes(x = dataset$Level, y = dataset$Salary), color = 'red')+
  geom_line(aes(x = x_grid, y = predict(regressor,
                                        newdata = data.frame(Level = x_grid))),
            colour = 'blue') +
  ggtitle('True or Bluff(SVR regression)')+
  xlab('Level')+
  ylab('Salary')

#predicting a new result using linear regression
y_pred_linear_regression = predict(regressor, newdata = data.frame(Level = 6.5))
