# **POWERPOINT PRESENTATION: ADVANCED MODULE 8 SESSION 1**
## **RAG Fundamentals**

**Module:** Advanced Module 8: RAG & Knowledge Systems
**Session Number:** 1 of 2
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Block 3 graduates (AI Automation Architects) who need to build knowledge-enabled AI agents for enterprise consulting engagements

**Session Learning Objectives:** By the end of this session, participants will:
1. Understand RAG architecture patterns and when to apply them vs. alternatives
2. Design and implement appropriate chunking strategies for different document types
3. Select and configure embedding models and vector databases for retrieval
4. Build a basic retrieval pipeline with proper context formatting

**Entry Criteria:**
- [ ] Block 3 completed with working agent system
- [ ] Understanding of vector similarity concepts (conceptual)
- [ ] Access to sample documents for testing
- [ ] Familiarity with API-based model interactions

**Exit Criteria:**
- [ ] RAG architecture patterns understood
- [ ] Chunking strategies mastered
- [ ] Embedding concepts clear
- [ ] Basic retrieval pipeline designed

**Presentation Structure:**
1. Opening & Recap (3 min) - Slides 1-3
2. Segment 1: RAG Architecture Fundamentals (12 min) - Slides 4-7
3. Segment 2: Document Chunking Strategies (12 min) - Slides 8-11
4. Segment 3: Embedding and Vector Storage (12 min) - Slides 12-15
5. Segment 4: Basic Retrieval Pipeline (9 min) - Slides 16-18
6. Homework Preview & Close (3 min) - Slides 19-21

**Total Slides:** 21

---

## Slide Definitions

### SLIDE 1: TITLE SLIDE

**Title:** Advanced Module 8 Session 1: RAG Fundamentals

**Subtitle:** Building Knowledge-Enabled AI Agents

**Content:**
- [Instructor Name]
- [Date/Cohort identifier]
- AI Practitioner Training Program - Advanced Module

**Graphic:** Clean title slide with green tones (advanced module theme). Include RAG concept visualization - documents flowing into a knowledge base connecting to an agent.

**SPEAKER NOTES:**

"[OPENING - Welcome]"

"Welcome to Advanced Module 8: RAG & Knowledge Systems. This is Session 1, where we'll cover RAG Fundamentals.

You've completed Block 3, which means you know how to build autonomous AI agents. But there's a critical gap: your agents can only work with the knowledge in their training data and what fits in their context window.

Today, we're solving that problem. We're teaching agents to retrieve and reason over unlimited enterprise knowledge - policies, documentation, research, case histories - anything your clients need.

This is the difference between a smart agent and an enterprise-ready agent."

[Transition: Click to next slide]

---

### SLIDE 2: SESSION OVERVIEW

**Title:** This Session's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-3 min | Opening | Module Overview & Expectations |
| 3-15 min | Segment 1 | RAG Architecture Fundamentals |
| 15-27 min | Segment 2 | Document Chunking Strategies |
| 27-39 min | Segment 3 | Embedding & Vector Storage |
| 39-48 min | Segment 4 | Basic Retrieval Pipeline |
| 48-51 min | Close | Homework & Resources |

**Graphic:** Simple timeline showing the session flow with icons for each segment

**SPEAKER NOTES:**

"Here's what we'll cover in the next 45 minutes:

First, we'll dive into RAG architecture fundamentals - what RAG is, why agents need it, and how it compares to alternatives like fine-tuning.

Then, we'll tackle document chunking strategies. This is critical - chunking directly determines retrieval quality. We'll cover four different approaches.

In our third segment, we'll explore embeddings and vector storage - how text becomes searchable vectors and how to choose the right embedding model.

Finally, we'll put it together with a basic retrieval pipeline - from query to context formatting.

By the end, you'll design your own RAG architecture in the homework exercises.

Any questions before we dive in?"

[Transition]

---

### SLIDE 3: LEARNING OBJECTIVES

**Title:** By the End of Today...

**Content:**

You will be able to:

1. **Design RAG architectures appropriate for enterprise use cases**
   - Compare RAG, fine-tuning, and long context approaches

2. **Implement effective chunking strategies for different document types**
   - Select chunk sizes, strategies, and overlap configurations

3. **Configure embedding models and vector databases**
   - Choose models, dimensions, and similarity metrics

4. **Build retrieval pipelines with proper context formatting**
   - Design end-to-end query-to-context flows

**Graphic:** Checklist visual with four objectives as checkboxes

**SPEAKER NOTES:**

"These are our four objectives for today. By the time you leave this session, you'll be able to:

[Read each objective, pausing briefly after each]

Notice that these are all ACTION-focused. We're not just learning concepts - you're building production RAG systems.

The first objective connects directly to real client needs - knowing when RAG is the right solution versus fine-tuning or just using long context windows.

Let's get started with RAG fundamentals."

[Transition: Click to Segment 1]

---

## SEGMENT 1: RAG ARCHITECTURE FUNDAMENTALS
### Duration: 12 minutes | Slides 4-7

