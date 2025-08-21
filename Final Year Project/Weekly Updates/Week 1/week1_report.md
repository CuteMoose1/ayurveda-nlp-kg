# 🌿 Week 1 Report — Ayurveda NLP Project

## ✅ Objective
- Build a **minimal working demo** to show feasibility:
  - Translate Sanskrit → English.
  - Extract `(Herb, Relation, Disease)` triples.
  - Construct a **mini Knowledge Graph (KG)**.
  - Export triples to **Neo4j**.

---

## 🧩 Demo Components
- **Lexicon (`sanskrit_to_english`)**: maps Sanskrit tokens → English.  
- **Verb Relation Map (`verb_relation_map`)**: verbs → semantic relations.  
- **Sample Sentences**: 5 Ayurveda-inspired Sanskrit examples.  

---

## ⚙️ Workflow
1. **Tokenize** sentence.  
2. **Detect Entities**: Herbs vs Diseases.  
3. **Detect Relation**: from verb map.  
4. **Extract Triple**: `(Herb, Relation, Disease)`.  
5. **Build KG** using `networkx`.  
6. **Export Cypher** statements for Neo4j.  

---

## 📊 Sample Output
```text
Sentence: हरिद्रा ज्वरं नाशयति
  -> Extracted triple: ('Turmeric', 'NASHAYATI', 'Fever')

Sentence: आमलकी पित्तं शमयति
  -> Extracted triple: ('Amla', 'SHAMAYATI', 'Pitta')

Sentence: गुडुची कासं उपयुज्यते
  -> Extracted triple: ('Guduchi', 'UPAYUJYATE', 'Cough')
```
---

## 🌐 Knowledge Graph Visualization
Herbs 🟠 vs Diseases 🟢, relations labeled 🔴.

> Add this image to your repo at: `docs/images/week1_kg_demo.png`  
> Then the link below will render on GitHub.

![Week 1 KG Demo](docs/images/week1_kg_demo.png)

---

## 🗃️ Cypher Export (Neo4j)
```cypher
MERGE (a:Herb {name:'Turmeric'}) MERGE (b:Disease {name:'Fever'}) MERGE (a)-[:NASHAYATI]->(b)
MERGE (a:Herb {name:'Amla'}) MERGE (b:Disease {name:'Pitta'}) MERGE (a)-[:SHAMAYATI]->(b)
MERGE (a:Herb {name:'Guduchi'}) MERGE (b:Disease {name:'Cough'}) MERGE (a)-[:UPAYUJYATE]->(b)
```

---

## 📌 Key Takeaways
- ✅ Sanskrit → Triple → KG pipeline is **feasible**.
- ✅ Demo runs in **Google Colab**.
- 🚀 Next Week: expand corpus, normalize texts, start annotation.
