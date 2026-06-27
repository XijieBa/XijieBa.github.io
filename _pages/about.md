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

<!-- 点赞 + 评论区域（若需移至侧边栏，请修改主题布局文件） -->
<div style="margin-top: 1.5rem; padding: 1rem; border: 1px solid #eee; border-radius: 8px; background: #fafafa;">
  <p style="margin: 0 0 0.5rem 0; font-weight: bold;">
    <span style="font-size: 1.2rem;">❤️</span> 
    <span id="likeCount">0</span> likes · 
    <button id="likeBtn" style="background: #1a73e8; color: white; border: none; padding: 4px 14px; border-radius: 16px; cursor: pointer; font-size: 0.9rem;">👍 Like</button>
  </p>
  <div id="flagContainer" style="display: flex; flex-wrap: wrap; align-items: center; gap: 0; margin-bottom: 0.8rem; min-height: 30px;"></div>
  <div style="margin-top: 0.8rem;">
    <textarea id="commentInput" rows="2" style="width: 100%; box-sizing: border-box; border: 1px solid #ccc; border-radius: 4px; padding: 6px; font-size: 0.9rem;" placeholder="Write a comment (anonymous)..."></textarea>
    <button id="commentBtn" style="margin-top: 4px; background: #34a853; color: white; border: none; padding: 4px 16px; border-radius: 16px; cursor: pointer; font-size: 0.9rem;">Post Comment</button>
  </div>
  <div id="commentList" style="margin-top: 0.8rem; max-height: 200px; overflow-y: auto; font-size: 0.9rem; border-top: 1px solid #e0e0e0; padding-top: 0.5rem;"></div>
</div>

