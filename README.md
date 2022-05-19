# Automatic Post Editing for Machine Translation at WMT

## Overview 

The 8th round of the APE shared task follows the success of the previous rounds organized from 2015 to 2021. The aim is to examine automatic methods for correcting errors produced by an unknown machine translation (MT) system. This has to be done by exploiting knowledge acquired from human post-edits, which are provided as training material.<br/>

### Goals

The aim of this task is to improve MT output in black-box scenarios, in which the MT system is used "as is" and cannot be modified. From the application point of view, APE components would make it possible to:<br/>

 - Cope with systematic errors of an MT system whose decoding process is not accessible
 - Provide professional translators with improved MT output quality to reduce (human) post-editing effort
 - Adapt the output of a general-purpose system to the lexicon/style requested in a specific application domain

### Task Description

This year we introduce Indian language focusing on English --> Marathi language pair. The dataset covers several domains like healthcare, tourism, general/news. In these datasets, the source sentences have been translated into the target language by using a state-of-the-art neural MT system unknown to the participants (in terms of system configuration) and then manually post-edited.<br/>

At the training stage, the collected human post-edits have to be used to learn correction rules for the APE systems. At the test stage they will be used for system evaluation with automatic metrics (TER and BLEU).<br/>

## DIFFERENCES FROM THE 7th ROUND (WMT 2021)

Compared to the previous round, the main differences are:

 - Focus on a low-resource Indian language (Marathi)
 - Use of new domains healthcare and tourism for Indian language

### Data

Training, development and test data consist in (source, target, post-edit) triplets. The source sentences in English come from the healthcare, tourism, and general/news domains. The target sentences are automatic translations to Marathi. The post-edits are human revisions of the target elements.<br/>

To download the data, click on the links in the table below:<br/>

| **Language Pair** 	|     **Data**     	                                                                            | **Additional Resource** 	|
|:-----------------:	|:----------------:	                                                                            |:-----------------------:	|
| English - Marathi 	| [train and dev](https://github.com/surrey-nlp/APE-Shared-Task/tree/main/data/ape-2022/en-mr) 	| +[synthetic data](https://github.com/surrey-nlp/APE-Shared-Task/tree/main/synthetic-data/ape-2022/en-mr)     	|


+: This synthetic training data is prepared as a part of the 2022 APE shared task. The data is created by taking a parallel corpus, where the source data is translated using an MT system, and the reference is considered as post-edits.

### NOTE:

 - Any use of additional data for training your system is allowed (e.g. parallel corpora, post-edited corpora).
 - Data Citation
 - Please cite the following paper if you use the datasets released in this shared task:
 -   (will be added during the camera-ready period)

### Evaluation

Systems' performance will be evaluated with respect to their capability to reduce the distance that separates an automatic translation from its human-revised version.<br/>
Such distance will be measured in terms of TER, which will be computed between automatic and human post-edits in case-sensitive mode.
<br/>
Also, BLEU will be taken into consideration as a secondary evaluation metric. To gain further insights on final output quality, a subset of the outputs of the submitted systems will also be manually evaluated like in previous rounds.
<br/>
The submitted runs will be ranked based on the average HTER calculated on the test set by using the tercom software.
<br/>
The HTER calculated between the raw MT output and human post-edits in the test set will be used as baseline (i.e. the baseline is a system that leaves all the test instances unmodified).
<br/>

The evaluation script can be downloaded here
<br/>

### Submission Format

The output of your system should produce automatic post-editions of the target sentences in the test in the following way (each column is tab separated):
<br/>

\<METHOD NAME>   \<SEGMENT NUMBER>   \<APE SEGMENT> <br/>

<br/>

Where:
 - METHOD NAME is the name of your automatic post-editing method.
 - SEGMENT NUMBER is the line number of the plain text target file you are post-editing (starting index is 1).
 - APE SEGMENT is the automatic post-edits for the particular segment.
 - Each field should be delimited by a single tab character.

### Submission Requirements

Each participating team can submit at most 2 systems, but they have to explicitly indicate which of them represents their primary submission. In the case that none of the runs is marked as primary, the latest submission received will be used as the primary submission.
<br/>

Submissions should be sent via email to wmt-ape-submission@fbk.eu. Please use the following pattern to name your files:
<br/>

INSTITUTION-NAME_METHOD-NAME_SUBTYPE, where:
<br/>

INSTITUTION-NAME is an acronym/short name for your institution, e.g. "UniXY"
<br/>

METHOD-NAME is an identifier for your method, e.g. "pt_1_pruned"
<br/>

SUBTYPE indicates whether the submission is primary or contrastive with the two alternative values: PRIMARY, CONTRASTIVE.
<br/>

You are also invited to submit a short paper (4 to 6 pages) to WMT describing your APE method(s). You are not required to submit a paper if you do not want to. In that case, we ask you to give an appropriate reference describing your method(s) that we can cite in the WMT overview paper.
<br/>

### Results

The official results of the 2022 APE shared task will be available here. <br/>

## Important dates

 - Release of training and development data:	May 17, 2022
 - Release of test data:	July 11, 2022
 - APE system submission deadline:	July 18, 2022
 - Manual evaluation:	August
 - Paper submission deadline:	September 7, 2022
 - Notification of acceptance:	October 9, 2022
 - Camera-ready deadline:	October 16, 2022

## Organizers

 - Pushpak Bhattacharyya (Indian Institute of Technology, Bombay)
 - Rajen Chatterjee (Apple Inc.)
 - Markus Freitag (Google Research)
 - Diptesh Kanojia (Surrey Institute for People-Centred AI, University of Surrey)
 - Matteo Negri (Fondazione Bruno Kessler)
 - Marco Turchi (Fondazione Bruno Kessler)

## Contact

For any information or question about the task, please send an email to: wmt-ape@fbk.eu. <br/>

To be always updated about this year's edition of the APE task, you can also join the wmt-ape group. <br/>
