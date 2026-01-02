# **Advanced Module 8: RAG & Knowledge Systems**
## **Session 1: RAG Fundamentals**

**Duration:** 45 min live + 75 min homework

-----

## **Entry Criteria**

- [ ] Block 3 completed with working agent system
- [ ] Understanding of vector similarity concepts (conceptual)
- [ ] Access to sample documents for testing
- [ ] Familiarity with API-based model interactions

## **Exit Criteria**

- [ ] RAG architecture patterns understood
- [ ] Chunking strategies mastered
- [ ] Embedding concepts clear
- [ ] Basic retrieval pipeline designed
- [ ] First RAG prototype functional

-----

## **Workshop Content (45 minutes)**

### **Segment 1: RAG Architecture Fundamentals (12 min)**

- **What is RAG?**
  - Retrieval-Augmented Generation
  - Combines retrieval systems with generative AI
  - Grounds AI responses in actual data
  - Reduces hallucination, increases accuracy

- **Why RAG for Agents?**
  - Agents need access to current, domain-specific knowledge
  - Context windows are limited and expensive
  - Dynamic knowledge that changes frequently
  - Audit trail: know what information informed decisions

- **Core RAG pipeline:**
  ```
  [Documents] → [Chunking] → [Embedding] → [Vector Store]
                                                  ↓
  [Query] → [Query Embedding] → [Similarity Search] → [Retrieved Chunks]
                                                           ↓
  [LLM Prompt] ← [Query + Retrieved Context] → [Generated Response]
  ```

- **RAG vs. Fine-tuning vs. Long Context:**

  | Approach | Best For | Limitations |
  |----------|----------|-------------|
  | RAG | Dynamic knowledge, citations needed, large corpora | Retrieval quality dependency |
  | Fine-tuning | Style/behavior changes, static domain knowledge | Expensive, no citations |
  | Long Context | Small, fixed documents | Cost, context dilution |

### **Segment 2: Document Chunking Strategies (12 min)**

- **Why chunking matters:**
  - Too large: irrelevant content, poor retrieval
  - Too small: lost context, fragmented information
  - Goal: semantically coherent units

- **Chunking strategies:**

  1. **Fixed-size chunking:**
     ```
     Document → [500 tokens] [500 tokens] [500 tokens]...
     - Simple to implement
     - May split mid-sentence/concept
     - Add overlap (50-100 tokens) to preserve context
     ```

  2. **Semantic chunking:**
     ```
     Document → [Complete paragraph] [Complete section]...
     - Respects natural boundaries
     - Variable chunk sizes
     - Better semantic coherence
     ```

  3. **Hierarchical chunking:**
     ```
     Document
       └── Section (summary)
             └── Subsection (summary)
                   └── Paragraphs (full text)
     - Multiple granularity levels
     - Enables different retrieval strategies
     ```

  4. **Agentic chunking:**
     ```
     LLM analyzes document → Identifies logical units → Creates chunks
     - Highest quality boundaries
     - Most expensive to create
     - Good for critical documents
     ```

- **Chunking decision framework:**

  | Document Type | Recommended Strategy | Chunk Size |
  |---------------|---------------------|------------|
  | Technical docs | Semantic (by section) | 500-1000 tokens |
  | Legal/contracts | Semantic (by clause) | 300-500 tokens |
  | Conversations | By turn/exchange | Variable |
  | Code | By function/class | Variable |
  | General prose | Fixed + overlap | 400-600 tokens |

### **Segment 3: Embedding and Vector Storage (12 min)**

- **What are embeddings?**
  - Dense vector representations of text
  - Capture semantic meaning
  - Similar concepts = similar vectors
  - Enable semantic search

- **Embedding model selection:**

  | Consideration | Options/Trade-offs |
  |---------------|-------------------|
  | Model quality | OpenAI ada-002, Cohere, open-source |
  | Dimension size | 384, 768, 1536 (larger = more nuance, more cost) |
  | Specialized vs. general | Domain-specific may outperform |
  | Cost | Per-token pricing varies significantly |

- **Vector database concepts:**
  ```
  Vector Store
  ├── Index: Enables fast similarity search
  ├── Vectors: Stored embeddings
  ├── Metadata: Source, date, type, permissions
  └── Search: k-NN, ANN algorithms
  ```

- **Key vector DB capabilities:**
  - Approximate nearest neighbor (ANN) search
  - Metadata filtering (pre/post retrieval)
  - Hybrid search (vector + keyword)
  - Namespaces/collections for organization

- **Metadata strategy:**
  ```json
  {
    "chunk_id": "doc-123-chunk-5",
    "source_document": "policy-handbook-2024.pdf",
    "section": "Employee Benefits",
    "page_number": 45,
    "created_date": "2024-01-15",
    "document_type": "policy",
    "access_level": "internal",
    "version": "2.1"
  }
  ```

### **Segment 4: Basic Retrieval Pipeline (9 min)**

- **Retrieval process:**
  ```
  1. Query arrives
  2. Query → embedding
  3. Similarity search (top-k)
  4. Apply metadata filters
  5. Return ranked chunks
  6. Format for LLM context
  ```

- **Similarity metrics:**
  - Cosine similarity (most common)
  - Euclidean distance
  - Dot product
  - Choice depends on embedding model

- **Top-k selection:**
  - Too few: miss relevant information
  - Too many: noise, context dilution, cost
  - Typical: 3-10 chunks
  - Adjust based on use case

- **Context formatting:**
  ```
  System: You are an assistant with access to company knowledge.

  Retrieved Context:
  ---
  [Source: policy-handbook.pdf, Section: Benefits]
  {chunk_1_content}
  ---
  [Source: faq-document.pdf, Section: Insurance]
  {chunk_2_content}
  ---

  User Query: {original_query}

  Instructions: Answer based on the provided context.
  If the context doesn't contain the answer, say so.
  ```

