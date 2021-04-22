This repository contains the materials for the submission 'Introducing Information Retrieval for Biomedical Informatics Students' presented at the Fifth Workshop on Teaching NLP @ NAACL 2021.  

## Getting started

### Prerequisites
* Clone the repository
* Create a Python virtual environment or conda environment with python=3.8
* Download and unzip the fine tuned models in files [clinBertFineTunedMedNLI](https://pitt-my.sharepoint.com/:u:/g/personal/rdb20_pitt_edu/ERtr_i2399RAsCayQ1WBfj8BXqs66w3fiHQ67xvG6k_aSw) and [BertCasedFineTunedMedNLI](https://pitt-my.sharepoint.com/:u:/g/personal/rdb20_pitt_edu/ETgDk3QZimNKv3SW5eTWTfIBmDkn_f3LzMUhwHVa4KElsw). These are used in [Notebook 3](https://github.com/dbmi-pitt/bioinf_teachingNLP/blob/master/notebooks/Information%20Retrieval%20-%20NLP%20Part%20III%20BERT.ipynb).

### Install packages
* **Using the requirements file available [here](https://github.com/dbmi-pitt/bioinf_teachingNLP/blob/master/requirements.txt), run the following command to install all packages and dependencies in the Python environment.**

1. Default Python install 

    ```python -m pip install -r requirements.txt```

2. Python virtual environment

    a. Install virtualenv
        ```python -m pip install --user virtualenv```

    b. Create venv with <env_name>
        MacOs and Linux
        ```python -m venv <env_name>```

        Windows
        ```py -m venv <env_name>```

    c. Activate venv and install requirements.txt
        ```source <env_name>/bin/activate```

        ```python3 -m pip install --user virtualenv```

3. Conda virtual environment
    ```conda create -n <env_name> python=3.7```
    ```conda activate <env_name>```
    ```python -m pip install -r requirements.txt```

All data required for the NLTK section will be downloaded, but to download more 
NLTK data. 

* **NLTK data download with interactive installer**

In a Python shell, run

```python
>>> import nltk
>>> nltk.download()
```
Once the NLTK Downloader window opens, select 'All packages' in the Collections tab and click Download. For more information, see [nltk.org](https://www.nltk.org/data.html)

* **word2vec as a service**

[Notebook 2](https://github.com/dbmi-pitt/bioinf_teachingNLP/blob/master/notebooks/Information%20Retrieval%20-%20NLP%20Part%20II%20Word%20Embedding.ipynb) uses word2vec service through a Docker container to create word embeddings. To set up -

1. Clone the Github repository https://github.com/vampolo/word2vec-service.git 
2. Change into the word2vec-service folder 
3. Run ```sudo docker-compose up -d```

### Running the notebooks
All notebooks can be executed using Jupyter notebook or JupyterLab in the Python environment. For more details on how instructors can set up the notebooks as assignments, see below.

## For instructors

## Troubleshoot

If nltk.download() gives error "SSL: CERTIFICATE_VERIFY_FAILED", run the following commands in the Python shell:
```python
import nltk
import ssl

try:
    _create_unverified_https_context = ssl._create_unverified_context
except AttributeError:
    pass
else:
    ssl._create_default_https_context = _create_unverified_https_context

nltk.download()
```

## Citation/License
