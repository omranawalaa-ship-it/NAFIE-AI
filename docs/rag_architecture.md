# NAFIE AI RAG Architecture

## 1. Purpose

The NAFIE AI Retrieval-Augmented Generation (RAG) architecture provides the knowledge retrieval layer that connects trusted regulatory and operational information with the AI decision-support engine.

The RAG architecture is designed to improve the relevance, traceability, and reliability of AI-generated outputs while maintaining human oversight.

---

## 2. Core Principle

NAFIE AI does not rely solely on the language model's internal knowledge.

Before generating a response, the system retrieves relevant information from the trusted Knowledge Repository and provides that information as contextual evidence to the AI model.

The resulting response should remain traceable to the retrieved sources.

---

## 3. High-Level RAG Pipeline

```text
User / Case Report
        |
        v
Query Understanding
        |
        v
Query Classification
        |
        v
Knowledge Retrieval
        |
        v
Candidate Ranking
        |
        v
Context Assembly
        |
        v
LLM Generation
        |
        v
Citation & Evidence Validation
        |
        v
Human Review
        |
        v
Decision Support Output## 4. Query Understanding

The system first analyzes the incoming report or user query.

The process may identify:

- Case type
- Fraud category
- Relevant entities
- Transaction context
- Jurisdiction
- Regulatory domain
- Urgency indicators
- Required information

The result is a structured retrieval query.

---

## 5. Query Classification

The retrieval system may classify queries into one or more knowledge domains.

Examples include:

- Financial fraud
- Banking
- Cybersecurity
- Identity fraud
- Payment fraud
- Regulatory requirements
- Reporting procedures
- AI governance
- Data protection

Multi-domain retrieval should be supported when a case involves more than one regulatory or operational area.

---

## 6. Knowledge Retrieval

The retrieval layer searches the Knowledge Repository for relevant information.

The initial architecture supports:

- Semantic search
- Metadata filtering
- Keyword search
- Hybrid retrieval
- Source-authority filtering

The retrieval layer should preserve the relationship between each retrieved chunk and its original source document.

---

## 7. Retrieval Ranking

Retrieved candidates should be ranked according to multiple factors.

Potential ranking signals include:

- Semantic relevance
- Keyword relevance
- Source authority
- Document status
- Recency
- Effective date
- Knowledge-domain match
- Metadata match

Authoritative sources should receive appropriate priority over lower-authority supporting material.

---

## 8. Context Assembly

The highest-quality retrieved knowledge units are assembled into a controlled context for the language model.

Context assembly should:

- Preserve source identity.
- Preserve section information.
- Preserve relevant metadata.
- Avoid unnecessary duplication.
- Maintain sufficient context to interpret regulatory provisions.
- Respect context-window limitations.

---

## 9. LLM Generation

The language model receives:

```text
System Instructions
        +
Case / User Query
        +
Retrieved Knowledge
        +
Output Schema
