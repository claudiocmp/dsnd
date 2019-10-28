Non parametric experiments have two functions:
  * Provide methodologies when data from a standard experiment is not available
  * can be used to double-check standard experiments


## Bootstrapping Test

Key facts:
  * Run on: data collected (with re-sampling)
  * Metric: mean
  * To compare: 'distance' between control and experimental groups


## Permutation Test

In brief: 

Key facts:
  * Run on: data collected (with re-sampling)
  * Metric: mean
  * To compare: 'distance' between control and experimental groups


## Rank-Sum Test (Mann-Whitney)

Key facts
  * Run on: data collected (no re-sampling)
  * Metric: None
  * To compare: data distribution
  * Principle: draw one random data point from each group. The draw probability will be:
    * The same, to not reject the null hypothesis
    * Different, to reject the null hypothesis
  * Pseudocode:
    * U = []
    * for each data_a in group A
      * win = $data_a > each_data_in_B$
      * tie = $data_a == each_data_in_B$
      * U.append(sum(win)+0.5*sum(tie))
    * calculate the mean_n for null hypothesis as n_1*n_2/2
    * calculate the sd_n for null hypothsesis as sqrt( n_1 * n_2 * (n_1 + n_2 + 1) / 12 )
    * calculate the z-score of u compared to the null hypothesis as z = (mean(u)-mean_null)/sd_null
    * calculate the p_value if:
      * alternative = less (p @ z)
      * alternative = greater (p @ -z)
      * alternative = both (p @ abs(z))
    
  * Finally, p indicates the probability for the deviation from the mean given by the difference of the mean measured by the z-score

Scipy:
```
import scipy.stats as stats

stats.mannwhitneyu(data[data['condition'] == 0]['time'],
                   data[data['condition'] == 1]['time'],
                   alternative = 'greater')
```

## Sign Test

