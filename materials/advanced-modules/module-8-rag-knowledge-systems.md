# **Advanced Module 8: RAG & Knowledge Systems**

## **2 Weeks | 45 min live + 75 min homework per week**

-----

## **Prerequisites**

- Block 3 Certification: AI Automation Architect
- Working agent system with tool-use capabilities
- Understanding of prompt engineering principles
- Familiarity with data retrieval concepts
- 30+ agent executions completed
- Model Context Protocol (MCP) proficiency demonstrated

-----

## **Module Overview**

**Target Audience:** Block 3 graduates who need to build knowledge-enabled AI agents that can access, retrieve, and reason over enterprise knowledge bases for consulting client engagements.

**Learning Objectives:**
- Understand RAG architecture patterns and when to apply them
- Design effective chunking and embedding strategies
- Implement retrieval patterns (semantic, hybrid, re-ranking)
- Integrate knowledge systems with agent workflows
- Evaluate and measure RAG system quality
- Make production deployment decisions for enterprise RAG

**Capstone:** Knowledge-Enabled Agent System
- RAG architecture design document
- Chunking strategy with rationale
- Retrieval pipeline implementation
- Agent integration demonstration
- Evaluation framework with metrics

-----

## **Week 1: RAG Fundamentals**

### **Entry Criteria**

- [ ] Block 3 completed with working agent system
- [ ] Understanding of vector similarity concepts (conceptual)
- [ ] Access to sample documents for testing
- [ ] Familiarity with API-based model interactions

### **Exit Criteria**

- [ ] RAG architecture patterns understood
- [ ] Chunking strategies mastered
- [ ] Embedding concepts clear
- [ ] Basic retrieval pipeline designed
- [ ] First RAG prototype functional

-----

### **Workshop Content (45 minutes)**

**Segment 1: RAG Architecture Fundamentals (12 min)**

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

**Segment 2: Document Chunking Strategies (12 min)**

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

**Segment 3: Embedding and Vector Storage (12 min)**

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

**Segment 4: Basic Retrieval Pipeline (9 min)**

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

### **Self-Paced Exercises (75 minutes total)**

**Exercise 1.1: RAG Architecture Design (25 minutes)**

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

**Exercise 1.2: Implement Chunking Pipeline (30 minutes)**

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

**Exercise 1.3: Basic Retrieval Testing (20 minutes)**

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

## **Week 2: Production RAG & Agent Integration**

### **Entry Criteria**

- [ ] RAG architecture designed
- [ ] Chunking pipeline implemented
- [ ] Basic retrieval tested
- [ ] Understanding of retrieval quality issues

### **Exit Criteria**

- [ ] Advanced retrieval patterns implemented
- [ ] Agent-RAG integration functional
- [ ] Evaluation framework established
- [ ] Production considerations documented
- [ ] Module capstone completed

-----

### **Workshop Content (45 minutes)**

**Segment 1: Advanced Retrieval Patterns (12 min)**

- **Hybrid search:**
  ```
  Query → [Semantic Search] → Candidates (vector similarity)
       → [Keyword Search]  → Candidates (BM25/TF-IDF)
       → [Fusion]          → Combined ranking
  ```
  - Combines semantic understanding with exact matching
  - Better for technical terms, names, codes
  - Reciprocal Rank Fusion (RRF) common fusion method

- **Query transformation:**
  ```
  Original Query: "What's our vacation policy?"
       ↓
  [Query Expansion]
  Expanded: "vacation policy PTO paid time off leave days"
       ↓
  [Hypothetical Document Embedding (HyDE)]
  Generate hypothetical answer → embed that → search
       ↓
  [Multi-query]
  Split into sub-queries → retrieve for each → merge
  ```

- **Re-ranking:**
  ```
  Initial retrieval (top-50, fast)
       ↓
  Re-ranker model (cross-encoder)
       ↓
  Final ranking (top-5, high quality)
  ```
  - Cross-encoders more accurate than bi-encoders
  - Computationally expensive (use on small candidate set)
  - Significant quality improvement

- **Contextual compression:**
  ```
  Retrieved chunk (500 tokens)
       ↓
  [Compression LLM]
       ↓
  Compressed chunk (100 tokens, query-relevant only)
  ```
  - Reduces context size
  - Focuses on query-relevant portions
  - Additional latency and cost trade-off

**Segment 2: Agent + RAG Integration Patterns (12 min)**

