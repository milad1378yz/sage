# SAGE: Symbolic Acceleration via Generative Evolution

Code for the paper **[LLM-Guided Evolution of Symbolic Acceleration Inequality Families for MILP](https://openreview.net/forum?id=rxJvINT074)**, published in *Transactions on Machine Learning Research* (TMLR), 2026.

SAGE uses LLM agents guided by evolutionary search to discover reusable acceleration inequality families for a symbolic MILP formulation. The discovered families are instantiated for each problem instance and appended to the model before solving.

## Installation

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Python 3.9 is recommended. A licensed MILP solver (e.g., [Gurobi](https://www.gurobi.com/)) is required.

## Configuration

In [`configs/`](./configs), copy each file whose name contains `_template`, remove `_template` from the copy's name, and fill in your credentials and hyperparameters.

## Data Preparation

```bash
python data/data_prepare_<problem>.py
```

Replace `<problem>` with one of the scripts in [`data/`](./data) (e.g., `tsp`, `cwlp_rand`).

## Usage

Run SAGE:

```bash
python src/main.py <args>    # see `python src/main.py -h`
```

Check the optimal solution preservation rate of the discovered inequalities:

```bash
python experiments/optimal_solution_preservation_cuts.py <args>
```

Evaluate on held-out instances:

```bash
python experiments/evaluate_cut.py <args>
```

## Citation

```bibtex
@article{
  yazdani2026llmguided,
  title={{LLM}-Guided Evolution of Symbolic Acceleration Inequality Families for {MILP}},
  author={Milad Yazdani and Mahdi Mostajabdaveh and Samin Aref and Zirui Zhou},
  journal={Transactions on Machine Learning Research},
  issn={2835-8856},
  year={2026},
  url={https://openreview.net/forum?id=rxJvINT074},
  note={}
}
```
