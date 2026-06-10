---
layout: default
title: "LLMs+Graphs: Toward Graph-Native, Synergistic AI Systems"
---

[//]: # (# LLMs+Graphs)

<section class="speakers-section" markdown="1">
## Speakers

<div class="speakers-grid">
  <div class="speaker">
    <img src="assets/speakers/khan.jpg" alt="Speaker 6 Name" class="speaker-photo">
    <h3><a href="https://www.cs.bgsu.edu/arijitk" target="_blank">Arijit Khan</a></h3>
    <p>Bowling Green State University</p>
  </div>
  <div class="speaker">
    <img src="assets/speakers/longxu.jpeg" alt="Speaker 6 Name" class="speaker-photo">
    <h3><a href="https://www.comp.hkbu.edu.hk/~cslxsun/" target="_blank">Longxu Sun</a></h3>
    <p>Hong Kong Baptist University</p>
  </div>
  <div class="speaker">
    <img src="assets/speakers/xin.jpg" alt="Speaker 6 Name" class="speaker-photo">
    <h3><a href="https://www.comp.hkbu.edu.hk/~xinhuang/" target="_blank">Xin Huang</a></h3>
    <p>Hong Kong Baptist University</p>
  </div>
</div>
</section>

<div class="tutorial-info-card">
  <p class="tutorial-info-text"><strong>Tutorial Info:</strong> 🗓️ Tuesday, June 9, 2026 · Tutorial 4 · 📍 Room 4, Tai Po II Room, 2/F</p>
</div>

---

## Abstract

<div class="abstract-section">

<p>
Large Language Models (LLMs) have advanced rapidly, but their limitations in structured and multi-hop reasoning underscore the need for graph-native, synergistic artificial intelligence (AI) systems.
Graph-structured data underpins critical applications across social, biological, financial, transportation, web, and knowledge domains, making it essential to understand how LLMs can leverage graph computationforgrounded,context-richinference. 
Three complementary synergies are emerging: LLMs augmented with graph computation for retrieval and reasoning; bidirectional integration between LLMs and knowledge graphs (KGs), where LLMs support KG construction and curation while KGs enforce semantic constraints and factual consistency; and AI agents strengthened by graph algorithms for planning, decision making, and multi-step reasoning. 
In parallel, LLMs introduce new capabilities for graph data management and graph machine learning (ML) through natural language interfaces and hybrid LLM-graph neural network (GNN) pipelines. 
This tutorial synthesizes the algorithms, systems, and design principles driving these converging directions, offering data science and data mining researchers aunified perspective on integrating LLMs,graph data management, graph mining, graph ML, and agentic computation into next-generation graph-native AI systems.
</p>

</div>

---

## Outline & Schedule

<section class="schedule-timeline">
  <h3 class="schedule-session-title">Session 1 (Time: 09:00-10:30, 90 min)</h3>
  <div class="timeline-track">
    <div class="timeline-item">
      <div class="timeline-meta">
        <div class="timeline-time">Time: 09:00-09:20, 20 min</div>
        <div class="timeline-speaker">Xin Huang</div>
        <a class="timeline-slides" href="{{ '/pages/slides' | relative_url }}#slide-1">Slides 1-15</a>
      </div>
      <div class="timeline-node" aria-hidden="true"></div>
      <div class="timeline-content">
        <strong class="timeline-section-title">Sec 1: Introduction</strong>
        <ul class="timeline-subsections">
          <li>1.1 LLMs</li>
          <li>1.2 AI Agents</li>
          <li>1.3 Graph Foundation Models</li>
          <li>1.4 Retrieval-Augmented Generation</li>
          <li>1.5 Knowledge Graphs</li>
        </ul>
      </div>
    </div>
    <div class="timeline-item">
    <div class="timeline-meta">
        <div class="timeline-time">Time: 09:20-09:40, 20 min</div>
        <div class="timeline-speaker">Xin Huang</div>
        <a class="timeline-slides" href="{{ '/pages/slides' | relative_url }}#slide-16">Slides 16-48</a>
      </div>
      <div class="timeline-node" aria-hidden="true"></div>
      <div class="timeline-content">
        <strong class="timeline-section-title">Sec 2: LLMs for Graphs</strong>
        <ul class="timeline-subsections">
          <li>2.1 Graph Understanding
            <ul>
              <li>2.1.1 Graph Computation</li>
            </ul>
          </li>
          <li>2.2 Graph Learning
            <ul>
              <li>2.2.1 LLMs-as-generators</li>
              <li>2.2.2 Unsupervised Graph Representation</li>
              <li>2.2.3 Graph Diffusion Prediction</li>
            </ul>
          </li>
          <li>2.3 Graph Foundational Models</li>
        </ul>
      </div>
    </div>

    <div class="timeline-item">
      <div class="timeline-meta">
        <div class="timeline-time">Time: 09:40-10:00, 20 min</div>
        <div class="timeline-speaker">Longxu Sun</div>
        <a class="timeline-slides" href="{{ '/pages/slides' | relative_url }}#slide-49">Slides 49-65</a>
      </div>
      <div class="timeline-node" aria-hidden="true"></div>
      <div class="timeline-content">
        <strong class="timeline-section-title">Sec 3: Graphs for LLMs</strong>
        <ul class="timeline-subsections">
          <li>3.1 Question-Answering: GraphRAG
            <ul>
              <li>3.1.1 From RAG to GraphRAG</li>
              <li>3.1.2 RAG vs GraphRAG</li>
            </ul>
          </li>
          <li>3.2 Agent Memory: Memory Graph</li>
          <li>3.3 LLM Planning: WorkFlow Graph</li>
          <li>3.4 LLM Selection: GraphRouter</li>
        </ul>
      </div>
    </div>

    <div class="timeline-item">
      <div class="timeline-meta">
        <div class="timeline-time">Time: 10:00-10:20, 20 min</div>
        <div class="timeline-speaker">Arijit Khan</div>
        <a class="timeline-slides" href="{{ '/pages/slides' | relative_url }}#slide-66">Slides 66-111</a>
      </div>
      <div class="timeline-node" aria-hidden="true"></div>
      <div class="timeline-content">
        <strong class="timeline-section-title">Sec 4: Large Language Models &amp; Knowledge Graphs</strong>
        <ul class="timeline-subsections">
          <li>4.1 KGs as background knowledge for LLMs</li>
          <li>4.2 KGs as reasoning guidelines for LLMs</li>
          <li>4.3 KGs as refiners and validators for LLMs</li>
          <li>4.4 LLM+KG for domain-specific applications (e.g., data integration)</li>
        </ul>
      </div>
    </div>

    <div class="timeline-item">
      <div class="timeline-meta">
        <div class="timeline-time">Time: 10:20-10:30, 10 min</div>
        <div class="timeline-speaker">All</div>
        <div class="timeline-slides">Q&A</div>
      </div>
      <div class="timeline-node" aria-hidden="true"></div>
      <div class="timeline-content">
        <strong>Q&A (Session 1)</strong>
      </div>
    </div>
  </div>

  <!-- <div class="timeline-break" role="note" aria-label="Break">
    Break (10:30 AM - 11:00 AM)
  </div> -->

  <h3 class="schedule-session-title">Session 2 (Time: 11:00-12:30, 90 min)</h3>
  <div class="timeline-track">
    

    <div class="timeline-item">
      <div class="timeline-meta">
        <div class="timeline-time">Time: 11:00-11:20, 20 min</div>
        <div class="timeline-speaker">Longxu Sun</div>
        <a class="timeline-slides" href="{{ '/pages/slides' | relative_url }}#slide-112">Slides 112-123</a>
      </div>
      <div class="timeline-node" aria-hidden="true"></div>
      <div class="timeline-content">
        <strong class="timeline-section-title">Sec 5: LLMs for Knowledge Graphs</strong>
        <ul class="timeline-subsections">
          <li>5.1 Knowledge Graph Link Prediction</li>
          <li>5.2 Knowledge Graph Embedding</li>
          <li>5.3 Knowledge Graph Construction</li>
          <li>5.4 Knowledge Graph Completion</li>
        </ul>
      </div>
    </div>

    <div class="timeline-item">
      <div class="timeline-meta">
        <div class="timeline-time">Time: 11:20-11:40, 20 min</div>
        <div class="timeline-speaker">Arijit Khan</div>
        <a class="timeline-slides" href="{{ '/pages/slides' | relative_url }}#slide-124">Slides 124-163</a>
      </div>
      <div class="timeline-node" aria-hidden="true"></div>
      <div class="timeline-content">
        <strong class="timeline-section-title">Sec 6: AI Agents</strong>
        <ul class="timeline-subsections">
          <li>6.1 Agent Interaction With Task Planning Graphs</li>
          <li>6.2 Agent Interaction With Task Execution Graphs</li>
          <li>6.3 Agent Interaction With Memory Graphs</li>
          <li>6.4 Multi-Agent Coordination Graphs</li>
        </ul>
      </div>
    </div>

    <div class="timeline-item">
      <div class="timeline-meta">
        <div class="timeline-time">Time: 11:40-12:00, 20 min</div>
        <div class="timeline-speaker">Longxu Sun</div>
        <a class="timeline-slides" href="{{ '/pages/slides' | relative_url }}#slide-164">Slides 164-177</a>
      </div>
      <div class="timeline-node" aria-hidden="true"></div>
      <div class="timeline-content">
        <strong class="timeline-section-title">Sec 7: AI Agents for Graphs</strong>
        <ul class="timeline-subsections">
          <li>7.1 General Graph Problem Solving</li>
          <li>7.2 Tool-Augmented Graph Algorithmic Reasoning</li>
          <li>7.3 Domain-Specific KG Construction</li>
          <li>7.4 Community Search</li>
        </ul>
      </div>
    </div>

    <div class="timeline-item">
      <div class="timeline-meta">
        <div class="timeline-time">Time: 12:00-12:20, 20 min</div>
        <div class="timeline-speaker">Arijit Khan</div>
        <a class="timeline-slides" href="{{ '/pages/slides' | relative_url }}#slide-178">Slides 178-185</a>
      </div>
      <div class="timeline-node" aria-hidden="true"></div>
      <div class="timeline-content">
        <strong class="timeline-section-title">Sec 8: Future Directions</strong>
        <ul class="timeline-subsections">
          <li>8.1 Explainability, Responsibility, and Reliability</li>
          <li>8.2 Security and Privacy</li>
          <li>8.3 Knowledge Graph-based Agentic Memory</li>
          <li>8.4 AI Agents with Graph DB &amp; Graph Analytics</li>
          <li>8.5 Domain-specific Applications</li>
        </ul>
      </div>
    </div>

    <div class="timeline-item">
      <div class="timeline-meta">
        <div class="timeline-time">Time: 12:20-12:30, 10 min</div>
        <div class="timeline-speaker">All</div>
        <div class="timeline-slides">Q&A</div>
      </div>
      <div class="timeline-node" aria-hidden="true"></div>
      <div class="timeline-content">
        <strong>Q&A (Session 2)</strong>
      </div>
    </div>
  </div>

  <!-- <h3 class="schedule-session-title">Session 3 (Time: TBD, 70 min)</h3>
  <div class="timeline-track">
    
  </div> -->
</section>
