1. Sample spaces
A sample space is the set of all possible outcomes of an experiment.
(a) Tossing 3 coins
Let H = Head and T = Tail.
Sample space:
\[
S=\{HHH,HHT,HTH,HTT,THH,THT,TTH,TTT\}
\]

Number of outcomes:
\[
n(S)=2^3=\boxed{8}
\]

(b) Tossing 4 coins
















So answer the questions













Exercise 3.1 — Answers
1. For 3 coins, find \(P(\text{at least one head})\) in two ways.
Method (a): Direct method
Sample space:
\[
S=\{HHH,HHT,HTH,HTT,THH,THT,TTH,TTT\}
\]

Total outcomes = 8.
Outcomes with at least one head:
\[
E=\{HHH,HHT,HTH,THH,HTT,THT,TTH\}
\]

Favourable outcomes = 7.
\[
P(E)=\frac{\text{Favourable outcomes}}{\text{Total outcomes}}
\]

\[
\boxed{P(E)=\frac{7}{8}=0.875}
\]

Method (b): Complement method
The complement of getting at least one head is getting no heads, which means all tails (TTT).
\[
P(E)=1-P(\text{no head})
\]

\[
P(E)=1-\frac{1}{8}
\]

\[
\boxed{P(E)=\frac{7}{8}=0.875}
\]

2. Generate other possible probabilities from the sample spaces of 3 coins, 4 coins and 2 dice.
Python code to run in your Jupyter Notebook:
from itertools import product# Sample spacescoins3 = list(product("HT", repeat=3))coins4 = list(product("HT", repeat=4))dice2 = list(product(range(1, 7), repeat=2))print("3 coins:", coins3)print("Number of outcomes:", len(coins3))print("\n4 coins:", coins4)print("Number of outcomes:", len(coins4))print("\n2 dice:", dice2)print("Number of outcomes:", len(dice2))# Example probabilitiesp3_heads = sum(1 for x in coins3 if x.count("H") == 2) / len(coins3)p4_heads = sum(1 for x in coins4 if x.count("H") >= 1) / len(coins4)p_dice_sum7 = sum(1 for x in dice2 if sum(x) == 7) / len(dice2)print("\nExactly 2 heads in 3 coins:", p3_heads)print("At least 1 head in 4 coins:", p4_heads)print("Sum of 7 on 2 dice:", p_dice_sum7)



Expected results and explanations
Experiment	Event	Probability
3 coins	Exactly 2 heads	\(3/8=0.375\)
3 coins	All tails	\(1/8=0.125\)
3 coins	All heads	\(1/8=0.125\)
4 coins	At least 1 head	\(15/16=0.9375\)
4 coins	Exactly 2 heads	\(6/16=0.375\)
2 dice	Sum equals 7	\(6/36=0.1667\)
2 dice	Both dice show 6	\(1/36\approx0.0278\)
2 dice	Sum equals 12	\(1/36\approx0.0278\)
Sample space sizes
- 3 coins: \(2^3=\boxed{8}\) outcomes.
- 4 coins: \(2^4=\boxed{16}\) outcomes.
- 2 dice: \(6^2=\boxed{36}\) outcomes.
Conclusion: The probability of an event is the number of favourable outcomes divided by the total number of equally likely outcomes.
















Okay step by step instructions while using markdown comments













We shall do it from the beginning in VS Code using your Jupyter Notebook, just like the practical shown on the classroom screen. I’ll show you what to click, what to type, and where to use Markdown comments.
Step 1: Open your notebook
1. Open VS Code.
2. Open Probability_Practical_Events.ipynb.
3. You should see the notebook with options such as + Code and + Markdown.
Step 2: Create the practical heading using Markdown
1. Click + Markdown.
2. Type the following into the cell:

# Probability Practical: Sample Spaces, Events and Computing Probability

## Exercise 3.1

This practical explores sample spaces, events and probability using Python.
We will use the itertools.product function to generate all possible outcomes.



3. Press Shift + Enter to run the Markdown cell.
Markdown cells are for headings, explanations and notes. They do not execute Python calculations.
Step 3: Question 1 — Sample spaces
Click + Markdown and enter:

### Question 1: Sample Spaces

A sample space is the set of all possible outcomes of an experiment.

