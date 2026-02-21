---
layout: default
title: "GNN Explainers 2.0: User-centric and Data-driven Insights"
description: "WSDM 2026 Tutorial Slides"
---

<style>
  body { background: #fff; }

  :root { --accent: #157878; --accent-ink: #0f4e4e; }

  .slides-toolbar {
    position: sticky;
    top: 0;
    z-index: 40;
    margin: 0 0 14px;
    padding: 10px;
    background: rgba(248, 250, 252, 0.75);
    -webkit-backdrop-filter: saturate(180%) blur(8px);
    backdrop-filter: saturate(180%) blur(8px);
    border: 1px solid #e5e7eb;
    border-radius: 10px;
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 10px;
    align-items: center;
    box-shadow: 0 6px 20px rgba(0, 0, 0, 0.06);
  }

  .slides-toolbar .toolbar-left {
    justify-self: start;
    display: flex;
    align-items: center;
    min-width: 0;
  }

  .slides-toolbar .toolbar-right {
    justify-self: end;
    display: flex;
    align-items: center;
    gap: 10px;
    flex-wrap: nowrap;
    white-space: nowrap;
  }

  .slides-toolbar .toolbar-right > * { flex: 0 0 auto; }

  .slides-toolbar::after {
    content: "";
    position: absolute;
    left: 0;
    right: 0;
    bottom: -12px;
    height: 12px;
    background: linear-gradient(to bottom, rgba(0, 0, 0, 0.06), rgba(0, 0, 0, 0));
    pointer-events: none;
  }

  .slides-toolbar .tool-btn {
    display: inline-block;
    padding: 7px 12px;
    font-size: 14px;
    border-radius: 8px;
    border: 1px solid #d1d5db;
    background: #fff;
    color: #111;
    text-decoration: none;
    cursor: pointer;
  }

  .slides-toolbar .tool-btn:hover { background: #f3f4f6; }

  .slides-toolbar .tool-btn.primary {
    border-color: var(--accent);
    color: var(--accent-ink);
    background: #eaf6f4;
  }

  .slides-toolbar .tool-btn[disabled] {
    opacity: 0.55;
    cursor: not-allowed;
  }

  .slides-toolbar .tool-btn[disabled]:hover { background: #fff; }

  .slides-toolbar .toolbar-group {
    position: relative;
    display: flex;
    gap: 8px;
    align-items: center;
  }

  .slides-toolbar .tool-input {
    padding: 7px 10px;
    border-radius: 8px;
    border: 1px solid #d1d5db;
    background: #fff;
    font-size: 14px;
    width: 120px;
    max-width: 30vw;
  }

  #topSlideInput {
    width: 110px;
    max-width: 26vw;
  }

  .tool-btn:focus {
    outline: 2px solid var(--accent);
    outline-offset: 1px;
  }

  .current-part {
    margin-left: 6px;
    font-size: 16px;
    color: #159957;
    font-weight: 700;
    white-space: nowrap;
    display: inline-block;
    max-width: 50vw;
    overflow: hidden;
    text-overflow: ellipsis;
  }

  @media (min-width: 768px) {
    .current-part {
      max-width: none;
      overflow: visible;
      text-overflow: initial;
    }
  }

  @media (max-width: 640px) {
    .current-part {
      max-width: 42vw;
      font-size: 14px;
    }

    .slides-toolbar .tool-btn {
      padding: 6px 9px;
      font-size: 13px;
    }

    .slides-toolbar {
      gap: 8px;
    }

    .slides-toolbar .tool-input {
      width: 100px;
      max-width: 28vw;
    }

    #topSlideInput {
      width: 90px;
      max-width: 26vw;
    }
  }

  @media (max-width: 480px) {
    .current-part {
      max-width: 38vw;
      font-size: 13px;
    }

    .slides-toolbar .tool-btn {
      padding: 5px 8px;
      font-size: 12.5px;
    }

    .slides-toolbar {
      gap: 6px;
    }

    .slides-toolbar .tool-input {
      width: 90px;
      max-width: 30vw;
      font-size: 12.5px;
      padding: 5px 8px;
    }

    #topSlideInput {
      width: 80px;
      max-width: 26vw;
    }
  }

  @media (max-width: 360px) {
    .current-part {
      max-width: 34vw;
      font-size: 12.5px;
    }

    .slides-toolbar .tool-btn {
      padding: 4px 7px;
      font-size: 12px;
    }

    .slides-toolbar {
      gap: 4px;
    }

    .slides-toolbar .tool-input {
      width: 80px;
      max-width: 28vw;
      font-size: 12px;
      padding: 4px 7px;
    }

    #topSlideInput { width: 70px; }
  }

  .dropdown-panel {
    position: absolute;
    top: 110%;
    left: 0;
    z-index: 10;
    display: none;
    min-width: 280px;
    padding: 10px;
    border: 1px solid #e5e7eb;
    border-radius: 10px;
    background: #fff;
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.12);
  }

  .dropdown-panel.open { display: block; }

  .dropdown-panel .menu {
    display: grid;
    gap: 6px;
  }

  .dropdown-panel .menu-item {
    display: block;
    width: 100%;
    text-align: left;
    padding: 7px 10px;
    border-radius: 8px;
    border: 1px solid #e5e7eb;
    background: #f9fafb;
    color: #111;
    text-decoration: none;
    font-size: 14px;
    white-space: nowrap;
    cursor: pointer;
  }

  .dropdown-panel .menu-item:hover {
    background: #eef2ff;
    border-color: #c7d2fe;
  }

  #roadmapPanel,
  #downloadPanel {
    width: max-content;
    max-width: calc(100vw - 32px);
    overflow-x: auto;
  }

  .page-header { display: none !important; }

  .main-content {
    max-width: none;
    padding: 0;
  }

  .slides-container {
    width: 100%;
    max-width: none;
    margin: 0;
  }

  .slide-card {
    background: #fff;
    border: 0;
    border-radius: 0;
    box-shadow: none;
    margin: 0;
    padding: 0;
    scroll-margin-top: 90px;
    position: relative;
  }

  .slide-canvas-wrap {
    position: relative;
    display: block;
    width: 100%;
    margin: 0 auto;
  }

  @media (min-width: 1024px) {
    .slide-canvas-wrap { width: 80%; }
  }

  .slide-separator {
    border-top: 2px dashed #cbd5e1;
    margin: 12px 0 18px;
  }

  .slide-card:last-child .slide-separator { display: none; }

  .slide-share {
    position: absolute;
    right: 10px;
    top: 10px;
    z-index: 2;
    padding: 6px 10px;
    border-radius: 8px;
    border: 1px solid rgba(255, 255, 255, 0.25);
    background: rgba(17, 24, 39, 0.7);
    color: #fff;
    font-size: 12.5px;
    line-height: 1;
    cursor: pointer;
    -webkit-backdrop-filter: saturate(160%) blur(4px);
    backdrop-filter: saturate(160%) blur(4px);
  }

  .slide-share:hover { background: rgba(17, 24, 39, 0.82); }

  .slide-share:focus {
    outline: 2px solid #93c5fd;
    outline-offset: 1px;
  }

  .slide-share.copied {
    background: rgba(16, 185, 129, 0.8);
    border-color: rgba(16, 185, 129, 0.6);
  }

  .slide-canvas {
    width: 100%;
    height: auto;
    display: block;
    background: #fff;
    border-radius: 6px;
  }

  .loading-overlay {
    position: fixed;
    inset: 0;
    z-index: 55;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 16px;
    background: radial-gradient(circle at 50% 30%, rgba(21, 120, 120, 0.12), rgba(255, 255, 255, 0.98) 62%);
  }

  .loading-card {
    width: min(480px, calc(100vw - 32px));
    background: #fff;
    border: 1px solid #dce8e8;
    border-left: 6px solid #159957;
    border-radius: 16px;
    box-shadow: 0 20px 48px rgba(15, 78, 78, 0.15);
    padding: 22px 24px 18px;
  }

  .loading-header {
    display: flex;
    align-items: center;
    gap: 14px;
    margin-bottom: 10px;
  }

  .loading-spinner {
    width: 34px;
    height: 34px;
    border-radius: 50%;
    border: 3px solid #d1d5db;
    border-top-color: #159957;
    animation: spin 0.85s linear infinite;
    flex: 0 0 auto;
  }

  .loading-title {
    margin: 0;
    color: #0f4e4e;
    font-weight: 700;
    font-size: 1.1rem;
    line-height: 1.2;
  }

  .loading-text {
    margin: 0 0 12px;
    color: #4b5563;
    font-size: 0.95rem;
    line-height: 1.35;
  }

  .loading-progress {
    width: 100%;
    height: 7px;
    border-radius: 999px;
    background: #e5e7eb;
    overflow: hidden;
  }

  .loading-progress-bar {
    display: block;
    width: 0%;
    height: 100%;
    border-radius: inherit;
    background: linear-gradient(90deg, #159957, #157878);
    transition: width 0.35s ease;
  }

  @keyframes spin {
    to { transform: rotate(360deg); }
  }

  .error-overlay .loading-card {
    border-left-color: #b91c1c;
  }

  .error-overlay .loading-title {
    color: #7f1d1d;
  }

  .error {
    color: #b91c1c;
    font-size: 13px;
  }
</style>

<div class="slides-container">
  <div class="slides-toolbar" role="navigation" aria-label="Slides toolbar">
    <div class="toolbar-left">
      <span id="currentPart" class="current-part" aria-live="polite">[WSDM'26 Tutorial] GNN Explainers 2.0: User-centric and Data-driven Insights</span>
    </div>
    <div class="toolbar-right">
      <div class="toolbar-group" id="roadmapGroup">
        <button id="roadmapBtn" class="tool-btn primary" type="button" aria-haspopup="true" aria-expanded="false" aria-controls="roadmapPanel">Roadmap</button>
        <div id="roadmapPanel" class="dropdown-panel" role="dialog" aria-modal="true" aria-label="Select part">
          <div class="menu" id="roadmapMenu"></div>
        </div>
      </div>
      <div class="toolbar-group" id="downloadGroup">
        <button id="downloadBtn" class="tool-btn primary" type="button" aria-haspopup="true" aria-expanded="false" aria-controls="downloadPanel">Download</button>
        <div id="downloadPanel" class="dropdown-panel" role="dialog" aria-modal="true" aria-label="Select format">
          <div class="menu">
            <a class="menu-item" href="{{ '/assets/docs/WSDM26Tut_GNNExplainers2.pdf' | relative_url }}" download>PDF (~9.1MB)</a>
            <a class="menu-item" href="{{ '/assets/docs/WSDM26Tut_GNNExplainers2.pptx' | relative_url }}" download>PPTX (~23.8MB)</a>
          </div>
        </div>
      </div>
      <a class="tool-btn primary" href="{{ '/' | relative_url }}">Back to Home</a>
      <div class="toolbar-group" id="slideGoGroup">
        <input id="topSlideInput" class="tool-input" type="number" min="1" placeholder="Slide #" aria-label="Jump to slide number in this deck" />
        <button id="topSlideGo" class="tool-btn" type="button">Go</button>
      </div>
    </div>
  </div>

  <div id="slidesRoot" aria-live="polite"></div>
  <div id="slidesStatus" class="loading-overlay" role="status" aria-live="polite" aria-atomic="true">
    <div class="loading-card">
      <div class="loading-header">
        <span class="loading-spinner" aria-hidden="true"></span>
        <p class="loading-title">Preparing Slide Viewer</p>
      </div>
      <p id="slidesStatusText" class="loading-text">Loading slides</p>
      <div class="loading-progress" aria-hidden="true">
        <span class="loading-progress-bar"></span>
      </div>
    </div>
  </div>
</div>

<script type="module">
  const pdfUrl = "{{ '/assets/docs/WSDM26Tut_GNNExplainers2.pdf' | relative_url }}";
  const deckTitle = "[WSDM'26 Tutorial] GNN Explainers 2.0: User-centric and Data-driven Insights";

  // Fallback roadmap used when the PDF does not contain outline/bookmarks.
  // Update slide numbers if you want precise manual control.
  const fallbackRoadmap = [
    { slide: 2, label: "Sec 1: Introduction" },
    { slide: 12, label: "Sec 2: GNN Explainers Categorization" },
    { slide: 23, label: "Sec 3: GNN Explainers 2.0" },
    { slide: 27, label: "Sec 4: User-centric and Data-driven Explainability Methods for GNNs" },
    { slide: 126, label: "Sec 5: Future Directions" }
  ];

  const root = document.getElementById("slidesRoot");
  const statusEl = document.getElementById("slidesStatus");
  const statusTextEl = document.getElementById("slidesStatusText");
  const roadmapBtn = document.getElementById("roadmapBtn");
  const roadmapPanel = document.getElementById("roadmapPanel");
  const roadmapMenu = document.getElementById("roadmapMenu");
  const currentPartEl = document.getElementById("currentPart");
  const downloadBtn = document.getElementById("downloadBtn");
  const downloadPanel = document.getElementById("downloadPanel");
  const topSlideInput = document.getElementById("topSlideInput");
  const topSlideGo = document.getElementById("topSlideGo");

  let roadmapItems = [];
  const totalLoadingSteps = 3;

  function setLoadingStep(step, message) {
    if (!statusEl) return;
    const currentStep = Math.max(1, Math.min(totalLoadingSteps, Number(step) || 1));
    if (statusTextEl) statusTextEl.textContent = message;
    const bar = statusEl.querySelector(".loading-progress-bar");
    if (bar) {
      bar.style.width = `${Math.round((currentStep / totalLoadingSteps) * 100)}%`;
    }
    statusEl.setAttribute("aria-label", `${message} (${currentStep}/${totalLoadingSteps})`);
  }

  function showLoadError(message) {
    statusEl.className = "loading-overlay error-overlay";
    statusEl.innerHTML = `
      <div class="loading-card">
        <p class="loading-title">Unable to Load Slides</p>
        <p class="loading-text">${message}</p>
      </div>
    `;
  }

  function makeId(n) { return `slide-${n}`; }
  function makeAnchor(n) { return `#${makeId(n)}`; }

  function pixelRatio() { return Math.min(window.devicePixelRatio || 1, 2); }

  function normalizedSlide(value, max) {
    let n = parseInt(value, 10);
    if (!Number.isFinite(n) || n < 1) n = 1;
    if (Number.isFinite(max)) n = Math.min(max, n);
    return n;
  }

  function jumpToSlide(n, behavior = "smooth") {
    const target = document.getElementById(makeId(n));
    if (target) {
      history.pushState(null, "", makeAnchor(n));
      target.scrollIntoView({ behavior, block: "start" });
      setCurrentPartBySlide(n);
    } else {
      location.hash = makeAnchor(n);
    }
  }

  function setCurrentPartBySlide(n) {
    if (!currentPartEl) return;
    if (n === 1) {
      currentPartEl.textContent = deckTitle;
      currentPartEl.title = `${deckTitle} (Slide 1)`;
      return;
    }
    let label = deckTitle;
    for (const item of roadmapItems) {
      if (item.slide <= n) label = item.label;
      else break;
    }
    currentPartEl.textContent = label;
    currentPartEl.title = `${label} (Slide ${n})`;
  }

  function normalizeRoadmap(items, totalSlides) {
    if (!Array.isArray(items)) return [];
    const normalized = items
      .map((item) => ({
        slide: normalizedSlide(item.slide, totalSlides),
        label: String(item.label || "Section")
      }))
      .filter((item) => item.label.trim())
      .sort((a, b) => a.slide - b.slide || a.label.localeCompare(b.label));

    return normalized.filter((item, idx) => {
      if (idx === 0) return true;
      const prev = normalized[idx - 1];
      return prev.slide !== item.slide || prev.label !== item.label;
    });
  }

  function renderRoadmapMenu(items) {
    roadmapMenu.innerHTML = "";
    if (!items.length) {
      roadmapBtn.disabled = true;
      return;
    }
    roadmapBtn.disabled = false;
    for (const item of items) {
      const btn = document.createElement("button");
      btn.className = "menu-item";
      btn.type = "button";
      btn.dataset.slide = String(item.slide);
      btn.textContent = item.label;
      roadmapMenu.appendChild(btn);
    }
  }

  async function roadmapFromPdfOutline(pdfDoc, totalSlides) {
    const outline = await pdfDoc.getOutline();
    if (!outline || !outline.length) return [];

    const queue = [...outline];
    const items = [];
    while (queue.length) {
      const node = queue.shift();
      if (!node) continue;
      if (Array.isArray(node.items) && node.items.length) {
        queue.unshift(...node.items);
      }

      const title = String(node.title || "").trim();
      if (!title || !node.dest) continue;

      let dest = node.dest;
      if (typeof dest === "string") {
        dest = await pdfDoc.getDestination(dest);
      }
      if (!Array.isArray(dest) || !dest[0]) continue;

      try {
        const pageIndex = await pdfDoc.getPageIndex(dest[0]);
        items.push({ slide: pageIndex + 1, label: title });
      } catch (_err) {
        // Ignore invalid bookmark destination.
      }
    }

    return normalizeRoadmap(items, totalSlides);
  }

  function buildSlideShell(n) {
    const card = document.createElement("section");
    card.className = "slide-card";
    card.id = makeId(n);

    const wrap = document.createElement("div");
    wrap.className = "slide-canvas-wrap";

    const canvas = document.createElement("canvas");
    canvas.className = "slide-canvas";
    canvas.dataset.page = String(n);
    canvas.setAttribute("role", "img");
    canvas.setAttribute("aria-label", `Slide ${n}`);
    wrap.appendChild(canvas);

    const share = document.createElement("button");
    share.className = "slide-share";
    share.type = "button";
    share.dataset.page = String(n);
    share.textContent = "Share this slide";
    share.setAttribute("aria-label", `Copy link to slide ${n}`);
    wrap.appendChild(share);

    card.appendChild(wrap);

    const sep = document.createElement("div");
    sep.className = "slide-separator";
    card.appendChild(sep);

    return card;
  }

  function observeAndRender(pdfDoc) {
    const pr = pixelRatio();

    const observer = new IntersectionObserver(
      async (entries) => {
        for (const entry of entries) {
          if (!entry.isIntersecting) continue;
          const canvas = entry.target;
          observer.unobserve(canvas);
          const n = parseInt(canvas.dataset.page, 10);
          try {
            const page = await pdfDoc.getPage(n);
            const unscaled = page.getViewport({ scale: 1 });
            const containerWidth = canvas.parentElement.clientWidth;
            const scale = Math.max(0.1, containerWidth / unscaled.width);
            const viewport = page.getViewport({ scale });
            canvas.style.width = `${viewport.width}px`;
            canvas.style.height = `${viewport.height}px`;
            canvas.width = Math.floor(viewport.width * pr);
            canvas.height = Math.floor(viewport.height * pr);
            const ctx = canvas.getContext("2d");
            const transform = pr !== 1 ? [pr, 0, 0, pr, 0, 0] : null;
            await page.render({ canvasContext: ctx, viewport, transform }).promise;
          } catch (err) {
            const errEl = document.createElement("div");
            errEl.className = "error";
            errEl.textContent = "Failed to render this slide.";
            canvas.replaceWith(errEl);
            console.error("Render error for slide", n, err);
          }
        }
      },
      { rootMargin: "400px 0px" }
    );

    root.querySelectorAll("canvas.slide-canvas").forEach((c) => observer.observe(c));

    let rid = 0;
    const debounced = () => {
      if (rid) cancelAnimationFrame(rid);
      rid = requestAnimationFrame(() => {
        root.querySelectorAll("canvas.slide-canvas").forEach((c) => observer.observe(c));
      });
    };
    window.addEventListener("resize", debounced);
  }

  async function importPdfjs() {
    try {
      return await import("{{ '/assets/js/pdf.mjs' | relative_url }}");
    } catch (_err) {
      try {
        return await import("https://cdn.jsdelivr.net/npm/pdfjs-dist@4.6.82/build/pdf.mjs");
      } catch (e2) {
        console.error("Failed to import pdf.mjs", e2);
        return null;
      }
    }
  }

  function setWorkerSrcLocal(pdfjs) {
    pdfjs.GlobalWorkerOptions.workerSrc = "{{ '/assets/js/pdf.worker.mjs' | relative_url }}";
  }

  function setWorkerSrcCdn(pdfjs) {
    pdfjs.GlobalWorkerOptions.workerSrc = "https://cdn.jsdelivr.net/npm/pdfjs-dist@4.6.82/build/pdf.worker.mjs";
  }

  (async function boot() {
    setLoadingStep(1, "Step 1/3: Loading Slides");

    const pdfjs = await importPdfjs();
    if (!pdfjs) {
      showLoadError("Viewer failed to load. Use Download to open the PDF directly.");
      return;
    }

    setWorkerSrcLocal(pdfjs);
    setLoadingStep(2, "Step 2/3: Parsing Pages");

    let pdfDoc = null;
    try {
      pdfDoc = await pdfjs.getDocument(pdfUrl).promise;
    } catch (e1) {
      console.warn("Local worker failed, retrying with CDN worker...", e1);
      try {
        setWorkerSrcCdn(pdfjs);
        pdfDoc = await pdfjs.getDocument(pdfUrl).promise;
      } catch (e2) {
        showLoadError("Failed to load PDF. Use the Download menu.");
        console.error(e2);
        return;
      }
    }

    const total = pdfDoc.numPages;
    setLoadingStep(3, "Step 3/3: Rendering Preview");
    const frag = document.createDocumentFragment();
    for (let i = 1; i <= total; i++) {
      frag.appendChild(buildSlideShell(i));
    }
    root.appendChild(frag);
    statusEl.remove();

    observeAndRender(pdfDoc);

    topSlideInput?.setAttribute("max", String(total));

    const manualRoadmap = normalizeRoadmap(fallbackRoadmap, total);
    // Use curated roadmap labels to keep section naming and boundaries consistent.
    roadmapItems = manualRoadmap;

    renderRoadmapMenu(roadmapItems);

    let initialSlide = 1;
    const match = (window.location.hash || "").match(/#slide-(\d+)/);
    if (match) {
      initialSlide = normalizedSlide(match[1], total);
      const target = document.getElementById(`slide-${initialSlide}`);
      if (target) target.scrollIntoView({ behavior: "auto", block: "start" });
    }
    setCurrentPartBySlide(initialSlide);

    const milestoneEls = roadmapItems
      .map((item) => document.getElementById(makeId(item.slide)))
      .filter(Boolean);

    const milestoneObserver = new IntersectionObserver(
      (entries) => {
        let best = null;
        for (const entry of entries) {
          if (!entry.isIntersecting) continue;
          if (!best || entry.intersectionRatio > best.intersectionRatio) best = entry;
        }
        if (!best) return;
        const m = best.target.id.match(/slide-(\d+)/);
        if (!m) return;
        setCurrentPartBySlide(parseInt(m[1], 10));
      },
      { threshold: 0.55 }
    );

    milestoneEls.forEach((el) => milestoneObserver.observe(el));
  })();

  function closeRoadmapPanel({ restoreFocus = true } = {}) {
    roadmapPanel.classList.remove("open");
    roadmapBtn.setAttribute("aria-expanded", "false");
    if (restoreFocus) roadmapBtn.focus();
  }

  function openRoadmapPanel() {
    roadmapPanel.classList.add("open");
    roadmapBtn.setAttribute("aria-expanded", "true");
    const first = roadmapPanel.querySelector(".menu-item");
    if (first) first.focus();
  }

  roadmapBtn?.addEventListener("click", () => {
    if (roadmapPanel.classList.contains("open")) closeRoadmapPanel();
    else openRoadmapPanel();
  });

  roadmapMenu?.addEventListener("click", (e) => {
    const item = e.target.closest(".menu-item");
    if (!item) return;
    const n = parseInt(item.getAttribute("data-slide"), 10);
    closeRoadmapPanel({ restoreFocus: false });
    setCurrentPartBySlide(n);
    jumpToSlide(n, "auto");
  });

  function closeDownloadPanel() {
    downloadPanel.classList.remove("open");
    downloadBtn.setAttribute("aria-expanded", "false");
    downloadBtn.focus();
  }

  function openDownloadPanel() {
    downloadPanel.classList.add("open");
    downloadBtn.setAttribute("aria-expanded", "true");
    const first = downloadPanel.querySelector(".menu-item");
    if (first) first.focus();
  }

  downloadBtn?.addEventListener("click", () => {
    if (downloadPanel.classList.contains("open")) closeDownloadPanel();
    else openDownloadPanel();
  });

  downloadPanel?.addEventListener("click", (e) => {
    const link = e.target.closest("a.menu-item");
    if (!link) return;
    closeDownloadPanel();
  });

  document.addEventListener("click", (e) => {
    if (downloadPanel.classList.contains("open") && !e.target.closest("#downloadGroup")) closeDownloadPanel();
    if (roadmapPanel.classList.contains("open") && !e.target.closest("#roadmapGroup")) closeRoadmapPanel();
  });

  document.addEventListener("keydown", (e) => {
    if (e.key !== "Escape") return;
    if (downloadPanel.classList.contains("open")) closeDownloadPanel();
    if (roadmapPanel.classList.contains("open")) closeRoadmapPanel();
  });

  function trapTab(e, panel) {
    if (e.key !== "Tab") return;
    const focusables = Array.from(
      panel.querySelectorAll("button, [href], select, [tabindex]:not([tabindex='-1'])")
    ).filter((el) => !el.hasAttribute("disabled"));
    if (focusables.length === 0) return;
    const first = focusables[0];
    const last = focusables[focusables.length - 1];
    const active = document.activeElement;
    if (!e.shiftKey && active === last) {
      e.preventDefault();
      first.focus();
    } else if (e.shiftKey && active === first) {
      e.preventDefault();
      last.focus();
    }
  }

  roadmapPanel?.addEventListener("keydown", (e) => trapTab(e, roadmapPanel));
  downloadPanel?.addEventListener("keydown", (e) => trapTab(e, downloadPanel));

  root.addEventListener("click", async (e) => {
    const btn = e.target.closest("button.slide-share");
    if (!btn) return;

    const n = parseInt(btn.dataset.page, 10);
    const url = new URL(window.location.href);
    url.hash = `slide-${n}`;

    try {
      if (navigator.clipboard && navigator.clipboard.writeText) {
        await navigator.clipboard.writeText(url.toString());
      } else {
        const ta = document.createElement("textarea");
        ta.value = url.toString();
        document.body.appendChild(ta);
        ta.select();
        document.execCommand("copy");
        ta.remove();
      }
      const original = btn.textContent;
      btn.textContent = "Slide link copied";
      btn.classList.add("copied");
      setTimeout(() => {
        btn.textContent = original;
        btn.classList.remove("copied");
      }, 1400);
    } catch (err) {
      console.error("Clipboard failed", err);
    }
  });

  topSlideGo?.addEventListener("click", () => {
    const max = parseInt(topSlideInput?.getAttribute("max") || "", 10);
    const n = normalizedSlide(topSlideInput?.value || "", max);
    jumpToSlide(n, "auto");
  });

  topSlideInput?.addEventListener("keydown", (e) => {
    if (e.key !== "Enter") return;
    e.preventDefault();
    const max = parseInt(topSlideInput?.getAttribute("max") || "", 10);
    const n = normalizedSlide(topSlideInput.value || "", max);
    jumpToSlide(n, "auto");
  });

  let labelResizeTid = null;
  window.addEventListener("resize", () => {
    if (labelResizeTid) cancelAnimationFrame(labelResizeTid);
    labelResizeTid = requestAnimationFrame(() => {
      const current = (window.location.hash || "").match(/#slide-(\d+)/);
      if (!current) {
        setCurrentPartBySlide(1);
        return;
      }
      setCurrentPartBySlide(parseInt(current[1], 10));
    });
  });
</script>
