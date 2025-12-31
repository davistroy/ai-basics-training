# **POWERPOINT PRESENTATION: THE AGENT MEMORY META-FRAMEWORK**
## **48 Slides with Complete Speaker Notes**

---

## **SLIDE 1: TITLE SLIDE**

**Title**: Why Your AI Agents Keep Failing
**Subtitle**: The Memory Architecture Framework for Agents That Actually Finish Work

**Content**:
- [Company/Presenter Name]
- [Date]

**Graphic**: Simple illustration of a robot with a question mark above its head, surrounded by incomplete task checkboxes

**SPEAKER NOTES**:

[OPENING - Establish credibility and connection]

"Good morning/afternoon. By show of hands, how many of you have either deployed or are planning to deploy AI agents in your organization? [Pause for hands] Great. Now keep your hand up if those agents are actually finishing the work you give them consistently. [Most hands go down] Right. That's what we're here to talk about.

I promise you this isn't another presentation about which model to use or how to write better prompts. This is about why your agents keep failing—and it has nothing to do with the intelligence of the AI.

Over the next [45-50] minutes, we're going to solve a problem that's costing organizations millions in failed AI investments. And the solution is going to feel both obvious and revolutionary at the same time. Let's dive in."

[Transition: Click to next slide]

"Let's start with just how big this problem has become..."

---

## **SLIDE 2: THE PROBLEM STATEMENT**

**Title**: The 750% Problem

**Content**:
- Gartner: 750% surge in AI agent inquiries in 2024
- But organizations keep asking the same question:
  - "Why do our agents fail on tasks spanning multiple sessions?"
- The demos look amazing
- The production deployments... not so much

**Graphic**: Line graph showing dramatic upward trend in "AI Agent Interest" vs flat or declining line for "Production Success Rate" - the two lines diverging sharply

**SPEAKER NOTES**:

"Gartner reported a 750% surge in AI agent-related inquiries in 2024. That's not a typo—seven hundred and fifty percent. Every enterprise wants agents. Every vendor is selling them. Every consultant is recommending them.

But here's the uncomfortable truth: [Point to diverging lines] Interest is through the roof, but production success? Flat or declining. This isn't a small gap—it's a chasm.

And the question I keep hearing from organizations isn't 'which model should we use?' It's 'why do our agents keep failing on tasks that take more than one session?' 

[Pause for effect]

The demos are spectacular. You've seen them. An agent writes code, conducts research, analyzes data—all in one impressive burst. Leadership gets excited. Budgets get approved. Deployment happens.

And then... crickets. Or worse, the agent wanders around doing random things and declaring victory when nothing's actually done.

Sound familiar?"

[Transition]

"So what's actually going wrong? The answer is going to surprise you..."

---

## **SLIDE 3: THE REAL CULPRIT**

**Title**: It's Not an Intelligence Problem

**Content**:
**What Leaders Think:**
- "We need a smarter model"
- "We need longer context windows"
- "We need better prompts"

**What's Actually Happening:**
- ✓ Models are capable
- ✓ Context windows are large
- ✗ Agents have no memory of what they did yesterday

**Graphic**: Split-screen comparison. Left side: Brain with increasing IQ scores. Right side: Calendar pages flipping with agent saying "Who am I? What was I doing?" each day

**SPEAKER NOTES**:

"When agents fail, here's what I hear from leadership: [Point to left column]
- 'We need GPT-5' or 'We need Claude Opus'
- 'We need those million-token context windows'
- 'We need a prompt engineer'

And look, I get it. These seem like the obvious answers. But they're wrong.

The models are genuinely capable—I mean, genuinely impressive. Claude, GPT-4, Gemini—these systems can code, reason, analyze. The capability question is settled.

Context windows? We have models that can process millions of tokens. That's not the bottleneck.

The actual problem? [Point to right side] Every single session, your agent wakes up with complete amnesia. It has no grounded sense of where the work stands. It's like hiring a brilliant contractor who gets a concussion every night and forgets everything they did.

[Light humor] It's not that your agent is dumb. It's that it has no idea what it did yesterday, what it's supposed to be doing today, or what 'done' even means.

This is a memory problem masquerading as an intelligence problem."

[Transition]

"Let me show you what this actually looks like in practice..."

---

## **SLIDE 4: THE AMNESIAC WITH A TOOLBELT**

**Title**: What You Actually Built

**Content**:
"Every session is a brand new intern who has never seen this project before"

**Without structured memory, you get:**
- Different definitions of "done" each session
- Repeated failed attempts (no learning)
- Premature declarations of completion
- Work that never actually finishes

**Graphic**: Illustration of multiple identical workers approaching the same partially-built structure, each with confused expression, starting over from scratch. Tools scattered around showing abandoned attempts.

**SPEAKER NOTES**:

"I call this the 'Amnesiac with a Toolbelt' problem. You've given your agent access to your codebase, your APIs, your databases—it's got all the tools. It's got the capability. But here's what actually happens:

Monday: Agent starts working on a feature. Tries approach A. Fails. Tries approach B. Makes some progress.

Tuesday: New session. Agent has no memory of Monday. Tries approach A again—the thing that already failed. Eventually tries something new. Maybe makes more progress.

Wednesday: New session. You guessed it—tries approach A again. Or declares the feature complete when it's only half done because it has no idea what 'done' means in your context.

[Personal story - adjust to your experience]
I watched a team at a Fortune 500 company spend three weeks with an agent that kept rewriting the same authentication module every single day. Same bugs. Same failures. No learning. Because every session was like hiring a new intern who'd never seen the project.

The problem isn't the intern's intelligence. The problem is they have no onboarding, no project documentation, no memory of what happened before they arrived.

[Point to graphic] Look at this—every worker approaching the same structure fresh, confused, starting over. That's your production agent right now."

[Transition]

"Now, you might be thinking: 'But we have huge context windows! Can't we just give the agent all the history?' Let me show you why that makes things worse, not better..."

---

## **SLIDE 5: WHY "MORE CONTEXT" FAILS**

**Title**: The Context Window Trap

**Research Findings:**
- "Lost in the Middle" study: Models ignore information in middle of long inputs
- 18-model test (Chroma Research): Performance degrades as input length increases
- **Counterintuitive result**: Complete histories perform WORSE than curated excerpts

**The Marketing Lie:**
"Million-token context windows solve the memory problem"

**The Reality:**
Longer windows introduce their own failure modes

**Graphic**: Funnel diagram with "All Context" being poured in at top, but showing "Attention" only focusing on beginning and end, with middle section grayed out and labeled "Lost in the Middle"

**SPEAKER NOTES**:

"So the obvious solution seems to be: 'Just feed the agent all the conversation history! We have million-token context windows now!' 

Right? Wrong. And this is where the research gets uncomfortable for vendors selling you on context window size.

There's a paper called 'Lost in the Middle'—widely cited, well-designed study. What they found: [Point to graphic] AI models pay attention to the beginning and end of long inputs, but information in the middle? Ignored. Even when it technically fits in the context window.

Then Chroma Research tested 18 different models. Their finding should concern you: performance degrades as input length increases, especially for reasoning tasks.

Here's the kicker—the counterintuitive result that nobody wants to talk about: [Emphasize this] Models often perform WORSE when you give them complete, coherent histories than when you give them only the most relevant excerpts.

Let me say that again: More context makes things worse.

[Pause]

So all that marketing about million-token context windows solving your agent memory problem? It's either uninformed or deliberately misleading. The research points in the opposite direction.

Longer windows don't solve the memory problem—they introduce their own failure modes. Stuffing everything into context causes signal degradation, attention dilution, and worse reasoning."

[Transition]

"Okay, so if bigger context windows aren't the answer, what is? Before we get to memory design, let me share an observation about what's actually working in production..."

---

## **SLIDE 6: THE MICRO-AGENT PATTERN**

**Title**: What's Actually Working in Production

**The Evolution:**
- Before agents: Deterministic DAGs (Airflow, Prefect, Dagster)
- The agent promise: LLM-driven flexibility, adaptive decision-making
- The reality: Agents reliably degrade after 10-20 turns

**The Pattern That Works:**
Small, focused agents (3-20 steps) embedded within larger deterministic workflows

```
Traditional DAG:     Step A → Step B → Step C → Step D → Step E
                     (all deterministic, all predefined)

Micro-Agent Pattern: [Deterministic] → [Agent: 5-10 steps] → [Deterministic] → [Agent: 5-10 steps]
                     (flexibility where needed, predictability everywhere else)
```

**Why It Works:**
- Bounds the context window
- Limits the scope of failures
- Leverages both deterministic reliability AND LLM flexibility

**The Uncomfortable Truth:**
A 90% success rate sounds good until you realize—can you imagine a web app that crashed on 10% of page loads?

**Graphic**: Flow diagram showing deterministic workflow boxes connected by micro-agent bubbles. Each agent bubble is small and focused. Compare to "autonomous agent" sprawl pattern (crossed out).

**SPEAKER NOTES**:

"Before we talk about memory design, let me share an observation about what's actually working in production right now.

[Point to Evolution] There's an evolution happening. Before agents, we had deterministic workflows—DAGs. Tools like Airflow, Prefect, Dagster. Every step predefined. You knew exactly what would run, when, in what order.

Then came the promise of agents: Let the LLM figure out the next step! Adaptive decision-making! No more hardcoding every branch!

And the reality? [Pause] Agents reliably degrade after 10-20 turns. They start repeating themselves, forget constraints, try failed approaches again.

[Point to Pattern] Here's what the teams actually succeeding with agents have figured out:

The most successful production agents aren't autonomous systems running indefinitely. They're SMALL, FOCUSED agents—3 to 20 steps—embedded within larger deterministic workflows.

[Point to diagram] Look at the difference. The traditional DAG: everything deterministic, predefined. The micro-agent pattern: you have deterministic code handling the predictable parts, and small agents handling the parts that need flexibility.

The agent handles flexible decision-making. Deterministic code handles everything else. Best of both worlds.

[Point to Why It Works] This works because:
- You bound the context window—agent only sees what's relevant to its small scope
- You limit failures—if an agent messes up, it's contained
- You get both reliability AND flexibility

[Emphasize uncomfortable truth] Here's the uncomfortable truth: a 90% success rate sounds impressive until you think about it.

Can you imagine using a web app that crashed on 10% of page loads? You'd uninstall it immediately.

That's the bar. That's what production means. And micro-agents are how you get there."

[Transition]

"Now let's talk about the fundamental insight that makes micro-agents—and any agent—actually work..."

---

## **SLIDE 7: THE FUNDAMENTAL INSIGHT**

**Title**: Memory Lives in Structure, Not Agents

**Core Principle:**
**Agents should be stateless. Memory should be external and structured.**

Think of it this way:
- ❌ Trying to give agents memory
- ✓ Building systems where amnesiacs can work effectively

**Analogy:**
A factory where you hire a new worker every day, but they succeed because:
- Clear task lists show what's done/pending
- Logs show what's been tried
- Procedures show how to validate work
- Records show what to do next

**Graphic**: Two side-by-side illustrations. Left: Agent with thought bubble trying to "remember" (crossed out). Right: Agent reading from clipboard/dashboard showing project status (checkmark)

**SPEAKER NOTES**:

"Here's the insight that took me way too long to internalize, and once you get it, everything else makes sense:

Stop trying to give agents memory. Instead, build systems where amnesiacs can work effectively.

[Let that land]

This sounds like a subtle distinction, but it's the difference between systems that fail and systems that work.

Think about it this way—imagine you run a factory, but for some weird reason, you have to hire a completely new worker every single day. They have skills, they have tools, but they have zero memory of what happened yesterday.

That sounds impossible, right? But actually, we know exactly how to make this work:

[Point to each bullet]
- You give them a task list showing what's completed and what's pending
- You give them logs showing what's been tried and what failed
- You give them procedures for validating their work
- You give them records showing exactly what to do next

The worker is still an amnesiac. But the FACTORY has memory. The system has memory. And because that memory is external and structured, any worker can walk in and be productive immediately.

[Point to graphic on right] That's the model. The agent doesn't remember. The agent READS. It reads from structured records that tell it everything it needs to know."

[Transition]

"Now, before we go further, I need to clarify something important because there's a lot of confusion about this..."

---

## **SLIDE 8: DOMAIN MEMORY VS. RAG**

**Title**: Not All Memory is the Same

**Content**:
| Concept | What It Does | Example |
|---------|--------------|---------|
| **RAG** (Retrieval-Augmented Generation) | Fetches potentially relevant information | Filing cabinet you search |
| **Domain Memory** | Maintains structured record of work state | Live project dashboard |

**Key Difference:**
- RAG: "Here's information that might help"
- Domain Memory: "Here's exactly where we are and what's next"

**Graphic**: Side-by-side comparison. Left: Filing cabinet with magnifying glass (RAG). Right: Project dashboard with task status, progress bars, and timeline (Domain Memory)

**SPEAKER NOTES**:

"Quick clarification because I see this confusion constantly: What I'm talking about is NOT Retrieval-Augmented Generation—RAG.

Many of you have already invested in RAG systems. You store information in vector databases, you do semantic search, you fetch relevant documents. That's useful! But it's not what we're talking about here.

[Point to table]

RAG is like having a well-organized filing cabinet. When you need information, you search for it and pull out potentially relevant documents. 'Here are some things that might help with your question.'

Domain Memory is like having a live project dashboard. It shows you exactly where the work stands. 'Task A is complete and validated. Task B failed three times with this error. Task C is next. Here's how to validate it when you're done.'

See the difference?

RAG says: 'Here's information that might be relevant.'
Domain Memory says: 'Here's exactly where we are and what's next.'

You can use both! They're complementary. But they solve different problems. RAG helps with knowledge retrieval. Domain Memory solves the work coordination problem.

If your agent needs to finish a project over multiple sessions, RAG alone won't save you. You need Domain Memory."

[Transition]

"So what does Domain Memory actually look like? It has three essential pillars..."

---

## **SLIDE 9: THE THREE PILLARS OF DOMAIN MEMORY**

**Title**: What Domain Memory Must Track

**Content**:

**1. EXPLICIT GOALS**
What "done" means with testable criteria

**2. PROGRESS RECORDS**  
What's been completed, attempted, failed

**3. OPERATING PROCEDURES**
How to validate, when to escalate, what standards apply

**These three components prevent:**
- Ambiguous success criteria
- Repeated mistakes
- Unpredictable behavior

**Graphic**: Three pillars holding up a platform labeled "Reliable Agent Performance". Each pillar labeled with one of the three components and has icon (target for goals, checklist for progress, manual/handbook for procedures)

**SPEAKER NOTES**:

"Domain Memory has three essential pillars. Miss any one of them, and the whole system becomes unreliable.

[Point to each pillar as you explain]

Pillar One: EXPLICIT GOALS. This is what 'done' means with testable criteria. Not vague instructions—specific, verifiable completion conditions.

Pillar Two: PROGRESS RECORDS. This is what's been completed, what's been attempted, what failed and why. This is your institutional memory.

