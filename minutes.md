## Minutes for IETF 125 AI Agent Security Side Meeting

The IETF 125 AI Agent Security Side Meeting took place on Thursday from 11:15 to 12:30 in the Hunan room. The session was well received, drawing strong interest from approximately 40 onsite and 60 remote participants, with positive feedback.
The agenda featured five key presentations focused on:

  - Gap analysis of current security standards.
  - Authentication and authorization requirements, specifically for cross-domain agent-to-agent communication.
  - Proposed security layers and potential future work items for the IETF.
  - Auditability and accountability frameworks.

Agenda, materials and recordings here: https://github.com/liuchunchi/IETF125-AI-Agent-Security-Side-Meeting

**Current risks and gaps identified:**
  1.	AI Agent security risks partially inherit from the LLM Top 10, with specific gaps including a lack of fine-grained access control, loss of security context, and insufficient continuous security monitoring, etc.
  2.	Threats against AI Agents are more implicit through payloads like prompt injection.
  3.	Cross-domain security context (like authentication chaining, rich authorization) should be preserved across multiple domains when necessary. Privacy should be considered.
  4.	In general, network experts are not able to perform threat modelling, threat analysis.

**Several consensus points achieved:**
  1.	Agents need to have individual identities and thus visibility.
  2.	Reuse current standards and best practices like OAuth, WIMSE, SCIM… as much as possible. 
  3.	Respect each individual administrative domain or ecosystem’s current security best practices, and focus on addressing trust gaps between proprietary and public-to-private domains. (There are some public domain agent discovery works going on)
  4.	Consensus that a guidance or BCP to map existing standards to agent scenarios and identify minor gaps for extension would be useful.
  5.	Need further privacy considerations for AI agent identity, authorization details, capability, etc.
  6.	Runtime and static integrity of AI should be considered to ensure audibility and compliance.

**Several controversial points:**

1. Should we treat agent identities more like workload identities or human user identities?  
  a. Peter thinks agents are special workloads that maintain stateful information between callers and LLM/tools, using which to complete ambiguous tasks.  
  b. Diego mentioned 3 works[1] that tries to do identity chains on SPICE.  
  c. Brian think agent identities are workloads thus should not go to SPICE.  
  d. Usama is not sure.  
  e. Daniel thinks this could be use case specific.  
   
2. Should a dedicated AI Security mailing list be created?  
  a. Some (7~8 Peter Mike Roberta Arnaud Usama Henk Daniel Russ…) people think it is best to have a dedicated discussion list (AISEC, for example), believing the A2A list is too crowded and broad.  
  b. 2-ish (Brian and Dapeng) think discussion should stay in A2A, adding a [security] tag.  

**Next steps agreed onsite:**
1.	Use Case Consolidation: Collect different agent application scenarios brought by network experts (mobile network, managed networks, Internet…)
2.	Develop a new agent security problem statement document, derive security requirements from the consolidated use case, and put it in the Google Doc/GitHub.
3.	Develop a map from existing standards to agent scenarios to help identify gaps. List and categorize new works.
4.	Workshops/interim: Regular meetings to iterate on the above documents. 
5.	Keep taking in useful input from external communities.


**Considerations for the IESG:**
1.	Are the security topics identified relevant for the IETF?
2.	Should there be a dedicated AI Security (AISEC) mailing list to be created?

[1] https://datatracker.ietf.org/doc/draft-mw-spice-actor-chain/
https://datatracker.ietf.org/doc/draft-mw-spice-inference-chain/
https://datatracker.ietf.org/doc/draft-mw-spice-intent-chain/
