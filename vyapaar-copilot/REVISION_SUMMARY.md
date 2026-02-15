# Vyapaar Copilot Spec Revision Summary

## Overview
Revised requirements.md and design.md to remove unverifiable "pitch-deck" claims and replace with defensible, judge-safe content suitable for hackathon evaluation.

## Critical Changes Made

### 1. Executive Summary (requirements.md)

**REMOVED:**
- "12.5M stores" (unverifiable exact number)
- "₹15k–₹60k/month loss" (unverifiable claim)
- "₹6,120 Cr TAM" (unverifiable market sizing)
- "50x ROI" (unverifiable value claim)
- "85-90% gross margins, 15:1 to 167:1 LTV:CAC ratios" (unverifiable unit economics)

**REPLACED WITH:**
- "~12 million grocery retail outlets (industry research)" with citation to Nielsen, IBEF
- Removed specific loss amounts
- Added "Illustrative Impact Scenario" section with:
  * Clear formula: `recovered_sales = monthly_sales × stockout_loss_% × reduction_%`
  * Example with explicit assumptions labeled
  * Disclaimer: "This is an illustrative scenario with explicit assumptions"
- Changed "Impact" to "Impact Hypothesis (to be validated through pilot testing)"
- Measurable metrics: stockout incidents, dead stock value, time saved/day, pulse completion rate

### 2. Market Sizing Section (requirements.md)

**REMOVED:**
- Exact segment splits (10M kirana, 2M mini-marts, 500K supermarkets)
- TAM calculation: "₹6,120 Cr/year (~$750M USD)"
- SAM and SOM projections with exact percentages

**REPLACED WITH:**
- Transparent formula: `ARR = adopting_stores × ARPU × 12`
- ONE illustrative example clearly labeled as assumptions
- "Illustrative ARR Formula (for business planning)"
- Disclaimer: "This is a planning scenario with explicit assumptions"

### 3. Impact Metrics (requirements.md)

**FIXED:**
- Corrected formula to: `recovered_sales = monthly_sales × stockout_loss_% × reduction_%`
- Removed incorrect calculations
- Changed to "Business Impact Metrics (Hypotheses to Validate)"
- Kept measurable metrics: stockout incidents, dead stock value, time saved/day, pulse completion rate
- Removed specific revenue claims (₹15k-60k/month)

### 4. Pricing Strategy (requirements.md)

**REMOVED:**
- "10M+ kirana shops" target claims
- "50x ROI" value propositions
- Specific revenue impact claims (₹15k/month, ₹30k/month, ₹60k/month)
- "₹40,000 freed capital" claims

**REPLACED WITH:**
- Simple target descriptions without numbers
- Removed all ROI and value prop claims
- Kept pricing tiers intact

### 5. Unit Economics (requirements.md)

**REMOVED:**
- "LTV:CAC Ratios: 15:1, 53:1, 167:1"

**REPLACED WITH:**
- "Illustrative Unit Economics (assumptions to be validated)"
- Added "(estimated)" labels to all numbers
- Disclaimer: "These are planning estimates. Actual CAC, LTV, and margins will depend on execution"

### 6. Pulse Mode Realism (design.md)

**ADDED CRITICAL CLARIFICATIONS:**
```
CRITICAL - Pulse Mode Limitations:
- Pulse buckets (0/1/2/3/4+) are NOT exact quantities
- They indicate stock levels: 0=out, 1=low, 2=medium, 3=good, 4+=high
- Consumption velocity REQUIRES actual purchase events (WhatsApp/POS data)
- In Pulse-only mode (no purchase history):
  * System uses "top-up to target bucket" logic
  * Recommendations are conservative with LOW confidence
  * Output: "top-up to bucket 3+" OR quantity range with LOW confidence
- Exact reorder quantities ONLY possible when purchase events exist
```

**UPDATED CODE COMMENTS:**
- Changed "Top up to reasonable level" to "Conservative estimate for demo"
- Added: "NEVER claim exact per-SKU quantities from Pulse-only data"
- Added: "Output: 'Top-up to bucket 3+' OR 'Order 8-12 units (LOW confidence)'"

