# Polish author recognition
>[!NOTE]
>This entire project was conducted as a final examination project at Natural Language Processing course.
## Main goal
Create a neural network model to recognize the authors of given old polish novels: Bolesław Prus, Henryk Sienkiewicz, Stanisław Reymont, Stefan Żeromski and Eliza Orzeszkowa.
## Workflow
1. Data extraction:
  - All data was downloaded using API from website wolnelektury.pl
  - For each author the number of texts downloaded were in the range of 7-8
  - Each text had to be classified as novel and had to have at least 10000 characters.
2. Analysis of given data:
  - Token frequency distribution
  - POS frequency distribution
  - Dialogue frequency distribution
  - Number of sentences per text
  - Mean number of words per sentence
  - Mean length of a word
  - Mean number of unique words
  - Hapax legomenon (A word or an expression that occurs only once within a context)
  - Jaccard Index for sets of POS and sets of tokens
3. Text Segmentation:
  - Length of each chunk was set on 50 sentences
4. Creation, training and validation of NN models:
```text
Stack model:
|
|--- HerBERT model
|--- Fusion model
     |
     |--- Stat model
     |--- N-gram model
     |--- POS model
```
>[!IMPORTANT]
>Each model was trained separately
## Available data
Each of the analyzed texts was retrieved from the wolnelektury.pl website using the site's API. Each text was properly cleaned to remove the superfluous title and footer added by the website. Below is a list of all the authors and the works retrieved for them:
| Bolesław Prus | Eliza Orzeszkowa | Stefan Żeromski | Władysław Stanisław Reymont | Henryk Sienkiewicz |
| --- | --- | --- | --- | --- |
| *The Doll*: Volume I | *Emancipated Women*: Volume I | *The Homeless* / *Homeless People*: Volume I | *The Promised Land*: Volume II | *The Knights of the Cross*: Volume I |
| *The Doll*: Volume II | *Emancipated Women*: Volume II | *The Homeless* / *Homeless People*: Volume II | *The Peasants*: Part One | *The Knights of the Cross*: Volume II |
| *The Pharaoh*: Volume I | *On the Niemen*: Volume I | *Ashes*: Volume I | *The Peasants*: Part Three | *With Fire and Sword*: Volume I |
| *The Pharaoh*: Volume II | *On the Niemen*: Volume II | *Ashes*: Volume II | *The Peasants*: Part Four | *With Fire and Sword*: Volume II |
| *The Pharaoh*: Volume III | *On the Niemen*: Volume III | *Ashes*: Volume III | *Ferments*: Volume I | *The Deluge*: Volume I |
| *Anielka* | *The Boor* | *The Spring to Come* | *Ferments*: Volume II | *The Deluge*: Volume II |
|  | *Marta* | *The Syzygy of the Class* / *The Labors of Sisyphus* | *The Vampire* | *The Deluge*: Volume III |
|  | *In the Cage* | *The Faithful River* |  |  |
|  | *Phantoms* |  |  |  |
## Repository contents
```text
Polish_author_recognition/
|
|--- data/      #All full texts
|--- plots/     #All PNG files generated during models training and validation
|--- chunks.txt
|--- main_pipeline.ipynb  #File with main script
|--- requirements.yml
|--- README.md
```
