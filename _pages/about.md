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

I am currently a second-year M.E. student at **Wuhan University** (2027QS: 165, expected graduation: June 2027), supervised by **[Prof. Jianting Ning](https://scholar.google.com/citations?user=HSaFwSwAAAAJ&hl=zh-CN), Prof. Qin Liu**, and **[Prof. Kaitai Liang](https://scholar.google.com/citations?user=_qHKRH4AAAAJ&hl=zh-CN)**. My research interests center on **applied cryptography**, with a particular focus on data and cloud security, as well as IoT security. Prior to this, I obtained my B.E. in Software Engineering from Southwest University (Chongqing) in June 2024, where I was fortunate to work under the guidance of **[Prof. Zheng Yang](https://scholar.google.com/citations?user=X6csOLgAAAAJ&hl=en)** and **[Prof. Jianying Zhou](https://scholar.google.com/citations?user=T-Uf3dYAAAAJ&hl=en)**. To bridge academic knowledge with industrial practice, I completed two six‑month internships: one with the Cybersecurity Engineering & Solutions team at **Logitech**, where I greatly enjoyed the collaborative environment with friends around the world, and another at **iFLYTEK**. These experiences deepened my understanding of real‑world security challenges and strengthened my collaborative skills. I am always open to academic discussions and potential collaborations. Feel free to reach out to me at [kk96500927@gmail.com](mailto:kk96500927@gmail.com) or [baxijie@whu.edu.cn](mailto:baxijie@whu.edu.cn).

---

<span class='anchor' id='news'></span>
# 📰 News

- **2026.06**: 🎉 Started a six‑month internship with the Cybersecurity Engineering & Solutions team at Logitech.

---

<span class='anchor' id='educations'></span>
# 📖 Educations

- **2024.09 – 2027.06 (expected)**, M.E. in Cyber Science, Wuhan University (GPA: 90.42/100)
- **2020.09 – 2024.06**, B.E. in Software Engineering, Southwest University & Deakin University (GPA: 87.08/100)
- **Language**: English (IELTS 7.0: Listening 8.0, Reading 7.0, Writing 7.0, Speaking 6.5)

---

<span class='anchor' id='internships'></span>
# 💻 Internships

- **2026.06 – 2026.11 (expected)** – Logitech (6 months) – Cybersecurity Engineering & Solutions
- **2023.02 - 2023.07** – iFLYTEK (6 months) – Front‑End Development

---

<span class='anchor' id='publications'></span>
# 📝 Publications

<!-- 按时间从新到旧排列 -->

<!-- TeeLSM-RAG: 无图片，文字占满，无链接（未发表） -->
<div class='paper-box'><div class='paper-box-text' style="width: 100%;" markdown="1">

**TeeLSM-RAG: Authenticated Retrieval with Log-Structured Indexing for RAG** **(In Progress)**

**Xijie Ba**, Jianting Ning, Kaitai Liang, Qin Liu*
</div>
</div>

<!-- VS3E: 有图片，无链接（未发表，Under Revision） -->
<div class='paper-box'><div class='paper-box-image'><div><div class="badge">TIFS (Under Revision)</div><img src='images/截屏2026-06-28 11.53.04.png' alt="VS3E scheme" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

**VS3E: Verifiable Substring-Searchable Symmetric Encryption** **(TIFS Under Revision)**

**Xijie Ba**, Yifeng Dai, Qin Liu, Jianting Ning*, Qiyu Liu

- This paper introduces the first verifiable substring-SSE scheme, which operates under the malicious server model. By leveraging a Merkle tree to prevent false positives and an RSA accumulator to eliminate false negatives, the scheme ensures the integrity of query results. The scheme employs blinding techniques to defend leakage abuse attacks. Experiments demonstrate that the client-side computational and spatial overhead remains within practical limits.
</div>
</div>

<!-- K-Opt: 有图片，无链接（未发表，Major Revision） -->
<div class='paper-box'><div class='paper-box-image'><div><div class="badge">TC (Major Revision)</div><img src='images/截屏2026-06-28 11.53.33.png' alt="K-Opt scheme" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

**Optimal Grouping of Encrypted KV Stores for Achieving K-Indistinguishable Data Accesses with Minimum Bandwidth Cost** **(TC Major Revision)**

Qiuyu Hu, **Xijie Ba**, Qin Liu*, Zhenyu Chai, Peng Li*

- This paper proposes K-Opt, a dynamic programming-based scheme for encrypted key-value storage that mitigates access pattern leakage by grouping data into K-indistinguishable clusters, minimizing bandwidth overhead while supporting secure dynamic updates. Experimental validation confirms reduced bandwidth costs without compromising security.
</div>
</div>

<!-- 已发表三篇，均有图片和链接 -->
<div class='paper-box'><div class='paper-box-image'><div><div class="badge">Inscrypt 2025</div><img src='images/截屏2026-06-28 11.24.34.png' alt="Leakage-Abuse Attack" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[Leakage-Abuse Attack Against Substring-SSE with Partially Known Dataset](https://link.springer.com/chapter/10.1007/978-981-95-6206-0_28) **Inscrypt 2025**

**Xijie Ba**, Qin Liu*, Xiaohong Li, Jianting Ning

- This paper proposes the first leakage-abuse attack against substring-SSE under partially-known-data settings. By extending the LEAP framework with a matrix-based correlation technique, we efficiently recover plaintext from encrypted suffix trees using known data fragments. Experiments achieve 98.32% recovery with 50% auxiliary knowledge, exposing critical vulnerabilities in existing schemes and highlighting the need for leakage-resilient designs.
</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">MSN 2023</div><img src='images/截屏2026-06-28 11.27.52.png' alt="Zone Authentication" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[A Lightweight Zone Authentication Scheme with Auto-Refreshing Pseudonyms for C-V2X](https://ieeexplore.ieee.org/abstract/document/10566958) **MSN 2023**

**Xijie Ba**, Jiaqi Yang, Cong Ma

- This paper proposes zone authentication for C-V2X communications, where vehicles use geographic zone-tied pseudonyms for message signing. Our scheme employs auto-refreshing pseudonyms and hierarchical authorization to reduce overhead while maintaining confidentiality. Evaluation shows superior efficiency over existing methods.
</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">SecureComm 2023</div><img src='images/截屏2026-06-28 11.31.16.png' alt="PLC Authentication" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[Lightweight Intermittent Message Authentication for Programmable Logic Controller](https://link.springer.com/chapter/10.1007/978-3-031-64948-6_12) **SecureComm 2023**

Jiaqi Yang, Jun Xian Chia, **Xijie Ba**, Jianying Zhou*, Zheng Yang*

- This paper introduces an optimized UHF tree for intermittent authentication in Cyber-Physical Systems, reducing synchronization overhead during prolonged interruptions. We implement a lightweight signature scheme on an Allen Bradley PLC using efficient pseudo-Mersenne arithmetic, demonstrating the first practical feasibility of such protocols on industrial hardware with improved performance.
</div>
</div>

---

<span class='anchor' id='honors-and-awards'></span>
# 🎖️ Honors and Awards

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

# ⚙️ Project Experience

- **Research and Application of Technologies for Virtual Currency** (2024–2025)  
  Deployed a functional platform with integrated cryptographic protocols. And developed the frontend component of a custody and control system, providing an interface for managing cryptographic keys.

- **Research and Development of a TEE-Based Computing Platform** (2025–2026)  
  Migrated and deployed ML-DSA and ML-KEM algorithms of varying security levels onto a Trusted Execution Environment (TEE) platform, in strict compliance with the latest PKCS#11 standard.
