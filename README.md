# Polish author recognition
>[!NOTE]
>This entire project was conducted as a final examination project at Natural Language Processing course.
## Main goal
Create a neural network model to recognize the authors of given old polish novels: Bolesław Prus, Henryk Sienkiewicz, Stanisław Reymont, Stefan Żeromski and Eliza Orzeszkowa.
## Workflow
1. Data extraction:
  - All data was downloaded using API from website www.wolnelektury.com
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
| Author                          | Work                                                 |
| ------------------------------- | ---------------------------------------------------- |
| **Bolesław Prus**               | *The Doll*: Volume I                                 |
| **Bolesław Prus**               | *The Doll*: Volume II                                |
| **Bolesław Prus**               | *The Pharaoh*: Volume I                              |
| **Bolesław Prus**               | *The Pharaoh*: Volume II                             |
| **Bolesław Prus**               | *The Pharaoh*: Volume III                            |
| **Bolesław Prus**               | *Anielka*                                            |
| **Eliza Orzeszkowa**            | *Emancipated Women*: Volume I                        |
| **Eliza Orzeszkowa**            | *Emancipated Women*: Volume II                       |
| **Eliza Orzeszkowa**            | *On the Niemen*: Volume I                            |
| **Eliza Orzeszkowa**            | *On the Niemen*: Volume II                           |
| **Eliza Orzeszkowa**            | *On the Niemen*: Volume III                          |
| **Eliza Orzeszkowa**            | *The Boor*                                           |
| **Eliza Orzeszkowa**            | *Marta*                                              |
| **Eliza Orzeszkowa**            | *In the Cage*                                        |
| **Eliza Orzeszkowa**            | *Phantoms*                                           |
| **Stefan Żeromski**             | *The Homeless* / *Homeless People*: Volume I         |
| **Stefan Żeromski**             | *The Homeless* / *Homeless People*: Volume II        |
| **Stefan Żeromski**             | *Ashes*: Volume I                                    |
| **Stefan Żeromski**             | *Ashes*: Volume II                                   |
| **Stefan Żeromski**             | *Ashes*: Volume III                                  |
| **Stefan Żeromski**             | *The Spring to Come*                                 |
| **Stefan Żeromski**             | *The Syzygy of the Class* / *The Labors of Sisyphus* |
| **Stefan Żeromski**             | *The Faithful River*                                 |
| **Władysław Stanisław Reymont** | *The Promised Land*: Volume II                       |
| **Władysław Stanisław Reymont** | *The Peasants*: Part One                             |
| **Władysław Stanisław Reymont** | *The Peasants*: Part Three                           |
| **Władysław Stanisław Reymont** | *The Peasants*: Part Four                            |
| **Władysław Stanisław Reymont** | *Ferments*: Volume I                                 |
| **Władysław Stanisław Reymont** | *Ferments*: Volume II                                |
| **Władysław Stanisław Reymont** | *The Vampire*                                        |
| **Władysław Stanisław Reymont** | *The Promised Land*: Volume II                       |
| **Henryk Sienkiewicz**          | *The Knights of the Cross*: Volume I                 |
| **Henryk Sienkiewicz**          | *The Knights of the Cross*: Volume II                |
| **Henryk Sienkiewicz**          | *With Fire and Sword*: Volume I                      |
| **Henryk Sienkiewicz**          | *With Fire and Sword*: Volume II                     |
| **Henryk Sienkiewicz**          | *The Deluge*: Volume I                               |
| **Henryk Sienkiewicz**          | *The Deluge*: Volume II                              |
| **Henryk Sienkiewicz**          | *The Deluge*: Volume III                             |
## Repository contents
```text
Polish_author_recognition/
|
|--- data/      #All full texts
|--- plots/     #All PNG files generated during models training and validation
|--- results/   #Folder generated by HerBERT model
|--- chunks.txt
|--- polish_author_recognition.ipynb  #File with main script
|--- requirements.yml
|--- README.md
```
