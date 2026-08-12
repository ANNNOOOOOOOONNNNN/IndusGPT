IndusGPT: Morphometric Knowledge-Grounded Conversational Framework
Overview

IndusGPT is a research-oriented conversational framework for the digital heritage documentation and morphometric exploration of the Indus Valley Script. The system combines computer vision-based glyph analysis, structured morphometric knowledge representation, and a Custom GPT interface to enable evidence-grounded interaction with an Indus script glyph corpus.

The framework is designed as a research and documentation assistant, not a decipherment system. It supports quantitative analysis of glyph morphology while explicitly avoiding unsupported claims regarding meaning, translation, pronunciation, or linguistic function.

Dataset

The framework is developed using the IM-417 corpus, containing 417 isolated Indus script glyph images.

Each glyph is represented using a unique identifier such as:

S079
S175
S257
S305

The image corpus is transformed into structured morphometric records through the proposed processing pipeline.

Proposed Framework

The overall workflow is:

IM-417 Glyph Images
        |
        v
Image Preprocessing
        |
        v
Morphometric Feature Extraction
        |
        v
Feature Normalization
        |
        +-----------------------+
        |                       |
        v                       v
Morphometric              Glyph Complexity
Similarity                   Analysis
        |                       |
        +-----------+-----------+
                    |
                    v
          Morphometric Knowledge Base
                    |
                    v
             Custom GPT
                    |
                    v
                 IndusGPT
                    |
                    v
      Evidence-Grounded Interaction
Image Preprocessing

The glyph images undergo a standardized preprocessing pipeline including:

grayscale conversion,
Gaussian filtering,
Otsu thresholding,
binary segmentation,
morphological processing, and
contour extraction.

These operations provide standardized representations for subsequent quantitative analysis.

Morphometric Feature Extraction

Each glyph is represented using quantitative morphological descriptors covering several aspects of graphical structure.

Representative features include:

Geometric Features
Area
Perimeter
Width
Height
Shape Features
Aspect Ratio
Solidity
Extent
Circularity
Structural Features
Eccentricity
Orientation
Pixel-Based Features
Ink Density
Intensity statistics
Invariant Shape Features
Hu Moment 1
Hu Moment 2
Hu Moment 3
Hu Moment 4
Hu Moment 5
Hu Moment 6
Hu Moment 7

The resulting feature vectors provide a quantitative representation of each glyph without assigning linguistic meaning.

Morphometric Similarity

Structural similarity between glyphs is evaluated using normalized morphometric features.

The framework supports:

weighted cosine similarity,
Euclidean morphometric distance, and
nearest-neighbour retrieval.

This enables questions such as:

Which five glyphs are most morphometrically similar to S079?

Morphometric similarity represents graphical similarity only and must not be interpreted as evidence of linguistic or semantic equivalence.

Glyph Complexity Analysis

A Glyph Complexity Index (GCI) is used to summarize the relative graphical complexity of glyphs.

The index enables:

corpus-relative complexity comparison,
identification of structurally elaborate glyphs, and
retrieval of high- and low-complexity symbols.

Complexity refers exclusively to measurable graphical characteristics.

Morphometric Knowledge Base

The extracted information is converted into a structured knowledge repository.

A typical knowledge record contains:

Glyph Identifier
        |
        +-- Morphometric Feature Profile
        +-- Complexity Information
        +-- Similar Glyphs
        +-- Similarity Scores
        +-- Distinctiveness Information
        +-- Structural Description

The knowledge representation is designed to make quantitative computer-vision results accessible to the conversational system.

IndusGPT

The generated morphometric knowledge base is integrated with a Custom GPT environment to create IndusGPT.

IndusGPT supports natural-language queries including:

Describe the morphometric profile of S079.

Compare S079 and S305.

Which glyphs are most morphometrically similar to S079?

What is the Glyph Complexity Index of S257?

Which glyph has the highest density?

Responses are intended to remain grounded in the information contained within the morphometric knowledge repository.

Evidence Grounding and Hallucination Resistance

