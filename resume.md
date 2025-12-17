---
layout: page
title: "Academic Resume"
permalink: /resume/
---

  <!-- =============== 新增导航栏 =============== -->
  <nav class="navbar">
    <a href="/" class="active">Home</a>
    <a href="/resume/">Resume</a>
    <a href="/publications/">Publications</a>
    <a href="/preprints/">Preprints</a>
    <a href="/courses/">Courses</a>
    <a href="/notes/">Notes</a>
  </nav>
  <!-- =============== 导航栏结束 =============== -->

<div class="math-resume">
  <header class="resume-header">
    <h1>Bao Shijie (包 诗界)</h1>
    
    <div class="contact-info">
      <p>✉️ <a href="mailto:bsjie@amss.ac.cn">bsjie@amss.ac.cn</a> | <a href="mailto:baoshijie96@gmail.com">baoshijie96@gmail.com</a></p>
      <p>📍 411 Room, Siyuan Building, No.55 Zhongguancun East Road, Beijing, China</p>
      <p> <a href="https://orcid.org/0000-0002-6781-2316">ORCID</a> | <a href="https://scholar.google.com/citations?user=FKbOyUAAAAAJ">Google Scholar</a> | <a href="https://www.researchgate.net/profile/Shijie-Bao-3">ResearchGate</a> | <a href="https://mathscinet.ams.org/mathscinet/author?authorId=1534515">MathSci</a></p>
    </div>
    
    <!-- 专业附件区 - 数学工作者必备 -->
    <div class="attachments">
      <a href="/assets/resume/CV_Shijie_Bao.pdf" class="btn" download>
        📥 CV
      </a>
    </div>
  </header>

  <!-- 研究领域摘要 - 多复变函数专家定位 -->
  <section class="research-focus">
    <h2>🔬 Research Profile</h2>
    <p>Specialized in <strong>Several Complex Variables and Algebraic Geometry</strong> with focus on:</p>
    <ul>
      <li>Multiplier ideal sheaves and strong openness property</li>
      <li>L² extension problems and Suita's conjecture</li>
      <li>Concavity properties of minimal L² integrals</li>
      <li>Fiberwise Bergman kernels and log-plurisubharmonicity</li>
    </ul>
  </section>

  <!-- 当前职位 - 博士后研究员 -->
  <section class="current-position">
    <h2>💼 Current Position</h2>
    <div class="timeline-item">
      <h3>Postdoctoral Fellow</h3>
      <p class="institution">Academy of Mathematics and Systems Science, Chinese Academy of Sciences | July 2022 - Present</p>
      <p>Supervisor: Prof. Xiangyu Zhou | Beijing, China</p>
    </div>
  </section>

  <!-- 教育背景 - 数学界标准格式 -->
  <section class="education">
    <h2>🎓 Education</h2>
    
    <div class="timeline-item">
      <h3>Ph.D. in Mathematics</h3>
      <p class="institution">Peking University, School of Mathematical Sciences | Sep 2017 - Jun 2022</p>
      <p>Advisor: Prof. Qi'an Guan | Thesis: "L² Extension and Effectiveness of Strong Openness Property"</p>
    </div>
    
    <div class="timeline-item">
      <h3>B.Sc. in Mathematics</h3>
      <p class="institution">University of Science and Technology of China | Sep 2013 - Jun 2017</p>
      <p>Thesis: "Hörmander's L² Theorem for Dirac Operator in Complex Clifford Analysis"</p>
    </div>
  </section>

  /* =============== 新增导航栏样式 =============== */
    .navbar {
      display: flex;
      justify-content: center;
      gap: 2rem;
      margin-bottom: 2rem;
      padding-bottom: 0.5rem;
      border-bottom: 1px solid #eaecef;
    }
    
    .navbar a {
      text-decoration: none;
      color: #2c3e50;
      font-weight: bold;
      padding: 0.5rem 1rem;
      border-radius: 4px;
      transition: all 0.3s;
    }
    
    .navbar a:hover {
      background: #f8f9fa;
      color: #e74c3c;
    }
    
    .navbar a.active {
      background: #2c3e50;
      color: white;
    }
    /* =============== 导航栏结束 =============== */
  
<!-- 更新时间戳 - 学术界惯例 -->
  <div class="last-updated">
    Last updated: <time datetime="2024-06-15">June 15, 2024</time>
  </div>
</div>

<!-- 保留原有样式 -->
<style>
.math-resume {
  max-width: 900px;
  margin: 0 auto;
  font-family: 'TeX Gyre Termes', 'Times New Roman', serif;
  line-height: 1.6;
  color: #333;
  padding: 20px;
}

.resume-header {
  text-align: center;
  padding: 2rem 0;
  border-bottom: 1px solid #eaecef;
  margin-bottom: 2rem;
}

.contact-info {
  font-size: 0.95rem;
  margin: 1.2rem 0;
  line-height: 1.4;
}

.attachments {
  display: flex;
  justify-content: center;
  gap: 15px;
  margin-top: 1rem;
  flex-wrap: wrap;
}

.btn {
  display: inline-block;
  padding: 0.6rem 1.2rem;
  background: #2c3e50;
  color: white;
  text-decoration: none;
  border-radius: 4px;
  font-weight: bold;
  transition: all 0.3s;
  min-width: 220px;
  text-align: center;
}

.btn:hover {
  background: #3498db;
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
}

.timeline-item {
  margin-bottom: 1.8rem;
  padding-left: 1.8rem;
  border-left: 2px solid #3498db;
  position: relative;
}

.timeline-item:before {
  content: "";
  position: absolute;
  left: -6px;
  top: 8px;
  width: 10px;
  height: 10px;
  border-radius: 50%;
  background: #e74c3c;
  border: 2px solid #c0392b;
}

.research-focus {
  background: #f8f9fa;
  padding: 1.2rem;
  border-radius: 8px;
  border-left: 3px solid #e74c3c;
  margin-bottom: 2rem;
}

.contribution-highlight {
  background: #fff8e6;
  padding: 0.8rem;
  border-left: 3px solid #ffc107;
  margin: 1rem 0;
  font-style: italic;
}

.last-updated {
  text-align: center;
  margin-top: 2.5rem;
  padding-top: 1rem;
  border-top: 1px dashed #eaecef;
  color: #7f8c8d;
  font-size: 0.9rem;
}

/* 数学符号特殊处理 */
sup {
  vertical-align: super;
  font-size: 0.8em;
}

/* 响应式设计 */
@media (max-width: 768px) {
  .resume-header h1 {
    font-size: 1.8rem;
  }
  
  .btn {
    width: 100%;
    margin-bottom: 8px;
  }
  
  .timeline-item {
    padding-left: 1.2rem;
  }
}
</style>
