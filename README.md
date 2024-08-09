# TabRepo

For an official introduction to TabRepo, check the README.md file in the main branch of this repository. This 
README.md file is concerned with running experiments using the modified TabRepo and AutoGluon repositories 
that allow the user to customize the ensemble selection method used when building ensemble models. 

Changes made to the TabRepo repository include a parameter in the evaluate_ensemble() and
a parameter in the experiment functions in the baselines.py file in the tabrepo/scripts/baseline_comparison
folder. Also, a new file evaluate_baselines_phem.py to run experiments specifically pertaining to the PHEM
methods. 

Changes made to the AutoGluon repository include a class that contains the logic for all the different 
ensemble selection methods and fits the ensemble model based on the ensemble selection method specified
by the user. 
 
## Installation

To install the tabrepo repository with the necessary changes, ensure you are using Python 3.9-3.11. Other Python versions are not supported. 
Then, run the following:

```bash
git clone --single-branch --branch cmaes_method https://github.com/alee4977/tabrepo.git
pip install -e tabrepo
```

Similarly, execute the same commands for AutoGluon. The following will do a source install of AutoGluon:
```bash
pip install -U pip
pip install -U setuptools wheel

git clone --single-branch --branch cmaes_method https://github.com/alee4977/autogluon.git
cd autogluon && ./full_install.sh
```

Finally, pip install the PHEM repository with the following command. This repository has PHEM method implementations that are used when the 
user specifies the specific ensemble selection method they want to use in TabRepo. 
```bash
pip install git+https://github.com/LennartPurucker/phem
```

## Quick-start
To run experiments using different ensemble selection methods, run:
```bash
python scripts/baseline_comparison/evaluate_baselines_phem.py
```
These are the same experiment as in the TabRepo paper, but with different ensemble selection methods used to run the experiments. 
