# Week-1+ Extraction Toolkit (CSV-configurable)

## What this does
- Reads **lexicon** and **verb map** from CSV.
- Processes Sanskrit sentences (space-separated) from `data/sentences.txt`.
- Extracts `(Herb, Relation, Disease)` triples.
- Saves results:
  - `out/triples.csv`
  - `out/cypher.txt` (Neo4j MERGE statements)
  - `docs/images/week1_kg_demo.png` (graph)

## How to use (Colab / local)
```bash
# Edit CSVs in data/ (add new herbs/diseases/verbs)
# Edit data/sentences.txt with your sentences (one per line)

# Run this notebook cell or Python script version
# Outputs will appear in out/ and docs/images/
```
