# Requirements Document: Vyapaar Copilot

## Executive Summary

**Problem**: India has approximately 12 million grocery retail outlets according to industry research (Nielsen, IBEF reports cite ~13 million kirana stores). Small-format retail stores—kirana shops, mini-marts, and small supermarkets—face inventory management challenges due to stockouts and dead stock. Traditional inventory management software assumes POS systems and digital infrastructure that most small-format retailers don't have.

**Solution**: Vyapaar Copilot is an AI-powered decision support system that works even without POS/receipts through progressive data capture modes. It uses Amazon Bedrock to extract structured data from unstructured inputs (WhatsApp messages, voice notes, images) and provides daily reorder recommendations with explainable, multilingual chat support.

**Innovation**: 
- Progressive capture (Pulse/WhatsApp/POS modes) meets stores where they are
- Hybrid AI-deterministic architecture prevents hallucinated numbers
- Multimodal extraction from real-world supplier communication
- Store type adaptation (kirana/mini-mart/supermarket)
- Bharat-first multilingual design (Hindi/English)

**Impact Hypothesis** (to be validated through pilot testing):
- Target: 30% stockout reduction through systematic tracking
- Time savings: Reduce daily inventory management from 30 min to <5 min
- Addressable market: ~12 million small-format retail stores in India
- Measurable metrics: stockout incidents, dead stock value, time saved/day, pulse completion rate

**Feasibility**: 
- Proven tech stack (FastAPI, SQLite, Bedrock, React)
- Demo-ready in 2-3 minutes with live Bedrock calls
- Clear GTM through POS partners, distributors, FMCG field sales

### Illustrative Impact Scenario

**Assumptions** (to be validated with pilot data):
- Typical kirana shop: ₹50,000 monthly sales
- Estimated stockout loss: 10-15% of potential sales (industry estimates)
- System reduces stockouts by: 30% (hypothesis)

**Formula**: 
```
recovered_sales = monthly_sales × stockout_loss_% × reduction_%
```

**Example Calculation**:
```
recovered_sales = ₹50,000 × 12% × 30% = ₹1,800/month
```

This is an illustrative scenario with explicit assumptions. Actual impact will vary by store type, product mix, and baseline inventory practices. Pilot testing is required to validate these hypotheses.

## Introduction

Vyapaar Copilot is an AI-powered decision support system designed for small-format retail stores—including kirana shops, mini-marts/convenience stores, and small supermarkets (1–3 outlets)—to help with inventory reordering and stockout prevention. The system addresses the unique challenge that many small-format retailers lack formal POS systems, receipts, or invoices, making traditional inventory management solutions impractical.

The solution leverages Amazon Bedrock for AI-powered extraction and natural language interactions while maintaining accuracy through deterministic algorithms for critical business calculations. It supports three progressive modes of data capture, from simple daily stock checks to WhatsApp message parsing to optional CSV ingestion.

## Problem Statement

Small-format retail stores across India face critical inventory management challenges that directly impact their profitability and customer satisfaction:

1. **Stockouts and Lost Sales**: Without systematic tracking, stores frequently run out of fast-moving products, leading to lost revenue and customer dissatisfaction
2. **Dead Stock and Capital Lock-in**: Overstocking slow-moving items ties up working capital and leads to wastage
3. **Manual Guesswork**: Reorder decisions are based on memory and intuition rather than data, leading to suboptimal inventory levels
4. **Data Maturity Gap**: Kirana shops often have no POS or receipts; mini-marts may have basic billing; small supermarkets may have POS exports—but none have actionable insights
5. **Time Burden**: Store owners spend 30+ minutes daily on inventory checks and supplier coordination
6. **Margin Leakage**: Poor inventory decisions erode already thin margins (typically 8-15% in small retail)

Traditional inventory management software assumes digital infrastructure (POS systems, barcode scanners, trained staff) that most small-format retailers don't have. This creates a technology adoption gap that leaves millions of stores without decision support tools.

## Solution Overview

Vyapaar Copilot is an AI-powered solution that enhances decision-making, efficiency, and user experience across retail ecosystems by:

1. **Zero-Setup Inventory Intelligence**: Works even without POS/receipts through progressive data capture modes
2. **AI-Powered Data Extraction**: Converts unstructured inputs (WhatsApp messages, voice notes, images) into structured inventory events
3. **Deterministic Reorder Recommendations**: Provides daily reorder carts with quantities, urgency, and confidence scores
4. **Multilingual Conversational Interface**: Enables Hindi and English queries with grounded, explainable responses
5. **Supplier Integration**: Generates WhatsApp-ready order messages for quick supplier coordination

The solution directly aligns with the "AI for Retail, Commerce & Market Intelligence" track by using AI to transform unstructured retail data into actionable intelligence, improving operational efficiency and decision-making for underserved small-format retailers.

## Innovation & Uniqueness

Vyapaar Copilot introduces several novel approaches that differentiate it from existing inventory management solutions:

