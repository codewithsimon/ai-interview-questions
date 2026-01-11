# Agentic AI Developer Interview Questions


## 1. What is an agent in the context of LLM-based systems?

### What the interviewer is evaluating
Whether you understand agents as **systems**, not just prompts or tools.

### What you should learn
- Definition of agents  
- Perception, decision-making, action loops  
- Difference between agents and chatbots  

### How to answer
- Start with a definition  
- Emphasize autonomy, state, and goal-directed behavior  

### Sample Answer
An agent is a system that can perceive its environment, reason about a goal, and take actions using tools or APIs over multiple steps. Unlike a simple chatbot, an agent maintains state, can plan ahead, and iteratively decide what to do next based on feedback from its actions.

---

## 2. How does an agent differ from a traditional LLM application?

### What the interviewer is evaluating
Your ability to distinguish static inference from dynamic decision-making.

### What you should learn
- Single-shot vs multi-step reasoning  
- Control flow around LLMs  

### How to answer
- Contrast execution models  
- Mention autonomy and feedback loops  

### Sample Answer
A traditional LLM application typically follows a fixed input-output flow. An agent introduces a control loop where the model decides what action to take next, evaluates results, and adapts its behavior. This allows agents to solve multi-step tasks that cannot be predefined.

---

## 3. What is the ReAct pattern and why is it useful?

### What the interviewer is evaluating
Your familiarity with foundational agent patterns.

### What you should learn
- ReAct (Reason + Act)  
- Thought-action-observation loops  

### How to answer
- Explain the loop  
- Explain why it improves reliability  

### Sample Answer
ReAct combines reasoning steps with actions. The model reasons about what to do, executes an action like calling a tool, observes the result, and continues. This structure helps reduce hallucinations and makes decision-making more transparent and debuggable.

---

## 4. How do you prevent agents from hallucinating tool usage?

### What the interviewer is evaluating
Practical production awareness.

### What you should learn
- Tool schemas  
- Validation layers  
- Retry and fallback strategies  

### How to answer
- Talk about constraints and verification  

### Sample Answer
I constrain tool usage through strict schemas, validate inputs before execution, and verify outputs after execution. I also add guardrails such as confidence checks and retries, and in critical paths, require deterministic rules or human confirmation.

---

## 5. What are common failure modes in agentic systems?

### What the interviewer is evaluating
Whether you think in terms of system failures.

### What you should learn
- Infinite loops  
- Tool misuse  
- Compounding errors  

### How to answer
- Name multiple failure types  
- Show mitigation thinking  

### Sample Answer
Common failures include infinite reasoning loops, incorrect tool selection, error propagation across steps, and loss of task context. I mitigate these with step limits, explicit termination conditions, structured memory, and evaluation checkpoints.

---

## 6. How do you design memory for an agent?

### What the interviewer is evaluating
Understanding of short-term vs long-term memory.

### What you should learn
- Context windows  
- Vector stores  
- Episodic vs semantic memory  

### How to answer
- Break memory into categories  

### Sample Answer
I separate memory into short-term working memory within the prompt, long-term memory stored in vector databases, and task-specific state. Only relevant information is retrieved to avoid context overload and reduce noise.

---

## 7. When should you not use an agent?

### What the interviewer is evaluating
Judgment and restraint.

### What you should learn
- Overengineering risks  
- Deterministic workflows  

### How to answer
- Emphasize cost and reliability  

### Sample Answer
Agents are unnecessary when the task is deterministic, low-variance, or safety-critical. In those cases, a rule-based workflow or single LLM call is cheaper, faster, and more reliable.

---

## 8. How do you evaluate an agent’s performance?

### What the interviewer is evaluating
Evaluation maturity beyond accuracy.

### What you should learn
- Task success rates  
- Trajectory evaluation  
- Human-in-the-loop evaluations  

### How to answer
- Mention multiple metrics  

### Sample Answer
I evaluate agents using task completion rate, number of steps taken, tool accuracy, cost, and failure recovery behavior. For complex tasks, I also use human review and regression testing on recorded trajectories.

---

## 9. What is tool calling and how does it work?

### What the interviewer is evaluating
API-level understanding.

### What you should learn
- Function calling  
- JSON schemas  

### How to answer
- Explain model-tool interface  

