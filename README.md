# De Novo Drug Design with DrugEx

This 'talktorial' will take us through a case study of generating novel chemical structures for compounds that could be of interest in the development of new ligands for the [Adenosine A2A receptor](https://www.uniprot.org/uniprotkb/P29274/entry) with a deep learning molecular generator, DrugEx. [DrugEx](https://github.com/CDDLeiden/DrugEx) uses multiple model architectures (from recurrent neural networks to transformers) to generate compounds of desired properties. It combines transfer learning, reinforcment learning and multiobjecetive optimization to drive chemical space exploration. In this tutorial, we will be using the simplest DrugEx model, which is based on recurrent neural networks (RNNs).

## Contents

1. [Data Preparation](data_prep.ipynb) - A short notebook to retrieve and prepare the data set used in this tutorial.
2. [QSAR Modelling](qsar.ipynb) - Creation of a QSAR model that will form one of the objectives in the de novo design workflow.
3. [De Novo Drug Design with DrugEx](de_novo.ipynb) - Implementation of a simple de novo drug design workflow with multiple objectives (predicted biological activity and synthetic accessibility).