### 1. Progressive Data Capture (Zero-Setup Innovation)
Unlike traditional systems that require POS infrastructure, Vyapaar Copilot works with whatever data the store has:
- **Mode 0 (Pulse)**: Quantity buckets (0/1/2/3/4+) for stores with zero digital infrastructure
- **Mode 1 (WhatsApp)**: AI extraction from existing supplier communication channels
- **Mode 2 (POS)**: CSV ingestion for stores with basic billing systems

**Novelty**: This progressive approach meets stores where they are, creating a zero-barrier entry point while allowing graduation to higher accuracy modes as stores digitize.

### 2. Hybrid AI-Deterministic Architecture (Responsible AI)
Most AI solutions are either pure-AI (prone to hallucination) or pure-rules (inflexible). Vyapaar Copilot combines both:
- **AI handles**: Unstructured data extraction, product normalization, multilingual chat
- **Deterministic code handles**: All business-critical calculations (reorder quantities, stockout risks)
- **Guardrails ensure**: No hallucinated numbers, all responses cite data sources

**Novelty**: This architecture delivers AI's flexibility for messy inputs while maintaining mathematical rigor for business decisions—critical for financial trust.

### 3. Multimodal WhatsApp Intelligence
Existing inventory tools require manual data entry. Vyapaar Copilot extracts from real-world supplier communication:
- **Text extraction**: Free-form Hindi/English messages with mixed formats
- **Image extraction**: Screenshots of handwritten orders, delivery receipts
- **Voice extraction**: Hindi/English voice notes with colloquial language

**Novelty**: Leverages Amazon Bedrock's multimodal capabilities to turn existing communication channels into structured data sources—no behavior change required from store owners.

### 4. Store Type Adaptation
One-size-fits-all solutions fail because kirana shops, mini-marts, and small supermarkets have different operational realities:
- **Kirana**: 50 SKUs, 5-7 day cover, 2-3 day lead time, Pulse Mode primary
- **Mini-Mart**: 80 SKUs, 7-10 day cover, 3-5 day lead time, WhatsApp Mode primary
- **Small Supermarket**: 200 SKUs, 10-14 day cover, 5-7 day lead time, POS Mode primary

**Novelty**: Configurable parameters adapt recommendations to store type while maintaining consistent core logic—maximizes relevance across diverse retail formats.

### 5. Bharat-First Multilingual Design
Most enterprise software is English-first with poor Hindi support. Vyapaar Copilot is designed for Bharat:
- **Language detection**: Automatic Hindi/English detection with Hinglish support
- **Contextual responses**: Not just translation—culturally appropriate explanations
- **WhatsApp integration**: Generates supplier messages in user's preferred language

**Novelty**: True multilingual support using Bedrock's language capabilities, not just UI translation—enables natural interaction for non-English users.

## Why AI is Necessary (Not Rule-Based Logic)

Traditional rule-based systems fundamentally cannot solve the core challenges faced by small-format retail stores. Here's why AI is essential:

### 1. Messy Product Names and Units (Impossible with Regex)

Store owners refer to products inconsistently across languages, spellings, abbreviations, and formats:
- "Tata Salt 1kg" vs "tata salt" vs "टाटा नमक 1 किलो" vs "TS 1kg" vs "Tata Namak 1 kilo"
- "Aashirvaad Atta 5kg" vs "ashirwad ata 5 kg" vs "आशीर्वाद आटा" vs "AA 5kg"

**Why Rules Fail**: Writing regex patterns for every product × every variant × every language × every abbreviation is infeasible. A single product can have 20+ variants. With 200 SKUs, that's 4,000+ patterns to maintain manually.

**AI Solution**: Amazon Bedrock's semantic understanding maps variants to canonical products using context, not exact matches. It learns that "टाटा नमक" and "Tata Salt" refer to the same product despite different scripts and languages.

### 2. Unstructured WhatsApp Purchase Signals (Beyond Parsing)

Small retailers coordinate with suppliers via WhatsApp using free-form text, voice notes, and screenshots:
- Hindi voice note: "भाई 10 टाटा नमक, 5 आटा भेज दो" (mixed Hindi-English, no punctuation)
- Screenshot of handwritten order list (cursive, crossed-out items, margin notes)
- Mixed format: "Send 10 pkt salt, 5 atta bags tomorrow, also 2 doz bread if available"

**Why Rules Fail**: 
- Voice transcription requires speech-to-text (AI)
- Handwriting recognition requires OCR + context understanding (AI)
- Free-form text has no fixed structure—quantities can appear before/after product names, units are implied, dates are relative ("tomorrow", "next week")
- Conditional items ("if available") require intent understanding

**AI Solution**: Bedrock's multimodal capabilities (text, image, audio) extract structured data from unstructured inputs. It understands context: "10 pkt" means 10 packets, "2 doz" means 24 units, "tomorrow" means next day's date.

### 3. Multilingual Explanations for Bharat Users (Context-Aware)

Small-format retail owners are more comfortable in regional languages and need explanations, not just numbers:
- "मेरे पास कौन से प्रोडक्ट कम हो रहे हैं?" (Which products are running low?)
- "Why should I order salt today?" (expects reasoning, not just "yes")
- "क्या मुझे चीनी का स्टॉक बढ़ाना चाहिए?" (Should I increase sugar stock?)