Pillar Three: OPERATING PROCEDURES. This is how to validate work, when to escalate to humans, what standards apply.

[Point to base of pillars] These three things sound obvious when I say them out loud, right? But I promise you, most teams building agents aren't thinking with this degree of specificity.

They're hoping the agent will figure out what 'done' means. They're trusting the agent to remember what failed. They're assuming the agent will know how to validate its own work.

[Light humor] That's like assuming your new intern will figure out the company's quality standards through osmosis.

When you have all three pillars? [Point to platform] You get reliable agent performance. The agent knows what to do, can see what's been done, and knows how to verify it worked.

When you're missing even one? Everything falls apart."

[Transition]

"Let's dig deeper into each of these. Starting with explicit goals, because this is where I see the most catastrophic failures..."

---

## **SLIDE 10: PILLAR 1 - EXPLICIT GOALS**

**Title**: Never Let Agents Guess What "Done" Means

**Bad Example:**
"Build a customer onboarding flow"
- ❌ Too vague
- Different sessions interpret differently
- No clear stopping point

**Good Example:**
"User can log in with email and password"
- ✓ Test: run login_test.py
- ✓ All assertions must pass
- ✓ Agent knows exactly what success looks like

**Key Principle:** If you can't test it, it's not a goal—it's a wish

**Graphic**: Two paths diverging. Left path (vague goal) leads to multiple confused agents going different directions. Right path (explicit goal with test) leads to all agents converging on clear target/bullseye

**SPEAKER NOTES**:

"Pillar One: Explicit Goals. This is where most failures start.

[Point to bad example] Here's what I see constantly: 'Build a customer onboarding flow.' Sounds reasonable, right? 

Wrong. This is what I call a 'wish,' not a goal.

What's a customer onboarding flow? Does it include email verification? Password reset? OAuth options? Profile completion? At what point is it 'done'?

Ask three different agents, you'll get three different implementations. Ask the same agent three different days, you'll get three different interpretations. And you'll never know when to actually stop working on it.

[Point to good example] Now look at this: 'User can log in with email and password. Test: run login_test.py. All assertions must pass.'

THIS is a goal. It's specific. It's testable. It's unambiguous. The agent knows EXACTLY what success looks like. When login_test.py passes, you're done. Not before.

[Emphasize this] Here's my rule: If you can't test it, it's not a goal—it's a wish.

[Personal story - adjust to context]
I watched a team waste two weeks because they told their agent to 'improve the documentation.' The agent rewrote the same sections over and over because 'improve' has no testable criteria. When they changed it to 'All API endpoints have examples, all examples execute successfully'—done in three days.

[Point to graphic] Vague goals lead to divergence and confusion. Explicit, testable goals lead to convergence and completion."

[Transition]

"But even with perfect goals, you need the second pillar..."

---

## **SLIDE 11: PILLAR 2 - PROGRESS RECORDS**

**Title**: Institutional Memory Prevents Groundhog Day

**Bad Example:**
Hope the agent figures it out from conversation history
- ❌ Constructs wrong narratives
- ❌ Hallucinates what happened
- ❌ Forgets critical details

**Good Example:**
"Tuesday 2pm: Tried approach A → timeout failure
Wednesday 10am: Tried approach B → tests pass → marked complete"
- ✓ Next session sees exact history
- ✓ No repeated failures
- ✓ Clear current state

**Graphic**: Timeline showing attempts with outcomes clearly marked. Failed attempts in red with X, successful in green with checkmark. Next agent reading timeline with clear understanding (lightbulb above head)

**SPEAKER NOTES**:

"Pillar Two: Progress Records. This is your defense against Groundhog Day.

[Reference the movie if audience is right age] Remember Groundhog Day? Bill Murray waking up to the same day over and over? That's your agent without progress records.

[Point to bad example] The naive approach: 'The agent can just read the conversation history and figure it out.'

No. It can't. Or rather, it will construct a narrative, but that narrative is often wrong. The agent will hallucinate things that didn't happen, forget things that did, and generally invent its own version of reality.

Why? Because conversation history is unstructured. It's full of noise. The model has to INFER what matters, and inference means guessing, and guessing means errors.

[Point to good example] Look at this instead: A structured log with timestamps, explicit outcomes, clear status.

'Tuesday 2pm: Tried approach A, got timeout failure.'
'Wednesday 10am: Tried approach B, tests pass, marked complete.'

The next agent reads this and immediately knows: Approach A doesn't work. Approach B does. Task is complete. Move to next task.

[Real example] I saw an agent try the same database optimization seven times over three days because there was no progress log. Each time, it thought it was trying something new. It wasn't. 

With a progress log? It tried it once, logged the failure, moved on.

[Point to graphic] This is institutional memory. This is how you prevent your agent from repeating the same mistakes in an infinite loop."

[Transition]

"And the third pillar ties it all together..."

---

## **SLIDE 12: PILLAR 3 - OPERATING PROCEDURES**

**Title**: Clear Instructions, Predictable Behavior

**Without Procedures:**
- Some sessions run tests, others skip
- Some log progress, others forget
- Behavior drifts unpredictably

**With Procedures:**
"After any change:
1. Run test suite
2. If pass → update status, log action
3. If fail → log failure, try different approach
4. After 3 failures → escalate to human"

**Result:** Consistent, reliable agent behavior

**Graphic**: Flow chart showing the procedure with decision points (test pass/fail), actions at each step, and escalation path. Shows how procedure creates predictable path through work

**SPEAKER NOTES**:

"Pillar Three: Operating Procedures. This is what keeps behavior consistent.

Without explicit procedures, behavior drifts. And I mean WILDLY.

[Point to left side] Session one runs tests after making changes. Session two skips testing and just assumes it worked. Session three runs tests but doesn't log the results. Session four tests, logs, then keeps working even after three failures.

It's chaos. Each session invents its own quality standards.

[Point to right side] Compare that to this: Explicit procedures that every session follows.

'After any change: run test suite.'
That's unambiguous. Not 'maybe run tests.' Not 'run tests if you feel like it.' Run tests.

'If tests pass, update status and log what you did.'
Clear action, clear documentation.

'If tests fail, log the failure and try a different approach.'
No wandering. No giving up. Try something else.

'After three failures, stop and escalate to human.'
Ah, the safety valve. When the agent is stuck, don't let it thrash forever. Get a human involved.

[Point to flowchart] This creates predictable, reliable behavior. Every session follows the same path. Quality is consistent. Escalations happen at the right time.

This is how human teams work! We don't rely on every team member to invent their own quality standards. We document procedures and everyone follows them.

Your agents need the same structure."

[Transition]

"Okay, so now we understand what Domain Memory needs. But how do you actually architect this? This is where it gets elegant..."

---

## **SLIDE 13: THE TWO-AGENT PATTERN**

**Title**: The Architecture That Works

**Content**:
Instead of one agent trying to do everything, separate concerns:

**SETUP AGENT** (runs once)
- Takes high-level human request
- Creates structured records
- Builds task list, procedures, success criteria
- Then it's done

**WORKER AGENT** (runs repeatedly, stateless)
- Reads current state from records
- Picks ONE incomplete task
- Does work, validates, updates records
- Stops

**Next worker starts fresh, reads updated state, continues**

**Graphic**: Flow diagram showing human input → Setup Agent → creates structured records → Worker Agent 1 → updates records → Worker Agent 2 → updates records → Worker Agent 3, etc. Show records in center as persistent store that all workers access

**SPEAKER NOTES**:

"Now that we understand the three pillars, let's talk about architecture. This is Anthropic's proposed solution, and it's elegant precisely because it doesn't fight the amnesiac nature of agents—it embraces it.

The pattern has two distinct roles:

[Point to Setup Agent] The Setup Agent runs once at the beginning. It's like a project manager setting up a new project.

It takes your high-level request—'Build a login system'—and translates it into structured records. It creates:
- A detailed task list with specific completion criteria
- Progress tracking structure
- Testing procedures
- Validation protocols

Then it's done. It doesn't execute the work. It just creates the scaffolding.

[Point to Worker Agents] Then we have Worker Agents—plural. These run repeatedly, but here's the key: each one is completely stateless.

Worker Agent 1 starts up. It reads the current state from the records. It picks exactly ONE incomplete task. It does the work. It validates against the success criteria. It updates the records. It stops. It's gone.

Then Worker Agent 2 starts up—fresh, no memory of Agent 1. But it doesn't need memory! It reads the updated records. Sees what's done, what's not. Picks the next task. Does it. Updates. Stops.

[Point to flow] See how the records in the center are the constant? That's where the memory lives. The agents are just functions that transform the project from state N to state N+1.

This is brilliant because it works WITH the constraint instead of against it."

[Transition]

"Let me give you an analogy that makes this crystal clear..."

---

## **SLIDE 14: WHY THIS PATTERN WORKS**

**Title**: The Daily Contractor Analogy

**Thought Experiment:**
You must onboard a brand new contractor every morning who has never seen your project

**If you say:** "Make progress on the project"
→ Chaos, repeated work, different interpretations

**If you provide:**
- Task list with status
- Log of what's been tried
- How to validate work
- Pick one item, finish it, update records

→ Functioning system

**Key Insight:** Each contractor is still an amnesiac, but the PROJECT has memory

**Graphic**: Calendar showing different contractor each day (different faces/names), but all reading from same project board that grows/updates each day. Project board shows cumulative progress despite changing workers

**SPEAKER NOTES**:

"Here's a thought experiment that clarifies why this works:

Imagine you're running a project, but due to some bizarre constraint, you have to onboard a completely new contractor every single morning. They're talented, they have skills, but they've never seen your project before.

[Pause for effect]

Scenario One: You point them at the codebase and say 'Make progress on the project.'

What happens? [Let audience think] Chaos. Different contractors interpret 'progress' differently. Some redo work that's already done. Some try approaches that already failed. Some declare victory when you're only halfway there.

Scenario Two: You give every contractor the same onboarding:
[Point to bullets]
'Here's the task list—these are done, these aren't.'
'Here's the log of what's been tried—approach A failed, approach B worked.'
'Here's how to validate your work—run these tests.'
'Pick exactly one incomplete item, finish it, update the records.'

What happens now? You have a functioning system.

[Personal story - adjust to your context]
This is exactly how effective software teams work! I joined a codebase at [company] that I'd never seen before. But within an hour, I was productive. Why? The issue tracker showed what needed doing. The git log showed what had been tried. The tests showed what 'done' meant. I didn't need to have been there from the beginning.

[Point to graphic] Each contractor is still an amnesiac. But the PROJECT has memory. And because that memory is explicit and structured, any contractor can walk in and be productive immediately.

That's the two-agent pattern. That's why it works."

[Transition]

"Now, before we look at specific workflows, let me give you the operational principles that make agents work..."

---

## **SLIDE 15: THE 12-FACTOR AGENT PRINCIPLES**

**Title**: Operational Principles for Production Agents

**The Core Factors:**

**1. Natural Language → Tool Calls**: The agent's job is converting requests into structured actions

**2. Own Your Prompts**: Treat prompts as first-class code—don't outsource to frameworks

**3. Own Your Context Window**: Context is everything—curate ruthlessly

**4. Tools Are Structured Outputs**: Tools are JSON the LLM emits; your code decides what to do with it

**5. Unify Execution State and Business State**: Single event stream = one source of truth

**6. Launch/Pause/Resume**: Agents must be controllable like any program

**7. Contact Humans via Tool Calls**: Human interaction is a tool, not a special case

**8. Own Your Control Flow**: YOUR code controls what happens after each tool call

**9. Compact Errors into Context**: Errors are context for recovery—include them, manage them

**10. Small, Focused Agents**: 3-20 step workflows; smaller context = better performance

**11. Trigger from Anywhere**: Agents should work from Slack, email, webhooks, cron, APIs

**12. Stateless Reducer**: Think `(state, event) → state`—enables testing, parallelization, replay

**Graphic**: 12 icons in a grid, each representing one factor. Highlight that these are OPERATIONAL principles, not theoretical concepts.

**SPEAKER NOTES**:

"Let me give you the operational principles that separate demo agents from production agents. These come from the 12-Factor Agents methodology—think of it like the 12-Factor App principles, but for AI agents.

[Move quickly through these—hit highlights]

Factor 1: The core agent pattern is converting natural language to structured tool calls. 'Create a payment link for $750' becomes a JSON object with function name and parameters.

Factor 2: Own your prompts. Don't outsource prompt engineering to frameworks. The prompt IS your product. Treat it like code—version it, test it, iterate on it.

Factor 3: Own your context window. As Andrej Karpathy said, context engineering is 'the delicate art of filling the context window with just the right information for the next step.' This is YOUR competitive advantage.

Factor 4: Tools are just structured outputs. The LLM doesn't 'execute' anything—it emits JSON, and YOUR code decides what to do with it. That distinction matters for control.

Factor 5: Unify your state. Instead of separate execution state and business state that can drift apart, use a single event stream. This makes pause/resume trivial.

Factor 6: Launch, pause, resume. Agents should be controllable like any program. Critical capability: pause BETWEEN tool selection and tool execution for human approval.

Factor 7: Contact humans via tool calls. Human-in-the-loop isn't a special case—it's just another tool. Same abstraction works for agent-to-agent communication too.

Factor 8: Own your control flow. Most frameworks don't let you pause between tool selection and execution. That gap is where you add approval, rate limiting, validation.

Factor 9: Compact errors into context. LLMs can read error messages and try different approaches. But limit retries—after 3 failures, escalate.

Factor 10: Small, focused agents. We covered this—3-20 step scope. Smaller context equals better performance.

Factor 11: Trigger from anywhere. Agents as 'digital coworkers' that operate through the same channels humans use—Slack, email, webhooks, cron jobs.

Factor 12: Stateless reducer. Think of agents as pure functions: state plus event yields new state. This enables reproducibility, testing, parallelization, time-travel debugging.

[Pause]

These aren't theoretical. These are the patterns that work in production."

[Transition]

"Now let's talk about sizing—how big should an agent's scope actually be?"

---

## **SLIDE 16: SIZING YOUR AGENTS**

**Title**: How Big Should an Agent's Scope Be?

**The Sweet Spots (Production-Derived Heuristics):**

| Metric | Warning Signs | Sweet Spot |
|--------|---------------|------------|
| **Steps per task** | >20 steps: degradation likely | 3-15 steps |
| **Token accumulation** | >50K tokens: attention dilution | <30K tokens per decision |
| **Time duration** | >30 min continuous: confusion likely | 5-20 minute focused work |
| **Tool calls** | >50 calls: need context management | 10-30 calls with compaction |

**Signs Your Scope Is Too Large:**
- Agent repeats approaches it already tried
- Agent forgets constraints acknowledged earlier
- Better models don't improve performance (harness is the bottleneck)

**Signs Your Scope Is Too Small:**
- Excessive handoffs lose context
- Coordination overhead exceeds work done
- Simple tasks fragmented unnecessarily

**The Capability Edge Principle:**
"Magical moments" happen when you operate near the edge of model capability—challenging enough to showcase what the model can do, but not so challenging that it fails. As models improve, expand scope gradually.