<!-- Firebase + 点赞/评论逻辑（请将下方配置替换为您自己的 Firebase 项目信息） -->
<script src="https://www.gstatic.com/firebasejs/9.23.0/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/9.23.0/firebase-database-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/9.23.0/firebase-auth-compat.js"></script>
<script>
  // ========== 你的 Firebase 配置（必须替换） ==========
  const firebaseConfig = {
    apiKey: "你的-apiKey",
    authDomain: "你的-authDomain",
    databaseURL: "你的-databaseURL",
    projectId: "你的-projectId",
    storageBucket: "你的-storageBucket",
    messagingSenderId: "你的-messagingSenderId",
    appId: "你的-appId"
  };
  // =================================================

  firebase.initializeApp(firebaseConfig);
  const auth = firebase.auth();
  const db = firebase.database();

  auth.signInAnonymously().catch(console.error);

  async function getCountry() {
    try {
      const res = await fetch('https://ipapi.co/json/');
      const data = await res.json();
      return data.country_code?.toLowerCase() || 'unknown';
    } catch {
      return 'unknown';
    }
  }

  function renderFlags(likeData) {
    const container = document.getElementById('flagContainer');
    container.innerHTML = '';
    const countryCount = {};
    if (likeData) {
      Object.values(likeData).forEach(entry => {
        const c = entry.country || 'unknown';
        countryCount[c] = (countryCount[c] || 0) + 1;
      });
    }
    const sorted = Object.entries(countryCount).sort((a, b) => b[1] - a[1]);
    if (sorted.length === 0) {
      container.innerHTML = '<span style="color: #999; font-size: 0.85rem;">No likes yet</span>';
      return;
    }
    const priority = ['cn', 'ch', 'us', 'in', 'ie', 'tw'];
    sorted.sort((a, b) => {
      const pa = priority.includes(a[0]) ? 0 : 1;
      const pb = priority.includes(b[0]) ? 0 : 1;
      return pa - pb || b[1] - a[1];
    });
    const total = sorted.length;
    sorted.forEach(([code, count], index) => {
      const img = document.createElement('img');
      img.src = `https://flagcdn.com/w20/${code}.png`;
      img.alt = code;
      img.title = `${code.toUpperCase()} (${count} likes)`;
      img.style.width = '30px';
      img.style.height = '30px';
      img.style.borderRadius = '50%';
      img.style.border = '2px solid white';
      img.style.boxShadow = '0 0 2px rgba(0,0,0,0.3)';
      img.style.objectFit = 'cover';
      img.style.marginLeft = (index === 0) ? '0' : '-10px';
      img.style.position = 'relative';
      img.style.zIndex = total - index;
      container.appendChild(img);
    });
  }

  function updateLikeCount(likeData) {
    const count = likeData ? Object.keys(likeData).length : 0;
    document.getElementById('likeCount').textContent = count;
    renderFlags(likeData);
  }

  db.ref('likes').on('value', snap => {
    const data = snap.val() || {};
    updateLikeCount(data);
  });

  document.getElementById('likeBtn').addEventListener('click', async () => {
    const user = auth.currentUser;
    if (!user) { alert('Please wait for anonymous login.'); return; }
    const country = await getCountry();
    db.ref('likes').push({
      uid: user.uid,
      country: country,
      timestamp: firebase.database.ServerValue.TIMESTAMP
    }).catch(console.error);
  });

  db.ref('comments').orderByChild('timestamp').limitToLast(20).on('value', snap => {
    const data = snap.val();
    const list = document.getElementById('commentList');
    list.innerHTML = '';
    if (!data) {
      list.innerHTML = '<div style="color: #999; font-size: 0.85rem;">No comments yet.</div>';
      return;
    }
    const items = Object.values(data).reverse();
    items.forEach(item => {
      const div = document.createElement('div');
      div.style.borderBottom = '1px solid #eee';
      div.style.padding = '4px 0';
      const flag = item.country ? `https://flagcdn.com/w20/${item.country}.png` : '';
      div.innerHTML = `
        <span style="font-weight: bold;">${item.name || 'Anonymous'}</span>
        ${flag ? `<img src="${flag}" style="width:18px;height:12px;border-radius:2px;margin:0 4px;">` : ''}
        <span style="font-size:0.8rem;color:#888;">${new Date(item.timestamp).toLocaleString()}</span>
        <br><span>${item.text}</span>
      `;
      list.appendChild(div);
    });
  });

  document.getElementById('commentBtn').addEventListener('click', async () => {
    const input = document.getElementById('commentInput');
    const text = input.value.trim();
    if (!text) return;
    const user = auth.currentUser;
    if (!user) { alert('Please wait for anonymous login.'); return; }
    const country = await getCountry();
    db.ref('comments').push({
      uid: user.uid,
      text: text,
      country: country,
      timestamp: firebase.database.ServerValue.TIMESTAMP,
      name: 'Visitor'
    }).then(() => {
      input.value = '';
    }).catch(console.error);
  });
</script>

---

<span class='anchor' id='news'></span>
# 📰 News

<!-- News 内容暂时留空，待后续更新 -->

---

<span class='anchor' id='educations'></span>
# 📖 Educations

- **2024.09 – 2027.06 (expected)**, M.E. in Cyber Science, Wuhan University (GPA: 90.42/100)
- **2020.09 – 2024.06**, B.E. in Software Engineering, Southwest University & Deakin University (GPA: 87.08/100)
- **Language**: English (IELTS 7.0: Listening 8.0, Reading 7.0, Writing 7.0, Speaking 6.5)

---

<span class='anchor' id='internships'></span>
# 💻 Internships

- **2026.06** – Logitech (6 months) – Cybersecurity Engineering & Solutions
- **2023.07** – iFLYTEK (6 months) – Front‑End Development

---

<span class='anchor' id='publications'></span>
# 📝 Publications

<!-- 按时间从新到旧排列，所有论文统一使用 paper-box 格式 -->

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">TIFS (Under Revision)</div><img src='images/500x300.png' alt="VS3E scheme" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[VS3E: Verifiable Substring-Searchable Symmetric Encryption](https://ieeexplore.ieee.org/xpl/RecentIssue.jsp?punumber=10206) **(Under Revision)**

**Xijie Ba**, Yifeng Dai, Qin Liu, Jianting Ning*, Qiyu Liu