**Why Rules Fail**: Template-based responses can't handle:
- Language detection and code-switching (Hinglish)
- Contextual reasoning ("why" questions require citing data + explaining logic)
- Follow-up questions that reference previous context
- Nuanced queries that don't match predefined templates

**AI Solution**: Bedrock generates contextual, language-appropriate responses grounded in actual data. It detects query language, retrieves relevant inventory context, and explains recommendations with citations.

### 4. Grounded Reasoning with Guardrails (Hybrid AI-Deterministic)

Unlike generic AI chatbots that hallucinate numbers, Vyapaar Copilot uses a hybrid approach:

**The Problem with Pure AI**: LLMs can generate plausible-sounding but incorrect numbers:
- "You should order 47 packets of salt" (made up)
- "Your average consumption is 3.7 packets/day" (hallucinated)

**The Problem with Pure Rules**: Rule-based systems can't handle natural language queries or unstructured inputs.

**Our Hybrid Solution**: 
- **AI Layer (Bedrock)**: Handles extraction, normalization, language understanding, explanation generation
- **Deterministic Layer (Python)**: Computes all business-critical numbers (reorder quantities, stockout risks)
- **Guardrails**: Bedrock guardrails prevent LLM from generating numerical recommendations
- **Grounding**: Chat responses cite specific data sources ("Based on your stock level from Feb 10...")
- **Transparency**: Confidence scores indicate reliability of AI-extracted data

This responsible AI approach ensures store owners can trust the system for critical business decisions while benefiting from AI's flexibility for unstructured data handling.

## Store Type Configuration

Vyapaar Copilot adapts to different small-format retail contexts through store type configuration:

### Store Types

1. **Kirana Shop**: Traditional neighborhood store, typically 200-500 sq ft, family-owned
   - Default tracked SKUs: 50
   - Target cover days: 5-7 days
   - Suggested lead time: 2-3 days
   - Primary mode: Pulse Mode (no POS)

2. **Mini-Mart / Convenience Store**: Slightly larger format, 500-1500 sq ft, may have basic billing
   - Default tracked SKUs: 80
   - Target cover days: 7-10 days
   - Suggested lead time: 3-5 days
   - Primary mode: WhatsApp Mode or POS Mode

3. **Small Supermarket**: 1500-3000 sq ft, 1-3 outlets, typically has POS system
   - Default tracked SKUs: 200
   - Target cover days: 10-14 days
   - Suggested lead time: 5-7 days
   - Primary mode: POS Mode with WhatsApp fallback

### Onboarding Flow

During initial setup, users select their store type, which configures default parameters. All parameters remain user-adjustable based on specific business needs.

## Glossary

- **Small_Format_Retail**: Kirana shops, mini-marts/convenience stores, and small supermarkets (1-3 outlets)
- **Kirana_Shop**: A small neighborhood retail shop in India, typically family-owned, selling groceries and daily essentials
- **Mini_Mart**: A convenience store format, 500-1500 sq ft, may have basic billing systems
- **Small_Supermarket**: A small supermarket with 1-3 outlets, typically 1500-3000 sq ft, usually has POS systems
- **Vyapaar_Copilot**: The AI-powered inventory decision support system
- **Pulse_Mode**: Mode 0 - Daily stock level capture using quantity buckets (0/1/2/3/4+)
- **WhatsApp_Mode**: Mode 1 - Extraction of purchase events from WhatsApp order messages
- **POS_Mode**: Mode 2 - CSV data ingestion for stores with basic point-of-sale systems
- **Reorder_Cart**: A list of products recommended for reordering with quantities and urgency levels
- **Stockout_Risk**: The probability that a product will run out of stock before the next reorder
- **Confidence_Score**: A numerical indicator (0-1) of how reliable a prediction or extraction is
- **Bedrock**: Amazon Bedrock, the managed AI service used for extraction and natural language processing
- **Grounded_Response**: An AI response that cites specific data sources and avoids hallucination
- **Quantity_Bucket**: A discrete stock level category (0, 1, 2, 3, or 4+)
- **Purchase_Event**: A recorded instance of inventory being purchased from a supplier
- **Product_Normalization**: The process of mapping variant product names to canonical product identifiers

## Requirements

### Requirement 1: Pulse Mode Stock Capture

**User Story:** As a small-format retail store owner, I want to quickly record my daily stock levels using simple quantity buckets, so that I can track inventory without complex data entry.

#### Acceptance Criteria

1. WHEN a user selects Pulse Mode, THE Vyapaar_Copilot SHALL display a list of tracked products with quantity bucket options (0, 1, 2, 3, 4+)
2. WHEN a user selects a quantity bucket for a product, THE Vyapaar_Copilot SHALL record the stock level with a timestamp
3. WHEN a user submits daily stock levels, THE Vyapaar_Copilot SHALL persist the data to the database immediately
4. WHEN a user views their stock history, THE Vyapaar_Copilot SHALL display historical quantity bucket selections organized by date
5. THE Vyapaar_Copilot SHALL support recording stock levels for at least 200 products in a single session (configurable based on store_type)

