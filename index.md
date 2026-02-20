---
layout: default
title: "GNN Explainers 2.0: User-centric and Data-driven Insights"
---

[//]: # (# GNN Explainers 2.0)

<section class="speakers-section" markdown="1">
## Speakers

<div class="speakers-grid">
  <div class="speaker">
    <img src="assets/speakers/khan.jpg" alt="Speaker 6 Name" class="speaker-photo">
    <h3><a href="https://www.cs.bgsu.edu/arijitk" target="_blank">Arijit Khan</a></h3>
    <p>Bowling Green State University</p>
  </div>
  <div class="speaker">
    <img src="assets/speakers/ke.jpg" alt="Speaker 6 Name" class="speaker-photo">
    <h3><a href="https://person.zju.edu.cn/en/kexiangyu" target="_blank">Xiangyu Ke</a></h3>
    <p>Zhejiang University</p>
  </div>
  <div class="speaker">
    <img src="assets/speakers/wu.jpg" alt="Speaker 6 Name" class="speaker-photo">
    <h3><a href="https://yinghwu.github.io" target="_blank">Yinghui Wu</a></h3>
    <p>Case Western Reserve<br> University</p>
  </div>
  <div class="speaker">
    <img src="assets/speakers/bonchi.jpg" alt="Speaker 6 Name" class="speaker-photo">
    <h3><a href="https://www.francescobonchi.com" target="_blank">Francesco Bonchi</a></h3>
    <p>CENTAI Institute</p>
  </div>
</div>
</section>

<div class="tutorial-info-card">
  <p class="tutorial-info-text"><strong>Tutorial Info:</strong> 🗓️ Sunday, Feb 22, 2026 · 9:00 AM-12:30 PM · 📍 Room 110CD</p>
</div>

---

## Abstract

<div class="abstract-section">

<p>
Graph neural networks (GNNs) are deep learning models designed
for graph-structured data that have achieved strong results across
domains–social networks, knowledge graphs, bioinformatics, transportation, 
World Wide Web, and finance–on tasks such as node
and graph classification, link prediction, entity resolution, question 
answering, recommendation, and fraud detection. Explaining
the decisions of high-performing, yet “black-box” GNNs remains
both challenging and essential. The initial five years have produced
tremendous progress with many GNN explainers (e.g., GNNExplainer, 
PGExplainer, SubgraphX, PGMExplainer, GraphLime, GCF-Explainer, CF2, GNN-LRP) 
that identify the influential nodes, edges,
subgraphs, and features aiming to explain the output of GNNs.
</p>

<p>
We refer to those works as GNN Explainers 1.0, since they provide 
one-time, final-output explanations and are focused on narrow
tasks like node or graph classification, which limits their usefulness 
for broader, user-centered needs. Practical debugging and
accountability require robust, multi-faceted, and GNN’s layer-wise
provenance so that data scientists can trace how inputs transform
through layers and locate where errors occur. Non-technical stakeholders 
need explanations that are accessible, configurable, and
queryable through familiar interfaces–structured queries, ad-hoc
instructions, counterfactual evidence, or natural language–so both
experts and non-experts can interactively explore model behavior.
</p>

<p>
This tutorial surveys latest advances in user-centered GNN explanations 
that shift focus from merely explaining model outputs
to producing actionable, end-user-facing explanations. We show
how data mining principles can improve comprehension, usability,
and trust, and outline practical strategies for creating configurable,
interpretable explanations tailored to diverse stakeholders. We refer
to this paradigm as GNN Explainers 2.0. We demonstrate key works
under this paradigm, summarize open challenges, and highlight
opportunities for the web and data mining community.
</p>

</div>

---

## Outline & Schedule

<section class="schedule-timeline">
  <h3 class="schedule-session-title">Session 1 (9:00 AM - 10:30 AM)</h3>
  <div class="timeline-track">
    <div class="timeline-item">
      <div class="timeline-meta">
        <div class="timeline-time">9:00 - 9:30 AM</div>
        <div class="timeline-speaker">Arijit Khan</div>
        <a class="timeline-slides" href="{{ '/pages/slides' | relative_url }}#slide-1">Slides 1-27</a>
      </div>
      <div class="timeline-node" aria-hidden="true"></div>
      <div class="timeline-content">
        <strong class="timeline-section-title">Sec 1: Introduction</strong>
        <ul class="timeline-subsections">
          <li>1.1 Graph Neural Networks (GNNs) and Applications</li>
          <li>1.2 Explainability of GNNs: Definitions, Importance, and Challenges</li>
        </ul>
        <strong class="timeline-section-title">Sec 2: GNN Explainers Categorization</strong>
        <ul class="timeline-subsections">
          <li>2.1 Post-hoc vs. Intrinsic / Self-explainable</li>
          <li>2.2 Global vs. Local</li>
          <li>2.3 Class-specific vs. Instance-specific</li>
          <li>2.4 Model-specific vs. Model-agnostic</li>
          <li>2.5 Forward vs. Backward</li>
          <li>2.6 Node-level vs. Edge-level vs. Subgraph-level</li>
          <li>2.7 Perturbation vs. Gradient vs. Decomposition vs. Surrogate Models</li>
          <li>2.8 Factuals vs. Counterfactuals</li>
        </ul>
        <strong class="timeline-section-title">Sec 3: GNN Explainers 2.0</strong>
      </div>
    </div>

    <div class="timeline-item">
      <div class="timeline-meta">
        <div class="timeline-time">9:30 - 10:00 AM</div>
        <div class="timeline-speaker">Xiangyu Ke</div>
        <a class="timeline-slides" href="{{ '/pages/slides' | relative_url }}#slide-28">Slides 28-49</a>
      </div>
      <div class="timeline-node" aria-hidden="true"></div>
      <div class="timeline-content">
        <strong class="timeline-section-title">Sec 4: User-centric and Data-driven Explainability Methods for GNNs</strong>
        <ul class="timeline-subsections">
          <li>4.1 Pattern Mining and Concept Hierarchies</li>
          <li>4.2 Model-slicing Explanations</li>
        </ul>
      </div>
    </div>

    <div class="timeline-item">
      <div class="timeline-meta">
        <div class="timeline-time">10:00 - 10:20 AM</div>
        <div class="timeline-speaker">Yinghui Wu</div>
        <a class="timeline-slides" href="{{ '/pages/slides' | relative_url }}#slide-50">Slides 50-62</a>
      </div>
      <div class="timeline-node" aria-hidden="true"></div>
      <div class="timeline-content">
        <ul class="timeline-subsections">
          <li>4.3 Robust Explanations</li>
          <li>4.4 Multi-criteria Explanations (Part I)</li>
        </ul>
      </div>
    </div>

    <div class="timeline-item">
      <div class="timeline-meta">
        <div class="timeline-time">10:20 - 10:30 AM</div>
        <div class="timeline-speaker">Yinghui Wu + All</div>
        <div class="timeline-slides">Q&A</div>
      </div>
      <div class="timeline-node" aria-hidden="true"></div>
      <div class="timeline-content">
        <strong>Q&A (Session 1)</strong>
      </div>
    </div>
  </div>

  <div class="timeline-break" role="note" aria-label="Break">
    Break (10:30 AM - 11:00 AM)
  </div>

  <h3 class="schedule-session-title">Session 2 (11:00 AM - 12:30 PM)</h3>
  <div class="timeline-track">
    <div class="timeline-item">
      <div class="timeline-meta">
        <div class="timeline-time">11:00 - 11:30 AM</div>
        <div class="timeline-speaker">Yinghui Wu</div>
        <a class="timeline-slides" href="{{ '/pages/slides' | relative_url }}#slide-63">Slides 63-77</a>
      </div>
      <div class="timeline-node" aria-hidden="true"></div>
      <div class="timeline-content">
        <ul class="timeline-subsections">
          <li>4.4 Multi-criteria Explanations (Part II)</li>
          <li>4.6 Efficiency and Interactiveness</li>
        </ul>
      </div>
    </div>

    <div class="timeline-item">
      <div class="timeline-meta">
        <div class="timeline-time">11:30 - 12:00 PM</div>
        <div class="timeline-speaker">Xiangyu Ke</div>
        <a class="timeline-slides" href="{{ '/pages/slides' | relative_url }}#slide-78">Slides 78-93</a>
      </div>
      <div class="timeline-node" aria-hidden="true"></div>
      <div class="timeline-content">
        <ul class="timeline-subsections">
          <li>4.5 Declarative Explanatory Queries</li>
          <li>4.7 Natural Language Explanations</li>
        </ul>
      </div>
    </div>

    <div class="timeline-item">
      <div class="timeline-meta">
        <div class="timeline-time">12:00 - 12:20 PM</div>
        <div class="timeline-speaker">Arijit Khan</div>
        <a class="timeline-slides" href="{{ '/pages/slides' | relative_url }}#slide-94">Slides 94-133</a>
      </div>
      <div class="timeline-node" aria-hidden="true"></div>
      <div class="timeline-content">
        <ul class="timeline-subsections">
          <li>4.8 Counterfactual Explanations</li>
        </ul>
        <strong class="timeline-section-title">Sec 5: Future Directions</strong>
        <ul class="timeline-subsections">
          <li>5.1 Downstream Tasks beyond Classification</li>
          <li>5.2 Qualitative Evaluation of GNN Explanation</li>
          <li>5.3 Explainability for Complex GNNs</li>
          <li>5.4 Explanation with Privacy Concern</li>
          <li>5.5 Explanation as Actionable Recourse</li>
          <li>5.6 Multi-modal Explanation</li>
        </ul>
      </div>
    </div>

    <div class="timeline-item">
      <div class="timeline-meta">
        <div class="timeline-time">12:20 - 12:30 PM</div>
        <div class="timeline-speaker">Arijit Khan + All</div>
        <div class="timeline-slides">Q&A</div>
      </div>
      <div class="timeline-node" aria-hidden="true"></div>
      <div class="timeline-content">
        <strong>Q&A (Session 2)</strong>
      </div>
    </div>
  </div>
</section>
