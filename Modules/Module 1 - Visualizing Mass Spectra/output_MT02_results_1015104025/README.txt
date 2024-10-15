
The recommended feature table is `preferred_Feature_table.tsv`. 

All peaks are kept in `export/full_Feature_table.tsv` 
if they meet signal (snr) and shape standards 
(part of input parameters but default values are fine for most people). 
The filtering decisions are left to end users.

Annotation is in JSON (`Annotated_empricalCompounds.json`) 
and in tab delimited text (`Feature_annotation.tsv`).

The processing parameters and history are in `project.json`.

Please refer to https://github.com/shuzhao-li/asari for details, 
report bugs or request features.