- This paper introduces the first verifiable substring-SSE scheme, which operates under the malicious server model. By leveraging a Merkle tree to prevent false positives and an RSA accumulator to eliminate false negatives, the scheme ensures the integrity of query results. The scheme employs blinding techniques to defend leakage abuse attacks. Experiments demonstrate that the client-side computational and spatial overhead remains within practical limits.
</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">TC (Major Revision)</div><img src='images/500x300.png' alt="K-Opt scheme" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[Optimal Grouping of Encrypted KV Stores for Achieving K-Indistinguishable Data Accesses with Minimum Bandwidth Cost](https://ieeexplore.ieee.org/xpl/RecentIssue.jsp?punumber=10206) **(Major Revision)**

Qiuyu Hu, **Xijie Ba**, Qin Liu*, Zhenyu Chai, Peng Li*

[**Project**](https://scholar.google.com) <strong><span class='show_paper_citations' data='DhtAFkwAAAAJ:ALROH1vI_8AC'></span></strong>
- This paper proposes K-Opt, a dynamic programming-based scheme for encrypted key-value storage that mitigates access pattern leakage by grouping data into K-indistinguishable clusters, minimizing bandwidth overhead while supporting secure dynamic updates. Experimental validation confirms reduced bandwidth costs without compromising security.
</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">Inscrypt 2025</div><img src='images/500x300.png' alt="Leakage-Abuse Attack" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[Leakage-Abuse Attack Against Substring-SSE with Partially Known Dataset](https://link.springer.com/chapter/10.1007/978-981-95-6206-0_28) **Inscrypt 2025**

**Xijie Ba**, Qin Liu*, Xiaohong Li, Jianting Ning

- This paper proposes the first leakage-abuse attack against substring-SSE under partially-known-data settings. By extending the LEAP framework with a matrix-based correlation technique, we efficiently recover plaintext from encrypted suffix trees using known data fragments. Experiments achieve 98.32% recovery with 50% auxiliary knowledge, exposing critical vulnerabilities in existing schemes and highlighting the need for leakage-resilient designs.
</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">MSN 2023</div><img src='images/500x300.png' alt="Zone Authentication" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[A Lightweight Zone Authentication Scheme with Auto-Refreshing Pseudonyms for C-V2X](https://ieeexplore.ieee.org/abstract/document/10566958) **MSN 2023**

**Xijie Ba**, Jiaqi Yang, Cong Ma

- This paper proposes zone authentication for C-V2X communications, where vehicles use geographic zone-tied pseudonyms for message signing. Our scheme employs auto-refreshing pseudonyms and hierarchical authorization to reduce overhead while maintaining confidentiality. Evaluation shows superior efficiency over existing methods.
</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">SecureComm 2023</div><img src='images/500x300.png' alt="PLC Authentication" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[Lightweight Intermittent Message Authentication for Programmable Logic Controller](https://link.springer.com/chapter/10.1007/978-3-031-64948-6_12) **SecureComm 2023**

Jiaqi Yang, Jun Xian Chia, **Xijie Ba**, Jianying Zhou*, Zheng Yang*

- This paper introduces an optimized UHF tree for intermittent authentication in Cyber-Physical Systems, reducing synchronization overhead during prolonged interruptions. We implement a lightweight signature scheme on an Allen Bradley PLC using efficient pseudo-Mersenne arithmetic, demonstrating the first practical feasibility of such protocols on industrial hardware with improved performance.
</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">In Progress</div><img src='images/500x300.png' alt="TeeLSM-RAG" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[TeeLSM-RAG: Authenticated Retrieval with Log-Structured Indexing for RAG]() **(In Progress)**

**Xijie Ba**, Jianting Ning, Kaitai Liang, Qin Liu*

- This paper proposes a log-structured and authenticated retrieval framework for dynamic RAG systems, leveraging TEE to ensure integrity and authenticity of query results. The scheme integrates log-structured merge trees with cryptographic accumulators to support efficient and verifiable dynamic updates.
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
