# 📄 Event-Driven Document Processing System

An **event-driven microservices-based** system that automates document processing using **Python (FastAPI/Django)** and **Java (Spring Boot)**. The system is designed to run **on AWS (S3, SNS, SQS, DynamoDB)** and **locally using Docker**.

---

## 🌟 Features
- 📤 **Uploads documents to AWS S3** (PDF, Word, Text)
- 🔔 **Triggers SNS event** upon upload
- 🐍 **Python Service (FastAPI/Django)** extracts text from documents
- ☕ **Java Service (Spring Boot)** analyzes sentiment and keywords
- 🗄 **Stores results in DynamoDB/PostgreSQL**
- 🛠 **Deployable via Docker & AWS**

---

## 🏗 Architecture Overview

```mermaid
sequenceDiagram
    participant User
    participant AWS S3
    participant SNS
    participant Python Service
    participant Java Service
    participant Database

    User->>AWS S3: Uploads Document
    AWS S3-->>SNS: Triggers Event
    SNS-->>Python Service: Notifies for text extraction
    Python Service-->>Database: Stores extracted text
    Python Service-->>Java Service: Sends extracted text for analysis
    Java Service-->>Database: Stores sentiment & keyword analysis

