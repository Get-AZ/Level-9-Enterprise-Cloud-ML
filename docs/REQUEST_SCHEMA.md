# Request Schema

## Required fields in order

1. `age` - numeric
2. `job` - categorical
3. `marital` - categorical
4. `education` - categorical
5. `default` - categorical
6. `balance` - numeric
7. `housing` - categorical
8. `loan` - categorical
9. `contact` - categorical
10. `day` - numeric
11. `month` - categorical
12. `duration` - numeric
13. `campaign` - numeric
14. `pdays` - numeric
15. `previous` - numeric
16. `poutcome` - categorical

## Azure MLflow envelope

Use an `input_data` object containing `columns`, `index`, and `data`. Preserve the exact column order. Do not include the target label. Validate JSON types and run local inference before sending a new request shape to Azure.

No sample customer values are published in this repository package.
