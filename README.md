# Control-System
Notes on control system (Renamed)

## PNAS 2019: Data-driven discovery of coordinates and governing equations
An interesting paper that uses DNN-Autoencoder to find the intrinsic vector (non-linear dimension rotation) for system identification (SinDy). 
Approach: Joint optimisation. 

Video Link: https://www.youtube.com/watch?v=WHhDgxkiR9c

Idea1: The autoencoder can be realised at the edge while the system identification can be realised at the cloud. 

Idea2: Maybe it can be extended to support multi-agent cases? 

Idea3: Use it on speech synthesis with GAN to guarantee speech quality.

Performance, the performance of this paper is trivial, not accurate. 

NOTE: This is different from RL. RL is to solve a task. This is about system identification. Maybe the identified system can better help solve a MDP problem. 
