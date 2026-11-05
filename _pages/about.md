---
permalink: /
title: ""
excerpt: ""
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">

{% if site.google_scholar_stats_use_cdn %}
{% assign gsDataBaseUrl = "https://cdn.jsdelivr.net/gh/" | append: site.repository | append: "@" %}
{% else %}
{% assign gsDataBaseUrl = "https://raw.githubusercontent.com/" | append: site.repository | append: "/" %}
{% endif %}

<style>
.scholar-summary {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 1rem;
  margin: 1.5rem 0 2rem;
}

.scholar-summary-card,
.scholar-paper-card {
  border: 1px solid rgba(15, 23, 42, 0.08);
  border-radius: 18px;
  background: linear-gradient(180deg, rgba(255,255,255,0.94), rgba(248,250,252,0.98));
  box-shadow: 0 18px 40px rgba(15, 23, 42, 0.06);
}

.scholar-summary-card {
  padding: 1.1rem 1.2rem;
}

.scholar-summary-card h3,
.scholar-paper-card h3 {
  margin: 0 0 0.4rem;
}

.scholar-summary-label {
  font-size: 0.88rem;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: rgba(15, 23, 42, 0.56);
  margin-bottom: 0.35rem;
}

.scholar-summary-value {
  font-size: 1.4rem;
  font-weight: 700;
  color: #0f172a;
}

.scholar-summary-copy {
  color: rgba(15, 23, 42, 0.8);
  margin: 0.35rem 0 0;
}

.scholar-pubs-grid {
  display: grid;
  gap: 1rem;
  margin-top: 1rem;
}

.scholar-paper-card {
  padding: 1.1rem 1.2rem;
}

.scholar-paper-title {
  font-size: 1.04rem;
  font-weight: 700;
  color: #0f172a;
  margin-bottom: 0.45rem;
}

.scholar-paper-meta {
  font-size: 0.92rem;
  line-height: 1.55;
  color: rgba(15, 23, 42, 0.76);
}

.scholar-paper-authors,
.scholar-paper-venue {
  display: block;
}

.scholar-paper-venue strong {
  color: #0f172a;
}

.scholar-paper-badge[hidden] {
  display: none;
}

.scholar-paper-badge {
  display: inline-flex;
  align-items: center;
  gap: 0.35rem;
  margin-top: 0.75rem;
  padding: 0.32rem 0.7rem;
  border-radius: 999px;
  background: rgba(14, 165, 233, 0.1);
  color: #0369a1;
  font-size: 0.84rem;
  font-weight: 600;
}

.scholar-status {
  margin-top: 0.85rem;
  color: rgba(15, 23, 42, 0.68);
}

@media (max-width: 640px) {
  .scholar-summary-card,
  .scholar-paper-card {
    border-radius: 14px;
  }
}
</style>

<span class='anchor' id='about-me'></span>

# <i class="fas fa-user"></i> About Me

I am <span class="accent-text">MA CHENGJIE</span>, a Ph.D. student in <span class="primary-gradient-text">Electrical and Electronic Engineering</span> at <span class="primary-gradient-text">Yonsei University</span>, based in <span class="primary-gradient-text">Sinchon, Seoul</span>. My research focuses on <span class="primary-gradient-text">Efficient Machine Learning, Federated Learning, LLM Fine-tuning, and AI-RAN</span>. If you enjoy <span class="primary-gradient-text">badminton, cycling, hiking,</span> or <span class="primary-gradient-text">academic exchange</span>, feel free to reach out. You can contact me at <a href="mailto:cjma@ramo.yonsei.ac.kr" class="link-accent">cjma@ramo.yonsei.ac.kr</a>.

<p><a href="{{ "/resume_chengjie_ma.pdf" | relative_url }}">Download CV (PDF)</a></p>

# <i class="fas fa-bullhorn"></i> News

- *2026*: My first ICML paper, “Breaking the Capacity Bottleneck in Model-Heterogeneous Federated Learning via Gradual Model Restoration,” appears in PMLR, volume 306, pages 84807–84845.
- *Planned, November 2026*: Technical exchanges during AI-RAN Summit activities (November 9–10, Seoul) and an initial CPU–GPU PHY acceleration demo at the AI-RAN Alliance All Member Meeting (November 11–12, Yonsei University).

