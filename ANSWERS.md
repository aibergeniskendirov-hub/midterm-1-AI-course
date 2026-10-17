# Midterm 1: answers

GitHub username: aibergeniskendirov-hub
Session code: zebra-28
Fingerprint: 83b3806f

> Fill in the three lines above from `my_data/DATA.md`. Do not rename headings or table columns: a script reads the numbers.
> Write only in the empty cells and lines. Percentages as 0.78 or 78 %, money as plain numbers.

## AI-use declaration

(About half a page: which assistants or tools you used and for what. If you used none, say so.)

## Part 1: Retrieval and cost decision

### 1a. Metrics (all 60 questions)

| config | recall@1 | recall@3 | recall@5 | MRR@10 |
|---|---|---|---|---|
| A |0.683333|0.850000|0.900000|0.769907 |
| B |0.266667|0.466667 |0.616667 |0.394392|

### 1b. Recall and 95 % Wilson interval of each candidate (recall at its own k)

| candidate | recall@k | lower | upper |
|---|---|---|---|
| A, k=3 |85% |73.89%|91.90%|
| A, k=5 |90%|79.85%|95.34%|
| B, k=3 |46.67%|34.63%|59.11%|
| B, k=5 |61.67%|49.02%|72.91%|

### 1c. Annual model cost in USD

| candidate | annual cost |
|---|---|
| A, k=3 |10607.57|
| A, k=5 |13809.61|
| B, k=3 |6975.94|
| B, k=5 |7756.89|

### 1d. Decision (at most 150 words)

Chosen candidate: А, k=3
I chose A, k=3. Its annual cost is 10607.57, which fits within the 12200 budget. Its overall recall is 85% with an interval of 73.89–91.90%. This interval does not overlap with the intervals of either B candidate, so by the task's rule A, k=3 is shown to be better than both, even though B is cheaper. A, k=5 is not an option because it costs 13809.61, which is over budget, and its interval overlaps with A, k=3, so it has not been shown to be better anyway.

Recall by language for A, k=3: EN 18/20 = 90%, RU 16/20 = 80%, KK 17/20 = 85%. Russian was the weakest, but with only 20 questions per language this difference is not conclusive.
(Decision, using your intervals and the budget. Give the recall of your choice for EN, RU and KK separately.)

### 1e. Next measurement (at most 60 words)
Next, I would compare A, k=3 and B, k=5 on 600 new questions, 200 per language. A teacher would check final answers without knowing which system produced them. I would compare accuracy and uncertainty for each language. I would choose cheaper B if the results showed it was no more than five percentage points worse in any language.

## Part 2: A document pipeline you can defend

### 2a. Numbers

| pipeline | overall accuracy | weakest cell (language, condition) | accuracy there | lower | upper | annual cost |
|---|---|---|---|---|---|---|
| H | | | | | | |
| L | | | | | | |

Personal-data pages per year sent abroad under H:

### 2b. Memo (at most 300 words)

## Part 3: Explain your own numbers

### Q1

Number:
Why (at most 40 words):

### Q2

Number:
Why (at most 40 words):

### Q3

Number:
Why (at most 40 words):

### Q4

Number:
Why (at most 40 words):

### Q5

Number:
Why (at most 40 words):
