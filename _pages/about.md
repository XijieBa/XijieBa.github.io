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

I am currently a second-year M.E. student at Wuhan University (expected graduation: June 2027), supervised by [Prof. Jianting Ning](https://scholar.google.com/citations?user=HSaFwSwAAAAJ&hl=zh-CN), Prof. Qin Liu, and [Prof. Kaitai Liang](https://scholar.google.com/citations?user=_qHKRH4AAAAJ&hl=zh-CN). My research interests center on applied cryptography, with a particular focus on data and cloud security, as well as IoT security. Prior to this, I obtained my B.E. in Software Engineering from Southwest University (Chongqing) in June 2024, where I was fortunate to work under the guidance of [Prof. Zheng Yang](https://scholar.google.com/citations?user=X6csOLgAAAAJ&hl=en) and [Prof. Jianying Zhou](https://scholar.google.com/citations?user=T-Uf3dYAAAAJ&hl=en). To bridge academic knowledge with industrial practice, I completed two six‑month internships: one with the cybersecurity team at Logitech (mentored by [Tana Dubel](https://globalcyberconference.com/conference-speakers/tana-dubel/)) and another at iFLYTEK. These experiences deepened my understanding of real‑world security challenges and strengthened my collaborative skills. I am always open to academic discussions and potential collaborations. Feel free to reach out to me at [kk96500927@gmail.com](mailto:kk96500927@gmail.com) or [baxijie@whu.edu.cn](mailto:baxijie@whu.edu.cn).

# 📝 Publications 

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">TIFS (Under Revision)</div><img src='images/500x300.png' alt="VS3E Scheme" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[VS3E: Verifiable Substring-Searchable Symmetric Encryption](https://ieeexplore.ieee.org/xpl/RecentIssue.jsp?punumber=10206) **(Under Revision)**

**Xijie Ba**, Yifeng Dai, Qin Liu, Jianting Ning*, Qiyu Liu

[**Project**](https://scholar.google.com) <strong><span class='show_paper_citations' data='DhtAFkwAAAAJ:ALROH1vI_8AC'></span></strong>
- This paper introduces the first verifiable substring-SSE scheme, which operates under the malicious server model. By leveraging a Merkle tree to prevent false positives and an RSA accumulator to eliminate false negatives, the scheme ensures the integrity of query results. The scheme employs blinding techniques to defend leakage abuse attacks. Experiments demonstrate that the client-side computational and spatial overhead remains within practical limits.
</div>
</div>

### 📄 Under Review / Major Revision

- [Optimal Grouping of Encrypted KV Stores for Achieving K-Indistinguishable Data Accesses with Minimum Bandwidth Cost](https://ieeexplore.ieee.org/xpl/RecentIssue.jsp?punumber=10206) **(TC, Major Revision)**, Qiuyu Hu, **Xijie Ba**, Qin Liu*, Zhenyu Chai, Peng Li*. 
  *This paper proposes K-Opt, a dynamic programming-based scheme for encrypted key-value storage that mitigates access pattern leakage by grouping data into K-indistinguishable clusters, minimizing bandwidth overhead while supporting secure dynamic updates.*

### 🗂️ Published Conference Papers

- [Leakage-Abuse Attack Against Substring-SSE with Partially Known Dataset](https://link.springer.com/conference/inscrypt) **Inscrypt 2025**, **Xijie Ba**, Qin Liu*, Xiaohong Li, Jianting Ning. 
  *This paper proposes the first leakage-abuse attack against substring-SSE under partially-known-data settings. By extending the LEAP framework with a matrix-based correlation technique, we efficiently recover plaintext from encrypted suffix trees using known data fragments. Experiments achieve 98.32% recovery with 50% auxiliary knowledge.*

- [A Lightweight Zone Authentication Scheme with Auto-Refreshing Pseudonyms for C-V2X](https://ieeexplore.ieee.org/xpl/conhome/1002628/all-proceedings) **MSN 2023**, **Xijie Ba**, Jiaqi Yang, Cong Ma. 
  *This paper proposes zone authentication for C-V2X communications, where vehicles use geographic zone-tied pseudonyms for message signing. Our scheme employs auto-refreshing pseudonyms and hierarchical authorization to reduce overhead while maintaining confidentiality.*

- [Lightweight Intermittent Message Authentication for Programmable Logic Controller](https://eudl.eu/proceedings/SECURECOMM) **SecureComm 2023**, Jiaqi Yang, Jun Xian Chia, **Xijie Ba**, Jianying Zhou*, Zheng Yang*. 
  *This paper introduces an optimized UHF tree for intermittent authentication in Cyber-Physical Systems, reducing synchronization overhead during prolonged interruptions. We implement a lightweight signature scheme on an Allen Bradley PLC using efficient pseudo-Mersenne arithmetic, demonstrating the first practical feasibility of such protocols on industrial hardware.*
  