# <i class="fas fa-graduation-cap"></i> Educations

- *2024.09 - Present*: Ph.D. student, Department of Electrical and Electronic Engineering, Yonsei University
  - GPA: 97.3/100
  - Advisor: Professor Seong-Lyun Kim
  - Research focus: Efficient Machine Learning and AI-RAN

- *2021.09 - 2024.06*: M.S. in Computer Science and Technology, Beijing University of Posts and Telecommunications
  - GPA: 92.69/100
  - Advisor: Professor Junping Du (IEEE Fellow)
  - Thesis: Communication Optimization in Federated Learning Based on Asynchrony and Pruning

- *2017.09 - 2021.06*: B.S. in Computer Science and Technology, Chongqing University of Posts and Telecommunications
  - GPA: 87.11/100, Top 2%
  - Honorary Bachelor's Degree
  - Minor: Business Administration

# <i class="fas fa-file-alt"></i> Publications

<div id="scholar-pubs" class="scholar-pubs-grid">
{% for pub in site.data.publications %}
  <article class="scholar-paper-card floating-card">
    <div class="scholar-paper-title">{{ pub.title | escape }}</div>
    <div class="scholar-paper-meta">
      <span class="scholar-paper-authors">{{ pub.authors | escape }}</span>
      <span class="scholar-paper-venue"><strong>Venue:</strong> {{ pub.venue | escape }} ({{ pub.year }})</span>
      {% if pub.volume %}<span class="scholar-paper-venue"><strong>Volume:</strong> {{ pub.volume }}</span>{% endif %}
      {% if pub.pages %}<span class="scholar-paper-venue"><strong>Pages:</strong> {{ pub.pages | escape }}</span>{% endif %}
      {% if pub.publisher %}<span class="scholar-paper-venue"><strong>Publisher:</strong> {{ pub.publisher | escape }}</span>{% endif %}
    </div>
    <span class="scholar-paper-badge" data-publication-title="{{ pub.title | escape }}" hidden></span>
  </article>
{% endfor %}
</div>
<p class="scholar-status"><a href="{{ site.author.googlescholar | escape }}">View Google Scholar profile</a></p>

<script>
(function () {
  function normalizeTitle(value) {
    return String(value || '').toLowerCase().replace(/\s+/g, ' ').trim();
  }
  // CV metadata stays visible even when Scholar is unavailable or out of date.
  fetch({{ gsDataBaseUrl | append: 'google-scholar-stats/gs_data.json' | jsonify }}, { cache: 'no-store' })
    .then(function (response) {
      if (!response.ok) throw new Error('Scholar unavailable');
      return response.json();
    })
    .then(function (data) {
      const byTitle = new Map(Object.values(data.publications || {}).map(function (pub) {
        return [normalizeTitle((pub.bib && pub.bib.title) || pub.title), pub];
      }));
      document.querySelectorAll('[data-publication-title]').forEach(function (badge) {
        const pub = byTitle.get(normalizeTitle(badge.dataset.publicationTitle));
        if (pub && pub.num_citations !== undefined && pub.num_citations !== null) {
          badge.textContent = 'Citations: ' + String(pub.num_citations);
          badge.hidden = false;
        }
      });
    })
    .catch(function () { /* The CV publication list does not depend on Scholar. */ });
})();
</script>

# <i class="fas fa-lightbulb"></i> Patent

- Training method, topic prediction method and device for federated variational autoencoder topic model. Patent number: **202310826329**; published January 31, 2024. Student first author.

# <i class="fas fa-briefcase"></i> Research Experience

