# GPU Monte Carlo Tree Search with MPI

# TL;DR
###### Solves checkers/reversi (why didn't I do GO?)
###### Includes **self-play**

<img src="http://olab.is.s.u-tokyo.ac.jp/~kamil.rocki/tree.png" width="200" /> <img src="http://olab.is.s.u-tokyo.ac.jp/~kamil.rocki/research/mcts.png" width="300" />

###### Runs on GPU (CUDA) or CPU (C++)

![alt text](http://olab.is.s.u-tokyo.ac.jp/~kamil.rocki/research/phd_3.png "REVERSI")

###### Over 1 million game simulations/second on a single 8 year old 280 GTX GPU.

###### GPU version is quite efficient actually ( here is the score advantage plotted on the y-axis vs time, playing againt a single-core CPU)

<img src="http://olab.is.s.u-tokyo.ac.jp/~kamil.rocki/research/score.png" width="600" />

###### Scales up nicely using MPI to a large distributed system (tested on a 2048-node supercomputer, up to 3.5M GPU threads)

<img src="http://olab.is.s.u-tokyo.ac.jp/~kamil.rocki/research/phd_4.png" width="600" />

###### Has a very minimal ssh-friendly interface

<img src="http://olab.is.s.u-tokyo.ac.jp/~kamil.rocki/research/mcts_git.gif" width="400" />

# I used this code while working on my PhD thesis. The MPI version has been tested on the Japanese TSUBAME supercomputer.
### THESIS + BIBTEX
[Thesis](http://olab.is.s.u-tokyo.ac.jp/~kamil.rocki/phd_thesis.pdf)
[Slides](http://olab.is.s.u-tokyo.ac.jp/~kamil.rocki/gpu_mcts_slides.pdf)

```
@phdthesis{rocki2011large,
  title={Large Scale Monte Carlo Tree Search on GPU},
  author={Rocki, Kamil Marek},
  year={2011},
  school={School of Information Science and Technology, The University of Tokyo}
}
```

# CAUTION:
Formatting needs to fixed. This code has been tested in 2010 on CUDA 3.0, so anything is possible.

# some background
As a PhD student I was a member of ULP-HPC (Ultra Low-Power, High-Performance Computing via Modeling and Optimization of Next Generation HPC Technologies) project. My PhD dissertation described a very effective parallelization scheme a novel, approximate Monte Carlo Tree Search (MCTS) algorithm. It is a method for making optimal decisions in artificial intelligence (AI) problems, typically move planning in combinatorial games. It combines the generality of random simulation with the precision of tree search. I have thoroughly investigated the problems related to parallelizing the algorithm and successively implemented a parallel multi-GPU version of the MCTS algorithm using CUDA on the TSUBAME 2.0 supercomputer. I was able to scale it up to 256 GPUs and 2048 CPUs showing tremendous improvement over the sequential program or any other existing work at that time. 

# more details in the thesis