### Requirement 2: WhatsApp Message Parsing

**User Story:** As a small-format retail store owner, I want the system to extract purchase information from my WhatsApp order messages, so that I don't have to manually enter every purchase.

#### Acceptance Criteria

1. WHEN a user uploads a WhatsApp text message containing order information, THE Vyapaar_Copilot SHALL extract product names, quantities, and prices into structured JSON
2. WHEN a user uploads a WhatsApp screenshot image, THE Vyapaar_Copilot SHALL use Bedrock to extract order details from the image
3. WHEN a user uploads a WhatsApp voice note, THE Vyapaar_Copilot SHALL transcribe and extract purchase information
4. WHEN extraction is complete, THE Vyapaar_Copilot SHALL display extracted purchase events with confidence scores for user verification
5. WHEN a user confirms extracted data, THE Vyapaar_Copilot SHALL record the purchase events in the database
6. IF extraction confidence is below 0.7 for any field, THEN THE Vyapaar_Copilot SHALL flag the field for manual review

### Requirement 3: POS Data Ingestion

**User Story:** As a small-format retail store owner with a basic POS system, I want to upload CSV files of my sales and purchase data, so that I can leverage existing digital records.

#### Acceptance Criteria

1. WHEN a user uploads a CSV file in POS Mode, THE Vyapaar_Copilot SHALL validate the file format and required columns
2. WHEN a valid CSV file is uploaded, THE Vyapaar_Copilot SHALL parse and import purchase events into the database
3. IF a CSV file has missing required columns, THEN THE Vyapaar_Copilot SHALL return a descriptive error message listing the missing columns
4. WHEN CSV import is complete, THE Vyapaar_Copilot SHALL display a summary showing the number of records imported and any errors encountered
5. THE Vyapaar_Copilot SHALL support CSV files with at least 1000 rows

### Requirement 4: Product Name Normalization

**User Story:** As a small-format retail store owner, I want the system to recognize that "Tata Salt 1kg", "tata salt", and "टाटा नमक" refer to the same product, so that my inventory tracking is accurate despite naming variations.

#### Acceptance Criteria

1. WHEN a product name is extracted from any input source, THE Vyapaar_Copilot SHALL use Bedrock to normalize it to a canonical product identifier
2. WHEN multiple variant names map to the same product, THE Vyapaar_Copilot SHALL consolidate their stock levels and purchase history
3. WHEN a new product name variant is encountered, THE Vyapaar_Copilot SHALL either map it to an existing product or create a new product entry
4. THE Vyapaar_Copilot SHALL maintain a mapping table of product name variants to canonical identifiers
5. WHEN displaying products to users, THE Vyapaar_Copilot SHALL show the canonical product name with variant names as metadata

### Requirement 5: Reorder Quantity Calculation

**User Story:** As a small-format retail store owner, I want the system to calculate exactly how much of each product I should reorder, so that I can maintain optimal stock levels without overstocking.

#### Acceptance Criteria

1. THE Vyapaar_Copilot SHALL compute reorder quantities using deterministic algorithms based on historical consumption rates
2. WHEN calculating reorder quantities, THE Vyapaar_Copilot SHALL consider current stock level, average daily consumption, and lead time
3. WHEN generating a reorder recommendation, THE Vyapaar_Copilot SHALL include the calculated quantity, urgency level (low/medium/high), and confidence score
4. THE Vyapaar_Copilot SHALL NOT use LLM-generated numbers for reorder quantities
5. WHEN historical data is insufficient, THE Vyapaar_Copilot SHALL use conservative default values and mark the confidence score as low

### Requirement 6: Stockout Risk Prediction

**User Story:** As a small-format retail store owner, I want to know which products are at risk of running out, so that I can prioritize my reordering decisions.

#### Acceptance Criteria

1. THE Vyapaar_Copilot SHALL calculate stockout risk for each product based on current stock and consumption velocity
2. WHEN a product's stockout risk exceeds 0.7, THE Vyapaar_Copilot SHALL flag it as high urgency in the reorder cart
3. WHEN a product's stockout risk is between 0.4 and 0.7, THE Vyapaar_Copilot SHALL flag it as medium urgency
4. WHEN a product's stockout risk is below 0.4, THE Vyapaar_Copilot SHALL flag it as low urgency
5. THE Vyapaar_Copilot SHALL update stockout risk calculations daily based on the latest stock levels

### Requirement 7: Daily Reorder Cart Generation

**User Story:** As a small-format retail store owner, I want to receive a daily reorder cart with recommended products and quantities, so that I can quickly place orders with my suppliers.

#### Acceptance Criteria

1. THE Vyapaar_Copilot SHALL generate a daily reorder cart containing all products that need reordering
2. WHEN displaying the reorder cart, THE Vyapaar_Copilot SHALL show product name, recommended quantity, urgency level, confidence score, and current stock level
3. WHEN a user views the reorder cart, THE Vyapaar_Copilot SHALL sort products by urgency level (high to low)
4. WHEN a user modifies a recommended quantity, THE Vyapaar_Copilot SHALL preserve the user's adjustment for that order
5. THE Vyapaar_Copilot SHALL allow users to remove products from the reorder cart before finalizing