- *2026.07 – Present*: **AI-RAN: CPU–GPU Acceleration and PHY Scheduling**, Yonsei University
  - Build a CPU–GPU heterogeneous computing platform using NVIDIA DGX Spark (GB10) and OCUDU 5G gNB, with PDSCH/PUSCH PHY processing and performance evaluation across CPU/GPU execution configurations.
  - Analyze latency, throughput capacity, and resource overhead across worker configurations, LDPC code block sizes, and PHY workloads; investigate Unified Memory data sharing, Static Routing, and Hybrid CPU–GPU PHY Scheduling.
  - Plan technical exchanges during AI-RAN Summit activities (November 9–10, Seoul) and an initial demo at the AI-RAN Alliance All Member Meeting (November 11–12, Yonsei University).

- *2025.09 – Present*: **TriBLoRA: Parameter-Efficient Fine-Tuning (Submitted)**, Yonsei University
  - Propose a tri-factor blockwise low-rank adaptation method that separates public and private information through shared outer factors and interaction-specific middle factors, enhancing LoRA’s expressive capacity.
  - Achieve intra-layer rank diversity through non-uniform parameter allocation within layers under a fixed parameter budget, supported by theoretical analysis and experiments.

- *2025.09 – 2026.07*: **AI-RAN**, Yonsei University
  - Explore GPU-accelerated base station architectures and offloading parts of gNB computation from CPUs to GPUs.
  - Investigated and implemented replacement of the gNB physical layer (L1) on the OCUDU platform using NVIDIA Aerial.

- *2024.09 – 2025.09*: **Federated Learning with Heterogeneous Clients**, Yonsei University
  - Studied heterogeneous environments with diverse client devices, asynchronous training, and varying model capacities.
  - Analyzed how system and model heterogeneity introduce skewed updates and degrade training performance.
  - Found that adaptive model capacity improves the effectiveness of contributions from weak clients.

- *2022.09 – 2024.06*: **Communication Optimization in Federated Learning**, Beijing University of Posts and Telecommunications
  - Worked on a sub-project supported by the National Natural Science Foundation of China (62192784, U22B2038, 62172056).
  - Studied communication-efficient federated learning with a focus on asynchronous training and model pruning.
  - Explored federated topic modeling and its applications in decentralized learning scenarios.

- *2022.03 – 2022.09*: **Shared Mobility Evaluation and Sentiment Analysis**, BUPT–Didi Global
  - Conducted topic analysis on customer reviews for shared mobility platforms.
  - Analyzed taxi transfer feedback and user sentiment trends.

# <i class="fas fa-code"></i> Skills

- **Programming and tools**: PyTorch, federated learning systems, model pruning, LLM fine-tuning, Docker.
- **Research areas**: Efficient Machine Learning, Federated Learning, Parameter-Efficient Fine-tuning, AI-RAN.
- **Languages**: CET-4: 454; CET-6: 434; IELTS: 6.0.

# <i class="fas fa-trophy"></i> Honors & Awards

- *2024*: Outstanding Graduate of Beijing, Provincial Level.
- *2021–2023*: First Class Graduate Scholarship (3 times), School Level.
- *2022–2023*: Outstanding Graduate Cadre (2 times), School Level.
- *2021*: CQUPT Honours Bachelor’s Degree, School Level.
- *2021*: Chongqing Advanced Individual in Enhancing Innovation Capability, Provincial Level.
- *2020*: Guo Changbo Scholarship, School Level.
- *2020*: 1st Prize, May Day Mathematical Modeling Competition, Provincial Level.
- *2020*: 2nd Prize, MathorCup Mathematical Modeling Challenge, Provincial Level.
- *2018–2019*: National Inspirational Scholarship (2 times), Provincial Level.

# <i class="fas fa-bullhorn"></i> Services

- *2026*: ICML 2026 Silver Reviewer.
- *2021.09 – 2024.06*: Class Monitor.
- *2023.09.27 – 2023.10.08*: Volunteer, China Open Tennis Championship.

# <i class="fas fa-envelope"></i> Contact

- Email: [cjma@ramo.yonsei.ac.kr](mailto:cjma@ramo.yonsei.ac.kr)
- Google Scholar: [Profile](https://scholar.google.com/citations?user=rQ45e8EAAAAJ)

- CV: [Download PDF]({{ "/resume_chengjie_ma.pdf" | relative_url }})