---

### SLIDE 4: THE KNOWLEDGE PROBLEM

**Title:** Why Do Agents Need External Knowledge?

**Content:**

**The Challenge:**
Your brilliant agent can only access:
- Training data (months old)
- Current conversation context (limited tokens)
- Built-in tools (no domain knowledge)

**The Cost:**
- Hallucinations on company-specific information
- Can't answer questions about current policies
- No citations or sources for audit trails
- Expensive context window usage

**Why It Matters:**
- Enterprise clients need current, accurate, traceable information
- Compliance requires knowing what informed decisions
- Cost at scale requires efficient knowledge access

**Graphic:** Split-screen showing an agent without RAG (confused, hallucinating) vs. with RAG (accessing structured knowledge base)

**SPEAKER NOTES:**

"[Hook - Create tension]"

"Let me ask you a question: What happens when a client asks your agent about their company's latest remote work policy, and that policy was updated last month?

[Pause - let question land]

If you're relying on the model's training data, you get a hallucination. If you try to fit the entire policy manual in the context window, you're burning tokens and money.

The reality is that most enterprise use cases need agents to work with knowledge that's:
- Too large for context windows
- Too dynamic for training data
- Too important for hallucination risk

[Point to graphic]

This is the RAG problem. On the left, an agent guessing. On the right, an agent with RAG - retrieving actual documents, citing sources, giving accurate answers.

Today we're building the right side. Here's how..."

[Transition]

---

### SLIDE 5: WHAT IS RAG?

**Title:** Retrieval-Augmented Generation Explained

**Content:**

**Core Principle:** Instead of generating from memory, retrieve relevant information first, then generate grounded responses.

**RAG Pipeline:**
```
[Documents] → [Chunking] → [Embedding] → [Vector Store]
                                              ↓
[Query] → [Embed Query] → [Search] → [Retrieved Context]
                                              ↓
                                    [LLM with Context] → [Response]
```

**Key Benefits:**
- Current information (update documents, not models)
- Citations and sources (audit trail)
- Reduced hallucination (grounded in facts)
- Cost efficiency (smaller context windows)

**Graphic:** Flow diagram showing the RAG pipeline with arrows and icons for each step

**GRAPHICS:**

**Graphic 1: Complete RAG Pipeline Flow**
- Purpose: Illustrate the end-to-end RAG process from document ingestion to response generation
- Type: Two-part horizontal flow diagram (indexing phase + retrieval phase)
- Elements: Top half showing offline indexing (Documents → Chunking → Embedding → Vector Store); bottom half showing online retrieval (Query → Embed → Search → Retrieve → Generate); connecting arrow from vector store to search
- Labels: Phase names clearly marked (Indexing/Offline vs. Retrieval/Online); step names under each component; icons for each step (document, scissors for chunking, neural net for embedding, database, magnifying glass for search, LLM brain); timing indicators (one-time vs. per-query)
- Relationships: Sequential flow in each phase; vector store as bridge between phases; feedback loop showing document updates; emphasis on query embedding using same model as documents

**Graphic 2: RAG vs. Traditional LLM Comparison**
- Purpose: Contrast how RAG-enabled and traditional LLMs answer questions
- Type: Side-by-side comparison flow diagram
- Elements: Left side "Traditional LLM" showing Query → LLM (with training data) → Response; right side "RAG-enabled LLM" showing Query → Retrieval → LLM + Context → Response; visual indicators of hallucination risk and accuracy
- Labels: "Training Data (Months Old)" on left; "Current Documents" on right; hallucination warning icon on left; citation/source icon on right; timestamps showing data freshness
- Relationships: Highlight key differences with callout boxes; show where hallucination typically occurs; indicate cost and latency tradeoffs

**Graphic 3: RAG Benefits Quadrant**
- Purpose: Visualize the four key benefits of RAG in enterprise context
- Type: Four-quadrant benefit diagram
- Elements: Four quadrants (Current Information, Citations/Audit, Reduced Hallucination, Cost Efficiency); each with icon and 2-3 supporting points; center showing "Enterprise RAG Advantages"
- Labels: Benefit names; specific examples for each (e.g., "Update docs not models" for Current Info); business impact indicators; use case callouts
- Relationships: All four benefits interconnected; emphasis on how benefits compound; mapping to enterprise requirements (compliance, accuracy, TCO)

**SPEAKER NOTES:**

"[INSIGHT - Deliver the solution]"

"RAG stands for Retrieval-Augmented Generation.

The core insight is simple but powerful: instead of asking the LLM to generate from memory, we retrieve relevant information first, then generate responses grounded in that information.

Here's how it works:

[Walk through the diagram]

Top row: We process documents - chunk them into pieces, convert chunks to vector embeddings, store in a vector database.

Bottom row: When a query comes in, we embed the query, search for similar chunks, retrieve the most relevant context, and feed that context to the LLM along with the question.

The LLM generates its response based on the retrieved information, not from memory.

[Point to graphic]

