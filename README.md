This repository contains the codes for verifying the distinguishers of CRAFT (https://tosc.iacr.org/index.php/ToSC/article/view/7396). The verified distinguisher are listed as follows:

- A 6-round single-key differential distinguisher  (`verification_6r.cpp`)
- An 8-round single-key differential distinguisher  (`verification_8r.cpp`)
- A 10-round single-key differential distinguisher  (`verification_6r.cpp`)
- A 12-round single-key differential distinguisher (verified with GUP accelerated computing)
- A 14-round single-key differential distinguisher (verified with GUP accelerated computing)
- A 16-round experimental differential distinguisher (verified with GUP accelerated computing)

For *r* in {6, 8}, the experimental probability for an *r*-round distinguisher is obtained as follows. First, we set the tweak to satisfy the required conditions of the distinguisher, then compute the probabilities of the distinguishers for several randomly chosen keys, and the average probability is used as the experimental probability. For *r* = 10, we only perform the experiment for 4 randomly chosen keys.

For r in {12, 14, 16}, due to the high complexity, the experiment is only performed for one randomly chosen key.

We also implement the Algorithm 1 in the submitted paper for an x-round distinguisher and try to recovery one nibble of the secret key. We run this experiment (`*.cpp`) 10 times for 10 randomly chosen secret keys, and we never fail to recover `K[x]`.