- **Pattern 1: RAG as Tool**
  ```
  Agent
    ├── Tool: search_knowledge_base(query)
    │     └── Returns: relevant chunks + sources
    ├── Tool: other_tools...
    └── Decides when to search knowledge
  ```
  - Agent controls retrieval timing
  - Natural fit for tool-using agents
  - Agent can refine queries

- **Pattern 2: RAG as Context**
  ```
  User Query
       ↓
  [Pre-retrieval] ← Always retrieves context
       ↓
  Agent (with context injected)
       ↓
  Response
  ```
  - Automatic context augmentation
  - Simpler agent logic
  - May retrieve when not needed

- **Pattern 3: Agentic RAG**
  ```
  Query → [Router Agent]
               ↓
         ┌─────┴─────┐
         ↓           ↓
  [Search Agent] [Other Agents]
         ↓
  [Retrieval Chain]
   - Query analysis
   - Multi-source search
   - Result synthesis
         ↓
  [Response Agent]
  ```
  - Most sophisticated
  - Multi-step retrieval
  - Query decomposition

- **Integration decision framework:**

  | Scenario | Recommended Pattern |
  |----------|---------------------|
  | Simple Q&A | RAG as Context |
  | Complex tasks with knowledge needs | RAG as Tool |
  | Research/analysis tasks | Agentic RAG |
  | Mixed tasks (some need KB, some don't) | RAG as Tool |

**Segment 3: RAG Evaluation Framework (12 min)**

- **Evaluation dimensions:**
  ```
  RAG Quality
    ├── Retrieval Quality
    │     ├── Precision: % retrieved that are relevant
    │     ├── Recall: % relevant that are retrieved
    │     └── MRR: Mean Reciprocal Rank
    │
    └── Generation Quality
          ├── Faithfulness: Response matches retrieved context
          ├── Relevance: Response answers the question
          └── Completeness: All aspects addressed
  ```

- **Retrieval metrics:**

  | Metric | Formula | Use When |
  |--------|---------|----------|
  | Precision@k | relevant_retrieved / k | Care about noise in results |
  | Recall@k | relevant_retrieved / total_relevant | Care about missing info |
  | MRR | 1 / rank_of_first_relevant | Care about top result |
  | NDCG | Normalized ranking quality | Care about full ranking |

- **Generation metrics:**

  | Metric | Measures | Evaluation Method |
  |--------|----------|-------------------|
  | Faithfulness | Grounded in context | LLM-as-judge or human |
  | Answer relevance | Answers the question | LLM-as-judge or human |
  | Context relevance | Retrieved context useful | Automated metrics |

- **Building evaluation sets:**
  ```json
  {
    "test_cases": [
      {
        "query": "What is the parental leave policy?",
        "expected_chunks": ["policy-ch5-p23", "faq-parental"],
        "expected_answer_contains": ["12 weeks", "paid"],
        "category": "policy_lookup"
      }
    ]
  }
  ```

**Segment 4: Production RAG Considerations (9 min)**

- **Scaling challenges:**

  | Challenge | Solutions |
  |-----------|-----------|
  | Index size | Sharding, tiered storage |
  | Query latency | Caching, ANN tuning |
  | Update frequency | Incremental indexing |
  | Cost | Embedding caching, batch processing |

- **Security considerations:**
  ```
  Access Control in RAG
    ├── Document-level ACLs → Metadata filtering
    ├── User context → Query-time filtering
    ├── Chunk inheritance → Propagate from parent doc
    └── Audit logging → Track what was retrieved
  ```

- **Freshness and updates:**
  ```
  Update Strategy Options:

  1. Full rebuild (simple, slow)
     - Rebuild index on schedule
     - Good for static content

  2. Incremental (complex, fast)
     - Detect changes
     - Update only affected chunks
     - Handle deletions carefully

  3. Hybrid
     - Incremental for additions
     - Periodic full rebuild for cleanup
  ```

- **Monitoring in production:**
  - Retrieval latency (p50, p95, p99)
  - Empty result rate
  - User feedback signals
  - Cost per query
  - Cache hit rate

-----

### **Self-Paced Exercises (75 minutes total)**

**Exercise 2.1: Implement Advanced Retrieval (25 minutes)**

*Add hybrid search and re-ranking to your pipeline*

```markdown
# Advanced Retrieval Implementation

## Baseline Performance (from Week 1)
- Average Precision@3: [X]
- Average Precision@5: [X]
- Problem queries: [List]

## Hybrid Search Implementation

### Configuration
```json
{
  "hybrid_search": {
    "semantic_weight": 0.7,
    "keyword_weight": 0.3,
    "fusion_method": "rrf",
    "keyword_fields": ["content", "title", "section"]
  }
}
```

### Test Results

| Query | Semantic Only P@3 | Keyword Only P@3 | Hybrid P@3 |
|-------|-------------------|------------------|------------|
| [Q1] | | | |
| [Q2] | | | |
| [Q3] | | | |
| **Average** | | | |

### Hybrid Search Observations
- [When hybrid helps]
- [When hybrid doesn't help]
- [Optimal weight balance]

## Re-ranking Implementation

### Configuration
```json
{
  "reranking": {
    "model": "[re-ranker model]",
    "initial_candidates": 20,
    "final_top_k": 5
  }
}
```

### Test Results

| Query | Before Re-rank P@5 | After Re-rank P@5 | Latency Added |
|-------|--------------------|--------------------|---------------|
| [Q1] | | | |
| [Q2] | | | |
| [Q3] | | | |
| **Average** | | | |

## Query Transformation (Optional)

### Technique Tested: [HyDE/Multi-query/Expansion]

### Results
[Document findings]

## Final Pipeline Configuration
```json
{
  "retrieval_pipeline": {
    "stage_1": "hybrid_search",
    "stage_1_k": 20,
    "stage_2": "reranker",
    "stage_2_k": 5,
    "total_latency_target": "< 2s"
  }
}
```

## Performance Summary

| Metric | Baseline | After Improvements | Change |
|--------|----------|-------------------|--------|
| Precision@3 | | | |
| Precision@5 | | | |
| MRR | | | |
| Avg latency | | | |
```

**Deliverable:** Advanced retrieval implementation + comparison analysis

-----

**Exercise 2.2: Agent-RAG Integration (25 minutes)**

*Connect your RAG system to your agent*

```markdown
# Agent-RAG Integration

## Integration Pattern Chosen
- **Pattern:** [RAG as Tool / RAG as Context / Agentic RAG]
- **Rationale:** [Why this pattern]

## Implementation

### RAG Tool Definition (if RAG as Tool)
```json
{
  "tool": {
    "name": "search_knowledge_base",
    "description": "Search the company knowledge base for relevant information. Use this when you need to answer questions about policies, procedures, or company-specific information.",
    "parameters": {
      "query": {
        "type": "string",
        "description": "The search query - be specific and include relevant terms"
      },
      "filters": {
        "type": "object",
        "description": "Optional filters for document type, date range, etc."
      }
    }
  }
}
```

### Agent System Prompt
```
You are an assistant with access to the company knowledge base.

When users ask questions about company policies, procedures, or
internal information, use the search_knowledge_base tool to find
relevant information.

Guidelines:
- Search before answering company-specific questions
- Cite your sources (document name, section)
- If information isn't found, say so clearly
- Don't make up information not in the knowledge base
```

### Context Injection Template (if RAG as Context)
```
System: [Base system prompt]

Relevant Knowledge:
---
{retrieved_context_formatted}
---

Use the above knowledge to inform your response when relevant.
```

## Test Scenarios

### Scenario 1: Direct knowledge question
- **User query:** [Query requiring KB lookup]
- **Agent behavior:** [Did it search? What query?]
- **Retrieved context:** [Summary]
- **Agent response:** [Summary]
- **Quality assessment:** [Good/Issues]

### Scenario 2: Question not in knowledge base
- **User query:** [Query with no KB match]
- **Agent behavior:** [How did it handle?]
- **Agent response:** [Summary]
- **Quality assessment:** [Appropriately indicated no info?]

### Scenario 3: Multi-turn conversation with knowledge
- **Turn 1:** [Query]
- **Agent response:** [Response with KB context]
- **Turn 2:** [Follow-up query]
- **Agent behavior:** [Did it search again? Use context?]
- **Quality assessment:** [Handled context well?]

### Scenario 4: Mixed task (some KB, some not)
- **User query:** [Complex query]
- **Agent behavior:** [When did it use KB?]
- **Quality assessment:** [Appropriate tool use?]

## Integration Issues Found
1. **Issue:** [Description]
   - **Impact:** [Effect]
   - **Fix:** [Solution]

## Final Integration Configuration
```json
{
  "agent_rag_config": {
    "pattern": "[chosen]",
    "retrieval_trigger": "[condition]",
    "context_format": "[template]",
    "max_context_tokens": 2000,
    "citation_format": "[format]"
  }
}
```
```

**Deliverable:** Working agent-RAG integration + test documentation

-----

**Exercise 2.3: Module Capstone - Knowledge-Enabled Agent System (25 minutes)**

*Complete your RAG-powered agent system*

```markdown
# Module Capstone: Knowledge-Enabled Agent System

## System Overview

### Purpose
[What knowledge problem does this agent solve?]

### Target Users
[Who will use this system?]

### Knowledge Domain
[What knowledge is covered?]

## Architecture Summary

```
[User Query]
      ↓
[Agent] ←→ [RAG Tool/Context]
  │              ↓
  │        [Query Processing]
  │              ↓
  │        [Hybrid Retrieval]
  │              ↓
  │        [Re-ranking]
  │              ↓
  │        [Context Assembly]
  │              ↓
[Response Generation]
      ↓
[Cited Response to User]
```

### Key Components

| Component | Implementation | Configuration |
|-----------|----------------|---------------|
| Chunking | [Strategy] | [Key settings] |
| Embeddings | [Model] | [Dimensions] |
| Vector Store | [Solution] | [Index type] |
| Retrieval | [Hybrid/Semantic] | [Top-k, etc.] |
| Re-ranking | [Model/None] | [Settings] |
| Agent Integration | [Pattern] | [Settings] |

## Evaluation Results

### Retrieval Quality

| Metric | Value | Target | Status |
|--------|-------|--------|--------|
| Precision@3 | | >0.7 | |
| Precision@5 | | >0.6 | |
| MRR | | >0.8 | |

### Generation Quality

| Metric | Value | Target | Status |
|--------|-------|--------|--------|
| Faithfulness | | >0.9 | |
| Answer Relevance | | >0.8 | |
| Citation Accuracy | | >0.95 | |

### End-to-End Testing

| Test Case | Query | Expected | Actual | Pass/Fail |
|-----------|-------|----------|--------|-----------|
| Simple lookup | [Query] | [Expected] | [Actual] | |
| Complex query | | | | |
| Out of scope | | | | |
| Edge case | | | | |

## Production Readiness Assessment

### Security
- [ ] Access control implemented
- [ ] User context filtering works
- [ ] Audit logging in place
- [ ] No data leakage between users

### Performance
- [ ] Query latency < [target]
- [ ] Can handle [X] concurrent users
- [ ] Caching strategy implemented
- [ ] Cost per query within budget

### Maintenance
- [ ] Update procedure documented
- [ ] Monitoring dashboards ready
- [ ] Alert thresholds defined
- [ ] Backup/recovery tested

## Lessons Learned

### What Worked Well
1. [Lesson]
2. [Lesson]

### Challenges Encountered
1. **Challenge:** [Description]
   - **Solution:** [How resolved]

### Recommendations for Production
1. [Recommendation]
2. [Recommendation]
3. [Recommendation]

## Demo Script

### Setup
[Prerequisites for demo]

### Demo Flow
1. [Step 1: Show agent handling non-KB query]
2. [Step 2: Show KB lookup with citation]
3. [Step 3: Show multi-turn conversation]
4. [Step 4: Show edge case handling]

### Key Points to Highlight
- [Point 1]
- [Point 2]
- [Point 3]
```

**Deliverable:** Complete capstone documentation + working demonstration

-----

# **APPENDICES**

## **Appendix A: RAG Architecture Template**

```markdown
# RAG Architecture Template

## System Configuration

```json
{
  "rag_system": {
    "name": "[System Name]",
    "version": "1.0",

    "ingestion": {
      "sources": [
        {
          "name": "[Source Name]",
          "type": "pdf|web|database|api",
          "connection": "[Connection details]",
          "schedule": "manual|daily|hourly|realtime"
        }
      ],
      "chunking": {
        "strategy": "fixed|semantic|hierarchical",
        "chunk_size": 500,
        "chunk_overlap": 50,
        "separators": ["\n\n", "\n", ". "]
      },
      "metadata_extraction": {
        "fields": ["title", "section", "date", "author"],
        "custom_extractors": []
      }
    },

    "embedding": {
      "model": "[Model name]",
      "dimensions": 1536,
      "batch_size": 100,
      "cache_enabled": true
    },

    "vector_store": {
      "type": "[Vector DB type]",
      "index_type": "hnsw|ivf|flat",
      "similarity_metric": "cosine|euclidean|dot",
      "index_params": {
        "m": 16,
        "ef_construction": 200
      }
    },

    "retrieval": {
      "search_type": "semantic|hybrid",
      "top_k": 5,
      "similarity_threshold": 0.7,
      "reranking": {
        "enabled": true,
        "model": "[Re-ranker model]",
        "top_k_rerank": 3
      },
      "filters": {
        "default": {},
        "user_context_field": "access_level"
      }
    },

    "generation": {
      "context_template": "[Template for formatting context]",
      "max_context_tokens": 3000,
      "citation_format": "inline|footnote|none"
    }
  }
}
```

## Component Selection Guide

### Chunking Strategy Selection
```
IF document_type == "structured" (code, legal, technical):
  USE semantic chunking (respect boundaries)
ELIF document_type == "conversational":
  USE turn-based chunking
ELIF document_type == "long_form_prose":
  USE fixed chunking with overlap
ELIF document_quality == "critical":
  USE agentic chunking (LLM-assisted)
```

### Retrieval Strategy Selection
```
IF query_type == "exact_match_needed" (names, codes, IDs):
  USE hybrid search (weight keyword higher)
ELIF query_type == "conceptual":
  USE semantic search
ELIF quality_critical == true:
  USE semantic + reranking
```
```

-----

## **Appendix B: Chunking Strategy Guide**

```markdown
# Chunking Strategy Decision Guide

## Decision Tree

```
Document Type?
├── Technical Documentation
│   ├── Has clear sections? → Semantic (by section)
│   └── Dense, continuous? → Fixed (400-600 tokens, 50 overlap)
│
├── Legal/Contracts
│   ├── Clause structure? → Semantic (by clause)
│   └── Narrative style? → Fixed (300-400 tokens, 100 overlap)
│
├── Code/Scripts
│   ├── Well-documented? → By function/class with docstrings
│   └── Minimal comments? → By logical blocks
│
├── FAQ/Q&A
│   └── → By question-answer pair
│
├── Emails/Messages
│   └── → By message/turn
│
└── General Documents
    ├── Structured (headers)? → Semantic (by heading)
    └── Unstructured? → Fixed (500 tokens, 50 overlap)
```

## Chunk Size Guidelines

| Content Density | Recommended Size | Rationale |
|-----------------|------------------|-----------|
| Dense (technical, legal) | 300-500 tokens | More focused retrieval |
| Medium (business docs) | 500-700 tokens | Balance context/precision |
| Sparse (conversational) | 700-1000 tokens | Need surrounding context |

## Overlap Guidelines

| Scenario | Recommended Overlap |
|----------|---------------------|
| Independent chunks | 0-25 tokens |
| Related content flows | 50-100 tokens |
| Highly connected content | 100-150 tokens |

## Quality Validation Checklist

For each chunk, verify:
- [ ] Chunk is semantically coherent (one topic)
- [ ] Chunk has enough context to be understood alone
- [ ] No critical information split across chunks
- [ ] Metadata correctly inherited
- [ ] Size within target range (+/- 20%)
```

-----

## **Appendix C: RAG Evaluation Framework**

```markdown
# RAG Evaluation Framework

## Evaluation Dimensions

### 1. Retrieval Evaluation

#### Metrics
```python
# Precision@k
precision_k = relevant_in_top_k / k

# Recall@k
recall_k = relevant_in_top_k / total_relevant

# Mean Reciprocal Rank
mrr = 1 / rank_of_first_relevant

# Normalized Discounted Cumulative Gain
ndcg = dcg / ideal_dcg
```

#### Test Set Structure
```json
{
  "retrieval_tests": [
    {
      "id": "RT-001",
      "query": "What is the remote work policy?",
      "relevant_chunk_ids": ["policy-ch3-p12", "policy-ch3-p13"],
      "category": "policy_lookup",
      "difficulty": "easy"
    }
  ]
}
```

### 2. Generation Evaluation

#### Faithfulness (Groundedness)
```
Score 1-5:
5 - All claims supported by retrieved context
4 - Minor claims unsupported but not contradictory
3 - Some claims unsupported
2 - Significant unsupported claims
1 - Contradicts retrieved context
```

#### Answer Relevance
```
Score 1-5:
5 - Directly and completely answers the question
4 - Answers question with minor gaps
3 - Partially answers question
2 - Tangentially related
1 - Does not address question
```

#### Citation Accuracy
```
Score 1-5:
5 - All citations accurate, sources traceable
4 - Minor citation issues
3 - Some citations missing or incorrect
2 - Major citation problems
1 - No citations or all incorrect
```

### 3. End-to-End Evaluation

#### Test Case Template
```json
{
  "e2e_tests": [
    {
      "id": "E2E-001",
      "user_query": "How many vacation days do I get in my first year?",
      "expected_answer_contains": ["10 days", "15 days after one year"],
      "expected_sources": ["policy-handbook"],
      "category": "hr_policy",
      "acceptable_alternatives": ["10-15 days depending on start date"]
    }
  ]
}
```

## Evaluation Process

### Automated Evaluation
```
1. Run retrieval tests
   - Calculate precision, recall, MRR
   - Flag queries below threshold

2. Run generation tests (LLM-as-judge)
   - Evaluate faithfulness
   - Evaluate relevance
   - Check citations

3. Generate report
   - Aggregate metrics
   - Identify problem areas
   - Track trends
```

### Human Evaluation (Sample)
```
1. Select random sample (20-50 queries)
2. Human evaluators score:
   - Answer quality (1-5)
   - Citation accuracy (1-5)
   - Would use this answer (Y/N)
3. Compare with automated scores
4. Calibrate automated evaluation
```

## Benchmark Targets

| Metric | Minimum | Good | Excellent |
|--------|---------|------|-----------|
| Precision@3 | 0.5 | 0.7 | 0.85 |
| Precision@5 | 0.4 | 0.6 | 0.75 |
| MRR | 0.6 | 0.8 | 0.9 |
| Faithfulness | 3.5 | 4.0 | 4.5 |
| Answer Relevance | 3.5 | 4.0 | 4.5 |
| E2E Pass Rate | 70% | 85% | 95% |
```

-----

## **Appendix D: Module Evaluation Rubric**

```markdown
# RAG & Knowledge Systems - Evaluation Rubric

**Total Points: 20 (4 criteria x 5 points each)**

## Criterion 1: RAG Architecture Design (5 points)

| Score | Description |
|-------|-------------|
| 5 | Comprehensive architecture with clear rationale for all decisions. Appropriate chunking, embedding, and retrieval choices. Production considerations addressed. |
| 4 | Good architecture design. Sound decisions with adequate rationale. Most components well-specified. |
| 3 | Basic architecture documented. Some decisions lack rationale. Key components covered. |
| 2 | Incomplete architecture. Poor or missing rationale. Gaps in design. |
| 1 | No meaningful architecture design. |

## Criterion 2: Retrieval Quality (5 points)

| Score | Description |
|-------|-------------|
| 5 | Excellent retrieval performance. Hybrid search and re-ranking implemented. Metrics exceed targets. Clear improvement over baseline. |
| 4 | Good retrieval quality. Advanced patterns attempted. Metrics meet targets. |
| 3 | Basic retrieval working. Meets minimum thresholds. Some optimization attempted. |
| 2 | Retrieval functional but quality issues. Below target metrics. |
| 1 | Retrieval not working or extremely poor quality. |

## Criterion 3: Agent Integration (5 points)

| Score | Description |
|-------|-------------|
| 5 | Seamless agent-RAG integration. Appropriate pattern selection. Agent uses knowledge effectively. Handles edge cases gracefully. |
| 4 | Good integration. Agent accesses knowledge appropriately. Most scenarios handled well. |
| 3 | Basic integration working. Agent can retrieve and use knowledge. Some edge cases fail. |
| 2 | Integration attempted but unreliable. Agent misuses knowledge tool. |
| 1 | No working agent-RAG integration. |

## Criterion 4: Evaluation & Documentation (5 points)

| Score | Description |
|-------|-------------|
| 5 | Comprehensive evaluation framework. Metrics tracked and reported. Clear documentation. Production readiness assessed. Lessons learned captured. |
| 4 | Good evaluation with key metrics. Adequate documentation. Most areas covered. |
| 3 | Basic evaluation. Some metrics tracked. Documentation present but incomplete. |
| 2 | Limited evaluation. Poor documentation. Few metrics. |
| 1 | No evaluation or documentation. |

## Passing Criteria

- **Pass:** 14+ points total, no criterion below 3
- **Pass with Distinction:** 18+ points total, no criterion below 4
```

-----

**END OF ADVANCED MODULE 8**
