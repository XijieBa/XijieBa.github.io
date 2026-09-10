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

I am currently a second-year M.E. student at **Wuhan University** (2027QS: 165, expected graduation: June 2027), supervised by **[Prof. Jianting Ning](https://scholar.google.com/citations?user=HSaFwSwAAAAJ&hl=zh-CN), Prof. Qin Liu**, and **[Prof. Kaitai Liang](https://scholar.google.com/citations?user=_qHKRH4AAAAJ&hl=zh-CN)**. My research interests center on **applied cryptography**, with a particular focus on data and cloud security, as well as IoT security. Prior to this, I obtained my B.E. in Software Engineering from Southwest University (Chongqing) in June 2024, where I was fortunate to work under the guidance of **[Prof. Zheng Yang](https://scholar.google.com/citations?user=X6csOLgAAAAJ&hl=en)** and **[Prof. Jianying Zhou](https://scholar.google.com/citations?user=T-Uf3dYAAAAJ&hl=en)**. To bridge academic knowledge with industrial practice, I completed two six‑month internships: one with the Cybersecurity Engineering & Solutions team at **Logitech**, where I greatly enjoyed the collaborative environment with friends around the world, and another at **iFLYTEK**. These experiences deepened my understanding of real‑world security challenges and strengthened my collaborative skills. I am always open to academic discussions and collaborations. Feel free to reach out to me at [baxijie.me@gmail.com](mailto:baxijie.me@gmail.com) or [baxijie@whu.edu.cn](mailto:baxijie@whu.edu.cn).

---

<span class='anchor' id='news'></span>
# 📰 News

- **2026.06**: 🎉 Started internship with the Cybersecurity Engineering & Solutions team at Logitech.

---

<span class='anchor' id='educations'></span>
# 📖 Educations

- **2024.09 – 2027.06 (expected)**, M.E. in Cyber Science, Wuhan University (GPA: 90.42/100)
- **2020.09 – 2024.06**, B.E. in Software Engineering, Southwest University & Deakin University (GPA: 87.08/100)
- **Language**: English (IELTS 7.0: Listening 8.0, Reading 7.0, Writing 7.0, Speaking 6.5)

---

<span class='anchor' id='internships'></span>
# 💻 Internships

- **2026.06 – 2026.11 (expected)** – Logitech – Cybersecurity Engineering & Solutions
- **2023.02 - 2023.07** – iFLYTEK – Front‑End Development

---

<span class='anchor' id='publications'></span>
# 📝 Publications

<!-- 按时间从新到旧排列 -->

<!-- ADRC: 有图片，无链接，无链接（未发表） -->
<div class='paper-box'><div class='paper-box-image'><div><div class="badge">Usenix FAST 2027 (Under Review)</div><img src='images/截屏2026-09-04 10.27.28.png' alt="ADRC scheme" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

**ADRC: Attested Dynamic RAG State Commitments**

**Xijie Ba**, Jianting Ning, Qin Liu*, Kaitai Liang

- This paper presents ADRC, a verifiable state‑commitment framework for RAG pipelines in the untrusted cloud model, using an append‑only transparency log for freshness and an out‑of‑core LSM‑tree for dynamic updates. Decoupled TEE enclaves and contextual metadata binding mitigate state rollback and ciphertext relocation. Evaluation indicates update overhead approaches constant‑time log append and retrieval latency stays practical.
</div>
</div>

<!-- VS3E: 有图片，无链接（未发表，Under Revision） -->
<div class='paper-box'><div class='paper-box-image'><div><div class="badge">TIFS (Under Review)</div><img src='images/截屏2026-06-28 11.53.04.png' alt="VS3E scheme" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

**VS3E: Verifiable Substring-Searchable Symmetric Encryption** **(TIFS Under Review)**

**Xijie Ba**, Yifeng Dai, Qin Liu, Jianting Ning*, Qiyu Liu

- This paper presents the first verifiable substring‑SSE scheme designed for the malicious server model. The construction integrates a Merkle tree to resist false positives and an RSA accumulator to resist false negatives, thereby providing result integrity. Blinding techniques are incorporated to mitigate leakage‑abuse attacks. Experimental evaluation indicates that the client‑side computational and storage costs remain within practical bounds.
</div>
</div>

<!-- K-Opt: 有图片，无链接 -->
<div class='paper-box'><div class='paper-box-image'><div><div class="badge">IEEE TC</div><img src='images/截屏2026-06-28 11.53.33.png' alt="K-Opt scheme" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

**Optimal Grouping of Encrypted KV Stores for Achieving K-Indistinguishable Data Accesses with Minimum Bandwidth Cost** **IEEE TC**

Qiuyu Hu, **Xijie Ba**, Qin Liu*, Zhenyu Chai, Peng Li*

- This paper proposes K‑Opt, a dynamic programming‑based scheme for encrypted key‑value storage. The scheme groups data into K‑indistinguishable clusters to reduce access pattern leakage and supports dynamic updates. Experimental results indicate a reduction in bandwidth overhead while the security properties remain preserved.
</div>
</div>

<!-- 已发表三篇，均有图片和链接 -->
<div class='paper-box'><div class='paper-box-image'><div><div class="badge">Inscrypt 2025</div><img src='images/截屏2026-06-28 11.24.34.png' alt="Leakage-Abuse Attack" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[Leakage-Abuse Attack Against Substring-SSE with Partially Known Dataset](https://link.springer.com/chapter/10.1007/978-981-95-6206-0_28) **Inscrypt 2025**

**Xijie Ba**, Qin Liu*, Xiaohong Li, Jianting Ning

- This paper presents a leakage‑abuse attack against substring‑SSE in the partially‑known‑data setting. The attack extends the LEAP framework with a matrix‑based correlation technique to recover plaintext from encrypted suffix trees using known data fragments. Experiments recover 98.32% of the plaintext with 50% auxiliary knowledge. The results point to vulnerabilities in existing schemes and suggest the need for leakage‑resilient designs.
</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">MSN 2023</div><img src='images/截屏2026-06-28 11.27.52.png' alt="Zone Authentication" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[A Lightweight Zone Authentication Scheme with Auto-Refreshing Pseudonyms for C-V2X](https://ieeexplore.ieee.org/abstract/document/10566958) **MSN 2023**

**Xijie Ba**, Jiaqi Yang, Cong Ma

- This paper proposes zone authentication for C‑V2X communications, where vehicles use geographic zone‑tied pseudonyms for message signing. The scheme employs auto‑refreshing pseudonyms and hierarchical authorization to reduce overhead and provide confidentiality. Evaluation indicates that the scheme offers efficiency gains over existing methods.
</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">SecureComm 2023</div><img src='images/截屏2026-06-28 11.31.16.png' alt="PLC Authentication" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[Lightweight Intermittent Message Authentication for Programmable Logic Controller](https://link.springer.com/chapter/10.1007/978-3-031-64948-6_12) **SecureComm 2023**

Jiaqi Yang, Jun Xian Chia, **Xijie Ba**, Jianying Zhou*, Zheng Yang*

- This paper introduces an optimized UHF tree for intermittent authentication in Cyber‑Physical Systems. The tree reduces synchronization overhead during prolonged interruptions. A lightweight signature scheme is implemented on an Allen Bradley PLC using efficient pseudo‑Mersenne arithmetic. This implementation demonstrates the practical feasibility of such protocols on industrial hardware and shows performance improvements.
</div>
</div>

---

<span class='anchor' id='honors-and-awards'></span>
# 🎖️ Honors and Awards

- **2026** – Excellence Scholarship, Wuhan University
- **2026** – Extraordinary Scholarship, Wuhan University
- **2025** – Outstanding Graduate Student, Wuhan University
- **2025** – Social Activist, Wuhan University
- **2025** – National Third Prize, "Challenge Cup" National College Student Competition (Enhanced e‑Passport)
- **2025** – Provincial Grand Prize, "Challenge Cup" Competition (Enhanced e‑Passport)
- **2025** – University Grand Prize, "Challenge Cup" Competition (Enhanced e‑Passport)
- **2024** – Outstanding Undergraduate Graduate, Southwest University
- **2024** – National Second Prize, National Cryptography Technology Competition (Embedded Secure Element OS)
- **2024** – Outstanding Freshman Scholarship, Wuhan University
- **2023** – National Third Prize, National Cryptography Technology Competition (Lightweight Signature for PLCs)
- **2023** – National Encouragement Scholarship of China
- **2023** – National Second Prize, Chinese Collegiate Computing Competition (HanYi Pavilion VR Museum)
- **2023** – Merit Student, Southwest University
- **2022** – First‑Class Scholarship, Southwest University
- **2022** – Second Prize, Chinese Mathematics Competitions for College Students
- **2022** – Academic Excellence Award, Southwest University
- **2022** – Merit Student, Southwest University
- **2021** – First‑Class Scholarship, Southwest University
- **2021** – Second Prize, China Undergraduate Mathematical Contest in Modeling
- **2021** – Volunteer Service Award, Southwest University
- **2021** – Merit Student, Southwest University

---

<span class='anchor' id='project-experience'></span>
# ⚙️ Project Experience

- **Research and Application of Technologies for Virtual Currency** (2024–2025)  
  Deployed a functional platform with integrated cryptographic protocols. And developed the frontend component of a custody and control system, providing an interface for managing cryptographic keys.

- **Research and Development of a TEE-Based Computing Platform** (2025–2026)  
  Migrated and deployed ML-DSA and ML-KEM algorithms of varying security levels onto a Trusted Execution Environment (TEE) platform, in strict compliance with the latest PKCS#11 standard.