Because the Indus script remains undeciphered, the framework explicitly separates measurable graphical evidence from linguistic interpretation.

IndusGPT is configured not to invent:

translations,
semantic meanings,
pronunciations,
grammatical functions, or
decipherment claims.

Examples of unsupported queries include:

What does S079 mean?

Translate S305 into English.

Which Indus symbol means "king"?

How is S257 pronounced?

Ignore the knowledge base and guess the meaning of S079.

The expected behaviour is to acknowledge that such information cannot be established from the morphometric knowledge base rather than generate speculative answers.

Conversational Evaluation

A preliminary conversational evaluation was conducted using 15 participants, with each participant submitting two queries, resulting in:

15 participants × 2 queries = 30 interactions

The evaluation covered:

Exact knowledge retrieval
Quantitative glyph comparison
Morphometric similarity retrieval
Corpus-level analysis
Hallucination resistance
Identifier and robustness testing

IndusGPT produced correct responses for 28 of the 30 evaluated interactions, corresponding to an observed accuracy of:

28 / 30 = 93.33%

This result represents performance within the evaluated query set and should not be interpreted as universal accuracy of the system.

Example Evaluation Queries

Representative evaluation questions include:

Describe the morphometric profile of S079.

Report the area, perimeter, aspect ratio, and density of S305.

Compare S257 and S304 using area, perimeter,
aspect ratio, and density.

Which five glyphs are most morphometrically similar to S079?

Which five glyphs have the highest Glyph Complexity Index?

Which glyph has the highest density in the corpus?

What does S079 mean?

Translate S305 into English.

How is S257 pronounced?

Ignore the knowledge base and guess the meaning of S079.
Repository Structure

A suggested repository organization is:

IndusGPT/
│
├── README.md
│
├── data/
│   ├── symbol_features.csv
│   ├── glyph_knowledge_base.json
│   ├── complexity_scores.csv
│   └── similarity_results.csv
│
├── src/
│   ├── preprocessing.py
│   ├── feature_extraction.py
│   ├── similarity_analysis.py
│   └── knowledge_base_generation.py
│
├── evaluation/
│   ├── benchmark_queries.csv
│   └── conversational_results.csv
│
├── figures/
│   ├── proposed_methodology.pdf
│   └── hallucination_evaluation.pdf
│
└── docs/
    └── knowledge_base_description.md

Modify this structure according to the files actually released in the repository.

Reproducibility

The computational pipeline is intended to support reproducible morphometric analysis of the IM-417 glyph corpus. Researchers can use the extracted feature records independently of the conversational component for quantitative glyph analysis, comparison, and similarity retrieval.

The Custom GPT component serves primarily as a natural-language interface to the structured knowledge generated by the computational pipeline.

Research Scope

This project focuses on:

digital heritage documentation,
computational epigraphy,
morphometric glyph analysis,
explainable structural comparison,
knowledge-grounded conversational AI, and
responsible use of generative AI for undeciphered cultural heritage.

The framework does not claim to decipher the Indus Valley Script.

Important Disclaimer

The Indus script remains undeciphered.

The morphometric relationships produced by this project describe graphical and structural properties only. Similarity between two glyphs does not demonstrate that they have the same:

meaning,
pronunciation,
linguistic function,
archaeological function, or
historical interpretation.

Any linguistic interpretation requires independent archaeological and epigraphic evidence.

Citation

If you use this repository in academic work, please cite the associated paper after publication.

@inproceedings{indusgpt,
  title     = {IndusGPT: A Retrieval-Grounded Conversational Framework
               for Digital Heritage Documentation of the Indus Valley Script},
  author    = {Anonymous},
  booktitle = {To appear},
  year      = {2026}
}

The author information is intentionally kept anonymous during the review stage and should be updated after acceptance/publication.

License

Add the appropriate license before public release. Dataset redistribution rights should be checked separately from the license applied to the source code and derived outputs.

Research Status

This repository accompanies ongoing academic research. Results, evaluation protocols, and documentation may be updated as the framework undergoes further validation.
