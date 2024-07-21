# Homework 1

## Problem 1
(Exercise 1.1.4 in Durrett) Suppose $\mathcal{F}_1, \mathcal{F}_2, \ldots$ are $\sigma$-fields over a sample space $\Omega$, and suppose they are nested: $\mathcal{F}_1 \subseteq \mathcal{F}_2 \subseteq \ldots$ Prove that

$$
\bigcup_{n=1}^{\infty} \mathcal{F}_n
$$

is a field. Is it necessarily a $\sigma$-field?



## Problem 2
Let $\Omega$ be an infinite set. Let $\mathcal{F}$ denote the collection of all sets $E \subseteq \Omega$ such that either $E$ or $E^c$ is finite.

a) Is $\mathcal{F}$ a field? Prove that your answer is correct.
\
b) Is $\mathcal{F}$ a $\sigma$-field? Prove that your answer is correct.
## Solution

### (a) $\mathcal{F}$ is a field.

**Proof:** We will show that $\mathcal{F}$ satisfies the three properties of a field:

1. $\Omega \in \mathcal{F}$:
   The complement of $\Omega$ is $\emptyset$, which is finite. Therefore, $\Omega \in \mathcal{F}$.

2. Closure under complementation:
   Let $E \in \mathcal{F}$. By definition, either $E$ or $E^c$ is finite, which means either $E^c$  or $(E^c)^c$ is finite. 
   Therefore, $E^c \in \mathcal{F}$.

3. Closure under finite unions:
   Let $A, B \in \mathcal{F}$. We consider two cases:
   
   Case 1: If both $A$ and $B$ are finite, then $A \cup B$ is finite, so $A \cup B \in \mathcal{F}$.
   
   Case 2: If at least one of $A$ or $B$ is infinite, without loss of generality, assume $A$ is infinite. 
   Then $A^c$ is finite. We have:
   
   $(A \cup B)^c = A^c \cap B^c$
   
   Since $A^c$ is finite, $A^c \cap B^c$ is also finite. Therefore, $(A \cup B)^c$ is finite, 
   which implies $A \cup B \in \mathcal{F}$.

Thus, $\mathcal{F}$ satisfies all properties of a field. ∎

### (b) $\mathcal{F}$ is not necessarily a $\sigma$-field.

**Proof:** We will provide a counterexample to show that $\mathcal{F}$ is not closed under countable unions.

Let $\Omega = \mathbb{N}$, the set of all natural numbers. Define $E_k = \{2k\}$ for $k \in \mathbb{N}$.

1. Each $E_k \in \mathcal{F}$ because $E_k$ is finite (it contains only one element).

2. Consider $E = \bigcup_{k=1}^{\infty} E_k = \{2, 4, 6, 8, ...\}$, the set of all even natural numbers.

3. $E$ is infinite, and its complement $E^c = \{1, 3, 5, 7, ...\}$ (the set of all odd natural numbers) 
   is also infinite.

4. Therefore, $E \notin \mathcal{F}$, as neither $E$ nor $E^c$ is finite.

This demonstrates that $\mathcal{F}$ is not closed under countable unions, and thus is not a $\sigma$-field. ∎



## Problem 3
(Exercise 4.8 in Driver) Let $\Omega$ be a set, and let $\mathcal{E}_1, \mathcal{E}_2 \subseteq 2^\Omega$ be collections of subsets of $\Omega$. 
\
Show that $\sigma(\mathcal{E}_1) = \sigma(\mathcal{E}_2)$ if and only if $\mathcal{E}_1 \subseteq \sigma(\mathcal{E}_2)$ and $\mathcal{E}_2 \subseteq \sigma(\mathcal{E}_1)$. Give an example where $\sigma(\mathcal{E}_1) = \sigma(\mathcal{E}_2)$, but $\mathcal{E}_1 \neq \mathcal{E}_2$.

## Solution

**Proof of "only if" part:**

Suppose $\sigma(\mathcal{E}_1) = \sigma(\mathcal{E}_2)$. By definition of $\sigma$-algebra, $\mathcal{E}_1 \subseteq \sigma(\mathcal{E}_1) = \sigma(\mathcal{E}_2)$. Similarly, $\mathcal{E}_2 \subseteq \sigma(\mathcal{E}_1)$. Therefore, $\sigma(\mathcal{E}_1) = \sigma(\mathcal{E}_2)$.

**Proof of "if" part:**

Suppose $\mathcal{E}_1 \subseteq \sigma(\mathcal{E}_2)$ and $\mathcal{E}_2 \subseteq \sigma(\mathcal{E}_1)$. Since $\sigma(\mathcal{E}_1)$ is the smallest $\sigma$-algebra containing $\mathcal{E}_1$, and $\mathcal{E}_1 \subseteq \sigma(\mathcal{E}_2)$, we have $\sigma(\mathcal{E}_1) \subseteq \sigma(\mathcal{E}_2)$. Similarly, we have $\sigma(\mathcal{E}_2) \subseteq \sigma(\mathcal{E}_1)$. Therefore, $\sigma(\mathcal{E}_1) = \sigma(\mathcal{E}_2)$.

