# Co-PSL: Controllable Expensive Multi-objective Optimization with warm-starting Bayesian Optimization

This anonymous repository serves as the implmentation code of manuscript "Controllable Expensive Multi-objective Optimization with warm-starting Bayesian Optimization", submitted into AAAI-24 with manuscript ID 13479. 

### Environment
This code is executed with the main libraries:

```
python==3.11.4
pymoo==0.6.0
numpy==1.18
matplotlib==3.7.2
torch==2.0.1
```

### Organization
The repository includes implementation code of the baseline ["PSL-MOBO"](https://arxiv.org/abs/2210.08495) and the poposed "Co-PLS" as follows:

- `mobo/`: library code for training and defining the surrogate model
- `result_weight/`: ablation studies results and performances results that are used for ploting figures in the manuscript
- `warmup_weight/`: contain the warm-starting solution weights on 6 testing problem run on DGEMO as the first phase of Co-PSL, with the total expensive evaluations are 220. For DTLZ2, we provide additional weights for ablation studies on warm-starting methods (between DGEMO and EHVI) and number of batch evaluation (5 and 10)
- `visualization_plot/`: all visualization plots used in the manuscript
- `lhs.py`: an efficient latin-hypercube design implementation, which is for generating initial solutions, derived from [PSL-MOBO](https://github.com/Xi-L/PSL-MOBO) repo
- `metrics.py`: metric for computing Mean Euclidean Distance
- `model.py`: a simple MLP model served as Pareto Set Model
- `partitioning.py`: code for sampling trade-off preference vectors
- `problem.py`: contains all test problems in MOO. However, in our manuscript, we only selected some exemplars.
- `run_PSL-MOBO.py`: main code for running the the baseline PSL-MOBO
- `run_Co-PSL.py`: main code for running the proposed Co-PSL

### Running:
All the code have been set to run on 6 problems as presented in the manuscript, one by one. The code should automatically generate a log folder for each problems for saving results. The execution commands are as follows:
```
python run_Co-PSL.py
python run_PSL-MOBO.py
```

### Acknowledgement

The repository is based on [PSL-MOBO repository](https://github.com/Xi-L/PSL-MOBO).
