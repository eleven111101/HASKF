# HASKF — Hypergraph-Based ADAS Safety Knowledge Framework

> **A multimodal safety intelligence framework for Advanced Driver Assistance Systems (ADAS)**

<p align="center">
  <b>Developed and maintained by <i>GRAVITY ~ AI</i></b>
</p>

---

## Overview

**HASKF (Hypergraph-Based ADAS Safety Knowledge Framework)** is a research framework that converts multimodal accident data into structured safety knowledge for validating **Advanced Driver Assistance Systems (ADAS)**.

Conventional graph-based methods capture only pairwise relationships between entities, which limits their ability to represent the complexity of real-world traffic accidents. HASKF instead uses **hypergraphs**, where a single hyperedge can connect many entities at once — weather, road environment, infrastructure, vehicles, vulnerable road users, driver behavior, and system failures — preserving the full context of each accident event rather than fragmenting it into isolated pairs.

The framework ingests and fuses information from:

- Accident reports
- Traffic images
- Driving videos
- Public safety scenario datasets
- Simulation data

and uses this fused knowledge to discover hazardous patterns, predict risk, analyze root causes, and generate realistic scenarios for ADAS validation.

---

## Framework Architecture

> *Insert overall framework architecture diagram here.*

```
docs/images/framework.png
```

---

## Pipeline Workflow

> *Insert processing pipeline diagram here.*

```
docs/images/pipeline.png
```

---

## Repository Structure

```
HASKF/
│
├── data/
│   ├── reports/
│   ├── images/
│   ├── videos/
│   └── scenarios/
│
├── ontology/
│
├── extraction/
│   ├── nlp/
│   ├── image/
│   └── video/
│
├── hypergraph/
│
├── analytics/
│   ├── pattern_mining/
│   ├── risk_prediction/
│   └── root_cause/
│
├── scenario_generation/
│
├── visualization/
│
├── docs/
│   ├── images/
│   └── paper/
│
├── notebooks/
│
└── README.md
```

---

## Objectives

HASKF is designed to:

- Build a unified, multimodal safety knowledge base
- Extract structured information from heterogeneous accident data
- Represent accident events as hypergraphs rather than simple graphs
- Discover recurring hazardous driving patterns
- Predict risk under novel combinations of driving conditions
- Explain the root causes of accidents
- Generate realistic scenarios for ADAS validation
- Improve test coverage for autonomous driving systems

---

## Data Sources

HASKF accepts and processes four complementary data modalities.

### 1. Accident Reports

Textual reports describing the sequence of events leading to an accident. Typical fields include weather, time of day, road type, driver actions, vehicle failures, and outcomes. These are processed with **Natural Language Processing (NLP)**.

### 2. Images

Traffic images provide spatial context for an accident scene. Extracted elements typically include vehicles, pedestrians, motorcycles, traffic signs, lane markings, road surface conditions, and weather conditions.

### 3. Videos

Driving videos capture temporal behavior. Extracted events typically include lane changes, braking, vehicle trajectories, traffic density, driver responses, and pedestrian crossings.

### 4. Scenario Library

A curated library of validated scenarios drawn from public datasets and safety investigations. Each scenario specifies environment, road geometry, weather, actors, failure type, and risk level.

---

## Processing Pipeline

| Step | Stage | Description |
|------|-------|-------------|
| 1 | **Data Collection** | Gather multimodal accident information from all supported sources. |
| 2 | **Information Extraction** | Extract entities and events using NLP, image analysis, and video analysis. |
| 3 | **Structured Event Construction** | Convert extracted information into structured driving events. |
| 4 | **Safety Ontology Mapping** | Map raw entities onto a standardized safety ontology. |
| 5 | **Hypergraph Construction** | Represent each accident event as a hyperedge. |
| 6 | **Safety Analytics** | Run pattern mining, risk prediction, and root cause analysis. |
| 7 | **Scenario Generation** | Produce realistic scenarios for ADAS validation. |
| 8 | **ADAS Test Cases** | Package scenarios into simulation-ready test cases. |

---

## Hypergraph Representation

A standard graph can only express one relationship at a time:

```
Car ---- Rain
```

A hypergraph, by contrast, can bind an arbitrary number of entities into a single hyperedge — capturing an entire accident context as one unit:

```
{
  Rain,
  Night,
  Construction Zone,
  Motorcycle,
  Temporary Lane,
  Emergency Braking
}
```

This structure enables richer reasoning across multiple simultaneous factors and supports more accurate downstream safety analysis than pairwise graph models.

---

## Safety Ontology

Extracted information is standardized into the following concept categories:

| Category | Examples |
|----------|----------|
| **Environmental** | Rain, Fog, Snow, Night, Day |
| **Road** | Highway, Urban Road, Rural Road, Intersection, Construction Zone |
| **Road Users** | Car, Truck, Motorcycle, Bicycle, Pedestrian |
| **Driving Behavior** | Lane Change, Overtaking, Braking, Turning, Driver Takeover |
| **ADAS Events** | Lane Keeping Failure, Collision Warning, Emergency Braking, Object Detection Failure |

---

## Safety Analytics

### Pattern Mining

Identifies recurring combinations of hazardous conditions. For example:

```
Rain + Night + Construction Zone  →  frequently precedes  →  Lane Departure
```

### Risk Prediction

Estimates the likelihood of hazardous outcomes under new or unseen combinations of driving conditions.

### Root Cause Analysis

Identifies the dominant contributing factors behind an accident, supporting explainability.

### Scenario Generation

Automatically synthesizes ADAS validation scenarios from mined patterns, for example:

```
Weather:          Heavy Rain
Time:             Night
Road:             Construction Zone
Traffic:          Motorcycle
Expected Hazard:  Lane Detection Failure
```

---

## Technology Stack

| Component | Purpose |
|-----------|---------|
| Python | Core implementation |
| NLP | Text information extraction |
| Computer Vision | Image understanding |
| Video Processing | Temporal event analysis |
| Hypergraph | Knowledge representation |
| Ontology | Semantic modeling |
| Machine Learning | Risk prediction |
| Visualization | Knowledge exploration |

---

## Acronyms

| Acronym | Meaning |
|---------|---------|
| **HASKF** | Hypergraph-Based ADAS Safety Knowledge Framework |
| **ADAS** | Advanced Driver Assistance Systems |
| **AI** | Artificial Intelligence |
| **NLP** | Natural Language Processing |
| **CV** | Computer Vision |
| **HG** | Hypergraph |
| **KB** | Knowledge Base |
| **HGNN** | Hypergraph Neural Network |
| **LLM** | Large Language Model |
| **PoC** | Proof of Concept |

---

## Future Enhancements

- Transformer-based NLP
- Advanced object detection
- Video understanding models
- Hypergraph Neural Networks (HGNNs)
- Explainable AI
- Simulation integration
- Digital twin support
- Real-time risk assessment

---

## Citation

If you use this repository in your research, please cite the corresponding publication once it becomes available.

---

## License

Released under the MIT License.

---

## Maintainer

**GRAVITY ~ AI**

Research focus areas:

- Artificial Intelligence
- Knowledge Graphs & Hypergraphs
- Autonomous Driving
- Computer Vision
- Intelligent Transportation Systems
- ADAS Safety
- Machine Learning

---

<p align="center">
<b>HASKF</b><br>
Hypergraph-Based ADAS Safety Knowledge Framework<br><br>
Developed with ❤️ by <b>GRAVITY ~ AI</b>
</p>