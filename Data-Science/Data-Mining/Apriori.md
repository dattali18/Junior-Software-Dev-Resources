# Apriori

The Apriori algorithm is a popular algorithm used in data mining for association rule learning. It is used to discover interesting relationships (associations) between variables in large databases. The algorithm is based on the concept of "frequent itemsets," which are sets of items that frequently occur together in transactions. 

### Principle of the Apriori Algorithm

The Apriori algorithm works in two phases:

1. **Generating Candidate Itemsets:**
   - Initially, individual items in the database are considered as itemsets of size 1.
   - Then, the algorithm iteratively generates itemsets of larger sizes by joining pairs of itemsets that meet a minimum support threshold.
   - The support of an itemset is the proportion of transactions in the database in which the itemset appears.

2. **Finding Frequent Itemsets:**
   - After generating candidate itemsets, the algorithm scans the database to count the support of each candidate itemset.
   - Itemsets that meet a minimum support threshold are considered frequent itemsets.

3. **Generating Association Rules:**
   - Once frequent itemsets are found, the algorithm generates association rules from these itemsets.
   - An association rule is a relationship between two sets of items, represented as $X \rightarrow Y$, where $X$ is the antecedent (or left-hand side) and $Y$ is the consequent (or right-hand side) of the rule.
   - The confidence of an association rule $X \rightarrow Y$ is the proportion of transactions that contain $X$ which also contain $Y$.

### Example

Let's consider a simple example with a list of transactions:

| Transaction ID | Items Purchased       |
|----------------|-----------------------|
| 1              | Bread, Milk           |
| 2              | Bread, Diapers, Beer  |
| 3              | Milk, Diapers, Eggs   |
| 4              | Milk, Diapers, Beer   |
| 5              | Bread, Milk, Diapers  |

We want to find frequent itemsets with a minimum support of 40%.

```python
from mlxtend.frequent_patterns import apriori, association_rules
import pandas as pd

# Create a dataframe of transactions
data = {'Transaction ID': [1, 2, 3, 4, 5],
        'Items Purchased': [['Bread', 'Milk'],
                             ['Bread', 'Diapers', 'Beer'],
                             ['Milk', 'Diapers', 'Eggs'],
                             ['Milk', 'Diapers', 'Beer'],
                             ['Bread', 'Milk', 'Diapers']]}
df = pd.DataFrame(data)

# Transform the dataframe into a one-hot encoded format
one_hot_encoded = df['Items Purchased'].str.join('|').str.get_dummies()

# Find frequent itemsets with minimum support of 40%
frequent_itemsets = apriori(one_hot_encoded, min_support=0.4, use_colnames=True)

# Generate association rules
rules = association_rules(frequent_itemsets, metric='confidence', min_threshold=0.7)

print("Frequent Itemsets:")
print(frequent_itemsets)
print("\nAssociation Rules:")
print(rules)
```

In this example, we first convert the transaction data into a one-hot encoded format. Then, we use the Apriori algorithm to find frequent itemsets with a minimum support of 40%. Finally, we generate association rules with a minimum confidence of 70%.

## Running Example 

Let's walk through the Apriori algorithm step by step using the example transactions and a minimum support of 40%.

### Step 1: Initial Transactions

| Transaction ID | Items Purchased       |
|----------------|-----------------------|
| 1              | Bread, Milk           |
| 2              | Bread, Diapers, Beer  |
| 3              | Milk, Diapers, Eggs   |
| 4              | Milk, Diapers, Beer   |
| 5              | Bread, Milk, Diapers  |

### Step 2: One-Hot Encoding

We convert the transactions into a one-hot encoded format, where each column represents an item and each row represents a transaction.

| Transaction ID | Bread | Milk | Diapers | Beer | Eggs |
|----------------|-------|------|---------|------|------|
| 1              | 1     | 1    | 0       | 0    | 0    |
| 2              | 1     | 0    | 1       | 1    | 0    |
| 3              | 0     | 1    | 1       | 0    | 1    |
| 4              | 0     | 1    | 1       | 1    | 0    |
| 5              | 1     | 1    | 1       | 0    | 0    |

### Step 3: Finding 1-Itemsets

Calculate the support for each item (1-itemset):

- Bread: 3/5 = 0.6
- Milk: 4/5 = 0.8
- Diapers: 4/5 = 0.8
- Beer: 2/5 = 0.4
- Eggs: 1/5 = 0.2

Since we have a minimum support of 40%, only Bread, Milk, and Diapers are frequent 1-itemsets.

### Step 4: Finding 2-Itemsets

Generate candidate 2-itemsets by joining frequent 1-itemsets:

- {Bread, Milk}: Check if {Bread} and {Milk} are frequent 1-itemsets, which they are.
- {Bread, Diapers}: Check if {Bread} and {Diapers} are frequent 1-itemsets, which they are.
- {Milk, Diapers}: Check if {Milk} and {Diapers} are frequent 1-itemsets, which they are.

Calculate the support for each candidate 2-itemset:

- {Bread, Milk}: 2/5 = 0.4
- {Bread, Diapers}: 3/5 = 0.6
- {Milk, Diapers}: 3/5 = 0.6

Since all candidate 2-itemsets have a support of at least 40%, all of them are frequent 2-itemsets.

