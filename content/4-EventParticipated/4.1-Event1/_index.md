---
title: "Event 1"
date: 2026-05-23
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Summary Report: "FCAJ Community Day - Conference Call - May"

### Purpose of the Event

- Connect the FCAJ (First Cloud AI Journey) internship community through in-person sharing sessions at Bitexco Financial Tower
- Update on trends in applying AI to product development and system operations
- Introduce core AWS services (CloudFront, Amazon Quick) and how to leverage them in practice
- Share hands-on experience from hackathon projects and enterprise use cases (credit scoring for startups)

### Speaker List

- Representatives from the AWS and FCAJ community teams covering topics: Context Engineering & AI, CloudFront, Amazon Quick, LLM Determinism, Multi-Agent System
- The LotusHacks Hackathon team sharing their journey building the UTMorpho product
- *(Specific speaker names will be added based on the official event program documentation)*

### Highlights

#### Context Is Everything: Making AI Actually Work for You

- Why AI "fails" when context is missing, and what context truly means in AI interaction
- The shift from plain prompt engineering to the "Second AI Brain" concept — AI with persistent memory and continuous learning
- The relationship between input context quality and the quality of AI output
- Career guidance for students who want to start building products with AI

#### 36 hrs with LotusHacks – Building UTMorpho from Idea to Reality

- The journey from initial idea to clearly defining the problem UTMorpho solves
- The pressure and discipline required when developing a product in 36 consecutive hours
- Failures, bottlenecks, and turning points during the development process
- Overall UTMorpho product demo and key takeaways from the competition

#### From Edge To Origin: CloudFront as Your Foundation

- Amazon CloudFront is suitable for many types of workloads, not just static content delivery
- Cost optimization strategies when using CloudFront
- Built-in security capabilities that protect applications at the edge layer
- Improved reliability and performance through a globally distributed architecture

#### Friendly AI Assistant with Amazon Quick

- **Quick Chat Agent**: AI assistant for data exploration and insight analysis
- **Quick Flows**: create intelligent workflows using natural language, no coding required
- **Quick Spaces**: collaborative space to transform individual insights into team-wide knowledge
- **Quick Sight**: build dashboards and reports from raw data using natural language

#### Non-Determinism of "Deterministic" LLM Settings

- How LLMs select the next token during text generation
- A common assumption: Temperature = 0 guarantees absolute determinism
- Reality: optimizations at the inference layer (batching, hardware, floating-point arithmetic) mean results can still vary
- Real-world impact on production systems and strategies to mitigate this risk

#### Enterprise-Grade Multi-Agent System: The Case of Startup Credit Scoring

- The mismatch between traditional banking data structures and startup-specific data characteristics
- When to use a single agent vs. when a multi-agent approach is needed
- The "Virtual Credit Committee" model — multiple agents playing different roles in the credit assessment process
- Guardrails and compliance requirements when deploying AI in financial services
- Operational ROI and a practical deployment roadmap

### Key Takeaways

#### AI & Product Thinking

- Context is the deciding factor for AI output quality — it goes far beyond writing a better prompt
- Great products often emerge from time pressure and the ability to make fast decisions (lesson from LotusHacks)
- AI is evolving from a single-purpose tool toward a system with persistent memory and continuous reasoning

#### Architecture & Infrastructure

- CloudFront is more than a CDN — it is a foundational layer for security, performance, and cost optimization
- A deeper understanding of non-determinism risk in LLMs, which is especially critical when building systems that require reproducibility
- Multi-agent systems are the right approach for complex, multi-step decision-making tasks like credit scoring

#### Enterprise AI Applications

- Amazon Quick highlights the trend of "AI-ifying" operational and data analysis tasks without requiring programming skills
- Designing guardrails and compliance frameworks is mandatory when introducing AI into sensitive domains such as finance

### Applying to Work

- Apply a "context-first" mindset when designing prompts and AI pipelines for current tasks
- Consider using CloudFront for workloads that need cost and latency optimization in the internship project
- Be mindful of non-determinism when testing and evaluating LLM outputs — avoid assuming identical results even with the same configuration
- Reference the multi-agent model when designing multi-step automation workflows
- Explore Amazon Quick as a potential tool for supporting internal reporting and data analysis

### Personal Experience at the Event

Attending the **FCAJ Community Day - Conference Call** at Bitexco Financial Tower was a memorable experience. It gave me direct access to the latest technology trends from AWS and real-world stories from the community.

#### Community Connection

- Had the opportunity to meet and exchange ideas directly with fellow FCAJ interns, as well as mentors and speakers
- The open and welcoming atmosphere of the event was inspiring for learning and sharing experiences

#### Academic and Technical Experience

- The "Context Is Everything" session changed how I approach working with AI — moving beyond writing prompts to thinking about how context is provided and managed
- The LotusHacks team's story about UTMorpho was a powerful source of inspiration, embodying the spirit of "real learning through real doing" under high-pressure conditions
- The presentation on LLM non-determinism made me reconsider previous assumptions about AI model consistency

#### Lessons Learned

- AI is not just a tool — it is gradually becoming a part of infrastructure that must be designed carefully, from context and reliability to compliance
- Combining foundational knowledge (cloud, system architecture) with AI is what truly creates sustainable value for an organization

#### Some Photos from the Event
![FCAJ Community Day - May](/images/Event1.jpg)
