This repository contains the materials for the submission 'Introducing Information Retrieval for Biomedical Informatics Students' presented at the Fifth Workshop on Teaching NLP @ NAACL 2021.  

## Getting started

### Prerequisites
* Clone the repository
* Create a Python virtual environment or conda environment with python=3.8

### Install packages
* Using the requirements file available [here](https://github.com/sanyabt/bioinf_teachingNLP/blob/main/requirements.txt), run the following command to install all packages and dependencies in the Python environment.

```python -m pip install -r requirements.txt```

or

```conda create --name <envname> --file requirements.txt```

* NLTK data download with interactive installer

In a Python shell, run

```python
>>> import nltk
>>> nltk.download()
```
Once the NLTK Downloader window opens, select 'All packages' in the Collections tab and click Download. For more information, see [nltk.org](https://www.nltk.org/data.html)

### Running the notebooks


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