Notice the feedback loop - the LLM only sees what we retrieve. This is both powerful and critical to get right.

The key benefits: your knowledge stays current, you get citations, hallucinations drop dramatically, and you control costs.

Let me show you how this compares to alternatives..."

[Transition to comparison]

---

### SLIDE 6: RAG VS. ALTERNATIVES

**Title:** When to Use RAG vs. Fine-Tuning vs. Long Context

**Content:**

| Approach | Best For | Limitations | Cost |
|----------|----------|-------------|------|
| **RAG** | Dynamic knowledge, citations needed, large corpora | Retrieval quality dependency | Low ongoing |
| **Fine-tuning** | Style/behavior changes, static domain knowledge | Expensive, no citations, outdated quickly | High upfront |
| **Long Context** | Small, fixed documents (< 50 pages) | Cost per query, context dilution | High per query |

**Decision Framework:**
- Need citations? → RAG
- Knowledge changes frequently? → RAG
- Need custom behavior/style? → Fine-tuning
- Have fixed, small documents? → Long Context
- Need all three? → Combine approaches

**Graphic:** Decision tree visual showing when to choose each approach

**SPEAKER NOTES:**

"Not every problem needs RAG. Let's compare the three main approaches:

RAG is best when you have dynamic knowledge that changes, when you need citations for compliance, or when you're working with large knowledge bases. The limitation is that your quality depends on retrieval quality.

Fine-tuning is for changing model behavior or style, or baking in static domain knowledge. But it's expensive to set up, gives you no citations, and becomes outdated the moment knowledge changes.

Long context is tempting - just stuff everything in the prompt. But it only works for small, fixed documents. Beyond that, you're paying for every token on every query, and suffering from context dilution - the model loses track of what's important.

[Point to decision framework]

The decision is usually clear: if you need citations, use RAG. If knowledge changes, use RAG. If you need custom style, fine-tune. Small fixed documents, use long context.

In practice, many systems combine approaches - RAG for knowledge, fine-tuning for style."

[Transition]

---

### SLIDE 7: SEGMENT 1 SUMMARY

**Title:** RAG Architecture Fundamentals - Key Takeaways

**Content:**

**Key Takeaway:** RAG retrieves relevant information before generation, grounding LLM responses in actual documents.

**Remember:**
- RAG solves the knowledge problem for agents
- Pipeline: Document → Chunk → Embed → Store → Search → Retrieve → Generate
- Choose RAG for dynamic knowledge and citations
- Quality depends on retrieval quality

**You'll Practice:**
Exercise 1.1 - Design your RAG architecture for a real use case

**Graphic:** Simple visual reinforcing the RAG pipeline concept

**SPEAKER NOTES:**

"Before we move on, let me summarize the key points:

RAG is about retrieval before generation. You're not asking the model to remember - you're giving it the right information to work with.

The pipeline has two parts: indexing (process documents) and retrieval (search and generate).

Use RAG when you need current knowledge, citations, or you're working with large, changing knowledge bases.

The critical insight: your RAG system is only as good as your retrieval. If you retrieve irrelevant chunks, the LLM will generate irrelevant answers.

That's why the next three segments focus on making retrieval excellent.

In Exercise 1.1 this week, you'll design a complete RAG architecture for a real use case.

Any final questions on RAG fundamentals before we move to chunking strategies?"

[Transition: Click to Segment 2]

---

## SEGMENT 2: DOCUMENT CHUNKING STRATEGIES
### Duration: 12 minutes | Slides 8-11

---

### SLIDE 8: THE CHUNKING CHALLENGE

**Title:** Why Chunking Makes or Breaks RAG

**Content:**

**The Challenge:**
Documents are long. Vector search needs bite-sized pieces. How do you split them?

**The Stakes:**
- **Too large:** Irrelevant content dilutes the signal
- **Too small:** Lost context, fragmented information
- **Just right:** Semantically coherent, complete units

**Real Impact:**
- Poor chunking = relevant information split across chunks = retrieval fails
- Good chunking = complete thoughts preserved = accurate retrieval

**Graphic:** Visual showing a document being chunked badly (mid-sentence split) vs. well (semantic boundaries)

**SPEAKER NOTES:**

"[Hook - Create tension]"

"Chunking seems simple - just split text every N tokens, right?

[Pause]

Wrong. Chunking is where most RAG systems fail.

Here's why it matters: your embedding model sees chunks, not documents. If you split a critical policy statement in half, both halves get embedded separately. When someone queries, they might get the first half but not the second.

[Point to graphic]

On the left, bad chunking - we split mid-sentence, lost context. On the right, good chunking - we respect semantic boundaries.

The challenge: documents are long, vector search needs bite-sized pieces, but those pieces need to be complete, coherent thoughts.

Let me show you four strategies for getting this right..."

[Transition]

---

### SLIDE 9: CHUNKING STRATEGIES OVERVIEW

**Title:** Four Approaches to Document Chunking

**Content:**

