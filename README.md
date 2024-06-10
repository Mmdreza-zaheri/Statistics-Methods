
# Student Stress and Illness Analysis

## Overview

This repository contains a dataset of student stress levels, illness frequency, and grades collected at the beginning and end of the year. Statistical tests, including paired t-tests and independent t-tests, were conducted to analyze the data. 

## Files

- `data.csv`: The dataset containing the following columns:
  - `gender`: Gender of the student (boy/girl)
  - `stress_first`: Stress level at the beginning of the year
  - `num_ill`: Number of times the student was ill
  - `grade_pre`: Grade at the beginning of the year
  - `final_grade`: Grade at the end of the year
  - `stress_final`: Stress level at the end of the year
- `analysis.ipynb`: Jupyter notebook containing the code for the statistical analysis.

## Statistical Analysis

### Independent t-tests

Independent t-tests were performed to compare the means between boys and girls for the following variables:

1. **Stress levels at the beginning of the year**
   ```python
   test, pval = ttest_ind(boys['stress_first'], girls['stress_first'])
   print('Test:', test)
   print('P-value:', pval)
   ```
   - **Test Statistic:** 1.320
   - **P-value:** 0.203

2. **Number of illnesses**
   ```python
   test, pval = ttest_ind(boys['num_ill'], girls['num_ill'])
   print('Test:', test)
   print('P-value:', pval)
   ```
   - **Test Statistic:** 0.420
   - **P-value:** 0.679

3. **Grades at the beginning of the year**
   ```python
   test, pval = ttest_ind(boys['grade_pre'], girls['grade_pre'])
   print('Test:', test)
   print('P-value:', pval)
   ```
   - **Test Statistic:** 0.650
   - **P-value:** 0.524

4. **Grades at the end of the year**
   ```python
   test, pval = ttest_ind(boys['final_grade'], girls['final_grade'])
   print('Test:', test)
   print('P-value:', pval)
   ```
   - **Test Statistic:** 2.435
   - **P-value:** 0.026

5. **Stress levels at the end of the year**
   ```python
   test, pval = ttest_ind(boys['stress_final'], girls['stress_final'])
   print('Test:', test)
   print('P-value:', pval)
   ```

### Paired t-tests

Paired t-tests were performed to compare stress levels within the same group of students at the beginning and end of the year.

1. **Stress levels change**
   ```python
   test, pval = stats.ttest_rel(df['stress_first'], df['stress_final'])
   print('Test:', test)
   print('P-value:', pval)
   ```
   - **Test Statistic:** 2.319
   - **P-value:** 0.032

## Results

- **Stress levels at the beginning of the year**: No significant difference between boys and girls (p > 0.05).
- **Number of illnesses**: No significant difference between boys and girls (p > 0.05).
- **Grades at the beginning of the year**: No significant difference between boys and girls (p > 0.05).
- **Grades at the end of the year**: Significant difference between boys and girls (p < 0.05).
- **Stress levels at the end of the year**: Test pending results.
- **Change in stress levels**: Significant difference over the year (p < 0.05).

## Conclusion

The analysis reveals that there is a significant difference in final grades between boys and girls and a significant change in stress levels over the year. Further investigation is needed for stress levels at the end of the year.

## Usage

To run the analysis, open the `analysis.ipynb` notebook and execute the cells. Ensure you have the necessary Python packages installed:

```bash
pip install pandas numpy scipy
```