**Graphic**: Goldilocks zone diagram showing "Too Small" (fragmented), "Just Right" (focused), and "Too Large" (overwhelmed). Include the specific metrics as callouts.

**SPEAKER NOTES**:

"So we've established: small, focused agents. But how small? How focused? Let me give you specific heuristics.

[Point to table] These are production-derived numbers—not theoretical, but observed from real systems.

Steps per task: If your agent is running more than 20 steps, expect degradation. The sweet spot is 3 to 15 steps. Enough to do meaningful work, not so much that context accumulates.

Token accumulation: If you're approaching 50K tokens in context, attention is diluting. Aim for under 30K tokens per decision. This is about what's IN the context, not what's in your storage.

Time duration: After 30 minutes of continuous work, confusion becomes likely. The sweet spot is 5 to 20 minutes of focused work. Then the agent stops, updates records, and a fresh agent continues.

Tool calls: More than 50 tool calls per task means you need serious context management. 10 to 30 calls with compaction is manageable.

[Point to 'Too Large' signs] How do you know your scope is too large?

The agent repeats approaches it already tried—that's a sign it forgot.

The agent forgets constraints it acknowledged earlier—context is too full.

And here's a critical one: if you swap in a better model and performance doesn't improve, YOUR HARNESS is the bottleneck, not the model.

[Point to 'Too Small' signs] Too small has its own problems:

Handoffs between agents lose context. Coordination overhead exceeds actual work. You've fragmented things that should stay together.

[Point to Capability Edge] The NotebookLM team calls this the 'capability edge'—you want to operate near the edge of what the model can do. Challenging enough to get value, not so challenging that it fails.

As models improve, that edge moves outward. Expand your scope gradually to match."

[Transition]

"Now, this pattern isn't just for software. Let me show you how this applies to any workflow..."

---

## **SLIDE 17: BEYOND CODE - FOUR WORKFLOW EXAMPLES**

**Title**: One Pattern, Many Domains

**Content**:

**SOFTWARE DEVELOPMENT**
- Goals: Issue tracker with test specs
- Progress: Git commits, CI/CD results  
- Procedures: Test protocols, review standards

**RESEARCH INVESTIGATION**
- Goals: Question list with status
- Progress: Evidence log, source reliability
- Procedures: Citation standards, confidence thresholds

**OPERATIONS/SUPPORT**
- Goals: Incident queue with SLAs
- Progress: Action timeline, outcomes
- Procedures: Runbook library, escalation matrix

**CONTENT PRODUCTION**
- Goals: Editorial calendar with assignments
- Progress: Draft registry, review stages
- Procedures: Style guide, approval workflow

**Graphic**: 2x2 grid showing four domains with icons (code, microscope, gear, pen). Each shows mini version of the three pillars adapted to that domain.

**SPEAKER NOTES**:

"Now you might be thinking: 'This makes sense for software, but we're not a software company.'

Great news: This pattern works for any workflow where you need an agent to accomplish something over time.

[Point to each quadrant as you explain]

Software Development is the obvious one. Developers have spent decades building these systems for human teams. Issue trackers ARE goal artifacts. Git logs ARE progress records. Test suites and code review standards ARE operating procedures.

But look at Research: Your goals are questions you need answered—'Is this approach viable?' 'What does the evidence show?' Your progress records are your evidence log—which sources you've checked, what they contributed, how reliable they are. Your procedures are citation standards and confidence thresholds.

Operations: Your goals are incidents that need resolving with SLA requirements. Your progress records are timelines of actions taken. Your procedures are runbooks and escalation protocols.

Content Production: Editorial calendar with assignments. Draft registry tracking versions and review stages. Style guides and approval workflows.

[Emphasize this] See the pattern? Every domain has the same structure:
- What needs to be done (goals)
- What's been done (progress)
- How to do it right (procedures)

The challenge for non-software domains is that these structures often don't exist explicitly—they're in people's heads. You have to design them.

But once you do? The two-agent pattern works exactly the same way."

[Transition]

"Okay, we understand what to persist in memory. Now let's talk about the other half of the equation: what to load into context. This is where context engineering comes in..."

---

## **SLIDE 18: CONTEXT ARCHITECTURE - THE FOUR TIERS**

**Title**: Not Everything Belongs in Active Context

**Content**:

**Tier 1: Working Context** (Active now)
- Current prompt, immediate task
- Minimal, high-signal only

**Tier 2: Session State** (This conversation)
- Structured event stream
- Filtered as needed

**Tier 3: Persistent Memory** (Across sessions)
- Historical patterns, preferences
- Retrieved on-demand

**Tier 4: Artifacts** (Large data)
- Files, databases
- Referenced, not pasted

**Graphic**: Pyramid or layered architecture diagram. Smallest layer at top (Working Context) is actively lit up. Layers get progressively larger going down. Arrows showing selective retrieval from lower layers to top layer. Label showing "Attention Budget" pointing to top layer only

**SPEAKER NOTES**:

"We've talked about what to persist. Now let's talk about what to load. Because here's a critical distinction: Just because something is in memory doesn't mean it needs to be in active context.

Think of this as a four-tier architecture:

[Point to Tier 1] Working Context is what the model sees RIGHT NOW. This is your current prompt, the immediate task, the essential information needed for this specific decision. This should be minimal—only high-signal information.

[Point to Tier 2] Session State is the structured record of this particular conversation. Not raw text—structured events. You filter this and pull in what's relevant for working context.

[Point to Tier 3] Persistent Memory is everything that spans multiple sessions. User preferences, past conversation patterns, learned insights. You retrieve from this on-demand, not automatically.

[Point to Tier 4] Artifacts are your large data—files, databases, documents. These are never pasted into context. They're referenced by identifier and loaded just-in-time when needed.

[Point to attention budget callout] Here's why this matters: [Emphasize] The model only has so much attention to give. Every token you put in working context competes for that attention.

Think of it like this: [Analogy] Your working memory can hold about 7 items at once. If I tell you 50 things, you'll remember the first few and the last few, but the middle gets lost.

AI models have the same constraint. It's called an 'attention budget.'

So you need to be ruthlessly selective about what goes into Tier 1—the working context. Everything else lives in the lower tiers and gets pulled in only when needed."

[Transition]

"This brings us to one of the most important concepts in context engineering..."

---

## **SLIDE 19: THE ATTENTION BUDGET**

**Title**: Context is a Finite Resource

**The Constraint:**
- Transformer architecture creates n² relationships for n tokens
- Models trained on shorter sequences
- Performance degrades as context fills ("context rot")

**The Principle:**
Find the SMALLEST set of HIGH-SIGNAL tokens that achieve your goal

**Not About:**
- Cramming everything in
- "Using" your context window
- Complete conversation history

**About:**
- Ruthless curation
- Just-in-time loading
- Progressive disclosure

**Graphic**: Gas gauge showing "Attention Budget" with needle dropping as context size increases. Or: Spotlight getting dimmer and more diffuse as area (context) expands

**SPEAKER NOTES**:

"The attention budget is one of the most critical concepts in context engineering, and most teams don't think about it at all.

Here's the technical reality: [Point to constraints]

Transformer models—the architecture behind all these LLMs—create pairwise relationships between every token. That's n-squared complexity. As your context grows, the model's ability to track all these relationships gets stretched thin.

Plus, models are trained mostly on shorter sequences. They have less experience with long-context dependencies. So performance naturally degrades as the window fills—researchers call this 'context rot.'

[Point to principle] So here's the guiding principle for all context engineering:

Find the SMALLEST set of HIGH-SIGNAL tokens that maximize the likelihood of your desired outcome.

Smallest. High-signal. Not 'use your full context window.' Not 'cram everything in.' The opposite.

[Light humor] I know, I know—you paid for a million-token context window, you want to use it! But it's like having a Ferrari—just because it CAN go 200 mph doesn't mean you should drive that fast through a school zone.

[Point to 'About' section] What you're aiming for:
- Ruthless curation: Only what matters
- Just-in-time loading: Pull things in when needed, not before
- Progressive disclosure: Let the agent discover context layer by layer

[Point to graphic] Think of your attention budget like a gas tank. The more tokens you add, the more it depletes. You want to make every token count."

[Transition]

"So how do you actually manage this over long tasks? There are three primary strategies..."

---

## **SLIDE 20: THREE STRATEGIES FOR LONG TASKS**

**Title**: Managing Context Over Time

**1. COMPACTION**
- Summarize conversation nearing limit
- Keep critical details, discard redundancy
- Restart with compressed summary
- **Use for:** Tasks needing extensive back-and-forth

**2. STRUCTURED NOTE-TAKING**
- Agent writes persistent notes outside context
- Retrieved when needed
- **Use for:** Iterative development with milestones

**3. SUB-AGENT ARCHITECTURE**
- Specialized agents with clean contexts
- Return condensed summaries
- **Use for:** Complex research, parallel exploration

**Graphic**: Three panels showing each strategy visually. Compaction: Large document → compression arrows → smaller document. Note-taking: Agent writing to external notebook. Sub-agents: Main agent coordinating multiple specialist agents, receiving summary reports

**SPEAKER NOTES**:

"When tasks run for hours or span multiple sessions, context management becomes critical. You have three main strategies, and which one you use depends on your task characteristics.

[Point to Strategy 1] Compaction is exactly what it sounds like. When your conversation is approaching the context limit, you summarize it. You keep architectural decisions, unresolved bugs, implementation details—the high-value stuff. You discard redundant tool outputs and repeated information.

Then you restart with the compressed summary. The agent continues with the essence of what came before, but without all the noise.

This is what Claude Code does—it compacts the history plus keeps the five most recently accessed files. You get continuity without hitting context limits.

Use this when you have tasks requiring extensive back-and-forth interaction.

[Point to Strategy 2] Structured Note-Taking is different. The agent writes notes to persistent storage outside the context window. These notes get pulled back in when needed.

Claude playing Pokémon is a great example—the agent tracked objectives across thousands of game steps. 'Trained Pikachu 8 levels toward target of 10.' It developed maps, logged achievements, maintained strategy notes—all outside context.

After context resets, it read its own notes and continued. No loss of coherence.

Use this for iterative development with clear milestones.

[Point to Strategy 3] Sub-Agent Architecture splits the work. You have a main coordinating agent and specialized sub-agents for focused tasks.

Each sub-agent explores deeply—maybe using tens of thousands of tokens—but returns only a condensed summary to the main agent. Maybe 1,000-2,000 tokens.

The detailed exploration stays isolated. The main agent just gets the distilled results.

Use this for complex research or when parallel exploration adds value.

[Emphasize] These aren't mutually exclusive! You can combine them. The key is matching strategy to task characteristics."

[Transition]

"Now let me show you a specific technique that's becoming increasingly important..."

---

## **SLIDE 21: JUST-IN-TIME CONTEXT LOADING**

**Title**: Progressive Disclosure Over Pre-Loading

**Traditional Approach:**
Load everything that might be relevant upfront
- → Context bloat
- → Attention dilution  
- → Stale information

**Progressive Disclosure:**
- Provide lightweight identifiers (file paths, links, queries)
- Agent loads what it needs, when it needs it
- Explores layer by layer

**Mirrors Human Cognition:**
We don't memorize entire libraries—we maintain indexes and retrieve on demand

**Graphic**: Two comparison diagrams. Top: "Pre-load" showing everything dumped into context at once (overwhelmed agent). Bottom: "Just-in-time" showing agent with tools reaching out to grab specific items as needed (focused agent)

**SPEAKER NOTES**:

"Here's a shift in thinking that's happening across the industry: moving from pre-loading to just-in-time context loading.

[Point to traditional approach] The old way: Before the agent starts work, you try to anticipate everything it might need. You load all potentially relevant files, all potentially useful data, all possibly important context.

What happens? Context bloat. The agent's attention gets diluted across dozens of things it doesn't actually need. And some of that information is stale by the time it's used.

[Point to progressive disclosure] The new way: You give the agent lightweight identifiers—file paths, database queries, web links—and tools to load what it needs, when it needs it.

The agent explores progressively. It might start by listing files in a directory. Based on what it sees, it reads specific files. Based on what it finds, it searches deeper.

Layer by layer, it builds understanding. And at any moment, only the currently relevant information is in context.

[Analogy] Think about how you work. You don't memorize an entire codebase before starting a task. You have file systems, search tools, git logs. You navigate to what you need when you need it.

That's what we're enabling here.

[Point to graphic - bottom] See the difference? The just-in-time agent is focused. It has exactly what it needs, nothing more. It's not overwhelmed by information it doesn't need yet.

This is how Claude Code works. It doesn't load entire codebases into context. It uses grep, glob, and targeted file reads to explore and load just what's relevant."

[Transition]

"But this just-in-time approach only works if you have the right infrastructure. Let me show you how to think about context as a compiled view..."

---

## **SLIDE 22: THE COMPILATION PIPELINE**

**Title**: From Storage to Working Context

**Content**:
Context isn't a mutable string—it's a compiled view

**Pipeline:**
```
[Storage Layers] 
    ↓
[Selection] - Rank by relevance
    ↓
[Filtering] - Remove noise
    ↓  
[Compaction] - Summarize redundancy
    ↓
[Formatting] - Structure for model
    ↓
[Working Context]
```

**This makes context:**
- Observable (inspect each stage)
- Testable (verify transformations)
- Evolvable (change without breaking storage)

**Graphic**: Industrial assembly line or compiler pipeline. Raw materials (diverse data types) enter left side, go through processing stages, emerge as refined "Working Context" on right. Each stage labeled with its function

**SPEAKER NOTES**:

"This is where we get into some sophisticated engineering, but the metaphor makes it clear: Context is a compiled view.

Stop thinking of context as a mutable string buffer that you append to. That's the old model. 

Instead, think of it as a compilation process. You have raw source materials—your storage layers—and you transform them through a pipeline into the final working context.

[Walk through pipeline]

Stage 1: Selection. You rank everything by relevance. What matters most for THIS task right now?

Stage 2: Filtering. You remove noise. Tool outputs from three hours ago that aren't relevant anymore? Gone. Framework messages the model doesn't need to see? Filtered out.

Stage 3: Compaction. You summarize redundancy. If the same information appears in multiple places, consolidate it.

Stage 4: Formatting. You structure everything for the model. Clear sections, appropriate tagging, logical organization.

Result: Your working context. Lean, high-signal, perfectly suited for the current task.

[Point to benefits] Why is this better than just appending to a string?

Observable: You can inspect what happens at each stage. When something goes wrong, you can trace where.

Testable: You can verify that your transformations work correctly. Does your filter actually remove noise? Does your compaction preserve critical details?

Evolvable: You can change how you store things without breaking how you present them to the model. They're decoupled.

[Analogy] It's like software compilation. Your source code is stored one way. The compiler transforms it through multiple passes. The output is optimized for execution.

Same principle here. Storage is optimized for persistence. Working context is optimized for the model."

[Transition]

"Now let me show you how this impacts your costs—because context engineering has real financial implications..."

---