**1. Fixed-Size Chunking**
- Split every N tokens with overlap
- Simple, fast, may split concepts

**2. Semantic Chunking**
- Split at natural boundaries (paragraphs, sections)
- Variable sizes, better coherence

**3. Hierarchical Chunking**
- Multiple granularity levels (document → section → paragraph)
- Enables sophisticated retrieval

**4. Agentic Chunking**
- LLM analyzes and creates logical units
- Highest quality, most expensive

**Selection Criteria:** Document type, retrieval precision needs, processing budget

**Graphic:** Four-quadrant visual showing each strategy with example chunks

**GRAPHICS:**

**Graphic 1: Chunking Strategies Comparison Matrix**
- Purpose: Compare the four chunking approaches across key dimensions
- Type: Four-column comparison matrix
- Elements: Four columns (one per strategy); rows showing Complexity, Quality, Speed, Cost, Best Use Case; cells with ratings/descriptions; sample document shown being chunked four different ways
- Labels: Strategy names prominently displayed; visual quality indicators (stars or bars); cost symbols ($-$$$$); example output for each strategy
- Relationships: Trade-off arrows showing inverse relationships (quality vs. speed, simplicity vs. sophistication); recommended progression path from fixed to agentic; decision criteria at bottom

**Graphic 2: Good vs. Bad Chunking Visual Example**
- Purpose: Illustrate the impact of chunking quality on retrieval
- Type: Before/after comparison with sample text
- Elements: Sample paragraph from policy document; two chunking approaches shown (bad=mid-sentence split, good=semantic boundary); retrieval scenarios showing which approach succeeds
- Labels: "Bad Chunking" and "Good Chunking" clearly marked; red X on bad example showing context loss; green checkmark on good showing preserved meaning; retrieval query examples
- Relationships: Show how bad chunking breaks semantic coherence; demonstrate failure mode in retrieval; highlight importance of overlap in fixed-size chunking

**Graphic 3: Hierarchical Chunking Architecture**
- Purpose: Explain multi-level chunking strategy and retrieval advantages
- Type: Tree/pyramid diagram showing document hierarchy
- Elements: Document at top; branches to Sections; sections branch to Subsections; subsections to Paragraphs; each level shows summary + full text storage; retrieval paths shown at different granularities
- Labels: Level names (Document/Section/Subsection/Paragraph); storage approach at each level (summary vs. full text); retrieval strategies for different query types; metadata inheritance shown
- Relationships: Parent-child relationships between levels; different retrieval paths for different query types (broad=section level, specific=paragraph level); summary propagation up the tree

**SPEAKER NOTES:**

"There are four main chunking strategies. Let's walk through each:

Fixed-size is the simplest - split every 500 tokens with 50-token overlap. Fast to implement, but it may split mid-concept. Good for general prose.

Semantic chunking respects natural boundaries - split at paragraph or section breaks. Variable chunk sizes, but better semantic coherence. Best for structured documents.

Hierarchical chunking creates multiple levels - store both section summaries and full paragraph text. This lets you retrieve at different granularities. More complex but very powerful.

Agentic chunking uses an LLM to analyze the document and identify logical units. Highest quality boundaries, but expensive. Use this for critical documents only.

[Point to graphic]

The right choice depends on your document type and requirements. Let me show you the decision framework..."

[Transition]

---

### SLIDE 10: CHUNKING DECISION FRAMEWORK

**Title:** Choosing the Right Strategy for Your Documents

**Content:**

| Document Type | Recommended Strategy | Chunk Size | Overlap |
|---------------|---------------------|------------|---------|
| Technical docs | Semantic (by section) | 500-1000 tokens | 50-100 |
| Legal/contracts | Semantic (by clause) | 300-500 tokens | 100 |
| Conversations | By turn/exchange | Variable | 0-25 |
| Code | By function/class | Variable | 0 |
| General prose | Fixed + overlap | 400-600 tokens | 50-100 |

**Key Principles:**
- Dense content (legal, technical) = smaller chunks
- Sparse content (conversational) = larger chunks
- Always preserve complete thoughts
- Use overlap to maintain context across boundaries

**Graphic:** Decision tree showing document type leading to strategy choice

**SPEAKER NOTES:**

"Here's how to choose:

For technical documentation with clear sections, use semantic chunking by section. Chunk size 500-1000 tokens with 50-100 token overlap.

Legal documents and contracts need semantic chunking by clause. Smaller chunks - 300-500 tokens - because legal language is dense. Larger overlap to preserve dependencies.

Conversations chunk by turn or exchange. Variable sizes since conversational turns vary.

Code chunks by function or class boundaries. No overlap needed - code has natural boundaries.

General prose defaults to fixed chunking with overlap. 400-600 tokens, 50-100 token overlap.

[Point to key principles]

The pattern: dense content needs smaller chunks for precision. Sparse content needs larger chunks for context. Always preserve complete thoughts.

In Exercise 1.2, you'll implement chunking for your own documents and see the impact of these choices."

[Transition]

---