- Three coins have 2^3 = 8 possible outcomes.
- Four coins have 2^4 = 16 possible outcomes.
- Two dice have 6^2 = 36 possible outcomes.



Press Shift + Enter.
Step 4: Import the Python library
Click + Code and type:
# Import product to generate all possible combinationsfrom itertools import product



Press Shift + Enter to execute it.
Step 5: Generate the sample space for 3 coins
Click + Code and type:
# Generate all possible outcomes when tossing 3 coinscoins3 = list(product("HT", repeat=3))# Display the sample spaceprint("Sample space for 3 coins:")print(coins3)# Count the total outcomesprint("Total outcomes:", len(coins3))



Press Shift + Enter.
You should get 8 outcomes: HHH, HHT, HTH, HTT, THH, THT, TTH, TTT.
Step 6: Generate the sample space for 4 coins
Click + Code and type:
# Generate all possible outcomes when tossing 4 coinscoins4 = list(product("HT", repeat=4))# Display the sample spaceprint("Sample space for 4 coins:")print(coins4)# Count the total outcomesprint("Total outcomes:", len(coins4))



Press Shift + Enter.
Expected total: 16 outcomes.
Step 7: Generate the sample space for 2 dice
Click + Code and type:
# Generate all possible outcomes when rolling 2 dicedice2 = list(product(range(1, 7), repeat=2))# Display the sample spaceprint("Sample space for 2 dice:")print(dice2)# Count the total outcomesprint("Total outcomes:", len(dice2))



Press Shift + Enter.
Expected total: 36 outcomes.
Step 8: Question 2 — Probability of at least one head with 3 coins
First, click + Markdown and type:

### Question 2: Probability of At Least One Head

#### Method A: Direct Method

Probability = Number of favourable outcomes / Total number of outcomes.

An outcome is favourable if it contains at least one head.



Press Shift + Enter.
Now click + Code and type:
# Count outcomes containing at least one headfavourable = sum(1 for outcome in coins3 if "H" in outcome)# Calculate the probability directlyprobability_direct = favourable / len(coins3)print("Favourable outcomes:", favourable)print("Total outcomes:", len(coins3))print("Probability using direct method:", probability_direct)



Expected probability: 0.875.
Step 9: Use the complement method
Click + Markdown and type:

#### Method B: Complement Method

The complement of getting at least one head is getting no heads.
This happens only when all three coins show tails (TTT).

P(at least one head) = 1 - P(no heads)




Click + Code and type:
# Count outcomes with no headsno_heads = sum(1 for outcome in coins3 if "H" not in outcome)# Calculate probability using the complementprobability_complement = 1 - (no_heads / len(coins3))print("Outcomes with no heads:", no_heads)print("Probability using complement:", probability_complement)



Expected probability: 0.875.
Both methods give the same answer: \(P(\text{at least one head})=\frac{7}{8}=0.875\).
Step 10: Generate other possible probabilities
Click + Markdown and type:

### Other Possible Probabilities

We can use the sample spaces to calculate additional probabilities for three coins, four coins and two di
Click + Code and type:
# Probability of exactly 2 heads when tossing 3 coinsexactly_two_heads = sum(    1 for outcome in coins3 if outcome.count("H") == 2) / len(coins3)# Probability of at least 1 head when tossing 4 coinsat_least_one_head_4 = sum(    1 for outcome in coins4 if "H" in outcome) / len(coins4)# Probability that two dice have a sum of 7sum_seven = sum(    1 for outcome in dice2 if sum(outcome) == 7) / len(dice2)# Display the resultsprint("Exactly 2 heads in 3 coins:", exactly_two_heads)print("At least 1 head in 4 coins:", at_least_one_head_4)print("Sum of 7 on 2 dice:", sum_seven)




Expected results:
- Exactly 2 heads in 3 coins: 0.375
- At least 1 head in 4 coins: 0.9375
- Sum of 7 on 2 dice: approximately 0.1667
Step 11: Write your conclusion using Markdown
Click + Markdown and enter:

### Conclusion

The practical demonstrated how to generate sample spaces using Python's itertools.product function. Three coins produce 8 possible outcomes, four coins produce 16 outcomes, and two dice produce 36 outcomes.

The probability of getting at least one head when tossing three coins is 0.875 using both the direct and compleme# statistics
explanation of stat
