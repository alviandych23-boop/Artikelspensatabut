<!doctype html>
<html lang="id" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Jurnal &amp; Artikel - SMP Negeri 1 Tabukan Utara</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&amp;family=Plus+Jakarta+Sans:wght@300;400;500;600;700&amp;display=swap" rel="stylesheet">
  <style>
    :root {
      --primary-bg: #0f172a;
      --secondary-surface: #1e293b;
      --text-color: #f1f5f9;
      --primary-action: #3b82f6;
      --secondary-action: #60a5fa;
    }
    
    html, body {
      height: 100%;
      margin: 0;
      padding: 0;
    }
    
    body {
      font-family: 'Plus Jakarta Sans', sans-serif;
      background: var(--primary-bg);
      color: var(--text-color);
    }
    
    .font-display {
      font-family: 'Playfair Display', serif;
    }
    
    .main-wrapper {
      width: 100%;
      height: 100%;
      overflow-y: auto;
      overflow-x: hidden;
      background: var(--primary-bg);
    }
    
    /* Animated Background */
    .animated-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      overflow: hidden;
      z-index: 0;
    }
    
    /* Floating Elements - School Items */
    .floating-item {
      position: absolute;
      opacity: 0.15;
      animation: float 20s ease-in-out infinite;
    }
    
    @keyframes float {
      0%, 100% { transform: translateY(0) rotate(0deg); }
      25% { transform: translateY(-30px) rotate(5deg); }
      50% { transform: translateY(-15px) rotate(-3deg); }
      75% { transform: translateY(-40px) rotate(3deg); }
    }
    
    /* Flying Paper Animation */
    .paper {
      position: absolute;
      width: 30px;
      height: 40px;
      background: linear-gradient(135deg, #ffffff 0%, #e2e8f0 100%);
      border-radius: 2px;
      animation: flyPaper 25s linear infinite;
      opacity: 0.2;
    }
    
    @keyframes flyPaper {
      0% { transform: translateX(-100px) translateY(100%) rotate(0deg); opacity: 0; }
      10% { opacity: 0.2; }
      90% { opacity: 0.2; }
      100% { transform: translateX(calc(100vw + 100px)) translateY(-100%) rotate(720deg); opacity: 0; }
    }
    
    /* Pencil Animation */
    .pencil {
      position: absolute;
      animation: writePencil 15s ease-in-out infinite;
      opacity: 0.12;
    }
    
    @keyframes writePencil {
      0%, 100% { transform: translateX(0) rotate(-45deg); }
      50% { transform: translateX(50px) rotate(-30deg); }
    }
    
    /* Book Animation */
    .book {
      animation: bookFloat 18s ease-in-out infinite;
    }
    
    @keyframes bookFloat {
      0%, 100% { transform: translateY(0) rotateY(0deg); }
      50% { transform: translateY(-20px) rotateY(15deg); }
    }
    
    /* Student Silhouette Animation */
    .student {
      position: absolute;
      bottom: 0;
      animation: studentWalk 30s linear infinite;
      opacity: 0.08;
    }
    
    @keyframes studentWalk {
      0% { transform: translateX(-200px); }
      100% { transform: translateX(calc(100vw + 200px)); }
    }
    
    /* Gradient Orbs */
    .gradient-orb {
      position: absolute;
      border-radius: 50%;
      filter: blur(80px);
      animation: orbPulse 8s ease-in-out infinite;
    }
    
    @keyframes orbPulse {
      0%, 100% { transform: scale(1); opacity: 0.3; }
      50% { transform: scale(1.2); opacity: 0.5; }
    }
    
    /* Hero Section */
    .hero-section {
      position: relative;
      min-height: 500px;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      padding: 80px 20px;
    }
    
    /* Card Hover Effects */
    .article-card {
      background: var(--secondary-surface);
      border-radius: 16px;
      overflow: hidden;
      transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
      border: 1px solid rgba(255,255,255,0.05);
    }
    
    .article-card:hover {
      transform: translateY(-8px);
      box-shadow: 0 25px 50px -12px rgba(59, 130, 246, 0.25);
      border-color: rgba(59, 130, 246, 0.3);
    }
    
    /* Navigation */
    .nav-link {
      position: relative;
      padding: 8px 16px;
      transition: color 0.3s ease;
    }
    
    .nav-link::after {
      content: '';
      position: absolute;
      bottom: 0;
      left: 50%;
      width: 0;
      height: 2px;
      background: var(--primary-action);
      transition: all 0.3s ease;
      transform: translateX(-50%);
    }
    
    .nav-link:hover::after {
      width: 80%;
    }
    
    /* Badge Animation */
    .badge {
      display: inline-block;
      padding: 4px 12px;
      border-radius: 20px;
      font-size: 12px;
      font-weight: 600;
      animation: badgePop 0.5s ease-out;
    }
    
    @keyframes badgePop {
      0% { transform: scale(0); }
      50% { transform: scale(1.1); }
      100% { transform: scale(1); }
    }
    
    /* Scroll Reveal */
    .reveal {
      opacity: 0;
      transform: translateY(30px);
      transition: all 0.8s cubic-bezier(0.4, 0, 0.2, 1);
    }
    
    .reveal.active {
      opacity: 1;
      transform: translateY(0);
    }
    
    /* Button Styles */
    .btn-primary {
      background: var(--primary-action);
      color: white;
      padding: 12px 28px;
      border-radius: 30px;
      font-weight: 600;
      transition: all 0.3s ease;
      display: inline-flex;
      align-items: center;
      gap: 8px;
    }
    
    .btn-primary:hover {
      background: var(--secondary-action);
      transform: translateY(-2px);
      box-shadow: 0 10px 30px -10px rgba(59, 130, 246, 0.5);
    }
    
    /* Stats Counter Animation */
    .stat-number {
      font-size: 3rem;
      font-weight: 700;
      background: linear-gradient(135deg, var(--primary-action), var(--secondary-action));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
    
    /* Marquee Animation */
    .marquee {
      animation: marquee 30s linear infinite;
    }
    
    @keyframes marquee {
      0% { transform: translateX(0); }
      100% { transform: translateX(-50%); }
    }
    
    /* Wave Animation */
    .wave {
      animation: wave 2s ease-in-out infinite;
    }
    
    @keyframes wave {
      0%, 100% { transform: rotate(0deg); }
      25% { transform: rotate(20deg); }
      75% { transform: rotate(-15deg); }
    }
    
    /* Typing Animation */
    .typing-cursor {
      animation: blink 1s step-end infinite;
    }
    
    @keyframes blink {
      0%, 100% { opacity: 1; }
      50% { opacity: 0; }
    }

    /* Section divider */
    .section-divider {
      height: 1px;
      background: linear-gradient(90deg, transparent, rgba(59, 130, 246, 0.3), transparent);
    }

    /* Admin Panel Styles */
    .admin-tab-btn {
      background: transparent;
      color: #94a3b8;
      border: none;
      cursor: pointer;
    }

    .admin-tab-btn.active {
      background: #3b82f6;
      color: white;
    }

    .admin-item {
      background: #1e293b;
      border: 1px solid #475569;
      border-radius: 8px;
      padding: 12px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .admin-item-text {
      flex: 1;
    }

    .admin-item-title {
      font-weight: 600;
      color: #f1f5f9;
      margin-bottom: 4px;
    }

    .admin-item-desc {
      font-size: 12px;
      color: #94a3b8;
    }

    .admin-item-actions {
      display: flex;
      gap: 8px;
    }

    .admin-btn-small {
      padding: 6px 12px;
      border-radius: 6px;
      border: none;
      color: white;
      font-size: 12px;
      cursor: pointer;
      transition: all 0.2s;
    }

    .admin-btn-edit {
      background: #3b82f6;
    }

    .admin-btn-edit:hover {
      background: #2563eb;
    }

    .admin-btn-delete {
      background: #ef4444;
    }

    .admin-btn-delete:hover {
      background: #dc2626;
    }

    .form-group {
      margin-bottom: 16px;
    }

    .form-group label {
      display: block;
      font-size: 14px;
      font-weight: 500;
      color: #cbd5e1;
      margin-bottom: 8px;
    }

    .form-group input,
    .form-group textarea,
    .form-group select {
      width: 100%;
      padding: 10px 12px;
      border-radius: 6px;
      background: #0f172a;
      border: 1px solid #475569;
      color: #f1f5f9;
      font-size: 14px;
      font-family: inherit;
    }

    .form-group input:focus,
    .form-group textarea:focus,
    .form-group select:focus {
      outline: none;
      border-color: #3b82f6;
      box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.1);
    }

    .form-group textarea {
      resize: vertical;
      min-height: 80px;
    }

    .form-actions {
      display: flex;
      gap: 12px;
    }

    .form-actions button {
      flex: 1;
      padding: 10px;
      border-radius: 6px;
      border: none;
      cursor: pointer;
      font-weight: 500;
      transition: all 0.2s;
    }

    .form-submit {
      background: #10b981;
      color: white;
    }

    .form-submit:hover {
      background: #059669;
    }

    .form-cancel {
      background: #6b7280;
      color: white;
    }

    .form-cancel:hover {
      background: #4b5563;
    }

    .error-message {
      background: #fee2e2;
      border: 1px solid #fecaca;
      color: #991b1b;
      padding: 12px;
      border-radius: 6px;
      font-size: 14px;
      margin-bottom: 16px;
    }

    .success-message {
      background: #dcfce7;
      border: 1px solid #bbf7d0;
      color: #166534;
      padding: 12px;
      border-radius: 6px;
      font-size: 14px;
      margin-bottom: 16px;
    }
  </style>
  <style>body { box-sizing: border-box; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
 </head>
 <body class="h-full">
  <div class="main-wrapper">
   <!-- Animated Background -->
   <div class="animated-bg">
    <!-- Gradient Orbs -->
    <div class="gradient-orb" style="width: 400px; height: 400px; background: #3b82f6; top: 10%; left: 10%;"></div>
    <div class="gradient-orb" style="width: 300px; height: 300px; background: #8b5cf6; top: 50%; right: 10%; animation-delay: -3s;"></div>
    <div class="gradient-orb" style="width: 350px; height: 350px; background: #06b6d4; bottom: 10%; left: 30%; animation-delay: -5s;"></div><!-- Floating School Items -->
    <svg class="floating-item pencil" style="top: 15%; left: 5%; width: 60px;" viewbox="0 0 24 24" fill="currentColor">
     <path d="M20.71 7.04c.39-.39.39-1.04 0-1.41l-2.34-2.34c-.37-.39-1.02-.39-1.41 0l-1.84 1.83 3.75 3.75M3 17.25V21h3.75L17.81 9.93l-3.75-3.75L3 17.25z" />
    </svg>
    <svg class="floating-item book" style="top: 25%; right: 8%; width: 70px; animation-delay: -2s;" viewbox="0 0 24 24" fill="currentColor">
     <path d="M18 2H6c-1.1 0-2 .9-2 2v16c0 1.1.9 2 2 2h12c1.1 0 2-.9 2-2V4c0-1.1-.9-2-2-2zM6 4h5v8l-2.5-1.5L6 12V4z" />
    </svg>
    <svg class="floating-item" style="top: 60%; left: 3%; width: 50px; animation-delay: -4s;" viewbox="0 0 24 24" fill="currentColor">
     <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm-5 14H7v-2h7v2zm3-4H7v-2h10v2zm0-4H7V7h10v2z" />
    </svg>
    <svg class="floating-item" style="bottom: 20%; right: 5%; width: 55px; animation-delay: -6s;" viewbox="0 0 24 24" fill="currentColor">
     <path d="M5 13.18v4L12 21l7-3.82v-4L12 17l-7-3.82zM12 3L1 9l11 6 9-4.91V17h2V9L12 3z" />
    </svg><!-- Flying Papers -->
    <div class="paper" style="top: 20%; animation-delay: 0s;"></div>
    <div class="paper" style="top: 40%; animation-delay: -5s;"></div>
    <div class="paper" style="top: 60%; animation-delay: -10s;"></div>
    <div class="paper" style="top: 80%; animation-delay: -15s;"></div><!-- Walking Students Silhouettes -->
    <svg class="student" style="height: 120px; animation-delay: 0s;" viewbox="0 0 24 24" fill="currentColor">
     <path d="M12 2C13.1 2 14 2.9 14 4S13.1 6 12 6 10 5.1 10 4 10.9 2 12 2zM21 9h-6v13h-2v-6h-2v6H9V9H3V7h18v2z" />
    </svg>
    <svg class="student" style="height: 100px; animation-delay: -10s;" viewbox="0 0 24 24" fill="currentColor">
     <path d="M12 2C13.1 2 14 2.9 14 4S13.1 6 12 6 10 5.1 10 4 10.9 2 12 2zM21 9h-6v13h-2v-6h-2v6H9V9H3V7h18v2z" />
    </svg>
    <svg class="student" style="height: 110px; animation-delay: -20s;" viewbox="0 0 24 24" fill="currentColor">
     <path d="M12 2C13.1 2 14 2.9 14 4S13.1 6 12 6 10 5.1 10 4 10.9 2 12 2zM21 9h-6v13h-2v-6h-2v6H9V9H3V7h18v2z" />
    </svg>
   </div><!-- Navigation -->
   <nav class="fixed top-0 left-0 right-0 z-50 bg-opacity-90 backdrop-blur-lg" style="background: rgba(15, 23, 42, 0.9);">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
     <div class="flex items-center justify-between h-16">
      <div class="flex items-center gap-3">
       <div class="w-10 h-10 rounded-full bg-gradient-to-br from-blue-500 to-cyan-400 flex items-center justify-center">
        <svg class="w-6 h-6 text-white" viewbox="0 0 24 24" fill="currentColor">
         <path d="M5 13.18v4L12 21l7-3.82v-4L12 17l-7-3.82zM12 3L1 9l11 6 9-4.91V17h2V9L12 3z" />
        </svg>
       </div><span id="nav-school-name" class="font-display font-bold text-lg">SMPN 1 Tabukan Utara</span>
      </div>
      <div class="hidden md:flex items-center gap-2">
       <a href="#beranda" class="nav-link text-sm font-medium hover:text-blue-400">Beranda</a> <a href="#artikel" class="nav-link text-sm font-medium hover:text-blue-400">Artikel</a> <a href="#jurnal" class="nav-link text-sm font-medium hover:text-blue-400">Jurnal</a> <a href="#galeri" class="nav-link text-sm font-medium hover:text-blue-400">Galeri</a> <a href="#tentang" class="nav-link text-sm font-medium hover:text-blue-400">Tentang</a>
      </div><button class="md:hidden p-2" onclick="toggleMobileMenu()">
       <svg class="w-6 h-6" fill="none" stroke="currentColor" viewbox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
       </svg></button>
     </div>
    </div><!-- Mobile Menu -->
    <div id="mobile-menu" class="hidden md:hidden bg-slate-800 border-t border-slate-700">
     <div class="px-4 py-3 space-y-2">
      <a href="#beranda" class="block py-2 text-sm hover:text-blue-400">Beranda</a> <a href="#artikel" class="block py-2 text-sm hover:text-blue-400">Artikel</a> <a href="#jurnal" class="block py-2 text-sm hover:text-blue-400">Jurnal</a> <a href="#galeri" class="block py-2 text-sm hover:text-blue-400">Galeri</a> <a href="#tentang" class="block py-2 text-sm hover:text-blue-400">Tentang</a>
     </div>
    </div>
   </nav><!-- Hero Section -->
   <section id="beranda" class="hero-section relative z-10 pt-20">
    <div class="max-w-4xl mx-auto">
     <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-blue-500/20 border border-blue-500/30 mb-6">
      <span class="wave">👋</span> <span class="text-sm font-medium text-blue-300">Selamat Datang di Portal Kami</span>
     </div>
     <h1 id="hero-title" class="font-display text-4xl md:text-6xl font-bold mb-6 leading-tight"><span class="bg-gradient-to-r from-white via-blue-100 to-cyan-200 bg-clip-text text-transparent"> Jurnal &amp; Artikel Ilmiah </span> <br><span class="text-2xl md:text-4xl text-slate-300">SMP Negeri 1 Tabukan Utara</span></h1>
     <p id="hero-subtitle" class="text-lg md:text-xl text-slate-400 max-w-2xl mx-auto mb-8">Wadah kreativitas dan karya ilmiah siswa-siswi terbaik. Temukan artikel menarik, jurnal penelitian, dan berbagai karya tulis berkualitas.</p>
     <div class="flex flex-col sm:flex-row gap-4 justify-center">
      <a href="#artikel" class="btn-primary">
       <svg class="w-5 h-5" fill="none" stroke="currentColor" viewbox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.747 0 3.332.477 4.5 1.253v13C19.832 18.477 18.247 18 16.5 18c-1.746 0-3.332.477-4.5 1.253" />
       </svg> Jelajahi Artikel </a> <a href="#jurnal" class="px-6 py-3 rounded-full border border-slate-600 font-semibold hover:border-blue-500 hover:bg-blue-500/10 transition-all"> Lihat Jurnal </a>
     </div><!-- Stats -->
     <div class="grid grid-cols-3 gap-6 mt-16 pt-8 border-t border-slate-700/50">
      <div class="text-center">
       <div class="stat-number" id="stat-articles">
        50+
       </div>
       <div class="text-sm text-slate-400">
        Artikel
       </div>
      </div>
      <div class="text-center">
       <div class="stat-number" id="stat-journals">
        25+
       </div>
       <div class="text-sm text-slate-400">
        Jurnal
       </div>
      </div>
      <div class="text-center">
       <div class="stat-number" id="stat-authors">
        100+
       </div>
       <div class="text-sm text-slate-400">
        Penulis
       </div>
      </div>
     </div>
    </div>
   </section><!-- Marquee Section -->
   <div class="relative z-10 py-8 bg-gradient-to-r from-blue-600/20 via-purple-600/20 to-blue-600/20 overflow-hidden mt-12">
    <div class="flex whitespace-nowrap marquee">
     <span class="mx-8 text-lg font-medium text-slate-300">📚 Pendidikan Berkualitas</span> <span class="mx-8 text-lg font-medium text-slate-300">✨ Kreativitas Tanpa Batas</span> <span class="mx-8 text-lg font-medium text-slate-300">🎓 Generasi Cerdas</span> <span class="mx-8 text-lg font-medium text-slate-300">🌟 Prestasi Gemilang</span> <span class="mx-8 text-lg font-medium text-slate-300">💡 Inovasi Siswa</span> <span class="mx-8 text-lg font-medium text-slate-300">📚 Pendidikan Berkualitas</span> <span class="mx-8 text-lg font-medium text-slate-300">✨ Kreativitas Tanpa Batas</span> <span class="mx-8 text-lg font-medium text-slate-300">🎓 Generasi Cerdas</span> <span class="mx-8 text-lg font-medium text-slate-300">🌟 Prestasi Gemilang</span> <span class="mx-8 text-lg font-medium text-slate-300">💡 Inovasi Siswa</span>
    </div>
   </div><!-- Articles Section -->
   <section id="artikel" class="relative z-10 py-20 px-4">
    <div class="max-w-6xl mx-auto">
     <div class="text-center mb-12 reveal">
      <span class="badge bg-blue-500/20 text-blue-300 border border-blue-500/30">Artikel Terbaru</span>
      <h2 class="font-display text-3xl md:text-4xl font-bold mt-4 mb-4">Karya Tulis Siswa</h2>
      <p class="text-slate-400 max-w-xl mx-auto">Kumpulan artikel menarik dari siswa-siswi berbakat SMPN 1 Tabukan Utara</p>
     </div>
     <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
      <!-- Article Card 1 -->
      <article class="article-card reveal" style="animation-delay: 0.1s;">
       <div class="h-48 bg-gradient-to-br from-blue-600 to-cyan-500 flex items-center justify-center">
        <svg class="w-16 h-16 text-white/80" viewbox="0 0 24 24" fill="currentColor">
         <path d="M12 3L1 9l4 2.18v6L12 21l7-3.82v-6l2-1.09V17h2V9L12 3zm6.82 6L12 12.72 5.18 9 12 5.28 18.82 9zM17 15.99l-5 2.73-5-2.73v-3.72L12 15l5-2.73v3.72z" />
        </svg>
       </div>
       <div class="p-6">
        <div class="flex items-center gap-2 mb-3">
         <span class="badge bg-green-500/20 text-green-300">Pendidikan</span> <span class="text-xs text-slate-500">5 min baca</span>
        </div>
        <h3 class="font-display text-xl font-semibold mb-2 hover:text-blue-400 transition-colors cursor-pointer">Pentingnya Literasi Digital untuk Pelajar SMP</h3>
        <p class="text-slate-400 text-sm mb-4 line-clamp-2">Memahami bagaimana teknologi dapat membantu proses pembelajaran di era modern...</p>
        <div class="flex items-center justify-between">
         <div class="flex items-center gap-2">
          <div class="w-8 h-8 rounded-full bg-gradient-to-br from-pink-500 to-rose-500"></div><span class="text-sm text-slate-300">Sinta Dewi</span>
         </div><span class="text-xs text-slate-500">12 Des 2024</span>
        </div>
       </div>
      </article><!-- Article Card 2 -->
      <article class="article-card reveal" style="animation-delay: 0.2s;">
       <div class="h-48 bg-gradient-to-br from-purple-600 to-pink-500 flex items-center justify-center">
        <svg class="w-16 h-16 text-white/80" viewbox="0 0 24 24" fill="currentColor">
         <path d="M14.4 6L14 4H5v17h2v-7h5.6l.4 2h7V6z" />
        </svg>
       </div>
       <div class="p-6">
        <div class="flex items-center gap-2 mb-3">
         <span class="badge bg-purple-500/20 text-purple-300">Sejarah</span> <span class="text-xs text-slate-500">8 min baca</span>
        </div>
        <h3 class="font-display text-xl font-semibold mb-2 hover:text-blue-400 transition-colors cursor-pointer">Sejarah Kepulauan Sangihe: Warisan Leluhur</h3>
        <p class="text-slate-400 text-sm mb-4 line-clamp-2">Mengenal lebih dalam tentang sejarah dan budaya Kepulauan Sangihe yang kaya...</p>
        <div class="flex items-center justify-between">
         <div class="flex items-center gap-2">
          <div class="w-8 h-8 rounded-full bg-gradient-to-br from-blue-500 to-cyan-500"></div><span class="text-sm text-slate-300">Budi Santoso</span>
         </div><span class="text-xs text-slate-500">10 Des 2024</span>
        </div>
       </div>
      </article><!-- Article Card 3 -->
      <article class="article-card reveal" style="animation-delay: 0.3s;">
       <div class="h-48 bg-gradient-to-br from-emerald-600 to-teal-500 flex items-center justify-center">
        <svg class="w-16 h-16 text-white/80" viewbox="0 0 24 24" fill="currentColor">
         <path d="M12 22c4.97 0 9-4.03 9-9-4.97 0-9 4.03-9 9zM5.6 10.25c0 1.38 1.12 2.5 2.5 2.5.53 0 1.01-.16 1.42-.44l-.02.19c0 1.38 1.12 2.5 2.5 2.5s2.5-1.12 2.5-2.5l-.02-.19c.4.28.89.44 1.42.44 1.38 0 2.5-1.12 2.5-2.5 0-1-.59-1.85-1.43-2.25.84-.4 1.43-1.25 1.43-2.25 0-1.38-1.12-2.5-2.5-2.5-.53 0-1.01.16-1.42.44l.02-.19C14.5 2.12 13.38 1 12 1S9.5 2.12 9.5 3.5l.02.19c-.4-.28-.89-.44-1.42-.44-1.38 0-2.5 1.12-2.5 2.5 0 1 .59 1.85 1.43 2.25-.84.4-1.43 1.25-1.43 2.25zM12 5.5c1.38 0 2.5 1.12 2.5 2.5s-1.12 2.5-2.5 2.5S9.5 9.38 9.5 8s1.12-2.5 2.5-2.5zM3 13c0 4.97 4.03 9 9 9 0-4.97-4.03-9-9-9z" />
        </svg>
       </div>
       <div class="p-6">
        <div class="flex items-center gap-2 mb-3">
         <span class="badge bg-emerald-500/20 text-emerald-300">Lingkungan</span> <span class="text-xs text-slate-500">6 min baca</span>
        </div>
        <h3 class="font-display text-xl font-semibold mb-2 hover:text-blue-400 transition-colors cursor-pointer">Menjaga Kelestarian Terumbu Karang di Laut Sangihe</h3>
        <p class="text-slate-400 text-sm mb-4 line-clamp-2">Upaya pelestarian ekosistem laut yang menjadi tanggung jawab kita bersama...</p>
        <div class="flex items-center justify-between">
         <div class="flex items-center gap-2">
          <div class="w-8 h-8 rounded-full bg-gradient-to-br from-orange-500 to-amber-500"></div><span class="text-sm text-slate-300">Maria Wulan</span>
         </div><span class="text-xs text-slate-500">8 Des 2024</span>
        </div>
       </div>
      </article>
     </div>
     <div class="text-center mt-10">
      <button class="btn-primary"> Lihat Semua Artikel 
       <svg class="w-4 h-4" fill="none" stroke="currentColor" viewbox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3" />
       </svg></button>
     </div>
    </div>
   </section>
   <div class="section-divider max-w-4xl mx-auto"></div><!-- Journal Section -->
   <section id="jurnal" class="relative z-10 py-20 px-4">
    <div class="max-w-6xl mx-auto">
     <div class="text-center mb-12 reveal">
      <span class="badge bg-purple-500/20 text-purple-300 border border-purple-500/30">Jurnal Penelitian</span>
      <h2 class="font-display text-3xl md:text-4xl font-bold mt-4 mb-4">Karya Ilmiah Siswa</h2>
      <p class="text-slate-400 max-w-xl mx-auto">Jurnal penelitian dan karya ilmiah hasil eksplorasi siswa</p>
     </div>
     <div class="space-y-6">
      <!-- Journal Item 1 -->
      <div class="article-card p-6 reveal flex flex-col md:flex-row gap-6">
       <div class="w-full md:w-48 h-32 bg-gradient-to-br from-indigo-600 to-violet-500 rounded-lg flex items-center justify-center flex-shrink-0">
        <svg class="w-12 h-12 text-white/80" viewbox="0 0 24 24" fill="currentColor">
         <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm-5 14H7v-2h7v2zm3-4H7v-2h10v2zm0-4H7V7h10v2z" />
        </svg>
       </div>
       <div class="flex-1">
        <div class="flex flex-wrap items-center gap-2 mb-2">
         <span class="badge bg-indigo-500/20 text-indigo-300">Vol. 1 No. 1</span> <span class="badge bg-slate-500/20 text-slate-300">2024</span>
        </div>
        <h3 class="font-display text-xl font-semibold mb-2 hover:text-blue-400 transition-colors cursor-pointer">Pengaruh Media Sosial terhadap Motivasi Belajar Siswa SMP</h3>
        <p class="text-slate-400 text-sm mb-3">Penelitian tentang dampak penggunaan media sosial terhadap semangat belajar siswa di era digital.</p>
        <div class="flex flex-wrap items-center justify-between gap-4">
         <div class="flex items-center gap-4 text-sm text-slate-500">
          <span class="flex items-center gap-1">
           <svg class="w-4 h-4" fill="none" stroke="currentColor" viewbox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z" />
           </svg> Riko Mamonto, Putri Sahaja </span>
         </div><button class="text-blue-400 hover:text-blue-300 text-sm font-medium flex items-center gap-1"> Baca Selengkapnya 
          <svg class="w-4 h-4" fill="none" stroke="currentColor" viewbox="0 0 24 24">
           <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
          </svg></button>
        </div>
       </div>
      </div><!-- Journal Item 2 -->
      <div class="article-card p-6 reveal flex flex-col md:flex-row gap-6" style="animation-delay: 0.1s;">
       <div class="w-full md:w-48 h-32 bg-gradient-to-br from-rose-600 to-pink-500 rounded-lg flex items-center justify-center flex-shrink-0">
        <svg class="w-12 h-12 text-white/80" viewbox="0 0 24 24" fill="currentColor">
         <path d="M7 14c-1.66 0-3 1.34-3 3 0 1.31-1.16 2-2 2 .92 1.22 2.49 2 4 2 2.21 0 4-1.79 4-4 0-1.66-1.34-3-3-3zm13.71-9.37l-1.34-1.34c-.39-.39-1.02-.39-1.41 0L9 12.25 11.75 15l8.96-8.96c.39-.39.39-1.02 0-1.41z" />
        </svg>
       </div>
       <div class="flex-1">
        <div class="flex flex-wrap items-center gap-2 mb-2">
         <span class="badge bg-rose-500/20 text-rose-300">Vol. 1 No. 2</span> <span class="badge bg-slate-500/20 text-slate-300">2024</span>
        </div>
        <h3 class="font-display text-xl font-semibold mb-2 hover:text-blue-400 transition-colors cursor-pointer">Kreativitas Seni Budaya Sangihe dalam Pembelajaran</h3>
        <p class="text-slate-400 text-sm mb-3">Integrasi seni budaya lokal Sangihe ke dalam kurikulum pembelajaran untuk melestarikan warisan budaya.</p>
        <div class="flex flex-wrap items-center justify-between gap-4">
         <div class="flex items-center gap-4 text-sm text-slate-500">
          <span class="flex items-center gap-1">
           <svg class="w-4 h-4" fill="none" stroke="currentColor" viewbox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z" />
           </svg> Anastasia Kaligis, Dimas Pangemanan </span>
         </div><button class="text-blue-400 hover:text-blue-300 text-sm font-medium flex items-center gap-1"> Baca Selengkapnya 
          <svg class="w-4 h-4" fill="none" stroke="currentColor" viewbox="0 0 24 24">
           <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
          </svg></button>
        </div>
       </div>
      </div><!-- Journal Item 3 -->
      <div class="article-card p-6 reveal flex flex-col md:flex-row gap-6" style="animation-delay: 0.2s;">
       <div class="w-full md:w-48 h-32 bg-gradient-to-br from-amber-600 to-orange-500 rounded-lg flex items-center justify-center flex-shrink-0">
        <svg class="w-12 h-12 text-white/80" viewbox="0 0 24 24" fill="currentColor">
         <path d="M20 6h-4V4c0-1.11-.89-2-2-2h-4c-1.11 0-2 .89-2 2v2H4c-1.11 0-1.99.89-1.99 2L2 19c0 1.11.89 2 2 2h16c1.11 0 2-.89 2-2V8c0-1.11-.89-2-2-2zm-6 0h-4V4h4v2z" />
        </svg>
       </div>
       <div class="flex-1">
        <div class="flex flex-wrap items-center gap-2 mb-2">
         <span class="badge bg-amber-500/20 text-amber-300">Vol. 1 No. 3</span> <span class="badge bg-slate-500/20 text-slate-300">2024</span>
        </div>
        <h3 class="font-display text-xl font-semibold mb-2 hover:text-blue-400 transition-colors cursor-pointer">Potensi Ekonomi Kreatif Berbasis Sumber Daya Lokal</h3>
        <p class="text-slate-400 text-sm mb-3">Studi tentang peluang pengembangan ekonomi kreatif dengan memanfaatkan sumber daya alam Sangihe.</p>
        <div class="flex flex-wrap items-center justify-between gap-4">
         <div class="flex items-center gap-4 text-sm text-slate-500">
          <span class="flex items-center gap-1">
           <svg class="w-4 h-4" fill="none" stroke="currentColor" viewbox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z" />
           </svg> Farel Tangkudung, Jessica Makagansa </span>
         </div><button class="text-blue-400 hover:text-blue-300 text-sm font-medium flex items-center gap-1"> Baca Selengkapnya 
          <svg class="w-4 h-4" fill="none" stroke="currentColor" viewbox="0 0 24 24">
           <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
          </svg></button>
        </div>
       </div>
      </div>
     </div>
    </div>
   </section>
   <div class="section-divider max-w-4xl mx-auto"></div><!-- Gallery Section -->
   <section id="galeri" class="relative z-10 py-20 px-4">
    <div class="max-w-6xl mx-auto">
     <div class="text-center mb-12 reveal">
      <span class="badge bg-cyan-500/20 text-cyan-300 border border-cyan-500/30">Galeri Kegiatan</span>
      <h2 class="font-display text-3xl md:text-4xl font-bold mt-4 mb-4">Momen Berharga</h2>
      <p class="text-slate-400 max-w-xl mx-auto">Dokumentasi kegiatan dan prestasi siswa SMPN 1 Tabukan Utara</p>
     </div>
     <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
      <div class="col-span-2 row-span-2 rounded-xl overflow-hidden group cursor-pointer reveal">
       <div class="w-full h-full min-h-[300px] bg-gradient-to-br from-blue-600 via-indigo-600 to-purple-600 flex items-center justify-center relative">
        <div class="text-center p-6">
         <div class="text-6xl mb-4">
          🏆
         </div>
         <h3 class="text-xl font-bold text-white mb-2">Olimpiade Sains</h3>
         <p class="text-white/70 text-sm">Juara 1 Tingkat Kabupaten</p>
        </div>
        <div class="absolute inset-0 bg-black/40 opacity-0 group-hover:opacity-100 transition-opacity flex items-center justify-center">
         <span class="text-white font-medium">Lihat Detail</span>
        </div>
       </div>
      </div>
      <div class="rounded-xl overflow-hidden group cursor-pointer reveal" style="animation-delay: 0.1s;">
       <div class="w-full h-40 bg-gradient-to-br from-emerald-500 to-teal-600 flex items-center justify-center relative">
        <div class="text-4xl">
         📚
        </div>
        <div class="absolute inset-0 bg-black/40 opacity-0 group-hover:opacity-100 transition-opacity flex items-center justify-center">
         <span class="text-white text-sm font-medium">Literasi</span>
        </div>
       </div>
      </div>
      <div class="rounded-xl overflow-hidden group cursor-pointer reveal" style="animation-delay: 0.15s;">
       <div class="w-full h-40 bg-gradient-to-br from-rose-500 to-pink-600 flex items-center justify-center relative">
        <div class="text-4xl">
         🎭
        </div>
        <div class="absolute inset-0 bg-black/40 opacity-0 group-hover:opacity-100 transition-opacity flex items-center justify-center">
         <span class="text-white text-sm font-medium">Pentas Seni</span>
        </div>
       </div>
      </div>
      <div class="rounded-xl overflow-hidden group cursor-pointer reveal" style="animation-delay: 0.2s;">
       <div class="w-full h-40 bg-gradient-to-br from-amber-500 to-orange-600 flex items-center justify-center relative">
        <div class="text-4xl">
         ⚽
        </div>
        <div class="absolute inset-0 bg-black/40 opacity-0 group-hover:opacity-100 transition-opacity flex items-center justify-center">
         <span class="text-white text-sm font-medium">Olahraga</span>
        </div>
       </div>
      </div>
      <div class="rounded-xl overflow-hidden group cursor-pointer reveal" style="animation-delay: 0.25s;">
       <div class="w-full h-40 bg-gradient-to-br from-violet-500 to-purple-600 flex items-center justify-center relative">
        <div class="text-4xl">
         🔬
        </div>
        <div class="absolute inset-0 bg-black/40 opacity-0 group-hover:opacity-100 transition-opacity flex items-center justify-center">
         <span class="text-white text-sm font-medium">Praktikum</span>
        </div>
       </div>
      </div>
     </div>
    </div>
   </section>
   <div class="section-divider max-w-4xl mx-auto"></div><!-- Admin Login Sidebar -->
   <div id="admin-sidebar" class="fixed right-0 top-0 w-full md:w-96 h-full bg-slate-900 border-l border-slate-700 transform translate-x-full transition-transform duration-300 z-50 flex flex-col overflow-hidden"><!-- Login View -->
    <div id="login-view" class="flex-1 overflow-y-auto p-6">
     <div class="flex items-center justify-between mb-6">
      <h3 class="font-display text-xl font-bold">Admin Panel</h3><button onclick="toggleAdminPanel()" class="p-2 hover:bg-slate-800 rounded-lg transition-colors">
       <svg class="w-5 h-5" fill="none" stroke="currentColor" viewbox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
       </svg></button>
     </div>
     <form onsubmit="handleAdminLogin(event)" class="space-y-4">
      <div><label class="block text-sm font-medium text-slate-300 mb-2">Username</label> <input id="admin-username" type="text" placeholder="admin" class="w-full px-4 py-2 rounded-lg bg-slate-800 border border-slate-700 text-white placeholder-slate-500 focus:outline-none focus:border-blue-500 transition-colors">
      </div>
      <div><label class="block text-sm font-medium text-slate-300 mb-2">Password</label> <input id="admin-password" type="password" placeholder="••••••••" class="w-full px-4 py-2 rounded-lg bg-slate-800 border border-slate-700 text-white placeholder-slate-500 focus:outline-none focus:border-blue-500 transition-colors">
      </div><button type="submit" class="w-full py-2 rounded-lg bg-blue-600 hover:bg-blue-700 text-white font-medium transition-colors"> Login </button>
      <p class="text-xs text-slate-500 text-center mt-4">Demo: username: <span class="font-mono">admin</span> | password: <span class="font-mono">admin123</span></p>
     </form>
    </div><!-- Dashboard View -->
    <div id="dashboard-view" class="hidden flex-1 overflow-y-auto flex flex-col">
     <div class="sticky top-0 bg-slate-900 border-b border-slate-700 p-6 flex items-center justify-between">
      <h3 class="font-display text-xl font-bold">Dashboard Admin</h3><button onclick="handleAdminLogout()" class="p-2 hover:bg-slate-800 rounded-lg transition-colors">
       <svg class="w-5 h-5" fill="none" stroke="currentColor" viewbox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 16l4-4m0 0l-4-4m4 4H7m6 4v1a3 3 0 01-3 3H6a3 3 0 01-3-3V7a3 3 0 013-3h4a3 3 0 013 3v1" />
       </svg></button>
     </div>
     <div class="flex-1 overflow-y-auto p-6 space-y-4"><!-- Tab Navigation -->
      <div class="flex gap-2 mb-6 sticky top-0 bg-slate-900 -mx-6 px-6 py-4 border-b border-slate-700"><button onclick="switchAdminTab('artikel')" class="admin-tab-btn active px-4 py-2 rounded-lg text-sm font-medium transition-colors" data-tab="artikel">Artikel</button> <button onclick="switchAdminTab('jurnal')" class="admin-tab-btn px-4 py-2 rounded-lg text-sm font-medium transition-colors" data-tab="jurnal">Jurnal</button>
      </div><!-- Artikel Tab -->
      <div id="admin-tab-artikel" class="admin-tab"><button onclick="showAddArticleForm()" class="w-full py-2 px-4 rounded-lg bg-blue-600 hover:bg-blue-700 text-white text-sm font-medium mb-4 transition-colors flex items-center justify-center gap-2">
        <svg class="w-4 h-4" fill="none" stroke="currentColor" viewbox="0 0 24 24">
         <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4v16m8-8H4" />
        </svg> Tambah Artikel </button>
       <div id="articles-list" class="space-y-3"></div>
      </div><!-- Jurnal Tab -->
      <div id="admin-tab-jurnal" class="admin-tab hidden"><button onclick="showAddJournalForm()" class="w-full py-2 px-4 rounded-lg bg-purple-600 hover:bg-purple-700 text-white text-sm font-medium mb-4 transition-colors flex items-center justify-center gap-2">
        <svg class="w-4 h-4" fill="none" stroke="currentColor" viewbox="0 0 24 24">
         <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4v16m8-8H4" />
        </svg> Tambah Jurnal </button>
       <div id="journals-list" class="space-y-3"></div>
      </div><!-- Add/Edit Form -->
      <div id="admin-form-container"></div>
     </div>
    </div>
   </div><!-- Admin Panel Toggle Button --> <button id="admin-toggle-btn" onclick="toggleAdminPanel()" class="fixed bottom-6 right-6 z-40 w-14 h-14 rounded-full bg-gradient-to-br from-blue-600 to-purple-600 hover:from-blue-700 hover:to-purple-700 flex items-center justify-center shadow-lg hover:shadow-xl transition-all" title="Admin Panel">
    <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewbox="0 0 24 24">
     <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z" /> <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" />
    </svg></button> <!-- About Section -->
   <section id="tentang" class="relative z-10 py-20 px-4">
    <div class="max-w-6xl mx-auto">
     <div class="grid md:grid-cols-2 gap-12 items-center">
      <div class="reveal">
       <span class="badge bg-blue-500/20 text-blue-300 border border-blue-500/30">Tentang Kami</span>
       <h2 class="font-display text-3xl md:text-4xl font-bold mt-4 mb-6">SMP Negeri 1 Tabukan Utara</h2>
       <p class="text-slate-400 mb-6">Sekolah Menengah Pertama Negeri 1 Tabukan Utara adalah lembaga pendidikan yang berkomitmen untuk menciptakan generasi muda yang cerdas, kreatif, dan berkarakter. Terletak di Kepulauan Sangihe, sekolah kami memiliki visi untuk menjadi pusat pendidikan berkualitas di kawasan Indonesia Timur.</p>
       <p class="text-slate-400 mb-6">Portal jurnal dan artikel ini merupakan wadah bagi siswa-siswi kami untuk mengekspresikan kreativitas dan mengembangkan kemampuan menulis ilmiah. Kami percaya bahwa setiap siswa memiliki potensi untuk berkontribusi dalam dunia literasi.</p>
       <div class="flex flex-wrap gap-4">
        <div class="flex items-center gap-2 text-slate-300">
         <svg class="w-5 h-5 text-blue-400" fill="none" stroke="currentColor" viewbox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z" /> <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z" />
         </svg><span class="text-sm">Kepulauan Sangihe, Sulawesi Utara</span>
        </div>
        <div class="flex items-center gap-2 text-slate-300">
         <svg class="w-5 h-5 text-blue-400" fill="none" stroke="currentColor" viewbox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
         </svg><span class="text-sm">info@smpn1tabukanutara.sch.id</span>
        </div>
       </div>
      </div>
      <div class="reveal" style="animation-delay: 0.2s;">
       <div class="article-card p-8">
        <h3 class="font-display text-xl font-semibold mb-6">Visi &amp; Misi</h3>
        <div class="space-y-4">
         <div class="flex items-start gap-3">
          <div class="w-8 h-8 rounded-full bg-blue-500/20 flex items-center justify-center flex-shrink-0 mt-0.5">
           <span class="text-blue-400 font-bold text-sm">1</span>
          </div>
          <div>
           <h4 class="font-semibold text-slate-200 mb-1">Pendidikan Berkualitas</h4>
           <p class="text-sm text-slate-400">Menyediakan pendidikan bermutu untuk seluruh siswa</p>
          </div>
         </div>
         <div class="flex items-start gap-3">
          <div class="w-8 h-8 rounded-full bg-purple-500/20 flex items-center justify-center flex-shrink-0 mt-0.5">
           <span class="text-purple-400 font-bold text-sm">2</span>
          </div>
          <div>
           <h4 class="font-semibold text-slate-200 mb-1">Karakter Unggul</h4>
           <p class="text-sm text-slate-400">Membentuk karakter siswa yang berakhlak mulia</p>
          </div>
         </div>
         <div class="flex items-start gap-3">
          <div class="w-8 h-8 rounded-full bg-cyan-500/20 flex items-center justify-center flex-shrink-0 mt-0.5">
           <span class="text-cyan-400 font-bold text-sm">3</span>
          </div>
          <div>
           <h4 class="font-semibold text-slate-200 mb-1">Kreativitas &amp; Inovasi</h4>
           <p class="text-sm text-slate-400">Mengembangkan potensi kreatif dan inovatif siswa</p>
          </div>
         </div>
         <div class="flex items-start gap-3">
          <div class="w-8 h-8 rounded-full bg-emerald-500/20 flex items-center justify-center flex-shrink-0 mt-0.5">
           <span class="text-emerald-400 font-bold text-sm">4</span>
          </div>
          <div>
           <h4 class="font-semibold text-slate-200 mb-1">Cinta Budaya Lokal</h4>
           <p class="text-sm text-slate-400">Melestarikan budaya dan kearifan lokal Sangihe</p>
          </div>
         </div>
        </div>
       </div>
      </div>
     </div>
    </div>
   </section><!-- Footer -->
   <footer class="relative z-10 py-12 px-4 border-t border-slate-800">
    <div class="max-w-6xl mx-auto">
     <div class="grid md:grid-cols-4 gap-8 mb-8">
      <div class="md:col-span-2">
       <div class="flex items-center gap-3 mb-4">
        <div class="w-10 h-10 rounded-full bg-gradient-to-br from-blue-500 to-cyan-400 flex items-center justify-center">
         <svg class="w-6 h-6 text-white" viewbox="0 0 24 24" fill="currentColor">
          <path d="M5 13.18v4L12 21l7-3.82v-4L12 17l-7-3.82zM12 3L1 9l11 6 9-4.91V17h2V9L12 3z" />
         </svg>
        </div><span class="font-display font-bold text-lg">SMPN 1 Tabukan Utara</span>
       </div>
       <p class="text-slate-400 text-sm mb-4">Portal Jurnal dan Artikel Ilmiah SMP Negeri 1 Tabukan Utara. Wadah kreativitas dan karya tulis siswa-siswi terbaik.</p>
       <div class="flex gap-3">
        <a href="#" class="w-9 h-9 rounded-full bg-slate-800 flex items-center justify-center hover:bg-blue-600 transition-colors">
         <svg class="w-4 h-4" fill="currentColor" viewbox="0 0 24 24">
          <path d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z" />
         </svg></a> <a href="#" class="w-9 h-9 rounded-full bg-slate-800 flex items-center justify-center hover:bg-blue-600 transition-colors">
         <svg class="w-4 h-4" fill="currentColor" viewbox="0 0 24 24">
          <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z" />
         </svg></a> <a href="#" class="w-9 h-9 rounded-full bg-slate-800 flex items-center justify-center hover:bg-blue-600 transition-colors">
         <svg class="w-4 h-4" fill="currentColor" viewbox="0 0 24 24">
          <path d="M19.615 3.184c-3.604-.246-11.631-.245-15.23 0-3.897.266-4.356 2.62-4.385 8.816.029 6.185.484 8.549 4.385 8.816 3.6.245 11.626.246 15.23 0 3.897-.266 4.356-2.62 4.385-8.816-.029-6.185-.484-8.549-4.385-8.816zm-10.615 12.816v-8l8 3.993-8 4.007z" />
         </svg></a>
       </div>
      </div>
      <div>
       <h4 class="font-semibold mb-4">Navigasi</h4>
       <ul class="space-y-2 text-sm text-slate-400">
        <li><a href="#beranda" class="hover:text-blue-400 transition-colors">Beranda</a></li>
        <li><a href="#artikel" class="hover:text-blue-400 transition-colors">Artikel</a></li>
        <li><a href="#jurnal" class="hover:text-blue-400 transition-colors">Jurnal</a></li>
        <li><a href="#galeri" class="hover:text-blue-400 transition-colors">Galeri</a></li>
        <li><a href="#tentang" class="hover:text-blue-400 transition-colors">Tentang</a></li>
       </ul>
      </div>
      <div>
       <h4 class="font-semibold mb-4">Kontak</h4>
       <ul class="space-y-2 text-sm text-slate-400">
        <li>Kepulauan Sangihe</li>
        <li>Sulawesi Utara, Indonesia</li>
        <li>info@smpn1tabukanutara.sch.id</li>
        <li>+62 xxx xxxx xxxx</li>
       </ul>
      </div>
     </div>
     <div class="pt-8 border-t border-slate-800 text-center text-sm text-slate-500">
      <p>© 2024 SMP Negeri 1 Tabukan Utara. Semua Hak Dilindungi.</p>
      <p class="mt-1">Dibuat dengan ❤️ untuk Pendidikan Indonesia</p>
     </div>
    </div>
   </footer>
  </div>
  <script>
    // Admin Panel State
    let adminState = {
      isLoggedIn: false,
      articles: [],
      journals: [],
      editingId: null,
      editingType: null
    };

    // Initialize Data SDK for admin content
    const adminHandler = {
      onDataChanged(data) {
        adminState.articles = data.filter(item => item.type === 'article');
        adminState.journals = data.filter(item => item.type === 'journal');
        renderAdminLists();
      }
    };

    // Initialize SDK on page load
    (async () => {
      const initResult = await window.dataSdk.init(adminHandler);
      if (initResult.isOk) {
        console.log('Data SDK initialized');
      }
    })();

    // Admin Panel Functions
    function toggleAdminPanel() {
      const sidebar = document.getElementById('admin-sidebar');
      sidebar.classList.toggle('translate-x-full');
    }

    function handleAdminLogin(e) {
      e.preventDefault();
      const username = document.getElementById('admin-username').value;
      const password = document.getElementById('admin-password').value;

      if (username === 'admin' && password === 'admin123') {
        adminState.isLoggedIn = true;
        document.getElementById('login-view').classList.add('hidden');
        document.getElementById('dashboard-view').classList.remove('hidden');
        renderAdminLists();
      } else {
        alert('Username atau password salah!');
      }
    }

    function handleAdminLogout() {
      adminState.isLoggedIn = false;
      adminState.editingId = null;
      adminState.editingType = null;
      document.getElementById('admin-username').value = '';
      document.getElementById('admin-password').value = '';
      document.getElementById('login-view').classList.remove('hidden');
      document.getElementById('dashboard-view').classList.add('hidden');
      document.getElementById('admin-form-container').innerHTML = '';
    }

    function switchAdminTab(tabName) {
      // Update tab buttons
      document.querySelectorAll('.admin-tab-btn').forEach(btn => {
        btn.classList.remove('active');
        btn.style.background = 'transparent';
        btn.style.color = '#94a3b8';
      });
      document.querySelector(`[data-tab="${tabName}"]`).classList.add('active');
      document.querySelector(`[data-tab="${tabName}"]`).style.background = '#3b82f6';
      document.querySelector(`[data-tab="${tabName}"]`).style.color = 'white';

      // Update tab content
      document.querySelectorAll('.admin-tab').forEach(tab => {
        tab.classList.add('hidden');
      });
      document.getElementById(`admin-tab-${tabName}`).classList.remove('hidden');
      document.getElementById('admin-form-container').innerHTML = '';
    }

    function showAddArticleForm() {
      adminState.editingId = null;
      adminState.editingType = 'article';
      renderArticleForm();
    }

    function showAddJournalForm() {
      adminState.editingId = null;
      adminState.editingType = 'journal';
      renderJournalForm();
    }

    function renderArticleForm(item = null) {
      const formHTML = `
        <div style="border-top: 1px solid #475569; padding-top: 16px; margin-top: 16px;">
          <h4 style="font-weight: 600; color: #f1f5f9; margin-bottom: 16px;">${item ? 'Edit Artikel' : 'Tambah Artikel Baru'}</h4>
          <form onsubmit="submitArticleForm(event)">
            <div class="form-group">
              <label>Judul</label>
              <input type="text" id="form-title" placeholder="Masukkan judul artikel" value="${item?.title || ''}" required>
            </div>
            <div class="form-group">
              <label>Kategori</label>
              <select id="form-category" required>
                <option value="">Pilih kategori</option>
                <option value="Pendidikan" ${item?.category === 'Pendidikan' ? 'selected' : ''}>Pendidikan</option>
                <option value="Sejarah" ${item?.category === 'Sejarah' ? 'selected' : ''}>Sejarah</option>
                <option value="Lingkungan" ${item?.category === 'Lingkungan' ? 'selected' : ''}>Lingkungan</option>
                <option value="Seni" ${item?.category === 'Seni' ? 'selected' : ''}>Seni</option>
              </select>
            </div>
            <div class="form-group">
              <label>Penulis</label>
              <input type="text" id="form-author" placeholder="Nama penulis" value="${item?.author || ''}" required>
            </div>
            <div class="form-group">
              <label>Konten</label>
              <textarea id="form-content" placeholder="Masukkan konten artikel" required>${item?.content || ''}</textarea>
            </div>
            <div class="form-actions">
              <button type="submit" class="form-submit">Simpan</button>
              <button type="button" class="form-cancel" onclick="cancelForm()">Batal</button>
            </div>
          </form>
        </div>
      `;
      document.getElementById('admin-form-container').innerHTML = formHTML;
    }

    function renderJournalForm(item = null) {
      const formHTML = `
        <div style="border-top: 1px solid #475569; padding-top: 16px; margin-top: 16px;">
          <h4 style="font-weight: 600; color: #f1f5f9; margin-bottom: 16px;">${item ? 'Edit Jurnal' : 'Tambah Jurnal Baru'}</h4>
          <form onsubmit="submitJournalForm(event)">
            <div class="form-group">
              <label>Judul Jurnal</label>
              <input type="text" id="form-title" placeholder="Masukkan judul jurnal" value="${item?.title || ''}" required>
            </div>
            <div class="form-group">
              <label>Kategori</label>
              <select id="form-category" required>
                <option value="">Pilih kategori</option>
                <option value="Sosial" ${item?.category === 'Sosial' ? 'selected' : ''}>Sosial</option>
                <option value="Budaya" ${item?.category === 'Budaya' ? 'selected' : ''}>Budaya</option>
                <option value="Ekonomi" ${item?.category === 'Ekonomi' ? 'selected' : ''}>Ekonomi</option>
                <option value="Penelitian" ${item?.category === 'Penelitian' ? 'selected' : ''}>Penelitian</option>
              </select>
            </div>
            <div class="form-group">
              <label>Penulis (Pisahkan dengan koma untuk multiple authors)</label>
              <input type="text" id="form-author" placeholder="Nama penulis" value="${item?.author || ''}" required>
            </div>
            <div class="form-group">
              <label>Deskripsi Singkat</label>
              <textarea id="form-content" placeholder="Deskripsi jurnal" required>${item?.content || ''}</textarea>
            </div>
            <div class="form-actions">
              <button type="submit" class="form-submit">Simpan</button>
              <button type="button" class="form-cancel" onclick="cancelForm()">Batal</button>
            </div>
          </form>
        </div>
      `;
      document.getElementById('admin-form-container').innerHTML = formHTML;
    }

    async function submitArticleForm(e) {
      e.preventDefault();
      const title = document.getElementById('form-title').value;
      const category = document.getElementById('form-category').value;
      const author = document.getElementById('form-author').value;
      const content = document.getElementById('form-content').value;

      const articleData = {
        type: 'article',
        title,
        category,
        author,
        content,
        date: new Date().toISOString().split('T')[0]
      };

      if (adminState.editingId) {
        const existingItem = adminState.articles.find(a => a.__backendId === adminState.editingId);
        const result = await window.dataSdk.update({ ...existingItem, ...articleData });
        if (result.isOk) {
          cancelForm();
        }
      } else {
        const result = await window.dataSdk.create(articleData);
        if (result.isOk) {
          document.getElementById('form-title').value = '';
          document.getElementById('form-category').value = '';
          document.getElementById('form-author').value = '';
          document.getElementById('form-content').value = '';
        }
      }
    }

    async function submitJournalForm(e) {
      e.preventDefault();
      const title = document.getElementById('form-title').value;
      const category = document.getElementById('form-category').value;
      const author = document.getElementById('form-author').value;
      const content = document.getElementById('form-content').value;

      const journalData = {
        type: 'journal',
        title,
        category,
        author,
        content,
        date: new Date().toISOString().split('T')[0]
      };

      if (adminState.editingId) {
        const existingItem = adminState.journals.find(j => j.__backendId === adminState.editingId);
        const result = await window.dataSdk.update({ ...existingItem, ...journalData });
        if (result.isOk) {
          cancelForm();
        }
      } else {
        const result = await window.dataSdk.create(journalData);
        if (result.isOk) {
          document.getElementById('form-title').value = '';
          document.getElementById('form-category').value = '';
          document.getElementById('form-author').value = '';
          document.getElementById('form-content').value = '';
        }
      }
    }

    function cancelForm() {
      adminState.editingId = null;
      adminState.editingType = null;
      document.getElementById('admin-form-container').innerHTML = '';
    }

    function editArticle(id) {
      adminState.editingId = id;
      adminState.editingType = 'article';
      const article = adminState.articles.find(a => a.__backendId === id);
      renderArticleForm(article);
    }

    function editJournal(id) {
      adminState.editingId = id;
      adminState.editingType = 'journal';
      const journal = adminState.journals.find(j => j.__backendId === id);
      renderJournalForm(journal);
    }

    async function deleteArticle(id) {
      if (confirm('Hapus artikel ini?')) {
        const article = adminState.articles.find(a => a.__backendId === id);
        const result = await window.dataSdk.delete(article);
        if (result.isOk) {
          renderAdminLists();
        }
      }
    }

    async function deleteJournal(id) {
      if (confirm('Hapus jurnal ini?')) {
        const journal = adminState.journals.find(j => j.__backendId === id);
        const result = await window.dataSdk.delete(journal);
        if (result.isOk) {
          renderAdminLists();
        }
      }
    }

    function renderAdminLists() {
      // Render articles
      const articlesHTML = adminState.articles.map(article => `
        <div class="admin-item">
          <div class="admin-item-text">
            <div class="admin-item-title">${article.title}</div>
            <div class="admin-item-desc">Oleh: ${article.author} • ${article.date}</div>
          </div>
          <div class="admin-item-actions">
            <button class="admin-btn-small admin-btn-edit" onclick="editArticle('${article.__backendId}')">Edit</button>
            <button class="admin-btn-small admin-btn-delete" onclick="deleteArticle('${article.__backendId}')">Hapus</button>
          </div>
        </div>
      `).join('');
      
      document.getElementById('articles-list').innerHTML = articlesHTML || '<p style="color: #94a3b8; text-align: center; padding: 20px; font-size: 14px;">Belum ada artikel</p>';

      // Render journals
      const journalsHTML = adminState.journals.map(journal => `
        <div class="admin-item">
          <div class="admin-item-text">
            <div class="admin-item-title">${journal.title}</div>
            <div class="admin-item-desc">Oleh: ${journal.author} • ${journal.date}</div>
          </div>
          <div class="admin-item-actions">
            <button class="admin-btn-small admin-btn-edit" onclick="editJournal('${journal.__backendId}')">Edit</button>
            <button class="admin-btn-small admin-btn-delete" onclick="deleteJournal('${journal.__backendId}')">Hapus</button>
          </div>
        </div>
      `).join('');
      
      document.getElementById('journals-list').innerHTML = journalsHTML || '<p style="color: #94a3b8; text-align: center; padding: 20px; font-size: 14px;">Belum ada jurnal</p>';
    }

    const defaultConfig = {
      school_name: 'SMPN 1 Tabukan Utara',
      hero_title: 'Jurnal & Artikel Ilmiah',
      hero_subtitle: 'Wadah kreativitas dan karya ilmiah siswa-siswi terbaik. Temukan artikel menarik, jurnal penelitian, dan berbagai karya tulis berkualitas.',
      background_color: '#0f172a',
      surface_color: '#1e293b',
      text_color: '#f1f5f9',
      primary_action: '#3b82f6',
      secondary_action: '#60a5fa',
      font_family: 'Plus Jakarta Sans',
      font_size: 16
    };
    
    // Initialize Element SDK
    if (window.elementSdk) {
      window.elementSdk.init({
        defaultConfig,
        onConfigChange: async (config) => {
          // Update school name
          const navSchoolName = document.getElementById('nav-school-name');
          if (navSchoolName) {
            navSchoolName.textContent = config.school_name || defaultConfig.school_name;
          }
          
          // Update hero title
          const heroTitle = document.getElementById('hero-title');
          if (heroTitle) {
            heroTitle.innerHTML = `
              <span class="bg-gradient-to-r from-white via-blue-100 to-cyan-200 bg-clip-text text-transparent">
                ${config.hero_title || defaultConfig.hero_title}
              </span>
              <br>
              <span class="text-2xl md:text-4xl text-slate-300">${config.school_name || defaultConfig.school_name}</span>
            `;
          }
          
          // Update hero subtitle
          const heroSubtitle = document.getElementById('hero-subtitle');
          if (heroSubtitle) {
            heroSubtitle.textContent = config.hero_subtitle || defaultConfig.hero_subtitle;
          }
          
          // Update colors
          const bgColor = config.background_color || defaultConfig.background_color;
          const surfaceColor = config.surface_color || defaultConfig.surface_color;
          const textColor = config.text_color || defaultConfig.text_color;
          const primaryAction = config.primary_action || defaultConfig.primary_action;
          const secondaryAction = config.secondary_action || defaultConfig.secondary_action;
          
          document.documentElement.style.setProperty('--primary-bg', bgColor);
          document.documentElement.style.setProperty('--secondary-surface', surfaceColor);
          document.documentElement.style.setProperty('--text-color', textColor);
          document.documentElement.style.setProperty('--primary-action', primaryAction);
          document.documentElement.style.setProperty('--secondary-action', secondaryAction);
          
          document.body.style.background = bgColor;
          document.body.style.color = textColor;
          
          // Update font
          const fontFamily = config.font_family || defaultConfig.font_family;
          const baseFontStack = 'Arial, sans-serif';
          document.body.style.fontFamily = `${fontFamily}, ${baseFontStack}`;
          
          // Update font size
          const baseSize = config.font_size || defaultConfig.font_size;
          document.body.style.fontSize = `${baseSize}px`;
        },
        mapToCapabilities: (config) => ({
          recolorables: [
            {
              get: () => config.background_color || defaultConfig.background_color,
              set: (value) => window.elementSdk.setConfig({ background_color: value })
            },
            {
              get: () => config.surface_color || defaultConfig.surface_color,
              set: (value) => window.elementSdk.setConfig({ surface_color: value })
            },
            {
              get: () => config.text_color || defaultConfig.text_color,
              set: (value) => window.elementSdk.setConfig({ text_color: value })
            },
            {
              get: () => config.primary_action || defaultConfig.primary_action,
              set: (value) => window.elementSdk.setConfig({ primary_action: value })
            },
            {
              get: () => config.secondary_action || defaultConfig.secondary_action,
              set: (value) => window.elementSdk.setConfig({ secondary_action: value })
            }
          ],
          borderables: [],
          fontEditable: {
            get: () => config.font_family || defaultConfig.font_family,
            set: (value) => window.elementSdk.setConfig({ font_family: value })
          },
          fontSizeable: {
            get: () => config.font_size || defaultConfig.font_size,
            set: (value) => window.elementSdk.setConfig({ font_size: value })
          }
        }),
        mapToEditPanelValues: (config) => new Map([
          ['school_name', config.school_name || defaultConfig.school_name],
          ['hero_title', config.hero_title || defaultConfig.hero_title],
          ['hero_subtitle', config.hero_subtitle || defaultConfig.hero_subtitle]
        ])
      });
    }
    
    // Mobile menu toggle
    function toggleMobileMenu() {
      const menu = document.getElementById('mobile-menu');
      menu.classList.toggle('hidden');
    }
    
    // Scroll reveal animation
    function revealOnScroll() {
      const reveals = document.querySelectorAll('.reveal');
      reveals.forEach(element => {
        const windowHeight = window.innerHeight;
        const elementTop = element.getBoundingClientRect().top;
        const revealPoint = 150;
        
        if (elementTop < windowHeight - revealPoint) {
          element.classList.add('active');
        }
      });
    }
    
    // Counter animation
    function animateCounters() {
      const counters = document.querySelectorAll('.stat-number');
      counters.forEach(counter => {
        const target = parseInt(counter.textContent);
        let count = 0;
        const increment = target / 50;
        
        const updateCount = () => {
          if (count < target) {
            count += increment;
            counter.textContent = Math.ceil(count) + '+';
            requestAnimationFrame(updateCount);
          } else {
            counter.textContent = target + '+';
          }
        };
        updateCount();
      });
    }
    
    // Smooth scroll for navigation links
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', function(e) {
        e.preventDefault();
        const target = document.querySelector(this.getAttribute('href'));
        if (target) {
          target.scrollIntoView({ behavior: 'smooth', block: 'start' });
          // Close mobile menu if open
          document.getElementById('mobile-menu').classList.add('hidden');
        }
      });
    });
    
    // Initialize
    window.addEventListener('scroll', revealOnScroll);
    window.addEventListener('load', () => {
      revealOnScroll();
      animateCounters();
    });
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9d1b83277613f884',t:'MTc3MTczMjE1My4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
