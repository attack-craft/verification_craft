This repository contains the codes for verifying the distinguishers of CRAFT (https://tosc.iacr.org/index.php/ToSC/article/view/7396). The verified distinguishers are listed as follows:

- A 6-round single-key differential distinguisher  (`verification_6r.cpp`)
- An 8-round single-key differential distinguisher  (`verification_8r.cpp`)
- A 10-round single-key differential distinguisher  (`verification_6r.cpp`)
- A 12-round single-key differential distinguisher (verified with GUP accelerated computing, see `cuda_verification.cu`)
- A 14-round single-key differential distinguisher (verified with GUP accelerated computing, see `cuda_verification.cu`)
- A 16-round experimental differential distinguisher (see `cuda_verification.cu`, and the program is still running to test more data)


- A 8-round weak-key differential characteristics  (`cuda_verification_afa---afa(8r).cu`)
- A 2-round weak-key differential characteristics  (`x_16---x_18.cpp`)



For *r* in {6, 8}, the experimental probability for an *r*-round distinguisher is obtained as follows. First, we set the tweak to satisfy the required conditions of the distinguisher, then compute the probabilities of the distinguishers for several randomly chosen keys, and the average probability is used as the experimental probability. For *r* = 10, we only perform the experiment for four randomly chosen keys.

For r in {12, 14, 16}, due to the high complexity, the experiment is only performed for one randomly chosen key.

We also implement Algorithm 1 in the submitted paper for a 7-round distinguisher and try to recovery one nibble of the secret key (`recover_knibble.cpp`). 

