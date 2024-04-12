<!---

    Copyright (c) 2023 Robert Bosch GmbH and its subsidiaries.

-->

# AnnoCTR Resources

This repository contains the companion material for the following publication:

> Lukas Lange, Marc Müller, Ghazaleh Haratinezhad Torbati, Dragan Milchevski, Patrick Grau, Subhash Pujari, Annemarie Friedrich. **AnnoCTR: A Dataset for Detecting and Linking Entities, Tactics, and Techniques in Cyber Threat Reports.** LREC-COLING 2024.

Please cite this paper if using the dataset or the code, and direct any questions to [Lukas Lange](mailto:lukas.lange@de.bosch.com).
The paper can be found at the [ACL Anthology (tbd.)](https://www.aclweb.org/anthology/TODO/) or at
[ArXiv](https://arxiv.org/abs/2404.07765).


## Purpose of this Software 

This software is a research prototype, solely developed for and published as
part of the publication cited above. It will neither be maintained nor monitored in any way.


## The AnnoCTR Corpus

AnnoCTR consists of 400 cyber threat reports that have been obtained from commercial CTI vendors. 
The reports describe threat-related information such as tactics, techniques, actors, tools, and targeted industries. 
The reports have been annotated by a domain expert with named entities, temporal expressions, and cybersecurity-specific concepts. 
The annotations include mentions of organizations, locations, industry sectors, time expressions, 
code snippets, hacker groups, malware, tools, tactics, and techniques.

The dataset is split into three parts: train, dev, and test, with 60%, 15%, and 25% of the documents, 
respectively. 
The train set is used for model training, the dev set is used for model selection, 
and the test set is used for evaluation.

For further information on the annotation scheme, 
please refer to our paper and the annotation guidelines for the 
[general concepts](Annotation_Guidelines_General_Layer.pdf) and 
[cybersecurity-specific concepts](Annotation_Guidelines_Cysec_Layer.pdf).

### Corpus File Formats

As AnnoCTR is annotated with different concepts and layers, the corpus is provided in different formats.
Each format is stored in a separate folder following popular file formats:

* **ner_bio** - Named entity recognition in typical BIO format
* **ner_json** - Named entity recognition in popular huggingface JSON format following https://huggingface.co/datasets/conll2003.
* **linking** - Linking of entities, tactics, and techniques in JSON KILT format 
following the GENRE model for entity linking (see https://github.com/facebookresearch/GENRE/tree/main/examples_genre for more information).
* **entities** - contains the KG dump as a list of entities in JSON following BLINK's file format 
(see http://dl.fbaipublicfiles.com/BLINK/entity.jsonl for an example). 
We only provide the MITRE ATT&CK entities due to the large size (3.7GB) of the Wikipedia [entity.jsonl](http://dl.fbaipublicfiles.com/BLINK/entity.jsonl) file. 
Download that file and combine both to link general and cybersecurity entities.
* **text** - Plain text of the reports in .txt files
* **time** - Temporal expressions in the TimeML format (with and without annotations)


### Acknowledgements

The reports have been kindly donated by 
[Intel471](https://intel471.com/blog}), 
[Lab52](https://lab52.io/blog/), 
the [threat intelligence division of S2 Grupo](https://s2grupo.es/), 
[Proofpoint](https://www.proofpoint.com/us/blog), 
[QuoIntelligence](https://quointelligence.eu/blog), 
and [ZScaler](https://www.zscaler.com/blogs/security-research).


## License

The AnnoCTR corpus located in the folder [AnnoCTR](AnnoCTR) is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/) (CC-BY-SA 4.0).
