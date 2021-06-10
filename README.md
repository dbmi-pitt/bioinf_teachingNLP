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

2. If creating new Python virtual environment:

* a. Install virtualenv

    ```python -m pip install --user virtualenv```

* b. Create venv with <env_name>
    * MacOs and Linux

    ```python -m venv <env_name>```
        
    * Windows

    ```py -m venv <env_name>```

* c. Activate venv and install requirements.txt

    ```python
    source <env_name>/bin/activate
    python3 -m pip install --user virtualenv
    ```

3. Conda virtual environment

    ```python
    conda create -n <env_name> python=3.7
    conda activate <env_name>
    python -m pip install -r requirements.txt
    ```

* **NLTK data download with interactive installer**

All data required for the NLTK code will be downloaded in the notebooks. To download rest of the NLTK data (optional), run the following in a Python shell:

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
All notebooks can be executed using Jupyter notebook or JupyterLab in the Python environment with the above setup instructions.

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
```
@inproceedings{taneja-etal-2021-introducing,
    title = "Introducing Information Retrieval for Biomedical Informatics Students",
    author = "Taneja, Sanya  and
      Boyce, Richard  and
      Reynolds, William  and
      Newman-Griffis, Denis",
    booktitle = "Proceedings of the Fifth Workshop on Teaching NLP",
    month = jun,
    year = "2021",
    address = "Online",
    publisher = "Association for Computational Linguistics",
    url = "https://www.aclweb.org/anthology/2021.teachingnlp-1.16",
    pages = "96--98",
    abstract = "Introducing biomedical informatics (BMI) students to natural language processing (NLP) requires balancing technical depth with practical know-how to address application-focused needs. We developed a set of three activities introducing introductory BMI students to information retrieval with NLP, covering document representation strategies and language models from TF-IDF to BERT. These activities provide students with hands-on experience targeted towards common use cases, and introduce fundamental components of NLP workflows for a wide variety of applications.",
}
```
