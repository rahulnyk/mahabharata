# Mahabharata
This is a compilation of the text of Mahabharata from the following sources

1. [Complete Translation by K. N. Ganguli](https://github.com/kunjee17/mahabharata/tree/master): Github Repository of the text. Here this project is trying to look at epic from the Data Science perspective.
2. [Laura Gibbs Tiny Tales](https://microfables.blogspot.com/2020/11/tiny-tales-from-mahabharata.html): This is a retelling of the Mahabharata using two hundred episodes that are each 100 words long. 
3. [Kaggle data repo by Tilak](https://www.kaggle.com/datasets/tilakd/mahabharata): All 18 parvas of Mahabharata in txt format for NLP
4. Wikipedia Parva Summaries

## Directory Structure

#### text
The text copied from the sources mentioned above. 

#### data_parse
Python Notebooks for parsing the data into CSV files 

#### data processing
Notebooks for processing the data. This directory contains the NER notebook for calculating named entitied for the text chunks. I am using the following model for Named Entity Recognition

[2rtl3/mn-xlm-roberta-base-named-entity](https://huggingface.co/2rtl3/mn-xlm-roberta-base-named-entity) using the **Hugging Face** transformers library

#### data
Contains the final output of data parsing notebooks into pandas dataframes as `|` delimited CSV files. All the metadata, including the source, chapter, section, etc. are maintained as columns in the csv. Each csv has a text column containing the text chunk with 100 to 500 tokens each. Each row also has a `chunk_id`, which is a uuid. This chunk id is used to index the named entities in the named entities dataframes.  

#### data/named_entities
Each data csv also has a corrosponding Named Entities csv. The `chunk_id` is used as an index for tagging named entities to corrosponding chunks.


> Note: If you regenerate the data csv files, you must also regenerate the named entities, or else the chunk_id in the named entity dataframes will not corrospond to the regenerated csv rows


