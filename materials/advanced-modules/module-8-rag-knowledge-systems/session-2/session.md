# **Advanced Module 8: RAG & Knowledge Systems**
## **Session 2: Production RAG & Agent Integration**

**Duration:** 45 min live + 75 min homework

-----

## **Entry Criteria**

- [ ] RAG architecture designed
- [ ] Chunking pipeline implemented
- [ ] Basic retrieval tested
- [ ] Understanding of retrieval quality issues

## **Exit Criteria**

- [ ] Advanced retrieval patterns implemented
- [ ] Agent-RAG integration functional
- [ ] Evaluation framework established
- [ ] Production considerations documented
- [ ] Module capstone completed

-----

## **Workshop Content (45 minutes)**

### **Segment 1: Advanced Retrieval Patterns (12 min)**

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

### **Segment 2: Agent + RAG Integration Patterns (12 min)**

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

### **Segment 3: RAG Evaluation Framework (12 min)**

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

### **Segment 4: Production RAG Considerations (9 min)**

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

## **Self-Paced Exercises (75 minutes total)**

### **Exercise 2.1: Implement Advanced Retrieval (25 minutes)**

*Add hybrid search and re-ranking to your pipeline*

```markdown
# Advanced Retrieval Implementation

## Baseline Performance (from Session 1)
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

### **Exercise 2.2: Agent-RAG Integration (25 minutes)**

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

### **Exercise 2.3: Module Capstone - Knowledge-Enabled Agent System (25 minutes)**

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
