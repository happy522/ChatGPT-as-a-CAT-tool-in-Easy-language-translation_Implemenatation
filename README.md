

# ChatGPT as a CAT tool in Easy language translation

This repository contains the extension of data used in the paper ["ChatGPT as a CAT tool in Easy language translation"](https://arxiv.org/pdf/2308.11563) by Silvana Deilen, Sergio Hernández Garrido, Ekaterina Lapshinova-Koltunski and Christiane Maaß.

In the paper, we analyse the feasibility of using ChatGPT to translate citizen-oriented administrative texts into German Easy Language, a simplified, controlled language variety that is adapted to the needs of people with reading impairments.

The online tool ChatGPT is used to translate selected texts from websites of German public authorities. Two strategies are applied: (a) linguistic and (b) holistic.

This project implements a complexity-aware Computer-Assisted Translation (CAT) tool using GPT-4.0 and GPT-4.1 generated holistic and linguistic texts in German. It includes analysis and visualization of multiple linguistic complexity measures to support easier and more consistent translation workflows.

Prompts for generation:
Holistic approach: übersetzen Sie den folgenden Text in die Deutsche Leichte Sprache: + base text
Linguistic approach:linguistischer Ansatz (Sprachebenen): reformuliere den Text, aber:
- ohne unwichtige Informationen (Textebene)
- ohne Nebensätze und mit einfachen syntaktischen Strukturen (Satzebene)
- füge Erklärungen für schwierige Wörter hinzu (Wortebene)

---
## Folder Structure

```plaintext
.
├── Implementation_Chatgpt_as_a_cat_eye_tool_4_1  # General script for processing data and generating outputs       
├── LLM Name/
│   ├── data/
│   │   ├── conll/             # Parsed linguistic annotation files
│   │   │   ├── *E.conll      # Holistic outputs
│   │   │   ├── *H.conll      # Linguistic outputs
│   │   │   ├── *B.conll      # Original input texts
│   │   └── txt/               # Raw text files with same naming convention
│   ├── plots/                 # Visualizations for all complexity measures
│   ├── Holistic_and_Linguistic_Data_LLM Name.csv
│   └── Complexity_Matrix_LLM Name.csv
````

---




## Measured Complexity Dimensions

### Lexical Measures

* **Type-Token Ratio (TTR)**: Measures vocabulary diversity.
* **Lexical Density**: Ratio of content words (nouns, verbs, adjectives, adverbs) to total words.
* **Word Rarity**: Frequency of uncommon words in the text.

### Syntactic Measures

* **Mean Dependency Distance (MDD)**: Average distance between tokens and their syntactic heads.
* **Subordination Index**: Ratio of subordinate clauses to total clauses.
* **Dependency Crossings**: Number of crossing dependencies; more implies higher complexity.

### Readability Indices (German-specific)

* **Wiener Sachtextformel**: Based on sentence and word lengths, plus syllables.
* **LIX (Lesbarhetsindex)**: Based on average sentence length and long word count.
* **Amstad’s FRE (German adaptation)**: Measures ease of reading news-like texts.
* **Gunning Fog Index**: Estimates years of education required to understand the text.