## **SLIDE 23: CACHE ECONOMICS**

**Title**: The 10x Cost Difference You're Probably Missing

**The Cache Opportunity:**
Contexts with identical prefixes can reuse cached KV computations

**Claude Pricing Example:**
| Context Type | Cost per Million Tokens |
|--------------|------------------------|
| Uncached input | $3.00 |
| Cached input | $0.30 |
| **Savings** | **10x cost reduction** |

**Requirements for Cache Stability:**
- Stable prompt prefix (NO timestamps at the start!)
- Append-only context modifications
- Deterministic serialization (watch JSON key ordering)

**The Two-Zone Architecture:**
```
[STABLE PREFIX: System prompt, identity, instructions]  ← Cached
[VARIABLE SUFFIX: Latest input, new outputs]            ← Fresh
```

**Target:** 70%+ of tokens should be cache-stable across consecutive steps

**Anti-Pattern:**
```python
# BAD: Timestamp at start destroys cache
system_prompt = f"Current time: {datetime.now()}\n\nYou are a deployment agent..."

# GOOD: Stable prefix, timestamp at end
system_prompt = "You are a deployment agent...\n\n"
variable_suffix = f"Current time: {datetime.now()}\nRecent events: ..."
```

**Graphic**: Cost comparison chart showing naive accumulation vs. computed context with caching. Show 10x cost difference visually. Include a "cache hit rate meter" showing 70%+ target.

**SPEAKER NOTES**:

"Let me show you something that has real financial impact—and most teams completely miss this.

[Point to Cache Opportunity] When you send context to models like Claude, if the prefix of your context is identical to a previous call, the model can reuse cached computations. This is called KV cache reuse.

[Point to pricing table] Look at the difference in pricing:

Uncached input costs $3.00 per million tokens.
Cached input costs $0.30 per million tokens.

That's a 10x cost reduction. Ten times.

For agents that make dozens or hundreds of calls, this adds up FAST. The difference between a $50 task and a $500 task.

[Point to Requirements] But caching only works if your context prefix is stable. Here's what breaks it:

Timestamps at the START of your prompt? Cache destroyed. Every call is unique.

Non-deterministic JSON serialization? Cache destroyed. Different key ordering, different bytes.

Modifying earlier parts of context? Cache destroyed. Only append-only modifications preserve the prefix.

[Point to Two-Zone Architecture] So you need to think in two zones:

Stable prefix: Your system prompt, agent identity, instructions that don't change. This is what gets cached.

Variable suffix: Latest user input, new tool outputs, recent events. This changes every call but doesn't break the cache.

[Point to Target] Your target: 70% or more of your tokens should be cache-stable across consecutive steps. If you're below that, you're paying 10x more than you need to.

[Point to Anti-Pattern] Here's a real mistake I see constantly:

[Show code] Someone puts 'Current time' at the START of the system prompt. Every call is unique. Zero cache hits. 10x cost multiplier.

Move that timestamp to the END, in the variable suffix. Now your prefix stays stable. Cache hits. 10x savings.

[Emphasize] This is not optimization for the sake of optimization. This is the difference between agent projects that make financial sense and projects that get killed for cost overruns."

[Transition]

"Now let's talk about what happens when things go wrong—because they will..."

---

## **SLIDE 24: ERROR RECOVERY PATTERNS**

**Title**: Designing for Graceful Degradation

**Principle:** Errors are inevitable. Design for recovery, not perfection.

**Single-Agent Error Handling:**
```python
consecutive_errors = 0
MAX_RETRIES = 3

while True:
    try:
        result = await execute_step(next_step)
        consecutive_errors = 0  # Reset on success
    except RecoverableError as e:
        consecutive_errors += 1
        session.append({"type": "error", "attempt": consecutive_errors, "error": str(e)})
        if consecutive_errors >= MAX_RETRIES:
            await escalate_to_human(context=session, message=f"Failed {MAX_RETRIES} times")
            break
```

**Multi-Agent Error Propagation:**
- Sub-agent failures return structured failure info (not crashes)
- Include: success flag, partial work completed, can_retry boolean
- Parent agent decides: retry, work around, or escalate

**Circuit Breaker Pattern:**
```python
class CircuitBreaker:
    max_iterations = 100
    timeout_seconds = 1800  # 30 minutes

    def check(self):
        if self.iteration > self.max_iterations:
            raise CircuitBreakerTripped("Iteration limit")
        if elapsed > self.timeout:
            raise CircuitBreakerTripped("Timeout")
```

**Key Insight:** LLMs can read error messages and try different approaches—but limit retries. After 3 failures, the agent is likely spinning.

**Graphic**: Flow chart showing error handling paths: Try → Success (continue) or Fail (increment counter) → Under limit (retry with different approach) or At limit (escalate to human). Include circuit breaker as safety valve.

**SPEAKER NOTES**:

"Errors are inevitable. The question is: how does your system handle them?

[Point to Single-Agent pattern] Here's the basic pattern for single-agent error handling:

You track consecutive errors. Each time something fails, increment the counter. Each time something succeeds, reset to zero.

When you hit your retry limit—I recommend 3—you stop and escalate. Don't let the agent thrash forever.

Important: Put the error into context! LLMs can read error messages and try different approaches. 'That approach timed out' gives the agent information to work with.

[Point to Multi-Agent pattern] For multi-agent systems, error propagation matters:

When a sub-agent fails, don't crash the parent. Return structured failure information.

Include: did it succeed? What partial work got done? Can we retry?

The parent agent then decides: try again, work around it, or escalate.

[Point to Circuit Breaker] And here's your safety valve—the circuit breaker pattern.

Set hard limits: maximum iterations, maximum time. If either is exceeded, trip the breaker.

This catches the case where an agent is stuck in a loop, burning tokens and time, but not making progress. The breaker stops the bleeding.

[Point to Key Insight] Here's the key insight: LLMs CAN recover from errors. They can read the error message, reason about what went wrong, and try something different.

But—and this is important—after about 3 failures on the same task, the agent is usually spinning. It's tried its best ideas. If those didn't work, it's not going to suddenly have a breakthrough.

That's when you escalate to a human. Don't let the agent thrash. Get help."

[Transition]

"Now, all of this only works if you can actually see what's happening. This is critical..."

---

## **SLIDE 25: THE OBSERVABILITY REQUIREMENT**

**Title**: If You Can't See It, You Can't Fix It

**Production Readiness Checklist:**

Can you answer these questions?
- ✓ What's in the context right now?
- ✓ Where did each piece come from?
- ✓ Why was this included?
- ✓ What was available but excluded?
- ✓ Can you replay any decision with exact context state?

**Without observability:**
- Debugging is guesswork
- Failures are mysterious
- Trust is impossible

**Graphic**: Control panel or diagnostic dashboard showing context inspection interface. Multiple views: content inventory, provenance traces, inclusion reasons, exclusion log, decision replay button. Think mission control monitoring screens

**SPEAKER NOTES**:

"Here's my litmus test for production readiness: Can you actually see what your agent sees?

Sounds simple, but most systems fail this test completely.

[Point to checklist] Let me ask you these questions about YOUR current agent system:

Can you inspect what's in the context right this moment? Not 'roughly what we think is there'—exactly what's there, token by token.

Can you trace where each piece came from? Was it user input? Tool output? Memory retrieval? Summarization?

Do you know WHY each piece was included? What triggered its retrieval or retention?

Do you have a log of what was AVAILABLE but EXCLUDED? And why it was excluded?

Can you replay any decision the agent made and see exactly what context it saw at that moment?

[Pause]

If you can't answer 'yes' to all of these, you don't have production-ready observability.

And without observability, [Point to bottom section] debugging is pure guesswork. 'Why did the agent do that?' 'I don't know, we can't see what it saw.'

Failures are mysterious. You can't trace the root cause because you can't inspect the state.

Trust becomes impossible. How can you trust a system you can't inspect?

[Personal story - adjust to context]
I worked with a team whose agent kept making bizarre decisions. They spent three days trying to figure out why. Finally, when we built proper observability, we discovered a stale piece of context from a completely unrelated task was polluting the window. Without observability, they never would have found it.

[Point to graphic] This is what you need: Mission control for your agent. Full visibility into context state at any moment."

[Transition]

"Observability lets you see what's happening. But what if your agent could learn from what's happening? That's where adaptation comes in..."

---

## **SLIDE 26: THE LEARNING LOOP**

**Title**: Agents That Get Better Over Time

**The Adaptation Cycle:**

1. **Execute** → Attempt task
2. **Observe** → Capture outcome (success/failure)
3. **Reflect** → Diagnose what worked/failed and why
4. **Extract** → Create structured lesson (not narrative)
5. **Update** → Add to domain memory
6. **Execute** → Apply learning to next task

**Critical Dependency:** Reliable feedback signals
- Code execution results
- Test outcomes
- Validation checks
- User corrections

**Graphic**: Circular flow diagram showing the 6 steps as continuous loop. In the center, show "Domain Memory" growing/improving with each cycle. Arrows showing lessons feeding back into memory, which informs next execution

**SPEAKER NOTES**:

"Everything we've talked about so far creates reliable agents. But what if we could make them better over time? That's adaptation.

This is the learning loop: [Walk through the cycle]

Step 1: Execute. The agent attempts a task.

Step 2: Observe. You capture the outcome. Did it succeed? Did it fail? What was the result?

Step 3: Reflect. You diagnose what happened. If it succeeded, why? If it failed, what went wrong?

Step 4: Extract. This is critical—you create a structured lesson. Not a narrative! Not 'that was hard.' A structured record: 'When doing X in context Y, approach A fails with error Z. Approach B succeeds.'

Step 5: Update. That lesson goes into domain memory. It becomes part of the operating procedures or the learned patterns.

Step 6: Execute again. The next task benefits from this learning.

[Point to center] See how domain memory grows and improves? This is continuous learning.

But here's the critical dependency: [Point to bottom section] You need reliable feedback signals.

Code execution results—did the code run or crash?
Test outcomes—did tests pass or fail?
Validation checks—did it meet the criteria?
User corrections—when a human steps in, what did they change?

Without reliable signals, you can't learn. Garbage in, garbage out.

[Real example] We've seen agents improve their code debugging strategies by 20-30% over time using this loop. Why? Because they accumulate structured lessons about what approaches work in what situations.

The key word is 'structured.' Not 'the last task was tricky'—that's useless. 'When refactoring database queries, approach A fails due to timeout 70% of the time. Approach B succeeds 90% of the time.' That's actionable."

[Transition]

"Now, I've been showing you general principles. Let me make this concrete with actual workflow examples..."

---

## **SLIDE 27: SOFTWARE DEVELOPMENT DEEP DIVE**

**Title**: Domain Memory for Software Engineering

**Goals Artifact: Issue Tracker**
- Each issue has test specification
- "Login with OAuth: Test runs oauth_test.py, all assertions pass"
- Status: Not Started → In Progress → Complete → Validated

**Progress Records: Git + CI/CD**
- Commits show what changed
- CI/CD results show what passed/failed
- PR comments capture review feedback

**Operating Procedures: Test Protocols**
- "After any code change, run full test suite"
- "All tests must pass before marking complete"
- "After 3 failed approaches, escalate with test logs"

**Graphic**: Mock issue tracker interface showing these elements in action with clear status indicators and test specifications

**SPEAKER NOTES**:

"Let me make this concrete. Software development is the easiest to illustrate because the infrastructure already exists.

[Point to Goals] Your issue tracker IS your goal artifact. But notice the specificity: It's not just 'Add OAuth login.' It's 'User can login with OAuth: Test runs oauth_test.py, all assertions pass.'

Every issue has testable criteria. Every issue has clear status: Not started, In Progress, Complete, Validated.

The agent doesn't guess when it's done. The tests tell it.

[Point to Progress Records] Your git commits ARE your progress records. They show exactly what changed and when. Your CI/CD results show what passed and failed.

If an agent tries approach A and the build breaks, that's in the CI/CD log. The next agent session can see it.

PR comments capture review feedback. If a human says 'this approach won't scale,' that's recorded. The next session knows.

[Point to Operating Procedures] Your test protocols ARE your operating procedures. They're explicit: 'After any code change, run the full test suite.' Not optional. Not 'if you remember.' Always.

'All tests must pass before marking complete.' Clear quality gate.

'After 3 failed approaches, escalate.' Safety valve—don't let the agent thrash forever.

[Personal example - adjust to context]
We deployed this pattern for a team migrating a legacy codebase. The agent worked for 6 hours across 3 days, maintaining perfect coherence because:
- Issue tracker showed what was done/pending
- Git showed what had been tried
- Tests showed what worked
- Procedures kept behavior consistent

No wandering. No repeated mistakes. Just steady, reliable progress."

[Transition]

"Now let's look at a very different domain—research..."

---

## **SLIDE 28: RESEARCH WORKFLOW DEEP DIVE**

**Title**: Domain Memory for Research/Investigation

**Goals Artifact: Question List**
- Questions with status: Not Started → In Progress → Answered → Unanswerable
- "Is approach X viable for use case Y?"
- Answerable only with evidence at threshold confidence

**Progress Records: Evidence Log**
- Source inventory: What's been examined
- Contribution tracking: What each source added
- Reliability rating: How trustworthy is this source?

**Operating Procedures: Citation + Confidence**
- "Claims require 2+ sources at high reliability"
- "Mark unanswerable after examining 10+ sources without consensus"
- "Low confidence conclusions require explicit uncertainty markers"

**Graphic**: Research dashboard showing question list, evidence log with sources, and confidence ratings. Show how evidence accumulates toward answering questions

**SPEAKER NOTES**:

"Research looks completely different from software, but the pattern is identical.

[Point to Goals] Your goals are questions you need to answer. But notice: each question has explicit status.

'Is approach X viable for use case Y?'

Not started—haven't looked into it yet.
In progress—gathering evidence.
Answered—have sufficient evidence at required confidence threshold.
Unanswerable—examined thoroughly, no consensus or insufficient data.

The agent doesn't make subjective judgments about when a question is 'answered.' The criteria are explicit.

