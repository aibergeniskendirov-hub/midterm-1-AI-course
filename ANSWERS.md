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
| H |86.67%|KK, clean|76.67%|59.07%|88.21%|7550.03|
| L |81.67%|RU, degraded; KK, degraded (tie)|76.67%|59.07%|88.21%|5400.00|

Personal-data pages per year sent abroad under H: 251850

### 2b. Memo (at most 300 words)
Recommendation. I recommend pipeline L. It costs 5400.00 per year compared with 7550.03 for H. H has higher overall accuracy (86.67% vs 81.67%), but the intervals overlap (H: 80.93–90.87%, L: 75.37–86.64%), so by the task's rule H's advantage is not established. H also sends 251850 personal-data pages per year abroad, a privacy risk that an unproven accuracy gain does not justify. L processes scans in Kazakhstan, but the location of backups and any external transfers still needs to be checked.

Who is worse served. The overall numbers hide weaker groups. For L, the weakest cells are Russian degraded scans and Kazakh degraded scans (tie), both at 76.67% with an interval of 59.07–88.21%. For H, the weakest cell is Kazakh clean documents, also 76.67% (59.07–88.21%).

Personal data. Under H, pages go to a provider abroad; we need to confirm who stores them, where, and for how long. Under L, the retention period is not yet known; we need to check staff access, backup locations and deletion deadlines.

Safeguards and remaining risk. I would add human review for degraded scans and for Russian and Kazakh documents, and track accuracy per language and scan quality each month. I would also audit the list of authorised users and test that old scans are deleted together with their backups. IINs are protected under Kazakhstan's Law No. 94-V on personal data, and a vendor's promise does not replace checking compliance. The remaining risk is that a reviewer may miss an error during checking, and our small test set may not reflect real scans.

## Part 3: Explain your own numbers

### Q1

Number:2.09
Why (at most 40 words):KK and EN have different shares of input and output tokens, and output tokens cost more than input tokens. So the cost ratio between KK and EN differs from their token-count ratio.

### Q2

Number:444
Why (at most 40 words):The answer sentence starts around token 444 and ends before token 464, inside e5-small's 512-token limit. Retrieval is therefore possible but not guaranteed; text beyond 512 tokens is truncated silently, without an error.

### Q3

Number:59.9%
Why (at most 40 words):Temperature reshapes the probability distribution; top-p then drops the low-probability tail and renormalizes the remaining probabilities. Here, "Easter" is removed.

### Q4

Number:13
Why (at most 40 words):Without a penalty, X wins, because unpenalized scoring rewards guessing. With a penalty for wrong answers, X scores 38 and Y scores 51, a difference of 13.

### Q5

Number:13.95
Why (at most 40 words):The model uses 279 tokens per parameter versus Chinchilla's 20. By this criterion it is trained far beyond the Chinchilla-optimal point, which is not necessarily overfitting. GPT-3, by contrast, was undertrained for its size.