### Sample Answer
Tool calling allows an LLM to output structured arguments that match a predefined schema. The system executes the tool externally and feeds the result back to the model, enabling reliable interaction with real systems.

---

## 10. How do you prevent infinite loops in agents?

### What the interviewer is evaluating
Operational safety awareness.

### What you should learn
- Step limits  
- State tracking  

### How to answer
- Mention hard and soft stops  

### Sample Answer
I enforce maximum step counts, track repeated states or actions, and include explicit termination conditions. If progress stalls, the agent escalates or exits gracefully.

---

## 11. What is the difference between planning-first and reactive agents?

### What the interviewer is evaluating
Architectural understanding.

### What you should learn
- Plan-and-execute models  
- Reactive control loops  

### How to answer
- Compare tradeoffs  

### Sample Answer
Planning-first agents create a full plan before acting, which improves coherence but reduces flexibility. Reactive agents decide step-by-step, adapting better to uncertainty but sometimes losing global structure.

---

## 12. How do multi-agent systems work?

### What the interviewer is evaluating
Scalability thinking.

### What you should learn
- Role specialization  
- Coordination patterns  

### How to answer
- Focus on communication and control  

### Sample Answer
Multi-agent systems assign specialized roles to agents that communicate via shared memory or message passing. Coordination is managed through protocols, supervisors, or voting mechanisms to avoid conflict.

---

## 13. How do you secure agent tool access?

### What the interviewer is evaluating
Security awareness.

### What you should learn
- Least privilege  
- Tool sandboxing  

### How to answer
- Talk about permissions  

### Sample Answer
I restrict agents to least-privilege tool access, sandbox execution, validate all inputs, and log actions. Sensitive tools require approval or human confirmation.

---

## 14. How do you handle cost control in agentic systems?

### What the interviewer is evaluating
Production readiness.

### What you should learn
- Token budgeting  
- Caching  
- Model selection  

### How to answer
- Show tradeoff thinking  

### Sample Answer
I control cost by limiting steps, using smaller models for routine reasoning, caching results, and only escalating to larger models when necessary.

---

## 15. What role does prompt design play in agents?

### What the interviewer is evaluating
Foundational skill depth.

### What you should learn
- System prompts  
- Instruction hierarchies  

### How to answer
- Emphasize structure  

### Sample Answer
Prompt design defines agent behavior, constraints, and priorities. A well-structured system prompt reduces ambiguity, improves tool usage, and stabilizes long-term behavior.

---

## 16. How do you debug an agent?

### What the interviewer is evaluating
Real-world problem-solving skills.

### What you should learn
- Tracing  
- Logging  
- Replay systems  

### How to answer
- Explain observability  

### Sample Answer
I log each reasoning step, tool call, and observation. I replay failed trajectories to identify where reasoning broke down and adjust prompts, tools, or constraints accordingly.

---

## 17. What is reflection in agents?

### What the interviewer is evaluating
Awareness of advanced techniques.

### What you should learn
- Self-critique loops  
- Meta-reasoning  

### How to answer
- Explain benefits and risks  

### Sample Answer
Reflection allows agents to review their own actions and improve. While it can increase performance, it must be bounded to avoid excessive cost or looping.

---

## 18. How do you ensure reliability under uncertainty?

### What the interviewer is evaluating
Robustness mindset.

### What you should learn
- Fallback strategies  
- Confidence estimation  

### How to answer
- Mention redundancy  

### Sample Answer
I design fallback paths, validate assumptions, and require confirmation for uncertain actions. When confidence is low, the agent escalates instead of guessing.

---

## 19. How do agents interact with humans in the loop?

### What the interviewer is evaluating
Human-AI collaboration thinking.

### What you should learn
- Escalation patterns  
- Approval workflows  

### How to answer
- Focus on safety and UX  

### Sample Answer
Agents should involve humans for high-risk decisions, ambiguous inputs, or failure recovery. Clear escalation points improve trust and system reliability.

---

## 20. How do you decide agent boundaries?

### What the interviewer is evaluating
System design maturity.

### What you should learn
- Scope definition  
- Autonomy tradeoffs  

### How to answer
- Emphasize constraints  

### Sample Answer
I define clear goals, allowed actions, and termination conditions. Strong boundaries prevent misuse, reduce risk, and make behavior predictable.