[Point to Progress] Your evidence log is critical. This tracks:
- What sources have been examined (so you don't recheck the same sources)
- What each source contributed (so you can see how evidence accumulates)
- How reliable each source is (not all sources are equal)

This prevents the agent from citing low-quality sources or missing high-quality ones.

[Point to Procedures] Your operating procedures enforce research standards.

'Claims require 2+ sources at high reliability.' Can't make assertions based on one blog post.

'Mark unanswerable after examining 10+ sources without consensus.' Safety valve—sometimes there is no answer. Don't let the agent search forever.

'Low confidence conclusions require explicit uncertainty markers.' If you're not sure, say so.

[Real example - adjust to context]
A research team used this to investigate competitive landscapes. The agent examined 200+ sources across three weeks, maintaining perfect coherence because:
- Question list showed what needed investigating
- Evidence log prevented redundant searches
- Procedures ensured quality standards

The final report had properly cited, high-confidence findings. No hallucinations. No made-up sources."

[Transition]

"One more domain—operations and incident response..."

---

## **SLIDE 29: OPERATIONS WORKFLOW DEEP DIVE**

**Title**: Domain Memory for Operations/Support

**Goals Artifact: Incident Queue**
- Incidents with SLA requirements
- "Production API returning 500 errors: Resolve within 2 hours, restore service"
- Priority levels: P0 (critical) → P1 (high) → P2 (medium) → P3 (low)

**Progress Records: Action Timeline**
- Timestamp of every action taken
- Outcome of each action
- Current status of incident

**Operating Procedures: Runbook Library**
- Standard procedures for common issues
- Escalation matrix: When to page humans
- Rollback protocols: When to undo changes

**Graphic**: Incident management dashboard showing queue, timeline of actions, and runbook references with clear SLA countdown timers

**SPEAKER NOTES**:

"Operations is all about speed and reliability. The domain memory pattern fits perfectly.

[Point to Goals] Your incident queue IS your goal artifact. But each incident has specific resolution criteria and SLA requirements.

'Production API returning 500 errors: Resolve within 2 hours, restore service.'

That's testable. Service is restored or it isn't. SLA is met or it isn't.

Priority levels ensure the agent works on the right things first. P0 critical incidents come before P3 low-priority issues.

[Point to Progress] Your action timeline is essential. When you're firefighting, you need to know:
- What's been tried
- What worked or failed
- Where things stand right now

Timestamp everything. 'Restarted service at 10:15am. Error persists. Checked logs at 10:18am. Found database connection timeout.'

The next agent (or human) sees this and doesn't waste time restarting the service again.

[Point to Procedures] Runbooks are your operating procedures. Standard approaches for common issues.

'If API returns 500: Step 1, check service health. Step 2, review recent deployments. Step 3, examine error logs.'

Escalation matrix: 'If service not restored after 30 minutes, page on-call engineer.'

Rollback protocols: 'If new deployment causes errors, roll back immediately, investigate after service is stable.'

[Real example - adjust to context]
A support team handles 50-100 incidents daily. With this pattern:
- Agents resolve 70% without human intervention
- Average resolution time dropped 40%
- Zero incidents got 'lost' because state was always clear
- Escalations happen at the right time with full context

The runbooks improved over time as the system learned which approaches worked for which incident types."

[Transition]

"Now let me show you what this looks like in the real world with two case studies..."

---

## **SLIDE 30: CASE STUDY - MANUS**

**Title**: What 50+ Tool Calls Per Task Taught Us

**Background:**
Manus is one of the most widely-used consumer agents, handling complex tasks averaging **50 tool calls per session**. They've rebuilt their architecture **5 times in 6 months**.

**The Problem They Solved:**
Without context management, a 50-tool-call task would accumulate:
- 50 tool call descriptions
- 50 tool results (many large)
- Intermediate reasoning
- **Result:** 100K+ tokens, massive attention dilution

**Their Mantra: "Reduce, Offload, Isolate"**

**1. REDUCE Context:**
- Tool results have "full" and "compact" representations
- Full version stored in filesystem, compact version in context
- Newer results stay full; older results get compacted
- **100:1 input-to-output token ratio** reported

**2. OFFLOAD to Sandbox:**
- <20 atomic tools (Bash, filesystem, code execution)
- Complex operations happen in sandbox
- MCP tools exposed as CLI commands—agent executes via Bash, not bound function calls

**3. ISOLATE with Sub-Agents:**
- Planner assigns tasks via function calling
- Executor sub-agents get own context windows
- Communication via structured artifacts with schema-constrained outputs
- Sub-agents have `submit_results` tool to populate defined schema

**What Didn't Work:**
Started with `todo.md` for task planning. Result? **~1/3 of all actions** spent updating the todo list. Shifted to dedicated planner agent instead.

**Graphic**: Architecture diagram showing Manus's reduce/offload/isolate pattern. Show token flow: Large tool output → compact reference → filesystem storage. Sub-agent isolation with structured handoffs.

**SPEAKER NOTES**:

"Let me show you what this looks like at scale. Manus is one of the most widely-used consumer agents—handling complex tasks that average 50 tool calls per session.

[Pause for effect] Fifty tool calls. That's a LOT of context to manage.

[Point to Problem] Without context management, here's what would happen: 50 tool call descriptions plus 50 tool results plus all the reasoning. Many of those results are large—API responses, file contents, search results. You'd quickly hit 100K+ tokens with massive attention dilution.

Their agent would become useless halfway through the task.

[Point to Mantra] Their solution became a three-word mantra: Reduce, Offload, Isolate.

[Point to Reduce] REDUCE context aggressively. Every tool result has two representations: full and compact.

The full version—all the details—goes to the filesystem. The context only sees the compact version: 'API response saved to /results/api.json (47 records).'

Newer results stay full because they guide the next decision. Older results get compacted. Fresh signal, archived noise.

They report a 100:1 input-to-output token ratio. Input dominates cost. Every token you can cut from input is real money saved.

[Point to Offload] OFFLOAD complexity to a sandbox. They keep fewer than 20 atomic tools: Bash, filesystem operations, code execution. That's it.

Everything else? Runs in the sandbox via Bash. Even MCP tools are exposed as CLI commands. This keeps the function-calling layer minimal.

[Point to Isolate] ISOLATE context with sub-agents. The planner doesn't do all the work—it assigns tasks to executor sub-agents.

Each executor gets its own clean context window. It does focused work, then returns results via a structured schema—not a transcript, a schema.

The planner never sees the executor's full context. Just the structured results.

[Point to What Didn't Work] And here's a lesson they learned the hard way: They started with a todo.md file for task planning. The agent would update it constantly.

Result? About one-third of all actions were spent updating the todo list. Token waste.

They shifted to a dedicated planner agent instead. The planner plans; executors execute. Separation of concerns.

[Emphasize] They've rebuilt this architecture FIVE TIMES in six months. That's not failure—that's iteration. As models improve, your architecture should evolve."

[Transition]

"Now let's look at how Anthropic approaches this with Claude Code..."

---

## **SLIDE 31: CASE STUDY - CLAUDE CODE**

**Title**: Anthropic's Reference Implementation

**Key Patterns from Claude Code:**

**1. The "Right Altitude" for Prompts (Goldilocks Zone):**
| Too Low (Brittle) | Just Right | Too High (Vague) |
|-------------------|------------|------------------|
| Complex if-else hardcoded in prompts | Specific enough to guide, flexible for heuristics | "Be helpful and complete tasks" |
| Breaks on edge cases | Strong signals for desired output | Model guesses intent |
| High maintenance | Adapts to model improvements | Falsely assumes shared context |

**2. Hybrid Context Retrieval:**
- **Upfront loading:** `CLAUDE.md` files dropped into context at session start
- **Just-in-time retrieval:** `glob` and `grep` navigate filesystem on demand
- Bypasses stale indexing and complex syntax trees

**3. Progressive Disclosure:**
- Agent discovers context incrementally through exploration
- Each interaction yields signals (file sizes, naming conventions)
- Only necessary information maintained in working memory

**4. Tool Result Clearing (Lightest-Touch Compaction):**
> "Context editing automatically clears stale tool calls and results from within the context window when approaching token limits."

**5. Skills as Filesystem, Not Bound Tools:**
- Skills stored in filesystem, not as tool definitions
- Agent only needs Bash + filesystem access to discover and use them
- No need to load full skill definitions into context

**Key Insight:** "Meet models at the capability edge—challenging enough to showcase what the model can do, but not so challenging that it fails."

**Graphic**: Claude Code architecture diagram showing hybrid retrieval (upfront + JIT), progressive disclosure pattern, and skills as filesystem entries. Show the "right altitude" concept visually.

**SPEAKER NOTES**:

"Claude Code is Anthropic's CLI tool for software development—and it's essentially a reference implementation of these patterns.

[Point to Right Altitude] First, the concept of 'prompt altitude.' There's a Goldilocks zone for prompts.

Too low: You've hardcoded complex logic into your prompts. Every edge case requires a prompt update. High maintenance, brittle.

Too high: 'Be helpful and complete tasks.' Vague. The model has to guess what you actually want. No clear signals.

Just right: Specific enough to guide behavior, but flexible enough to let the model use heuristics. Strong signals for the desired output. Adapts as models improve.

[Point to Hybrid Retrieval] Second, hybrid context retrieval. Claude Code doesn't try to pre-load everything.

Some things ARE loaded upfront: CLAUDE.md files that contain project-specific instructions. These go in at session start.

But most context is just-in-time. The agent uses glob and grep to navigate the filesystem. It reads files when it needs them, not before.

This bypasses the whole problem of stale indexes or complex syntax trees. The filesystem IS the index.

[Point to Progressive Disclosure] Third, progressive disclosure. The agent discovers context incrementally.

It doesn't try to understand the entire codebase upfront. It explores. It reads a directory listing. That gives signals—file sizes suggest complexity, naming conventions hint at purpose.

Based on those signals, it digs deeper. Layer by layer, it builds understanding. At any moment, only what's currently relevant is in context.

[Point to Tool Result Clearing] Fourth, lightest-touch compaction. When the context window gets full, Claude Code automatically clears stale tool calls and results.

Not aggressive summarization. Just removing stuff that's no longer relevant. This extends how long agents can run without intervention.

[Point to Skills] Fifth—and this is elegant—skills are stored as filesystem entries, not bound tools.

The agent doesn't need 50 tool definitions loaded into context. It needs Bash and filesystem access. It can DISCOVER skills in the filesystem and use them.

This keeps the tool definition overhead minimal while maintaining unlimited capability.

[Point to Key Insight] The key insight from the Claude Code team: Meet models at the capability edge. Challenging enough to showcase what the model can do, but not so challenging that it fails.

That edge moves as models improve. Your scope should move with it."

[Transition]

"Okay, we've covered the concepts and seen concrete examples. Now let's talk about actually implementing this in your organization..."

---

## **SLIDE 32: IMPLEMENTATION ROADMAP**

**Title**: How to Build This (8-Week Plan)

**Weeks 1-2: Foundation**
- Map one workflow to domain memory
- Define success criteria for each task type
- Design progress tracking schema
- Document current operating procedures

**Weeks 3-4: Architecture**
- Implement tiered storage (working/session/persistent/artifacts)
- Build selection and filtering pipeline
- Create just-in-time loading tools
- Add basic observability

**Weeks 5-6: Patterns**
- Deploy two-agent pattern (setup + worker)
- Implement appropriate context strategy
- Enable progressive disclosure
- Test with representative workflows

**Weeks 7-8: Adaptation**
- Build feedback capture mechanisms
- Implement reflection and learning loops
- Create memory update protocols
- Monitor, measure, iterate

**Graphic**: Gantt chart or timeline showing 8 weeks with major milestones, deliverables at each stage, and dependencies between phases

**SPEAKER NOTES**:

"Alright, you're convinced this is the right approach. How do you actually build it?

Here's an 8-week roadmap. You can compress this if you have resources, but don't skip phases.

[Point to Weeks 1-2] Foundation is critical. Pick ONE workflow to start with. Don't try to boil the ocean.

Map that workflow to domain memory. What are your goals? What progress needs tracking? What procedures exist (even if they're informal)?

Define success criteria. Get specific. 'Complete the analysis' is not a criterion. 'Report includes sections A, B, C with supporting data' is.

[Point to Weeks 3-4] Architecture is where you build the infrastructure.

Implement your four-tier storage. Build the pipeline that transforms storage into working context. Create tools for just-in-time loading.

And add observability from day one. You need to see what's happening.

[Point to Weeks 5-6] Patterns is where you deploy the two-agent approach.

Build your setup agent that creates structured records. Build your worker agent that reads, executes, and updates.

Choose your context strategy—compaction, notes, or sub-agents—based on your task characteristics.

Test with real workflows. Not toy examples—actual work you need done.

[Point to Weeks 7-8] Adaptation is where you close the learning loop.

How do you capture feedback? How do you reflect on successes and failures? How do lessons get incorporated into memory?

Then monitor and iterate. You won't get everything perfect the first time.

[Key advice] Start small, prove value, then expand. Don't try to implement this across your entire organization in week one. Pick one high-value workflow, nail it, then scale."

[Transition]

"Now, as you implement this, there are five laws you need to follow religiously..."

---

## **SLIDE 33: THE FIVE LAWS**

**Title**: Operational Principles for Agent Memory

**1. LAW OF EXPLICIT STATE**
If it's not in structured memory, it doesn't exist for the next agent

**2. LAW OF MINIMUM CONTEXT**
Use smallest token set that achieves the goal

**3. LAW OF STATELESS EXECUTION**
Each agent starts fresh; memory lives in records

**4. LAW OF VALIDATION FIRST**
Never trust completion without verification

**5. LAW OF OBSERVABILITY**
Must be able to inspect, trace, and replay every decision

**Graphic**: Stone tablet or monument with the 5 laws engraved. Or: Five pillars/columns each with a law inscribed, supporting a structure labeled "Reliable Agent Systems"

**SPEAKER NOTES**:

"These are the five laws of agent memory. Violate them at your peril.

[Point to Law 1] Law of Explicit State: If it's not written in structured memory, it doesn't exist.

Don't rely on the agent 'figuring it out' from context. Don't assume it will remember. If it matters, write it down in a structured format.

[Point to Law 2] Law of Minimum Context: Use the smallest set of tokens that achieves your goal.

More is not better. More is worse. Be ruthless about what goes into working context.

[Point to Law 3] Law of Stateless Execution: Each agent starts fresh. Memory lives in the records, not the agent.

Design your system assuming every agent session has zero memory. Because it does.

[Point to Law 4] Law of Validation First: Never trust that something is complete without verification.

Tests. Checks. Validation protocols. No task is done until it's proven done.

[Point to Law 5] Law of Observability: You must be able to inspect, trace, and replay every decision.

If you can't see it, you can't debug it. If you can't debug it, you can't trust it.

[Emphasize this] These aren't guidelines. These aren't suggestions. These are laws.

When your agents fail—and they will fail sometimes—it will be because you violated one of these laws.

When your agents succeed consistently, it will be because you followed them.

[Light humor] I had these made into a poster for my office. They're not the Ten Commandments, but in the world of AI agents, they might as well be."

[Transition]

"Now, as you build this, you need a way to audit your progress. Here are the diagnostic questions..."

---

## **SLIDE 34: DIAGNOSTIC QUESTIONS**

**Title**: How to Audit Your Current System

**Memory Design:**
- Can a new agent pick up where the last left off?
- Do different sessions interpret "done" the same way?
- Can you prevent repeated mistakes without code changes?

**Context Engineering:**
- Does context size stay managed or grow unbounded?
- Can you trace why specific information entered context?
- Would system benefit from smarter model with no code changes?

**Execution Pattern:**
- Does agent do one thing and stop, or wander?
- Can you parallelize work across multiple agents safely?
- Do failures leave clear audit trails?

**Adaptation:**
- Does system learn from successes and failures?
- Are learned patterns reusable across similar situations?
- Can humans inject corrections that persist?

**Graphic**: Scorecard or health check dashboard. Each question with checkbox and traffic light indicator (red/yellow/green) showing system health

**SPEAKER NOTES**:

"Use these questions to audit where you are right now. Be honest—this isn't about feeling good, it's about diagnosing reality.

[Point to Memory Design] First category: Memory Design.

Can a brand new agent instance pick up where the last one left off? Or does it flounder around trying to figure out what happened?

If you give the same task to your agent on Monday and again on Tuesday, do they both interpret 'done' the same way? Or do you get different results?

Can you prevent repeated mistakes just by updating memory, without changing code? Or do you have to modify the agent itself?

[Point to Context Engineering] Second: Context Engineering.

Is your context size managed? Or does it grow unbounded until you hit limits?

Can you trace exactly why a specific piece of information entered context? Or is it a mystery?

Here's a critical one: If you swapped in a more capable model tomorrow, would your system's capabilities increase proportionally? Or is your architecture the bottleneck?

[Point to Execution Pattern] Third: Execution Pattern.

Does your agent do exactly one thing and stop? Or does it wander around doing multiple things, some relevant, some not?

Can you safely run multiple agent instances in parallel on different tasks? Or do they interfere with each other?

When something fails, do you have clear audit trails? Or are failures mysterious black boxes?

[Point to Adaptation] Fourth: Adaptation.

Does your system actually learn? Or does it make the same mistakes repeatedly?

When it learns something, can that lesson apply to similar situations? Or is learning siloed?

When a human corrects something, does that correction persist? Or will the agent make the same error tomorrow?

[Pause]

Go through these questions for your current system. Score yourself honestly. Red, yellow, or green for each category.

Most systems are mostly red. And that's okay—that's why we're here."

[Transition]

"Now let me give you a concrete way to score your current system..."

---

## **SLIDE 35: ASSESSMENT SCORECARD**

**Title**: Rate Your Agent System

**Section A: Domain Memory (Cross-Session)** — Max 13 points

| Question | Yes (3) | Partial (1) | No (0) |
|----------|:-------:|:-----------:|:------:|
| Agent reads structured records at session start? | 3 | 1 | 0 |
| Each task has explicit, testable success criteria? | 3 | 1 | 0 |
| Log of what's been attempted and what failed? | 3 | 1 | 0 |
| Records are machine-readable (not prose)? | 2 | 1 | 0 |
| Agent updates records after each task? | 2 | 1 | 0 |

**Section B: Context Engineering (Within-Session)** — Max 12 points

| Question | Yes (3) | Partial (1) | No (0) |
|----------|:-------:|:-----------:|:------:|
| Context computed fresh each call (not accumulated)? | 3 | 1 | 0 |
| Large results stored externally and referenced? | 3 | 1 | 0 |
| Schema for what survives summarization? | 2 | 1 | 0 |
| Track token counts per step? | 2 | 1 | 0 |
| Cache hit rate monitored? | 2 | 1 | 0 |

**Section C: Control & Reliability** — Max 10 points

| Question | Yes (3) | Partial (1) | No (0) |
|----------|:-------:|:-----------:|:------:|
| Agent can pause for human approval? | 3 | 1 | 0 |
| Retry limit with escalation? | 2 | 1 | 0 |
| Can resume paused agent from saved state? | 2 | 1 | 0 |
| Validation against external criteria (not self-assessment)? | 3 | 1 | 0 |

**Section D: Architecture Health** — Max 8 points

| Question | Yes (3) | Partial (1) | No (0) |
|----------|:-------:|:-----------:|:------:|
| Performance improves with stronger models? | 3 | 1 | 0 |
| Can trace what context produced any decision? | 3 | 1 | 0 |
| Prompts and context tested like code? | 2 | 1 | 0 |

**Score Interpretation:**
| Total Score | Status |
|-------------|--------|
| **35-43** | Production-ready architecture |
| **25-34** | Solid foundation, specific gaps to address |
| **15-24** | Significant work needed; prioritize domain memory |
| **<15** | Demo-stage; systematic redesign recommended |

**Graphic**: Interactive scorecard with sliders or checkboxes for audience to follow along. Score meter at bottom showing the four ranges with labels.

**SPEAKER NOTES**:

"Let me give you a concrete scoring system. This takes those diagnostic questions and turns them into a number.

[Invite participation] I want you to actually score your current system as we go through this. Be honest. This is for your benefit, not for show.

[Point to Section A] Section A: Domain Memory. Maximum 13 points.

Does your agent read structured records at session start? 3 points for yes, 1 for partial, 0 for no.

Does each task have explicit, testable success criteria? Not 'finish the feature'—specific tests. 3 points.

Do you have a log of what's been attempted and failed? Can a new agent see what didn't work? 3 points.

Are your records machine-readable—structured data, not prose? 2 points.

Does the agent update records after each task? Immediately, not batched? 2 points.

Add up your Section A score. Maximum 13.

[Point to Section B] Section B: Context Engineering. Maximum 12 points.

Is context computed fresh each call, not accumulated? 3 points.

Large results stored externally and referenced by path? 3 points.

Do you have a schema for what MUST survive summarization? 2 points.

Are you tracking token counts per step? 2 points.

Monitoring cache hit rate? 2 points.

[Point to Section C] Section C: Control & Reliability. Maximum 10 points.

Can the agent pause for human approval? 3 points.

Retry limit with automatic escalation? 2 points.

Can you resume a paused agent from saved state? 2 points.

Validation against external criteria—tests, not self-assessment? 3 points.

[Point to Section D] Section D: Architecture Health. Maximum 8 points.

If you swap in a stronger model, does performance improve proportionally? Or is your harness the bottleneck? 3 points.

Can you trace exactly what context produced any decision? 3 points.

Are prompts and context assembly tested like code? 2 points.

[Point to Interpretation] Now add up your total. Maximum 43 points.

35 to 43: Production-ready. You've got this figured out.

25 to 34: Solid foundation with specific gaps. You know what to fix.

15 to 24: Significant work needed. Start with domain memory—it's the foundation.

Below 15: Demo-stage. You need systematic redesign, not patches.

[Pause] Most teams I work with score below 20 on their first assessment. That's normal. That's why we're having this conversation."

[Transition]

"Based on your situation, here's how to choose the right architecture..."

---

## **SLIDE 36: DECISION MATRIX**

**Title**: Choose Your Architecture

**Content**:

| Your Situation | Memory Strategy | Context Strategy | Execution Pattern |
|---|---|---|---|
| **Single-session, quick tasks** | Minimal (goals + validation) | Direct loading | Single agent |
| **Multi-turn within session** | Progress log + notes | Compaction | Worker loop |
| **Cross-session work** | Full domain memory | Structured notes | Two-agent pattern |
| **Complex research** | Evidence logs + conclusions | Sub-agent architecture | Coordinator + specialists |
| **Ongoing operations** | Incident timelines + runbooks | Hybrid (preload + JIT) | Worker pool |
| **Learning required** | Failure archive + playbooks | Adaptation (ACE) | Reflector loop |

**Graphic**: Decision tree or flowchart. Start with "What's your task type?" and branch to different architectural recommendations based on characteristics (duration, complexity, learning needed)

**SPEAKER NOTES**:

"Not every task needs the full architecture. Here's how to choose based on your situation.

[Point to row 1] Single-session quick tasks: You're doing something that starts and finishes in one conversation. You don't need elaborate memory. Just clear goals and validation. Direct context loading. Single agent.

[Point to row 2] Multi-turn within a session: The task takes multiple back-and-forths, but finishes in one session. Add progress logging and note-taking. Use compaction to manage context. Worker loop that iterates until done.

[Point to row 3] Cross-session work: This is where you need the full domain memory system. The work spans days or weeks. Full three-pillar memory. Structured notes for persistence. Two-agent pattern with setup and workers.

[Point to row 4] Complex research: You're exploring multiple angles, gathering evidence, synthesizing findings. Evidence logs and conclusions. Sub-agent architecture where specialists investigate in parallel and report back to coordinator.

[Point to row 5] Ongoing operations: You have continuous workflows—incident response, support tickets, monitoring. Incident timelines and runbooks. Hybrid context strategy—preload critical data, JIT for details. Pool of worker agents handling queue.

[Point to row 6] Learning required: Your agent needs to improve over time. Add failure archives and success playbooks. Implement adaptation with reflection loops.

[Point to decision tree] The decision tree makes this concrete. Start with your task characteristics and follow the branches to your recommended architecture.

[Key advice] Start simple. Don't over-engineer for your first deployment. You can always add sophistication as needs grow.

But DO include observability from day one. That's non-negotiable."

[Transition]

"Now let's talk about how you measure success..."

---

## **SLIDE 37: SUCCESS METRICS**

**Title**: Measuring Agent Reliability

**Agent Reliability:**
- Task completion rate without human intervention
- Consistency of "done" interpretation across sessions
- Reduction in repeated failed attempts
- **Target: 80%+ completion rate, <10% repeat failures**

**Context Efficiency:**
- Tokens per successful task completion
- Signal-to-noise ratio in working context
- Time to first relevant output
- **Target: 30%+ reduction in tokens, 2x signal improvement**

**Memory Effectiveness:**
- Progress preserved across session boundaries
- Learnings successfully applied to new situations  
- Reduction in escalations due to missing information
- **Target: Zero session continuity failures, 50%+ fewer escalations**

**System Maintainability:**
- Time to onboard new workflows
- Effort required to debug failures
- Adaptability to changing requirements
- **Target: <1 week for new workflows, <4 hours to debug**

**Graphic**: Dashboard with four metric panels, each showing current vs. target performance with trend lines

**SPEAKER NOTES**:

"You can't improve what you don't measure. Here are the metrics that matter.

[Point to Agent Reliability] First, agent reliability. These are your core operational metrics.

Task completion rate without human intervention. Are agents finishing what you give them? You should be targeting 80% or higher. Below that, something's wrong with your memory or context design.

Consistency of 'done' interpretation. If you give the same task to your agent twice, do you get the same definition of complete? You should get consistency near 100%.

Reduction in repeated failures. Is the agent trying the same thing over and over? You should see repeat failures drop below 10%.

[Point to Context Efficiency] Second, context efficiency. These measure how well you're using your attention budget.

Tokens per successful completion. Are you being efficient? You should see this improve 30% or more as you optimize.

Signal-to-noise ratio. What percentage of your context is actually relevant? Target at least 2x improvement as you refine your pipeline.

Time to first relevant output. How quickly does the agent get to productive work? This should drop significantly with better context design.

[Point to Memory Effectiveness] Third, memory effectiveness. These measure whether your persistence actually works.

Progress preserved across sessions. Do agents pick up where others left off? Target zero continuity failures.

Learnings applied to new situations. When you solve a problem once, does the solution transfer? This should trend upward.

Escalations due to missing information. Are agents calling for help because they don't know what happened before? Target 50% reduction or more.

[Point to System Maintainability] Fourth, maintainability. These measure long-term health.

Time to onboard new workflows. How long to add a new use case? Target under a week.

Effort to debug failures. When something goes wrong, how long to diagnose? Target under four hours.

[Emphasize this] Track these from day one. They tell you whether your implementation is working and where to focus improvement efforts."

[Transition]

"Now, let's talk about where your competitive advantage actually lives..."

---

## **SLIDE 38: THE COMPETITIVE MOAT**

**Title**: Where Your Advantage Actually Lives

**Not Your Moat:**
- ❌ Which model you choose (everyone has access)
- ❌ Context window size (commoditizing rapidly)
- ❌ Prompt engineering tricks (easily copied)
- ❌ Agent frameworks (open source available)

**Your Real Moat:**
- ✓ Domain memory design for your workflows
- ✓ Quality of your goal artifacts and procedures
- ✓ Refinement of your context pipeline
- ✓ Accumulated learnings in your system
- ✓ Speed of iteration and improvement

**Strategic Implication:**
Organizations mastering structured memory design will build agents that finish work while competitors deploy expensive amnesiacs

**Graphic**: Castle/fortress diagram. Outside the walls: commodity capabilities everyone has access to (models, context, prompts). Inside the protected area: unique memory architecture and domain knowledge. Moat surrounding castle labeled "Domain Memory Design"

**SPEAKER NOTES**:

"Let's talk strategy for a moment. Where does your competitive advantage actually live?

[Point to 'Not Your Moat'] Here's what won't differentiate you:

Which model you choose. Everyone has access to the same models. GPT-4, Claude, Gemini—they're available to everyone. This is not your moat.

Context window size. This is commoditizing rapidly. Everyone will have million-token windows soon. Not your moat.

Prompt engineering tricks. These spread fast. What works for one team gets copied by others within weeks. Not your moat.

Agent frameworks. Most are open source. LangGraph, AutoGen—anyone can use them. Not your moat.

[Point to 'Your Real Moat'] So where IS your moat?

Domain memory design for YOUR specific workflows. This is unique to you. No one else has your exact use cases, your exact definition of success, your exact procedures.

Quality of your goal artifacts and operating procedures. This is accumulated knowledge about how work gets done in YOUR organization. That's proprietary.

Refinement of your context pipeline. How you select, filter, compact, and format context—this improves over time with iteration. Your pipeline gets better while competitors are still figuring out basics.

Accumulated learnings in your system. Every success, every failure, every correction—these become part of your system's memory. This compounds over time.

Speed of iteration and improvement. How fast can you identify what's not working and fix it? This velocity is hard to replicate.

[Point to graphic] Think of it like a castle with a moat. 

Outside the walls: commodity capabilities. Everyone has these. They're necessary but not sufficient.

Inside: your unique memory architecture. Your domain knowledge encoded in structure. Your refined processes. Your accumulated learnings.

The moat protecting it all: domain memory design expertise. Competitors can't just buy this. They have to build it.

[Emphasize this] The strategic implication: Organizations that master structured memory design will build agents that actually finish work. Everyone else will keep deploying sophisticated amnesiacs and wondering why their ROI is so poor."

[Transition]

"Speaking of competitors, let's talk about vendor claims..."

---

## **SLIDE 39: VENDOR CLAIM TRIAGE**

**Title**: What to Ask, What to Dismiss

**Immediately Dismiss:**
- "Drop-in universal agents that work out of the box"
- "Our agents maintain state automatically"
- "Longer context windows solve the memory problem"
- "No configuration needed, just start using it"
- "Agents that handle any task you give them"

**Questions to Ask Instead:**
- "How does your platform handle progress tracking across sessions?"
- "What structured memory components do you provide?"
- "How do you prevent context pollution in long-running tasks?"
- "Can I inspect what's in context at any step?"
- "How do you handle learning from failures?"
- "What observability tools do you provide?"
- "Show me domain memory architecture for my use case"

**Graphic**: Two columns with red X's on left (dismiss) and green checkmarks on right (ask). Perhaps detective with magnifying glass examining vendor claims

**SPEAKER NOTES**:

"Alright, real talk about vendors. There's a LOT of marketing happening in this space right now. Here's how to cut through it.

[Point to Dismiss column] If a vendor tells you ANY of these things, be skeptical:

'Drop-in universal agents that work out of the box.' Remember: generalized agents are a fantasy. If it sounds too easy, it doesn't work.

'Our agents maintain state automatically.' No, they don't. Someone designed memory for them, or they're failing in ways you haven't discovered yet.

'Longer context windows solve the memory problem.' We covered this. They don't. They make it worse.

'No configuration needed, just start using it.' Complex problems require configuration. No configuration means no customization means doesn't work for your use case.

'Agents that handle any task.' No. Agents that handle specific, well-defined tasks with proper memory architecture? Yes. Anything else? Marketing.

[Point to Ask column] Here are the questions that separate serious vendors from marketing:

'How does your platform handle progress tracking across sessions?' If they can't give you a specific, technical answer, they haven't solved this.

'What structured memory components do you provide?' If the answer is 'we use RAG,' they're not solving the domain memory problem.

'How do you prevent context pollution?' If they say 'bigger windows,' run away.

'Can I inspect what's in context at any step?' If they say 'you don't need to,' they don't have observability.

'How do you handle learning from failures?' If they say 'the model learns,' they don't have a learning loop.

'What observability tools do you provide?' If they can't show you dashboards and traces, you can't debug their system.

And the killer question: 'Show me the domain memory architecture for MY specific use case.' If they can't map your workflow to their memory design, they're selling generic tools.

[Light humor] Look, I'm not here to bash vendors. Many are doing good work. But this space is full of hype right now, and you need to be able to separate substance from marketing.

The vendors who can answer these questions? Talk to them. The ones who can't? Save your budget."

[Transition]

"This also has implications for how you structure your teams..."

---

## **SLIDE 40: TEAM IMPLICATIONS**

**Title**: Organizing for Success

**Required Capabilities:**

**Domain Experts** (Critical Role)
- Define what "done" means in your context
- Specify validation procedures that actually matter
- Identify failure patterns from experience
- Design goal artifacts and operating procedures

**AI Engineers** (Implementation)
- Implement memory systems and storage architecture
- Build context pipelines and transformations
- Create observability and debugging tools
- Optimize token efficiency

**DevOps/Platform** (Infrastructure)
- Deploy persistent storage systems
- Monitor performance and reliability
- Ensure availability and scalability
- Manage secrets and access control

**Product Owners** (Coordination)
- Prioritize workflows for agent implementation
- Measure ROI and business impact
- Manage stakeholder expectations
- Drive continuous improvement

**Cross-functional collaboration is mandatory**
Domain knowledge must translate into agent-readable structure

**Graphic**: Venn diagram with four overlapping circles (Domain Experts, AI Engineers, DevOps, Product). In center overlap: "Effective Agent Systems". Around diagram, show specific contributions from each group

**SPEAKER NOTES**:

"You can't implement this with just engineers. This requires cross-functional teams. Let me explain the roles.

[Point to Domain Experts] Domain Experts are actually THE most critical role, and organizations often undervalue this.

These are the people who know how work actually gets done. They define what 'done' means. They know which validation procedures actually matter versus which are theater.

They've seen the failure patterns. They know what goes wrong and why.

Without domain experts, your AI engineers will build beautiful architectures that don't actually solve your problems. The memory will be technically correct but domain-wrong.

[Point to AI Engineers] AI Engineers do the implementation.

They build the memory systems, the storage tiers, the context pipelines. They create the observability tools. They optimize for token efficiency.

But they can't do this in a vacuum. They need domain experts to tell them WHAT to build.

[Point to DevOps] DevOps handles infrastructure.

Someone has to actually run these systems. Deploy the storage. Monitor performance. Ensure reliability. Manage secrets and access control.

Agent systems have operational requirements just like any other production system.

[Point to Product Owners] Product Owners coordinate everything.

Which workflows should we tackle first? What's the ROI? Are stakeholders' expectations realistic? How do we measure success? How do we continuously improve?

[Point to center] All four need to collaborate. Here's why:

Domain expert says: 'For this task to be complete, we need X, Y, and Z validated.'

AI engineer asks: 'How do I make that machine-readable?'

DevOps asks: 'What storage and performance requirements does that create?'

Product owner asks: 'What business impact does that deliver?'

That conversation is where effective agent systems get built.

[Key advice] Don't silo this as 'an AI project.' Treat it as an organizational capability that requires multiple functions working together."

[Transition]

"Now let me address some objections I hear frequently..."

---

## **SLIDE 41: ADDRESSING COMMON OBJECTIONS**

**Title**: "But Our Situation Is Different..."

**Objection 1: "This seems too complex for our needs"**
Response: The complexity is necessary because the problem is hard. Simple approaches fail for a reason. Start small, but don't oversimplify.

**Objection 2: "Our current agents work fine"**
Response: Do they? Can they handle multi-session tasks? Do they finish work consistently? Do they learn from mistakes? Or are you just using them for simple one-shot queries?

**Objection 3: "We don't have time to build all this infrastructure"**
Response: You don't have time NOT to. Every day you run unreliable agents, you're paying for failures, repeated work, and human intervention.

**Objection 4: "Can't we just wait for better models?"**
Response: Better models don't solve memory problems. GPT-5 will be smarter but still have no memory. You'll have the same issues, just faster.

**Objection 5: "Our vendor says their agents handle this automatically"**
Response: Ask them HOW. Ask for architecture diagrams. Ask to see the domain memory design. If they can't show you, it's marketing.

**Graphic**: FAQ-style layout with objection on left, response on right. Maybe lightbulb icons for key insights

**SPEAKER NOTES**:

"Let me address the objections I hear most frequently. Maybe you're thinking some of these right now.

[Point to Objection 1] 'This seems too complex for our needs.'

I get it. It looks like a lot. But here's the thing: the complexity is necessary because the problem is genuinely hard.

Simple approaches fail. That's why your current agents aren't working consistently. You can start small—pick one workflow, implement the basics—but don't oversimplify the architecture. The three pillars exist for a reason.

[Point to Objection 2] 'Our current agents work fine.'

Really? Let me ask some diagnostic questions:

Can they handle tasks that span multiple sessions? Do they finish work consistently without human intervention? Do they learn from mistakes? Can different agent sessions interpret 'done' the same way?

Or are you just using them for simple one-shot queries—summarization, simple analysis, single-turn responses? Because that's not what we're talking about here.

[Point to Objection 3] 'We don't have time to build all this infrastructure.'

You don't have time NOT to. Let's do the math:

Every day you run unreliable agents, you're paying for: repeated failed attempts, human intervention and cleanup, work that never actually finishes, and frustrated teams who lose trust in AI.

Eight weeks to build proper infrastructure versus months of ongoing failures and waste. Which costs more?

[Point to Objection 4] 'Can't we just wait for better models?'

No. Better models don't solve memory architecture problems.

GPT-5 will be smarter than GPT-4. It will reason better, write better code, analyze better. But it will still have ZERO memory between sessions.

You'll have the same memory problem, just with a more capable amnesiac.

[Point to Objection 5] 'Our vendor says their agents handle this automatically.'

Great! Ask them HOW. Ask for architecture diagrams. Ask to see the domain memory design for your specific workflow.

If they can show you the three pillars, the context architecture, the observability—fantastic, evaluate it.

If they can't, or they say 'you don't need to worry about that,' it's marketing, not engineering.

[Pause]

Look, I'm not saying this is easy. It's not. But it's necessary. And it's the difference between agents that actually work and agents that look good in demos."

[Transition]

"Let me show you what failure looks like versus what success looks like..."

---

## **SLIDE 42: FAILURE PATTERNS VS. SUCCESS PATTERNS**

**Title**: What Failure and Success Look Like

**FAILURE PATTERNS:**

**The Wandering Agent**
- Starts task A, gets distracted, works on task B
- Declares victory when nothing is complete
- Tries same approach repeatedly without learning
- No clear stopping point

**The Amnesiac Loop**  
- Monday: Tries approach A, fails
- Tuesday: Tries approach A again (forgot it failed)
- Wednesday: Tries approach A again
- Never makes progress

**The Context Polluter**
- Loads everything "just in case"
- Buries signal in noise
- Makes poor decisions based on irrelevant info
- Performance degrades over time

**SUCCESS PATTERNS:**

**The Focused Executor**
- Reads state, picks ONE task
- Works on it until complete or blocked
- Validates completion, updates records, stops
- Next session continues seamlessly

**The Learning System**
- Captures outcomes of attempts
- Builds structured lessons
- Applies learnings to new situations
- Gets better over time

**The Efficient Operator**
- Loads minimal context
- Retrieves additional info just-in-time
- Maintains high signal-to-noise
- Fast and accurate

**Graphic**: Two columns showing contrasting scenarios. Left side (failure) shows chaotic, circular patterns. Right side (success) shows linear, progressive patterns

**SPEAKER NOTES**:

"Let me make this concrete by showing you what failure looks like versus success.

[Point to Failure Patterns] First, common failure patterns:

The Wandering Agent: You give it task A. It starts working, gets distracted, switches to task B. Then notices task C needs doing too. Eventually declares everything complete when nothing actually is.

Why? No explicit goals. No focus on one thing. No validation before moving on.

The Amnesiac Loop: This is brutal to watch. [Tell story with emotion]

Monday, the agent tries approach A. It fails. Tuesday, new session, tries approach A again—totally forgot it failed Monday. Wednesday, AGAIN approach A.

I watched this happen for THREE WEEKS on a real project. The agent never made progress because it had no memory of what didn't work.

The Context Polluter: Agent loads everything that might possibly be relevant. Complete conversation history, all files that might matter, every tool output ever generated.

Result? Signal drowns in noise. The agent makes poor decisions because it's distracted by irrelevant information. Performance degrades over time.

[Point to Success Patterns] Now contrast with success patterns:

The Focused Executor: Reads current state from domain memory. Picks exactly ONE incomplete task. Works on it until complete or blocked. Validates completion against criteria. Updates records. Stops.

Next session starts fresh, but immediately knows where things stand and continues seamlessly.

The Learning System: When it tries something, it captures the outcome. Success? Log what worked. Failure? Log what didn't and why.

These outcomes become structured lessons. When similar situations arise, apply the learning. The system gets better over time.

The Efficient Operator: Loads only what's needed right now. When it needs more information, retrieves it just-in-time. Context stays clean and focused. High signal-to-noise ratio. Fast and accurate decisions.

[Pause]

The difference between these patterns? Memory architecture and context engineering. That's it. Same models, same capabilities. Different outcomes."

[Transition]

"Now, let's talk about the economics of this..."

---

## **SLIDE 43: THE ECONOMIC ARGUMENT**

**Title**: ROI of Proper Memory Architecture

**Current State (Typical Broken Agent):**
- 30% task completion rate without intervention
- 3-5x repeated failed attempts per task
- 40% of agent time wasted on already-tried approaches
- Average 4 hours human time per complex task for intervention
- Zero learning between sessions
- **Estimated cost per completed task: $200-500**

**With Proper Memory Architecture:**
- 80%+ task completion rate without intervention
- <10% repeated failures
- 90%+ of agent time productive
- Average <1 hour human time per complex task
- Continuous learning and improvement
- **Estimated cost per completed task: $50-100**

**Payback Period:**
- Implementation: 8 weeks, ~$100K investment
- Savings: $150-400 per task × 100 tasks/month = $15K-40K/month
- **Payback in 3-7 months, then ongoing savings**

**Plus intangible benefits:**
- Faster time-to-market
- Higher quality outputs
- Team trust in AI
- Competitive advantage

**Graphic**: Cost comparison bar chart showing current vs. optimized costs, plus ROI timeline showing crossover point where savings exceed investment

**SPEAKER NOTES**:

"Let's talk money, because this needs to make business sense.

[Point to Current State] Here's what most organizations are experiencing with broken agent systems:

30% task completion rate without human intervention. That means 70% of the time, someone has to step in.

3-5x repeated failures per task. The agent tries the same thing multiple times before either succeeding or giving up.

40% of agent time wasted on approaches that have already been tried and failed. No learning means repeated mistakes.

Average 4 hours of human time per complex task for intervention, cleanup, and correction.

Zero learning between sessions. Every mistake gets made over and over.

When you add up the agent compute costs plus human intervention costs, you're paying $200-500 per completed task. And that's being generous.

[Point to With Proper Memory] Now with proper memory architecture:

80%+ completion rate without intervention. Most tasks finish correctly the first time.

Under 10% repeated failures. The system learns what doesn't work.

Over 90% of agent time is productive. No thrashing, no wandering, no repeated mistakes.

Average under 1 hour of human time for complex tasks. Usually just final review.

Continuous learning. Mistakes made once become lessons for future tasks.

Cost per completed task drops to $50-100.

[Point to Payback Period] What's the ROI?

Implementation takes about 8 weeks with proper resourcing. Investment around $100K (team time, infrastructure, iteration).

But you're saving $150-400 per task. If you're running 100 tasks per month—which is modest for most organizations—that's $15K-40K in monthly savings.

Payback in 3-7 months. Then ongoing savings.

[Point to intangible benefits] Plus intangibles:

Faster time-to-market because agents actually finish work.

Higher quality outputs because validation is built in.

Team trust in AI increases when systems actually work.

And competitive advantage—you're deploying agents that work while competitors deploy expensive amnesiacs.

[Emphasize] This isn't an expense. It's an investment with clear payback and ongoing returns."

[Transition]

"Alright, we've covered a lot. Let me bring this all together with one key insight..."

---

## **SLIDE 44: THE CORE INSIGHT REVISITED**

**Title**: One Idea to Remember

**The Problem:**
Agents are stateless amnesiacs that forget everything between sessions

**The Wrong Solution:**
Try to give agents memory through bigger context windows or smarter models

**The Right Solution:**
Build systems where amnesiacs can work effectively through structured external memory

**The Pattern:**
1. Setup Agent creates structured records (goals, procedures, validation)
2. Worker Agents read state, execute one task, update records, stop
3. Domain Memory persists between sessions
4. Context Engineering keeps attention focused
5. Observability enables debugging and trust
6. Adaptation enables continuous improvement

**Your competitive advantage is designing the best memory architecture for your domain, not choosing the best model**

**Graphic**: Powerful central image showing agent successfully completing tasks by reading from structured dashboard, with clear checkmarks appearing. Contrast with faded background of confused agent without structure.

**SPEAKER NOTES**:

"We've covered a lot of ground. Let me bring it all back to one central insight.

[Point to The Problem] The problem: Agents are stateless amnesiacs. They forget everything between sessions. This is not a bug to be fixed—it's a fundamental characteristic of how these systems work.

[Point to Wrong Solution] The wrong solution—and this is what most organizations are trying—is to fight this reality. 

'We'll use bigger context windows!' No, that makes reasoning worse.
'We'll use smarter models!' No, smarter amnesiacs are still amnesiacs.
'We'll prompt it to remember!' No, that doesn't actually work.

[Point to Right Solution] The right solution is to ACCEPT that agents are amnesiacs and build systems where amnesiacs can work effectively.

You do this through structured external memory. Not memory IN the agent. Memory the agent READS.

[Point to The Pattern] And the pattern is clear:

Setup Agent translates human requests into structured records. Goals with testable criteria. Progress tracking structures. Operating procedures.

Worker Agents—stateless, fresh every time—read current state, pick one task, work on it, validate it, update records, stop.

Domain Memory persists between sessions. It's the constant. It's where coherence lives.

Context Engineering keeps the agent focused on high-signal information. No wandering in irrelevant context.

Observability enables debugging. You can see what the agent saw at any decision point.

Adaptation enables learning. The system gets better over time.

[Emphasize this] And here's the strategic insight: Your competitive advantage is NOT in choosing the best model. Everyone has access to the same models.

Your advantage is in designing the best memory architecture for YOUR specific workflows. That's unique. That's hard to replicate. That's your moat.

[Pause]

Master this pattern, and you'll build agents that actually finish work. Ignore it, and you'll keep deploying sophisticated amnesiacs that look impressive in demos but fail in production."

[Transition]

"So what should you do next? Here are your concrete next steps..."

---

## **SLIDE 45: YOUR NEXT STEPS**

**Title**: What to Do Monday Morning

**Immediate Actions (This Week):**

1. **Audit one current agent deployment**
   - Run through the diagnostic questions
   - Document where it's failing and why
   - Identify if it's a memory or context problem

2. **Map one workflow to domain memory**
   - Choose your highest-value use case
   - Define explicit goals with testable criteria
   - Design progress tracking structure
   - Document operating procedures

3. **Assess your team capabilities**
   - Do you have domain experts who can define success criteria?
   - Do you have AI engineers who can implement architecture?
   - Do you have DevOps who can run infrastructure?
   - Identify gaps and plan to fill them

**Next 30 Days:**

4. **Build a minimal viable implementation**
   - Implement basic domain memory for one workflow
   - Deploy two-agent pattern (setup + worker)
   - Add basic observability
   - Test with real work

5. **Measure baseline metrics**
   - Completion rate, repeated failures, context efficiency
   - Document current costs per task
   - Establish what success looks like

**Next 90 Days:**

6. **Iterate and expand**
   - Refine based on learnings
   - Add context engineering optimizations
   - Implement adaptation loop
   - Scale to additional workflows

**Graphic**: Timeline showing Week 1, Week 4, and Week 12 milestones with specific deliverables at each point. Checklist format with actionable items.

**SPEAKER NOTES**:

"Alright, you're convinced. What should you actually DO? Here's your action plan.

[Point to Immediate Actions] This week—like, starting Monday morning:

First, audit one current agent deployment. Take one agent you have running—or one you tried to deploy—and run it through our diagnostic questions.

Where is it failing? Why? Is it a memory problem? Context problem? Both?

Document this honestly. You can't fix what you can't see.

Second, map one workflow to domain memory. Don't try to boil the ocean. Pick ONE high-value use case.

Define explicit goals with testable criteria. Design progress tracking. Document procedures.

This is work, but it's necessary work. If you can't define success criteria for humans, you can't define them for agents.

Third, assess your team. Do you have the right capabilities?

Domain experts to define what 'done' means?
AI engineers to build the systems?
DevOps to run the infrastructure?

Identify gaps now, plan to fill them.

[Point to Next 30 Days] In the next month:

Fourth, build a minimal viable implementation. Not the full sophisticated architecture—the basics.

Basic domain memory. Two-agent pattern. Basic observability. That's it for version one.

Test it with real work. Not toy examples. Actual tasks that matter to your business.

Fifth, measure baseline metrics. How many tasks complete? How many failures repeat? What's your cost per task?

You need a baseline to know if you're improving.

[Point to Next 90 Days] In the next quarter:

Sixth, iterate and expand. You'll learn a ton from your first implementation. Feed that learning back.

Refine your memory design. Add context engineering optimizations. Implement the adaptation loop.

Then scale to additional workflows.

[Pause]

The key is: START. Don't wait for perfect. Don't wait for more resources. Don't wait for better models.

Pick one workflow. Implement the basics. Learn. Iterate.

That's how you actually make progress."

[Transition]

"Let me leave you with some resources to help you implement this..."

---

## **SLIDE 46: RESOURCES AND REFERENCES**

**Title**: Where to Learn More

**Academic Research:**
- "Lost in the Middle" - How models lose track in long contexts
- Chroma Research - Performance degradation with input length
- Anthropic Context Engineering Guide - Official best practices

**Implementation Frameworks:**
- Google ADK (Agent Development Kit) - Open source, context-native
- Anthropic SDK - Memory and context tools
- LangGraph - State management for agents

**Case Studies:**
- Claude Code - Software development with memory
- Research agents with evidence logs
- Operations agents with runbooks

**Design Prompts (Use with AI to Design Your Architecture):**
1. **State Persistence Analysis** - "What must persist across agent calls?"
2. **View Compilation Design** - "How should context be computed for each call?"
3. **Retrieval Trigger Design** - "When and how should context be retrieved?"
4. **Attention Budget Allocation** - "What's consuming tokens? What earns its cost?"
5. **Summarization Schema Design** - "What MUST survive summarization?"
6. **External Memory Architecture** - "What goes in filesystem vs. vector store vs. artifacts?"
7. **Multi-Agent Scope Design** - "What work requires separate context windows?"
8. **Cache Stability Optimization** - "How do we get 70%+ cache hit rate?"
9. **Failure Reflection System** - "How do mistakes get captured and integrated?"
10. **Architecture Ceiling Test** - "Does performance improve with stronger models?"
11. **Context Observability Audit** - "Can we trace what the agent sees and why?"
12. **Success Criteria Definition** - "What does testable success look like?"

**Our Templates:**
- Domain Memory Designer (any workflow)
- Research Workflow Memory
- Operations Agent Memory
- Content Production Memory
- Agent Workflow Audit

**Community:**
- [Your organization's internal Slack/Teams channel]
- Office hours: [Schedule]
- Technical deep-dives: [Schedule]

**Graphic**: Resource library visualization showing categories (Research, Tools, Case Studies, Design Prompts, Templates) with icons and links. Highlight the 12 design prompts as interactive tools.

**SPEAKER NOTES**:

"I know I've thrown a lot at you. Here are resources to help you implement this.

[Point to Academic Research] Start with the research. These papers establish WHY this matters:

'Lost in the Middle' explains the attention problem.
Chroma Research shows performance degradation.
Anthropic's official guide covers context engineering best practices.
ACE research from Stanford/SambaNova shows how context can evolve—10% improvement on benchmarks with their approach.

Read these. They'll give you confidence that this isn't just theory—it's grounded in solid research.

[Point to Implementation Frameworks] For actually building this, these frameworks help:

Google ADK is open source and designed around context as a compiled view. If you're building from scratch, start here.

Anthropic SDK has memory and context tools built in. If you're using Claude, leverage these.

LangGraph handles state management. Useful for certain workflow patterns.

[Point to Case Studies] Learn from examples:

Claude Code shows how this works for software development—hybrid retrieval, progressive disclosure, skills as filesystem.

Manus shows how to handle 50+ tool calls—reduce, offload, isolate.

Study these. Don't reinvent wheels.

[Point to Design Prompts] This is the most practical resource: 12 design prompts you can use with an AI assistant to design YOUR specific architecture.

Each prompt guides you through designing one aspect of your agent system. State persistence. View compilation. Retrieval triggers. Summarization schema. And so on.

Use these with Claude or GPT to work through YOUR specific use case. They'll ask you the right questions and help you make design decisions.

[Point to Templates] We've also created templates for common workflows:

Domain Memory Designer for any workflow.
Specific templates for research, operations, and content production.
An audit prompt to diagnose your current systems.

[Point to Community] And finally, community resources:

[Adjust to your context] We're setting up internal channels for this. Office hours where you can ask questions. Technical deep-dives on specific patterns.

You're not doing this alone. We're building organizational capability together.

[Pause]

Download these resources. Read the papers. Try the frameworks. Use the prompts.

But most importantly: start implementing. That's where real learning happens."

[Transition]

"Let me close with some final thoughts..."

---

## **SLIDE 47: FINAL THOUGHTS**

**Title**: The Path Forward

**What We've Learned:**

The 750% surge in AI agent interest is real, but most deployments fail because they ignore fundamental memory constraints.

Agents are amnesiacs. Trying to fight this with bigger context windows or smarter models doesn't work—it makes things worse.

The solution is structured external memory: explicit goals, progress records, and operating procedures. Memory lives in records, not agents.

The two-agent pattern (setup + worker) acknowledges amnesiac nature and works with it, not against it.

Context engineering treats attention as finite resource requiring ruthless curation.

Your competitive moat is memory architecture design, not model selection.

**What This Means:**

Over the next 18 months, the market will bifurcate:
- Organizations building proper memory architecture will have agents that actually finish work
- Organizations deploying generalized agents will keep writing checks for sophisticated amnesiacs

**The choice is yours.**

**This is not about AI capabilities. It's about system design.**

**And system design is something you can master.**

**Graphic**: Simple powerful image of two diverging paths. One path leads to "Agents That Work" (structured, organized). Other path leads to "Expensive Amnesiacs" (chaotic, scattered). Fork in road is labeled "Your Decision: Next 90 Days"

**SPEAKER NOTES**:

"Let me bring this home.

[Recap with energy] We started with a problem: 750% surge in AI agent interest, but most deployments are failing. Organizations keep asking 'why do our agents fail on multi-session tasks?'

The answer isn't about model intelligence. It's about memory architecture.

Agents are amnesiacs. Every session starts with zero memory. That's not a bug—it's how these systems work.

The wrong solution is fighting this with bigger context windows or smarter models. The research shows this makes things worse.

The right solution is structured external memory. Three pillars: explicit goals, progress records, operating procedures.

The two-agent pattern—setup and workers—works WITH the amnesiac constraint, not against it.

Context engineering treats attention as finite and valuable. Ruthless curation. Just-in-time loading. Progressive disclosure.

And your competitive moat? It's not about having access to GPT-5 or Claude Opus. Everyone will have that. It's about designing the best memory architecture for YOUR workflows.

[Point to What This Means] Here's what I believe will happen over the next 18 months:

The market is going to bifurcate. Split into two camps.

One camp will master proper memory architecture. Their agents will actually finish work. They'll see real ROI. They'll build competitive advantages.

The other camp will keep deploying generalized agents, wondering why things don't work, throwing money at the problem, getting frustrated.

[Pause and let that land]

Which camp will you be in?

[Emphatic] This is not about AI capabilities. The capabilities are there. This is about system design. About architecture. About thinking clearly about constraints and working with them.

And system design is something you can master.

[Point to graphic] You're at a fork in the road right now. The next 90 days will determine which path you take.

Down one path: agents that actually work. Structured. Reliable. Improving over time.

Down the other path: expensive amnesiacs that look great in demos but fail in production.

[Final emphasis] The choice is yours. The knowledge is here. The frameworks exist. The pattern is clear.

What you do with it—that's up to you.

Thank you."

[Pause for questions]

---

## **SLIDE 48: Q&A**

**Title**: Questions & Discussion

**Common Questions We Often Address:**
- "What's the minimum viable implementation?"
- "How do we choose which workflow to start with?"
- "What if our use case doesn't fit these patterns?"
- "How do we convince leadership to invest in this?"
- "What are the biggest failure modes to avoid?"
- "Can we integrate this with our existing agent framework?"
- "How long before we see ROI?"
- "What skills do we need to hire for?"

**[Open discussion]**

**Contact Information:**
[Your name, email, calendar link]
[Link to resources repository]
[Link to implementation templates]

**Graphic**: Simple graphic encouraging questions, perhaps with thought bubbles or question marks. Keep focus on discussion

**SPEAKER NOTES**:

"Alright, that was a lot. Let's open this up.

[Gesture openly] I've got time for questions. And I promise: there are no stupid questions here. This is complex stuff.

[If silence] Let me share some questions I often get:

'What's the minimum viable implementation?' - Great question. Start with basic three-pillar memory for one workflow. Two-agent pattern. Basic observability. That's your MVP.

'How do we choose which workflow to start with?' - Pick something high-value but not mission-critical. You want meaningful impact but room to learn.

'What if our use case doesn't fit these patterns?' - I haven't found one that doesn't, but I'm curious. Tell me about your use case.

'How do we convince leadership?' - Show them the economics slide. $200-500 per task now, $50-100 with proper architecture. That usually does it.

'What are the biggest failure modes to avoid?' - Three big ones: skipping observability, oversimplifying goals, trying to implement everything at once.

'Can we integrate with existing agent frameworks?' - Yes. These patterns work on top of LangGraph, AutoGen, whatever you're using. You're adding memory architecture, not replacing infrastructure.

'How long before we see ROI?' - Usually 3-7 months payback, then ongoing savings. But you'll see improvement in reliability within weeks.

'What skills do we need?' - Domain experts who can define success, AI engineers who can implement architecture, DevOps who can run infrastructure. Cross-functional team.

[Open to room] What questions do you have?

[Handle Q&A naturally, refer back to specific slides when relevant]

[When wrapping] 

Great questions, thank you. Listen, I know this is a lot to absorb. That's normal. Here's what I'd recommend:

[Point to contact info] Reach out. Seriously. We can talk through your specific situation. I've included calendar link, email, and links to all the resources and templates.

You're not doing this alone. We're building this capability together.

Thank you for your time. Now go build agents that actually work."

---

**END OF PRESENTATION**

---

## **SUPPLEMENTAL NOTES FOR PRESENTER:**

**Timing Guide:**
- Average 60-75 minutes for full presentation
- Can be compressed to 45 minutes by reducing examples
- Can be expanded to 90 minutes with deeper Q&A

**Audience Adaptation:**
- **Technical audience**: Emphasize architecture diagrams, add code examples
- **Executive audience**: Emphasize economics and competitive advantage
- **Mixed audience**: Balance technical depth with business impact (as written)

**Energy Management:**
- High energy for problem statement (slides 1-6)
- Thoughtful, explanatory for core concepts (slides 7-24)
- Practical, actionable for implementation (slides 25-35)
- Strategic, forward-looking for implications (slides 36-44)
- Concrete, helpful for next steps (slides 45-48)

**Key Moments to Emphasize:**
- Slide 6: The Micro-Agent Pattern (what's working in production)
- Slide 7: The fundamental insight (memory lives in structure)
- Slide 14: The daily contractor analogy (makes pattern click)
- Slide 25: The observability requirement (production readiness)
- Slide 30: Case Study - Manus (real-world validation)
- Slide 38: The competitive moat (strategic importance)
- Slide 44: The core insight revisited (bringing it all together)

**Interactive Elements:**
- Slide 2: Show of hands (who's deploying agents)
- Slide 35: Encourage audience to score their current systems (Assessment Scorecard)
- Throughout: Pause for "Does this resonate?" moments

**Common Audience Reactions to Prepare For:**
- "We already do this" → Ask diagnostic questions to verify
- "This won't work for us" → Ask about their specific use case
- "Our vendor says..." → Guide through vendor triage questions
- "This seems like too much" → Emphasize start small, iterate