### SLIDE 11: SEGMENT 2 SUMMARY

**Title:** Document Chunking - Key Takeaways

**Content:**

**Key Takeaway:** Chunking quality determines retrieval quality. Choose strategies that preserve semantic coherence.

**Remember:**
- Too large = noise, too small = fragmentation
- Fixed-size: simple, general-purpose
- Semantic: structured documents, natural boundaries
- Hierarchical: multi-level retrieval needs
- Agentic: critical documents only

**You'll Practice:**
Exercise 1.2 - Implement and analyze chunking for test documents

**Graphic:** Visual showing the spectrum from simple to sophisticated chunking

**SPEAKER NOTES:**

"Key points on chunking:

Chunking directly determines retrieval quality. Get this right and everything else is easier.

The fundamental tradeoff: too large means noise, too small means fragmentation. You want semantically coherent units.

Start with the simple approach - fixed-size with overlap. If results aren't good enough, move to semantic chunking. Only use hierarchical or agentic if you need them.

In Exercise 1.2 this week, you'll implement chunking for real documents and analyze the results. You'll see firsthand how chunk size and strategy affect retrieval.

Questions on chunking before we move to embeddings?"

[Transition: Click to Segment 3]

---

## SEGMENT 3: EMBEDDING AND VECTOR STORAGE
### Duration: 12 minutes | Slides 12-15

---

### SLIDE 12: WHAT ARE EMBEDDINGS?

**Title:** From Text to Vectors: The Magic of Embeddings

**Content:**

**Definition:** Embeddings are dense vector representations that capture semantic meaning

**The Transformation:**
```
Text: "The customer refund policy allows returns within 30 days"
       ↓
Embedding: [0.23, -0.45, 0.67, ..., 0.12] (1536 dimensions)
       ↓
Similar to: "Our return window is one month"
       ↓
Not similar to: "Employees receive vacation benefits"
```

**Why It Works:**
- Similar meanings → similar vectors
- Enables semantic search (concept matching, not keyword matching)
- Captures relationships and context

**Graphic:** Visual showing text converting to vectors, with similar concepts clustering together in vector space

**GRAPHICS:**

**Graphic 1: Text to Vector Transformation**
- Purpose: Visualize how text is converted to numerical vectors through embedding
- Type: Process flow with visual transformation
- Elements: Text sentence at top → Embedding model (neural network icon) in middle → Vector array at bottom; similar texts shown converging to nearby vectors; dissimilar texts shown far apart
- Labels: "Input Text" at top; "Embedding Model" in center (with model name like text-embedding-3); "Vector (1536 dimensions)" at bottom; similarity scores shown between vectors
- Relationships: Multiple example texts flowing through same model; arrows connecting similar concepts in vector space; distance/proximity indicating semantic similarity; 3D visualization showing vector clustering

**Graphic 2: Vector Space Clustering Visualization**
- Purpose: Show how semantically similar concepts cluster together in vector space
- Type: 2D/3D scatter plot (simplified from high dimensions)
- Elements: Points representing embedded text chunks; color-coded clusters by topic (HR policies=blue, Finance=green, IT procedures=red, etc.); query vector shown with search radius; similar items within radius highlighted
- Labels: Cluster labels; distance metrics shown; query point clearly marked; nearest neighbors highlighted; axes labeled "Semantic Dimension 1" and "Semantic Dimension 2" (note: simplified from 1536D)
- Relationships: Clusters showing topical grouping; overlap areas showing related concepts; search radius demonstrating similarity threshold; arrows from query to retrieved results

**Graphic 3: Embedding Model Selection Decision Tree**
- Purpose: Guide users through choosing appropriate embedding model
- Type: Decision tree with model recommendations
- Elements: Decision nodes based on criteria (Domain specificity, Scale, Privacy requirements, Budget); terminal nodes recommending specific models (OpenAI, Cohere, open-source options)
- Labels: Decision criteria clearly stated; model names with key specs (dimensions, cost, performance); pros/cons for each recommendation; use case examples
- Relationships: Flow from requirements to recommendations; trade-off visualization between cost/quality/control; migration paths showing evolution as needs change

**SPEAKER NOTES:**

"Now we get to the magic: embeddings.

An embedding is a dense vector representation of text. Instead of words, you have numbers - typically 384 to 1536 dimensions.

[Point to example]

Here's a sentence about refund policy. When we embed it, we get a vector of numbers. That vector captures the semantic meaning.

The magic: similar meanings produce similar vectors. A sentence about returns and refunds will have a vector close to our original, even if it uses completely different words.

But a sentence about vacation benefits will be far away in vector space.

This is why RAG works - we can find semantically similar content, not just keyword matches.

The question is: which embedding model should you use?"

[Transition]

---

### SLIDE 13: CHOOSING EMBEDDING MODELS

**Title:** Embedding Model Selection Framework

**Content:**

