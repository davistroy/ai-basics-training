# **ADVANCED MODULE 8 SESSION 1: RAG FUNDAMENTALS**

**Module:** Advanced Module 8: RAG & Knowledge Systems
**Session:** 1 of 2
**Estimated Self-Paced Time:** 75 minutes

---

## Navigation

**Session Navigation:** N/A (Session 1) | **Session 1** | [Session 2 →](../session-2/participant-guide.md)

**In This Guide:**
- [Learning Objectives](#learning-objectives)
- [Entry Criteria](#entry-criteria)
- [Key Concepts](#key-concepts)
- [Workshop Recap](#workshop-recap)
- [Self-Paced Exercises](#self-paced-exercises)
- [Templates & Resources](#templates--resources)
- [Self-Assessment](#self-assessment)
- [Getting Help](#getting-help)

---

## Learning Objectives

By the end of this session, you will be able to:

| # | Objective | Practiced In |
|---|-----------|--------------|
| 1 | Design RAG architectures appropriate for enterprise use cases | Exercise 1.1 |
| 2 | Implement effective chunking strategies for different document types | Exercise 1.2 |
| 3 | Configure embedding models and vector databases for retrieval | Exercise 1.1, 1.3 |
| 4 | Build retrieval pipelines with proper context formatting | Exercise 1.3 |

---

## Entry Criteria

Before starting this session, confirm you have completed:

- [ ] Block 3: AI Automation Architecture (certified)
- [ ] Working agent system with tool-use capabilities
- [ ] Understanding of vector similarity concepts (conceptual level is fine)
- [ ] Access to sample documents for testing (policies, documentation, etc.)

**Not ready?** Review [Block 3](../../block-3/block-3.md) materials or reach out in [support channel] for help.

---

## Key Concepts

### Concept 1: Retrieval-Augmented Generation (RAG)

**Definition:**
RAG is a technique that enhances LLM responses by retrieving relevant information from external knowledge sources before generation, grounding responses in actual documents rather than relying on model memory.

**Why It Matters:**
Enterprise agents need access to current, domain-specific knowledge that changes frequently. RAG provides this while maintaining citations for compliance and audit trails.

**Core Principle:**
> "Retrieve first, then generate. Never ask the model to remember what it can look up."

**The RAG Pipeline:**
```
[Documents] → [Chunking] → [Embedding] → [Vector Store]
                                              ↓
[Query] → [Query Embedding] → [Search] → [Retrieved Chunks]
                                              ↓
                                    [LLM + Context] → [Response]
```

**Common Mistake:**
Trying to fit entire documents into the context window instead of retrieving only relevant sections. This wastes tokens and degrades performance.

---

### Concept 2: Document Chunking

**Definition:**
Chunking is the process of splitting documents into smaller, semantically coherent units for embedding and retrieval.

**Why It Matters:**
Chunk quality directly determines retrieval quality. Poor chunking (e.g., splitting mid-sentence) causes retrieval failures even with perfect embeddings and search.

**The Pattern:**
```
Document → Analyze Structure → Apply Strategy → Generate Chunks + Metadata
```

**Four Main Strategies:**

| Strategy | When to Use | Chunk Size | Overlap |
|----------|-------------|------------|---------|
| **Fixed-size** | General prose, unstructured text | 400-600 tokens | 50-100 tokens |
| **Semantic** | Structured docs (sections, clauses) | Variable | 50-100 tokens |
| **Hierarchical** | Complex docs needing multi-level retrieval | Variable | Depends on level |
| **Agentic** | Critical documents, highest quality needs | Variable | LLM-determined |

**When to Use:**
- Fixed-size: Starting point, general documents
- Semantic: Technical documentation, legal contracts, structured content
- Hierarchical: Large documents where you need section summaries and details
- Agentic: High-stakes documents where chunking errors are costly

**When NOT to Use:**
- Don't use agentic chunking for every document (too expensive)
- Don't use hierarchical chunking for simple, flat documents
- Don't use fixed chunking for highly structured content with clear boundaries

---

### Concept 3: Embeddings and Vector Search

**Definition:**
Embeddings are dense vector representations of text that capture semantic meaning, enabling similarity search based on concepts rather than keywords.

**Key Components:**

| Component | Description | Example |
|-----------|-------------|---------|
| **Embedding Model** | Converts text to vectors | OpenAI text-embedding-3-small |
| **Vector Dimensions** | Size of the vector | 1536 dimensions |
| **Similarity Metric** | How to measure closeness | Cosine similarity |
| **Vector Database** | Stores and searches vectors | Pinecone, Qdrant, Weaviate |

**Visual Reference:**
```
Text Chunks in Vector Space:

    "Vacation Policy"    "PTO Benefits"
           ●──────────────●  ← Close together (similar meaning)



           ●  "Office Location"  ← Far away (different meaning)
```

**How It Works:**
1. Text → Embedding model → Vector representation
2. Similar meanings → Similar vectors (close in vector space)
3. Query gets embedded → Search for nearest vectors → Retrieve chunks

---

### Concept 4: Retrieval Pipeline

**Definition:**
The retrieval pipeline is the end-to-end process of converting a user query into retrieved, formatted context for the LLM.

**The Steps:**
```
1. Query arrives
2. Embed query (same model as chunks)
3. Similarity search (find top-k nearest vectors)
4. Apply metadata filters (optional)
5. Rank results by similarity
6. Format chunks for LLM context
7. Generate response with citations
```

**Critical Parameters:**

| Parameter | Typical Value | Purpose |
|-----------|---------------|---------|
| **Top-k** | 3-10 chunks | How many results to retrieve |
| **Similarity threshold** | 0.7+ (optional) | Filter low-quality matches |
| **Similarity metric** | Cosine | How to measure vector closeness |
| **Context template** | Structured format | How to present chunks to LLM |

---

### Quick Reference: RAG vs. Alternatives

| Approach | Best For | Cost | Update Speed | Citations |
|----------|----------|------|--------------|-----------|
| **RAG** | Dynamic knowledge, large corpora | Low ongoing | Instant | Yes |
| **Fine-tuning** | Style/behavior, static knowledge | High upfront | Slow (retrain) | No |
| **Long Context** | Fixed, small documents (< 50 pages) | High per query | Instant | Manual |

**Decision Rule:**
- Need citations? → RAG
- Knowledge changes frequently? → RAG
- Need custom style/behavior? → Fine-tuning
- Small, fixed documents? → Long context
- Large, dynamic knowledge? → RAG (almost always)

---

## Workshop Recap

### Session Summary

**Today's Focus:** Understanding RAG fundamentals - architecture, chunking strategies, embeddings, and basic retrieval pipelines.

**Key Points from Each Segment:**

**Segment 1: RAG Architecture Fundamentals**
- RAG retrieves relevant information before generation, grounding responses in actual documents
- Core pipeline: Index (chunk → embed → store) + Retrieval (search → format → generate)
- Choose RAG for dynamic knowledge and citations; fine-tuning for behavior; long context for small, fixed docs
- Quality depends on retrieval quality - garbage in, garbage out

**Segment 2: Document Chunking Strategies**
- Chunking quality determines retrieval quality
- Four strategies: fixed-size (simple), semantic (structured), hierarchical (multi-level), agentic (highest quality)
- Decision framework: document type → chunking strategy + chunk size + overlap
- Too large chunks = noise; too small chunks = fragmentation

**Segment 3: Embedding and Vector Storage**
- Embeddings convert text to vectors that capture semantic meaning
- Similar meanings → similar vectors → enables concept-based search
- Embedding model selection: balance quality, cost, domain specificity
- Vector databases enable fast ANN search with metadata filtering
- Metadata strategy critical for filtering, citations, access control

**Segment 4: Basic Retrieval Pipeline**
- Pipeline: query → embed → search → filter → rank → format → generate
- Top-k typically 3-10 chunks (balance coverage and precision)
- Cosine similarity most common metric
- Context formatting must include source attribution and instructions to cite

---

## Self-Paced Exercises

**Total Time:** 75 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 1.1 | 25 min | `rag-architecture-design.md` | Architecture design and component selection |
| 1.2 | 30 min | Chunking implementation + analysis | Chunking strategies and quality |
| 1.3 | 20 min | `retrieval-quality-test.md` | Retrieval testing and metrics |

**Important:** Complete exercises in order - each builds on the previous one.

---

### Exercise 1.1: RAG Architecture Design

**Duration:** 25 minutes

**Purpose:**
Design a complete RAG architecture for a real enterprise use case, making informed decisions about components and documenting rationale.

**You Will Create:**
A comprehensive architecture design document with justified component choices

---

#### Instructions

**Step 1: Define Your Use Case (5 minutes)**

Choose a real or realistic enterprise knowledge problem:
- Employee knowledge base (policies, procedures)
- Technical documentation system
- Legal document repository
- Research paper collection
- Customer support knowledge base

Document:
- What knowledge problem are you solving?
- Who are the users?
- What questions do they need answered?

**Step 2: Identify Knowledge Sources (5 minutes)**

For each source in your system, document:
- Type (PDF, web pages, database, API)
- Size (estimated documents/pages)
- Update frequency (static, daily, real-time)
- Access control requirements

You need at least 2 sources, preferably 3-5.

**Step 3: Design Architecture Components (10 minutes)**

Make and document decisions for:

1. **Chunking Strategy**
   - Which strategy? (fixed, semantic, hierarchical, agentic)
   - Chunk size and overlap?
   - Rationale for your choice?

2. **Embedding Model**
   - Which model? (OpenAI, Cohere, open-source)
   - Dimensions?
   - Why this model?

3. **Vector Store**
   - Which database? (Pinecone, Qdrant, Weaviate, pgvector)
   - Index type?
   - Why this choice?

4. **Retrieval Configuration**
   - Top-k value?
   - Similarity metric?
   - Metadata filters?
   - Rationale?

**Step 4: Document Challenges (5 minutes)**

Identify 3 expected challenges and mitigation strategies:
- Technical challenges (scale, performance)
- Data challenges (quality, structure)
- Operational challenges (updates, access control)

---

#### Deliverable Specification

**File Name:** `rag-architecture-design.md`

**Location:** Your project repository (create `rag-system/` folder)

**Format Requirements:**
- Use the template provided below
- Include rationale for every major decision
- Be specific (not "an embedding model" but "OpenAI text-embedding-3-small")
- Document trade-offs considered

**Quality Criteria:**
- [ ] Clear use case definition with specific user needs
- [ ] At least 2 knowledge sources documented with details
- [ ] All architecture components specified with rationale
- [ ] At least 3 challenges identified with mitigations
- [ ] Demonstrates understanding of trade-offs

---

#### Template

```markdown
# RAG Architecture Design

## System Purpose
[What knowledge problem are you solving? Be specific about user needs.]

## Knowledge Sources

### Source 1: [Name]
- **Type:** [PDF/Web/Database/API]
- **Size:** [Estimated documents/pages]
- **Update frequency:** [Static/Daily/Real-time]
- **Access control:** [Public/Internal/Restricted]
- **Current location:** [Where does this data live?]

### Source 2: [Name]
[Repeat for each source]

## Architecture Diagram
```
[Document Sources]
      ↓
[Ingestion Pipeline]
  - Document parsing: [Tools/libraries]
  - Chunking strategy: [Fixed/Semantic/Hierarchical/Agentic]
  - Metadata extraction: [Fields]
      ↓
[Embedding Service]
  - Model: [Specific model name]
  - Dimensions: [Number]
  - Batch size: [If relevant]
      ↓
[Vector Store]
  - Type: [Specific database]
  - Index type: [HNSW/IVF/etc.]
  - Similarity metric: [Cosine/Euclidean/Dot]
      ↓
[Retrieval Service]
  - Search type: [Semantic/Hybrid]
  - Top-k: [Number]
  - Filters: [Metadata filters]
  - Re-ranking: [Yes/No]
      ↓
[Context Assembly]
  - Template: [Basic format]
  - Max context tokens: [Limit]
      ↓
[LLM Generation]
  - Model: [Which LLM]
  - Temperature: [Setting]
```

## Design Decisions

### Chunking Strategy
- **Chosen approach:** [Strategy name]
- **Chunk size:** [Tokens]
- **Overlap:** [Tokens]
- **Rationale:** [Why this approach for these documents?]
- **Trade-offs considered:** [What did you choose NOT to do and why?]

### Embedding Model
- **Model:** [Specific name and version]
- **Dimensions:** [Size]
- **Rationale:** [Why this model?]
- **Cost consideration:** [Per-token cost and expected volume]

### Vector Store
- **Database:** [Specific product]
- **Index type:** [Algorithm]
- **Rationale:** [Why this database for this use case?]
- **Hosting:** [Cloud/Self-hosted]

### Retrieval Configuration
- **Top-k:** [Number]
- **Similarity threshold:** [If any]
- **Metadata filters:** [List of filters]
- **Rationale:** [Why these settings?]

### Metadata Schema
```json
{
  "chunk_id": "string",
  "source_document": "string",
  // Add all metadata fields you'll capture
}
```

## Expected Challenges

### Challenge 1: [Name]
- **Description:** [What problem do you expect?]
- **Impact:** [How serious is this?]
- **Mitigation:** [How will you address it?]

### Challenge 2: [Name]
[Repeat]

### Challenge 3: [Name]
[Repeat]

## Success Metrics
- **Retrieval precision:** [Target]
- **Response latency:** [Target]
- **Cost per query:** [Target]
- **User satisfaction:** [How measured]

## Next Steps
1. [First implementation step]
2. [Second step]
3. [Third step]
```

---

#### Tips & Troubleshooting

**Tips:**
- Start with the simplest approach that could work (fixed chunking, OpenAI embeddings, Pinecone)
- Document why you're NOT choosing alternatives (shows you considered options)
- Be realistic about your knowledge sources - use actual documents you have access to
- Think about your specific users - policy documents for employees vs. technical docs for engineers need different approaches

**Common Issues:**

| Problem | Solution |
|---------|----------|
| "I don't know which to choose" | Use the decision frameworks from the workshop. When in doubt, choose the simpler option |
| "My use case doesn't fit the templates" | Adapt the template - it's a starting point, not a straitjacket |
| "I can't estimate costs" | Look up published pricing for embedding models and vector databases, estimate based on document count |

---

### Exercise 1.2: Implement Chunking Pipeline

**Duration:** 30 minutes

**Purpose:**
Build a document chunking pipeline, test different strategies, and analyze quality to understand the impact of chunking decisions.

**You Will Create:**
Working chunking implementation with quality analysis and refined configuration

---

#### Instructions

**Step 1: Select Test Documents (5 minutes)**

Choose 3-5 representative documents for testing:
- Mix document types if possible (policy, FAQ, technical, conversational)
- Use real documents from your RAG architecture use case
- Keep total under 50 pages for this exercise

Document why you selected each:
- What type of content?
- Why is this representative?
- What chunking challenges do you expect?

**Step 2: Implement Chunking (15 minutes)**

Choose a chunking implementation approach:
- **Option A:** Use a library (LangChain, LlamaIndex, Semantic Kernel)
- **Option B:** Write simple chunking code yourself
- **Option C:** Manual chunking for small test set

Implement at least TWO strategies:
1. Fixed-size chunking
2. Semantic chunking OR another strategy relevant to your documents

For each strategy, configure:
- Chunk size (in tokens or characters)
- Overlap amount
- Separators (for semantic chunking)

Process your test documents and generate chunks.

**Step 3: Analyze Quality (10 minutes)**

For each chunking strategy:

1. **Sample 3-5 chunks** from each document
2. **Assess quality:**
   - Is the chunk semantically coherent?
   - Does it have enough context to be understood alone?
   - Was critical information split across chunks?
   - Is the size within target range?

3. **Calculate statistics:**
   - Total chunks per document
   - Average, min, max chunk size
   - How many chunks are "bad" (split concepts, too short, too long)

4. **Compare strategies:**
   - Which performed better?
   - Why?
   - What would you change?

**Step 4: Refine Configuration**

Based on your analysis:
- Adjust chunk size, overlap, or separators
- Re-chunk at least one document
- Document the improvement

---

#### Deliverable Specification

**File Name:** `chunking-implementation-analysis.md` + your code/scripts

**Location:** Your project repository `rag-system/` folder

**Format Requirements:**
- Analysis document following template below
- Include code/scripts or note which library you used
- Include sample chunks (at least 3 per document)
- Include statistics table

**Quality Criteria:**
- [ ] At least 2 chunking strategies implemented and tested
- [ ] At least 3 sample chunks analyzed per document
- [ ] Statistics calculated (total chunks, avg/min/max size)
- [ ] Quality issues identified with specific examples
- [ ] Refined configuration documented with rationale
- [ ] Clear comparison between strategies

---

#### Template

```markdown
# Chunking Implementation Analysis

## Test Documents

| Document | Type | Pages/Size | Chunking Challenges Expected |
|----------|------|------------|------------------------------|
| [Doc 1 name] | [Type] | [Size] | [What makes this challenging?] |
| [Doc 2 name] | [Type] | [Size] | [Challenge] |
| [Doc 3 name] | [Type] | [Size] | [Challenge] |

## Implementation Approach

**Library/Method:** [What did you use?]

**Reason for choice:** [Why this approach?]

## Strategy 1: Fixed-Size Chunking

### Configuration
```json
{
  "chunking_config": {
    "strategy": "fixed",
    "chunk_size": 500,
    "chunk_overlap": 50,
    "size_unit": "tokens",
    "separators": ["\n\n", "\n", ". ", " "]
  }
}
```

### Sample Chunks Analysis

#### Document: [Name]

##### Chunk 1
```
[Paste actual chunk content here]
```
- **Size:** [X tokens/chars]
- **Quality assessment:** [Good/Issues - be specific]
- **Context:** [Can this chunk be understood standalone?]

##### Chunk 2
[Repeat for 2-3 chunks per document]

### Statistics

| Document | Total Chunks | Avg Size | Min Size | Max Size | Bad Chunks |
|----------|--------------|----------|----------|----------|------------|
| [Doc 1] | | | | | |
| [Doc 2] | | | | | |
| [Doc 3] | | | | | |

### Quality Assessment

**Issues Found:**
1. **Issue:** [Description with chunk example]
   - **Chunk ID:** [Which chunk]
   - **Impact:** [Why this is a problem]

**What Worked Well:**
1. [Strength of this approach]

## Strategy 2: [Semantic/Hierarchical/Other]

### Configuration
```json
{
  "chunking_config": {
    "strategy": "[name]",
    // Your configuration
  }
}
```

[Repeat same analysis structure as Strategy 1]

## Comparison

| Metric | Fixed-Size | [Strategy 2] | Winner |
|--------|------------|--------------|--------|
| Avg chunks per doc | | | |
| Semantic coherence | [Rating 1-5] | [Rating 1-5] | |
| Context preservation | [Rating 1-5] | [Rating 1-5] | |
| Ease of implementation | [Rating 1-5] | [Rating 1-5] | |

**Overall recommendation:** [Which strategy for these documents?]

**Rationale:** [Why?]

## Refined Configuration

Based on testing, final configuration:

```json
{
  "final_chunking_config": {
    "strategy": "[chosen]",
    "chunk_size": [refined value],
    "chunk_overlap": [refined value],
    // Other parameters
  }
}
```

**Changes made from initial:**
1. [Change 1 and why]
2. [Change 2 and why]

**Expected improvement:** [What should be better now?]

## Lessons Learned

1. [Insight about chunking]
2. [Insight about your documents]
3. [What you'd do differently for production]
```

---

#### Example

**Scenario:** Chunking a company policy handbook (50 pages, structured with sections)

**Input:** Policy handbook PDF with sections like "Employee Benefits," "Time Off Policy," "Code of Conduct"

**Strategy 1: Fixed-size (500 tokens, 50 overlap)**

Sample Chunk:
```
...employees are eligible for health insurance after 90 days. The company offers three
plan options: Basic, Standard, and Premium. Basic plan includes medical and dental
coverage with a $2000 deductible. Standard plan reduces the deductible to $1000 and
adds vision coverage. Premium plan offers $500 deductible and includes all coverage
types. Employees pay a portion of premiums based on plan selection. See the benefits
enrollment guide for detailed...
```

Quality: Good - complete information, coherent topic, understandable standalone.

**Strategy 2: Semantic (by section)**

Sample Chunk:
```
Section 4.2: Health Insurance Eligibility and Options

All full-time employees are eligible for health insurance coverage beginning on the
first day of the month following 90 days of continuous employment. The company offers
three health plan options:

1. Basic Plan: Medical and dental coverage with $2000 annual deductible
2. Standard Plan: Medical, dental, and vision with $1000 deductible
3. Premium Plan: Comprehensive coverage with $500 deductible

Employees pay a portion of monthly premiums based on plan selection and number of
dependents. See the benefits enrollment guide for current premium rates and detailed
plan comparisons.
```

Quality: Excellent - natural section boundary, complete topic, includes heading for context.

**Why Semantic Works Better:**
The policy handbook has clear section structure. Semantic chunking preserves complete policy statements and includes section headers for context. Result: better retrieval when users ask "What's the health insurance policy?"

---

#### Tips & Troubleshooting

**Tips:**
- Don't overthink the implementation - a simple script or library call is fine
- Focus on the analysis, not perfect code
- Test edge cases (very short documents, documents with tables, lists)
- Include chunk numbers/IDs to reference specific chunks in your analysis

**Common Issues:**

| Problem | Solution |
|---------|----------|
| Chunks are too small/large | Adjust chunk_size parameter, re-run |
| Content split mid-concept | Increase overlap or switch to semantic chunking |
| Can't decide which is "better" | Use specific criteria: coherence (can it be understood alone?), completeness (is information split?), size (within target range?) |
| Library errors | Check token counting method, file encoding, or try a different library |

---

### Exercise 1.3: Basic Retrieval Testing

**Duration:** 20 minutes

**Purpose:**
Test retrieval quality with realistic queries, measure performance with objective metrics, and identify improvements needed.

**You Will Create:**
Retrieval quality test results with metrics and improvement recommendations

---

#### Instructions

**Step 1: Set Up Retrieval Testing (5 minutes)**

You have three options for this exercise:

**Option A: Full Implementation** (if you have time/tools)
- Embed your chunks from Exercise 1.2
- Store in a vector database (Pinecone free tier, Qdrant local, etc.)
- Implement query → retrieval flow

**Option B: Simulated Testing** (recommended for time-constrained)
- Manually select which chunks SHOULD be retrieved for each query
- Use a simple similarity matching (even keyword matching is fine for this exercise)
- Focus on the evaluation methodology

**Option C: Use Existing RAG Tool**
- LangChain, LlamaIndex, or other RAG framework
- Load your chunks, run test queries
- Capture results for analysis

Choose based on your time and technical setup. The key is the testing methodology, not the perfect implementation.

**Step 2: Create Test Queries (5 minutes)**

Design 5 test queries covering different scenarios:

1. **Simple factual query** - Single piece of information
2. **Complex multi-part query** - Requires information from multiple chunks
3. **Edge case: Ambiguous query** - Could match multiple topics
4. **Edge case: No relevant content** - Not covered in your documents
5. **Domain-specific terminology** - Uses specific terms from your domain

For each query, document:
- The query text
- Which chunks SHOULD be retrieved (expected results)
- Why those chunks are relevant

**Step 3: Run Retrieval Tests (7 minutes)**

For each query:
1. Run retrieval (or simulate which chunks would be retrieved)
2. Get top-k results (use k=3 and k=5)
3. Record: chunk IDs, similarity scores, whether each is relevant

Calculate:
- **Precision@3**: How many of top 3 are relevant? (relevant_count / 3)
- **Precision@5**: How many of top 5 are relevant? (relevant_count / 5)

**Step 4: Analyze Results (3 minutes)**

- Calculate average precision across all queries
- Identify which queries failed (low precision)
- Hypothesize why (chunking? embedding? query formulation?)
- List 2-3 improvements to try in Session 2

---

#### Deliverable Specification

**File Name:** `retrieval-quality-test.md`

**Location:** Your project repository `rag-system/` folder

**Format Requirements:**
- Follow template structure below
- Include all 5 test queries with results
- Calculate precision metrics
- Identify at least 2 specific issues with proposed solutions

**Quality Criteria:**
- [ ] 5 diverse test queries with expected results documented
- [ ] Retrieval results recorded for each query (top-3 and top-5)
- [ ] Precision@3 and Precision@5 calculated for each query
- [ ] Average precision calculated
- [ ] At least 2 specific issues identified with root cause analysis
- [ ] At least 2 concrete improvements proposed for Session 2

---

#### Template

```markdown
# Retrieval Quality Testing

## Test Setup
- **Embedding model:** [Model used or "simulated"]
- **Vector store:** [Database used or "manual"]
- **Top-k:** 3 and 5
- **Documents indexed:** [Count]
- **Total chunks:** [Count]
- **Similarity metric:** [Cosine/Euclidean/Other]

## Test Queries

### Query 1: [Simple factual query]
**Query text:** "[Exact query]"

**Expected relevant chunks:**
- [Chunk ID or description]: [Why relevant]
- [Chunk ID or description]: [Why relevant]

**Retrieved chunks (top-3):**
| Rank | Chunk ID | Score | Content Preview | Relevant? |
|------|----------|-------|-----------------|-----------|
| 1 | [ID] | [Score] | [First 50 chars] | Yes/No |
| 2 | [ID] | [Score] | [First 50 chars] | Yes/No |
| 3 | [ID] | [Score] | [First 50 chars] | Yes/No |

**Retrieved chunks (top-5):**
[Add ranks 4-5]

**Metrics:**
- **Precision@3:** [X/3] = [percentage]
- **Precision@5:** [X/5] = [percentage]

**Notes:** [Observations about why retrieval worked or failed]

---

### Query 2: [Complex multi-part query]
**Query text:** "[Exact query]"

[Repeat structure from Query 1]

---

### Query 3: [Edge case - ambiguous query]
[Repeat structure]

---

### Query 4: [Edge case - no relevant content]
[Repeat structure]

---

### Query 5: [Domain-specific terminology]
[Repeat structure]

---

## Summary Metrics

| Metric | Value |
|--------|-------|
| Average Precision@3 | [Sum of P@3 / 5] |
| Average Precision@5 | [Sum of P@5 / 5] |
| Queries with relevant top-1 result | [X/5] |
| Queries with no relevant results | [X/5] |
| Perfect queries (P@3 = 100%) | [X/5] |

## Performance Analysis

### What Worked Well
1. [Query type or scenario that had good retrieval]
   - **Why it worked:** [Analysis]

2. [Another success]
   - **Why it worked:** [Analysis]

### Issues Identified

#### Issue 1: [Specific problem]
- **Affected queries:** [Which queries?]
- **Symptoms:** [What happened?]
- **Potential root cause:** [Chunking? Embedding? Query formulation?]
- **Example:** [Specific chunk that was missed or wrongly retrieved]

#### Issue 2: [Specific problem]
[Repeat structure]

#### Issue 3 (if applicable): [Problem]
[Repeat structure]

## Recommended Improvements for Session 2

### Improvement 1: [Specific change]
- **What to change:** [Detailed description]
- **Expected impact:** [How this should improve retrieval]
- **Priority:** [High/Medium/Low]

### Improvement 2: [Specific change]
[Repeat structure]

### Improvement 3 (optional): [Change]
[Repeat structure]

## Next Steps
1. [First thing to try in Session 2]
2. [Second thing]
3. [Third thing]
```

---

#### Tips & Troubleshooting

**Tips:**
- If you don't have time for full implementation, manual/simulated testing is fine - the methodology matters more
- Be honest about failures - a query that retrieves poorly is MORE valuable for learning than perfect results
- Think like a user - what would they actually ask?
- Document your reasoning for expected results - this helps identify why retrieval failed

**Common Issues:**

| Problem | Solution |
|---------|----------|
| "I don't have embeddings set up" | Use Option B (simulated) - manually identify which chunks should match which queries based on content |
| "Everything retrieves perfectly" | Your queries might be too easy. Try ambiguous queries, edge cases, or queries requiring multiple chunks |
| "Nothing retrieves well" | Check: Are chunks too small? Are you using the right similarity metric? Is the query well-formed? |
| "I can't calculate precision" | Formula: Precision@k = (number of relevant chunks in top-k) / k. If 2 of top 3 are relevant, P@3 = 2/3 = 0.67 |

---

## Templates & Resources

### Module Resources

| Resource | Location | Purpose |
|----------|----------|---------|
| RAG Architecture Template | Exercise 1.1 template above | Structure for architecture design |
| Chunking Strategy Guide | Module Appendix B | Decision framework for chunking |
| Evaluation Framework | Module Appendix C | Metrics and testing methodology |

---

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| OpenAI Embeddings Guide | Documentation | [OpenAI Embeddings](https://platform.openai.com/docs/guides/embeddings) | Choosing and using embedding models |
| Vector Database Comparison | Article | [Search: "vector database comparison 2024"] | Selecting a vector database |
| LangChain Chunking | Documentation | [LangChain Text Splitters](https://python.langchain.com/docs/modules/data_connection/document_transformers/) | Implementing chunking |
| LlamaIndex RAG | Tutorial | [LlamaIndex Docs](https://docs.llamaindex.ai/) | End-to-end RAG implementation |

---

### Block Appendix References

For this session's exercises, reference:

- **Appendix A:** RAG Architecture Template - Complete configuration schema
- **Appendix B:** Chunking Strategy Guide - Decision tree and validation checklist
- **Appendix C:** RAG Evaluation Framework - Metrics definitions and test set structure

See the main module document ([Module 8](../module-8-rag-knowledge-systems.md)) for full appendix content.

---

## Self-Assessment

### Exit Criteria Checklist

Before moving to Session 2, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Design a RAG architecture with justified component choices | Exercise 1.1 complete with rationale | ☐ |
| 2 | Implement and compare different chunking strategies | Exercise 1.2 shows 2+ strategies tested | ☐ |
| 3 | Configure embeddings and vector storage | Exercise 1.1 includes embedding/storage decisions | ☐ |
| 4 | Test retrieval quality with objective metrics | Exercise 1.3 calculates precision metrics | ☐ |

---

### Deliverables Checklist

| Deliverable | File Name | Location | Complete? |
|-------------|-----------|----------|-----------|
| Exercise 1.1 output | `rag-architecture-design.md` | `rag-system/` | ☐ |
| Exercise 1.2 output | `chunking-implementation-analysis.md` | `rag-system/` | ☐ |
| Exercise 1.3 output | `retrieval-quality-test.md` | `rag-system/` | ☐ |

---

### Reflection Questions

Take 5 minutes to consider:

1. **What clicked this session?**
   - Which concept suddenly made sense?

2. **What's still fuzzy?**
   - What do you need more practice or clarification on?

3. **How will you apply this?**
   - Name one real work deliverable where you'll use RAG

4. **What surprised you?**
   - What was harder or easier than expected?

[Optional: Share insights in support channel to help your peers]

---

## Getting Help

### Quick Answers
- **[Support Channel]** - Post questions, usually answered within 24 hours
- **Peer Discussion** - Tag your cohort for quick tips

### Common Questions This Session

**Q: "I don't have access to a vector database. Can I still complete the exercises?"**
A: Yes! For Exercise 1.1, you're designing architecture (no implementation needed). For Exercise 1.3, you can simulate retrieval by manually identifying which chunks should match which queries. The methodology matters more than the tooling for learning purposes.

**Q: "My chunking results don't look good. Is that okay?"**
A: Absolutely! The goal is to learn what works and what doesn't. Document the issues you found - that's valuable learning. Session 2 will help you improve.

**Q: "Should I use LangChain/LlamaIndex or build from scratch?"**
A: Use libraries if you're comfortable with them - they'll save time. But don't let library complexity block you. A simple Python script that splits on paragraphs is fine for learning chunking concepts.

**Q: "How do I know if my architecture design is 'good'?"**
A: Check: (1) Does it have clear rationale for decisions? (2) Does it consider trade-offs? (3) Is it appropriate for your specific use case? There's no single "right" architecture - it depends on requirements.

### When to Ask for Help

- **Before asking:** Check this guide's templates and troubleshooting sections
- **Good to ask:** "I tried [X approach] but got [Y result]. Here's my reasoning... What am I missing?"
- **Include:** Your specific scenario, what you tried, and the result

---

## Looking Ahead

### Next Session Preview: Session 2 - Production RAG & Agent Integration

**Focus:**
Advanced retrieval patterns (hybrid search, re-ranking), agent-RAG integration, evaluation frameworks, and production considerations

**How It Builds on This Session:**
- You'll enhance your basic retrieval (Session 1) with hybrid search and re-ranking
- You'll integrate your RAG system with your Block 3 agent
- You'll build evaluation frameworks to measure quality objectively
- You'll address production concerns like scaling, security, updates

**To Prepare:**
- [ ] Complete all Session 1 exercises (we build directly on them)
- [ ] Have your basic RAG system design and chunking implementation ready
- [ ] Review your Block 3 agent system - we'll be integrating RAG with it
- [ ] Think about how you'll measure RAG quality in production

---

## Glossary

| Term | Definition |
|------|------------|
| **RAG** | Retrieval-Augmented Generation - technique combining retrieval with generation |
| **Chunking** | Process of splitting documents into smaller, coherent units |
| **Embedding** | Dense vector representation of text capturing semantic meaning |
| **Vector Database** | Specialized database for storing and searching vector embeddings |
| **Top-k** | Number of most similar results to retrieve (e.g., top-5 chunks) |
| **Semantic Search** | Search based on meaning/concepts rather than exact keywords |
| **Cosine Similarity** | Metric measuring angle between vectors (common for embeddings) |
| **Precision@k** | Percentage of top-k results that are actually relevant |
| **ANN** | Approximate Nearest Neighbor - fast similarity search algorithm |
| **Metadata** | Additional information about chunks (source, date, type, etc.) |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2026-01-02 | Initial guide created |

---

**Navigation:** N/A (Session 1) | **Session 1** | [Session 2 →](../session-2/participant-guide.md)
