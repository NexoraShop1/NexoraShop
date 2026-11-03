I'll build this carefully as a single-file page. Let me lay out the exact coordinates, sections, and motion details, then write the full HTML/CSS/JS.

A few key implementation notes up front so the design intent is clear:

- **Scale system** uses your `u` unit (`min(100vw/1440, 1.333px)`), switching to `100vw/390` below 760px.
- **Statement fill** works by splitting every word into a span, measuring each word's position (via `data` order in reading sequence), and driving opacity/color through a soft-edge window as the section scrolls.
- **Recorder mode (`?rec=1`)** runs the scroll-driven parts on a fixed timeline using `document.timeline` so a single-frame capture still shows the fill, counters, avatars, and card lift.
- **Reduced motion** fills everything and disables transitions.

Here is the complete single-file page.

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Orvante — Branding Agency</title>
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=Inter+Tight:wght@100..900&family=Archivo:wdth,wght@62..125,100..900&display=swap" rel="stylesheet" />
<style>
  :root{
    --paper:#dadada;
    --ink:#111;
    --black:#000;
    --text:#f4f4f4;
    --grey:#6f6f6f;
    --white:14%;
  }
  *{box-sizing:border-box;margin:0;padding:0;}
  html,body{overflow-x:hidden;}
  body{
    font-family:'Inter Tight',system-ui,sans-serif;
    font-weight:500;
    background:var(--black);
    color:var(--text);
    -webkit-font-smoothing:antialiased;
    text-rendering:optimizeLegibility;
  }
  .u{ width:var(--u); } /* unused helper */

  /* ---------- scale ---------- */
  :root{ --u: min(100vw / 1440, 1.333px); }
  @media (max-width:760px){
    :root{ --u: 100vw / 390; }
  }

  /* ---------- utility ---------- */
  .inter{font-family:'Inter Tight',sans-serif;}
  .archivo{font-family:'Archivo',sans-serif;}

  /* ---------- hero ---------- */
  .hero{
    position:relative;
    height:938u;
    background:var(--paper);
    color:var(--ink);
    overflow:hidden;
  }
  .hero-photo-wrap{
    position:absolute;
    left:338u; top:-86u;
    width:764u; height:1024u;
    will-change:transform,filter,opacity;
  }
  .hero-photo-wrap img{
    width:100%; height:100%;
    object-fit:cover;
    display:block;
    -webkit-mask-image:linear-gradient(90deg,transparent 0%,#000 6%,#000 94%,transparent 100%);
            mask-image:linear-gradient(90deg,transparent 0%,#000 6%,#000 94%,transparent 100%);
  }

  /* nav */
  .nav{
    position:absolute;
    top:61u; left:57u;
    height:48u;
    display:flex; align-items:center;
    background:#fff;
    border-radius:999px;
    padding:4u;
    z-index:5;
  }
  .nav a{
    position:relative;
    padding:0 22u;
    height:40u;
    line-height:40u;
    font-size:14u;
    font-weight:500;
    color:var(--ink);
    text-decoration:none;
    border-radius:999px;
    z-index:1;
    transition:color .3s;
  }
  .nav .pill{
    position:absolute;
    top:4u; left:4u;
    height:40u;
    background:#000;
    border-radius:999px;
    transition:transform .35s cubic-bezier(.5,0,.2,1), width .35s cubic-bezier(.5,0,.2,1);
  }
  .nav a.active{color:#fff;}

  /* top-right */
  .hero-date{
    position:absolute;
    top:70u; left:1038u;
    font-size:13u;
    color:var(--ink);
    z-index:5;
  }
  .contact-btn{
    position:absolute;
    top:63u; left:1237u;
    width:144u; height:46u;
    background:var(--ink);
    color:#fff;
    display:flex; align-items:center; justify-content:center;
    gap:6u;
    font-size:14u; font-weight:500;
    border-radius:4u;
    text-decoration:none;
    z-index:5;
    transition:transform .2s;
  }
  .contact-btn:hover{transform:translateY(-1px);}

  /* title */
  .title-mask{position:absolute; top:246u; left:57u; overflow:hidden;}
  .title{
    font-family:'Archivo',sans-serif;
    font-stretch:104%;
    font-variation-settings:'wdth' 104,'wght' 640;
    font-weight:640;
    font-size:90u;
    line-height:.86;
    letter-spacing:-.06em;
    white-space:nowrap;
  }
  .title-sub{
    position:absolute;
    top:272u; left:339u;
    font-family:'Archivo',sans-serif;
    font-size:24u;
    font-weight:400;
  }

  /* about */
  .about{
    position:absolute;
    top:458u; left:57u;
    width:290u;
  }
  .about .label{
    font-size:13u;
    font-weight:600;
    margin-bottom:12u;
  }
  .about p{
    font-size:14u;
    line-height:1.45;
    font-weight:400;
  }
  .book-call{
    display:inline-flex;
    margin-top:16u;
    height:46u;
    padding:0 22u;
    background:var(--ink);
    color:#fff;
    font-size:14u;
    align-items:center; justify-content:center;
    text-decoration:none;
    border-radius:4u;
    transition:transform .2s;
  }
  .book-call:hover{transform:translateY(-1px);}

  /* stats frame */
  .stats-frame{
    position:absolute;
    top:693u; left:57u;
    width:341u; height:208u;
    background:#cdcdcd;
    border-radius:8u;
    padding:14u;
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:12u;
  }
  .stat-dark{
    background:var(--ink);
    color:#fff;
    border-radius:8u;
    padding:12u;
    display:flex; flex-direction:column;
    justify-content:space-between;
  }
  .stat-dark .big{font-size:30u; font-weight:700; line-height:1;}
  .stat-dark .sub{font-size:11u; color:#aaa; margin-top:4u;}
  .partner-marks{
    display:grid; grid-template-columns:repeat(3,1fr);
    gap:4u; font-size:8u; color:#bbb;
    text-transform:uppercase; letter-spacing:.04em;
  }
  .stat-dark .bar{
    margin-top:6u;
    height:22u;
    background:#fff; color:#000;
    border-radius:4u;
    font-size:10u; font-weight:600;
    display:flex; align-items:center; justify-content:center;
  }
  .stat-cap{
    position:relative;
    border-radius:8u;
    overflow:hidden;
  }
  .stat-cap img{width:100%; height:100%; object-fit:cover; display:block;}
  .stat-cap .line{
    position:absolute; top:0; left:0; right:0;
    height:1px; background:rgba(255,255,255,.4);
  }
  .stat-cap .tag{
    position:absolute; top:8u; left:8u;
    font-size:9u; color:#fff; background:rgba(0,0,0,.35);
    padding:2u 6u; border-radius:999px;
  }
  .stat-cap .caption{
    position:absolute; bottom:8u; right:8u;
    font-size:9u; color:#fff; text-align:right;
    text-shadow:0 1px 2u rgba(0,0,0,.5);
  }

  /* right column */
  .true-growth{
    position:absolute;
    top:258u; left:1216u;
    display:flex; align-items:center; gap:8u;
    height:34u; padding:0 14u;
    border-radius:999px;
    background:rgba(255,255,255,.28);
    backdrop-filter:blur(8u);
    -webkit-backdrop-filter:blur(8u);
    font-size:13u; font-weight:500;
    z-index:5;
  }
  .true-growth .check{
    width:16u; height:16u; border-radius:50%;
    background:#000;
    position:relative;
  }
  .true-growth .check::after{
    content:''; position:absolute;
    left:5u; top:3u; width:4u; height:7u;
    border:solid #fff; border-width:0 2u 2u 0;
    transform:rotate(45deg);
  }
  .available{
    position:absolute;
    top:442u; right:57u;
    text-align:right;
    font-size:14u;
  }
  .outnow{
    position:absolute;
    top:560u; right:57u;
    width:270u;
  }
  .outnow .head{
    display:flex; align-items:center; justify-content:space-between;
    font-size:13u; margin-bottom:12u;
  }
  .outnow .img-card{
    position:relative;
    width:270u; height:196u;
    border-radius:8u; overflow:hidden;
  }
  .outnow .img-card img{
    width:100%; height:100%; object-fit:cover;
    transform:scale(1.55);
    transform-origin:62% 45%;
    transition:transform .6s;
  }
  .outnow .img-card:hover img{transform:scale(1.7);}
  .outnow .arrow{
    position:absolute; right:12u; bottom:12u;
    width:44u; height:44u; border-radius:50%;
    background:rgba(255,255,255,.28);
    backdrop-filter:blur(8u);
    -webkit-backdrop-filter:blur(8u);
    display:flex; align-items:center; justify-content:center;
    font-size:18u; color:#fff;
    transition:transform .4s;
  }
  .outnow .img-card:hover .arrow{transform:rotate(45deg);}
  .progress{
    margin-top:12u; height:2u;
    background:rgba(255,255,255,.35);
    position:relative;
  }
  .progress .fill{
    position:absolute; left:0; top:0; height:100%;
    width:35%; background:#fff;
    transform-origin:left;
  }

  /* brand plate */
  .brand-plate{
    position:absolute;
    top:444u; left:532u;
    width:364u; height:73u;
    background:rgba(0,0,0,.45);
    backdrop-filter:blur(6u);
    -webkit-backdrop-filter:blur(6u);
    border-radius:10u;
    display:flex; align-items:center; gap:14u;
    padding:0 20u;
    color:#fff;
    z-index:4;
  }
  .tri-mark{
    position:relative;
    width:22u; height:18u;
  }
  .tri-mark::before{
    content:''; position:absolute; left:0; top:0;
    border-left:11u solid transparent;
    border-right:11u solid transparent;
    border-bottom:18u solid #fff;
  }
  .brand-plate .word{
    font-family:'Archivo',sans-serif;
    font-variation-settings:'wdth' 118,'wght' 700;
    font-size:25u;
    letter-spacing:.04em;
  }
  .brand-plate .menu{
    margin-left:auto;
    display:flex; flex-direction:column; gap:4u;
  }
  .brand-plate .menu span{
    display:block; width:20u; height:2u; background:#fff; border-radius:1u;
  }
  .brand-plate .menu span:last-child{width:12u;}

  /* logos strip */
  .hero-logos{
    position:absolute;
    top:864u; left:57u; right:57u;
    display:flex; align-items:center; justify-content:space-between;
    font-size:16u; color:#333; letter-spacing:.06em;
  }

  /* ---------- bar ---------- */
  .bar{
    position:relative;
    height:111u;
    background:#000;
    display:flex; align-items:center; justify-content:space-between;
    padding:0 57u;
    font-family:'Archivo',sans-serif;
    font-size:14u;
    letter-spacing:.03em;
    border-bottom:1px solid rgba(255,255,255,.14);
  }
  .bar .grey{color:#6f6f6f;}
  .bar .mid{display:flex; align-items:center; gap:10u;}
  .bar .arrow{
    width:24u; height:24u; border-radius:50%;
    border:1.5px solid #fff;
    display:inline-flex; align-items:center; justify-content:center;
  }

  /* ---------- statement ---------- */
  .statement{
    position:relative;
    background:#000;
    padding:170u 0 230u;
    display:flex; justify-content:center;
  }
  .statement .wrap{
    width:830u;
  }
  .statement .txt{
    font-size:52u;
    line-height:1.33;
    letter-spacing:-.028em;
    font-weight:500;
  }
  .statement .word{
    color:#6f6f6f;
    transition:color .15s linear;
  }
  .statement .sub{
    margin-top:150u;
    font-size:23u;
    line-height:1.4;
  }
  .statement .sub .g{color:#6f6f6f;}

  /* ---------- trust ---------- */
  .trust{
    background:#000;
    padding-bottom:150u;
    display:flex; justify-content:center;
  }
  .trust-panel{
    position:relative;
    width:1302u; height:429u;
    border:1px solid rgba(255,255,255,.28);
    border-radius:14u;
    display:flex;
    overflow:hidden;
  }
  .trust-left{
    position:relative;
    width:520u;
    padding:64u 40u 0 64u;
    flex-shrink:0;
  }
  .trust-left h3{
    font-size:55u; font-weight:500; line-height:1.05;
  }
  .trust-left p{
    margin-top:28u;
    font-size:14.5u; line-height:1.6; color:#999;
    max-width:360u;
  }
  .glass-tile{
    position:absolute;
    width:88u; height:88u;
    border-radius:12u;
    background:rgba(255,255,255,.08);
    backdrop-filter:blur(12u);
    -webkit-backdrop-filter:blur(12u);
    display:flex; align-items:center; justify-content:center;
    font-size:30u; color:#fff;
  }
  .glass-asterisk{top:-20u; right:20u;}
  .glass-dots{
    bottom:-30u; left:40u;
    display:grid; grid-template-columns:1fr 1fr; gap:8u; padding:22u;
  }
  .glass-dots i{width:12u; height:12u; border-radius:50%; background:#fff;}

  .trust-cards{
    flex:1;
    display:flex;
    gap:16u;
    padding:52u 0 0 0;
    align-items:flex-end;
  }
  .card{
    height:326u; border-radius:8u;
    overflow:hidden;
    transition:transform .4s;
  }
  .card:hover{transform:translateY(-6u);}
  .card-avatars{
    width:293u; background:#d6d6d6; color:#111;
    padding:20u;
    display:flex; flex-direction:column;
  }
  .grid-avatars{
    display:grid; grid-template-columns:repeat(4,1fr);
    gap:10u;
  }
  .avatar{
    width:48u; height:48u; border-radius:50%;
    object-fit:cover; display:block;
  }
  .card-avatars .num{
    margin-top:auto; font-size:43u; font-weight:700; line-height:1;
  }
  .card-avatars .lbl{font-size:14u; color:#555;}
  .card-awards{
    width:298u; background:#262626; color:#fff;
    padding:24u;
    display:flex; flex-direction:column;
    justify-content:space-between;
  }
  .card-awards .big{font-size:30u; font-weight:700;}
  .card-awards .big .slash{color:#888; font-weight:400;}
  .laurel{
    display:flex; align-items:center; gap:12u;
    font-size:13u; letter-spacing:.05em;
  }
  .laurel svg{width:40u; height:40u;}
  .card-awards .note{font-size:12.5u; color:#bbb; line-height:1.5;}
  .card-portrait{
    width:200u; position:relative;
  }
  .card-portrait img{
    width:100%; height:100%; object-fit:cover; display:block;
  }

  /* ---------- motion base ---------- */
  .fade{
    opacity:0;
    transform:translateY(14px);
  }
  .title-line{
    transform:translateY(100%);
  }
  .hero-photo-anim{
    opacity:0;
    filter:blur(14px);
    transform:translateY(40px);
  }

  @media (prefers-reduced-motion: reduce){
    .fade,.title-line,.hero-photo-anim{opacity:1; transform:none; filter:none; transition:none !important;}
    *{animation:none !important; transition:none !important;}
  }
</style>
</head>
<body>

<section class="hero" id="hero">
  <div class="hero-photo-wrap hero-photo-anim" id="heroPhoto">
    <img src="https://d2ol7oe51mr4n9.cloudfront.net/user_38xzZboKViGWJOttwIXH07lWA1P/7dc8b8f3-4ccb-4599-8ce4-7f7c7881bad9.webp" alt="" />
  </div>

  <nav class="nav fade" id="nav">
    <span class="pill" id="navPill"></span>
    <a href="#" class="active" data-nav="home">Home</a>
    <a href="#" data-nav="studio">Studio</a>
    <a href="#" data-nav="works">Works</a>
    <a href="#" data-nav="blog">Blog</a>
  </nav>

  <div class="hero-date fade">Sunday / 17.06 – 27 June 2026</div>
  <a class="contact-btn fade" href="#">Contact Us ↗</a>

  <div class="title-mask">
    <div class="title title-line" id="titleLine">PURE / DESIGN</div>
  </div>
  <div class="title-sub fade">(’25)</div>

  <div class="about fade">
    <div class="label">● (ABOUT)</div>
    <p>Building stunning website that every brand deserves to be seen.</p>
    <a class="book-call" href="#">Book A Call ↗</a>
  </div>

  <div class="stats-frame fade">
    <div class="stat-dark">
      <div>
        <div class="big"><span id="count400">0</span>+</div>
        <div class="sub">Trusted Partner</div>
      </div>
      <div class="partner-marks">
        <span>◆ Halcyon</span><span>● Ostra</span><span>▲ Fenwick</span>
        <span>■ Monolo</span><span>✦ Kitefly</span><span>▣ Arbor</span>
      </div>
      <div class="bar">Book a call ↗</div>
    </div>
    <div class="stat-cap">
      <span class="line"></span>
      <span class="tag">Studio Feed · 05/06</span>
      <img src="https://d2ol7oe51mr4n9.cloudfront.net/user_38xzZboKViGWJOttwIXH07lWA1P/a9d3641f-d629-46e5-8d2d-5f75386b803d.webp" alt="" />
      <div class="caption"><span id="count230">0</span>+<br/>Projects successfully<br/>launched worldwide</div>
    </div>
  </div>

  <div class="true-growth fade"><span class="check"></span> True Growth</div>
  <div class="available fade">We’re available<br/>● for you</div>

  <div class="outnow fade">
    <div class="head"><span>Out Now</span><span>Q Industrial [2025]</span></div>
    <div class="img-card">
      <img src="https://d2ol7oe51mr4n9.cloudfront.net/user_38xzZboKViGWJOttwIXH07lWA1P/9340eb08-877d-4d08-91fb-b70754541d98.webp" alt="" />
      <span class="arrow">↗</span>
    </div>
    <div class="progress"><span class="fill" id="qProgress"></span></div>
  </div>

  <div class="brand-plate">
    <span class="tri-mark"></span>
    <span class="word">ORVANTE</span>
    <span class="menu"><span></span><span></span></span>
  </div>

  <div class="hero-logos fade">Lumon · Paperfold · Northwind</div>
</section>

<div class="bar">
  <span>EST <span class="grey">2019</span></span>
  <span class="mid">SCROLL DOWN <span class="arrow">↓</span></span>
  <span class="grey">LIVE IN DETAILS</span>
</div>

<section class="statement" id="statement">
  <div class="wrap">
    <div class="txt" id="statementTxt">
      We believe the strongest brands are / built through strategy, not just / aesthetics. Every campaign is designed / to capture attention, inspire action, and / create lasting business growth.
    </div>
    <div class="sub">
      Performance-driven marketing, from / strategy to execution.
      <span class="g"><em>Built for growing brands.</em></span>
    </div>
  </div>
</section>

<section class="trust" id="trust">
  <div class="trust-panel">
    <div class="trust-left">
      <span class="glass-tile glass-asterisk">✳</span>
      <span class="glass-tile glass-dots" id="glassDots"><i></i><i></i><i></i><i></i></span>
      <h3>Trusted by<br/>Hundreds of<br/>Growing<br/>Businesses</h3>
      <p>We partner with ambitious teams to build brands that stand the test of time — pairing sharp strategy with bold, measurable creative.</p>
    </div>
    <div class="trust-cards">
      <div class="card card-avatars" id="cardAvatars">
        <div class="grid-avatars" id="avatarGrid"></div>
        <div class="num"><span id="count56">0</span>M+</div>
        <div class="lbl">Global Collaborations</div>
      </div>
      <div class="card card-awards" id="cardAwards">
        <div class="big"><span id="count10">0</span>+ <span class="slash">/ Industry Awards</span></div>
        <div class="laurel">
          <svg viewBox="0 0 40 40" fill="none">
            <path d="M20 6l4 9 9 1-7 6 2 9-8-5-8 5 2-9-7-6 9-1z" fill="#c9a24b"/>
          </svg>
          <span>BEST GROWTH PARTNER 2026</span>
        </div>
        <div class="note">Recognised for measurable growth, bold creative and lasting client partnerships across 40+ markets.</div>
      </div>
      <div class="card card-portrait">
        <img src="https://d2ol7oe51mr4n9.cloudfront.net/user_38xzZboKViGWJOttwIXH07lWA1P/addecc7d-666f-4342-8290-ed7f7cbbffd6.webp" alt="" />
      </div>
    </div>
  </div>
</section>

<script>
(function(){
  const AVATARS = [
    "https://d2ol7oe51mr4n9.cloudfront.net/user_38xzZboKViGWJOttwIXH07lWA1P/300f41b1-3de5-4153-afde-06e15e753ad0.webp",
    "https://d2ol7oe51mr4n9.cloudfront.net/user_38xzZboKViGWJOttwIXH07lWA1P/bfff4cdf-4fda-4491-ada6-62f3b6236492.webp",
    "https://d2ol7oe51mr4n9.cloudfront.net/user_38xzZboKViGWJOttwIXH07lWA1P/943b121e-fe72-479f-93ae-aa8cd1650f69.webp",
    "https://d2ol7oe51mr4n9.cloudfront.net/user_38xzZboKViGWJOttwIXH07lWA1P/c673306f-2b81-4c3d-a7d2-3df61d481abb.webp",
    "https://d2ol7oe51mr4n9.cloudfront.net/user_38xzZboKViGWJOttwIXH07lWA1P/2e4fcf11-d0fc-4f31-8f7a-dfe751777141.webp",
    "https://d2ol7oe51mr4n9.cloudfront.net/user_38xzZboKViGWJOttwIXH07lWA1P/ab458fcd-4c2c-426f-8213-21cc3c7274be.webp",
    "https://d2ol7oe51mr4n9.cloudfront.net/user_38xzZboKViGWJOttwIXH07lWA1P/c1fcd833-5ac9-41e9-9352-fead7e64fa24.webp",
    "https://d2ol7oe51mr4n9.cloudfront.net/user_38xzZboKViGWJOttwIXH07lWA1P/4c2b3307-e555-4633-949c-efd3b7e09d82.webp"
  ];
  const reduced = window.matchMedia('(prefers-reduced-motion: reduce)').matches;
  const rec = new URLSearchParams(location.search).get('rec') === '1';

  /* ---------- build avatars ---------- */
  const grid = document.getElementById('avatarGrid');
  AVATARS.forEach(src=>{
    const img = document.createElement('img');
    img.className = 'avatar';
    img.src = src;
    img.alt = '';
    grid.appendChild(img);
  });

  /* ---------- split statement into word spans ---------- */
  const txt = document.getElementById('statementTxt');
  const raw = txt.innerHTML;
  const words = raw.split(/(\s+)/).filter(t=>t.trim().length);
  txt.innerHTML = '';
  const wordEls = [];
  words.forEach(w=>{
    const s = document.createElement('span');
    s.className = 'word';
    s.textContent = w;
    txt.appendChild(s);
    wordEls.push(s);
  });

  /* ---------- load animations (Web Animations) ---------- */
  function animateLoad(){
    if(reduced) return;

    // title rise
    document.getElementById('titleLine').animate(
      [{transform:'translateY(100%)'},{transform:'translateY(0)'}],
      {duration:1000, easing:'cubic-bezier(.2,.8,.2,1)', fill:'forwards'}
    );

    // photo
    const ph = document.getElementById('heroPhoto');
    ph.animate(
      [{opacity:0, filter:'blur(14px)', transform:'translateY(40px)'},
       {opacity:1, filter:'blur(0)', transform:'translateY(0)'}],
      {duration:1300, delay:110, easing:'ease-out', fill:'forwards'}
    );

    // nav drop
    document.getElementById('nav').animate(
      [{opacity:0, transform:'translateY(-16px)'},
       {opacity:1, transform:'translateY(0)'}],
      {duration:500, easing:'ease-out', fill:'forwards'}
    );

    // every other fade element
    const fades = document.querySelectorAll('.fade');
    fades.forEach((el,i)=>{
      el.animate(
        [{opacity:0, transform:'translateY(14px)'},
         {opacity:1, transform:'translateY(0)'}],
        {duration:600, delay:i*55, easing:'ease-out', fill:'forwards'}
      );
    });

    // progress draw
    document.getElementById('qProgress').animate(
      [{transform:'scaleX(0)'},{transform:'scaleX(1)'}],
      {duration:1000, delay:800, easing:'ease-out', fill:'forwards'}
    );

    // counters
    countUp('count400', 400, 1400);
    countUp('count230', 230, 1400);
  }

  /* ---------- counter helper ---------- */
  function countUp(id, target, dur){
    const el = document.getElementById(id);
    if(!el) return;
    if(reduced){ el.textContent = target; return; }
    const start = performance.now();
    function tick(now){
      const p = Math.min((now-start)/dur, 1);
      const eased = 1 - Math.pow(1-p, 3);
      el.textContent = Math.round(target*eased);
      if(p<1) requestAnimationFrame(tick);
    }
    requestAnimationFrame(tick);
  }

  /* ---------- scroll: photo drift ---------- */
  function setupScroll(){
    if(reduced) return;
    const ph = document.getElementById('heroPhoto');
    const hero = document.getElementById('hero');
    let raf = 0;
    window.addEventListener('scroll', ()=>{
      if(raf) return;
      raf = requestAnimationFrame(()=>{
        const y = window.scrollY;
        const drift = y * 0.12;
        ph.style.transform = 'translateY('+drift+'px)';
        raf = 0;
      });
    }, {passive:true});
  }

  /* ---------- scroll: statement fill ---------- */
  function setupStatementFill(){
    if(reduced){ fillAll(); return; }
    const section = document.getElementById('statement');

    function update(){
      const r = section.getBoundingClientRect();
      const vh = window.innerHeight;
      // progress 0 -> 1 as section enters and crosses viewport
      const total = vh + r.height;
      const progress = Math.min(Math.max((vh - r.top)/total, 0), 1);
      const lit = Math.floor(progress * (wordEls.length + 3));
      wordEls.forEach((el,i)=>{
        const d = lit - i; // words ahead of the lit edge
        if(d <= 0){ el.style.color = '#6f6f6f'; }
        else if(d >= 3){ el.style.color = '#f4f4f4'; }
        else { // soft edge
          const t = d/3;
          el.style.color = mix('#6f6f6f','#f4f4f4', t);
        }
      });
      if(!rec) requestAnimationFrameTick = false;
    }
    let requestAnimationFrameTick = false;
    let ticking = false;
    function onScroll(){
      if(!ticking){ ticking = true; requestAnimationFrame(()=>{ update(); ticking=false; }); }
    }
    window.addEventListener('scroll', onScroll, {passive:true});
    update();
    if(rec){
      // run on timeline
      const tl = document.timeline;
      if(tl){
        const animate = (t)=>{
          const p = Math.min(Math.max((t-1300)/(4200-1300),0),1);
          const lit = Math.floor(p*(wordEls.length+3));
          wordEls.forEach((el,i)=>{
            const d = lit - i;
            if(d<=0){el.style.color='#6f6f6f';}
            else if(d>=3){el.style.color='#f4f4f4';}
            else{el.style.color=mix('#6f6f6f','#f4f4f4',d/3);}
          });
          if(t<4200) requestAnimationFrame(animate);
        };
        requestAnimationFrame(animate);
      }
    }
  }

  function fillAll(){
    wordEls.forEach(el=>el.style.color='#f4f4f4');
    ['count56','count10'].forEach(id=>{ const e=document.getElementById(id); if(e) e.textContent = id==='count56'?'56':'10'; });
    const avs = document.querySelectorAll('.avatar');
    avs.forEach(a=>a.style.transform='scale(1)');
  }

  function mix(c1,c2,t){
    const a=[parseInt(c1.slice(1,3),16),parseInt(c1.slice(3,5),16),parseInt(c1.slice(5,7),16)];
    const b=[parseInt(c2.slice(1,3),16),parseInt(c2.slice(3,5),16),parseInt(c2.slice(5,7),16)];
    const c=a.map((v,i)=>Math.round(v+(b[i]-v)*t));
    return 'rgb('+c.join(',')+')';
  }

  /* ---------- scroll: trust panel ---------- */
  function setupTrust(){
    const panel = document.getElementById('trust');
    const avs = document.querySelectorAll('.avatar');
    // reset avatar scale
    if(!