| Consideration | Options | Trade-offs |
|---------------|---------|------------|
| **Model Quality** | OpenAI ada-002, Cohere, Voyage, open-source | Quality vs. cost vs. privacy |
| **Dimension Size** | 384, 768, 1536 | More dimensions = more nuance = more cost/storage |
| **Domain** | General-purpose vs. specialized | Medical, legal, code-specific models may outperform |
| **Cost** | $0.0001 - $0.0004 per 1K tokens | Adds up at scale |
| **Latency** | API vs. self-hosted | Trade control for convenience |

**Recommendations:**
- **Start:** OpenAI text-embedding-3-small (cheap, good quality)
- **Production:** Test domain-specific models for your use case
- **Scale:** Consider self-hosted models to reduce ongoing costs

**Graphic:** Comparison matrix showing model options plotted on quality/cost axes

**SPEAKER NOTES:**

"Choosing an embedding model involves several trade-offs:

Model quality matters - OpenAI's ada-002 and text-embedding-3 models are solid general-purpose choices. Cohere and Voyage offer alternatives. Open-source models like sentence-transformers work well for self-hosting.

Dimension size: 384 dimensions is fast and cheap. 768 is a good middle ground. 1536 captures the most nuance but costs more in storage and compute.

Domain specialization: if you're working with medical, legal, or code documents, domain-specific models often outperform general ones.

Cost varies significantly - from $0.0001 to $0.0004 per 1000 tokens. At millions of chunks, this matters.

[Point to recommendations]

My recommendation: start with OpenAI text-embedding-3-small. It's cheap, fast, and good quality. As you scale, test domain-specific models for your use case. If you hit cost issues, explore self-hosted open-source models.

Now let's talk about where these embeddings live..."

[Transition]

---

### SLIDE 14: VECTOR DATABASES

**Title:** Storing and Searching Vector Embeddings

**Content:**

**Vector Store Components:**
```
Vector Database
├── Index: Enables fast similarity search (HNSW, IVF, FLAT)
├── Vectors: Stored embeddings (your chunks)
├── Metadata: Source, date, type, permissions, etc.
└── Search: Approximate Nearest Neighbor (ANN) algorithms
```

**Key Capabilities:**
- Fast similarity search (milliseconds for millions of vectors)
- Metadata filtering (pre/post retrieval)
- Hybrid search (vector + keyword)
- Namespaces/collections for multi-tenancy

**Popular Options:**
- **Hosted:** Pinecone, Weaviate Cloud, Qdrant Cloud
- **Self-hosted:** Qdrant, Milvus, Chroma
- **Extensions:** pgvector (Postgres), Azure AI Search

**Graphic:** Diagram showing vector database architecture with index, vectors, and metadata layers

**SPEAKER NOTES:**

"Your embeddings need a home - a vector database.

[Walk through components]

The index enables fast similarity search. Popular algorithms: HNSW (hierarchical graph), IVF (inverted file), or FLAT (brute force for small datasets).

Vectors are your actual embeddings - one per chunk.

Metadata is critical - source document, page numbers, dates, permissions, document type. This enables filtering.

Search uses Approximate Nearest Neighbor algorithms. 'Approximate' because exact search is too slow - ANN gives you near-perfect results in milliseconds.

Key capabilities: fast search, metadata filtering, hybrid search combining vectors with keywords, and namespaces for isolating different projects or tenants.

[Point to options]

For getting started: Pinecone is easiest (fully hosted). Qdrant or Chroma work well self-hosted. If you already use Postgres, pgvector is compelling.

Let me show you the metadata strategy..."

[Transition]

---

### SLIDE 15: METADATA STRATEGY

**Title:** Metadata: The Secret to Great Retrieval

**Content:**

**Example Metadata Structure:**
```json
{
  "chunk_id": "doc-123-chunk-5",
  "source_document": "policy-handbook-2024.pdf",
  "section": "Employee Benefits",
  "page_number": 45,
  "created_date": "2024-01-15",
  "document_type": "policy",
  "access_level": "internal",
  "version": "2.1",
  "author": "HR Department"
}
```

**Why Metadata Matters:**
- **Filtering:** "Only search policy documents from 2024"
- **Access control:** Filter by user permissions
- **Citations:** Include source, page, section in responses
- **Debugging:** Track which chunks are retrieving

**Best Practices:**
- Inherit metadata from parent documents
- Include temporal information (dates, versions)
- Add access control fields upfront
- Store enough to generate meaningful citations

**Graphic:** Visual showing a chunk with its associated metadata fields

**SPEAKER NOTES:**

"Metadata is often overlooked but it's critical for production RAG.

[Point to JSON example]

Here's a well-structured metadata object. We have:
- Identifiers: chunk_id, source_document
- Content context: section, page_number
- Temporal: created_date, version
- Classification: document_type, access_level
- Provenance: author

This metadata enables powerful filtering. You can search only policy documents, only from 2024, only accessible to this user.

It powers citations - your response can say 'According to the Employee Benefits section, page 45 of the Policy Handbook...'

It helps debugging - you can see which chunks are being retrieved and why.

[Point to best practices]

