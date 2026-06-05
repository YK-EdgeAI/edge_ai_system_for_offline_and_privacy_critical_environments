# Power Plant Incident Correlation using Edge LLM
## Prototype Architecture for Offline & Privacy-Critical Energy Environments

---

# Objective

Build an offline-capable Edge AI prototype that helps power plant operators:

- Correlate multiple alarms and operational events
- Understand probable root causes
- Summarize incidents automatically
- Reduce alarm fatigue
- Support faster operational decisions

The prototype combines:
- Traditional ML/event analytics
- Retrieval systems (RAG)
- Edge-hosted LLM reasoning

without requiring cloud connectivity.

---

# 1. High-Level Architecture

```text
┌──────────────────────────────────────────────┐
│              Data Sources Layer              │
├──────────────────────────────────────────────┤
│ SCADA Events │ Sensor Streams │ OT Logs      │
│ Maintenance Logs │ SOPs │ Incident Reports   │
└──────────────────────────────────────────────┘
                     ↓
┌──────────────────────────────────────────────┐
│         Event Processing Layer               │
├──────────────────────────────────────────────┤
│ Event Parsing                                │
│ Time Synchronization                         │
│ Alarm Normalization                          │
│ Basic Anomaly Detection (ML/Rules)           │
└──────────────────────────────────────────────┘
                     ↓
┌──────────────────────────────────────────────┐
│          Context Retrieval Layer             │
├──────────────────────────────────────────────┤
│ Vector Database                              │
│ Document Embeddings                          │
│ Retrieval-Augmented Generation (RAG)         │
└──────────────────────────────────────────────┘
                     ↓
┌──────────────────────────────────────────────┐
│              Edge LLM Layer                  │
├──────────────────────────────────────────────┤
│ Local LLM Inference                          │
│ Incident Correlation                         │
│ Root Cause Reasoning                         │
│ Natural Language Summarization               │
│ Action Recommendation                        │
└──────────────────────────────────────────────┘
                     ↓
┌──────────────────────────────────────────────┐
│          Operator Experience Layer           │
├──────────────────────────────────────────────┤
│ Incident Dashboard                           │
│ Chat Interface                               │
│ Alert Summary Panel                          │
│ Recommended Actions                          │
└──────────────────────────────────────────────┘