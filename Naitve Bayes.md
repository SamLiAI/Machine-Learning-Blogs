
# Naive Bayes Rule

Hi guys! In this Blog, I will show an interesting example of how to use the Naive Bayes Rule to predict the probability of an event. Let's get to it!

## Example
Suppose we have a table that looks like this which shows the features (color, type, and origin), and we simply want to calculate the probability that a car will be stolen when it is a domestic red SUV. 
| Example No | Color  | Type   | Origin   | Stolen? |
|------------|--------|--------|----------|---------|
| 1          | Red    | Sports | Domestic | YES     |
| 2          | Red    | Sports | Domestic | NO      |
| 3          | Red    | Sports | Domestic | YES     |
| 4          | Yellow | Sports | Domestic | NO      |
| 5          | Yellow | Sports | Imported | YES     |
| 6          | Yellow | SUV    | Imported | NO      |
| 7          | Yellow | SUV    | Imported | YES     |
| 8          | Yellow | SUV    | Domestic | NO      |
| 9          | Red    | SUV    | Imported | NO      |
| 10         | Red    | SUV    | Imported | YES     |

To solve this problem, we first transfer the problem statement to a mathematical statement, which is to predict P(YES|Red, SUV, Domestic).

According to Naive Bayes Rule, P(YES|RED, SUV, Domestic) = P(Red|YES)*P(SUV|YES)*P(Domestic|YES)

Then, we just need to count the frequency of each event. So, P(Red|YES) = 3/5, P(SUV|YES) = 1/5, P(Domestic|YES) = 2/5, P(YES) = 1/2.
Therefore, the result = 0.024

## Summary
This example shows the foundation of Naive Bayes Rule, and we can implement Naive Bayes Rule for further classification projects. 