Best practices: inherit metadata from parent documents, include dates and versions, add access control fields from day one, and store enough information to generate meaningful citations.

In Exercise 1.1, you'll design your metadata strategy as part of your RAG architecture.

Questions on embeddings or vector storage before we move to retrieval?"

[Transition: Click to Segment 4]

---

## SEGMENT 4: BASIC RETRIEVAL PIPELINE
### Duration: 9 minutes | Slides 16-18

---

### SLIDE 16: THE RETRIEVAL PROCESS

**Title:** From Query to Context: The Retrieval Pipeline

**Content:**

**Retrieval Flow:**
```
1. User query arrives
2. Embed query (same model as chunks)
3. Similarity search (top-k chunks)
4. Apply metadata filters (optional)
5. Return ranked chunks
6. Format for LLM context
7. Generate response with citations
```

**Key Decisions:**
- **Similarity metric:** Cosine (most common), Euclidean, Dot Product
- **Top-k:** How many chunks to retrieve (typical: 3-10)
- **Threshold:** Minimum similarity score (optional)
- **Reranking:** Re-order results for quality (Week 2 topic)

**Graphic:** Flow diagram showing query transformation through each step to final context

**SPEAKER NOTES:**

"Let's put it all together with the retrieval pipeline.

[Walk through the flow]

Step 1: User asks a question. 'What's the vacation policy?'

Step 2: Embed that query using the same embedding model you used for chunks. Critical - must be the same model.

Step 3: Similarity search against your vector database. Request top-k chunks - we'll talk about choosing k in a moment.

Step 4: Apply any metadata filters. Maybe you only want current-year documents, or documents this user can access.

Step 5: Get back your ranked chunks, ordered by similarity score.

Step 6: Format those chunks for the LLM - we'll see the template next.

Step 7: LLM generates the response using the retrieved context.

[Point to key decisions]

