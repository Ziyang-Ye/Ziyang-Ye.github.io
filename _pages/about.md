---
permalink: /
title: ""
excerpt: ""
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

{% if site.google_scholar_stats_use_cdn %}
{% assign gsDataBaseUrl = "https://cdn.jsdelivr.net/gh/" | append: site.repository | append: "@" %}
{% else %}
{% assign gsDataBaseUrl = "https://raw.githubusercontent.com/" | append: site.repository | append: "/" %}
{% endif %}
{% assign url = gsDataBaseUrl | append: "google-scholar-stats/gs_data_shieldsio.json" %}

<span class='anchor' id='about-me'></span>

I am Ziyang Ye (叶子扬), an undergraduate student in Software Engineering at Jilin University. I am currently a **Research Assistant** at **The Chinese University of Hong Kong, Shenzhen (CUHK-SZ)**, working with [**Prof. Li Jiang**](https://llijiang.github.io/), and an **Intern** at **Didi, Voyager AI Research**.

My research asks how generative video models can become **world models that survive contact with action**. Visual plausibility alone is not enough: an embodied world model must remain reliable when its own predictions become new context and when actions alter the scene.

I approach this question through three connected directions:

- **Video Generation:** learning expressive and scalable visual priors that preserve appearance, motion, and scene structure as environments evolve over long sequences.
- **Interactive World Model:** turning video generators into closed-loop simulators that remain stable under self-generated context, respond coherently to actions, and maintain consistent dynamics across multiple actors.
- **World Action Model:** developing foundation models for embodied intelligence that connect multimodal perception, predictive world dynamics, and action, so imagined futures can support planning, execution, verification, and recovery.

Together, these directions move from generating plausible futures, to simulating interactive worlds, to using predictive models for embodied decisions.

<div style="padding: 10px 14px; border-left: 4px solid #2a7ae2; background: #f0f6ff; border-radius: 4px; margin: 12px 0;">
<strong>🚀 I am actively seeking <span style="color:#2a7ae2;">research collaborations</span> in Artificial Intelligence.</strong> Feel free to reach out via <a href="mailto:yeziyang777@gmail.com">email</a> if you'd like to collaborate or discuss research ideas.
</div>


# 📝 Publications

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">ICML 2026</div><img src='images/live_paper.png' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[LIVE: Long-horizon Interactive Video World Modeling](https://doi.org/10.48550/arXiv.2602.03747)

Junchao Huang, **Ziyang Ye**, Xinting Hu, Tianyu He, Guiyu Zhang, Shaoshuai Shi, Jiang Bian, Li Jiang

**Accepted at ICML 2026**
- Addresses error accumulation in autoregressive video world models, which degrades generation quality over long horizons
- Uses forward-reverse cycle consistency and progressive training to improve robustness under self-generated context
- Reports stable video generation on long rollouts beyond the training horizon

</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">ICLR 2027 Under Review</div><img src='images/500x300.png' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

WorldCast: Distributed Multiplayer World Models

**Ziyang Ye**, Junchao Huang, Evelyn Zhang, Zhihao Xie, Ruicheng Zhang, Boyao Han, Litao Ban, Ziye Wang, Xinting Hu, Shaoshuai Shi, Zhuotao Tian, Li Jiang

**Under review at ICLR 2027**
- Extends interactive video world models from a single player to a shared multiplayer scene
- Uses scene-time synchronization, cross-player communication, and shared latent memory with private-view decoding
- Targets cross-view consistency when multiple players act on the same world simultaneously

</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">ICLR 2027 Under Review</div><img src='images/500x300.png' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

Iso-WAM: Rethinking Representation Forcing in World Action Models

Zhihao Xie, Yuanhao Wang, Jingxin Wang, Yuxin Cheng, **Ziyang Ye**, Haobo Li, Junchao Huang, Junfeng Wu, Xinting Hu, Li Jiang

**Under review at ICLR 2027**
- Identifies a misalignment in world-action models: pixel-level future prediction entangles physical task dynamics with task-irrelevant appearance, so policies misread appearance shifts as state changes under OOD conditions
- Builds a dynamic information bottleneck that isolates actionable dynamics, aligning learnable query tokens in the action stream with dual latent action targets from DINOv3 (semantic transitions) and VGGT (spatio-temporal geometric transitions)
- Predicts a control-consistent future *change* rather than a visually consistent state, outperforming state-of-the-art WAMs on LIBERO-Plus and real-robot OOD evaluation

</div>
</div>

# 📖 Education
- *2023.09 - 2027.06 (Expected)*, Bachelor of Engineering in Software Engineering, Jilin University, China. **Average Score: 88.68 / 100**

# 🔬 Research Experience

<div style="margin-bottom: 1.5em;">
  <div><strong>The Chinese University of Hong Kong, Shenzhen (CUHK-SZ)</strong> &nbsp;·&nbsp; <em>Dec. 2025 – Present</em></div>
  <div style="color:#666; margin: 2px 0;">Research Assistant &nbsp;|&nbsp; Advisor: <a href="https://llijiang.github.io/">Prof. Li Jiang</a> &nbsp;|&nbsp; Shenzhen, China</div>
  <ul style="margin-top: 6px;">
    <li><strong>LIVE</strong> (ICML 2026): Contributed to implementing the cycle-consistency training loop for a Causal DiT, including forward-rollout scheduling, temporal reversal of frames and controls, reverse-causal masking, and flow-matching loss integration; conducted training and evaluation on RealEstate10K, UE Engine, and Minecraft.</li>
    <li><strong>GeometryWAM — World Action Model for Embodied Manipulation</strong>: Designed a world-action DiT using privileged depth and 3D targets during training, with asymmetric attention masking policy queries from geometry inputs at deployment.</li>
    <li><strong>WorldCast</strong> (ICLR 2027 submission, first author): Led a distributed multiplayer world model using scene-time synchronization, cross-player communication, shared latent memory, and private-view decoding to maintain cross-view consistency under simultaneous actions.</li>
    <li><strong>Iso-WAM</strong> (ICLR 2027 submission): Contributed to a world-action model that isolates action-induced dynamics from visual appearance through a dynamic information bottleneck over DINOv3 and VGGT latent action targets, improving OOD robustness on LIBERO-Plus and real robots.</li>
  </ul>
</div>

# 💼 Internship Experience

<div style="margin-bottom: 1.5em;">
  <div><strong>Didi, Voyager AI Research</strong> &nbsp;·&nbsp; <em>Jun. 2026 – Present</em></div>
  <div style="color:#666; margin: 2px 0;">Intern &nbsp;|&nbsp; Mentor: <a href="https://shishaoshuai.com/">Shaoshuai Shi</a> &nbsp;|&nbsp; Guangzhou, China</div>
  <ul style="margin-top: 6px;">
    <li>Developing Vision-Language-Action (VLA) systems for complex real-robot manipulation tasks.</li>
  </ul>
</div>

# 🎖 Honors and Awards
- *2026* &nbsp; **Honorable Mention, Mathematical Contest in Modeling (MCM)**
  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;COMAP
- *2025* &nbsp; **Academic Scholarship & Second-Class Scholarship**
  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Jilin University
- *2024* &nbsp; **Outstanding Student Leader & Second-Class Scholarship**
  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Jilin University