-----

## **Self-Paced Exercises (75 minutes total)**

### **Exercise 1.1: RAG Architecture Design (25 minutes)**

*Design your knowledge retrieval system*

```markdown
# RAG Architecture Design

## System Purpose
[What knowledge problem are you solving?]

## Knowledge Sources

### Source 1: [Name]
- **Type:** [PDF/Web/Database/API]
- **Size:** [Estimated documents/pages]
- **Update frequency:** [Static/Daily/Real-time]
- **Access control:** [Public/Internal/Restricted]

### Source 2: [Name]
[Repeat for each source]

## Architecture Diagram
```
[Document Sources]
      ↓
[Ingestion Pipeline]
  - Document parsing
  - Chunking strategy: [chosen approach]
  - Metadata extraction
      ↓
[Embedding Service]
  - Model: [chosen model]
  - Dimension: [size]
      ↓
[Vector Store]
  - Type: [chosen solution]
  - Index type: [HNSW/IVF/etc.]
      ↓
[Retrieval Service]
  - Search type: [semantic/hybrid]
  - Top-k: [number]
  - Filters: [metadata filters]
      ↓
[Context Assembly]
      ↓
[LLM Generation]
```

## Design Decisions

### Chunking Strategy
- **Chosen approach:** [Strategy]
- **Chunk size:** [tokens]
- **Overlap:** [tokens]
- **Rationale:** [Why this approach]

### Embedding Model
- **Model:** [Name]
- **Dimensions:** [Size]
- **Rationale:** [Why this model]

### Retrieval Configuration
- **Top-k:** [Number]
- **Similarity threshold:** [If any]
- **Metadata filters:** [List]
- **Rationale:** [Why these settings]

## Expected Challenges
1. [Challenge and mitigation]
2. [Challenge and mitigation]
3. [Challenge and mitigation]
```

**Deliverable:** `rag-architecture-design.md`

-----

### **Exercise 1.2: Implement Chunking Pipeline (30 minutes)**

*Build your document processing pipeline*

1. **Select test documents:**
   - Choose 3-5 representative documents
   - Mix of types if possible (policy, FAQ, technical)

2. **Implement chunking:**

```markdown
# Chunking Implementation

## Test Documents

| Document | Type | Pages/Size | Purpose |
|----------|------|------------|---------|
| [Doc 1] | [Type] | [Size] | [Why selected] |
| [Doc 2] | | | |
| [Doc 3] | | | |

## Chunking Configuration

### Strategy: [Chosen approach]

```json
{
  "chunking_config": {
    "strategy": "semantic|fixed|hierarchical",
    "chunk_size": 500,
    "chunk_overlap": 50,
    "separators": ["\n\n", "\n", ". "],
    "preserve_metadata": true
  }
}
```

## Sample Chunks Analysis

### Document: [Name]

#### Chunk 1
- **Size:** [tokens]
- **Content preview:** [First 100 chars]
- **Metadata:** [Associated metadata]
- **Quality assessment:** [Good/Issues]

#### Chunk 2
[Repeat]

#### Chunk 3
[Repeat]

## Chunking Statistics

| Document | Total Chunks | Avg Size | Min Size | Max Size |
|----------|--------------|----------|----------|----------|
| [Doc 1] | | | | |
| [Doc 2] | | | | |
| [Doc 3] | | | | |

## Quality Assessment

### Issues Found
1. **Issue:** [Description]
   - **Chunk affected:** [ID]
   - **Fix:** [How to address]

### Improvements Made
1. [Adjustment to chunking config]
2. [Adjustment]

## Final Configuration
```json
{
  "final_chunking_config": {
    // Refined configuration
  }
}
```
```

**Deliverable:** Chunking implementation + analysis document

-----

### **Exercise 1.3: Basic Retrieval Testing (20 minutes)**

*Test retrieval quality with sample queries*

```markdown
# Retrieval Quality Testing

## Test Setup
- **Embedding model:** [Model used]
- **Vector store:** [Solution used]
- **Top-k:** [Number]
- **Documents indexed:** [Count]
- **Total chunks:** [Count]

## Test Queries

### Query 1: [Simple factual query]
- **Expected relevant chunks:** [List chunk IDs or descriptions]
- **Retrieved chunks:**
  | Rank | Chunk ID | Score | Relevant? |
  |------|----------|-------|-----------|
  | 1 | | | Yes/No |
  | 2 | | | |
  | 3 | | | |
- **Precision@3:** [X/3]
- **Notes:** [Observations]

### Query 2: [Complex multi-part query]
- **Expected relevant chunks:** [List]
- **Retrieved chunks:**
  | Rank | Chunk ID | Score | Relevant? |
  |------|----------|-------|-----------|
  | 1 | | | |
  | 2 | | | |
  | 3 | | | |
- **Precision@3:** [X/3]
- **Notes:** [Observations]

### Query 3: [Edge case - ambiguous query]
[Repeat structure]

### Query 4: [Edge case - no relevant content]
[Repeat structure]

### Query 5: [Domain-specific terminology]
[Repeat structure]

## Summary Metrics

| Metric | Value |
|--------|-------|
| Average Precision@3 | |
| Average Precision@5 | |
| Queries with relevant top-1 | X/5 |
| Failed retrievals | |

## Issues Identified
1. [Issue and potential cause]
2. [Issue]

## Recommended Improvements
1. [Improvement to try in Week 2]
2. [Improvement]
```

**Deliverable:** `retrieval-quality-test.md`

-----