**Example:**

Let $\Omega = \{0, 1\}$. Consider the collections:
- $\mathcal{E}_1 = \{\emptyset, \{0\}, \Omega\}$
- $\mathcal{E}_2 = \{\emptyset, \{0\}, \{1\}, \Omega\}$

Here, $\sigma(\mathcal{E}_1) = \sigma(\mathcal{E}_2) = \{\emptyset, \{0\}, \{1\}, \Omega\}$, but clearly $\mathcal{E}_1 \neq \mathcal{E}_2$.



## Problem 4
(Exercise 4.9 in Driver) Verify that the Borel $\sigma$-field $\mathcal{B}(\mathbb{R})$ is generated by any of the following collections of intervals:

a) $\mathcal{E}_1 = \{(a, \infty): a \in \mathbb{R}\}$
\
b) $\mathcal{E}_2 = \{(a, \infty): a \in \mathbb{Q}\}$
\
c) $\mathcal{E}_3 = \{[a, \infty): a \in \mathbb{Q}\}$



## Problem 5
Let $(\Omega, \mathcal{F}, P)$ be a probability space, and suppose $A \in \mathcal{F}$ satisfies $P(A) > 0$. Define

$$
\mathcal{F}_A := \{B \in \mathcal{F}: B \subseteq A\}, \text{ and for } B \in \mathcal{F}_A \text{ define } P_A(B) = \frac{P(B)}{P(A)}.
$$

Prove that $(A, \mathcal{F}_A, P_A)$ is a probability space.

## Proof

We need to prove that $(A, \mathcal{F}_A, P_A)$ is a probability space. To do this, we will first show that $\mathcal{F}_A$ is a σ-algebra on $A$, and then demonstrate that $P_A$ is a probability measure on $\mathcal{F}_A$.

### Part 1: $\mathcal{F}_A$ is a σ-algebra on $A$

1) $A \in \mathcal{F}_A$:
   Since $A \subseteq A$ and $A \in \mathcal{F}$, we have $A \in \mathcal{F}_A$ by definition.

2) $\mathcal{F}_A$ is closed under complementation:
   Let $B \in \mathcal{F}_A$. We need to show that $B_A^c := A \setminus B \in \mathcal{F}_A$. We have
   $$B_A^c = A \setminus B = A \cap B^c$$
   Since $B \in \mathcal{F}$ and $\mathcal{F}$ is a σ-algebra, $B^c \in \mathcal{F}$.
   As $\mathcal{F}$ is closed under finite intersections, $A \cap B^c \in \mathcal{F}$.
   Besides, $A \cap B^c \subseteq A$. So by definition of $\mathcal{F}_A$, we have $B_A^c \in \mathcal{F}_A$.

3) $\mathcal{F}_A$ is closed under countable unions:
   Let $\{B_i\}_{i=1}^{\infty}$ be a countable collection of sets in $\mathcal{F}_A$.
   For each $i$, $B_i \in \mathcal{F}$ and $B_i \subseteq A$.
   Since $\mathcal{F}$ is a σ-algebra, $\bigcup_{i=1}^{\infty} B_i \in \mathcal{F}$.
   Moreover, $\bigcup_{i=1}^{\infty} B_i \subseteq A$ since each $B_i \subseteq A$.
   Therefore, $\bigcup_{i=1}^{\infty} B_i \in \mathcal{F}_A$.

Thus, $\mathcal{F}_A$ is a σ-algebra on $A$.

### Part 2: $P_A$ is a probability measure on $\mathcal{F}_A$

1) Non-negativity: For any $B \in \mathcal{F}_A$,
   $$P_A(B) = \frac{P(B)}{P(A)} \geq 0$$
   since $P(B) \geq 0$ and $P(A) > 0$.

2) Countable additivity: Let $\{B_i\}_{i=1}^{\infty}$ be a countable collection of disjoint sets in $\mathcal{F}_A$.
   Then,
   
   $$\begin{aligned}
   P_A(\bigcup_{i=1}^{\infty} B_i) &= \frac{P(\bigcup_{i=1}^{\infty} B_i)}{P(A)} \\
   &= \frac{1}{P(A)} \sum_{i=1}^{\infty} P(B_i) \quad \text{(by countable additivity of } P\text{)} \\
   &= \sum_{i=1}^{\infty} \frac{P(B_i)}{P(A)} = \sum_{i=1}^{\infty} P_A(B_i)
   \end{aligned}$$

3) Normalization: 
   $$P_A(A) = \frac{P(A)}{P(A)} = 1$$

Therefore, $P_A$ is a probability measure on $\mathcal{F}_A$.

Since $\mathcal{F}_A$ is a σ-algebra on $A$ and $P_A$ is a probability measure on $\mathcal{F}_A$, we conclude that $(A, \mathcal{F}_A, P_A)$ is indeed a probability space.