### Requirement 8: Supplier Order Message Generation

**User Story:** As a small-format retail store owner, I want the system to generate WhatsApp-ready order messages for my suppliers, so that I can quickly place orders without manual typing.

#### Acceptance Criteria

1. WHEN a user finalizes a reorder cart, THE Vyapaar_Copilot SHALL generate a formatted WhatsApp message containing the order details
2. WHEN generating supplier messages, THE Vyapaar_Copilot SHALL group products by supplier if supplier information is available
3. WHEN displaying the generated message, THE Vyapaar_Copilot SHALL provide a copy-to-clipboard button for easy sharing
4. THE Vyapaar_Copilot SHALL format the message in a clear, readable format with product names and quantities
5. WHERE the user has specified a preferred language, THE Vyapaar_Copilot SHALL generate the message in that language (Hindi or English)

### Requirement 9: Multilingual Chat Interface

**User Story:** As a small-format retail store owner, I want to ask questions about my inventory in Hindi or English, so that I can get insights in my preferred language.

#### Acceptance Criteria

1. THE Vyapaar_Copilot SHALL provide a chat interface that accepts queries in both Hindi and English
2. WHEN a user asks a question, THE Vyapaar_Copilot SHALL use Bedrock to generate a response grounded in the user's actual inventory data
3. WHEN generating responses, THE Vyapaar_Copilot SHALL cite specific data sources (e.g., "Based on your stock levels from January 15...")
4. WHEN a query cannot be answered from available data, THE Vyapaar_Copilot SHALL explicitly state the limitation rather than hallucinating information
5. THE Vyapaar_Copilot SHALL detect the language of the user's query and respond in the same language

### Requirement 10: Responsible AI Guardrails

**User Story:** As a small-format retail store owner, I want to trust that the system provides accurate information without making up numbers, so that I can make reliable business decisions.

#### Acceptance Criteria

1. THE Vyapaar_Copilot SHALL use Bedrock guardrails to prevent hallucinated numerical values in chat responses
2. WHEN generating any numerical recommendation, THE Vyapaar_Copilot SHALL compute it using deterministic code rather than LLM generation
3. WHEN displaying AI-extracted data, THE Vyapaar_Copilot SHALL always show confidence scores to indicate reliability
4. THE Vyapaar_Copilot SHALL log all AI interactions for audit and debugging purposes
5. WHEN confidence scores are below acceptable thresholds, THE Vyapaar_Copilot SHALL require human verification before persisting data

### Requirement 11: Data Persistence and History

**User Story:** As a small-format retail store owner, I want my inventory data to be saved reliably, so that I can track trends over time and recover from any issues.

#### Acceptance Criteria

1. THE Vyapaar_Copilot SHALL persist all stock levels, purchase events, and reorder decisions to a SQLite database
2. WHEN data is written to the database, THE Vyapaar_Copilot SHALL ensure transactional consistency
3. THE Vyapaar_Copilot SHALL maintain at least 90 days of historical data for trend analysis
4. WHEN a user requests historical data, THE Vyapaar_Copilot SHALL retrieve and display it within 2 seconds
5. THE Vyapaar_Copilot SHALL provide database backup functionality for data recovery

### Requirement 12: Web User Interface

**User Story:** As a small-format retail store owner, I want a simple web interface to interact with the system, so that I can access it from my phone or computer without installing apps.

#### Acceptance Criteria

1. THE Vyapaar_Copilot SHALL provide a web-based user interface accessible via standard browsers
2. WHEN a user accesses the interface, THE Vyapaar_Copilot SHALL display a dashboard with current stock status and reorder recommendations
3. THE Vyapaar_Copilot SHALL provide navigation to access Pulse Mode, WhatsApp Mode, POS Mode, and the chat interface
4. THE Vyapaar_Copilot SHALL render correctly on mobile devices with screen widths down to 360px
5. WHEN a user performs an action, THE Vyapaar_Copilot SHALL provide immediate visual feedback (loading indicators, success messages)

## Success Metrics & Impact

### Technical Performance Metrics
1. **Extraction Accuracy**: >85% accuracy for WhatsApp message parsing (measured against manually labeled test set)
2. **Confidence Calibration**: Confidence scores correlate with actual accuracy (±10% margin)
3. **Response Grounding**: 100% of chat responses cite specific data sources or acknowledge data limitations
4. **Multi-Store Type Validation**: System performs effectively across all three store types (kirana, mini-mart, small supermarket)
5. **System Latency**: <2 seconds for reorder cart generation, <3 seconds for AI extraction

### Business Impact Metrics (Hypotheses to Validate)
1. **Stockout Prevention**: Target 30% reduction in stockouts compared to manual inventory management
   - **Measurement**: Track stockout incidents before/after system adoption
