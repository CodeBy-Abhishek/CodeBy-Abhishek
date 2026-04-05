<!-- <img width="1440" height="640" alt="image" src="https://github.com/user-attachments/assets/e735d2a6-2429-4858-9c8f-a9f965e027b1" /><!-- ═══════════════════════════════════════════════════════════ --> 
<!--                    HEADER WAVE BANNER                      -->
<!-- ═══════════════════════════════════════════════════════════ -->

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Abhishek Yadav — AI Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Space+Mono:wght@400;700&family=Rajdhani:wght@300;400;600;700&display=swap" rel="stylesheet"/>
<style>
  *{margin:0;padding:0;box-sizing:border-box}
  html,body{width:100%;height:100%;overflow:hidden;background:#020408}

  #canvas{
    position:absolute;inset:0;width:100%;height:100%;
    z-index:0;
  }

  .overlay{
    position:absolute;inset:0;z-index:1;
    background:
      radial-gradient(ellipse 80% 60% at 50% 50%, transparent 30%, #020408 100%),
      repeating-linear-gradient(0deg, transparent, transparent 3px, rgba(0,255,200,0.015) 3px, rgba(0,255,200,0.015) 4px);
    pointer-events:none;
  }

  .scanlines{
    position:absolute;inset:0;z-index:2;
    background:repeating-linear-gradient(
      to bottom,
      transparent 0px,transparent 1px,
      rgba(0,0,0,0.12) 1px,rgba(0,0,0,0.12) 2px
    );
    pointer-events:none;animation:scan 8s linear infinite;
  }
  @keyframes scan{
    0%{background-position:0 0}
    100%{background-position:0 100vh}
  }

  .container{
    position:relative;z-index:3;
    width:100%;height:100%;
    display:flex;flex-direction:column;
    align-items:center;justify-content:center;
    padding:2rem;
    text-align:center;
  }

  /* --- top badge --- */
  .badge{
    font-family:'Space Mono',monospace;
    font-size:11px;letter-spacing:4px;
    color:#00ffc8;text-transform:uppercase;
    border:1px solid rgba(0,255,200,0.35);
    padding:6px 18px;border-radius:20px;
    background:rgba(0,255,200,0.06);
    margin-bottom:28px;
    animation:fadeSlide 0.8s ease both;
    box-shadow:0 0 18px rgba(0,255,200,0.18), inset 0 0 12px rgba(0,255,200,0.05);
  }

  /* --- name --- */
  .name-wrap{position:relative;margin-bottom:14px}
  .name{
    font-family:'Orbitron',monospace;
    font-weight:900;
    font-size:clamp(36px,6vw,72px);
    color:#fff;
    letter-spacing:3px;
    line-height:1;
    animation:fadeSlide 0.9s 0.2s ease both;
    position:relative;display:inline-block;
  }
  .name::before,.name::after{
    content:'Abhishek Yadav';
    position:absolute;top:0;left:0;
    width:100%;height:100%;
    font-family:'Orbitron',monospace;font-weight:900;
    font-size:inherit;letter-spacing:3px;
  }
  .name::before{
    color:#00ffc8;clip-path:polygon(0 0,100% 0,100% 35%,0 35%);
    animation:glitch1 4s infinite;left:2px;
  }
  .name::after{
    color:#bf5fff;clip-path:polygon(0 60%,100% 60%,100% 100%,0 100%);
    animation:glitch2 4s infinite;left:-2px;
  }

  @keyframes glitch1{
    0%,90%,100%{transform:translate(0);opacity:0}
    91%{transform:translate(-3px,1px);opacity:0.9}
    93%{transform:translate(3px,-1px);opacity:0.9}
    95%{transform:translate(-2px,2px);opacity:0.7}
    97%{transform:translate(0);opacity:0}
  }
  @keyframes glitch2{
    0%,88%,100%{transform:translate(0);opacity:0}
    89%{transform:translate(4px,-2px);opacity:0.9}
    92%{transform:translate(-3px,1px);opacity:0.8}
    94%{transform:translate(2px,0);opacity:0.6}
    96%{transform:translate(0);opacity:0}
  }

  /* accent line */
  .line-wrap{
    display:flex;align-items:center;justify-content:center;
    gap:14px;margin-bottom:22px;
    animation:fadeSlide 1s 0.4s ease both;
  }
  .h-line{
    height:1px;width:80px;
    background:linear-gradient(to right,transparent,#00ffc8);
  }
  .h-line.right{background:linear-gradient(to left,transparent,#00ffc8)}
  .diamond{
    width:8px;height:8px;
    background:#00ffc8;transform:rotate(45deg);
    box-shadow:0 0 12px #00ffc8,0 0 24px rgba(0,255,200,0.5);
    animation:pulse 2s ease-in-out infinite;
  }
  @keyframes pulse{
    0%,100%{box-shadow:0 0 8px #00ffc8,0 0 18px rgba(0,255,200,0.4)}
    50%{box-shadow:0 0 18px #00ffc8,0 0 36px rgba(0,255,200,0.7)}
  }

  /* --- typewriter role --- */
  .role-wrap{
    font-family:'Rajdhani',sans-serif;
    font-size:clamp(14px,2.2vw,22px);
    font-weight:600;
    letter-spacing:2px;
    color:rgba(255,255,255,0.85);
    margin-bottom:28px;
    height:30px;
    animation:fadeSlide 1s 0.5s ease both;
  }
  .cursor{
    display:inline-block;
    width:2px;height:1em;
    background:#bf5fff;
    margin-left:3px;
    vertical-align:text-bottom;
    animation:blink 0.75s step-end infinite;
  }
  @keyframes blink{0%,100%{opacity:1}50%{opacity:0}}

  /* --- tags --- */
  .tags{
    display:flex;flex-wrap:wrap;
    justify-content:center;gap:10px;
    margin-bottom:36px;
    animation:fadeSlide 1s 0.7s ease both;
  }
  .tag{
    font-family:'Space Mono',monospace;
    font-size:10px;letter-spacing:1.5px;
    padding:5px 14px;border-radius:4px;
    text-transform:uppercase;
    transition:all 0.3s ease;cursor:default;
  }
  .tag.cyan{
    color:#00ffc8;border:1px solid rgba(0,255,200,0.4);
    background:rgba(0,255,200,0.06);
  }
  .tag.violet{
    color:#bf5fff;border:1px solid rgba(191,95,255,0.4);
    background:rgba(191,95,255,0.06);
  }
  .tag.blue{
    color:#5fb4ff;border:1px solid rgba(95,180,255,0.4);
    background:rgba(95,180,255,0.06);
  }
  .tag:hover{transform:translateY(-2px);filter:brightness(1.3)}

  /* --- stats row --- */
  .stats{
    display:flex;gap:clamp(16px,3vw,42px);
    animation:fadeSlide 1s 0.9s ease both;
  }
  .stat{text-align:center}
  .stat-num{
    font-family:'Orbitron',monospace;
    font-weight:700;
    font-size:clamp(18px,2.5vw,28px);
    color:#fff;
    display:block;
    line-height:1;
  }
  .stat-num span{color:#00ffc8}
  .stat-label{
    font-family:'Rajdhani',sans-serif;
    font-size:11px;letter-spacing:2px;
    color:rgba(255,255,255,0.4);
    text-transform:uppercase;
    margin-top:4px;display:block;
  }
  .sep{width:1px;background:rgba(255,255,255,0.1);align-self:stretch}

  /* corner decorations */
  .corner{position:absolute;width:28px;height:28px;z-index:3}
  .corner.tl{top:18px;left:18px;border-top:2px solid #00ffc8;border-left:2px solid #00ffc8}
  .corner.tr{top:18px;right:18px;border-top:2px solid #00ffc8;border-right:2px solid #00ffc8}
  .corner.bl{bottom:18px;left:18px;border-bottom:2px solid rgba(0,255,200,0.4);border-left:2px solid rgba(0,255,200,0.4)}
  .corner.br{bottom:18px;right:18px;border-bottom:2px solid rgba(0,255,200,0.4);border-right:2px solid rgba(0,255,200,0.4)}

  /* coords label */
  .coords{
    position:absolute;bottom:14px;right:52px;
    font-family:'Space Mono',monospace;font-size:9px;
    color:rgba(0,255,200,0.3);letter-spacing:2px;z-index:3;
  }
  .coords-l{
    position:absolute;bottom:14px;left:52px;
    font-family:'Space Mono',monospace;font-size:9px;
    color:rgba(0,255,200,0.3);letter-spacing:2px;z-index:3;
  }

  @keyframes fadeSlide{
    from{opacity:0;transform:translateY(16px)}
    to{opacity:1;transform:translateY(0)}
  }
</style>
</head>
<body>

<canvas id="canvas"></canvas>
<div class="overlay"></div>
<div class="scanlines"></div>

<!-- Corners -->
<div class="corner tl"></div>
<div class="corner tr"></div>
<div class="corner bl"></div>
<div class="corner br"></div>
<div class="coords">26°N 80°E // KANPUR.IN</div>
<div class="coords-l">SYS_ID // AY-2025-BCA</div>

<div class="container">

  <div class="badge">⬡ &nbsp;AI Engineer &nbsp;⬡</div>

  <div class="name-wrap">
    <h1 class="name">Abhishek Yadav</h1>
  </div>

  <div class="line-wrap">
    <div class="h-line"></div>
    <div class="diamond"></div>
    <div class="h-line right"></div>
  </div>

  <div class="role-wrap">
    <span id="typewriter"></span><span class="cursor"></span>
  </div>

  <div class="tags">
    <span class="tag cyan">LangChain</span>
    <span class="tag violet">RAG Pipelines</span>
    <span class="tag cyan">Agentic AI</span>
    <span class="tag blue">LLM Systems</span>
    <span class="tag violet">MCP Architecture</span>
    <span class="tag cyan">FastAPI</span>
    <span class="tag blue">Claude API</span>
    <span class="tag violet">LangGraph</span>
  </div>

  <div class="stats">
    <div class="stat">
      <span class="stat-num"><span>6</span></span>
      <span class="stat-label">Internships</span>
    </div>
    <div class="sep"></div>
    <div class="stat">
      <span class="stat-num"><span>11</span>+</span>
      <span class="stat-label">Certifications</span>
    </div>
    <div class="sep"></div>
    <div class="stat">
      <span class="stat-num"><span>2</span></span>
      <span class="stat-label">Live Projects</span>
    </div>
    <div class="sep"></div>
    <div class="stat">
      <span class="stat-num"><span>∞</span></span>
      <span class="stat-label">Building</span>
    </div>
  </div>

</div>

<script>
/* ── Neural Network Particle Canvas ── */
const cvs = document.getElementById('canvas');
const ctx = cvs.getContext('2d');
let W, H, nodes = [], mouse = {x:-9999,y:-9999};
const NODE_COUNT = 80;
const MAX_DIST = 160;

function resize(){
  W = cvs.width = window.innerWidth;
  H = cvs.height = window.innerHeight;
}
resize();
window.addEventListener('resize', ()=>{ resize(); init(); });
window.addEventListener('mousemove', e=>{ mouse.x=e.clientX; mouse.y=e.clientY; });

class Node{
  constructor(){this.reset(true)}
  reset(init){
    this.x = Math.random()*W;
    this.y = Math.random()*H;
    this.vx = (Math.random()-0.5)*0.4;
    this.vy = (Math.random()-0.5)*0.4;
    this.r  = Math.random()*2+0.8;
    this.opacity = Math.random()*0.6+0.2;
    this.color = Math.random()>0.6 ? '#00ffc8' : Math.random()>0.5 ? '#bf5fff' : '#5fb4ff';
  }
  update(){
    this.x += this.vx; this.y += this.vy;
    const dx=this.x-mouse.x, dy=this.y-mouse.y, d=Math.sqrt(dx*dx+dy*dy);
    if(d<90){ this.x+=dx/d*1.2; this.y+=dy/d*1.2; }
    if(this.x<0||this.x>W) this.vx*=-1;
    if(this.y<0||this.y>H) this.vy*=-1;
    this.x=Math.max(0,Math.min(W,this.x));
    this.y=Math.max(0,Math.min(H,this.y));
  }
  draw(){
    ctx.beginPath();
    ctx.arc(this.x,this.y,this.r,0,Math.PI*2);
    ctx.fillStyle=this.color;
    ctx.globalAlpha=this.opacity;
    ctx.fill();
    ctx.globalAlpha=1;
  }
}

function init(){
  nodes=[];
  for(let i=0;i<NODE_COUNT;i++) nodes.push(new Node());
}
init();

function drawEdges(){
  for(let i=0;i<nodes.length;i++){
    for(let j=i+1;j<nodes.length;j++){
      const dx=nodes[i].x-nodes[j].x, dy=nodes[i].y-nodes[j].y;
      const d=Math.sqrt(dx*dx+dy*dy);
      if(d<MAX_DIST){
        const a=(1-d/MAX_DIST)*0.35;
        ctx.beginPath();
        ctx.moveTo(nodes[i].x,nodes[i].y);
        ctx.lineTo(nodes[j].x,nodes[j].y);
        ctx.strokeStyle=nodes[i].color;
        ctx.globalAlpha=a;
        ctx.lineWidth=0.5;
        ctx.stroke();
        ctx.globalAlpha=1;
      }
    }
  }
}

function loop(){
  ctx.clearRect(0,0,W,H);
  ctx.fillStyle='#020408';
  ctx.fillRect(0,0,W,H);
  drawEdges();
  nodes.forEach(n=>{ n.update(); n.draw(); });
  requestAnimationFrame(loop);
}
loop();

/* ── Typewriter ── */
const roles=[
  'Building RAG Pipelines',
  'LLM Systems Engineer',
  'Agentic AI Developer',
  'MCP Architecture',
  'GenAI Product Builder',
  'AI-First Startup Ready'
];
let ri=0,ci=0,del=false;
const tw=document.getElementById('typewriter');

function type(){
  const word=roles[ri];
  if(!del){
    ci++;
    tw.textContent=word.slice(0,ci);
    if(ci===word.length){ del=true; setTimeout(type,1800); return; }
  } else {
    ci--;
    tw.textContent=word.slice(0,ci);
    if(ci===0){ del=false; ri=(ri+1)%roles.length; }
  }
  setTimeout(type, del?45:80);
}
setTimeout(type,1400);
</script>
</body>
</html>

<!-- ═══════════════════════════════════════════════════════════ -->
<div align="center">
  <img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,20,24&height=220&section=header&text=Abhishek%20Yadav&fontSize=58&fontColor=ffffff&fontAlignY=38&desc=AI%20Engineer%20%7C%20RAG%20Pipelines%20%7C%20Agentic%20AI%20%7C%20LLM%20Systems&descAlignY=60&descSize=17&descColor=c4b5fd&animation=fadeIn&stroke=a78bfa&strokeWidth=1" />
</div>

<!-- ═══════════════════════════════════════════════════════════ -->
<!--                    TYPING ANIMATION                        -->
<!-- ═══════════════════════════════════════════════════════════ -->


<!-- <p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=700&size=17&pause=1000&color=A78BFA&center=true&vCenter=true&width=780&height=45&lines=🤖+Building+Production+RAG+%26+Agentic+AI+Systems;⚡+Anthropic+API+%7C+LangChain+%7C+LangGraph+%7C+ChromaDB+%7C+MCP;🚀+Live+Deployed+→+HuggingFace+Spaces;📜+11x+Anthropic+Academy+Certified+%7C+Kanpur+🇮🇳;🔍+Seeking+AI+Engineer+%7C+LLM+Engineer+%7C+GenAI+Developer" />
</p> -->

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=700&size=17&pause=1000&color=A78BFA&center=true&vCenter=true&width=900&height=60&lines=Building+Production+RAG+and+Agentic+AI+Systems;Anthropic+API+%7C+LangChain+%7C+LangGraph+%7C+ChromaDB+%7C+MCP;Live+Deployed+on+HuggingFace+Spaces;Anthropic+Certified+Developer+%7C+Kanpur+India;Seeking+AI+Engineer+%7C+LLM+Engineer+%7C+GenAI+Developer" alt="Typing SVG" />
</p>

<!-- ═══════════════════════════════════════════════════════════ -->
<!--                    SOCIAL LINKS                            -->
<!-- ═══════════════════════════════════════════════════════════ -->
<p align="center">
  <a href="https://3-d-protfolio.vercel.app/" target="_blank">
    <img src="https://img.shields.io/badge/Portfolio-000000?style=for-the-badge&logo=googlechrome&logoColor=white" />
  </a>&nbsp;
  <a href="https://www.linkedin.com/in/abhishek-yadav72/" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>&nbsp;
  <a href="https://huggingface.co/spaces/abhishekyadav16/abhishekyadav16" target="_blank">
    <img src="https://img.shields.io/badge/HuggingFace-FFD21E?style=for-the-badge&logo=huggingface&logoColor=000000" />
  </a>&nbsp;
  <a href="mailto:abhishek977266@gmail.com">
    <img src="https://img.shields.io/badge/Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white" />
  </a>&nbsp;
  <a href="https://docs.google.com/document/d/10ekITm5NIJIMaJxs-teDLg1-nPWNXq7M/edit?usp=drivesdk&ouid=115189545770320518615&rtpof=true&sd=true" target="_blank">
    <img src="https://img.shields.io/badge/Resume-4285F4?style=for-the-badge&logo=googledrive&logoColor=white" />
  </a>
</p>

<!-- OPEN TO WORK -->
<p align="center">
  <img src="https://img.shields.io/badge/🟢_OPEN_TO_WORK-AI_Engineer_%7C_LLM_Engineer_%7C_GenAI_Developer-0d1117?style=for-the-badge&labelColor=0d1117&color=7c3aed" />
</p>

<!-- QUICK STATS ROW -->
<p align="center">
  <img src="https://img.shields.io/badge/🏅_Anthropic_Certs-11x-D97706?style=flat-square" />&nbsp;
  <img src="https://img.shields.io/badge/💼_Internships-6x-0EA5E9?style=flat-square" />&nbsp;
  <img src="https://img.shields.io/badge/🚀_Live_Projects-HuggingFace_Deployed-10B981?style=flat-square" />&nbsp;
  <img src="https://img.shields.io/badge/📍_Location-Kanpur,_India-EF4444?style=flat-square" />
</p>

<br/>

---

<!-- ═══════════════════════════════════════════════════════════ -->
<!--                    WHO AM I — PYTHON BLOCK                 -->
<!-- ═══════════════════════════════════════════════════════════ -->

## 🧠 Who Am I?

```python
class AbhishekYadav:
    """AI Engineer | BCA @ CSJMU Kanpur (2022–2025) | CGPA: 7.59"""

    role       = "AI Engineer"
    location   = "Kanpur, Uttar Pradesh, India 🇮🇳"

    specializations = [
        "3-Stage RAG:   Retrieval → Hybrid Search + RRF → Agentic Generation",
        "Agentic AI:    Chaining | Routing | Parallelization | Evaluator-Optimizer",
        "MCP Protocol:  Custom Tool Servers + Claude Orchestration (stdio/SSE)",
        "LLM Eng:       Prompt Caching | Files API | Extended Thinking | Batch",
        "Multi-Agent:   LangGraph Orchestration with Tool-Augmented Workflows",
    ]

    stack = {
        "LLM":       ["Anthropic API", "LangChain", "LangGraph", "ChromaDB"],
        "Infra":     ["FastAPI", "Docker", "HuggingFace Spaces", "Railway"],
        "Languages": ["Python", "TypeScript", "JavaScript"],
    }

    certifications = "11x Anthropic Academy 🏅"
    internships    = 6
    deployed_live  = "https://huggingface.co/spaces/abhishekyadav16/abhishekyadav16"
    seeking        = ["Remote", "Bengaluru", "Hyderabad", "Noida"]

    def say_hi(self):
        print("Let's build production-grade AI systems together! 🚀")
```

<br/>

---

<!-- ═══════════════════════════════════════════════════════════ -->
<!--                  CURRENTLY BUILDING                        -->
<!-- ═══════════════════════════════════════════════════════════ -->

## ⚡ Currently Building

```
🔨  Multi-Agent LangGraph Orchestration    →  Tool-routing + parallel subgraph execution
📡  Extended MCP Server Architecture       →  SSE transport + custom Resource + Prompt primitives  
🧪  Evaluator-Optimizer Agent Loop         →  Self-improving RAG with reflection pattern
```

<br/>

---

<!-- ═══════════════════════════════════════════════════════════ -->
<!--                  FLAGSHIP PROJECTS                         -->
<!-- ═══════════════════════════════════════════════════════════ -->

## 🚀 Flagship Projects

<table>
<tr>
<td width="50%" valign="top">

### 🤖 AI Document Intelligence
> 🟢 **Live on HuggingFace Spaces**

Production **3-stage AI pipeline** combining RAG + Computer Vision + Agentic AI for intelligent document Q&A.

```
Stage 1 ── Ingestion & Vision
           PDF → OCR → Chunking → Embedding
           
Stage 2 ── Hybrid RAG Retrieval
           ChromaDB  +  all-MiniLM-L6-v2
           Dense + Sparse → RRF Reranking

Stage 3 ── Agentic Generation
           Anthropic Claude API + Tool-Use
           Context-Grounded Answers
```

**Stack**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Anthropic](https://img.shields.io/badge/Anthropic_API-D97706?style=flat-square)
![ChromaDB](https://img.shields.io/badge/ChromaDB-FF6B35?style=flat-square)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![HuggingFace](https://img.shields.io/badge/HuggingFace-FFD21E?style=flat-square&logo=huggingface&logoColor=black)

[![🔗 Live Demo](https://img.shields.io/badge/🔗_Live_Demo-HuggingFace_Spaces-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black)](https://huggingface.co/spaces/abhishekyadav16/abhishekyadav16)
[![GitHub](https://img.shields.io/badge/Source_Code-181717?style=for-the-badge&logo=github)](https://github.com/CodeBy-Abhishek/ai-doc-intelligence)

</td>
<td width="50%" valign="top">

### ⚡ MCP Lead Generation System
> 🏗️ **Architecturally Distinctive**

**MCP-powered agentic system** — Claude orchestrates custom Python MCP servers for end-to-end automated lead generation.

```
Claude (MCP Client)
│
├── Tool: scrape_leads()
│         ↳ Targeted web scraping
│
├── Tool: enrich_profile()
│         ↳ LinkedIn + data enrichment
│
├── Tool: score_lead()
│         ↳ AI-powered ICP scoring
│
└── Tool: export_crm()
          ↳ Push to CRM / CSV / Sheet

Transport: stdio  |  Server: FastAPI + Python
```

**Stack**

![MCP](https://img.shields.io/badge/MCP_Protocol-6366F1?style=flat-square)
![Claude](https://img.shields.io/badge/Claude_API-D97706?style=flat-square)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Railway](https://img.shields.io/badge/Railway-0B0D0E?style=flat-square&logo=railway&logoColor=white)

[![GitHub](https://img.shields.io/badge/Source_Code-181717?style=for-the-badge&logo=github)](https://github.com/CodeBy-Abhishek/mcp-lead-gen-system)
[![Architecture](https://img.shields.io/badge/Deep_Dive-LinkedIn-0A66C2?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/abhishek-yadav72/)

</td>
</tr>
</table>

<br/>

---

<!-- ═══════════════════════════════════════════════════════════ -->
<!--                     TECH STACK                             -->
<!-- ═══════════════════════════════════════════════════════════ -->

## 🛠️ Tech Stack

### 🤖 AI / LLM Layer *(Core Focus)*
<p>
  <img src="https://img.shields.io/badge/Anthropic_API-D97706?style=for-the-badge&logoColor=white" />
  <img src="https://img.shields.io/badge/LangChain-1C3C3C?style=for-the-badge&logoColor=white" />
  <img src="https://img.shields.io/badge/LangGraph-4A90D9?style=for-the-badge&logoColor=white" />
  <img src="https://img.shields.io/badge/ChromaDB-FF6B35?style=for-the-badge&logoColor=white" />
  <img src="https://img.shields.io/badge/HuggingFace-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black" />
  <img src="https://img.shields.io/badge/MCP_Protocol-6366F1?style=for-the-badge&logoColor=white" />
  <img src="https://img.shields.io/badge/RAG_Pipelines-0EA5E9?style=for-the-badge&logoColor=white" />
  <img src="https://img.shields.io/badge/Agentic_AI-EF4444?style=for-the-badge&logoColor=white" />
  <img src="https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white" />
  <img src="https://img.shields.io/badge/Prompt_Engineering-10B981?style=for-the-badge&logoColor=white" />
  <img src="https://img.shields.io/badge/Vector_DB-8B5CF6?style=for-the-badge&logoColor=white" />
  <img src="https://img.shields.io/badge/n8n-EA4B71?style=for-the-badge&logo=n8n&logoColor=white" />
</p>

### ⚙️ Backend & APIs
<p>
  <img src="https://skillicons.dev/icons?i=python,fastapi,flask,django,nodejs,expressjs" />
</p>

### 🎨 Frontend
<p>
  <img src="https://skillicons.dev/icons?i=react,nextjs,typescript,javascript,tailwind,html,css,bootstrap" />
</p>

### 🗄️ Databases & Infrastructure
<p>
  <img src="https://skillicons.dev/icons?i=mongodb,postgres,mysql,redis,docker,aws,linux,git" />
</p>

<br/>

---

<!-- ═══════════════════════════════════════════════════════════ -->
<!--                   CERTIFICATIONS                           -->
<!-- ═══════════════════════════════════════════════════════════ -->

## 📜 Certifications — 11x Anthropic Academy 🏅

<table>
<tr>
  <td align="center"><img src="https://img.shields.io/badge/01-7C3AED?style=for-the-badge" /><br/><b>Claude API Fundamentals</b></td>
  <td align="center"><img src="https://img.shields.io/badge/02-7C3AED?style=for-the-badge" /><br/><b>MCP Architecture</b></td>
  <td align="center"><img src="https://img.shields.io/badge/03-7C3AED?style=for-the-badge" /><br/><b>Agentic Design Patterns</b></td>
  <td align="center"><img src="https://img.shields.io/badge/04-7C3AED?style=for-the-badge" /><br/><b>Prompt Engineering</b></td>
</tr>
<tr>
  <td align="center"><img src="https://img.shields.io/badge/05-D97706?style=for-the-badge" /><br/><b>RAG & Retrieval</b></td>
  <td align="center"><img src="https://img.shields.io/badge/06-D97706?style=for-the-badge" /><br/><b>Extended Thinking</b></td>
  <td align="center"><img src="https://img.shields.io/badge/07-D97706?style=for-the-badge" /><br/><b>Tool Use & Function Calling</b></td>
  <td align="center"><img src="https://img.shields.io/badge/08-D97706?style=for-the-badge" /><br/><b>Batch Processing</b></td>
</tr>
<tr>
  <td align="center"><img src="https://img.shields.io/badge/09-0EA5E9?style=for-the-badge" /><br/><b>Files API</b></td>
  <td align="center"><img src="https://img.shields.io/badge/10-0EA5E9?style=for-the-badge" /><br/><b>Prompt Caching</b></td>
  <td align="center"><img src="https://img.shields.io/badge/11-10B981?style=for-the-badge" /><br/><b>Claude Code</b></td>
  <td align="center"><img src="https://img.shields.io/badge/🏅_All_Issued_by-Anthropic_Academy-D97706?style=for-the-badge" /></td>
</tr>
</table>

<br/>

---

<!-- ═══════════════════════════════════════════════════════════ -->
<!--                   EXPERIENCE                               -->
<!-- ═══════════════════════════════════════════════════════════ -->

## 💼 Experience — 6 Internships

| # | Company | Role | Type |
|---|---------|------|------|
| 6 | **Codevirus Security** | Security + AI Integration | Cybersecurity |
| 5 | **Code-A-Nova** | AI Developer Intern | AI/ML |
| 4 | **Klynt Solutions** | Full-Stack + AI | Product |
| 3 | **HexSoftwares** | Software Developer Intern | Full-Stack |
| 2 | **Google Developer Campus** | Developer Intern | Cloud/Dev |
| 1 | *(Earlier Internship)* | Web Development | Frontend |

<br/>

---

<!-- ═══════════════════════════════════════════════════════════ -->
<!--                  GITHUB ANALYTICS                          -->
<!-- ═══════════════════════════════════════════════════════════ -->

## 📊 GitHub Analytics

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=CodeBy-Abhishek&show_icons=true&hide_border=true&theme=tokyonight&include_all_commits=true&count_private=true&rank_icon=github&show=reviews,prs_merged" height="175"/>
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=CodeBy-Abhishek&hide_border=true&theme=tokyonight" height="175"/>
</p>



<p align="center">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=CodeBy-Abhishek&layout=compact&hide_border=true&theme=tokyonight&langs_count=8&hide=jupyter%20notebook,html,css" height="148"/>
</p>


<!-- TROPHIES -->
<p align="center">
  <img src="https://github-profile-trophy.vercel.app/?username=CodeBy-Abhishek&theme=tokyonight&no-frame=true&row=1&column=7&margin-w=6" />
</p>


<!-- ACTIVITY GRAPH -->
<p align="center">
  <img width="95%" src="https://github-readme-activity-graph.vercel.app/graph?username=CodeBy-Abhishek&theme=tokyo-night&hide_border=true&area=true&area_color=7c3aed" />
</p>

<!-- CONTRIBUTION SNAKE -->
<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/CodeBy-Abhishek/CodeBy-Abhishek/output/github-contribution-grid-snake-dark.svg" />
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/CodeBy-Abhishek/CodeBy-Abhishek/output/github-contribution-grid-snake.svg" />
    <img alt="contribution snake" src="https://raw.githubusercontent.com/CodeBy-Abhishek/CodeBy-Abhishek/output/github-contribution-grid-snake-dark.svg" />
  </picture>
</p>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=CodeBy-Abhishek&style=for-the-badge&color=7c3aed&label=Profile+Views" />
</p>





<table align="center">
<tr>
</tr>

<tr>
<td><img src="https://skillicons.dev/icons?i=html"/></td>
<td><img src="https://skillicons.dev/icons?i=css"/></td>
<td><img src="https://skillicons.dev/icons?i=bootstrap"/></td>
<td><img src="https://skillicons.dev/icons?i=tailwind"/></td>
<td><img src="https://skillicons.dev/icons?i=javascript"/></td>
<td><img src="https://skillicons.dev/icons?i=react"/></td>
<td><img src="https://skillicons.dev/icons?i=nextjs"/></td>
<td><img src="https://skillicons.dev/icons?i=typescript"/></td>
<td align="center">
  <img src="https://skillicons.dev/icons?i=mui" />
</td>
</tr>


<tr>
<td><img src="https://skillicons.dev/icons?i=expressjs"/></td>
<td><img src="https://skillicons.dev/icons?i=nodejs"/></td>
<td><img src="https://skillicons.dev/icons?i=python"/></td>
<td><img src="https://skillicons.dev/icons?i=django"/></td>
<td><img src="https://skillicons.dev/icons?i=fastapi"/></td>
<td><img src="https://skillicons.dev/icons?i=flask"/></td>
<td><img src="https://skillicons.dev/icons?i=mysql"/></td>
<td><img src="https://skillicons.dev/icons?i=postgres"/></td>
<td><img src="https://skillicons.dev/icons?i=mongodb"/></td>
</tr>

<tr>
<td><img src="https://skillicons.dev/icons?i=aws"/></td>
<td><img src="https://skillicons.dev/icons?i=docker"/></td>
<td><img src="https://skillicons.dev/icons?i=tensorflow"/></td>
<td><img src="https://skillicons.dev/icons?i=pytorch"/></td>
<td><img src="https://skillicons.dev/icons?i=matlab"/></td>
<!-- <td><img src="https://skillicons.dev/icons?i=tableau"/></td>
<td><img src="https://skillicons.dev/icons?i=openai"/></td>
<td><img src="https://skillicons.dev/icons?i=databricks"/></td> -->
<td><img src="https://skillicons.dev/icons?i=redis"/></td>
<td><img src="https://skillicons.dev/icons?i=vscode"/></td>
<td><img src="https://skillicons.dev/icons?i=linux"/></td>
<td><img src="https://skillicons.dev/icons?i=git"/></td>
</tr>

<tr>
<!-- <td><img src="https://skillicons.dev/icons?i=redis"/></td>
<td><img src="https://skillicons.dev/icons?i=spark"/></td>
<td><img src="https://skillicons.dev/icons?i=iceberg"/></td>
<td><img src="https://skillicons.dev/icons?i=snowflake"/></td>
<td><img src="https://skillicons.dev/icons?i=minio"/></td>
<td><img src="https://skillicons.dev/icons?i=vscode"/></td>
<td><img src="https://skillicons.dev/icons?i=linux"/></td>
<td><img src="https://skillicons.dev/icons?i=git"/></td> -->
</tr>
</table>
<p align="center">
  <img src="https://img.shields.io/badge/REST%20API-02569B?style=for-the-badge" />
  <img src="https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white" />
  <img src="https://img.shields.io/badge/n8n-EA4B71?style=for-the-badge&logo=n8n&logoColor=white" />
  <img src="https://img.shields.io/badge/SQL-003B57?style=for-the-badge" />
</p>
---

<!-- ═══════════════════════════════════════════════════════════ -->
<!--                    FOOTER WAVE                             -->
<!-- ═══════════════════════════════════════════════════════════ -->
<div align="center">
  <img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=24,20,12&height=130&section=footer&text=Open+to+AI+Engineer+Roles&fontSize=26&fontColor=c4b5fd&fontAlignY=62&desc=Remote+%7C+Bengaluru+%7C+Hyderabad+%7C+Noida+%7C+Kanpur&descSize=14&descColor=ffffff&descAlignY=82" />
</div>
