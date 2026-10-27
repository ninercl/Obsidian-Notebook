#AIagents

>[!tip]- It is expectd that AI agents will save $80 billion dollars to companies. Gartner 

Benefits: 
- Leverages automation
- Makes data-driven decisiones
- Boost efficiency 
- Drives innovation
- Enhances competitiveness

![[Pasted image 20261005203918.png|595]]


Self-driving car example

![[Pasted image 20261005204017.png|601]]

![[Pasted image 20261005204051.png|604]]

![[Pasted image 20261005204129.png|601]]

Multi-agent systems
- Collaborate between multiple agents
- achieve individual and collective goals
- Enable distributed problem-solving
- Foster cooperative decision-making
- Exhibit emergen behaviors 

![[Pasted image 20261005204303.png|603]]


![[Pasted image 20261005204352.png|616]]

![[Pasted image 20261005204405.png|620]]

![[Pasted image 20261005204451.png|622]]

![[Pasted image 20261005204510.png|616]]

Whats is an Agent ?

	Shift models            →       Compound systems 

	(-) limited knowledge         (+)  Modular
  
	(-) hard to adapt             (+) Easier to adjust

![[Pasted image 20261005210917.png|506]]


---
Robotics and automation

- Global industries plan to invest 25% into automation 
- Robotics involve: 
	- Design, construct, and operate robots
	- Perform tasks with or without assistances 

![[Pasted image 20261005212518.png|571]]

![[Pasted image 20261005212535.png|586]]



![[Pasted image 20261005212552.png]]

![[Pasted image 20261005212610.png]]

![[Pasted image 20261005212622.png]]


Cobots

![[Pasted image 20261005212701.png|581]]

What is Robotic Process Automation (RPA)?

- Helps, create, use, and control virtual robots.
![[Pasted image 20261005212858.png|588]]

![[Pasted image 20261005212931.png|590]]

---
AI in business

Chatbots 

![[Pasted image 20261007000246.png|601]]

![[Pasted image 20261007000306.png|597]]

![[Pasted image 20261007000340.png|595]]


![[Pasted image 20261007000355.png|595]]
![[Pasted image 20261007001148.png|599]]



![[Pasted image 20261007001910.png]]



---
Introduction to RAG
[RAG]

# RAG — Retrieval-Augmented Generation

**Retrieval-augmented generation (RAG)** combines external information retrieval with a generative model to produce responses grounded in relevant documents.

## How It Works

1. **Retrieve:** Search a knowledge base for documents or passages relevant to the query.
2. **Augment:** Add the retrieved information to the model’s input alongside the query.
3. **Generate:** The LLM uses the query and retrieved context to produce a response.

**Flow:** Query → Retrieval → Query + context → Response.

> [!example] Example  
> A customer asks about a refund policy. The system retrieves the relevant policy document, and the LLM generates an answer based on its contents.

## Key Components

|Component|Purpose|Examples|
|---|---|---|
|**Retriever**|Find relevant information in a knowledge base|BM25, embedding-based retrieval|
|**Generative model**|Produce a response using the query and retrieved context|An LLM such as GPT|

- **BM25:** Retrieves information through term matching and relevance scoring.
- **Dense retrieval:** Uses numerical representations called _embeddings_ to identify semantic similarity.

## How RAG Helps Address LLM Limitations

|LLM limitation|How RAG helps|
|---|---|
|Hallucinations|Supplies sources that can ground the response|
|Outdated knowledge|Enables access to updated external information|
|Limited domain knowledge|Retrieves specialized documentation|
|Documents exceeding the context window|Selects relevant passages to include in the available context|

> [!important] Important Distinctions
> 
> - RAG **reduces but does not eliminate** hallucinations.
> - Responses are current **only if the retrieved sources are current**.
> - RAG **does not physically expand the context window**; it selects information to fit within it.
> - Retrieval adds processing, so RAG **does not guarantee lower costs or faster responses**.
> - Updating the knowledge base does not require retraining the LLM.

## Benefits and Applications

- **More specific, grounded responses** using external information.
- **Flexibility:** Knowledge sources can be changed or updated.
- **Question answering:** Answer questions using specialized documents.
- **Customer support:** Retrieve manuals, policies, and troubleshooting guides.
- **Content creation:** Generate reports and articles supported by sources.
- **Search:** Synthesize answers from retrieved documents.

## Google Cloud — From the Reading

- **Vertex AI:** Tools for integrating and deploying AI models and applications.
- **BigQuery:** Data querying capabilities that can support retrieval.
- Cloud infrastructure supports scalability, customization, and integration with different data sources.

> [!warning] Correction to the Reading  
> **Standard BERT is not a text generator like GPT.** It can support retrieval or classification tasks, but it is not an appropriate example of the generative component in a conversational RAG system.

## Key Takeaway

**RAG lets an LLM consult relevant external information before answering. Its effectiveness depends on source quality, retrieval quality, and the generative model.**

## Related Notes

[[Generative AI]] · [[Large Language Models]] · [[Embeddings]] · [[Natural Language Processing]]

>[!warning] LLM Challenges
>1. No source
>2. Out of Date


---
## Adopting AI in your business

![[Pasted image 20261008002549.png|652]]

![[Pasted image 20261008002617.png|643]]

Tata consultancy: 86% of senior business leaders adopted AI

![[Pasted image 20261008002845.png|648]]

![[Pasted image 20261009001735.png|641]]

![[Pasted image 20261009001750.png|643]]

---
Ai Frameworks

IBM AI Ladder
- A structured framework
- Navigates organizations from data collection to full-scale AI integration

Collect → Organize → Analyze → Infuse 


![[Pasted image 20261009002222.png|643]]

![[Pasted image 20261009002250.png|641]]

![[Pasted image 20261009002330.png|642]]

---
AI for Your Career

> [!tip] Statista estimates that the number of gobal user in ten years will increase to 700 million


![[Pasted image 20261009003849.png]]