2. **Time Savings**: Reduce daily inventory management time from 30 minutes to <5 minutes
   - **Measurement**: User-reported time tracking
3. **Working Capital Optimization**: Target 20% reduction in dead stock through better reorder timing
   - **Measurement**: Track dead stock value before/after
4. **User Adoption**: Target 80% of test users continue using the system after initial trial period
   - **Measurement**: 30-day retention rate
5. **User Satisfaction**: Target NPS >50
   - **Measurement**: Post-trial surveys

### Scale & Reach (Impact Scoring)
1. **Addressable Market**: 
   - ~12 million small-format retail stores in India (industry research: Nielsen, IBEF)
   - Includes kirana shops, mini-marts, and small supermarkets

2. **Measurable Impact per Store** (to be validated):
   - Stockout incident reduction (count)
   - Time saved per day (minutes)
   - Dead stock value reduction (₹)
   - Pulse completion rate (%)

3. **Ecosystem Benefits**:
   - **FMCG Brands**: Better shelf availability data, reduced stockouts at retail
   - **Distributors**: More efficient retailer ordering, reduced emergency deliveries
   - **Customers**: Fewer stockouts, better product availability

4. **Social Impact**:
   - Empowers small business owners with enterprise-grade decision support
   - Reduces financial stress from poor inventory decisions
   - Enables data-driven growth for underserved retail segment

## Demo Flow (2-3 Minutes)

This demo showcases the same product (Tata Salt 1kg) across three different store types to demonstrate how Vyapaar Copilot adapts to varying data maturity levels.

### Demo Product: Tata Salt 1kg
- Common across all store types
- High-velocity item with frequent reorders
- Multiple name variants for normalization demo

### Flow 1: Kirana Shop (Pulse Mode)
**Persona**: Ramesh, runs a 300 sq ft kirana shop in Pune, no POS system

1. **Onboarding** (15 sec)
   - Select store type: "Kirana Shop"
   - System configures: 50 tracked SKUs, 5-7 day cover, 2-3 day lead time

2. **Daily Stock Check** (30 sec)
   - Open Pulse Mode
   - Scroll through 10 products
   - Mark Tata Salt 1kg: quantity bucket = 1 (low stock)
   - Mark 3 other products with various buckets
   - Submit → Data saved

3. **View Reorder Cart** (45 sec)
   - System shows: "Tata Salt 1kg - Order 15 packets (HIGH urgency, 0.85 confidence)"
   - Explanation: "Current stock: 1 packet. Avg consumption: 5 packets/day. Will run out in <1 day."
   - Click "Generate Order Message"
   - Copy WhatsApp message in Hindi: "नमस्ते, कृपया भेजें: टाटा नमक 1kg - 15 पैकेट"

4. **Chat Query** (30 sec)
   - Ask in Hindi: "मेरे पास कौन से प्रोडक्ट कम हो रहे हैं?"
   - Response: "आपके स्टॉक में 3 प्रोडक्ट कम हैं (15 फरवरी के डेटा के अनुसार): 1. टाटा नमक 1kg - केवल 1 पैकेट..."

### Flow 2: Mini-Mart (WhatsApp Mode)
**Persona**: Priya, runs a 800 sq ft mini-mart in Bangalore, uses WhatsApp for supplier orders

1. **Onboarding** (15 sec)
   - Select store type: "Mini-Mart"
   - System configures: 80 tracked SKUs, 7-10 day cover, 3-5 day lead time

2. **WhatsApp Purchase Upload** (45 sec)
   - Navigate to WhatsApp Mode
   - Upload screenshot of supplier message: "Delivered: 20 Tata Salt 1kg @ ₹18/pc, 10 Aashirvaad Atta 5kg @ ₹240/bag"
   - System extracts:
     - Tata Salt 1kg: 20 packets, ₹18 each (confidence: 0.92)
     - Aashirvaad Atta 5kg: 10 bags, ₹240 each (confidence: 0.89)
   - Confirm extraction → Purchase events recorded

3. **View Reorder Cart** (45 sec)
   - System shows: "Tata Salt 1kg - Order 25 packets (MEDIUM urgency, 0.88 confidence)"
   - Explanation: "Current stock: 8 packets. Avg consumption: 3 packets/day. Will run out in 2.7 days."
   - Adjust quantity to 30 (user override)
   - Generate order message in English

4. **Chat Query** (15 sec)
   - Ask: "Why should I order salt today?"
   - Response: "Based on your stock level from Feb 14 (8 packets) and average consumption (3 packets/day), you'll run out in 2.7 days. With 3-day lead time, ordering today prevents stockout."

### Flow 3: Small Supermarket (POS Mode)
**Persona**: Amit, manages 2 small supermarkets in Delhi, has POS system with daily exports

1. **Onboarding** (15 sec)
   - Select store type: "Small Supermarket"
   - System configures: 200 tracked SKUs, 10-14 day cover, 5-7 day lead time

