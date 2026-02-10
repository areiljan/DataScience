# Questions
## 1.
what is the output of the following function?
``len(list(range(10))[-1::-1])``
- 10

What is the output of the following code?
``array = np.array(range(74))
np.argmax(np.sort(array)-np.sum(array))``
- 0

## 2.
Let `awesome.dt` be a DataFrame. Which command produces the following table?
|   | x | y     |
|---|---|-------|
| 0 | 6 | True  |
| 1 | 5 | True  |
| 2 | 4 | True  |
| 3 | 3 | False |
| 4 | 2 | False |
| 5 | 1 | False |
- df = pd.DataFrame({"x": range(1, 6), "y": [True]*3 + [False]*3})

Find the last 10 flights arriving in LAX on Christmas Eve (24. December). Don’t worry about sorting
for now, just find the last 10 entries in the table.
- flights[(flights['MONTH'] == 12) & (flights['DAY'] == 24) & (flights['DESTINATION_AIRPORT']
== 'LAX')].tail(10)

Calculate the total number of outbound flights in the summer months (June - August) by airport.
- flights[flights['MONTH'].isin(range(6,9))].groupby('ORIGIN_AIRPORT').size()

## 3.
QUestions: Are these datasets tidy?

| Index | Model             | mpg  | hp  | wt    |
|------:|-------------------|-----:|----:|------:|
| 0     | Mazda RX4         | 21.0 | 110 | 2.620 |
| 1     | Mazda RX4 Wag     | 21.0 | 110 | 2.875 |
| 2     | Datsun 710        | 22.8 | 93  | 2.320 |
| 3     | Hornet 4 Drive    | 21.4 | 110 | 3.215 |
| 4     | Hornet Sportabout | 18.7 | 175 | 3.440 |

- Yes, this dataset is tidy. Each variable has a column, each observation has a row. Each value ahas its own cell.

| Index | country | 1999 | 2000 |
|-------|---------|------|------|
| 0 |Afghanistan | 745 | 2666 |
| 1 | Brazil | 37737 | 80488 |
| 2 | China | 212258 | 213766 | 

- No, this dataset is not tidy. There are variables (1999, 2000) that are used in multiple columns. They should be values in separate column called year. The values that are marked here need an explanation.

| religion | <$10k | $10-20k | $20-30k | $30-40k | $40-50k | $50-75k |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Agnostic | 27 | 34 | 60 | 81 | 76 | 137 |
| Atheist | 12 | 27 | 37 | 52 | 35 | 70 |
| Buddhist | 27 | 21 | 30 | 34 | 33 | 58 |
| Catholic | 418 | 617 | 732 | 670 | 638 | 1116 |
| Don't know/refused | 15 | 14 | 15 | 11 | 10 | 35 |
- This is not a tidy dataset. We would need to melt it first in order to get the earnings brackets into a single column. 

| id | year | month | element | d1 | d2 | d3 | d4 | d5 | d6 | d7 | d8 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| MX17004 | 2010 | 1 | tmax | --- | --- | --- | --- | --- | --- | --- | --- |
| MX17004 | 2010 | 1 | tmin | --- | --- | --- | --- | --- | --- | --- | --- |
| MX17004 | 2010 | 2 | tmax | --- | 27.3 | 24.1 | --- | --- | --- | --- | --- |
| MX17004 | 2010 | 2 | tmin | --- | 14.4 | 14.4 | --- | --- | --- | --- | --- |
| MX17004 | 2010 | 3 | tmax | --- | --- | --- | --- | 32.1 | --- | --- | --- |
| MX17004 | 2010 | 3 | tmin | --- | --- | --- | --- | 14.2 | --- | --- | --- |
- This is not a tidy dataset. We could pivot the table to be in long format. I would first make the tmax and tmin separate columns. Then melt the d(day) values and combine them into a single column date. The final column will have headers: id, date, tmax, tmin.
## 4.

When do we use a line plot for visualizing data?

- to show a connection between a series of individual data points

What's the result of the following command? ``ggplot(mpg)``
- empty plot, missing coordinates

What's the result of the following command? ``ggplot(mpg, aes(x=hwy, y=cty))``
- An empty plot with a x and y axis marked, no data points marked

For which type of data will boxplots produce meaningful visualizations?
- For exponentially distributed data, for non-Gaussian, symmetric data


## 5. 
What could make k-means clustering fail?

- When data are not normalized, making data points stick together

**4.** Each entry **A**, **B**, **C**, **D** in the table shows hypothetical explained variance values attributed to **PC1** and **PC2** of a 4-dimensional dataset. Which entr(ies) **A**, **B**, **C** or **D** are possible?

| | PC1 | PC2 |
| :--- | :--- | :--- |
| **A** | 60 % | 50 % |
| **B** | 35 % | 40 % |
| **C** | 60 % | 40 % |
| **D** | 40 % | 25 % |
- **A** is not possible as the explained variance is over 100%. **B** is not possible as PC1 must always explain the most variance by definition. **C** is possible but highly unlikely. **D** is very possible.
## 6. 
Which of the following claims could be an example of reversing cause and effect?
1. Healthier diets increase blood pressure.
2. Low social status leads to a higher risk of schizophrenia.
3. The number of fire engines on a fire gives rise to higher damages.
4. Entering an intensive care unit increases the risk of death.
- All of them are possible examples of reversing cause and effect. There is no firm way to decide the direction of causality from a mere association.

The ministry of health of Datavizland observed a positive correlation between the liters of water drunk
per day and sunburns.
Which kind of causal diagram may best describe this scenario?
- There is likely not a direct relationship as a third variable is involved. This is called Common Cause.

A study conducted in Datavizland by Woman’s magazine analyzed the dating preference of women.
For each previous or current partner, women were asked to evaluate men on two parameters from 0-10:
How handsome and how fun they are.
The study concluded: ”We report a negative correlation between how handsome and how fun a man is,
therefore we conclude that handsome men are boring”.
In the same week a study conducted on the whole population of men by Men’s magazine reported no
correlation between how handsome and how fun a man is.
How can you explain this apparent paradox? Which kind of causal diagram describes this scenario?
- This is likely a common consequence. The thing is that women usually date men who are handsome and fun.
## 7. 
The null hypothesis of a study states ‘The number of Olympic gold medals expected from U.S. competitors
is the same for both genders’. What are possible one-tailed alternative hypotheses?
- The expected number of US Olympic gold medals from females is larger than from males. OR
The U.S. Olympic team is more likely to win gold medals from the competitions involving male
athletes than female athletes.

The p-value of a certain hypothesis test is 0.007. What can the researcher conclude?
- Assuming the null hypothesis is true, the probability of making this observation or a more extreme
one is 0.7%.

Let X be a pandas Series that contains some collected data. Which of the following lines of code produces
one sample of a case resampling bootstrap?
- ``X.sample(frac=1, replace=True)``
- ``X.sample(frac=1, replace=True, weights=[0.2] * (len(X)//2) + [0.5] * (len(X)//2))``

## 8.
Consider the following (extreme) 2x2 contingency table and assume we want to test the association of taking antiviral medicine with having symptoms from a viral disease. Indicate which, if any, of the following statements are **correct**:

| has_symptoms <br> got_antiviral | False | True | All |
| :--- | :---: | :---: | :---: |
| **False** | 1 | 100 | 101 |
| **True** | 99 | 0 | 99 |
| **All** | 100 | 100 | 200 |



## 9.

## 10.

## 11.

## 12.