Key decisions: similarity metric (usually cosine), top-k (we'll cover this next), and whether to use a similarity threshold to filter low-quality matches.

Let me show you the top-k decision..."

[Transition]

---

### SLIDE 17: TOP-K AND CONTEXT FORMATTING

**Title:** How Many Chunks? And How to Format Them?

**Content:**

**Top-K Selection:**
- **Too few (k=1-2):** Risk missing relevant information
- **Too many (k=20+):** Noise, context dilution, high cost
- **Sweet spot (k=3-10):** Balance coverage and precision
- **Adjust based on:** Query complexity, chunk size, context window budget

**Context Template:**
```
System: You are an assistant with access to company knowledge.

Retrieved Context:
---
[Source: policy-handbook.pdf, page 45]
{chunk_1_content}
---
[Source: faq-document.pdf, section 3]
{chunk_2_content}
---

User Query: {original_query}

Instructions: Answer based on the provided context.
If the context doesn't contain the answer, say so clearly.
Cite your sources using [Source: filename, location] format.
```

**Graphic:** Visual showing different top-k values and their impact on response quality

**SPEAKER NOTES:**

"Two critical choices: how many chunks, and how to format them.

Top-k is the number of chunks you retrieve. Too few and you miss relevant information. Too many and you add noise, dilute the context, and burn tokens.

The sweet spot is usually 3-10 chunks. Start with 5. If you're missing information, increase. If you're getting irrelevant content, decrease.

Adjust based on your query complexity - simple factual questions might need fewer chunks, complex analytical questions need more.

[Point to template]

Here's how to format context for the LLM.

System message: establish the assistant's role.

Retrieved context: each chunk clearly marked with its source. Notice we include the source filename and location - this enables citations.

User query: the original question.

Instructions: critical - tell the model to answer from context, admit when the answer isn't there, and cite sources.

This template structure dramatically reduces hallucination and improves answer quality.

In Exercise 1.3, you'll test retrieval quality and iterate on these parameters."

[Transition]

---

### SLIDE 18: SEGMENT 4 SUMMARY

**Title:** Basic Retrieval Pipeline - Key Takeaways

**Content:**

**Key Takeaway:** Retrieval quality depends on the right k, similarity metric, and context formatting.

**Remember:**
- Query → Embed → Search → Filter → Rank → Format → Generate
- Top-k: 3-10 is typical, adjust for your use case
- Use cosine similarity for most embedding models
- Format context with clear source attribution
- Instruct the model to cite sources and admit uncertainty

**You'll Practice:**
Exercise 1.3 - Test retrieval quality with sample queries

**Graphic:** Complete RAG pipeline diagram from documents to response

**SPEAKER NOTES:**

"Final takeaways on retrieval:

The pipeline is: query, embed, search, filter, rank, format, generate.

Top-k typically falls between 3 and 10. Start at 5, adjust based on results.

Cosine similarity works well for most embedding models. Check your model's documentation.

Context formatting matters - clear source attribution enables citations and debugging.

Always instruct the model to cite sources and admit when it doesn't know. This is how you build trust.

In Exercise 1.3, you'll test retrieval quality with real queries and measure precision. You'll see where the pipeline works and where it needs tuning.

That's the foundation of RAG. Let's preview your homework."

[Transition: Click to Closing]

---

## CLOSING SECTION
### Duration: 3 minutes | Slides 19-21

---

### SLIDE 19: HOMEWORK OVERVIEW

**Title:** This Week's Practice: Building Your RAG System

**Content:**

| Exercise | Time | Deliverable | Skills Practiced |
|----------|------|-------------|------------------|
| Exercise 1.1: RAG Architecture Design | 25 min | `rag-architecture-design.md` | Architecture decisions, component selection |
| Exercise 1.2: Implement Chunking Pipeline | 30 min | Chunking implementation + analysis | Chunking strategies, quality assessment |
| Exercise 1.3: Basic Retrieval Testing | 20 min | `retrieval-quality-test.md` | Retrieval evaluation, metrics |
| **Total** | **75 min** | | |

**Graphic:** Three-step workflow showing exercises building on each other

**SPEAKER NOTES:**

"Here's your homework for this week. You have 75 minutes of exercises to complete before Session 2.

Exercise 1.1, about 25 minutes: Design your complete RAG architecture for a real use case. Choose knowledge sources, chunking strategy, embedding model, vector database. Document your rationale.

Exercise 1.2, about 30 minutes: Implement chunking for real documents. Test different strategies, analyze quality, refine your configuration.

Exercise 1.3, about 20 minutes: Test retrieval quality with sample queries. Measure precision, identify issues, document improvements for next week.

These exercises build on each other - complete them in order.

All detailed instructions are in your participant guide, along with templates."

[Transition]

---

### SLIDE 20: RESOURCES

**Title:** Resources for This Week

**Content:**

**Templates & Files:**
- RAG Architecture Template - See participant guide
- Chunking Configuration Template - See participant guide
- Retrieval Testing Template - See participant guide

**Reference Materials:**
- OpenAI Embeddings Documentation
- Vector Database Comparison Guide
- Chunking Strategies Research

**Module Resources:**
- Appendix A: RAG Architecture Template
- Appendix B: Chunking Strategy Guide
- Appendix C: RAG Evaluation Framework

**Support:**
- Questions: [Async channel name]
- Office Hours: [Time/location if applicable]

**Graphic:** QR code or resource icon linking to materials

**SPEAKER NOTES:**

"You have several resources to support your homework:

Templates for all three exercises are in your participant guide. Copy them and fill them in.

Reference materials include OpenAI's embedding documentation, vector database comparisons, and research on chunking strategies.

Module appendices A, B, and C provide detailed templates and frameworks.

If you get stuck, post in [async channel]. I monitor it daily and your peers often answer quickly.

All materials are in your participant guide."

[Transition]

---

### SLIDE 21: NEXT SESSION PREVIEW

**Title:** Next Session: Production RAG & Agent Integration

**Content:**

**Preview:**
Session 2 covers advanced retrieval, agent integration, evaluation, and production considerations.

**What to Complete Before Then:**
- [ ] Exercise 1.1: RAG Architecture Design
- [ ] Exercise 1.2: Implement Chunking Pipeline
- [ ] Exercise 1.3: Basic Retrieval Testing

**Topics We'll Cover:**
- Hybrid search and re-ranking
- Agent-RAG integration patterns
- Evaluation frameworks
- Production scaling and security

**Key Preparation:**
Have your basic RAG system from this week's exercises ready to enhance

**Graphic:** Preview image showing advanced RAG patterns

**SPEAKER NOTES:**

"Next session we'll level up your RAG system.

We'll cover hybrid search - combining vector and keyword retrieval. Re-ranking for better quality. Different patterns for integrating RAG with agents.

We'll build evaluation frameworks so you can measure quality objectively.

And we'll tackle production considerations - scaling, security, updates, monitoring.

Make sure you've completed all three exercises before next session. We'll be building directly on your work.

Have your basic RAG system ready to enhance.

[Final close]

Excellent session today. You now understand RAG fundamentals. This week, you'll design and build your first RAG system.

Remember: start simple, measure quality, iterate.

See you next session!"

---

## Appendix: Presentation Guidelines

### Timing Notes
- Opening must be brisk (3 min max) - participants want to get to content
- Segment 1 introduces concepts (12 min)
- Segment 2 dives into chunking details (12 min)
- Segment 3 covers embeddings (12 min)
- Segment 4 puts it together (9 min)
- Closing must happen even if running behind (3 min min)

### Backup Plans
- If demo/technical content fails: Use conceptual explanations and defer hands-on to exercises
- If running behind: Shorten examples in Segments 2-3, maintain full Segment 1 and closing
- If running ahead: Add Q&A, discuss edge cases, preview advanced patterns from Session 2

### Key Messages to Emphasize
1. "RAG quality depends on retrieval quality"
2. "Chunking makes or breaks RAG"
3. "Start simple, measure, iterate"

---

**Version History:**

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2026-01-02 | Initial presentation created | Claude |
