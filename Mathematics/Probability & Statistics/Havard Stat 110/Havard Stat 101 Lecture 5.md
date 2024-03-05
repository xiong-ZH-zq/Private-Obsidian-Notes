---
date_creation: 2024-02-01
type: video_note
url: https://www.youtube.com/watch?v=JzDvVgNDxo8&list=PL2SOU6wwxB0uwwH80KTQ6ht66KWxbzTIo&index=5
tags: 
---
# Conditioning Continued, Law of Total Probability
## Law of Total Probability
>[!note] Theorem: Law of Total Probability
>Choose a partition of event $A$ : $A_1,\cdots,A_n$. Then $P(B)$ can be written as:
>$$P(B) = \sum\limits_{i=1}^n P(B|A_i)P(A_i)$$

### An example
Get random 2 cards from standard deck. Compute the probability below:
[14:20](https://www.youtube.com/watch?v=JzDvVgNDxo8&list=PL2SOU6wwxB0uwwH80KTQ6ht66KWxbzTIo&index=5#t=860.630911038147) 
$$
P(\text{both aces}| \text{have Ace of Spades})
$$

### Sickness Model
[18:27](https://www.youtube.com/watch?v=JzDvVgNDxo8&list=PL2SOU6wwxB0uwwH80KTQ6ht66KWxbzTIo&index=5#t=1107.875849061035) 
Patient gets tested for disease afflicts 1% of population. Suppose test is advertised as "95% accurate". If the patient tested positive, what is the probability that he really has disease?

Define $D$ to be the event "The patient **has disease**". And let $T$ be "Patients tests **positive**".

"95% accurate" means when the patient has a disease and the patient tests positive, it is accurate.

So now we know $P(T|D) = 0.95 = P(\overline{T}|\overline{D})$, $P(D) = 0.01$ and we should calculate $P(D|T)$ .

Use Bayes Rule that we can get
$$
P(D|T) = \dfrac{P(T|D)P(D)}{P(T)}
$$
Then apply Law of Total Probability:
$$
\begin{aligned}
P(D|T) &= \dfrac{P(T|D)P(D)}{P(T|D)P(D)+P(T|\overline{D})P(\overline{D})} \\
&= \dfrac{0.0095}{0.0095+0.99\times 0.05} \\
&\approx 0.16 
\end{aligned}
$$
## Common Mistakes
[33:22](https://www.youtube.com/watch?v=JzDvVgNDxo8&list=PL2SOU6wwxB0uwwH80KTQ6ht66KWxbzTIo&index=5#t=2002.14659) 
Biohazard:
1. Confusing about $P(A|B)$ and $P(B|A)$. ("Prosecutor's Fallacy")
2. Confusing $P(A)$ and $P(A|B)$ . (Prior and Posterior)
3. Confusing independence and conditional independence.
### Conditional Independence
>[!note] Definition: Conditional Independence
>Events $A,B$ are conditionally independent when given $C$ if 
>$$P(AB|C) = P(A|C)P(B|C)$$

So what is the relation between **Independent** and **Conditionally Independent**? Actually they have no relations.




