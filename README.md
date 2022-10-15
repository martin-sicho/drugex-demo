# De Novo Drug Design with DrugEx

This 'talktorial' will take us through a case study of generating novel chemical structures for compounds that could be of interest in the development of new ligands for the [Adenosine A2A receptor](https://www.uniprot.org/uniprotkb/P29274/entry) with a deep learning molecular generator, DrugEx. [DrugEx](https://github.com/CDDLeiden/DrugEx) uses multiple model architectures (from recurrent neural networks to transformers) to generate compounds of desired properties. It combines transfer learning, reinforcment learning and multiobjecetive optimization to drive chemical space exploration. In this tutorial, we will be using the simplest DrugEx model, which is based on recurrent neural networks (RNNs). You can find

## Google Colab

[![Open All Collab](https://colab.research.google.com/assets/colab-badge.svg)](https://githubtocolab.com/martin-sicho/drugex-demo)

You can run the notebooks in this repostiry via [Google Colab](https://colab.research.google.com/). You will just need to execute the following at the begining of each notebook to install libraries and be able to access the example files from your Google Drive:

```python
# mount google drive
from google.colab import drive
drive.mount('/content/drive')

# define work directory to store data
DATA_ROOT = '/content/drive/MyDrive/DrugExDemo/' # or wherever you want the generated files to live on your GoogleDrive
import os
os.makedirs(DATA_ROOT, exist_ok=True)
os.chdir(DATA_ROOT) 

# fetch pretrained model
os.makedirs("./data/drugex/models/pretrained/", exist_ok=True)
! wget -nc -P './data/drugex/models/pretrained/' 'https://zenodo.org/record/7096859/files/DrugEx_v2_PT_Papyrus05.5.zip'
! unzip -f './data/drugex/models/pretrained/DrugEx_v2_PT_Papyrus05.5.zip' -d './data/drugex/models/pretrained/DrugEx_v2_PT_Papyrus05.5'

# install dependencies
! git clone https://github.com/martin-sicho/drugex-demo
! pip install -r drugex-demo/requirements.txt

# verify where we are working
os.getcwd()
```

## Contents

1. [Data Preparation](data_prep.ipynb) - A short notebook to retrieve and prepare the data set used in this tutorial.
2. [QSAR Modelling](qsar.ipynb) - Creation of a QSAR model that will form one of the objectives in the de novo design workflow.
3. [De Novo Drug Design with DrugEx](de_novo.ipynb) - Implementation of a simple de novo drug design workflow with multiple objectives (predicted biological activity and synthetic accessibility). If you are using Google Colab, do not forget to switch your runtime to GPU for this one!
