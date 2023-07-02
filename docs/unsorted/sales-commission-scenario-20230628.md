---
createdAt: 2023-06-28T08:28:18+02:00
dg-publish: true
modifiedAt: 2023-07-02T11:37:00+02:00
title: "Sales commission scenario"
---
# Sales commission scenario

How to calculate the total compensation (salary + sales commission) of a salesperson in a Vietnam company

## Overview

Situation: A company in Vietnam ask their salespersons to choose a monthly sales target based on a given compensation table.

Question: Which target should a salesperson choose?

## Thoughts

The calculation is quite simple. You can check this [public ggsheet simulation table](https://docs.google.com/spreadsheets/d/1vp6-_2dE4raeym03sYPakXQfrSXLxJRVntI9yuN23SE/edit?usp=sharing) for the formulae in details. In the ggsheet, the 2 sheets `param_salary` and `param_input` were established based on the information derived from [this compensation table](https://app.box.com/s/9q6n3e7a1b7fwdqlf3c99wizh66k3jf7).

The chart below visualize the difference in total compensation between each pair of possible targets.

![sales-target-compensation-diff](https://ik.imagekit.io/casa/h7b-dendron/20230701_sales-target-compensation-diff_BZGK0uLSB.svg?updatedAt=1688179752735)

My observations:
- The monthly target 8 container seems to be a trap for employee. It's the worst case for every possible actual number of containers that a salesperson can achieve
- When the salesman estimate his number of monthly sales figure (N) can reach up to 27 containers per month, the target 15 is the optimal choice.
- When 28 <= N <= 38, choose the target 30.
- When N > 38, choose the target 45
- I stopped the simulation from here, since I estimated that the highest possible number of this salesperson cannot surpass the target 45

The calculation used spreadsheet formula which is simple but not elegant. A version using jupyter notebook might be elaborated if I can get enough interest from my audience.