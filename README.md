# VyapaarMitra

**Inventory intelligence for every Indian retailer**

AI-powered inventory management system for small-format retail stores in India.

## Overview

VyapaarMitra is a hybrid AI-deterministic system that combines Amazon Bedrock's language understanding with deterministic algorithms for reliable inventory management across kirana shops, mini-marts, and small supermarkets.

## Key Features

- **Progressive Data Capture**: Three modes (Pulse/WhatsApp/POS) adapt to store's digital maturity
- **Multimodal AI Extraction**: Extract purchase data from text, images, and voice
- **Deterministic Reorder Calculations**: Reliable, verifiable business logic
- **Multilingual Support**: Hindi and English with natural language chat
- **Store Type Adaptation**: Configurable for kirana, mini-mart, or small supermarket

## Technology Stack

- **Backend**: FastAPI (Python 3.11+)
- **Database**: SQLite → PostgreSQL migration path
- **AI**: Amazon Bedrock (Claude 3 Sonnet/Haiku)
- **Multimodal**: Amazon Transcribe (voice), Amazon Textract (images)
- **Frontend**: React/HTML responsive web app
- **Deployment**: AWS (EC2/ECS/Lambda)

## Project Structure

```
vyapaar-copilot/
├── requirements.md    # Product requirements and acceptance criteria
├── design.md         # Technical design and architecture
└── tasks.md          # Implementation task list
```

## Market Context

India has approximately 12 million grocery retail outlets and ~13 million kirana stores (source: McKinsey, Business Standard reports). This project addresses the inventory management needs of small-format retail stores that lack traditional POS infrastructure.

## Documentation

- **[Requirements](vyapaar-copilot/requirements.md)**: Detailed product requirements with acceptance criteria
- **[Design](vyapaar-copilot/design.md)**: Technical architecture and implementation details
- **[Tasks](vyapaar-copilot/tasks.md)**: Implementation roadmap and task breakdown

## Getting Started

Documentation for setup and development will be added as implementation progresses.

## License

TBD