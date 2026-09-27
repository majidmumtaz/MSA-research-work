# Open Problems in Agentic AI

Following are common open problems of Agentic AI Engineering.

## 1. Reasoning, planning and execution loops
- **Repetition loops:** agents repeat the same thoughts and actions and can't break out. This is often caused by missing physical commonsense.
- **Local minima:** self-reflection style optimization gets stuck and struggles with open-ended or creative exploration.
- **Noisy feedback:** uninformative search results or observations derail the agent's reasoning.
- **Scale dependency:** ReAct and Reflexion patterns emerge only in large models. Smaller models need heavy fine-tuning.
- **Context distraction:** a long history of actions and failures anchors the agent to what it did before.
- **Long context is not long-horizon reasoning:** a large window helps fact retrieval, but it doesn't help planning over changing states. Models also suffer from "lost in the middle."
- *Sources: Papers 1, 4, 5; 

## 2. Tool use and action execution
- **Chaining:** Toolformer-style calls are made independently, so there is no multi-step chaining or query refinement.
- **Prompts and samples:** tool triggering is sensitive to prompt wording, and training for tool use is sample-inefficient.
- **Execution cost:** models don't take the cost or latency of API calls into account.
- **Schema bloat:** loading hundreds of tool definitions uses up tokens and leads to wrong tool choices.
- **Code execution limits:** problems include non-determinism, impure APIs, hardware-dependent output and concurrency.
- **Real-world actions:** payments, infrastructure and database changes need authentication, sandboxing and approval workflows.
- *Sources: Papers 2, 4; 5 Papers Every Agentic AI Engineer; 

## 3. Memory and context management
- **Retrieval:** retrieval returns partial or irrelevant memories, which leads to contradictory behaviour.
- **Spatial drift:** as agents learn more locations, their spatial decisions get worse.
- **Context poisoning:** hallucinated facts saved in persistent memory carry over and build up in later steps.
- **Context clash:** old and new facts coexist and nothing says which one wins.
- **Open questions:** adaptive retrieval (a dynamic top_k) and judging compaction quality over multi-hour runs.
- *Sources: Papers 3, 4;

## 4. Multi-agent coordination
- **Overhead:** subagents can raise token use by more than 600% and roughly quadruple cost compared with a single agent.
- **Conflicts:** subagents produce conflicting outputs and use inconsistent terminology, which makes debugging hard.
- **Chatter:** unmanaged agent conversations turn into dialogue loops.
- **Ungrounded role-play:** role-playing through prompts alone, without code execution or tools, fails on complex tasks.
- **Unknowns:** the best topology, role assignment and balance between automation and human control are still unknown.
- *Sources: Paper 5; 5 Papers; 

## 5. Evaluation and instrumentation
- **Outcome-only metrics:** judging only the final output hides bloat, poor retrieval and redundant tool calls.
- **Action logs:** logs record tool calls but not what was in the context window, so root-cause analysis is hard.
- **Cost tracking:** attributing tokens and cost across subagents is difficult.
- **Benchmarks:** evaluations are short and compared against crowdworkers. Long-horizon, real-world benchmarks are missing.
- **Demo vs. production:** without benchmarks, cost caps and permission limits, reflection loops are just "confident retries."
- *Sources: Paper 3; 5 Papers; 

## 6. Safety, security and societal risks
- **Autonomy risks:** cascading errors, reward hacking and runaway execution.
- **Misuse and attacks:** misuse includes deepfakes, misinformation and tailored persuasion. Attacks include prompt hacking and "memory gaslighting."
- **Human impact:** users can form parasocial relationships with human-like agents.
- **Bias:** agents inherit the model's biases and represent marginalized groups poorly.
- *Sources: Papers 3, 4, 5*
