<!DOCTYPE html>
<html lang="zh-CN" data-theme="dark">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Dracore - 让你的服务器 喷火，而不是冒烟</title>
<meta name="description" content="Dracore 是基于 Paper 深度优化的 Minecraft 服务端核心：极致优化、多线程、完全插件兼容、高度自定义。同场景实测性能对比 Leaf。">
<style>
  /* ================= 主题变量 ================= */
  :root[data-theme="dark"] {
    --bg: #121016; --bg-card: #1d1924; --bg-code: #0d0b11;
    --text: #f2ecf2; --text-dim: #b3aab6; --line: #2c2530;
    --card-bg: rgba(29,25,36,.82); --code-bg: rgba(13,11,17,.92);
    --nav-bg: rgba(18,16,22,.72); --th-bg: rgba(255,77,157,.10);
    --blob-op: .45; --shine: rgba(255,255,255,.05);
  }
  :root[data-theme="light"] {
    --bg: #faf8fb; --bg-card: #ffffff; --bg-code: #f4f1f6;
    --text: #1b1620; --text-dim: #564d5d; --line: #e3dbe6;
    --card-bg: rgba(255,255,255,.92); --code-bg: #f4f1f6;
    --nav-bg: rgba(255,255,255,.78); --th-bg: rgba(255,77,157,.08);
    --blob-op: .22; --shine: rgba(0,0,0,.04);
    /* 亮色下文字强调色整体加深，避免浅粉糊在白底上；渐变背景仍鲜艳 */
    --magenta: #e1308a; --pink: #c21f79; --pink-soft: #8f1459; --cm: #6a6372;
    --violet: #7c3aed; --ember: #ea7317; --val: #1f6fb5;
  }
  :root[data-theme="dark"] { --val: #5aa9e6; --cm: #7d7382; }
  :root {
    --magenta: #ff4d9d; --pink: #ff8fc0; --pink-soft: #ffc2db;
    --violet: #8b5cf6; --ember: #ff8a5c;
  }
  * { margin: 0; padding: 0; box-sizing: border-box; }
  html { scroll-behavior: smooth; }
  body {
    font-family: "PingFang SC", "Microsoft YaHei", "Segoe UI", system-ui, sans-serif;
    background: var(--bg); color: var(--text); line-height: 1.72;
    -webkit-font-smoothing: antialiased; overflow-x: hidden;
    transition: background .3s ease, color .3s ease;
  }
  a { color: var(--pink); text-decoration: none; }
  a:hover { color: var(--magenta); }
  .container { max-width: 1040px; margin: 0 auto; padding: 0 24px; }

  /* ===== 流动渐变背景 ===== */
  .bg-flow { position: fixed; inset: 0; z-index: -2; overflow: hidden; background: var(--bg); }
  .bg-flow .blob { position: absolute; border-radius: 50%; filter: blur(90px); opacity: var(--blob-op);
    animation: drift 26s ease-in-out infinite alternate; }
  .blob.b1 { width: 640px; height: 640px; left: -180px; top: -160px;
    background: radial-gradient(circle, rgba(255,77,157,.55), transparent 65%); }
  .blob.b2 { width: 560px; height: 560px; right: -160px; top: 18%;
    background: radial-gradient(circle, rgba(139,92,246,.42), transparent 65%); animation-duration: 32s; animation-delay: -8s; }
  .blob.b3 { width: 520px; height: 520px; left: 22%; bottom: -220px;
    background: radial-gradient(circle, rgba(255,138,92,.30), transparent 65%); animation-duration: 38s; animation-delay: -16s; }
  .blob.b4 { width: 460px; height: 460px; right: 18%; bottom: -120px;
    background: radial-gradient(circle, rgba(255,143,192,.35), transparent 65%); animation-duration: 30s; animation-delay: -20s; }
  @keyframes drift {
    0% { transform: translate(0,0) scale(1); }
    33% { transform: translate(120px,60px) scale(1.12); }
    66% { transform: translate(-70px,110px) scale(.94); }
    100% { transform: translate(60px,-70px) scale(1.08); }
  }
  .bg-flow::after {
    content: ""; position: absolute; inset: 0;
    background: radial-gradient(ellipse 70% 40% at 50% -5%, rgba(255,77,157,.14), transparent 70%);
  }

  /* ===== 流动渐变文字 ===== */
  .grad-flow {
    background: linear-gradient(90deg, var(--magenta), var(--violet), var(--ember), var(--pink), var(--magenta));
    background-size: 300% 100%;
    -webkit-background-clip: text; background-clip: text; color: transparent;
    animation: flowText 7s linear infinite;
  }
  @keyframes flowText { 0% { background-position: 0% 50%; } 100% { background-position: 300% 50%; } }

  /* ===== 龙标：emoji 仅作遮罩形状，颜色全来自背景渐变（纯单色） ===== */
  .dragon {
    display: inline-block; width: 1.25em; height: 1.25em; margin-right: 7px;
    vertical-align: -0.28em;
    background: linear-gradient(90deg, var(--magenta), var(--violet), var(--ember), var(--pink), var(--magenta));
    background-size: 300% 100%;
    animation: flowText 6s linear infinite;
    -webkit-mask-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 32 32'%3E%3Ctext x='0' y='27' font-size='28'%3E%F0%9F%90%89%3C/text%3E%3C/svg%3E");
    mask-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 32 32'%3E%3Ctext x='0' y='27' font-size='28'%3E%F0%9F%90%89%3C/text%3E%3C/svg%3E");
    -webkit-mask-size: contain; mask-size: contain;
    -webkit-mask-repeat: no-repeat; mask-repeat: no-repeat;
    -webkit-mask-position: center; mask-position: center;
  }

  /* ===== 导航 ===== */
  nav { position: sticky; top: 0; z-index: 100; backdrop-filter: blur(14px);
    background: var(--nav-bg); border-bottom: 1px solid var(--line); }
  .nav-inner { max-width: 1040px; margin: 0 auto; padding: 14px 24px;
    display: flex; align-items: center; justify-content: space-between; flex-wrap: wrap; gap: 8px; }
  .logo { font-weight: 800; font-size: 20px; letter-spacing: 1px; cursor: pointer; }
  .nav-right { display: flex; align-items: center; gap: 18px; }
  .nav-links { display: flex; gap: 20px; font-size: 14.5px; }
  .nav-links a { color: var(--text-dim); transition: color .2s; }
  .nav-links a:hover, .nav-links a.active { color: var(--pink); font-weight: 600; }
  .theme-btn {
    border: 1px solid var(--line); background: transparent; color: var(--text);
    border-radius: 999px; padding: 5px 12px; font-size: 13px; cursor: pointer;
    transition: border-color .2s, color .2s;
  }
  .theme-btn:hover { border-color: var(--magenta); color: var(--magenta); }

  /* ===== 视图切换 ===== */
  .view { display: none; }
  .view.active { display: block; }

  /* ===== Hero ===== */
  .hero { text-align: center; padding: 96px 24px 72px; }
  .badge { display: inline-block; font-size: 13px; color: var(--pink-soft); font-weight: 600;
    border: 1px solid rgba(255,77,157,.45); background: linear-gradient(120deg, rgba(255,77,157,.14), rgba(139,92,246,.14));
    background-size: 200% 100%; border-radius: 999px; padding: 4px 16px; margin-bottom: 22px;
    animation: flowText 9s linear infinite; }
  .hero h1 { font-size: clamp(34px, 6vw, 58px); font-weight: 800; line-height: 1.25; margin-bottom: 18px; }
  .hero p.sub { max-width: 660px; margin: 0 auto 36px; color: var(--text-dim); font-size: 17px; }
  .actions { display: flex; gap: 14px; justify-content: center; flex-wrap: wrap; }
  .btn { padding: 12px 30px; border-radius: 12px; font-size: 15px; font-weight: 600;
    transition: transform .15s ease, box-shadow .15s ease; display: inline-block; }
  .btn:hover { transform: translateY(-2px); }
  .btn-primary { background: linear-gradient(90deg, var(--magenta), var(--violet), var(--ember), var(--magenta));
    background-size: 300% 100%; animation: flowText 5s linear infinite; color: #1a0d14;
    box-shadow: 0 4px 28px rgba(255,77,157,.4); }
  .btn-ghost { border: 1px solid var(--line); color: var(--text); background: rgba(128,128,128,.04); }
  .stats { display: flex; gap: 52px; justify-content: center; margin-top: 56px; flex-wrap: wrap; }
  .stat b { display: block; font-size: 30px; }
  .stat span { font-size: 13.5px; color: var(--text-dim); }

  /* ===== 通用 section ===== */
  section { padding: 64px 0; }
  .sec-tag { font-size: 13px; letter-spacing: 2px; font-weight: 600; margin-bottom: 8px; }
  h2 { font-size: 30px; font-weight: 800; margin-bottom: 14px; }
  .sec-sub { color: var(--text-dim); max-width: 660px; }

  /* ===== 卡片 ===== */
  .bench { display: grid; grid-template-columns: repeat(auto-fit, minmax(210px,1fr)); gap: 16px; margin-top: 32px; }
  .bench-card { position: relative; background: var(--card-bg); border: 1px solid var(--line); border-radius: 14px;
    padding: 22px; overflow: hidden; transition: transform .15s, border-color .2s; }
  .bench-card::before { content: ""; position: absolute; inset: 0;
    background: linear-gradient(115deg, transparent 30%, var(--shine) 45%, transparent 60%);
    transform: translateX(-100%); transition: transform .7s ease; pointer-events: none; }
  .bench-card:hover::before { transform: translateX(100%); }
  .bench-card:hover { transform: translateY(-3px); }
  .bench-card b { font-size: 30px; }
  .bench-card span { display: block; margin-top: 6px; color: var(--text-dim); font-size: 14px; }
  .bench-card .note { font-size: 12px; color: var(--text-dim); margin-top: 10px; opacity: .85; }
  .bench-card.hl { border-color: rgba(255,77,157,.6);
    background: linear-gradient(160deg, rgba(255,77,157,.12), rgba(139,92,246,.08)), var(--card-bg);
    box-shadow: 0 0 34px rgba(255,77,157,.16); }
  /* 倍率徽章：卡片右上角悬浮，亮暗双主题都醒目 */
  .multiplier {
    display: block; width: -moz-fit-content; width: fit-content;
    margin: 0 0 12px 0; padding: 5px 13px; border-radius: 999px;
    font-size: 13px; font-weight: 800; letter-spacing: .3px; white-space: nowrap;
    background: linear-gradient(90deg, var(--magenta), var(--violet));
    color: #fff; text-shadow: 0 1px 2px rgba(0,0,0,.25);
    box-shadow: 0 4px 16px rgba(255,77,157,.5);
  }
  .features { display: grid; grid-template-columns: repeat(auto-fit, minmax(240px,1fr)); gap: 16px; margin-top: 32px; }
  .feature { background: var(--card-bg); border: 1px solid var(--line); border-radius: 14px; padding: 26px;
    transition: border-color .2s, transform .15s; }
  .feature:hover { border-color: rgba(255,77,157,.45); transform: translateY(-3px); }
  .feature .icon { font-size: 26px; margin-bottom: 12px; }
  .feature h3 { font-size: 17px; margin-bottom: 8px; }
  .feature p { color: var(--text-dim); font-size: 14.5px; }
  .card { background: var(--card-bg); border: 1px solid var(--line); border-radius: 14px; padding: 22px 24px; margin-bottom: 16px; }
  .card p { color: var(--text-dim); font-size: 14.5px; }
  .card p + p { margin-top: 8px; }
  h3 { font-size: 18px; font-weight: 700; margin: 26px 0 10px; }
  h3:first-child { margin-top: 0; }

  .config-wrap { display: grid; grid-template-columns: 1fr 1fr; gap: 32px; align-items: center; margin-top: 32px; }
  @media (max-width: 800px) { .config-wrap { grid-template-columns: 1fr; } }
  .config-list { list-style: none; }
  .config-list li { padding: 7px 0; color: var(--text-dim); font-size: 15px; }
  .config-list li::before { content: "◈ "; color: var(--magenta); }
  ul.list { list-style: none; margin: 10px 0; }
  ul.list li { padding: 5px 0; color: var(--text-dim); font-size: 14.5px; }
  ul.list li::before { content: "◈ "; color: var(--magenta); }
  ol.list { margin: 10px 0 10px 22px; color: var(--text-dim); font-size: 14.5px; }
  ol.list li { padding: 3px 0; }

  pre.code { background: var(--code-bg); border: 1px solid var(--line); border-radius: 14px;
    padding: 20px 22px; font-size: 13px; overflow-x: auto; line-height: 1.75;
    font-family: "Cascadia Code", Consolas, monospace; }
  pre.code .cm { color: var(--cm); }
  pre.code .key { color: var(--pink); }
  pre.code .val { color: var(--val); }

  table { width: 100%; border-collapse: collapse; margin: 14px 0; font-size: 14px; }
  th, td { border: 1px solid var(--line); padding: 9px 12px; text-align: left; vertical-align: top; }
  th { background: var(--th-bg); color: var(--pink-soft); font-weight: 700; }
  td { color: var(--text-dim); background: var(--card-bg); }
  td b { color: var(--text); }
  code { font-family: "Cascadia Code", Consolas, monospace; font-size: 13px;
    background: rgba(255,77,157,.10); border: 1px solid rgba(255,77,157,.25);
    border-radius: 6px; padding: 1px 7px; color: var(--pink-soft); }
  .warn { border-left: 3px solid var(--ember); background: rgba(255,138,92,.08);
    border-radius: 0 10px 10px 0; padding: 12px 16px; margin: 12px 0; color: var(--text-dim); font-size: 14px; }
  .tip { border-left: 3px solid var(--violet); background: rgba(139,92,246,.08);
    border-radius: 0 10px 10px 0; padding: 12px 16px; margin: 12px 0; color: var(--text-dim); font-size: 14px; }
  details { background: var(--card-bg); border: 1px solid var(--line); border-radius: 12px; padding: 16px 20px; margin-top: 12px; }
  details summary { cursor: pointer; font-weight: 600; font-size: 15px; }
  details p { margin-top: 10px; color: var(--text-dim); font-size: 14.5px; }

  /* ===== 下载页（LeafMC 风） ===== */
  .dl-hero { text-align: center; padding: 64px 24px 24px; }
  .dl-hero h1 { font-size: clamp(28px, 5vw, 42px); font-weight: 800; }
  .dl-hero p { color: var(--text-dim); margin-top: 10px; }
  .build { background: var(--card-bg); border: 1px solid var(--line); border-radius: 16px; padding: 26px; margin-top: 28px; }
  .build.latest { border-color: rgba(255,77,157,.55); box-shadow: 0 0 34px rgba(255,77,157,.14); }
  .build-head { display: flex; align-items: center; justify-content: space-between; flex-wrap: wrap; gap: 10px; }
  .build-title { font-size: 20px; font-weight: 800; }
  .build-tag { font-size: 12px; font-weight: 700; padding: 3px 10px; border-radius: 999px;
    background: linear-gradient(90deg, var(--magenta), var(--violet)); color: #fff; }
  .build-meta { display: flex; gap: 22px; flex-wrap: wrap; margin-top: 12px; font-size: 13.5px; color: var(--text-dim); }
  .build-meta b { color: var(--text); }
  .build-actions { display: flex; gap: 12px; margin-top: 18px; flex-wrap: wrap; }
  .changelog { margin-top: 16px; }
  .changelog li { padding: 4px 0; color: var(--text-dim); font-size: 14px; }

  /* ===== 文档页头 ===== */
  .doc-head { text-align: center; padding: 56px 24px 24px; }
  .doc-head h1 { font-size: clamp(30px, 5vw, 42px); font-weight: 800; }
  .doc-head p { color: var(--text-dim); margin-top: 10px; }
  .doc-nav { display: flex; gap: 12px; flex-wrap: wrap; justify-content: center; margin-top: 22px; font-size: 13.5px; }
  .doc-nav a { background: var(--card-bg); border: 1px solid var(--line); border-radius: 999px; padding: 5px 14px; }

  footer { border-top: 1px solid var(--line); padding: 34px 24px; text-align: center;
    color: var(--text-dim); font-size: 13.5px; margin-top: 40px; }

  /* ================= 移动端排版 ================= */
  /* 表格：小屏改为可横向滚动，避免撑破视口 */
  @media (max-width: 860px) {
    .table-scroll { overflow-x: auto; -webkit-overflow-scrolling: touch; }
    table { display: block; width: 100%; min-width: 620px; overflow-x: auto;
      -webkit-overflow-scrolling: touch; }
    table th, table td { white-space: normal; }
  }

  @media (max-width: 720px) {
    .container { padding: 0 16px; }
    .nav-inner { padding: 10px 16px; gap: 6px; }
    .logo { font-size: 17px; }
    .nav-right { width: 100%; justify-content: space-between; gap: 10px; }
    .nav-links { gap: 14px; font-size: 13px; flex-wrap: wrap; }
    .theme-btn { padding: 4px 10px; font-size: 12px; }

    .hero { padding: 56px 18px 40px; }
    .hero h1 { font-size: clamp(26px, 8vw, 38px); }
    .hero p.sub { font-size: 15.5px; margin-bottom: 26px; }
    .badge { font-size: 12px; padding: 4px 12px; }
    .actions { flex-direction: column; align-items: center; gap: 10px; }
    .btn { width: 100%; max-width: 320px; text-align: center; padding: 13px 20px; }
    .stats { gap: 24px 32px; margin-top: 36px; }
    .stat b { font-size: 25px; }
    .stat span { font-size: 12.5px; }

    section { padding: 44px 0; }
    h2 { font-size: 24px; }
    .sec-sub { font-size: 14.5px; }
    .bench, .features { grid-template-columns: 1fr; gap: 12px; }
    .bench-card, .feature, .card, .build { padding: 18px; }
    .card { padding: 18px 18px; }
    .config-wrap { gap: 20px; }
    pre.code { font-size: 12px; padding: 14px 16px; }

    .doc-head { padding: 36px 18px 12px; }
    .doc-head h1 { font-size: clamp(24px, 7vw, 32px); }
    .doc-nav { gap: 8px; font-size: 12.5px; }
    .doc-nav a { padding: 4px 11px; }
    details { padding: 13px 15px; }
    details summary { font-size: 14.5px; }
    .faq-intro { margin-bottom:18px; }
    .faq-group-label { margin-top:24px; }
    details p, .card p, .feature p { font-size: 14px; }

    .dl-hero { padding: 40px 18px 8px; }
    .build-head { flex-direction: column; align-items: flex-start; gap: 8px; }
    .build-meta { gap: 8px 16px; font-size: 13px; }
    .build-title { font-size: 18px; }

    footer { padding: 26px 16px; font-size: 12.5px; }
  }

  @media (max-width: 420px) {
    .nav-links { gap: 11px; font-size: 12.5px; }
    .stat b { font-size: 22px; }
    .stats { gap: 18px 24px; }
    .multiplier { font-size: 11.5px; padding: 4px 10px; }
  }

  /* =========================================================
     Dracore UI Refresh — performance dashboard + glass system
     ========================================================= */
  :root {
    --radius-lg: 22px;
    --radius-md: 16px;
    --glass-border: rgba(255,255,255,.09);
    --shadow-soft: 0 18px 60px rgba(0,0,0,.20);
  }
  :root[data-theme="light"] {
    --glass-border: rgba(40,25,50,.09);
    --shadow-soft: 0 18px 60px rgba(80,40,90,.10);
  }

  body {
    background:
      radial-gradient(900px 500px at 50% -180px, rgba(255,77,157,.10), transparent 70%),
      var(--bg);
  }

  .bg-flow::before {
    content:"";
    position:absolute;
    inset:0;
    opacity:.28;
    background-image:
      linear-gradient(rgba(255,255,255,.025) 1px, transparent 1px),
      linear-gradient(90deg, rgba(255,255,255,.025) 1px, transparent 1px);
    background-size:42px 42px;
    mask-image:linear-gradient(to bottom, #000, transparent 72%);
    pointer-events:none;
  }

  nav {
    background: color-mix(in srgb, var(--bg) 72%, transparent);
    box-shadow: 0 1px 0 rgba(255,255,255,.025);
  }
  .nav-inner { min-height:64px; }
  .logo { font-size:21px; }
  .nav-links a {
    position:relative;
    padding:7px 1px;
  }
  .nav-links a::after {
    content:"";
    position:absolute;
    left:0; right:0; bottom:0;
    height:2px;
    border-radius:99px;
    background:linear-gradient(90deg,var(--magenta),var(--violet));
    transform:scaleX(0);
    transform-origin:center;
    transition:transform .22s ease;
  }
  .nav-links a:hover::after,
  .nav-links a.active::after { transform:scaleX(1); }

  .theme-btn {
    background:rgba(255,255,255,.035);
    backdrop-filter:blur(10px);
  }

  .hero {
    position:relative;
    padding-top:112px;
  }
  .hero::before {
    content:"";
    position:absolute;
    width:540px;
    height:260px;
    left:50%;
    top:80px;
    transform:translateX(-50%);
    background:radial-gradient(ellipse,rgba(255,77,157,.12),transparent 68%);
    filter:blur(10px);
    pointer-events:none;
  }
  .hero > * { position:relative; }
  .hero h1 {
    letter-spacing:-1.8px;
    text-shadow:0 8px 40px rgba(255,77,157,.10);
  }
  .hero p.sub {
    line-height:1.85;
    font-size:16px;
  }

  .hero-status {
    display:inline-flex;
    align-items:center;
    gap:10px;
    padding:8px 13px;
    margin-bottom:25px;
    border:1px solid var(--line);
    border-radius:999px;
    background:rgba(255,255,255,.035);
    box-shadow:0 8px 30px rgba(0,0,0,.10);
    color:var(--text-dim);
    font-size:12px;
    letter-spacing:.2px;
    backdrop-filter:blur(12px);
  }
  .hero-status i {
    width:3px; height:3px; border-radius:50%;
    background:var(--line);
  }
  .status-dot,.live-dot {
    display:inline-block;
    width:7px;height:7px;border-radius:50%;
    background:#5ee28a;
    box-shadow:0 0 0 4px rgba(94,226,138,.10),0 0 14px rgba(94,226,138,.5);
  }

  .performance-strip {
    position:relative;
    display:grid;
    grid-template-columns:1.45fr 1px .9fr .9fr .9fr;
    align-items:center;
    max-width:900px;
    margin:54px auto 0;
    padding:18px 8px;
    border:1px solid var(--glass-border);
    border-radius:20px;
    background:linear-gradient(120deg,rgba(255,255,255,.055),rgba(255,255,255,.018));
    box-shadow:var(--shadow-soft);
    backdrop-filter:blur(18px);
    text-align:left;
    overflow:hidden;
  }
  .performance-strip::before {
    content:"";
    position:absolute;
    inset:0;
    background:linear-gradient(110deg,transparent 0%,rgba(255,77,157,.06) 45%,transparent 72%);
    pointer-events:none;
  }
  .perf-main,.perf-item { padding:5px 22px; position:relative; z-index:1; }
  .perf-label {
    display:flex;align-items:center;gap:9px;
    color:var(--text-dim);font-size:12px;
    text-transform:uppercase;letter-spacing:1.2px;
  }
  .perf-value {
    margin:2px 0 -2px;
    font-size:42px;font-weight:850;line-height:1.05;
    letter-spacing:-1.5px;
  }
  .perf-sub { color:var(--text-dim);font-size:12px; }
  .perf-sub b { color:var(--text); }
  .perf-divider { height:48px;background:var(--line); }
  .perf-item span {
    display:block;color:var(--text-dim);font-size:11px;
    letter-spacing:.4px;margin-bottom:3px;
  }
  .perf-item b {
    display:block;font-size:25px;line-height:1.1;
    letter-spacing:-.6px;
  }
  .perf-item b span { display:inline;font-size:13px;margin-left:2px;color:var(--text-dim); }
  .perf-item b.accent { color:var(--pink); }
  .perf-item small { color:var(--text-dim);font-size:11px; }

  .actions .btn {
    border-radius:13px;
    box-shadow:none;
  }
  .btn-primary {
    box-shadow:0 10px 35px rgba(255,77,157,.24);
  }

  section { position:relative; }
  section::before {
    content:"";
    position:absolute;
    left:50%; top:0;
    width:min(900px,90%);
    height:1px;
    transform:translateX(-50%);
    background:linear-gradient(90deg,transparent,var(--line),transparent);
    opacity:.7;
  }
  .sec-tag { display:flex;align-items:center;gap:12px; }
  .sec-tag::after {
    content:"";
    width:42px;height:1px;
    background:linear-gradient(90deg,var(--magenta),transparent);
  }
  h2 { letter-spacing:-.6px; }

  .bench {
    grid-template-columns:1.15fr .85fr .85fr .85fr;
    align-items:stretch;
  }
  .bench-card {
    border-radius:18px;
    padding:23px;
    min-height:170px;
    box-shadow:0 10px 35px rgba(0,0,0,.07);
  }
  .bench-card.hl {
    border-color:rgba(255,77,157,.42);
    box-shadow:0 16px 55px rgba(255,77,157,.12);
  }
  .bench-card b { font-size:32px; letter-spacing:-1px; }
  .bench-kicker {
    display:flex;
    align-items:center;
    gap:7px;
    margin-bottom:16px;
    font-size:11px;
    color:var(--text-dim);
  }
  .bench-icon {
    width:23px;height:23px;display:grid;place-items:center;
    border-radius:7px;
    background:rgba(255,77,157,.12);
    color:var(--pink);font-weight:800;
  }
  .bench-kicker strong {
    margin-left:auto;
    color:var(--text);
    font-size:13px;
  }
  .bench-kicker em { font-style:normal;color:var(--pink-soft);font-size:11px; }
  .bench-card.hl > .grad-flow { display:block; }
  .multiplier { margin-bottom:12px; }

  .feature,.card,.build,details {
    border-radius:18px;
    box-shadow:0 10px 40px rgba(0,0,0,.055);
  }
  .feature { padding:25px; }
  .feature .icon {
    width:42px;height:42px;display:grid;place-items:center;
    border:1px solid var(--line);border-radius:12px;
    background:linear-gradient(135deg,rgba(255,77,157,.12),rgba(139,92,246,.08));
    font-size:21px;
  }
  .feature h3 { margin-top:0; }

  table { border-collapse:separate;border-spacing:0;overflow:hidden;border-radius:14px; }
  th:first-child { border-radius:12px 0 0 0; }
  th:last-child { border-radius:0 12px 0 0; }
  th,td { border-right:0;border-bottom:1px solid var(--line); }
  tr:last-child td { border-bottom:0; }
  th { padding:11px 13px; }
  td { padding:10px 13px; }

  pre.code {
    border-radius:16px;
    box-shadow:inset 0 1px 0 rgba(255,255,255,.025);
  }

  .build {
    padding:28px;
    position:relative;
    overflow:hidden;
  }
  .build.latest::after {
    content:"";
    position:absolute;
    width:230px;height:230px;
    right:-100px;top:-110px;
    background:radial-gradient(circle,rgba(255,77,157,.16),transparent 68%);
    pointer-events:none;
  }

  details {
    transition:border-color .2s,background .2s;
  }
  details:hover { border-color:rgba(255,77,157,.30); }
  details summary { list-style:none; }
  details summary::-webkit-details-marker { display:none; }
  details summary::before {
    content:"＋";
    display:inline-grid;place-items:center;
    width:23px;height:23px;margin-right:10px;
    border-radius:7px;background:rgba(255,77,157,.09);
    color:var(--pink);
    transition:transform .2s;
  }
  details[open] summary::before { content:"−"; }
  .faq-intro { margin: 0 auto 24px; max-width: 900px; line-height: 1.8; }
  .faq-group-label { display:flex; align-items:center; gap:12px; margin:30px 2px 10px; font-size:13px; font-weight:700; letter-spacing:.5px; color:var(--text-dim); }
  .faq-group-label .grad-flow { font-size:11px; letter-spacing:1.5px; font-weight:800; }
  .faq-group-label::before { content:""; width:3px; height:18px; border-radius:99px; background:linear-gradient(180deg,var(--magenta),var(--violet)); }
  .faq-group-label:first-child { margin-top:0; }

  footer { background:rgba(0,0,0,.06); }

  @media (max-width: 900px) {
    .bench { grid-template-columns:1fr 1fr; }
    .performance-strip { grid-template-columns:1.4fr 1px 1fr 1fr; }
    .perf-item:last-child { display:none; }
  }
  @media (max-width: 720px) {
    .hero { padding-top:72px; }
    .hero-status { max-width:100%; flex-wrap:wrap; justify-content:center; }
    .performance-strip {
      grid-template-columns:1fr 1fr;
      gap:0;
      padding:14px;
      text-align:center;
    }
    .perf-main { grid-column:1/-1; padding:8px 8px 18px; }
    .perf-divider { display:none; }
    .perf-item { padding:12px 8px; }
    .perf-label { justify-content:center; }
    .perf-sub { margin-top:3px; }
    .bench { grid-template-columns:1fr; }
    .bench-card { min-height:auto; }
  }
  @media (max-width: 420px) {
    .hero-status i { display:none; }
    .hero-status { gap:7px; }
    .performance-strip { border-radius:17px; }
    .perf-value { font-size:38px; }
  }


/* =========================================================
   Dracore Mature UI — production-grade visual system
   ========================================================= */
:root{
  --max:1180px;
  --surface:rgba(18,17,23,.78);
  --surface-2:rgba(255,255,255,.035);
  --border:rgba(255,255,255,.095);
  --border-strong:rgba(255,77,157,.30);
  --muted:#9e97a6;
  --muted-2:#716a78;
  --green:#65d89a;
  --blue:#69a9ff;
  --danger:#ff9a72;
}
:root[data-theme="light"]{
  --surface:rgba(255,255,255,.86);
  --surface-2:rgba(30,20,35,.025);
  --border:rgba(45,25,55,.11);
  --border-strong:rgba(190,30,115,.28);
  --muted:#625a68;
  --muted-2:#8a8190;
}
body{
  letter-spacing:.005em;
  background:
    radial-gradient(900px 420px at 50% -220px,rgba(255,77,157,.13),transparent 72%),
    var(--bg);
}
body::selection{background:rgba(255,77,157,.28)}
.container{max-width:var(--max)}
nav{
  height:68px;
  background:color-mix(in srgb,var(--bg) 78%,transparent);
  border-bottom:1px solid var(--border);
  backdrop-filter:blur(22px) saturate(140%);
}
.nav-inner{max-width:var(--max);height:68px;padding:0 24px}
.logo{display:flex;align-items:center;gap:0;white-space:nowrap}
.nav-right{gap:22px}
.nav-links{gap:24px}
.nav-links a{font-size:13px;font-weight:600;color:var(--muted);letter-spacing:.15px}
.nav-links a.active{color:var(--text)}
.nav-meta{display:flex;align-items:center;gap:9px;font-size:11px;color:var(--muted)}
.nav-version{
  padding:4px 8px;border:1px solid var(--border);border-radius:6px;
  background:var(--surface-2);font-family:"Cascadia Code",Consolas,monospace;color:var(--text)
}
.nav-sep{width:1px;height:14px;background:var(--border)}
.nav-status{display:flex;align-items:center;gap:6px}
.nav-status i{
  width:6px;height:6px;border-radius:50%;background:var(--green);
  box-shadow:0 0 10px rgba(101,216,154,.45)
}
.theme-btn{font-size:12px;padding:6px 10px;border-radius:8px;background:var(--surface-2)}
.hero{max-width:980px;margin:auto;padding:104px 24px 38px}
.hero-status{
  border-color:var(--border);background:var(--surface-2);
  box-shadow:0 12px 50px rgba(0,0,0,.10)
}
.hero h1{word-break:keep-all;overflow-wrap:normal;font-size:clamp(42px,6.5vw,72px);line-height:1.1;letter-spacing:-2.8px;margin-bottom:24px}
.hero p.sub{max-width:760px;color:var(--muted);font-size:16px;line-height:1.95}
.hero p.sub b{color:var(--text);font-weight:650}
.actions{margin-top:32px}
.btn{border-radius:9px;padding:11px 20px;font-size:13px;letter-spacing:.1px}
.btn-primary{
  color:#fff;
  background:linear-gradient(135deg,#f23f92,#8b5cf6);
  box-shadow:0 12px 32px rgba(255,77,157,.18);
}
.btn-primary:hover{box-shadow:0 16px 38px rgba(255,77,157,.26)}
.btn-ghost{background:var(--surface-2);border-color:var(--border);color:var(--text)}
.btn-disabled{cursor:not-allowed;opacity:.55;box-shadow:none!important}
.performance-strip{
  max-width:980px;margin:48px auto 0;
  border-radius:14px;padding:10px;
  background:var(--surface);
  border:1px solid var(--border);
  box-shadow:0 24px 80px rgba(0,0,0,.14);
  backdrop-filter:blur(22px)
}
.perf-main,.perf-item{padding:12px 20px}
.perf-value{font-size:46px}
.perf-item b{font-size:24px}
.hero-trust{
  max-width:980px;margin:22px auto 0;
  display:grid;grid-template-columns:repeat(3,1fr);
  border:1px solid var(--border);border-radius:12px;overflow:hidden;
  background:var(--surface-2)
}
.hero-trust>div{
  display:flex;align-items:center;gap:12px;padding:15px 18px;
  border-right:1px solid var(--border)
}
.hero-trust>div:last-child{border-right:0}
.trust-icon{
  width:28px;height:28px;display:grid;place-items:center;border:1px solid var(--border);
  border-radius:7px;font:700 10px "Cascadia Code",Consolas,monospace;color:var(--pink)
}
.hero-trust b{display:block;font-size:12px;font-weight:700}
.hero-trust small{display:block;margin-top:2px;color:var(--muted-2);font-size:10px}
section{padding:86px 0}
section::before{background:linear-gradient(90deg,transparent,var(--border),transparent)}
.sec-tag{font-size:11px;letter-spacing:2.4px}
h2{font-size:31px;letter-spacing:-1px}
.sec-sub{font-size:14px;line-height:1.85;color:var(--muted)}
.bench{gap:12px;margin-top:28px}
.bench-card{
  min-height:180px;padding:21px;border-radius:14px;
  background:var(--surface);border-color:var(--border);
  box-shadow:0 15px 45px rgba(0,0,0,.07)
}
.bench-card:hover{transform:translateY(-2px);border-color:var(--border-strong)}
.bench-card.hl{background:linear-gradient(145deg,rgba(255,77,157,.09),rgba(139,92,246,.05)),var(--surface)}
.bench-card b{font-size:30px}
.bench-kicker{margin-bottom:22px}
.features{gap:12px;margin-top:28px}
.feature{
  min-height:205px;padding:23px;border-radius:14px;
  background:var(--surface);border-color:var(--border)
}
.feature:hover{border-color:var(--border-strong)}
.feature .icon{width:38px;height:38px;border-radius:9px;font-size:17px}
.feature h3{font-size:16px;margin:17px 0 8px}
.feature p{font-size:13.5px;line-height:1.8}
.card,.build,details{
  background:var(--surface);border-color:var(--border);border-radius:14px;
  box-shadow:0 15px 55px rgba(0,0,0,.06)
}
.card{padding:22px}
.config-wrap{gap:22px}
pre.code{
  background:rgba(5,5,8,.72);border-color:var(--border);
  border-radius:11px;font-size:12px;padding:18px
}
:root[data-theme="light"] pre.code{background:#f5f2f7}
table{font-size:13px}
th{font-size:12px;text-transform:none;letter-spacing:.2px}
td{line-height:1.7}
code{font-size:11px;padding:2px 6px}
.warn,.tip{font-size:13px;border-radius:0 8px 8px 0}
details{padding:0;margin-top:8px;overflow:hidden}
details summary{
  display:flex;align-items:center;padding:16px 18px;
  font-size:14px;min-height:54px
}
details summary::before{flex:0 0 auto}
details p{padding:0 18px 18px;margin-top:0;font-size:13.5px;line-height:1.85}
.doc-head{padding:68px 24px 30px}
.doc-head h1{font-size:42px;letter-spacing:-1.3px}
.doc-head p{font-size:14px;color:var(--muted)}
.doc-nav a{
  padding:6px 12px;border-radius:7px;font-size:12px;background:var(--surface);
  border-color:var(--border)
}
.view-docs .container{position:relative}
.docs-toc{
  position:fixed;z-index:20;top:94px;
  left:calc(50% + 500px);
  width:168px;padding:13px;
  border:1px solid var(--border);border-radius:12px;
  background:color-mix(in srgb,var(--bg) 84%,transparent);
  backdrop-filter:blur(18px);
  box-shadow:0 18px 55px rgba(0,0,0,.10)
}
.toc-title{font:700 9px "Cascadia Code",Consolas,monospace;letter-spacing:1.7px;color:var(--muted-2);margin:3px 7px 9px}
.docs-toc a{display:block;padding:7px 8px;border-radius:6px;color:var(--muted);font-size:11px}
.docs-toc a:hover{background:var(--surface-2);color:var(--text)}
.faq-toolbar{
  max-width:900px;margin:0 auto 14px;display:flex;align-items:center;gap:10px
}
.faq-search{
  flex:1;display:flex;align-items:center;gap:8px;padding:0 12px;height:42px;
  border:1px solid var(--border);border-radius:9px;background:var(--surface)
}
.faq-search span{font-size:19px;color:var(--muted)}
.faq-search input{
  width:100%;border:0;outline:0;background:transparent;color:var(--text);
  font:13px inherit
}
.faq-count{font-size:11px;color:var(--muted-2);white-space:nowrap}
.faq-hidden{display:none!important}
.build{padding:25px}
.build-title{font-size:19px}
.build-meta{font-size:12px}
.build-tag{font-size:10px;letter-spacing:.5px}
footer{
  max-width:none;margin-top:70px;padding:38px 24px;
  background:rgba(0,0,0,.08);border-top:1px solid var(--border)
}
footer p{font-size:12px}
@media (max-width:1260px){.docs-toc{display:none}}
@media (max-width:860px){
  .nav-meta{display:none}
  .hero-trust{grid-template-columns:1fr}
  .hero-trust>div{border-right:0;border-bottom:1px solid var(--border)}
  .hero-trust>div:last-child{border-bottom:0}
  .performance-strip{border-radius:13px}
}
@media (max-width:720px){
  nav,.nav-inner{height:60px}
  .nav-inner{padding:0 16px}
  .nav-right{gap:12px}
  .nav-links{gap:13px}
  .nav-links a{font-size:12px}
  .hero{padding:76px 18px 28px}
  .hero h1{word-break:keep-all;overflow-wrap:normal;font-size:clamp(36px,11vw,50px);letter-spacing:-1.8px}
  .hero p.sub{font-size:14px}
  .hero-status{font-size:10px}
  .hero-trust{margin-top:18px}
  section{padding:62px 0}
  h2{font-size:25px}
  .doc-head{padding-top:46px}
  .doc-head h1{font-size:32px}
  .faq-toolbar{align-items:stretch;flex-direction:column}
  .faq-count{padding-left:3px}
}
@media (prefers-reduced-motion:reduce){
  *,*::before,*::after{animation-duration:.01ms!important;animation-iteration-count:1!important;scroll-behavior:auto!important;transition:none!important}
}

.docs-toc a.toc-active{color:var(--text);background:var(--surface-2);box-shadow:inset 2px 0 0 var(--magenta)}
</style>
</head>
<body>

<div class="bg-flow">
  <div class="blob b1"></div><div class="blob b2"></div><div class="blob b3"></div><div class="blob b4"></div>
</div>

<nav>
  <div class="nav-inner">
    <div class="logo" onclick="go('home')"><span class="dragon" aria-hidden="true"></span><span class="grad-flow">Dracore</span></div>
    <div class="nav-right">
      <div class="nav-links">
        <a href="#/home" data-nav="home" class="active">首页</a>
        <a href="#/docs" data-nav="docs">文档</a>
        <a href="#/download" data-nav="download">下载</a>
        <a href="#/faq" data-nav="faq">FAQ</a>
      </div>
      <div class="nav-meta" aria-label="项目状态">
        <span class="nav-version">1.21.11</span><span class="nav-sep"></span><span class="nav-status"><i></i>稳定构建</span>
      </div>
      <button class="theme-btn" id="themeBtn" onclick="toggleTheme()">☀ 亮色</button>
    </div>
  </div>
</nav>

<!-- ================= 首页 ================= -->
<div class="view active" id="view-home">
  <header class="hero">
    <div class="hero-status"><span class="status-dot"></span><span>Paper 1.21.11</span><i></i><span>Ryzen 9 7940HX 实测</span><i></i><span>性能压测模式</span></div>
    <h1>让你的服务器 <span class="grad-flow">喷火<br>而不是冒烟</span></h1>
    <p class="sub">
      Dracore —— <b>拳打 Paper，脚踩 Folia</b><br>
      同场景 150 假人实测 <b>TPS 峰值 15.9</b>，是 Leaf 的 2 倍多<br>
      <b>优化、稳定、兼容、多线程，全都要，而且全都要最好</b>
    </p>
    <div class="actions">
      <a class="btn btn-primary" href="#/download">获取 Dracore</a>
      <a class="btn btn-ghost" href="#/docs">查看文档</a>
    </div>
    <div class="performance-strip">
      <div class="perf-main">
        <div class="perf-label"><span class="live-dot"></span>峰值 TPS</div>
        <div class="perf-value grad-flow">15.9</div>
        <div class="perf-sub">平均 <b>14.5</b> · 150 假人 · 5 分钟采样</div>
      </div>
      <div class="perf-divider"></div>
      <div class="perf-item">
        <span>平均 MSPT</span>
        <b>64.8<span>ms</span></b>
      </div>
      <div class="perf-item">
        <span>性能优势</span>
        <b class="accent">2.04<span>×</span></b>
        <small>相对 Leaf</small>
      </div>
      <div class="perf-item">
        <span>优化补丁</span>
        <b>40<span>+</span></b>
        <small>持续迭代</small>
      </div>
    </div>
    <div class="hero-trust">
      <div><span class="trust-icon">01</span><div><b>基于 Paper 生态</b><small>Bukkit / Spigot / Paper API</small></div></div>
      <div><span class="trust-icon">02</span><div><b>面向生产环境</b><small>保守默认 · 明确行为差异</small></div></div>
      <div><span class="trust-icon">03</span><div><b>可观测与可回退</b><small>spark · 日志 · 配置级控制</small></div></div>
    </div>
  </header>

  <section id="bench">
    <div class="container">
      <div class="sec-tag"><span class="grad-flow">BENCHMARK</span></div>
      <h2>基准测试结果</h2>
      <p class="sec-sub">同一份世界、150 个假人（半径 1000 漫游）、相同 JVM 参数（Aikar G1 flags + GC 日志），全部性能选项开启，实测 5 分钟取值。数据只展示同条件下的实测结果。</p>
      <div class="bench">
        <div class="bench-card hl"><div class="bench-kicker"><span class="bench-icon">↗</span><span>性能领先</span><strong>2.04×</strong><em>vs Leaf</em></div><b class="grad-flow">14.5 TPS</b><span>Dracore 全开 · 峰值 15.9</span><div class="note">MSPT 64.8ms · Ryzen 9 7940HX 本机实测</div></div>
        <div class="bench-card"><b>7.1 TPS</b><span>Leaf 全开 · 对照组</span><div class="note">MSPT 139.6ms · 相同 JVM 参数，依旧跑不动</div></div>
        <div class="bench-card"><b>8.9 TPS</b><span>Dracore 路径点治理前</span><div class="note">砍掉一个 O(n²) 系统 = 白捡 5.6 TPS</div></div>
        <div class="bench-card"><b>2.8 TPS</b><span>Paper 原版（对照组）</span><div class="note">同一世界同一批假人，原版就是这么惨</div></div>
      </div>
      <p class="sec-sub" style="margin-top:18px;">💡 同一份世界、同一批假人、同一套参数——<b>如果你的 CPU 比作者的 7940HX 更强，你的成绩只会比这里更漂亮。</b>瓶颈从来不在 Dracore，在你敢给它多大的世界。</p>
    </div>
  </section>

  <section id="features">
    <div class="container">
      <div class="sec-tag"><span class="grad-flow">FEATURES</span></div>
      <h2>为生产环境设计的核心能力</h2>
      <div class="features">
        <div class="feature"><div class="icon">⚡</div><h3>热点路径优化</h3>
          <p>定位栏 O(n²) 治理、biome 三路缓存、装备数组化、K-D 树玩家查找、异步全家桶——每一条都对着火焰图热点开火，每一发都实测命中。砍出来的 5.6 TPS，就是证据。</p></div>
        <div class="feature"><div class="icon">🧵</div><h3>可选并行与异步</h3>
          <p>实体追踪、刷怪统计、区块包序列化、寻路各自独立线程化，SparklyPaper 并行世界 tick 完整移植。你的 CPU 有几核，Dracore 就用几核。</p></div>
        <div class="feature"><div class="icon">🔌</div><h3>Paper 生态兼容</h3>
          <p>构建于 Paper 之上，继承完整 Bukkit/Paper/Spigot API。能在 Paper 上跑的插件就能在 Dracore 上跑——换核心像换电池一样简单。</p></div>
        <div class="feature"><div class="icon">🎮</div><h3>可控的行为差异</h3>
          <p>1.8 式战斗手感（击退、格挡）内建，红石引擎可自选 ALTERNATE_CURRENT，全中文配置带风险标注——性能拉满，玩法一点不少。</p></div>
      </div>
    </div>
  </section>

  <section id="config">
    <div class="container">
      <div class="sec-tag"><span class="grad-flow">CONFIG</span></div>
      <h2>配置透明，风险可见</h2>
      <p class="sec-sub">config 目录下自动生成，每个开关上方都有中文说明；危险的选项带明确警告，不危言耸听。完整开关表见<a href="#/docs">文档</a>。</p>
      <div class="config-wrap">
        <ul class="config-list">
          <li>首次启动自动生成 config/dracore.yml</li>
          <li>/dracore reload 热重载，需重启的项明确标注</li>
          <li>危险选项带「⚠ 警告」注释，说清开了会发生什么</li>
          <li>战斗 / 性能 / 趣味 / 中文 分区管理</li>
        </ul>
        <pre class="code"><span class="cm"># Dracore 配置文件（节选）</span>
<span class="key">性能</span>:
  <span class="key">路径点更新节流</span>: <span class="val">4</span>
  <span class="cm"># 0 = 彻底禁用，主线程收益极大</span>
  <span class="key">缓存biome</span>:
    <span class="key">启用</span>: <span class="val">true</span>
    <span class="key">刷怪路径</span>: <span class="val">true</span>
  <span class="key">异步实体追踪</span>: <span class="val">true</span>
<span class="key">战斗</span>:
  <span class="key">击退</span>:
    <span class="key">启用1点8式击退</span>: <span class="val">true</span>
<span class="cm"># ……更多配置项见完整文件</span></pre>
      </div>
    </div>
  </section>
</div>

<!-- ================= FAQ（独立视图） ================= -->
<div class="view" id="view-faq">
  <div class="container">
    <div class="doc-head">
      <h1>常见问题 <span class="grad-flow">FAQ</span></h1>
      <p>从兼容性、迁移、性能到多线程，把换核心前最常问的问题一次讲清楚。</p>
    </div>
    <div class="faq-intro card"><strong>先看这里：</strong> Dracore 是面向 Paper 生态的性能向服务端核心，强调可回退、可诊断和插件生态兼容。FAQ 按成熟服务端核心常见的兼容性、升级、性能、配置和多线程问题重新整理。</div>
    <div class="faq-toolbar">
      <div class="faq-search">
        <span>⌕</span><input id="faqSearch" type="search" placeholder="搜索 FAQ，例如：插件兼容、TPS、Folia、配置……" autocomplete="off">
      </div>
      <div class="faq-count" id="faqCount">全部问题</div>
    </div>
    <div class="faq-grid" style="max-width:900px;margin:0 auto;">
      <div class="faq-group-label"><span class="grad-flow">CORE</span><span>核心与兼容性</span></div>
      <details data-faq><summary>Dracore 是 Paper 的分支吗？</summary><p>是。Dracore 构建于 Paper 生态之上，目标是在保持 Bukkit / Spigot / Paper 插件生态的前提下加入性能优化与可选的多线程能力。核心级改动会明确记录在文档的「行为差异」与配置章节。</p></details>
      <details data-faq><summary>Paper / Spigot 插件能直接用吗？</summary><p>设计目标是保持 Paper 兼容性，因此绝大多数 Bukkit、Spigot、Paper 插件无需修改即可运行。但任何服务端核心都不能保证所有插件的内部实现都兼容；如果插件依赖未公开的内部实现、特定版本 NMS 或线程模型，就应该先在测试服验证。</p></details>
      <details data-faq><summary>为什么不是“100% 插件兼容”？</summary><p>插件可能依赖 Paper 的内部实现，而不仅仅是公开 API。成熟的服务端核心通常会把“API 兼容”和“所有第三方插件永远兼容”区分开来。遇到问题时，请先用最小插件集复现，再提供 crash-report、插件列表和复现步骤。</p></details>
      <details data-faq><summary>Dracore 会修改原版玩法吗？</summary><p>默认优先保持 Paper 行为。可能改变玩法或时序的项目会作为独立配置提供，例如路径点更新节流、DAB、生物激活范围、部分红石参数以及可选的 1.8 战斗机制。每项都应该能够在「行为差异」中找到对应说明。</p></details>

      <div class="faq-group-label"><span class="grad-flow">MIGRATION</span><span>迁移与升级</span></div>
      <details data-faq><summary>从 Paper / Leaf 迁移需要重做世界吗？</summary><p>正常情况下不需要。停服后完整备份服务器目录，再替换核心并启动即可。插件、世界和大多数服务端配置继续使用原文件；首次启动后再按 Dracore 文档检查新增配置。任何核心更换都建议先在测试服验证。</p></details>
      <details data-faq><summary>从 Leaf 换到 Dracore 最大的区别是什么？</summary><p>Leaf 同样强调性能、稳定性与 Paper 兼容性；Dracore 更强调“可选优化 + 可诊断 + 逐项异步化”的路线。不要只看宣传倍率，真正决定生产环境体验的是插件兼容、实际负载、MSPT、GC 和长期稳定性。</p></details>
      <details data-faq><summary>Dracore 会跟进上游版本吗？</summary><p>服务端核心依赖上游 Minecraft / Paper 的更新。正式生产服建议优先选择已经完成构建、测试与插件验证的版本，而不是仅仅因为版本号更新就立即升级。升级前应阅读变更日志并保留可回滚的旧核心。</p></details>
      <details data-faq><summary>升级核心前最重要的事情是什么？</summary><p>备份。至少保留世界、玩家数据、插件配置、核心配置和当前可运行的核心 JAR。升级后先在测试环境启动并观察日志，再逐步恢复插件与高负载玩法。</p></details>

      <div class="faq-group-label"><span class="grad-flow">PERFORMANCE</span><span>性能与压测</span></div>
      <details data-faq><summary>TPS、MSPT 到底应该看哪个？</summary><p>两者都看。TPS 更适合快速判断服务器是否跟得上 20 tick/s；MSPT 更适合定位每 tick 的计算成本。理想状态是接近 20 TPS，同时 MSPT 稳定低于 50ms。出现卡顿时还应结合 spark、GC 日志和插件负载判断瓶颈，而不是只看一个数字。</p></details>
      <details data-faq><summary>Dracore 的实测数据怎么来的？</summary><p>当前展示的数据来自同一份测试世界、150 个假人、相同 JVM 参数和相同测试流程；正式计时前进行预热，并持续采样 TPS / MSPT。首页展示的是当前这组基准数据，不代表所有硬件、世界和插件组合都能得到相同结果。</p></details>
      <details data-faq><summary>为什么我的 TPS 和官网不一样？</summary><p>这是正常的。CPU 单核性能、世界复杂度、模拟距离、区块加载、实体数量、插件、红石机器、GC 和磁盘性能都会改变结果。基准数据的价值在于同条件横向比较，而不是承诺每台机器都会得到同一个 TPS。</p></details>
      <details data-faq><summary>服务器没卡，是否应该继续关闭更多优化？</summary><p>不建议。性能优化不是越激进越好。成熟的调优方式是从默认配置开始，只在实际出现瓶颈时逐项修改，并记录每次修改前后的 MSPT、TPS 和玩家体验。</p></details>
      <details data-faq><summary>CPU 很强，但 TPS 还是低，怎么办？</summary><p>先确认是不是主线程在等待：检查 GC 停顿、锁竞争、插件同步 IO、区块生成与加载，再用 spark 找到真正的自耗时热点。CPU 总占用低并不意味着服务器没有瓶颈，单线程等待同样会让 TPS 掉下来。</p></details>

      <div class="faq-group-label"><span class="grad-flow">MULTITHREADING</span><span>多线程与 Folia</span></div>
      <details data-faq><summary>Dracore 和 Folia 有什么区别？</summary><p>Folia 的核心思路是把世界划分为多个区域并进行区域化 tick，是对传统单线程世界模型的更大改造；它并不是 Paper 的“直接替换版”，而且官方明确指出它并不适合大多数服务器。Dracore 更偏向逐项异步化，并提供可选的并行世界 tick，尽量保留传统 Paper 插件模型。</p></details>
      <details data-faq><summary>什么类型的服务器更适合 Folia？</summary><p>官方建议重点考虑玩家天然分散的服务器，例如大型 SMP、SkyBlock 等。Folia 的收益取决于玩家是否分散以及服务器是否有足够的 CPU 核心，并需要根据 Netty、区块系统、GC 和 tick 线程实际负载调参。</p></details>
      <details data-faq><summary>为什么普通 Paper 插件不能直接算作 Folia 插件？</summary><p>Folia 改变了线程与调度模型。插件如果假设所有世界操作都发生在同一个主线程，就可能出现线程安全问题。因此真正支持 Folia 不只是写一个兼容标记，还需要按 global / region / entity / async scheduler 模型重新处理任务调度。</p></details>
      <details data-faq><summary>Dracore 的多线程会不会让插件随机崩服？</summary><p>Dracore 的路线是把适合下放的计算逐项异步化，而不是把所有 Bukkit 世界操作粗暴搬到后台线程。涉及主线程语义的操作应保留同步边界，并在异常情况下回退。生产环境仍建议先用完整插件集压测。</p></details>

      <div class="faq-group-label"><span class="grad-flow">CONFIG</span><span>配置与故障排查</span></div>
      <details data-faq><summary>开关是不是全部打开就性能最好？</summary><p>不是。部分优化会改变游戏行为，部分只适合特定负载。推荐先保持保守默认值，再根据 spark 和实际玩家行为逐项启用。尤其是数据包、红石、村民交易大厅和大型农场服，应重点验证行为差异。</p></details>
      <details data-faq><summary>修改配置后没有效果怎么办？</summary><p>先确认该配置是否标记为“需重启”。支持热重载的项目可以使用 <code>/dracore reload</code>；线程数、DAB 等项目通常需要完整重启。修改后最好检查启动日志确认配置被正确解析。</p></details>
      <details data-faq><summary>如何提交 Bug 才最容易被定位？</summary><p>请提供：① 完整 crash-report 或错误日志；② 最小复现步骤；③ Dracore 配置；④ 插件列表与版本；⑤ 如果是性能问题，再附上 spark profiler 报告。不要只提交一句“服务器很卡”。</p></details>
      <details data-faq><summary>出现严重问题可以快速回退吗？</summary><p>可以。停服后恢复之前备份的核心 JAR 和配置即可。不要在没有备份的情况下直接覆盖生产服核心；升级与切换核心都应该保留明确的回滚点。</p></details>

      <div class="faq-group-label"><span class="grad-flow">COMMUNITY</span><span>生态与开发</span></div>
      <details data-faq><summary>Dracore 是否兼容 Purpur 的思路和配置？</summary><p>Dracore 建立在 Paper 生态上，具体是否采用某个上游分支的补丁，需要以当前版本源码与变更记录为准。不要把不同核心的配置文件整份互换；只迁移明确对应的配置项。</p></details>
      <details data-faq><summary>我应该用 Dracore、Leaf、Purpur 还是 Folia？</summary><p>如果你最看重成熟的 Paper 插件生态与传统线程模型，优先选择 Paper 系兼容核心；如果服务器天然适合区域化并行且插件生态允许，再考虑 Folia。Leaf、Purpur、Dracore 则应该结合你的实际玩法、插件和压测结果选择，而不是单纯比较首页宣传的“最快”。</p></details>
      <details data-faq><summary>哪里能看到优化到底改了什么？</summary><p>优先查看文档中的「配置详解」「优化原理」「行为差异」和「压测方法论」。性能核心最重要的不是列出一个巨大优化数量，而是让每一项改动都能解释、验证和回退。</p></details>
    </div>
  </div>
</div>

<!-- ================= 下载页 ================= -->
<div class="view" id="view-download">
  <div class="container">
    <div class="dl-hero">
      <h1><span class="grad-flow">获取 Dracore</span></h1>
      <p>选择目标 Minecraft 版本，查看构建信息与安装要求。</p>
    </div>

    <!-- ===== 新增构建：复制下面整个 <div class="build"> ... </div> 块，
             改 build-title 的版本号、build-meta 里的信息、changelog 条目，
             最重要的是把 build-actions 里 <a class="btn btn-primary" href="..."> 的 href 换成真实的 jar 直链
             （GitHub Releases 附件直链 / 镜像都行）。旧版本记得去掉 .latest 类并保留 build-tag 样式。 ===== -->
    <div class="build latest">
      <div class="build-head">
        <div class="build-title">Dracore 1.21.11 <span class="grad-flow">v1</span></div>
        <span class="build-tag">LATEST · 最新稳定版</span>
      </div>
      <div class="build-meta">
        <span><b>MC 版本：</b>1.21.11</span>
        <span><b>核心：</b>Paper 1.21.11</span>
        <span><b>格式：</b>paperclip jar</span>
        <span><b>Java：</b>21+</span>
        <span><b>SHA-256：</b>待发布后填入</span>
      </div>
      <ul class="list changelog">
        <li>初版构建：16 条起步补丁 + 21 条批次 A 热路径优化</li>
        <li>路径点 O(n²) 治理（可配置节流 / 禁用），主线程收益最大单项</li>
        <li>异步全家桶：区块发送、玩家数据、实体追踪、寻路、运动包过滤</li>
        <li>biome 三路缓存、装备数组化、目标选择器专用数据结构</li>
        <li>并行世界 tick（SparklyPaper 移植，默认关，多世界场景启用）</li>
      </ul>
      <div class="build-actions">
        <!-- ↓ 把 href="#" 换成真实下载直链即可 -->
        <span class="btn btn-primary btn-disabled" aria-disabled="true">构建待发布</span>
        <a class="btn btn-ghost" href="#/docs">安装与配置文档</a>
      </div>
    </div>
    <!-- ===== 构建块结束 ===== -->

    <div class="card" style="margin-top:28px;">
      <h3>安装步骤</h3>
      <ol class="list">
        <li>停服并完整备份服务器目录。</li>
        <li>下载的 jar 替换原核心 jar（文件名可自定，启动命令跟着改）。</li>
        <li>首次启动自动解包并生成 <code>config/dracore.yml</code>。</li>
        <li>按文档打开需要的性能开关，重启一次让"需重启"项生效。</li>
      </ol>
      <div class="warn">⚠ 强烈建议先在测试环境跑一天再上生产。任何核心更换都应以备份为前提。</div>
      <div class="tip">推荐配套 JVM 参数（Aikar G1 flags）见<a href="#/docs">文档 · JVM 参数</a>。</div>
    </div>
  </div>
</div>

<!-- ================= 文档页 ================= -->
<div class="view" id="view-docs">
  <div class="container">
    <div class="doc-head">
      <h1><span class="dragon" aria-hidden="true" style="width:1em;height:1em;vertical-align:-0.18em"></span>Dracore <span class="grad-flow">文档</span></h1>
      <p>从安装、配置到性能分析，逐步了解 Dracore。适用版本：1.21.11</p>
      <div class="doc-nav">
        <a href="#/docs">快速开始</a><a href="#/docs">JVM 参数</a><a href="#/docs">配置详解</a>
        <a href="#/docs">优化原理</a><a href="#/docs">行为差异</a><a href="#/docs">压测方法</a>
        <a href="#/docs">故障排查</a><a href="#/docs">源码构建</a>
      </div>
    </div>

    <aside class="docs-toc" aria-label="文档目录">
      <div class="toc-title">DOCUMENTATION</div>
      <a href="#d-start">快速开始</a>
      <a href="#d-jvm">JVM 参数</a>
      <a href="#d-config">配置详解</a>
      <a href="#d-principle">优化原理</a>
      <a href="#d-diff">行为差异</a>
      <a href="#d-bench">压测方法</a>
      <a href="#d-trouble">故障排查</a>
      <a href="#d-build">源码构建</a>
    </aside>

    <section id="d-start">
      <h2><span class="grad-flow">快速开始</span></h2>
      <div class="card">
        <h3>系统需求</h3>
        <ul class="list">
          <li>Java 21+（推荐 JDK 21 或 25；64 位 JVM）</li>
          <li>内存 4G 起，建议 6G+ 留给系统</li>
          <li>1.21.11 客户端（ViaVersion 等跨版本方案未逐一验证）</li>
        </ul>
      </div>
      <div class="card">
        <h3>安装（从 Paper / Leaf 迁移）</h3>
        <ol class="list">
          <li>停服，完整备份整个服务器目录（存档 + 插件 + 配置）。</li>
          <li>用 <code>dracore-1.21.11-v1.jar</code> 替换原核心 jar（paperclip 格式，首次启动自动解包）。</li>
          <li>启动服务器，首次启动自动生成 <code>config/dracore.yml</code>（全中文注释）。</li>
          <li>按需打开性能开关（默认保守），重启一次让"需重启"项生效。</li>
        </ol>
        <p>世界、插件、玩家数据全部原样保留，Paper 插件无需任何改动。</p>
      </div>
      <div class="card">
        <h3>配置文件结构</h3>
        <pre class="code">config/
├── dracore.yml              <span class="cm"># Dracore 全部开关（战斗/性能/趣味/中文）</span>
├── paper-world-defaults.yml <span class="cm"># Paper 世界配置（红石引擎 / 漏斗等）</span>
└── spigot.yml               <span class="cm"># 激活范围 / 合并半径 / 漏斗频率</span></pre>
        <p><code>/dracore reload</code> 可热重载大部分开关；标注「⚠ 需重启」的项（如线程数、DAB）需要重启生效。</p>
      </div>
    </section>

    <section id="d-jvm">
      <h2><span class="grad-flow">JVM 参数</span></h2>
      <p class="sec-sub">GC 不当的停顿会伪装成"TPS 低"。实测：裸 -Xmx4G → Aikar flags，仅 GC 调优即白捡 0.4 TPS，95 分位尖峰明显收敛。以下为压测同款参数：</p>
      <pre class="code">java <span class="val">-Xms4G -Xmx4G</span> \
  <span class="val">-XX:+UseG1GC</span> <span class="val">-XX:+ParallelRefProcEnabled</span> \
  <span class="val">-XX:MaxGCPauseMillis=200</span> <span class="val">-XX:+UnlockExperimentalVMOptions</span> \
  <span class="val">-XX:+DisableExplicitGC</span> <span class="val">-XX:+AlwaysPreTouch</span> \
  <span class="val">-XX:G1NewSizePercent=30</span> <span class="val">-XX:G1MaxNewSizePercent=40</span> \
  <span class="val">-XX:G1HeapRegionSize=8M</span> <span class="val">-XX:G1ReservePercent=20</span> \
  <span class="val">-XX:G1HeapWastePercent=5</span> <span class="val">-XX:G1MixedGCCountTarget=4</span> \
  <span class="val">-XX:InitiatingHeapOccupancyPercent=15</span> <span class="val">-XX:G1MixedGCLiveThresholdPercent=90</span> \
  <span class="val">-XX:G1RSetUpdatingPauseTimePercent=5</span> <span class="val">-XX:SurvivorRatio=32</span> \
  <span class="val">-XX:+PerfDisableSharedMem</span> <span class="val">-XX:MaxTenuringThreshold=1</span> \
  <span class="val">-Xlog:gc*:file=gc.log:time,uptime,level,tags:filecount=3,filesize=20M</span> \
  <span class="val">-jar</span> dracore-1.21.11-v1.jar --nogui</pre>
      <div class="tip">-Xms 与 -Xmx 设成相同值避免堆伸缩开销。8G 以上内存的机器堆给 6~8G 即可，<b>超大堆反而让 GC 停顿变长</b>。</div>
      <div class="tip">开启 <code>-Xlog:gc*</code> 后观察 gc.log：若单次停顿常态 &gt; 50ms（一个 tick 的预算），先解决 GC 再谈优化。</div>
    </section>

    <section id="d-config">
      <h2><span class="grad-flow">配置详解</span></h2>
      <h3>性能 · 异步家族</h3>
      <table>
        <tr><th>开关</th><th>作用</th><th>代价 / 影响</th><th>建议</th></tr>
        <tr><td><b>异步区块发送</b></td><td>区块数据包的序列化与发送移出主线程</td><td>几乎无副作用</td><td>开</td></tr>
        <tr><td><b>异步玩家数据保存</b></td><td>玩家存盘异步化</td><td>极小（掉电时最后几秒数据可能丢失）</td><td>开</td></tr>
        <tr><td><b>异步实体追踪</b></td><td>"谁能看见谁"的追踪计算多线程化</td><td>实体越多收益越大</td><td>开，线程数 0=自动</td></tr>
        <tr><td><b>异步寻路</b></td><td>寻路计算移入线程池</td><td>队列满时 FLUSH_ALL 回退主线程，保证正确</td><td>开，线程数 0=自动</td></tr>
        <tr><td><b>过滤实体运动包</b></td><td>无位移的实体不广播移动包</td><td>无感知，带宽大降</td><td>开</td></tr>
      </table>
      <h3>性能 · 缓存与治理</h3>
      <table>
        <tr><th>开关</th><th>作用</th><th>代价 / 影响</th><th>建议</th></tr>
        <tr><td><b>路径点更新节流</b></td><td>每 N tick 更新一次定位栏连接；0=禁用，1=原生</td><td>图标更新变慢（视觉无感），0 时冻结</td><td>重压服 0，常规 4</td></tr>
        <tr><td><b>缓存biome.启用/刷怪路径/成就路径</b></td><td>biome 查询结果哈希缓存（65536 桶）</td><td>失效边界已处理，结果一致</td><td>全开</td></tr>
        <tr><td><b>execute跳过不活跃实体</b></td><td>/execute 选择器跳过被节流的实体</td><td>重度数据包语义变化</td><td>数据包服按需</td></tr>
        <tr><td><b>缓存方块状态标签</b></td><td>方块状态标签固化为位掩码</td><td>无</td><td>开（默认开）</td></tr>
        <tr><td><b>阻止进入弱加载区块(.启用/.弹射物)</b></td><td>实体移动不进入弱加载区块</td><td>极端情况下实体行为边界变化</td><td>实测再定，默认关</td></tr>
        <tr><td><b>复用随机刻BlockPos</b></td><td>随机刻传递可变坐标省分配</td><td>⚠ 方块若存储传入坐标会出错</td><td>实验性，默认关</td></tr>
      </table>
      <h3>性能 · DAB（动态大脑激活）</h3>
      <table>
        <tr><th>开关</th><th>作用</th><th>代价 / 影响</th></tr>
        <tr><td><b>DAB.启用</b></td><td>距离玩家越远的生物 AI 越稀疏（起始 12 格，最远每 20 tick 一次）</td><td>远处生物反应慢；【需重启】</td></tr>
        <tr><td><b>起始距离 / 最大tick频率</b></td><td>调节分级曲线</td><td>默认即可</td></tr>
      </table>
      <div class="tip">DAB 就是"村民按距离分级变慢"的正解：配合 spigot.yml 的 <code>entity-activation-range.villagers: 16</code> 与 <code>tick-inactive-villagers: false</code>，形成"分级变慢 + 硬截止"双层体系。</div>
      <h3>战斗</h3>
      <table>
        <tr><th>开关</th><th>作用</th><th>说明</th></tr>
        <tr><td><b>启用1点8式击退</b></td><td>1.8 经典击退手感</td><td>PvP 服最爱；默认关</td></tr>
        <tr><td><b>剑格挡</b></td><td>1.8 剑格挡</td><td>同上</td></tr>
        <tr><td><b>钓鱼竿击退</b></td><td>钓竿拉扯敌方</td><td>怀旧 PvP</td></tr>
        <tr><td><b>1点8盔甲减伤 / 关闭减伤上限</b></td><td>旧版减伤公式</td><td>按服定位</td></tr>
      </table>
      <h3>配套参数（spigot.yml / paper-world-defaults.yml）</h3>
      <table>
        <tr><th>参数</th><th>推荐值</th><th>说明</th></tr>
        <tr><td>entity-activation-range</td><td>animals 16 / monsters 24 / villagers 16 / misc 8</td><td>激活范围外 AI 冻结</td></tr>
        <tr><td>tick-inactive-villagers</td><td>false</td><td>范围外村民彻底不 tick</td></tr>
        <tr><td>merge-radius</td><td>item 3.5 / exp 4.0</td><td>掉落物合并；老式过滤器需改设计</td></tr>
        <tr><td>ticks-per.hopper-check</td><td>8</td><td>漏斗 8 tick 一查；漏斗钟会变调</td></tr>
        <tr><td>hopper.disable-move-event</td><td>true</td><td>砍掉漏斗 Bukkit 事件</td></tr>
        <tr><td>redstone-implementation</td><td>ALTERNATE_CURRENT</td><td>红石引擎整体换血，快数倍</td></tr>
        <tr><td>simulation-distance</td><td>6</td><td>模拟区块少 60%+，单项最大杠杆</td></tr>
      </table>
    </section>

    <section id="d-principle">
      <h2><span class="grad-flow">优化原理</span></h2>
      <div class="card"><h3>定位栏 O(n²) 治理</h3>
        <p>1.21.6+ 的路径点系统为每对（玩家 × 发射器）维护连接，150 名玩家即 22500 对，每 tick 全量遍历。实测占主线程自耗时 ~8%。方案：updatePlayer / updateWaypoint 引入 tick 节流（0/1/N 三档）。Folia 系的区域化线程模型则可以进一步降低这类系统的全局开销；Dracore 选择保留传统插件模型，并通过节流与局部优化降低成本。</p></div>
      <div class="card"><h3>biome 三路缓存</h3>
        <p>getBiome 走噪声采样，是刷怪与成就判定的热路径。建立 65536 桶哈希缓存（键 = 区块坐标打包 long）；刷怪路径额外传入所在区块做快速路径。</p></div>
      <div class="card"><h3>目标选择器优化</h3>
        <p>换成专用二叉目标集合 + 数组化 BehaviorControl 集合 + Activity 位集，把 AI 目标管理的常数项压到最低。</p></div>
      <div class="card"><h3>装备数组化 + 碰撞缓存</h3>
        <p>EntityEquipment 从 EnumMap 换为定长数组（槽位即下标）；实体碰撞候选列表复用三组 fastutil 数组，省掉每次移动的临时分配。</p></div>
      <div class="card"><h3>异步家族（逐项异步化）</h3>
        <p>原则：主线程语义不变，只把可安全下放的计算移出主线程。每条异步路径都有边界加固与回退策略，出问题自动退化为同步行为。</p></div>
      <div class="card"><h3>并行世界 tick（SparklyPaper 移植，默认关）</h3>
        <p>多世界场景下各世界主 tick 在独立线程并行执行。配套 STRICT / BUFFERED / DISABLED 三档异步读策略。单世界无收益，多世界近线性收益。</p></div>
    </section>

    <section id="d-diff">
      <h2><span class="grad-flow">行为差异（诚实清单）</span></h2>
      <table>
        <tr><th>差异</th><th>触发条件</th><th>玩家感知</th><th>如何关回</th></tr>
        <tr><td>定位栏图标更新变慢/冻结</td><td>路径点节流 ≠ 1</td><td>图标延迟或停在初始位置</td><td>= 1</td></tr>
        <tr><td>远处生物 AI 稀疏</td><td>DAB 启用</td><td>离玩家远的怪反应慢</td><td>DAB.启用 = false【需重启】</td></tr>
        <tr><td>屏幕外生物 AI 冻结</td><td>激活范围收紧</td><td>范围外农场停摆</td><td>调回 32+</td></tr>
        <tr><td>远处村民停止补货</td><td>tick-inactive-villagers = false</td><td>远的交易大厅不刷新</td><td>改回 true</td></tr>
        <tr><td>漏斗变慢</td><td>hopper-check = 8</td><td>漏斗钟/出货变慢</td><td>改回 1</td></tr>
        <tr><td>红石时序边缘差异</td><td>ALTERNATE_CURRENT</td><td>极少数 0tick/BUD 机器不同</td><td>= VANILLA</td></tr>
        <tr><td>/execute 目标集变化</td><td>execute跳过不活跃实体 = true</td><td>数据包选择器结果不同</td><td>改回 false</td></tr>
        <tr><td>1.8 战斗手感</td><td>战斗开关启用</td><td>击退/格挡/减伤公式变化</td><td>战斗区 = false（默认）</td></tr>
      </table>
    </section>

    <section id="d-bench">
      <h2><span class="grad-flow">压测方法论</span></h2>
      <div class="card">
        <ol class="list">
          <li>同一份测试世界（模拟距离 10，无插件）。</li>
          <li>开服后先 <code>kill @e[type=!player]</code> 清残留实体，保证每轮起点一致。</li>
          <li>150 个假人随机分布在半径 1000 范围内漫游。</li>
          <li>60 秒预热，随后正式计时 5 分钟，每 30 秒采样 TPS(1m) 与 MSPT(avg)。</li>
          <li>对照组使用完全相同的世界、假人与 JVM 参数。</li>
        </ol>
      </div>
      <div class="warn">⚠ 世界状态污染是压测最大陷阱：残留实体、已生成区块会让每轮都比上一轮慢（实测过 7.3 → 5.2 的"假衰减"）。每轮清理实体，否则数据不可信。</div>
      <div class="tip">剖析用 spark：<code>/spark profiler start --timeout 60</code>。优先看「自耗时」而非「总耗时」；警惕 CPU 占用率低但 TPS 也低——那是主线程在等（GC / 锁 / IO）。</div>
    </section>

    <section id="d-trouble">
      <h2><span class="grad-flow">故障排查</span></h2>
      <details data-faq><summary>TPS 低，但 CPU 占用率也很低？</summary><p>主线程在"等"。按序排查：① gc.log 单次停顿是否常态 &gt; 50ms ② 是否有插件每 tick 做磁盘 IO ③ spark 报告是否有锁等待大头。</p></details>
      <details data-faq><summary>开服报 dracore.yml 值不是 true/false？</summary><p>配置键为父子结构（如 缓存biome 与 缓存biome.启用），不要把父键写成布尔又加子键。删掉对应段重启即自动重建。</p></details>
      <details data-faq><summary>改了开关没生效？</summary><p>查注释是否标注「⚠ 需重启」（线程数、DAB 等）；其余 /dracore reload 即可。</p></details>
      <details data-faq><summary>实体追踪/寻路线程数怎么定？</summary><p>0 = 自动（追踪：核心数一半；寻路：核心数/4）。除非明确知道自己在做什么，否则保持 0。</p></details>
      <details data-faq><summary>玩家反馈定位栏不动？</summary><p>路径点更新节流为 0（禁用档）。改成 4 可恢复每秒 5 次更新，性能损失很小。</p></details>
      <details data-faq><summary>并行世界 tick 开了没效果？</summary><p>单世界无收益（只有一个可并行单元）。多世界且各有玩家时才兑现收益。</p></details>
      <details data-faq><summary>崩了怎么办？</summary><p>收集三件套：crash-report 全文、复现步骤、dracore.yml。疑似某开关导致就先关回默认验证。</p></details>
    </section>

    <section id="d-build">
      <h2><span class="grad-flow">源码构建</span></h2>
      <div class="card">
        <h3>环境</h3>
        <ul class="list">
          <li>JDK 21（工具链锁死本地路径时可跳过自动下载）</li>
          <li>Git（报 "git exit value 1" 先 <code>gradlew --stop</code> 清守护进程）</li>
        </ul>
        <h3>常用命令</h3>
        <pre class="code">./gradlew applyPatches                    <span class="cm"># 应用全部补丁</span>
./gradlew rebuildPatches                  <span class="cm"># 把修改固化回补丁文件</span>
./gradlew paper-server:compileJava --offline <span class="cm"># 快速编译验证</span>
./gradlew paper-server:createMojmapPaperclipJar --offline <span class="cm"># 出 paperclip jar</span></pre>
        <div class="tip">修改工作目录后：先删 .orig/.rej → 提交内部仓库 → rebuildPatches → 提交主仓库 → createMojmapPaperclipJar。</div>
      </div>
    </section>
  </div>
</div>

<footer>
  <p><span class="dragon" aria-hidden="true" style="width:1em;height:1em;vertical-align:-0.18em;margin-right:5px"></span><span class="grad-flow">Dracore</span> · 面向 Paper 生态的性能优化核心。</p>
</footer>

<script>
  // ===== 视图路由 =====
  var VIEWS = ['home', 'docs', 'download', 'faq'];
  function go(name) { location.hash = '#/' + name; }
  function applyRoute() {
    var h = (location.hash || '#/home').replace('#/', '');
    if (VIEWS.indexOf(h) === -1) h = 'home';
    VIEWS.forEach(function (v) {
      document.getElementById('view-' + v).classList.toggle('active', v === h);
    });
    document.querySelectorAll('.nav-links a').forEach(function (a) {
      a.classList.toggle('active', a.getAttribute('data-nav') === h);
    });
    window.scrollTo(0, 0);
  }
  window.addEventListener('hashchange', applyRoute);
  applyRoute();

  // ===== 亮/暗主题 =====
  var root = document.documentElement;
  var btn = document.getElementById('themeBtn');
  function paintBtn(t) { btn.textContent = t === 'dark' ? '☀ 亮色' : '☾ 暗色'; }
  (function initTheme() {
    var saved = localStorage.getItem('dracore-theme');
    if (saved) { root.setAttribute('data-theme', saved); }
    paintBtn(root.getAttribute('data-theme'));
  })();
  function toggleTheme() {
    var next = root.getAttribute('data-theme') === 'dark' ? 'light' : 'dark';
    root.setAttribute('data-theme', next);
    localStorage.setItem('dracore-theme', next);
    paintBtn(next);
  }

  // ===== FAQ 即时搜索 =====
  (function initFaqSearch(){
    var input = document.getElementById('faqSearch');
    var count = document.getElementById('faqCount');
    if (!input) return;
    var items = Array.prototype.slice.call(document.querySelectorAll('[data-faq]'));
    function update(){
      var q = input.value.trim().toLowerCase();
      var visible = 0;
      items.forEach(function(item){
        var text = item.textContent.toLowerCase();
        var hit = !q || text.indexOf(q) !== -1;
        item.classList.toggle('faq-hidden', !hit);
        if(hit) visible++;
      });
      count.textContent = q ? ('找到 ' + visible + ' 个问题') : '全部问题';
    }
    input.addEventListener('input', update);
    input.addEventListener('keydown', function(e){
      if(e.key === 'Escape'){ input.value=''; update(); input.blur(); }
    });
  })();

  // ===== 文档目录高亮 =====
  (function initDocToc(){
    var links = Array.prototype.slice.call(document.querySelectorAll('.docs-toc a'));
    var sections = links.map(function(a){
      return document.querySelector(a.getAttribute('href'));
    }).filter(Boolean);
    if(!sections.length) return;
    function sync(){
      var best = sections[0];
      sections.forEach(function(s){
        if(s.getBoundingClientRect().top <= 140) best = s;
      });
      links.forEach(function(a){
        a.classList.toggle('toc-active', a.getAttribute('href') === '#' + best.id);
      });
    }
    window.addEventListener('scroll', sync, {passive:true});
    sync();
  })();
</script>

</body>
</html>