2. **CSV Upload** (30 sec)
   - Navigate to POS Mode
   - Upload CSV file (150 rows of yesterday's purchases)
   - System validates and imports:
     - 148 records imported successfully
     - 2 records flagged for review (missing product mapping)
   - Summary shows: Tata Salt 1kg - 45 packets purchased @ ₹17.50/pc

3. **View Reorder Cart** (60 sec)
   - System shows: "Tata Salt 1kg - Order 120 packets (LOW urgency, 0.92 confidence)"
   - Explanation: "Current stock: 85 packets. Avg consumption: 8 packets/day. Will run out in 10.6 days."
   - View historical trend chart (last 30 days consumption)
   - Generate bulk order message for 15 products

4. **Multi-Store Dashboard** (15 sec)
   - Switch between Store 1 and Store 2
   - Compare Tata Salt stock levels: Store 1 (85 packets), Store 2 (42 packets)
   - Consolidated reorder recommendation across both stores

### Key Demo Takeaways
- Same product, three different data maturity levels
- AI adapts to available data: manual buckets → WhatsApp extraction → POS CSV
- Consistent deterministic logic with varying confidence based on data quality
- Multilingual support (Hindi for kirana, English for supermarket)
- Grounded explanations cite specific data sources

## Business Model and Go-to-Market

### Market Opportunity & Sizing

**Addressable Market**: India has approximately 12 million grocery retail outlets (industry research from Nielsen, IBEF reports cite ~13 million kirana stores).

**Market Segments**:
- Kirana shops: Majority of small-format retail
- Mini-marts/convenience stores: Growing urban segment
- Small supermarkets (1-3 outlets): Premium segment

**Illustrative ARR Formula** (for business planning):
```
ARR = adopting_stores × ARPU × 12
```

**Example Scenario** (assumptions to be validated):
- Assume 10,000 stores adopt in Year 1
- Average ARPU: ₹500/month (blended across tiers)
- Illustrative ARR: 10,000 × ₹500 × 12 = ₹6 Cr

This is a planning scenario with explicit assumptions. Actual adoption rates, pricing, and revenue will depend on market validation, competitive dynamics, and execution.

### Tiered Pricing Strategy

1. **Kirana Plan** (₹299/month or ₹2,999/year - 17% discount)
   - Up to 50 tracked SKUs
   - Pulse Mode + WhatsApp Mode
   - Single user
   - Hindi + English support
   - Email support
   - **Target**: Kirana shops across India

2. **Mini-Mart Plan** (₹799/month or ₹7,999/year - 17% discount)
   - Up to 100 tracked SKUs
   - All modes (Pulse + WhatsApp + POS)
   - Up to 3 users
   - Priority support
   - Basic analytics dashboard
   - **Target**: Mini-marts and convenience stores

3. **Small Supermarket Plan** (₹1,999/month per outlet or ₹19,999/year - 17% discount)
   - Up to 500 tracked SKUs per outlet
   - Multi-store dashboard
   - Unlimited users
   - API access for integration
   - Advanced analytics and forecasting
   - Dedicated account manager
   - **Target**: Small supermarket chains

### Revenue Model & Unit Economics

**Illustrative Unit Economics** (assumptions to be validated):

**Customer Acquisition Cost (CAC)** (estimated):
- Direct digital: ₹500-800 per customer (WhatsApp campaigns, content marketing)
- Partner channel: ₹300-500 per customer (revenue share with POS/distributor partners)
- Blended CAC target: ₹600

**Lifetime Value (LTV)** (estimated, assumes retention):
- Kirana: ₹2,999/year × 3 years retention = ₹8,997
- Mini-Mart: ₹7,999/year × 4 years retention = ₹31,996
- Small Supermarket: ₹19,999/year × 5 years retention = ₹99,995

**Gross Margins** (estimated): 85-90% (SaaS model, AWS infrastructure costs ~10-15%)

These are planning estimates. Actual CAC, LTV, and margins will depend on execution, market conditions, and operational efficiency.

### Go-to-Market Channels

1. **POS/Billing Software Partners** (30% of customer acquisition)
   - Integrate with existing POS providers (Marg ERP, Vyapar, Tally, Zoho Books)
   - Offer as add-on module in their app stores
   - Revenue share: 20% to partner, 80% to Vyapaar Copilot
   - **Advantage**: Access to existing user base, trusted distribution channel

2. **Distributor/Wholesaler Networks** (25% of customer acquisition)
   - Partner with FMCG distributors who serve small retailers
   - Offer as value-added service to improve retailer efficiency
   - Reduces distributor's stockout complaints and emergency deliveries
   - **Advantage**: Distributors incentivized to improve retailer operations

3. **FMCG Field Sales Networks** (20% of customer acquisition)
   - Partner with brands (HUL, ITC, Parle, Britannia) whose field teams visit stores daily
   - Field teams help onboard stores during routine visits
   - Brands benefit from better shelf availability data and reduced stockouts
   - **Advantage**: Daily touchpoints, trusted brand relationships

4. **Digital Payment Platforms** (15% of customer acquisition)
   - Partner with Paytm, PhonePe, Google Pay for merchant services
   - Cross-sell to existing merchant base through in-app promotions
   - Leverage payment data for enhanced insights (with consent)
   - **Advantage**: Large merchant base, digital-first users

5. **Direct Digital Marketing** (10% of customer acquisition)
   - WhatsApp Business API campaigns targeting retail communities
   - Regional language content marketing (Hindi, Tamil, Telugu, Bengali)
   - Influencer partnerships with retail community leaders and associations
   - SEO/SEM for "inventory management for kirana" searches
   - **Advantage**: Scalable, measurable, direct customer relationships

### Sustainability & Growth Strategy

**Year 1: Product-Market Fit** (target: 10,000 stores)
- Focus on kirana and mini-mart segments
- Pilot partnerships with 2-3 POS providers
- Refine AI models based on real-world usage
- Target: 80%+ retention rate

**Year 2: Channel Expansion** (target: 50,000 stores)
- Scale POS partnerships to 10+ providers
- Launch distributor partnership program
- Add small supermarket features (multi-store, API)
- Expand to 5 regional languages

**Year 3: Market Leadership** (target: 200,000 stores)
- FMCG brand partnerships for data insights
- Payment platform integrations
- International expansion (Bangladesh, Sri Lanka, Indonesia)
- Enterprise features for chains (10+ outlets)

**Competitive Advantages**:
1. **Progressive Capture**: Works without POS—captures market others can't serve
2. **Integration Ecosystem**: Partnerships with POS, distributors, FMCG brands
3. **Multilingual AI**: Trained on Indian retail context
4. **Data Network Effects**: More stores → better product normalization → better recommendations

## Responsible AI Considerations

1. **No Hallucinated Numbers**: All numerical recommendations (quantities, prices, predictions) must be computed deterministically, never generated by LLMs
2. **Transparency**: All AI-extracted data must display confidence scores; low-confidence extractions require human verification
3. **Grounded Responses**: Chat responses must cite specific data sources and explicitly acknowledge when data is unavailable
4. **Audit Trail**: All AI interactions must be logged for debugging and accountability
5. **Guardrails**: Bedrock guardrails must prevent generation of fabricated business data
6. **Language Fairness**: System must perform equally well in Hindi and English
7. **Error Handling**: System must fail gracefully and provide clear error messages rather than incorrect data
8. **User Control**: Users must be able to override AI recommendations and corrections

## Hackathon Alignment

### Ideation & Creativity (30%)
**Novelty**: 
- First inventory solution that works without POS infrastructure (progressive capture)
- Hybrid AI-deterministic architecture prevents hallucination while maintaining flexibility
- Multimodal extraction from real-world WhatsApp communication (text/image/voice)

**Uniqueness**: 
- Only solution addressing 10M+ kirana shops with zero digital infrastructure
- Store type adaptation (kirana/mini-mart/supermarket) vs one-size-fits-all
- Bharat-first multilingual design, not just English translation

**Problem Alignment**: 
- Directly addresses "AI for Retail, Commerce & Market Intelligence" track
- Transforms unstructured retail data into actionable intelligence
- Enhances decision-making, efficiency, and user experience for underserved segment

### Technical Aptness & Feasibility (30%)
**Plausible Architecture**: 
- Proven tech stack (FastAPI, SQLite, Bedrock, React)
- Clear separation: AI for extraction, deterministic for calculations
- Scalability path: SQLite → PostgreSQL → Aurora

**Constraints Addressed**: 
- Bedrock rate limits → batching, caching, queuing
- Image quality → preprocessing, confidence thresholds
- Hindi support → Claude 3 Sonnet, extensive testing
- Offline support → PWA, local caching

**Demo-Ready**: 
- Live Bedrock calls for extraction and chat
- Pre-seeded sample data for 3 store types
- 2-3 minute demo flow with expected screens
- <30 minutes setup time

### Impact (20%)
**Beneficiaries**: 
- ~12 million small-format retail stores in India (industry research: Nielsen, IBEF)
- FMCG brands, distributors, end customers (ecosystem benefits)

**Measurable Improvement** (hypotheses to validate): 
- Target: 30% stockout reduction through systematic tracking
- Target: 25 minutes/day time savings (30 min → 5 min)
- Target: 20% dead stock reduction through better reorder timing
- Measurable metrics: stockout incidents, dead stock value, time saved/day, pulse completion rate

**Scale**: 
- Addressable market: ~12 million stores
- Illustrative ARR formula: adopting_stores × ARPU × 12
- Example: 10,000 stores × ₹500/month × 12 = ₹6 Cr ARR (Year 1 scenario)

### Business Feasibility (20%)
**GTM Strategy**: 
- 5 clear channels: POS partners (30%), distributors (25%), FMCG field sales (20%), payment platforms (15%), direct digital (10%)
- Revenue share partnerships reduce CAC

**Pricing**: 
- Tiered: ₹299/₹799/₹1,999 per month
- 17% discount for annual plans
- Value proposition: Systematic tracking reduces stockouts and saves time

**Sustainability**: 
- Estimated 85-90% gross margins (SaaS model)
- Clear 3-year growth path: 10K → 50K → 200K stores (targets)
- Data network effects create competitive advantage
