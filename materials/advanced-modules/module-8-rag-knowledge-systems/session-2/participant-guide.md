# **ADVANCED MODULE 8 SESSION 2: PRODUCTION RAG & AGENT INTEGRATION**

**Module:** Advanced Module 8: RAG & Knowledge Systems
**Session:** 2 of 2
**Estimated Self-Paced Time:** 75 minutes

---

## Navigation

**Session Navigation:** [← Session 1](../session-1/participant-guide.md) | **Session 2** | N/A (Final Session)

**In This Guide:**
- [Learning Objectives](#learning-objectives)
- [Entry Criteria](#entry-criteria)
- [Key Concepts](#key-concepts)
- [Workshop Recap](#workshop-recap)
- [Self-Paced Exercises](#self-paced-exercises)
- [Templates & Resources](#templates--resources)
- [Module Completion](#module-completion)
- [Getting Help](#getting-help)

---

## Learning Objectives

By the end of this session, you will be able to:

| # | Objective | Practiced In |
|---|-----------|--------------|
| 1 | Implement advanced retrieval patterns (hybrid search, re-ranking) | Exercise 2.1 |
| 2 | Integrate RAG systems with agent workflows using appropriate patterns | Exercise 2.2 |
| 3 | Establish evaluation frameworks to measure RAG quality objectively | Exercise 2.3 (Capstone) |
| 4 | Address production considerations for enterprise RAG deployment | Exercise 2.3 (Capstone) |

---

## Entry Criteria

Before starting this session, confirm you have completed:

- [ ] Session 1 Exercise 1.1: RAG Architecture Design
- [ ] Session 1 Exercise 1.2: Chunking Implementation
- [ ] Session 1 Exercise 1.3: Basic Retrieval Testing
- [ ] Understanding of retrieval quality issues from testing

**Not ready?** Complete [Session 1](../session-1/participant-guide.md) exercises before continuing.

---

## Key Concepts

### Concept 1: Hybrid Search

**Definition:**
Hybrid search combines semantic (vector) search with keyword (lexical) search, fusing results to leverage the strengths of both approaches.

**Why It Matters:**
Pure semantic search misses exact matches (names, codes, technical terms). Pure keyword search misses conceptual similarity. Hybrid search catches both.

**The Pattern:**
```
Query → [Semantic Search] → Results ranked by vector similarity
      → [Keyword Search]  → Results ranked by term matching
      → [Fusion (RRF)]    → Combined ranking
      → Top-k results
```

**Reciprocal Rank Fusion (RRF):**
```
For each result:
  score = 1/(k + rank_in_semantic) + 1/(k + rank_in_keyword)

Sort by score (descending)
```
Where k is typically 60 (a constant that prevents division by zero).

**When to Use:**
- Almost always beneficial for enterprise use cases
- Essential when queries mix semantic and keyword requirements
- Critical for technical, legal, or compliance domains

**Configuration:**
```json
{
  "semantic_weight": 0.7,
  "keyword_weight": 0.3,
  "fusion_method": "rrf",
  "k_constant": 60
}
```

**Common Mistake:**
Using pure semantic search when exact term matching matters (product codes, legal clauses, technical specifications).

---

### Concept 2: Re-ranking

**Definition:**
Re-ranking is a two-stage retrieval pattern that uses fast approximation for initial retrieval, then applies a slower, more accurate model to refine the ranking.

**Why It Matters:**
Bi-encoder models (used for initial retrieval) are fast but less accurate. Cross-encoder models are very accurate but too slow for full corpus search. Combining them gives you both speed and accuracy.

**The Pattern:**
```
Stage 1: Bi-encoder retrieval
  - Fast ANN search
  - Retrieve top-50 candidates
  - Takes ~100ms

Stage 2: Cross-encoder re-ranking
  - Score query+chunk pairs
  - Re-rank top-50 → final top-5
  - Takes ~400ms

Total: ~500ms for much higher precision
```

**Bi-encoder vs. Cross-encoder:**

| Aspect | Bi-encoder | Cross-encoder |
|--------|------------|---------------|
| **How it works** | Embed query and docs separately | Score query+doc as a pair |
| **Speed** | Very fast (ANN search) | Slow (pairwise scoring) |
| **Accuracy** | Good | Excellent |
| **Use** | Initial retrieval | Final re-ranking |

**When to Use:**
- High-stakes queries where precision is critical
- Can tolerate 200-500ms additional latency
- Precision improvements of 10-20% justify the cost

**When NOT to Use:**
- Low-stakes queries where speed matters more
- Cost-sensitive applications
- Already achieving target precision without it

---

### Concept 3: Agent-RAG Integration Patterns

**Three Main Patterns:**

**Pattern 1: RAG as Tool**
```
Agent
  ├── Tool: search_knowledge_base(query, filters)
  ├── Tool: calculator(expression)
  ├── Tool: send_email(to, subject, body)
  └── Decides which tool to use when
```

**Characteristics:**
- Agent controls when to search knowledge
- Natural extension of tool-using agents
- Cost-efficient (only search when needed)
- Requires agent to reason about tool use

**Best for:** Mixed tasks where some need KB, some don't

---

**Pattern 2: RAG as Context**
```
User Query → [Automatic Retrieval] → [Inject Context] → Agent → Response
```

**Characteristics:**
- Always retrieves and injects context
- Simpler agent logic (no tool reasoning)
- May retrieve unnecessarily
- Good for pure Q&A use cases

**Best for:** Simple Q&A where all queries need knowledge

---

**Pattern 3: Agentic RAG**
```
Query → [Router Agent] → Decides on approach
              ↓
        [Search Agent]
          - Query analysis
          - Multi-source search
          - Result synthesis
              ↓
        [Response Agent] → Final answer
```

**Characteristics:**
- Most sophisticated approach
- Multi-step retrieval with query decomposition
- Handles complex research tasks
- Higher latency and complexity

**Best for:** Complex research and analysis tasks

---

### Concept 4: RAG Evaluation Metrics

**Retrieval Metrics:**

| Metric | Formula | What It Measures | Target |
|--------|---------|------------------|--------|
| **Precision@k** | relevant_in_top_k / k | % of results that are relevant (noise level) | >0.70 for k=3 |
| **Recall@k** | relevant_in_top_k / total_relevant | % of relevant items found (completeness) | Varies by use case |
| **MRR** | 1 / rank_of_first_relevant | Quality of top result | >0.80 |
| **NDCG** | Normalized DCG | Full ranking quality | >0.80 |

**Example Calculation:**
```
Query: "vacation policy"
Expected relevant chunks: 5 total in corpus
Top-5 retrieved: [relevant, relevant, irrelevant, relevant, irrelevant]

Precision@3 = 2/3 = 0.67
Precision@5 = 3/5 = 0.60
Recall@5 = 3/5 = 0.60
MRR = 1/1 = 1.0 (first result was relevant)
```

**Generation Metrics:**

| Metric | What It Measures | Evaluation Method | Target |
|--------|------------------|-------------------|--------|
| **Faithfulness** | Response grounded in context | LLM-as-judge (1-5) | >4.0 |
| **Relevance** | Response answers the question | LLM-as-judge (1-5) | >4.0 |
| **Citation Accuracy** | Citations correct and traceable | Automated or human | >0.95 |

**LLM-as-Judge Pattern:**
Use a strong model (GPT-4, Claude) to evaluate your system's outputs:
```
Evaluate this RAG response:

Query: {user_query}
Retrieved Context: {chunks}
Response: {agent_response}

Rate faithfulness (1-5):
5 - All claims supported by context
4 - Minor unsupported details
3 - Some unsupported claims
2 - Significant hallucinations
1 - Contradicts context

Provide rating and explanation.
```

---

## Workshop Recap

### Session Summary

**Today's Focus:** Advanced retrieval patterns, agent integration, evaluation frameworks, and production deployment.

**Key Points from Each Segment:**

**Segment 1: Advanced Retrieval Patterns**
- Hybrid search combines semantic + keyword for best of both
- Re-ranking uses two stages: fast retrieval → accurate refinement
- Query transformation can optimize complex queries
- Hybrid search is almost always beneficial

**Segment 2: Agent + RAG Integration**
- Three patterns: RAG as Tool (recommended), RAG as Context, Agentic RAG
- RAG as Tool gives agent control, reduces cost, extends Block 3 patterns
- Citations are essential for compliance, trust, debugging
- Three citation formats: inline, footnote, structured

**Segment 3: RAG Evaluation Framework**
- Can't improve what you don't measure
- Retrieval metrics: Precision@k, Recall@k, MRR
- Generation metrics: Faithfulness, Relevance, Citation Accuracy
- Build test sets, automate evaluation, sample for human review

**Segment 4: Production Considerations**
- Scaling: latency budgets, caching, index optimization
- Security: document ACLs, query-time filtering, audit logging
- Monitoring: latency, empty result rate, cost per query, cache hit rate
- Build access control in from day one

---

## Self-Paced Exercises

**Total Time:** 75 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 2.1 | 25 min | Advanced retrieval implementation + analysis | Hybrid search, re-ranking |
| 2.2 | 25 min | Agent-RAG integration + test docs | Integration patterns |
| 2.3 | 25 min | Complete capstone documentation | Full system |

**Important:** Exercise 2.3 is the module capstone - bring everything together.

---

### Exercise 2.1: Implement Advanced Retrieval

**Duration:** 25 minutes

**Purpose:**
Enhance your Session 1 retrieval with hybrid search and/or re-ranking, measure the improvement, and document your findings.

**You Will Create:**
Enhanced retrieval implementation with before/after comparison

---

#### Instructions

**Step 1: Document Session 1 Baseline (5 minutes)**

From your Session 1 Exercise 1.3 results, document:
- Average Precision@3
- Average Precision@5
- Which queries performed poorly
- Identified issues

This is your baseline to measure improvement against.

**Step 2: Implement Hybrid Search (12 minutes)**

Choose an implementation approach:
- **Option A:** Use a vector database with native hybrid search (Weaviate, Qdrant, Azure AI Search)
- **Option B:** Implement RRF yourself by combining semantic + keyword results
- **Option C:** Use a framework (LangChain, LlamaIndex) with hybrid search support

Configure:
```json
{
  "semantic_weight": 0.7,
  "keyword_weight": 0.3,
  "fusion_method": "rrf"
}
```

Test with the same queries from Session 1 Exercise 1.3.

**Step 3: Measure Improvement (5 minutes)**

For each test query:
- Run with semantic only (Session 1 approach)
- Run with keyword only
- Run with hybrid search

Calculate Precision@3 for each approach.

**Step 4: (Optional) Add Re-ranking (3 minutes)**

If you have time and access to a re-ranking model:
- Implement re-ranking on top of hybrid search
- Measure precision improvement
- Measure latency added

If you don't implement it, document:
- When you would add re-ranking
- Which re-ranker model you'd choose
- Expected cost/benefit

---

#### Deliverable Specification

**File Name:** `advanced-retrieval-analysis.md` + implementation code/notes

**Location:** Your project repository `rag-system/` folder

**Format Requirements:**
- Follow template structure below
- Include comparison table (semantic vs. keyword vs. hybrid)
- Document configuration choices and rationale
- Include before/after metrics

**Quality Criteria:**
- [ ] Baseline performance from Session 1 documented
- [ ] Hybrid search implemented and tested (or designed if not implemented)
- [ ] Comparison table shows all three approaches
- [ ] Precision@3 calculated for each query
- [ ] Analysis identifies when hybrid helps vs. doesn't
- [ ] Configuration choices explained

---

#### Template

```markdown
# Advanced Retrieval Implementation

## Baseline Performance (from Session 1)

**Average Metrics:**
- Precision@3: [X]
- Precision@5: [X]
- MRR: [X]

**Problem Queries:**
1. [Query]: [Issue - e.g., "missed keyword match"]
2. [Query]: [Issue]
3. [Query]: [Issue]

## Hybrid Search Implementation

### Configuration
```json
{
  "hybrid_search": {
    "semantic_weight": 0.7,
    "keyword_weight": 0.3,
    "fusion_method": "rrf",
    "k_constant": 60,
    "keyword_fields": ["content", "title", "section"]
  }
}
```

**Rationale for weights:** [Why 70/30 or your chosen weights]

### Implementation Approach
[Option A/B/C - what did you use?]

[Brief description of implementation]

### Test Results

| Query | Semantic P@3 | Keyword P@3 | Hybrid P@3 | Notes |
|-------|--------------|-------------|------------|-------|
| [Q1] | | | | |
| [Q2] | | | | |
| [Q3] | | | | |
| [Q4] | | | | |
| [Q5] | | | | |
| **Average** | | | | |

### Hybrid Search Observations

**When hybrid helped:**
1. [Query type where hybrid improved results]
2. [Another scenario]

**When hybrid didn't help:**
1. [Query type where semantic alone was sufficient]

**Optimal weight balance:**
[Did you experiment with weights? What worked best?]

## Re-ranking Implementation (or Design)

### Implemented: [Yes/No]

**If Yes:**

#### Configuration
```json
{
  "reranking": {
    "model": "[model name]",
    "initial_candidates": 20,
    "final_top_k": 5,
    "threshold": 0.7
  }
}
```

#### Test Results

| Query | Hybrid P@5 | After Rerank P@5 | Latency Added | Improvement |
|-------|------------|------------------|---------------|-------------|
| [Q1] | | | | |
| [Q2] | | | | |
| [Q3] | | | | |
| **Average** | | | | |

**If No (Design Only):**

**When I would add re-ranking:**
[Scenarios where re-ranking would be beneficial]

**Re-ranker model choice:**
[Which model and why - Cohere Rerank, cross-encoder, etc.]

**Expected cost/benefit:**
- Precision improvement: [estimated %]
- Latency added: [estimated ms]
- Cost per query: [if applicable]

## Final Pipeline Configuration

```json
{
  "retrieval_pipeline": {
    "stage_1": "hybrid_search",
    "stage_1_k": 20,
    "semantic_weight": 0.7,
    "keyword_weight": 0.3,

    "stage_2": "reranking",
    "stage_2_enabled": true/false,
    "stage_2_k": 5,

    "total_latency_target": "< 2000ms"
  }
}
```

## Performance Summary

| Metric | Session 1 Baseline | After Enhancements | Improvement |
|--------|--------------------|--------------------|-------------|
| Precision@3 | | | |
| Precision@5 | | | |
| MRR | | | |
| Avg latency | | | |

## Lessons Learned

**What worked well:**
1. [Insight]
2. [Insight]

**Challenges encountered:**
1. [Challenge and how you addressed it]

**Recommendations for production:**
1. [Recommendation]
2. [Recommendation]
```

---

#### Tips & Troubleshooting

**Tips:**
- If you can't implement hybrid search, design it thoroughly - explain your approach
- Focus on 3-5 test queries that cover diverse scenarios
- Don't chase perfection - 10-20% improvement is excellent
- Document your reasoning even if results don't improve

**Common Issues:**

| Problem | Solution |
|---------|----------|
| No improvement from hybrid | Check if your queries are purely semantic - hybrid helps most with mixed semantic/keyword needs |
| Can't access re-ranker | That's fine - design it instead, document when you'd add it |
| Implementation taking too long | Switch to design mode - explain what you'd implement and why |

---

### Exercise 2.2: Agent-RAG Integration

**Duration:** 25 minutes

**Purpose:**
Integrate your RAG system with your Block 3 agent, test with realistic scenarios, and document the integration.

**You Will Create:**
Working agent-RAG integration with test documentation

---

#### Instructions

**Step 1: Choose Integration Pattern (5 minutes)**

Review the three patterns:
1. **RAG as Tool:** Agent decides when to search (recommended for most)
2. **RAG as Context:** Always inject context (for pure Q&A)
3. **Agentic RAG:** Multi-agent sophistication (for complex research)

Choose based on your use case. Document your rationale.

**Step 2: Implement Integration (12 minutes)**

**If RAG as Tool:**
- Define `search_knowledge_base` tool for your agent
- Update agent system prompt with guidelines
- Implement tool that calls your RAG pipeline
- Return chunks + sources to agent

**If RAG as Context:**
- Set up automatic retrieval on every query
- Create context injection template
- Update system prompt to use injected context

**If Agentic RAG:**
- Design multi-agent architecture
- Implement router logic
- Document search agent capabilities

**Step 3: Implement Citations (3 minutes)**

Choose citation format:
- **Inline:** "According to [Source], ..."
- **Footnote:** Numbered references at end
- **Structured:** Separate answer and sources object

Update your agent's response formatting to include citations.

**Step 4: Test Scenarios (5 minutes)**

Test at least 4 scenarios:
1. **Direct knowledge question:** Should search KB and cite sources
2. **Question not in KB:** Should search, find nothing, admit it
3. **Multi-turn conversation:** Should maintain context appropriately
4. **Mixed task:** Should use KB only when relevant

Document agent behavior in each scenario.

---

#### Deliverable Specification

**File Name:** `agent-rag-integration.md` + code/configuration

**Location:** Your project repository `rag-system/` folder

**Format Requirements:**
- Follow template structure
- Include tool definition or context template
- Document all 4 test scenarios
- Include sample agent responses

**Quality Criteria:**
- [ ] Integration pattern chosen with clear rationale
- [ ] Implementation documented (or thoroughly designed)
- [ ] Citations included in responses
- [ ] All 4 test scenarios documented with agent behavior
- [ ] Issues identified and resolved (or mitigation planned)
- [ ] Final configuration documented

---

#### Template

```markdown
# Agent-RAG Integration

## Integration Pattern Chosen

**Pattern:** [RAG as Tool / RAG as Context / Agentic RAG]

**Rationale:** [Why this pattern for your use case?]

**Trade-offs considered:**
- **Pros:** [Benefits of chosen pattern]
- **Cons:** [Limitations or challenges]
- **Alternatives rejected:** [Why not the other patterns?]

## Implementation

### RAG Tool Definition (if RAG as Tool)

```json
{
  "tool": {
    "name": "search_knowledge_base",
    "description": "Search the [domain] knowledge base for information about [topics]. Use this when users ask about [specific types of questions].",
    "parameters": {
      "query": {
        "type": "string",
        "description": "The search query - be specific and include relevant terms",
        "required": true
      },
      "filters": {
        "type": "object",
        "description": "Optional metadata filters (document_type, date_range, etc.)",
        "required": false
      },
      "top_k": {
        "type": "number",
        "description": "Number of results to return (default: 5)",
        "required": false
      }
    }
  }
}
```

### Agent System Prompt

```
[Your complete agent system prompt including RAG usage guidelines]

Example structure:
You are an assistant with access to [domain] knowledge.

Capabilities:
- Answer questions using the search_knowledge_base tool
- [Other capabilities]

Guidelines for knowledge base usage:
- Use search_knowledge_base when users ask about [specific topics]
- Always cite your sources using [citation format]
- If information isn't found in the knowledge base, say so clearly
- Don't make up information not present in retrieved sources
- For [topic type], also use [other tool]

Citation format: [Describe how to cite]
```

### Context Injection Template (if RAG as Context)

```
System: [Base system prompt]

--- Retrieved Knowledge ---

{for each chunk:}
Source: {document_name}, Section: {section}, Page: {page}
Content: {chunk_content}
---

{end for}

--- End Retrieved Knowledge ---

Instructions: Use the above knowledge to inform your response when relevant.
Always cite sources. If the knowledge doesn't answer the question, say so.

User Query: {user_query}
```

### Citation Implementation

**Format chosen:** [Inline / Footnote / Structured]

**Example response:**
```
[Show a sample agent response with proper citations]
```

**Why this format:**
[Rationale for citation format choice]

## Test Scenarios

### Scenario 1: Direct knowledge question

**User query:** "[A question that should be answered from KB]"

**Agent behavior:**
- Did agent use search_knowledge_base? [Yes/No]
- Search query used: "[query]"
- Chunks retrieved: [Number]

**Retrieved context (summary):**
[Brief summary of what was retrieved]

**Agent response (summary):**
[Summarize the response]

**Quality assessment:**
- Faithfulness: [1-5] - [Response grounded in context?]
- Relevance: [1-5] - [Answered the question?]
- Citations: [Correct/Incorrect/Missing]
- Overall: [Good/Issues]

**Issues found:** [Any problems?]

---

### Scenario 2: Question not in knowledge base

**User query:** "[A question KB can't answer]"

**Agent behavior:**
- Did agent search? [Yes/No]
- Search query: "[query]"
- Results found: [Number]

**Agent response (summary):**
[How did agent handle no results?]

**Quality assessment:**
- Appropriately indicated no information? [Yes/No]
- Hallucinated instead? [Yes/No]
- Offered to help differently? [Yes/No]
- Overall: [Good/Issues]

---

### Scenario 3: Multi-turn conversation with knowledge

**Turn 1:**
- **User:** "[Initial query]"
- **Agent:** "[Response with KB lookup]"

**Turn 2:**
- **User:** "[Follow-up query]"
- **Agent behavior:** [Searched again? Used context? Both?]
- **Agent:** "[Response]"

**Quality assessment:**
- Maintained context? [Yes/No]
- Appropriate KB usage? [Yes/No]
- Overall conversation quality: [Good/Issues]

---

### Scenario 4: Mixed task (some KB, some not)

**User query:** "[Query mixing KB needs with other needs]"

**Example:** "What's our vacation policy and can you schedule a meeting?"

**Agent behavior:**
- Used search_knowledge_base for policy? [Yes/No]
- Used meeting tool? [Yes/No]
- Handled both parts? [Yes/No]

**Agent response (summary):**
[How agent handled the mixed request]

**Quality assessment:**
- Appropriate tool selection? [Yes/No]
- Both parts addressed? [Yes/No]
- Overall: [Good/Issues]

## Integration Issues Found

### Issue 1: [Description]
- **Symptom:** [What went wrong]
- **Impact:** [Effect on system]
- **Root cause:** [Why it happened]
- **Fix:** [How you resolved it or plan to]

### Issue 2: [If applicable]
[Repeat structure]

## Final Integration Configuration

```json
{
  "agent_rag_config": {
    "pattern": "[chosen pattern]",
    "retrieval_trigger": "[always / agent_decision / query_analysis]",
    "context_format": "[template name]",
    "max_context_tokens": 2000,
    "citation_format": "[inline / footnote / structured]",
    "fallback_behavior": "[what happens if retrieval fails]",

    "tool_config": {
      "name": "search_knowledge_base",
      "default_top_k": 5,
      "default_filters": {}
    }
  }
}
```

## Production Considerations

### Access Control
- How are user permissions checked? [Approach]
- Where is filtering applied? [Query-time / Post-retrieval]
- How is data leakage prevented? [Method]

### Performance
- Average retrieval latency: [ms]
- Cache strategy: [Approach]
- Concurrent user handling: [Method]

### Monitoring
- What would you log? [List metrics]
- How would you detect issues? [Monitoring approach]
- Alert thresholds: [Define key alerts]

## Lessons Learned

**What worked well:**
1. [Insight about integration]
2. [Insight about agent behavior]

**Challenges encountered:**
1. [Challenge and solution]

**Recommendations for production:**
1. [Recommendation]
2. [Recommendation]
```

---

#### Tips & Troubleshooting

**Tips:**
- Start with RAG as Tool - it's the most flexible
- Test edge cases (no results, permission errors, very long queries)
- Make citations mandatory in your system prompt
- Log everything during testing for debugging

**Common Issues:**

| Problem | Solution |
|---------|----------|
| Agent not using KB tool | Make tool description clearer, ensure system prompt mentions when to use it |
| Citations missing | Add explicit citation instruction in system prompt, include in response format |
| Agent searches unnecessarily | Refine tool description to specify when KB is needed vs. not needed |
| Multi-turn context lost | Ensure conversation history is passed to agent, not just latest message |

---

### Exercise 2.3: Module Capstone - Knowledge-Enabled Agent System

**Duration:** 25 minutes

**Purpose:**
Complete your production-ready, knowledge-enabled agent system by bringing together all components, evaluating quality, and documenting for deployment.

**You Will Create:**
Comprehensive capstone documentation demonstrating a complete RAG-powered agent system

---

#### Instructions

**This is your portfolio piece.** Make it comprehensive but focus on demonstrating what you've learned rather than achieving perfection.

**Step 1: System Overview (5 minutes)**

Document:
- What knowledge problem does your system solve?
- Who are the target users?
- What knowledge domain is covered?
- Why is this valuable?

**Step 2: Architecture Summary (5 minutes)**

Create a comprehensive architecture diagram and component table showing:
- All components from Session 1 (chunking, embeddings, vector store, retrieval)
- Session 2 enhancements (hybrid search, re-ranking if included, agent integration)
- How they connect

**Step 3: Evaluation Results (8 minutes)**

Build and execute an evaluation framework:

**Retrieval Quality:**
- Test 5 queries minimum
- Calculate Precision@3, Precision@5, MRR
- Compare to targets

**Generation Quality:**
- Evaluate faithfulness and relevance (LLM-as-judge or human)
- Check citation accuracy
- Compare to targets

**End-to-End Testing:**
- 4 test cases covering different scenarios
- Document expected vs. actual behavior

**Step 4: Production Readiness (4 minutes)**

Complete the production readiness checklist:
- Security: access control, audit logging, data isolation
- Performance: latency, caching, cost per query
- Maintenance: update procedures, monitoring, backups

**Step 5: Lessons Learned (3 minutes)**

Document:
- What worked well in your design/implementation
- Challenges encountered and how you addressed them
- Recommendations for production deployment

---

#### Deliverable Specification

**File Name:** `module-capstone-knowledge-enabled-agent.md`

**Location:** Your project repository root (highly visible)

**Format Requirements:**
- Follow template structure
- Include architecture diagram (ASCII art is fine)
- Document all evaluation results
- Complete all checklists
- Include demo script

**Quality Criteria:**
- [ ] Clear system purpose and value proposition
- [ ] Complete architecture with all components documented
- [ ] Evaluation framework with actual results (not placeholders)
- [ ] Production readiness assessed honestly
- [ ] Lessons learned captured with specific insights
- [ ] Demo script shows system capabilities

---

#### Template

```markdown
# Module Capstone: Knowledge-Enabled Agent System

## Executive Summary

**System Name:** [Your system name]

**Purpose:** [One paragraph: what problem does this solve?]

**Value Proposition:** [Why is this valuable to users/organization?]

**Status:** [Prototype / Proof of Concept / Production Ready]

---

## System Overview

### Purpose
[Detailed description of what knowledge problem this agent solves]

### Target Users
- **Primary:** [User type]
- **Secondary:** [User type]
- **Use cases:** [List 3-5 specific use cases]

### Knowledge Domain
- **Scope:** [What knowledge is covered?]
- **Sources:** [How many documents, types, size]
- **Update frequency:** [How often knowledge changes]

### Success Metrics
- **User success rate:** [Target %]
- **Query response time:** [Target ms]
- **Answer accuracy:** [Target %]
- **User satisfaction:** [Target score]

---

## Architecture

### System Diagram

```
[User Query]
      ↓
[Agent System]
  ├── Tool: search_knowledge_base()
  │     ↓
  │   [Query Processing]
  │     - Query understanding
  │     - Permission check
  │     ↓
  │   [Hybrid Retrieval]
  │     - Semantic search (vector)
  │     - Keyword search (BM25)
  │     - RRF fusion
  │     ↓
  │   [Re-ranking] (optional)
  │     - Cross-encoder scoring
  │     - Top-k refinement
  │     ↓
  │   [Context Assembly]
  │     - Format chunks
  │     - Add metadata
  │     - Apply filters
  │
  ├── Tool: [other_tools...]
  │
  └── Response Generation
        - LLM with context
        - Citation formatting
        - Quality checks
      ↓
[Cited Response to User]
      ↓
[Audit Log]
```

### Component Details

| Component | Implementation | Configuration | Rationale |
|-----------|----------------|---------------|-----------|
| **Chunking** | [Strategy] | Size: [X] tokens, Overlap: [Y] | [Why chosen] |
| **Embeddings** | [Model] | Dimensions: [X] | [Why chosen] |
| **Vector Store** | [Database] | Index: [Type] | [Why chosen] |
| **Retrieval** | [Hybrid/Semantic] | Weights: [X/Y], Top-k: [Z] | [Why chosen] |
| **Re-ranking** | [Model/None] | Candidates: [X] | [Why included/excluded] |
| **Agent** | [Framework] | Model: [X] | [Why chosen] |
| **Integration** | [Pattern] | [Config] | [Why this pattern] |

---

## Implementation Details

### Session 1 Foundation

**Chunking Implementation:**
- Strategy: [What you implemented]
- Quality: [Results from Session 1 Exercise 1.2]
- Refinements: [Improvements made]

**Basic Retrieval:**
- Initial precision: [Session 1 baseline]
- Issues identified: [Key problems]

### Session 2 Enhancements

**Advanced Retrieval:**
- Hybrid search: [Implemented/Designed]
- Re-ranking: [Implemented/Designed]
- Improvement: [% better than baseline]

**Agent Integration:**
- Pattern: [RAG as Tool/Context/Agentic]
- Tool definition: [Summary]
- Citation format: [Inline/Footnote/Structured]

---

## Evaluation Results

### Test Set

**Total test queries:** [Number]
**Categories covered:** [List categories]

**Sample queries:**
1. [Simple factual query]
2. [Complex multi-part query]
3. [Edge case query]
4. [Domain-specific query]
5. [Out-of-scope query]

### Retrieval Quality

| Metric | Value | Target | Status |
|--------|-------|--------|--------|
| Precision@3 | [X.XX] | >0.70 | ✓ / ✗ |
| Precision@5 | [X.XX] | >0.60 | ✓ / ✗ |
| MRR | [X.XX] | >0.80 | ✓ / ✗ |
| Recall@5 | [X.XX] | [Your target] | ✓ / ✗ |

**Analysis:**
- [Which metrics met targets?]
- [Which queries performed best/worst?]
- [What drives good/bad performance?]

### Generation Quality

| Metric | Value | Target | Status | Evaluation Method |
|--------|-------|--------|--------|-------------------|
| Faithfulness | [X.X/5] | >4.0 | ✓ / ✗ | [LLM-as-judge / Human] |
| Answer Relevance | [X.X/5] | >4.0 | ✓ / ✗ | [LLM-as-judge / Human] |
| Citation Accuracy | [X%] | >95% | ✓ / ✗ | [Manual check] |

**Sample Evaluation:**

Query: "[Test query]"

Retrieved Context: [Summary]

Agent Response: "[Response]"

Faithfulness Score: [X/5] - [Justification]
Relevance Score: [X/5] - [Justification]
Citations: [Correct/Incorrect] - [Details]

### End-to-End Testing

| Test Case | Query | Expected Behavior | Actual Behavior | Pass/Fail |
|-----------|-------|-------------------|-----------------|-----------|
| Simple lookup | "[Q]" | Find policy, cite source | [What happened] | ✓ / ✗ |
| Complex query | "[Q]" | Multi-chunk answer | [What happened] | ✓ / ✗ |
| Out of scope | "[Q]" | Admit no info | [What happened] | ✓ / ✗ |
| Edge case | "[Q]" | [Expected] | [What happened] | ✓ / ✗ |

**Overall Pass Rate:** [X/Y] = [%]

---

## Production Readiness Assessment

### Security ✓ / ⚠ / ✗

- [ ] Access control implemented
  - Method: [How permissions are checked]
  - Testing: [How verified]
- [ ] User context filtering functional
  - Approach: [Query-time filtering details]
- [ ] Audit logging in place
  - What's logged: [Details]
  - Where: [Log destination]
- [ ] Data leakage prevention tested
  - Test approach: [How verified isolation]
  - Results: [Pass/Fail]

**Security Status:** [Production Ready / Needs Work / Not Implemented]

**If not ready:** [What needs to be done]

### Performance ✓ / ⚠ / ✗

- [ ] Query latency < [target]
  - Measured: [p50, p95, p99]
  - Target met: [Yes/No]
- [ ] Concurrent user capacity: [X users]
  - Tested: [How verified]
- [ ] Caching strategy implemented
  - Approach: [What's cached, TTL]
  - Hit rate: [%]
- [ ] Cost per query acceptable
  - Measured: [$X per query]
  - Budget: [$Y per query]
  - Status: [Within/Over budget]

**Performance Status:** [Production Ready / Needs Optimization / Not Tested]

**If not ready:** [What needs optimization]

### Maintenance ✓ / ⚠ / ✗

- [ ] Update procedure documented
  - Process: [How to update knowledge base]
  - Frequency: [How often]
- [ ] Monitoring approach defined
  - Metrics: [List key metrics]
  - Tools: [Monitoring stack]
- [ ] Alert thresholds set
  - Critical: [List critical alerts]
  - Warning: [List warning alerts]
- [ ] Backup/recovery documented
  - Backup: [Approach]
  - Recovery: [Process]
  - Tested: [Yes/No]

**Maintenance Status:** [Production Ready / Needs Documentation / Not Defined]

**If not ready:** [What needs definition]

---

## Lessons Learned

### What Worked Well

1. **[Success #1]**
   - What: [What worked]
   - Why: [Why it worked well]
   - Evidence: [Metrics or observations]

2. **[Success #2]**
   [Repeat structure]

3. **[Success #3]**
   [Repeat structure]

### Challenges Encountered

1. **Challenge:** [Description of problem]
   - **Impact:** [How it affected the system]
   - **Root cause:** [Why it happened]
   - **Solution:** [How you addressed it]
   - **Outcome:** [Result of the solution]

2. **Challenge:** [Repeat for each major challenge]

### Recommendations for Production

#### Immediate (Before Launch)
1. [Critical item to address]
2. [Critical item]

#### Short-term (First 3 months)
1. [Improvement to make early]
2. [Improvement]

#### Long-term (Beyond 3 months)
1. [Future enhancement]
2. [Future enhancement]

---

## Demo Script

### Setup Requirements
- [Prerequisites for running demo]
- [Data needed]
- [Tools/access required]

### Demo Flow (5-minute demo)

**Minute 0-1: Introduction**
> "This is [system name], a knowledge-enabled agent for [purpose].
> It can answer questions about [domain] by searching [X documents] and citing sources."

**Minute 1-2: Scenario 1 - Successful KB Lookup**
- **Query:** "[Simple question in domain]"
- **Show:** Agent uses search tool
- **Highlight:** Retrieved chunks, cited response
- **Point out:** Source attribution

**Minute 2-3: Scenario 2 - Out of Scope Handling**
- **Query:** "[Question not in KB]"
- **Show:** Agent searches, finds nothing
- **Highlight:** Graceful handling, admits lack of info

**Minute 3-4: Scenario 3 - Complex Multi-turn**
- **Turn 1:** "[Initial question]"
- **Show:** KB-backed response
- **Turn 2:** "[Follow-up question]"
- **Highlight:** Context maintenance, appropriate tool use

**Minute 4-5: Metrics & Production Readiness**
- **Show:** Evaluation metrics (Precision, MRR)
- **Show:** Production checklist
- **Emphasize:** Security, monitoring, scalability

### Key Points to Highlight
1. [Core capability to emphasize]
2. [Unique aspect of your implementation]
3. [Production-readiness features]
4. [Measurable quality metrics]

---

## Appendix

### Configuration Files

**Full retrieval pipeline config:**
```json
{
  // Complete configuration
}
```

**Agent system prompt:**
```
[Complete system prompt]
```

### Test Set Details

**Complete test queries:**
1. [Query] - [Category] - [Expected chunks]
2. [Repeat for all test queries]

### Sample Outputs

**Sample 1:**
- Query: [Q]
- Retrieved: [Chunks]
- Response: [Full response]
- Evaluation: [Scores and reasoning]

[Include 2-3 more samples showing diverse scenarios]

---

## Conclusion

**System Capabilities:** [Summary of what system can do]

**Quality Assessment:** [Overall quality level achieved]

**Production Readiness:** [Ready/Nearly Ready/Needs Work + details]

**Next Steps:**
1. [Immediate next action]
2. [Follow-up action]
3. [Future direction]

---

**Author:** [Your name]
**Date:** [Completion date]
**Module:** Advanced Module 8: RAG & Knowledge Systems
**Status:** [Draft / Complete / Production Ready]
```

---

#### Tips & Troubleshooting

**Tips:**
- This is a showcase piece - make it comprehensive
- Focus on demonstrating understanding, not perfection
- Include actual results, not placeholders
- Be honest about production readiness - gaps are okay if documented
- Think of this as documentation you'd hand to a client or engineering team

**Common Issues:**

| Problem | Solution |
|---------|----------|
| "I don't have perfect metrics" | Document what you have, explain what you'd measure in production |
| "My system isn't production ready" | That's fine - document what's missing and how you'd address it |
| "25 minutes isn't enough" | Focus on documentation over implementation - design is as valuable as code |
| "I'm not sure what to include" | Follow the template - it covers all required components |

---

## Templates & Resources

### Module Resources

| Resource | Location | Purpose |
|----------|----------|---------|
| Hybrid Search Config | Exercise 2.1 template | Configuration guide |
| Integration Patterns | Exercise 2.2 template | Agent-RAG patterns |
| Evaluation Framework | Module Appendix C | Metrics and testing |
| Production Checklist | Module Appendix (inline) | Deployment readiness |

### External Resources

| Resource | Link/Reference | When to Use |
|----------|----------------|-------------|
| RAGAS Framework | [GitHub: explodinggradients/ragas] | Automated RAG evaluation |
| Cohere Rerank | [Cohere docs] | Re-ranking implementation |
| LangChain Retrievers | [LangChain docs] | Implementation patterns |
| Vector DB Optimization Guides | [Provider-specific docs] | Performance tuning |

---

## Module Completion

### Module Achievement

You have completed Advanced Module 8: RAG & Knowledge Systems!

**Session 1 Accomplishments:**
- ✓ Designed RAG architecture
- ✓ Implemented chunking strategies
- ✓ Configured embeddings and vector storage
- ✓ Built basic retrieval pipeline

**Session 2 Accomplishments:**
- ✓ Implemented advanced retrieval (hybrid search, re-ranking)
- ✓ Integrated RAG with agent workflows
- ✓ Established evaluation frameworks
- ✓ Addressed production considerations

### Certification

To receive certification for this module, ensure your capstone demonstrates:
1. Complete RAG system architecture with rationale
2. Working retrieval implementation (basic or advanced)
3. Agent integration with citations
4. Evaluation framework with metrics
5. Production readiness assessment

**Passing Criteria:** 14+ points (out of 20) on module rubric (see Module Appendix D)

### Final Checklist

- [ ] Session 1 exercises completed
- [ ] Session 2 exercises completed
- [ ] Capstone comprehensive and well-documented
- [ ] All deliverables in repository
- [ ] Ready to demonstrate system capabilities

---

## Getting Help

### Support Channel
- Questions about exercises or concepts
- Implementation troubleshooting
- Capstone review requests

### Common Questions

**Q: "I couldn't implement hybrid search - is that okay for the capstone?"**
A: Yes! Document your hybrid search design thoroughly - explain configuration, when you'd use it, expected benefits. Design with rationale is valuable.

**Q: "My evaluation metrics don't meet targets - did I fail?"**
A: No! Document your actual metrics and explain why. Suggest improvements. The learning is in the iteration, not perfection.

**Q: "Can I use the capstone in my portfolio?"**
A: Absolutely! This is designed as a portfolio piece. Sanitize any sensitive client data, but otherwise showcase your work.

---

## Glossary

| Term | Definition |
|------|------------|
| **Hybrid Search** | Combining semantic (vector) and keyword (lexical) search |
| **RRF** | Reciprocal Rank Fusion - method for combining rankings |
| **Re-ranking** | Two-stage retrieval using fast then accurate models |
| **Bi-encoder** | Model that embeds query and documents separately |
| **Cross-encoder** | Model that scores query+document pairs together |
| **RAG as Tool** | Integration pattern where agent decides when to search KB |
| **Precision@k** | Percentage of top-k results that are relevant |
| **MRR** | Mean Reciprocal Rank - quality of first relevant result |
| **Faithfulness** | Whether response is grounded in retrieved context |
| **LLM-as-Judge** | Using LLM to evaluate system outputs |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2026-01-02 | Initial guide created |

---

**Navigation:** [← Session 1](../session-1/participant-guide.md) | **Session 2** | N/A (Final Session)

---

**Congratulations on completing Advanced Module 8: RAG & Knowledge Systems!**