### 7. Technical Accuracy (design.md)

**ENCRYPTION FIX:**
- **OLD**: "Data encrypted at rest in SQLite database"
- **NEW**: "Data encrypted at rest via managed storage/disk encryption in deployment environment; SQLite used for demo/development; production deployments use managed database services with encryption"

**DATA MODEL FIX:**
- Added `store_id` field to `ReorderRecommendation` class (was missing but referenced in validator)
- Updated database schema to include `store_id` foreign key in `reorder_recommendations` table

### 8. Market Context (design.md)

**UPDATED:**
- Changed "India has approximately 12 million grocery outlets and ~13 million kirana stores (source: Nielsen, IBEF reports)"
- To: "India has approximately 12 million grocery retail outlets according to industry research (Nielsen, IBEF reports cite ~13 million kirana stores)"

## Judge-Safe Claims Checklist

### ✅ FACTS (Defensible)
- [x] Multimodal pipeline (Voice → Transcribe → Bedrock, Image → Textract → Bedrock)
- [x] Numeric Integrity Validator exists
- [x] "LLM never calculates quantities" rule
- [x] Hybrid AI-deterministic architecture
- [x] Progressive capture modes (Pulse/WhatsApp/POS)
- [x] Store type adaptation with configurable parameters
- [x] ~12 million stores (cited from industry research)
- [x] Proven tech stack (FastAPI, SQLite, Bedrock, React)

### ⚠️ ASSUMPTIONS (Clearly Labeled)
- [x] Stockout loss percentages (10-15%) - labeled as "industry estimates"
- [x] 30% reduction target - labeled as "hypothesis to validate"
- [x] Time savings (30 min → 5 min) - labeled as "target"
- [x] Unit economics (CAC, LTV, margins) - labeled as "estimated" and "to be validated"
- [x] Market sizing (ARR calculations) - labeled as "illustrative scenario"
- [x] Impact per store - labeled as "to be validated"

### ❌ REMOVED (Unverifiable)
- [x] Exact market segment splits (10M/2M/500K)
- [x] Specific revenue impact claims (₹15k-60k/month)
- [x] TAM/SAM/SOM with exact numbers
- [x] ROI claims (50x)
- [x] LTV:CAC ratios (15:1, 53:1, 167:1)
- [x] Margin improvement claims (2-3%)
- [x] Freed capital claims (₹40,000)

## Key Principles Applied

1. **Transparency**: All assumptions explicitly labeled
2. **Formulas Over Claims**: Show calculation methods, not just results
3. **Measurable Metrics**: Focus on countable things (incidents, time, completion rate)
4. **Hypotheses Not Facts**: Frame impact as "to be validated"
5. **Industry Citations**: Reference sources for market data
6. **Technical Honesty**: Clarify Pulse Mode limitations
7. **Conservative Language**: "Target", "estimated", "illustrative", "hypothesis"

## What Remains Strong

1. **Technical Innovation**: Multimodal pipeline, hybrid architecture, progressive capture
2. **Problem-Solution Fit**: Clear problem statement with technical solution
3. **Feasibility**: Proven tech stack, demo-ready approach
4. **Measurability**: Clear metrics for validation
5. **Market Opportunity**: Cited industry research for addressable market
6. **GTM Strategy**: Clear distribution channels
7. **Responsible AI**: Guardrails, grounding, confidence scores

## Recommendation for Demo

When presenting to judges:
1. Lead with technical innovation (multimodal, hybrid AI-deterministic)
2. Show live demo with Bedrock calls
3. Emphasize measurable metrics (not revenue claims)
4. Present impact as "hypotheses to validate through pilot"
5. Use illustrative scenarios with explicit assumptions
6. Focus on problem-solution fit and technical feasibility
7. Highlight responsible AI approach (no hallucinated numbers)

## Files Modified

1. `.kiro/specs/vyapaar-copilot/requirements.md` - Executive summary, market sizing, impact metrics, pricing, unit economics
2. `.kiro/specs/vyapaar-copilot/design.md` - Market context, encryption description, Pulse Mode algorithm, data models
