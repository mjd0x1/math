

### Basic Probability ###


1) There is a group of 13 people who run a race. 

   
    *  How many possibilities are there for the race.
     *   How many possibilities are there for people to place, ie finish 1st, 2nd or 3rd
     * If there 8 people from the UK, how many combinations of at least one UK person placing.

    &nbsp;   
  
    
    There are 

    $$13!$$

    Permutations of the entire race,  and 

    $$13 \times 12 \times 11 $$

    Permutations of 1st, 2nd and 3rd place.

    For placing, we're not concerned about order 

    $${13\choose 3}$$

    There are 5 non UK runners so permutations involving no UK runners are

    $$5 \times 4 \times 3 $$

    Therefore at permutations involving at least one runner are  
    
    $$13 \times 12 \times 11 - 5 \times 4 \times 3 $$


2) How many 5 letter words contain at least 1 vowel

    There are 21 consonants, so

    $$21^5$$ 

     Have no vowels, therefore

    $$26^5  - 21^5$$ 

    Have at least 1 vowel


3)  How many 5 letter words have at least one repeated letter

    There are 

    $$26 \times 25 \times 24 \times 23 \times 22 $$

    words with unique letters so:

    $$26^5 -  26 \times 25 \times 24 \times 23 \times 22 $$

    words with at least one duplicate.

4)  How many 5 letter words have exactly 2 repeated letters

???

5) How many 3 digit numbers are odd

    Need to reverse and consider the last digit first

    Last digit can be 

    $$[1,3,5,7,9] $$

    1st digit cannot be zero,  so answer is

    $$ 9 \times 10 \times 5 = 450 $$


6) Toss 8 dice,  how many
    *   outcomes with repetition e.g 6,1,6...
    *  outcomes without repetition e.g 1,6

    For with repetition

    $$6^8$$
    For without recognise that with 8 dice the best case is 6 unique and 2 duplicates

    $$[1,1,2,3,4,5,6,6]$$

    Therefore

    $$[1,1, |, 2, |, 3, |, 4, |, 5, | ,6,6]$$

    There are always 5 partitions, so the problem reduces to finding the permutation indices of the partitions, so

    $${13\choose 5}$$









7)  There are 20 different cakes in a shop, and I wish to purchase 10 how many outcomes

    *  If each type selected are unique
    *   if each type selected are not unique  

    If unique then 

    $${20 \choose 10} $$


    If not unique then,  in general, select the first cake but then add that cake back into the selection set and continue until done. So if the 1st cake is picked, that cake is added back up to the 9th cake. The 10th cake doesn't add back because we're finished. So

    $${20 + 9\choose 10}$$

8)  Flip a fair coin 10 times, what's the probability of between 4 and 6 heads.

    Note the binomial distribution, for k= 4,5,6

    $$P(X=k) = {n\choose k} p^k (1-p)^{n-k}$$

    $$=\frac12^{10}({10\choose4}+{10\choose5}+{10\choose6})$$



9)  Toss 3 dice. What is the probability of: 
    *  Exactly 3 sixes
    *  No sixes
    *  At least one six
    *  Exactly one six  
    *  Two of a kind
    
    
    Exactly 3 sixes has only 1 occurance

    $$\frac1{6^3}$$

    No sixes means every die must show 1-5

    $$(\frac56)^3$$

    At least one 6, then we simply complement the no sixes

    $$1- (\frac56)^3$$

    Exactly one six, we have 5 numbers in remaining 2 dice and 3 different positions of the 6

    $$\frac{5\times 5 \times 3}{6^3} $$

    Two of a kind,  consider exactly 2 sixes. Patterns are [6,6,x],[6,x,6] and [x,6,6] where x has 5 combinations.

    $$\frac{5\times 3}{6^3}  $$   

    Then 2 of a kind has 6 different ways

    $$\frac{6 \times 5\times 3}{6^3}  $$ 

10)  For a 5 card hand
*   What's the probability of all cards being same suit?

    For example hearts, there are 13 cards then multiply by 4 for other suits
    
    $$\frac{4\times {13 \choose 5}}{52\choose5}$$


*   What's the probability of 4 of a kind?

    For example 4 * Ace,  there is only 1 way of getting 4 of a kind from 4 8s say and remaining card must be one of the other 48 left. Then there are 13 ways across all card values.

    $$\frac{13\times 48}{52\choose5}$$


