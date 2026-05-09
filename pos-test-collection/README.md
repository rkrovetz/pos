# POS (Part-of-Speech) Tagging Test Collection

This repository contains the evaluation dataset used in the paper:

Robert Krovetz. 2026.
"A Test Collection for Part-of-Speech Tagging and Word Sense Disambiguation"

The dataset focuses on words at the intersection of part-of-speech tagging
and word sense disambiguation.  These are words such as _train_, _novel_,
and _lean_, where the difference in part of speech aligns with clear 
differences in meaning.

The repository also includes:

- a tagged subset of the Wikipedia based on the test collection vocabulary
- an assessment resource focused on adjective ambiguity
- documentation describing the methodology and annotation issues

## Contents

datasets/
    pos-test-collection.csv                 Evaluation dataset
    wikipedia-assessment-of-15-words.txt    Assessment of adjective ambiguity
    
docs/
    methodology.md
    annotation-notes.md
    wikipedia-subset.md

LICENSE

CITATION