### Step 5: Generating Association Rules

Generate association rules from the frequent itemsets:

- {Bread, Milk} -> {Diapers}
- {Bread, Diapers} -> {Milk}
- {Milk, Diapers} -> {Bread}

### Step 6: Output

The output of the Apriori algorithm would be the frequent itemsets and the generated association rules, as shown below:

#### Frequent Itemsets:
| Itemset       | Support |
|---------------|---------|
| {Bread}       | 0.6     |
| {Milk}        | 0.8     |
| {Diapers}     | 0.8     |
| {Bread, Milk} | 0.4     |
| {Bread, Diapers} | 0.6  |
| {Milk, Diapers} | 0.6   |

#### Association Rules:
| Rule                   | Support | Confidence |
|------------------------|---------|------------|
| {Bread} -> {Milk}      | 0.4     | 2/3 (0.67) |
| {Milk} -> {Bread}      | 0.4     | 1/2 (0.50) |
| {Bread} -> {Diapers}   | 0.6     | 1.0        |
| {Diapers} -> {Bread}   | 0.6     | 3/4 (0.75) |
| {Milk} -> {Diapers}    | 0.6     | 3/4 (0.75) |
| {Diapers} -> {Milk}    | 0.6     | 3/4 (0.75) |

These tables show the frequent itemsets and association rules found by the Apriori algorithm for the given dataset and minimum support threshold.

## Rule Generating 

Certainly! Generating association rules from frequent itemsets involves finding all possible combinations of items in the itemset and creating rules based on these combinations. 

Let's consider a frequent itemset $F$ with $k$ items: $F = \{item_1, item_2, ..., item_k\}$.

To generate association rules from $F$, we need to consider all possible non-empty subsets of $F$. Each subset will be the antecedent of a rule, and the remaining items will be the consequent.

For example, if $F$ contains items $A$, $B$, and $C$, the possible rules would be:

1. $A, B \rightarrow C$
2. $A, C \rightarrow B$
3. $B, C \rightarrow A$
4. $A \rightarrow B, C$
5. $B \rightarrow A, C$
6. $C \rightarrow A, B$

In general, the number of rules that can be generated from an itemset with $k$ items is $2^k - 2$, as we exclude the empty set and the full itemset itself.

### Mathematically

Let $X$ be a subset of $F$ with $m$ items, and let $Y$ be the complement of $X$ in $F$ (i.e., $Y = F - X$). The association rule generated from $X$ and $Y$ would be $X \rightarrow Y$.

The support of the rule is calculated as the support of the union of $X$ and $Y$ divided by the total number of transactions.

$$
\text{support}(X \rightarrow Y) = \frac{\text{support}(X \cup Y)}{\text{total number of transactions}}
$$

The confidence of the rule is calculated as the support of the union of $X$ and $Y$ divided by the support of $X$.

$$
\text{confidence}(X \rightarrow Y) = \frac{\text{support}(X \cup Y)}{\text{support}(X)}
$$

### Example

Let's say we have a frequent itemset $F$ with items $A$, $B$, and $C$, and we want to generate association rules from this itemset.

1. Calculate support for each item: $\text{support}(A)$, $\text{support}(B)$, $\text{support}(C)$
2. Calculate support for each pair of items: $\text{support}(A, B)$, $\text{support}(A, C)$, $\text{support}(B, C)$
3. Calculate support for each triple of items: $\text{support}(A, B, C)$
4. Generate rules using the above formulae for support and confidence.

This process is repeated for all frequent itemsets to generate association rules.

Once the Apriori algorithm has found all frequent itemsets, it generates association rules from these itemsets. Here's how it works:

1. **Generate Association Rules:** For each frequent itemset $F$ with more than one item, the algorithm considers all possible non-empty subsets $X$ of $F$ ($\forall X\subset F, X\neq \emptyset$), as the antecedent of a rule, and the remaining items in $F$ as the consequent. This generates candidate rules of the form $X \rightarrow (F - X)$.

2. **Calculate Confidence:** For each candidate rule $X \rightarrow (F - X)$, the algorithm calculates the confidence of the rule as the support of $F$ divided by the support of $X$. The support of $F$ is the proportion of transactions that contain all the items in $F$, and the support of $X$ is the proportion of transactions that contain all the items in $X$.

3. **Filter Rules:** The algorithm filters out rules that do not meet the minimum confidence threshold set by the user. If the confidence of a rule is below the threshold, the rule is discarded.

4. **Output:** The algorithm outputs the remaining rules, which are the association rules that meet the minimum confidence threshold.

Here's a simplified example to illustrate this process:

- Suppose we have a frequent itemset $F$ with items $A$, $B$, and $C$.
- The algorithm generates the following candidate rules: $A \rightarrow (B, C)$, $B \rightarrow (A, C)$, and $C \rightarrow (A, B)$.
- For each candidate rule, the algorithm calculates the confidence. For example, for the rule $A \rightarrow (B, C)$, the confidence is calculated as the support of $A, B, C$ divided by the support of $A$.
- If the confidence of a rule is below the minimum threshold, the rule is discarded. Otherwise, it is considered a valid association rule.

By generating association rules in this way, the Apriori algorithm ensures that each rule satisfies the downward closure property and meets the minimum confidence threshold, making the rules more meaningful and useful for analysis.