*   What's the probability of a full house?

    We need to combine 3 of a kind with a pair and note that there are 13 x 12 combinations of the values

    $$\frac{13\times 12 \times{4\choose3}\times{4\choose2}}{52\choose5}$$


11) There are 2 types of people in population A, B and these people are tall/short.  20% of the population are A. 90% of A are tall.  40% of B are tall. You see a person and can see they are tall, what is the probability they are type A.


    Work in absolute probability. Calculate all the Tall people then look for the subset inside that of A/Tall people Probability required is

    $$\frac{A \cap Tall}{Total \ Tall \ People}$$
    
    Where x is the total population.

    $$\frac{0.9\times0.2\times x}{0.8\times0.4\times x +0.2\times0.9\times x}$$



## Geometric Distribution ##

Is Memoryless

$$ E(X | X > k) = E(X) + k $$

For example, what is the expected value?

$$ E(X) = p . 1 + (1 - p). E(X | X > 1) $$

Either we have success on the first observation or else we reset the expectation beyond the first observation

$$ E(X) = p.1 + (1-p) . (E(X) + 1) $$

$$ E(X) = 1/p $$

How many coin tosses to get 2 successive heads?

$$ E(X) = 2 + 1/2 . 1 + 1/2 . (E(X) + 1) $$

$$ E(X) = 6 $$

How many coin tosses to get 3 successive heads

$$ E(X) = 6 + 1/2 . 1 + 1/2 . (E(X) + 1) $$
$$ E(X) = 14 $$


## Markov ##

We can define the transition matrix as follows.  With 3 states Z, H, HH the last is an absorbing state:


$$
\begin{bmatrix}
1/2 & 1/2 & 0\\
1/2 & 0 & 1/2\\
0 & 0 & 1\\
\end{bmatrix}
$$

Calculate the fundamental matrix

$$ N = (I - Q)^{-1} $$

The i,j entry gives the number of times it is transient state j given it starts in transient state j

Therefore if we sum the zero row, ie add the number of times it is in state zero, state h, we will get the expectation of the absorbing state HH

N = 6

Extending for 3 consecutive heads

$$
\begin{bmatrix}
1/2 & 1/2 & 0 & 0\\
1/2 & 0 & 1/2 & 0\\
1/2 & 0 & 0 & 1/2\\
0 & 0 & 0 & 1\\
\end{bmatrix}
$$

N  = 14

```python
import numpy as np


Q = np.array([[0.5, 0.5,0],
              [0.5,0,0.5],
              [0.5,0,0]])

I = np.identity(3)
N = np.linalg.inv(I - Q)

```

## Markov Expectation Approach ##

Rather than using the transition matrix we can also use Markov on expectations themselves. 

In the example to get 2 consecutive Heads.

E(Z),E(H),E(HH)

are the expectations of getting two heads starting in states Z, H, HH

 From state zero we either stay in state Z which incurs a further E(Z) tosses or we move to state H which will incur further E(H) tosses. In both cases we increment the expectation by 1 as we used up the toss in moving to the state

$$ E(Z) =  1/2 . (E(Z) + 1) + 1/2 . (E(H) + 1) $$

$$ E(H) =  1/2 . (E(Z) + 1) + 1/2 . (E(HH) + 1)$$

Once we're in state HH we're finished so no count

$$ E(HH) = 0 $$

Solving gives E(Z) = 6

## Djikstras Algorithm ##

Calculate the shortest path in a graph.  For example given an adjency matrix

$$
\begin{bmatrix}
3 & 2 & 1\\
0 & 1 & 1\\
9 & 0 & 1\\
\end{bmatrix}
$$

We calculate the shortest path from [0,0] to [2,2]

Which is 3 -> 0 -> 1 -> 0 -> 1 = 5

Pseudocode Algorithm:

```
directions = [N,S,E,W]
minimum_cost = array(3,3) initialised to .inf
visited = array(3,3) boolean

set nodes =[(0,0)]
while nodes ! empty:
    initialise current_nodes
    for each n in nodes:
        set n = visited
        for each direction:
            d = calculate distance from n to each neighbour 
            if d < minimum_cost[n]:
                minimum_cost[n] = d
            if each neighbour is not visited then add to current_nodes

    make current_nodes unique and sort by minimum distances
    set nodes = current_nodes
```


    







 