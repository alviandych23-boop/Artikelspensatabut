<!doctype html>
<html lang="id" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Jurnal SMP Negeri 1 Tabukan Utara</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&amp;family=Source+Sans+Pro:wght@300;400;600;700&amp;display=swap" rel="stylesheet">
  <style>
    html, body { height: 100%; margin: 0; }
    
    :root {
      --primary-bg: #0f172a;
      --secondary-surface: #1e293b;
      --text-color: #f8fafc;
      --primary-action: #3b82f6;
      --secondary-action: #60a5fa;
    }
    
    .font-display { font-family: 'Playfair Display', Georgia, serif; }
    .font-body { font-family: 'Source Sans Pro', Arial, sans-serif; }
    
    /* Modal Styles */
    .modal-overlay {
      display: none;
      position: fixed;
      inset: 0;
      background: rgba(0, 0, 0, 0.7);
      z-index: 1000;
      animation: fadeIn 0.3s ease;
    }
    
    .modal-overlay.active {
      display: flex;
      align-items: center;
      justify-content: center;
    }
    
    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }
    
    .modal-content {
      background: var(--primary-bg);
      border: 1px solid rgba(59, 130, 246, 0.3);
      border-radius: 1.5rem;
      max-width: 90%;
      max-height: 90%;
      overflow-y: auto;
      animation: slideUp 0.3s ease;
    }
    
    @keyframes slideUp {
      from { transform: translateY(30px); opacity: 0; }
      to { transform: translateY(0); opacity: 1; }
    }
    
    .admin-btn {
      position: fixed;
      bottom: 2rem;
      right: 2rem;
      z-index: 100;
      width: 60px;
      height: 60px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--primary-action), var(--secondary-action));
      border: none;
      cursor: pointer;
      font-size: 1.5rem;
      display: flex;
      align-items: center;
      justify-content: center;
      box-shadow: 0 10px 30px rgba(59, 130, 246, 0.3);
      transition: all 0.3s ease;
      animation: pulse 2s infinite;
    }
    
    .admin-btn:hover {
      transform: scale(1.1);
      box-shadow: 0 15px 40px rgba(59, 130, 246, 0.5);
    }
    
    @keyframes pulse {
      0%, 100% { box-shadow: 0 10px 30px rgba(59, 130, 246, 0.3); }
      50% { box-shadow: 0 10px 40px rgba(59, 130, 246, 0.6); }
    }
    
    /* Animated Background */
    .animated-bg {
      background: linear-gradient(135deg, var(--primary-bg) 0%, #1e3a5f 50%, var(--primary-bg) 100%);
      background-size: 400% 400%;
      animation: gradientShift 15s ease infinite;
    }
    
    @keyframes gradientShift {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }
    
    /* Floating Elements Animation */
    .float-element {
      animation: float 6s ease-in-out infinite;
    }
    
    .float-element:nth-child(2) { animation-delay: -2s; }
    .float-element:nth-child(3) { animation-delay: -4s; }
    
    @keyframes float {
      0%, 100% { transform: translateY(0px) rotate(0deg); }
      50% { transform: translateY(-20px) rotate(5deg); }
    }
    
    /* Particle Animation */
    .particle {
      position: absolute;
      width: 4px;
      height: 4px;
      background: var(--secondary-action);
      border-radius: 50%;
      opacity: 0.6;
      animation: particleFloat 8s infinite;
    }
    
    @keyframes particleFloat {
      0%, 100% { transform: translateY(0) translateX(0); opacity: 0.6; }
      25% { transform: translateY(-100px) translateX(20px); opacity: 0.3; }
      50% { transform: translateY(-200px) translateX(-10px); opacity: 0.6; }
      75% { transform: translateY(-100px) translateX(30px); opacity: 0.3; }
    }
    
    /* Scroll Reveal Animation */
    .reveal {
      opacity: 0;
      transform: translateY(30px);
      transition: all 0.8s cubic-bezier(0.4, 0, 0.2, 1);
    }
    
    .reveal.active {
      opacity: 1;
      transform: translateY(0);
    }
    
    /* Card Hover Effects */
    .article-card {
      transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
      transform-style: preserve-3d;
    }
    
    .article-card:hover {
      transform: translateY(-10px) scale(1.02);
      box-shadow: 0 25px 50px -12px rgba(59, 130, 246, 0.25);
    }
    
    .article-card::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background: linear-gradient(135deg, transparent 0%, rgba(59, 130, 246, 0.1) 100%);
      opacity: 0;
      transition: opacity 0.4s ease;
      border-radius: inherit;
    }
    
    .article-card:hover::before {
      opacity: 1;
    }
    
    /* Book Animation */
    .book-icon {
      animation: bookBounce 2s ease-in-out infinite;
    }
    
    @keyframes bookBounce {
      0%, 100% { transform: rotate(-5deg); }
      50% { transform: rotate(5deg); }
    }
    
    /* Pen Writing Animation */
    .pen-icon {
      animation: penWrite 3s ease-in-out infinite;
    }
    
    @keyframes penWrite {
      0%, 100% { transform: translateX(0) rotate(0deg); }
      25% { transform: translateX(5px) rotate(5deg); }
      75% { transform: translateX(-5px) rotate(-5deg); }
    }
    
    /* Graduation Cap Animation */
    .cap-icon {
      animation: capFloat 4s ease-in-out infinite;
    }
    
    @keyframes capFloat {
      0%, 100% { transform: translateY(0) rotate(0deg); }
      50% { transform: translateY(-10px) rotate(10deg); }
    }
    
    /* Shine Effect */
    .shine {
      position: relative;
      overflow: hidden;
    }
    
    .shine::after {
      content: '';
      position: absolute;
      top: -50%;
      left: -50%;
      width: 200%;
      height: 200%;
      background: linear-gradient(
        to right,
        transparent 0%,
        rgba(255, 255, 255, 0.1) 50%,
        transparent 100%
      );
      transform: rotate(30deg);
      animation: shine 4s infinite;
    }
    
    @keyframes shine {
      0% { transform: translateX(-100%) rotate(30deg); }
      100% { transform: translateX(100%) rotate(30deg); }
    }
    
    /* Pulse Ring */
    .pulse-ring {
      animation: pulseRing 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
    }
    
    @keyframes pulseRing {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.5; }
    }
    
    /* Navigation Link Animation */
    .nav-link {
      position: relative;
      transition: color 0.3s ease;
    }
    
    .nav-link::after {
      content: '';
      position: absolute;
      bottom: -4px;
      left: 0;
      width: 0;
      height: 2px;
      background: var(--primary-action);
      transition: width 0.3s ease;
    }
    
    .nav-link:hover::after {
      width: 100%;
    }
    
    /* Stagger Animation */
    .stagger-item {
      opacity: 0;
      animation: staggerIn 0.6s ease forwards;
    }
    
    .stagger-item:nth-child(1) { animation-delay: 0.1s; }
    .stagger-item:nth-child(2) { animation-delay: 0.2s; }
    .stagger-item:nth-child(3) { animation-delay: 0.3s; }
    .stagger-item:nth-child(4) { animation-delay: 0.4s; }
    .stagger-item:nth-child(5) { animation-delay: 0.5s; }
    .stagger-item:nth-child(6) { animation-delay: 0.6s; }
    
    @keyframes staggerIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
    
    /* Typing Animation */
    .typing-text {
      overflow: hidden;
      border-right: 3px solid var(--primary-action);
      white-space: nowrap;
      animation: typing 3.5s steps(40, end), blink 0.75s step-end infinite;
    }
    
    @keyframes typing {
      from { width: 0; }
      to { width: 100%; }
    }
    
    @keyframes blink {
      from, to { border-color: transparent; }
      50% { border-color: var(--primary-action); }
    }
    
    /* Category Badge Animation */
    .category-badge {
      transition: all 0.3s ease;
    }
    
    .category-badge:hover {
      transform: scale(1.1);
      box-shadow: 0 0 20px rgba(59, 130, 246, 0.5);
    }
    
    /* Stats Counter Animation */
    .stat-number {
      background: linear-gradient(135deg, var(--primary-action), var(--secondary-action));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
    
    /* Scrollbar Styling */
    ::-webkit-scrollbar {
      width: 8px;
    }
    
    ::-webkit-scrollbar-track {
      background: var(--primary-bg);
    }
    
    ::-webkit-scrollbar-thumb {
      background: var(--primary-action);
      border-radius: 4px;
    }
    
    ::-webkit-scrollbar-thumb:hover {
      background: var(--secondary-action);
    }
  </style>
  <style>body { box-sizing: border-box; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
 </head>
 <body class="h-full animated-bg font-body overflow-auto" style="color: var(--text-color);"><!-- Floating Particles Background -->
  <div class="fixed inset-0 pointer-events-none overflow-hidden">
   <div class="particle" style="top: 10%; left: 10%;"></div>
   <div class="particle" style="top: 20%; left: 80%; animation-delay: -2s;"></div>
   <div class="particle" style="top: 60%; left: 20%; animation-delay: -4s;"></div>
   <div class="particle" style="top: 80%; left: 70%; animation-delay: -6s;"></div>
   <div class="particle" style="top: 40%; left: 50%; animation-delay: -3s;"></div>
   <div class="particle" style="top: 70%; left: 90%; animation-delay: -5s;"></div>
  </div><!-- Floating School Icons -->
  <div class="fixed inset-0 pointer-events-none overflow-hidden opacity-10">
   <div class="float-element absolute top-20 left-10 text-6xl book-icon">
    📚
   </div>
   <div class="float-element absolute top-40 right-20 text-5xl pen-icon">
    ✏️
   </div>
   <div class="float-element absolute bottom-40 left-20 text-6xl cap-icon">
    🎓
   </div>
   <div class="float-element absolute top-60 right-40 text-4xl" style="animation-delay: -1s;">
    🏫
   </div>
   <div class="float-element absolute bottom-20 right-10 text-5xl" style="animation-delay: -3s;">
    📖
   </div>
  </div>
  <div class="relative z-10 w-full min-h-full"><!-- Header Navigation -->
   <header class="sticky top-0 z-50 backdrop-blur-md border-b" style="background: rgba(15, 23, 42, 0.9); border-color: rgba(59, 130, 246, 0.2);">
    <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
     <div class="flex items-center justify-between h-16"><!-- Logo -->
      <div class="flex items-center space-x-3">
       <div class="w-12 h-12 rounded-full flex items-center justify-center shine" style="background: linear-gradient(135deg, var(--primary-action), var(--secondary-action));"><span class="text-2xl">🏫</span>
       </div>
       <div>
        <h1 id="school-name" class="font-display font-bold text-lg" style="color: var(--text-color);">SMP Negeri 1 Tabukan Utara</h1>
        <p id="tagline" class="text-xs" style="color: var(--secondary-action);">Unggul dalam Prestasi, Santun dalam Perilaku</p>
       </div>
      </div><!-- Navigation Links -->
      <div class="hidden md:flex items-center space-x-8"><a href="#beranda" class="nav-link text-sm font-medium" style="color: var(--text-color);">Beranda</a> <a href="#artikel" class="nav-link text-sm font-medium" style="color: var(--text-color);">Artikel</a> <a href="#kategori" class="nav-link text-sm font-medium" style="color: var(--text-color);">Kategori</a> <a href="#tentang" class="nav-link text-sm font-medium" style="color: var(--text-color);">Tentang</a>
      </div><!-- Mobile Menu Button --> <button id="mobile-menu-btn" class="md:hidden p-2 rounded-lg transition-colors" style="background: var(--secondary-surface);">
       <svg class="w-6 h-6" fill="none" stroke="currentColor" viewbox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
       </svg></button>
     </div><!-- Mobile Menu -->
     <div id="mobile-menu" class="hidden md:hidden pb-4">
      <div class="flex flex-col space-y-2"><a href="#beranda" class="px-4 py-2 rounded-lg transition-colors" style="background: var(--secondary-surface);">Beranda</a> <a href="#artikel" class="px-4 py-2 rounded-lg transition-colors" style="background: var(--secondary-surface);">Artikel</a> <a href="#kategori" class="px-4 py-2 rounded-lg transition-colors" style="background: var(--secondary-surface);">Kategori</a> <a href="#tentang" class="px-4 py-2 rounded-lg transition-colors" style="background: var(--secondary-surface);">Tentang</a>
      </div>
     </div>
    </nav>
   </header><!-- Hero Section -->
   <section id="beranda" class="relative py-20 px-4 sm:px-6 lg:px-8 overflow-hidden">
    <div class="max-w-7xl mx-auto text-center">
     <div class="stagger-item"><span class="inline-block px-4 py-2 rounded-full text-sm font-medium mb-6" style="background: rgba(59, 130, 246, 0.2); color: var(--secondary-action);"> 📰 Portal Jurnal &amp; Artikel Sekolah </span>
     </div>
     <h1 id="welcome-title" class="stagger-item font-display text-4xl sm:text-5xl lg:text-6xl font-bold mb-6" style="color: var(--text-color);">Selamat Datang di Portal<br><span class="stat-number">Artikel &amp; Jurnal</span></h1>
     <p class="stagger-item text-lg sm:text-xl max-w-3xl mx-auto mb-10" style="color: rgba(248, 250, 252, 0.7);">Jelajahi berbagai artikel pendidikan, jurnal ilmiah, dan karya tulis dari siswa dan guru SMP Negeri 1 Tabukan Utara</p>
     <div class="stagger-item flex flex-col sm:flex-row items-center justify-center gap-4"><a href="#artikel" class="px-8 py-4 rounded-xl font-semibold transition-all transform hover:scale-105 shine" style="background: linear-gradient(135deg, var(--primary-action), var(--secondary-action)); color: white;"> 📖 Baca Artikel </a> <a href="#kategori" class="px-8 py-4 rounded-xl font-semibold transition-all transform hover:scale-105 border" style="border-color: var(--primary-action); color: var(--text-color);"> 🗂️ Lihat Kategori </a>
     </div><!-- Stats -->
     <div class="grid grid-cols-2 md:grid-cols-4 gap-6 mt-16">
      <div class="stagger-item p-6 rounded-2xl" style="background: var(--secondary-surface);">
       <div class="stat-number text-3xl font-bold font-display">
        150+
       </div>
       <p class="text-sm mt-2" style="color: rgba(248, 250, 252, 0.6);">Artikel</p>
      </div>
      <div class="stagger-item p-6 rounded-2xl" style="background: var(--secondary-surface);">
       <div class="stat-number text-3xl font-bold font-display">
        45+
       </div>
       <p class="text-sm mt-2" style="color: rgba(248, 250, 252, 0.6);">Penulis</p>
      </div>
      <div class="stagger-item p-6 rounded-2xl" style="background: var(--secondary-surface);">
       <div class="stat-number text-3xl font-bold font-display">
        12
       </div>
       <p class="text-sm mt-2" style="color: rgba(248, 250, 252, 0.6);">Kategori</p>
      </div>
      <div class="stagger-item p-6 rounded-2xl" style="background: var(--secondary-surface);">
       <div class="stat-number text-3xl font-bold font-display">
        5K+
       </div>
       <p class="text-sm mt-2" style="color: rgba(248, 250, 252, 0.6);">Pembaca</p>
      </div>
     </div>
    </div>
   </section><!-- Featured Articles -->
   <section id="artikel" class="py-20 px-4 sm:px-6 lg:px-8">
    <div class="max-w-7xl mx-auto">
     <div class="text-center mb-12 reveal"><span class="inline-block px-4 py-2 rounded-full text-sm font-medium mb-4" style="background: rgba(59, 130, 246, 0.2); color: var(--secondary-action);"> ✨ Artikel Terbaru </span>
      <h2 class="font-display text-3xl sm:text-4xl font-bold" style="color: var(--text-color);">Karya Terbaik Kami</h2>
     </div>
     <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8"><!-- Article 1 -->
      <article class="article-card relative rounded-2xl overflow-hidden reveal" style="background: var(--secondary-surface);">
       <div class="h-48 relative overflow-hidden" style="background: linear-gradient(135deg, #3b82f6, #8b5cf6);">
        <div class="absolute inset-0 flex items-center justify-center"><span class="text-6xl">🔬</span>
        </div>
        <div class="absolute top-4 left-4"><span class="category-badge px-3 py-1 rounded-full text-xs font-medium" style="background: rgba(255,255,255,0.2); color: white;"> Sains </span>
        </div>
       </div>
       <div class="p-6">
        <h3 class="font-display text-xl font-bold mb-3" style="color: var(--text-color);">Eksperimen Fotosintesis: Membuktikan Proses Kehidupan Tumbuhan</h3>
        <p class="text-sm mb-4" style="color: rgba(248, 250, 252, 0.6);">Penelitian sederhana yang dilakukan siswa kelas 8 untuk memahami proses fotosintesis secara langsung...</p>
        <div class="flex items-center justify-between">
         <div class="flex items-center space-x-2">
          <div class="w-8 h-8 rounded-full flex items-center justify-center" style="background: var(--primary-action);"><span class="text-xs">AS</span>
          </div><span class="text-xs" style="color: rgba(248, 250, 252, 0.6);">Andi Susanto</span>
         </div><span class="text-xs" style="color: var(--secondary-action);">12 Jan 2024</span>
        </div>
       </div>
      </article><!-- Article 2 -->
      <article class="article-card relative rounded-2xl overflow-hidden reveal" style="background: var(--secondary-surface);">
       <div class="h-48 relative overflow-hidden" style="background: linear-gradient(135deg, #10b981, #3b82f6);">
        <div class="absolute inset-0 flex items-center justify-center"><span class="text-6xl">📚</span>
        </div>
        <div class="absolute top-4 left-4"><span class="category-badge px-3 py-1 rounded-full text-xs font-medium" style="background: rgba(255,255,255,0.2); color: white;"> Bahasa </span>
        </div>
       </div>
       <div class="p-6">
        <h3 class="font-display text-xl font-bold mb-3" style="color: var(--text-color);">Kekayaan Bahasa Daerah Sangihe dalam Karya Sastra Modern</h3>
        <p class="text-sm mb-4" style="color: rgba(248, 250, 252, 0.6);">Melestarikan bahasa daerah Sangihe melalui puisi dan cerpen kontemporer yang ditulis oleh generasi muda...</p>
        <div class="flex items-center justify-between">
         <div class="flex items-center space-x-2">
          <div class="w-8 h-8 rounded-full flex items-center justify-center" style="background: var(--primary-action);"><span class="text-xs">SR</span>
          </div><span class="text-xs" style="color: rgba(248, 250, 252, 0.6);">Siti Rahayu</span>
         </div><span class="text-xs" style="color: var(--secondary-action);">10 Jan 2024</span>
        </div>
       </div>
      </article><!-- Article 3 -->
      <article class="article-card relative rounded-2xl overflow-hidden reveal" style="background: var(--secondary-surface);">
       <div class="h-48 relative overflow-hidden" style="background: linear-gradient(135deg, #f59e0b, #ef4444);">
        <div class="absolute inset-0 flex items-center justify-center"><span class="text-6xl">🎨</span>
        </div>
        <div class="absolute top-4 left-4"><span class="category-badge px-3 py-1 rounded-full text-xs font-medium" style="background: rgba(255,255,255,0.2); color: white;"> Seni Budaya </span>
        </div>
       </div>
       <div class="p-6">
        <h3 class="font-display text-xl font-bold mb-3" style="color: var(--text-color);">Tarian Tradisional Masamper: Warisan Budaya yang Harus Dijaga</h3>
        <p class="text-sm mb-4" style="color: rgba(248, 250, 252, 0.6);">Dokumentasi dan pelestarian tarian Masamper sebagai identitas budaya masyarakat Sangihe Talaud...</p>
        <div class="flex items-center justify-between">
         <div class="flex items-center space-x-2">
          <div class="w-8 h-8 rounded-full flex items-center justify-center" style="background: var(--primary-action);"><span class="text-xs">BW</span>
          </div><span class="text-xs" style="color: rgba(248, 250, 252, 0.6);">Bu Wati, S.Pd</span>
         </div><span class="text-xs" style="color: var(--secondary-action);">8 Jan 2024</span>
        </div>
       </div>
      </article><!-- Article 4 -->
      <article class="article-card relative rounded-2xl overflow-hidden reveal" style="background: var(--secondary-surface);">
       <div class="h-48 relative overflow-hidden" style="background: linear-gradient(135deg, #8b5cf6, #ec4899);">
        <div class="absolute inset-0 flex items-center justify-center"><span class="text-6xl">🌊</span>
        </div>
        <div class="absolute top-4 left-4"><span class="category-badge px-3 py-1 rounded-full text-xs font-medium" style="background: rgba(255,255,255,0.2); color: white;"> Lingkungan </span>
        </div>
       </div>
       <div class="p-6">
        <h3 class="font-display text-xl font-bold mb-3" style="color: var(--text-color);">Menjaga Kelestarian Terumbu Karang di Perairan Tabukan</h3>
        <p class="text-sm mb-4" style="color: rgba(248, 250, 252, 0.6);">Program konservasi laut yang melibatkan siswa dalam upaya pelestarian ekosistem terumbu karang...</p>
        <div class="flex items-center justify-between">
         <div class="flex items-center space-x-2">
          <div class="w-8 h-8 rounded-full flex items-center justify-center" style="background: var(--primary-action);"><span class="text-xs">RH</span>
          </div><span class="text-xs" style="color: rgba(248, 250, 252, 0.6);">Riko Hartono</span>
         </div><span class="text-xs" style="color: var(--secondary-action);">5 Jan 2024</span>
        </div>
       </div>
      </article><!-- Article 5 -->
      <article class="article-card relative rounded-2xl overflow-hidden reveal" style="background: var(--secondary-surface);">
       <div class="h-48 relative overflow-hidden" style="background: linear-gradient(135deg, #06b6d4, #3b82f6);">
        <div class="absolute inset-0 flex items-center justify-center"><span class="text-6xl">💻</span>
        </div>
        <div class="absolute top-4 left-4"><span class="category-badge px-3 py-1 rounded-full text-xs font-medium" style="background: rgba(255,255,255,0.2); color: white;"> Teknologi </span>
        </div>
       </div>
       <div class="p-6">
        <h3 class="font-display text-xl font-bold mb-3" style="color: var(--text-color);">Pengenalan Coding untuk Siswa: Membangun Generasi Digital</h3>
        <p class="text-sm mb-4" style="color: rgba(248, 250, 252, 0.6);">Ekstrakurikuler pemrograman yang mengajarkan dasar-dasar coding kepada siswa sejak dini...</p>
        <div class="flex items-center justify-between">
         <div class="flex items-center space-x-2">
          <div class="w-8 h-8 rounded-full flex items-center justify-center" style="background: var(--primary-action);"><span class="text-xs">PK</span>
          </div><span class="text-xs" style="color: rgba(248, 250, 252, 0.6);">Pak Kenan, S.Kom</span>
         </div><span class="text-xs" style="color: var(--secondary-action);">3 Jan 2024</span>
        </div>
       </div>
      </article><!-- Article 6 -->
      <article class="article-card relative rounded-2xl overflow-hidden reveal" style="background: var(--secondary-surface);">
       <div class="h-48 relative overflow-hidden" style="background: linear-gradient(135deg, #84cc16, #22c55e);">
        <div class="absolute inset-0 flex items-center justify-center"><span class="text-6xl">⚽</span>
        </div>
        <div class="absolute top-4 left-4"><span class="category-badge px-3 py-1 rounded-full text-xs font-medium" style="background: rgba(255,255,255,0.2); color: white;"> Olahraga </span>
        </div>
       </div>
       <div class="p-6">
        <h3 class="font-display text-xl font-bold mb-3" style="color: var(--text-color);">Tim Futsal SMPN 1 Tabukan Utara Juara Tingkat Kabupaten</h3>
        <p class="text-sm mb-4" style="color: rgba(248, 250, 252, 0.6);">Perjalanan panjang tim futsal sekolah hingga meraih prestasi gemilang di tingkat kabupaten...</p>
        <div class="flex items-center justify-between">
         <div class="flex items-center space-x-2">
          <div class="w-8 h-8 rounded-full flex items-center justify-center" style="background: var(--primary-action);"><span class="text-xs">DM</span>
          </div><span class="text-xs" style="color: rgba(248, 250, 252, 0.6);">Deni Mamonto</span>
         </div><span class="text-xs" style="color: var(--secondary-action);">1 Jan 2024</span>
        </div>
       </div>
      </article>
     </div><!-- Load More Button -->
     <div class="text-center mt-12"><button class="px-8 py-4 rounded-xl font-semibold transition-all transform hover:scale-105 border pulse-ring" style="border-color: var(--primary-action); color: var(--text-color);"> Muat Lebih Banyak Artikel </button>
     </div>
    </div>
   </section><!-- Categories Section -->
   <section id="kategori" class="py-20 px-4 sm:px-6 lg:px-8" style="background: rgba(30, 41, 59, 0.5);">
    <div class="max-w-7xl mx-auto">
     <div class="text-center mb-12 reveal"><span class="inline-block px-4 py-2 rounded-full text-sm font-medium mb-4" style="background: rgba(59, 130, 246, 0.2); color: var(--secondary-action);"> 🗂️ Kategori Artikel </span>
      <h2 class="font-display text-3xl sm:text-4xl font-bold" style="color: var(--text-color);">Jelajahi Berdasarkan Topik</h2>
     </div>
     <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4">
      <div class="category-badge p-6 rounded-2xl text-center cursor-pointer transition-all reveal" style="background: var(--secondary-surface);"><span class="text-4xl mb-3 block">🔬</span>
       <h3 class="font-semibold mb-1" style="color: var(--text-color);">Sains</h3>
       <p class="text-xs" style="color: rgba(248, 250, 252, 0.6);">24 Artikel</p>
      </div>
      <div class="category-badge p-6 rounded-2xl text-center cursor-pointer transition-all reveal" style="background: var(--secondary-surface);"><span class="text-4xl mb-3 block">📐</span>
       <h3 class="font-semibold mb-1" style="color: var(--text-color);">Matematika</h3>
       <p class="text-xs" style="color: rgba(248, 250, 252, 0.6);">18 Artikel</p>
      </div>
      <div class="category-badge p-6 rounded-2xl text-center cursor-pointer transition-all reveal" style="background: var(--secondary-surface);"><span class="text-4xl mb-3 block">📚</span>
       <h3 class="font-semibold mb-1" style="color: var(--text-color);">Bahasa</h3>
       <p class="text-xs" style="color: rgba(248, 250, 252, 0.6);">32 Artikel</p>
      </div>
      <div class="category-badge p-6 rounded-2xl text-center cursor-pointer transition-all reveal" style="background: var(--secondary-surface);"><span class="text-4xl mb-3 block">🎨</span>
       <h3 class="font-semibold mb-1" style="color: var(--text-color);">Seni Budaya</h3>
       <p class="text-xs" style="color: rgba(248, 250, 252, 0.6);">15 Artikel</p>
      </div>
      <div class="category-badge p-6 rounded-2xl text-center cursor-pointer transition-all reveal" style="background: var(--secondary-surface);"><span class="text-4xl mb-3 block">🌍</span>
       <h3 class="font-semibold mb-1" style="color: var(--text-color);">IPS</h3>
       <p class="text-xs" style="color: rgba(248, 250, 252, 0.6);">21 Artikel</p>
      </div>
      <div class="category-badge p-6 rounded-2xl text-center cursor-pointer transition-all reveal" style="background: var(--secondary-surface);"><span class="text-4xl mb-3 block">💻</span>
       <h3 class="font-semibold mb-1" style="color: var(--text-color);">Teknologi</h3>
       <p class="text-xs" style="color: rgba(248, 250, 252, 0.6);">12 Artikel</p>
      </div>
      <div class="category-badge p-6 rounded-2xl text-center cursor-pointer transition-all reveal" style="background: var(--secondary-surface);"><span class="text-4xl mb-3 block">🌊</span>
       <h3 class="font-semibold mb-1" style="color: var(--text-color);">Lingkungan</h3>
       <p class="text-xs" style="color: rgba(248, 250, 252, 0.6);">16 Artikel</p>
      </div>
      <div class="category-badge p-6 rounded-2xl text-center cursor-pointer transition-all reveal" style="background: var(--secondary-surface);"><span class="text-4xl mb-3 block">⚽</span>
       <h3 class="font-semibold mb-1" style="color: var(--text-color);">Olahraga</h3>
       <p class="text-xs" style="color: rgba(248, 250, 252, 0.6);">14 Artikel</p>
      </div>
     </div>
    </div>
   </section><!-- About Section -->
   <section id="tentang" class="py-20 px-4 sm:px-6 lg:px-8">
    <div class="max-w-7xl mx-auto">
     <div class="grid lg:grid-cols-2 gap-12 items-center">
      <div class="reveal"><span class="inline-block px-4 py-2 rounded-full text-sm font-medium mb-6" style="background: rgba(59, 130, 246, 0.2); color: var(--secondary-action);"> 🏫 Tentang Kami </span>
       <h2 class="font-display text-3xl sm:text-4xl font-bold mb-6" style="color: var(--text-color);">SMP Negeri 1 Tabukan Utara</h2>
       <p class="mb-6" style="color: rgba(248, 250, 252, 0.7);">Portal Jurnal dan Artikel ini merupakan wadah kreativitas dan ekspresi ilmiah bagi seluruh civitas akademika SMP Negeri 1 Tabukan Utara. Kami berkomitmen untuk mengembangkan budaya literasi dan penulisan ilmiah di kalangan siswa.</p>
       <p class="mb-8" style="color: rgba(248, 250, 252, 0.7);">Melalui portal ini, siswa dan guru dapat berbagi pengetahuan, hasil penelitian, dan karya tulis yang bermanfaat bagi pengembangan pendidikan di Kepulauan Sangihe.</p>
       <div class="flex flex-wrap gap-4">
        <div class="flex items-center space-x-2 px-4 py-2 rounded-lg" style="background: var(--secondary-surface);"><span>📍</span> <span class="text-sm">Tabukan Utara, Sangihe</span>
        </div>
        <div class="flex items-center space-x-2 px-4 py-2 rounded-lg" style="background: var(--secondary-surface);"><span>📧</span> <span class="text-sm">info@smpn1tabukan.sch.id</span>
        </div>
       </div>
      </div>
      <div class="reveal">
       <div class="relative">
        <div class="w-full aspect-square rounded-3xl flex items-center justify-center shine" style="background: linear-gradient(135deg, var(--primary-action), #8b5cf6);">
         <div class="text-center p-8">
          <div class="text-8xl mb-6">
           🎓
          </div>
          <h3 class="font-display text-2xl font-bold mb-2" style="color: white;">Visi Kami</h3>
          <p class="text-sm" style="color: rgba(255,255,255,0.8);">Menjadi sekolah unggul yang menghasilkan generasi berilmu, berkarakter, dan berwawasan global</p>
         </div>
        </div><!-- Floating badges -->
        <div class="absolute -top-4 -right-4 w-20 h-20 rounded-2xl flex items-center justify-center float-element" style="background: var(--secondary-surface);"><span class="text-3xl">📖</span>
        </div>
        <div class="absolute -bottom-4 -left-4 w-24 h-24 rounded-2xl flex items-center justify-center float-element" style="background: var(--secondary-surface); animation-delay: -2s;"><span class="text-4xl">✏️</span>
        </div>
       </div>
      </div>
     </div>
    </div>
   </section><!-- Newsletter Section -->
   <section class="py-16 px-4 sm:px-6 lg:px-8" style="background: rgba(30, 41, 59, 0.5);">
    <div class="max-w-3xl mx-auto text-center reveal"><span class="text-5xl mb-4 block">📬</span>
     <h2 class="font-display text-2xl sm:text-3xl font-bold mb-4" style="color: var(--text-color);">Dapatkan Artikel Terbaru</h2>
     <p class="mb-8" style="color: rgba(248, 250, 252, 0.6);">Berlangganan newsletter kami untuk mendapatkan notifikasi artikel terbaru langsung ke email Anda</p>
     <form id="newsletter-form" class="flex flex-col sm:flex-row gap-4 justify-center"><input type="email" placeholder="Masukkan email Anda" class="px-6 py-4 rounded-xl flex-1 max-w-md outline-none focus:ring-2 transition-all" style="background: var(--secondary-surface); border: 1px solid rgba(59, 130, 246, 0.3); color: var(--text-color);"> <button type="submit" class="px-8 py-4 rounded-xl font-semibold transition-all transform hover:scale-105 shine" style="background: linear-gradient(135deg, var(--primary-action), var(--secondary-action)); color: white;"> Berlangganan </button>
     </form>
     <p id="newsletter-message" class="mt-4 text-sm hidden" style="color: var(--secondary-action);"></p>
    </div>
   </section><!-- Footer -->
   <footer class="py-12 px-4 sm:px-6 lg:px-8 border-t" style="border-color: rgba(59, 130, 246, 0.2);">
    <div class="max-w-7xl mx-auto">
     <div class="grid md:grid-cols-4 gap-8 mb-8">
      <div>
       <div class="flex items-center space-x-3 mb-4">
        <div class="w-10 h-10 rounded-full flex items-center justify-center" style="background: linear-gradient(135deg, var(--primary-action), var(--secondary-action));"><span class="text-xl">🏫</span>
        </div><span class="font-display font-bold">SMPN 1 Tabukan Utara</span>
       </div>
       <p class="text-sm" style="color: rgba(248, 250, 252, 0.6);">Portal Jurnal dan Artikel resmi SMP Negeri 1 Tabukan Utara, Kabupaten Kepulauan Sangihe.</p>
      </div>
      <div>
       <h4 class="font-semibold mb-4" style="color: var(--text-color);">Navigasi</h4>
       <ul class="space-y-2">
        <li><a href="#beranda" class="text-sm transition-colors hover:text-blue-400" style="color: rgba(248, 250, 252, 0.6);">Beranda</a></li>
        <li><a href="#artikel" class="text-sm transition-colors hover:text-blue-400" style="color: rgba(248, 250, 252, 0.6);">Artikel</a></li>
        <li><a href="#kategori" class="text-sm transition-colors hover:text-blue-400" style="color: rgba(248, 250, 252, 0.6);">Kategori</a></li>
        <li><a href="#tentang" class="text-sm transition-colors hover:text-blue-400" style="color: rgba(248, 250, 252, 0.6);">Tentang</a></li>
       </ul>
      </div>
      <div>
       <h4 class="font-semibold mb-4" style="color: var(--text-color);">Kategori</h4>
       <ul class="space-y-2">
        <li><a href="#" class="text-sm transition-colors hover:text-blue-400" style="color: rgba(248, 250, 252, 0.6);">Sains</a></li>
        <li><a href="#" class="text-sm transition-colors hover:text-blue-400" style="color: rgba(248, 250, 252, 0.6);">Bahasa</a></li>
        <li><a href="#" class="text-sm transition-colors hover:text-blue-400" style="color: rgba(248, 250, 252, 0.6);">Seni Budaya</a></li>
        <li><a href="#" class="text-sm transition-colors hover:text-blue-400" style="color: rgba(248, 250, 252, 0.6);">Teknologi</a></li>
       </ul>
      </div>
      <div>
       <h4 class="font-semibold mb-4" style="color: var(--text-color);">Kontak</h4>
       <ul class="space-y-2">
        <li class="flex items-center space-x-2 text-sm" style="color: rgba(248, 250, 252, 0.6);"><span>📍</span><span>Tabukan Utara, Sangihe</span></li>
        <li class="flex items-center space-x-2 text-sm" style="color: rgba(248, 250, 252, 0.6);"><span>📞</span><span>(0432) 123456</span></li>
        <li class="flex items-center space-x-2 text-sm" style="color: rgba(248, 250, 252, 0.6);"><span>📧</span><span>info@smpn1tabukan.sch.id</span></li>
       </ul>
      </div>
     </div>
     <div class="pt-8 border-t text-center" style="border-color: rgba(59, 130, 246, 0.2);">
      <p id="footer-text" class="text-sm" style="color: rgba(248, 250, 252, 0.6);">© 2024 SMP Negeri 1 Tabukan Utara. Hak Cipta Dilindungi.</p>
     </div>
    </div>
   </footer>
  </div><!-- Admin Button --> <button class="admin-btn" id="admin-toggle" title="Admin Panel"> 🔐 </button> <!-- Login Modal -->
  <div class="modal-overlay" id="login-modal">
   <div class="modal-content w-full md:w-96 p-8">
    <div class="flex items-center justify-between mb-8">
     <h2 class="font-display text-2xl font-bold" style="color: var(--text-color);">Login Admin</h2><button id="login-close" class="text-2xl cursor-pointer" style="color: rgba(248, 250, 252, 0.6);">×</button>
    </div>
    <form id="login-form" class="space-y-4">
     <div>
      <label class="block text-sm font-medium mb-2" style="color: var(--text-color);">Email</label> <input type="email" id="login-email" placeholder="admin@smpn1tabukan.sch.id" required class="w-full px-4 py-3 rounded-lg outline-none focus:ring-2 focus:ring-blue-400 transition" style="background: var(--secondary-surface); color: var(--text-color); border: 1px solid rgba(59, 130, 246, 0.3);">
     </div>
     <div>
      <label class="block text-sm font-medium mb-2" style="color: var(--text-color);">Password</label> <input type="password" id="login-password" placeholder="••••••••" required class="w-full px-4 py-3 rounded-lg outline-none focus:ring-2 focus:ring-blue-400 transition" style="background: var(--secondary-surface); color: var(--text-color); border: 1px solid rgba(59, 130, 246, 0.3);">
     </div>
     <div id="login-error" class="text-sm p-3 rounded-lg hidden" style="background: rgba(239, 68, 68, 0.1); color: #ef4444;"></div><button type="submit" class="w-full py-3 rounded-lg font-semibold transition-all" style="background: linear-gradient(135deg, var(--primary-action), var(--secondary-action)); color: white;"> Masuk </button>
    </form>
    <p class="text-center text-sm mt-4" style="color: rgba(248, 250, 252, 0.6);">Demo: admin@smpn1tabukan.sch.id / admin123</p>
   </div>
  </div><!-- Admin Dashboard Modal -->
  <div class="modal-overlay" id="admin-modal">
   <div class="modal-content w-full md:w-3xl lg:w-4xl p-8">
    <div class="flex items-center justify-between mb-8">
     <h2 class="font-display text-2xl font-bold" style="color: var(--text-color);">Panel Admin</h2>
     <div class="flex items-center gap-4">
      <span id="admin-user" class="text-sm" style="color: rgba(248, 250, 252, 0.6);"></span> <button id="admin-logout" class="px-4 py-2 rounded-lg font-semibold transition" style="background: rgba(239, 68, 68, 0.1); color: #ef4444;"> Logout </button> <button id="admin-close" class="text-2xl cursor-pointer" style="color: rgba(248, 250, 252, 0.6);">×</button>
     </div>
    </div><!-- Tabs Navigation -->
    <div class="flex gap-2 mb-8 border-b" style="border-color: rgba(59, 130, 246, 0.2);">
     <button class="admin-tab px-4 py-3 font-semibold transition border-b-2" data-tab="website" style="border-color: var(--primary-action); color: var(--text-color);"> 🌐 Website </button> <button class="admin-tab px-4 py-3 font-semibold transition border-b-2" data-tab="articles" style="border-color: transparent; color: rgba(248, 250, 252, 0.6);"> 📰 Artikel </button> <button class="admin-tab px-4 py-3 font-semibold transition border-b-2" data-tab="categories" style="border-color: transparent; color: rgba(248, 250, 252, 0.6);"> 🗂️ Kategori </button> <button class="admin-tab px-4 py-3 font-semibold transition border-b-2" data-tab="accounts" style="border-color: transparent; color: rgba(248, 250, 252, 0.6);"> 👥 Admin </button>
    </div><!-- Website Settings Tab -->
    <div class="admin-tab-content" data-tab="website">
     <div class="space-y-6">
      <!-- School Info Section -->
      <div class="p-6 rounded-xl" style="background: var(--secondary-surface);">
       <h3 class="font-semibold mb-4" style="color: var(--text-color);">ℹ️ Informasi Sekolah</h3>
       <div class="space-y-4">
        <div>
         <label class="block text-sm font-medium mb-2" style="color: rgba(248, 250, 252, 0.8);">Nama Sekolah</label> <input type="text" id="edit-school-name" class="w-full px-4 py-3 rounded-lg outline-none focus:ring-2" style="background: var(--primary-bg); color: var(--text-color); border: 1px solid rgba(59, 130, 246, 0.3);">
        </div>
        <div>
         <label class="block text-sm font-medium mb-2" style="color: rgba(248, 250, 252, 0.8);">Tagline</label> <input type="text" id="edit-tagline" class="w-full px-4 py-3 rounded-lg outline-none focus:ring-2" style="background: var(--primary-bg); color: var(--text-color); border: 1px solid rgba(59, 130, 246, 0.3);">
        </div>
        <div>
         <label class="block text-sm font-medium mb-2" style="color: rgba(248, 250, 252, 0.8);">Email Sekolah</label> <input type="email" id="edit-school-email" class="w-full px-4 py-3 rounded-lg outline-none focus:ring-2" style="background: var(--primary-bg); color: var(--text-color); border: 1px solid rgba(59, 130, 246, 0.3);">
        </div>
        <div class="grid grid-cols-2 gap-4">
         <div>
          <label class="block text-sm font-medium mb-2" style="color: rgba(248, 250, 252, 0.8);">Telepon</label> <input type="tel" id="edit-school-phone" class="w-full px-4 py-3 rounded-lg outline-none focus:ring-2" style="background: var(--primary-bg); color: var(--text-color); border: 1px solid rgba(59, 130, 246, 0.3);">
         </div>
         <div>
          <label class="block text-sm font-medium mb-2" style="color: rgba(248, 250, 252, 0.8);">Alamat</label> <input type="text" id="edit-school-address" class="w-full px-4 py-3 rounded-lg outline-none focus:ring-2" style="background: var(--primary-bg); color: var(--text-color); border: 1px solid rgba(59, 130, 246, 0.3);">
         </div>
        </div>
       </div>
      </div><!-- Hero Section -->
      <div class="p-6 rounded-xl" style="background: var(--secondary-surface);">
       <h3 class="font-semibold mb-4" style="color: var(--text-color);">🎯 Hero Section</h3>
       <div class="space-y-4">
        <div>
         <label class="block text-sm font-medium mb-2" style="color: rgba(248, 250, 252, 0.8);">Judul Utama</label> <input type="text" id="edit-welcome-title" class="w-full px-4 py-3 rounded-lg outline-none focus:ring-2" style="background: var(--primary-bg); color: var(--text-color); border: 1px solid rgba(59, 130, 246, 0.3);">
        </div>
        <div>
         <label class="block text-sm font-medium mb-2" style="color: rgba(248, 250, 252, 0.8);">Deskripsi</label> <textarea id="edit-welcome-desc" rows="4" class="w-full px-4 py-3 rounded-lg outline-none focus:ring-2" style="background: var(--primary-bg); color: var(--text-color); border: 1px solid rgba(59, 130, 246, 0.3); resize: vertical;"></textarea>
        </div>
        <div class="grid grid-cols-2 gap-4">
         <div>
          <label class="block text-sm font-medium mb-2" style="color: rgba(248, 250, 252, 0.8);">Jumlah Artikel</label> <input type="number" id="edit-stat-articles" class="w-full px-4 py-3 rounded-lg outline-none focus:ring-2" style="background: var(--primary-bg); color: var(--text-color); border: 1px solid rgba(59, 130, 246, 0.3);">
         </div>
         <div>
          <label class="block text-sm font-medium mb-2" style="color: rgba(248, 250, 252, 0.8);">Jumlah Penulis</label> <input type="number" id="edit-stat-writers" class="w-full px-4 py-3 rounded-lg outline-none focus:ring-2" style="background: var(--primary-bg); color: var(--text-color); border: 1px solid rgba(59, 130, 246, 0.3);">
         </div>
        </div>
       </div>
      </div><!-- Footer Section -->
      <div class="p-6 rounded-xl" style="background: var(--secondary-surface);">
       <h3 class="font-semibold mb-4" style="color: var(--text-color);">📄 Footer</h3>
       <div class="space-y-4">
        <div>
         <label class="block text-sm font-medium mb-2" style="color: rgba(248, 250, 252, 0.8);">Teks Footer</label> <input type="text" id="edit-footer-text" class="w-full px-4 py-3 rounded-lg outline-none focus:ring-2" style="background: var(--primary-bg); color: var(--text-color); border: 1px solid rgba(59, 130, 246, 0.3);">
        </div>
        <div>
         <label class="block text-sm font-medium mb-2" style="color: rgba(248, 250, 252, 0.8);">Deskripsi Sekolah (Footer)</label> <textarea id="edit-footer-desc" rows="3" class="w-full px-4 py-3 rounded-lg outline-none focus:ring-2" style="background: var(--primary-bg); color: var(--text-color); border: 1px solid rgba(59, 130, 246, 0.3); resize: vertical;"></textarea>
        </div>
       </div>
      </div><!-- Save Button --> <button id="save-website-btn" class="w-full py-3 rounded-lg font-semibold transition" style="background: linear-gradient(135deg, var(--primary-action), var(--secondary-action)); color: white;"> 💾 Simpan Perubahan Website </button>
     </div>
    </div><!-- Articles Tab -->
    <div class="admin-tab-content hidden" data-tab="articles">
     <div class="space-y-4">
      <button id="add-article-btn" class="w-full py-3 rounded-lg font-semibold transition" style="background: rgba(59, 130, 246, 0.2); color: var(--primary-action);"> ➕ Tambah Artikel Baru </button>
      <div id="articles-list" class="space-y-3">
       <!-- Articles will be loaded here -->
      </div>
     </div>
    </div><!-- Categories Tab -->
    <div class="admin-tab-content hidden" data-tab="categories">
     <div class="space-y-4">
      <button id="add-category-btn" class="w-full py-3 rounded-lg font-semibold transition" style="background: rgba(59, 130, 246, 0.2); color: var(--primary-action);"> ➕ Tambah Kategori Baru </button>
      <div id="categories-list" class="space-y-3">
       <!-- Categories will be loaded here -->
      </div>
     </div>
    </div><!-- Admin Accounts Tab -->
    <div class="admin-tab-content hidden" data-tab="accounts">
     <div class="space-y-4">
      <button id="add-admin-btn" class="w-full py-3 rounded-lg font-semibold transition" style="background: rgba(59, 130, 246, 0.2); color: var(--primary-action);"> ➕ Tambah Admin Baru </button>
      <div id="admins-list" class="space-y-3">
       <!-- Admins will be loaded here -->
      </div>
     </div>
    </div>
   </div>
  </div><!-- Add Article Modal -->
  <div class="modal-overlay" id="article-modal">
   <div class="modal-content w-full md:w-2xl p-8">
    <div class="flex items-center justify-between mb-8">
     <h2 class="font-display text-2xl font-bold" style="color: var(--text-color);">Tambah/Edit Artikel</h2><button id="article-close" class="text-2xl cursor-pointer" style="color: rgba(248, 250, 252, 0.6);">×</button>
    </div>
    <form id="article-form" class="space-y-4">
     <div>
      <label class="block text-sm font-medium mb-2" style="color: rgba(248, 250, 252, 0.8);">Judul Artikel</label> <input type="text" id="article-title" placeholder="Judul artikel" required class="w-full px-4 py-3 rounded-lg outline-none focus:ring-2" style="background: var(--secondary-surface); color: var(--text-color); border: 1px solid rgba(59, 130, 246, 0.3);">
     </div>
     <div class="grid grid-cols-2 gap-4">
      <div>
       <label class="block text-sm font-medium mb-2" style="color: rgba(248, 250, 252, 0.8);">Kategori</label> <select id="article-category" class="w-full px-4 py-3 rounded-lg outline-none focus:ring-2" style="background: var(--secondary-surface); color: var(--text-color); border: 1px solid rgba(59, 130, 246, 0.3);"> <option value="Sains">🔬 Sains</option> <option value="Matematika">📐 Matematika</option> <option value="Bahasa">📚 Bahasa</option> <option value="Seni Budaya">🎨 Seni Budaya</option> <option value="IPS">🌍 IPS</option> <option value="Teknologi">💻 Teknologi</option> <option value="Lingkungan">🌊 Lingkungan</option> <option value="Olahraga">⚽ Olahraga</option> </select>
      </div>
      <div>
       <label class="block text-sm font-medium mb-2" style="color: rgba(248, 250, 252, 0.8);">Penulis</label> <input type="text" id="article-author" placeholder="Nama penulis" required class="w-full px-4 py-3 rounded-lg outline-none focus:ring-2" style="background: var(--secondary-surface); color: var(--text-color); border: 1px solid rgba(59, 130, 246, 0.3);">
      </div>
     </div>
     <div>
      <label class="block text-sm font-medium mb-2" style="color: rgba(248, 250, 252, 0.8);">Deskripsi</label> <textarea id="article-description" placeholder="Deskripsi artikel" rows="4" required class="w-full px-4 py-3 rounded-lg outline-none focus:ring-2" style="background: var(--secondary-surface); color: var(--text-color); border: 1px solid rgba(59, 130, 246, 0.3); resize: vertical;"></textarea>
     </div><button type="submit" class="w-full py-3 rounded-lg font-semibold transition" style="background: linear-gradient(135deg, var(--primary-action), var(--secondary-action)); color: white;"> 💾 Simpan Artikel </button>
    </form>
   </div>
  </div><!-- Add Admin Modal -->
  <div class="modal-overlay" id="admin-add-modal">
   <div class="modal-content w-full md:w-96 p-8">
    <div class="flex items-center justify-between mb-8">
     <h2 class="font-display text-2xl font-bold" style="color: var(--text-color);">Tambah Admin</h2><button id="admin-add-close" class="text-2xl cursor-pointer" style="color: rgba(248, 250, 252, 0.6);">×</button>
    </div>
    <form id="admin-add-form" class="space-y-4">
     <div>
      <label class="block text-sm font-medium mb-2" style="color: rgba(248, 250, 252, 0.8);">Email</label> <input type="email" id="new-admin-email" placeholder="admin@example.com" required class="w-full px-4 py-3 rounded-lg outline-none focus:ring-2" style="background: var(--secondary-surface); color: var(--text-color); border: 1px solid rgba(59, 130, 246, 0.3);">
     </div>
     <div>
      <label class="block text-sm font-medium mb-2" style="color: rgba(248, 250, 252, 0.8);">Password</label> <input type="password" id="new-admin-password" placeholder="••••••••" required class="w-full px-4 py-3 rounded-lg outline-none focus:ring-2" style="background: var(--secondary-surface); color: var(--text-color); border: 1px solid rgba(59, 130, 246, 0.3);">
     </div><button type="submit" class="w-full py-3 rounded-lg font-semibold transition" style="background: linear-gradient(135deg, var(--primary-action), var(--secondary-action)); color: white;"> ➕ Tambah Admin </button>
    </form>
   </div>
  </div>
  <script>
    // Initialize Data SDK first
    let currentUser = null;
    let allAdmins = [];
    let adminInitialized = false;

    const dataHandler = {
      onDataChanged(data) {
        if (data && Array.isArray(data)) {
          allAdmins = data.filter(item => item.role === 'admin');
          if (adminInitialized) {
            loadAdminsList();
          }
        }
      }
    };

    // Initialize Data SDK
    (async () => {
      const result = await window.dataSdk.init(dataHandler);
      if (!result.isOk) {
        console.error('Failed to initialize Data SDK');
      }
    })();

    // Default configuration
    const defaultConfig = {
      school_name: 'SMP Negeri 1 Tabukan Utara',
      tagline: 'Unggul dalam Prestasi, Santun dalam Perilaku',
      welcome_title: 'Selamat Datang di Portal',
      footer_text: '© 2024 SMP Negeri 1 Tabukan Utara. Hak Cipta Dilindungi.',
      primary_bg: '#0f172a',
      secondary_surface: '#1e293b',
      text_color: '#f8fafc',
      primary_action: '#3b82f6',
      secondary_action: '#60a5fa',
      font_family: 'Playfair Display',
      font_size: 16
    };

    // Initialize Element SDK
    if (window.elementSdk) {
      window.elementSdk.init({
        defaultConfig,
        onConfigChange: async (config) => {
          // Update school name
          const schoolNameEl = document.getElementById('school-name');
          if (schoolNameEl) {
            schoolNameEl.textContent = config.school_name || defaultConfig.school_name;
          }
          
          // Update tagline
          const taglineEl = document.getElementById('tagline');
          if (taglineEl) {
            taglineEl.textContent = config.tagline || defaultConfig.tagline;
          }
          
          // Update welcome title
          const welcomeEl = document.getElementById('welcome-title');
          if (welcomeEl) {
            const title = config.welcome_title || defaultConfig.welcome_title;
            welcomeEl.innerHTML = `${title}<br><span class="stat-number">Artikel & Jurnal</span>`;
          }
          
          // Update footer text
          const footerEl = document.getElementById('footer-text');
          if (footerEl) {
            footerEl.textContent = config.footer_text || defaultConfig.footer_text;
          }
          
          // Update colors
          const root = document.documentElement;
          root.style.setProperty('--primary-bg', config.primary_bg || defaultConfig.primary_bg);
          root.style.setProperty('--secondary-surface', config.secondary_surface || defaultConfig.secondary_surface);
          root.style.setProperty('--text-color', config.text_color || defaultConfig.text_color);
          root.style.setProperty('--primary-action', config.primary_action || defaultConfig.primary_action);
          root.style.setProperty('--secondary-action', config.secondary_action || defaultConfig.secondary_action);
          
          // Update font family
          const fontFamily = config.font_family || defaultConfig.font_family;
          document.querySelectorAll('.font-display').forEach(el => {
            el.style.fontFamily = `${fontFamily}, Georgia, serif`;
          });
          
          // Update font size
          const baseSize = config.font_size || defaultConfig.font_size;
          document.body.style.fontSize = `${baseSize}px`;
        },
        mapToCapabilities: (config) => ({
          recolorables: [
            {
              get: () => config.primary_bg || defaultConfig.primary_bg,
              set: (value) => { config.primary_bg = value; window.elementSdk.setConfig({ primary_bg: value }); }
            },
            {
              get: () => config.secondary_surface || defaultConfig.secondary_surface,
              set: (value) => { config.secondary_surface = value; window.elementSdk.setConfig({ secondary_surface: value }); }
            },
            {
              get: () => config.text_color || defaultConfig.text_color,
              set: (value) => { config.text_color = value; window.elementSdk.setConfig({ text_color: value }); }
            },
            {
              get: () => config.primary_action || defaultConfig.primary_action,
              set: (value) => { config.primary_action = value; window.elementSdk.setConfig({ primary_action: value }); }
            },
            {
              get: () => config.secondary_action || defaultConfig.secondary_action,
              set: (value) => { config.secondary_action = value; window.elementSdk.setConfig({ secondary_action: value }); }
            }
          ],
          borderables: [],
          fontEditable: {
            get: () => config.font_family || defaultConfig.font_family,
            set: (value) => { config.font_family = value; window.elementSdk.setConfig({ font_family: value }); }
          },
          fontSizeable: {
            get: () => config.font_size || defaultConfig.font_size,
            set: (value) => { config.font_size = value; window.elementSdk.setConfig({ font_size: value }); }
          }
        }),
        mapToEditPanelValues: (config) => new Map([
          ['school_name', config.school_name || defaultConfig.school_name],
          ['tagline', config.tagline || defaultConfig.tagline],
          ['welcome_title', config.welcome_title || defaultConfig.welcome_title],
          ['footer_text', config.footer_text || defaultConfig.footer_text]
        ])
      });
    }

    // Mobile menu toggle
    const mobileMenuBtn = document.getElementById('mobile-menu-btn');
    const mobileMenu = document.getElementById('mobile-menu');
    
    mobileMenuBtn.addEventListener('click', () => {
      mobileMenu.classList.toggle('hidden');
    });

    // Newsletter form
    const newsletterForm = document.getElementById('newsletter-form');
    const newsletterMessage = document.getElementById('newsletter-message');
    
    newsletterForm.addEventListener('submit', (e) => {
      e.preventDefault();
      const email = newsletterForm.querySelector('input[type="email"]').value;
      if (email) {
        newsletterMessage.textContent = '✅ Terima kasih! Anda telah berlangganan newsletter kami.';
        newsletterMessage.classList.remove('hidden');
        newsletterForm.querySelector('input[type="email"]').value = '';
        setTimeout(() => {
          newsletterMessage.classList.add('hidden');
        }, 5000);
      }
    });

    // Scroll reveal animation
    const revealElements = document.querySelectorAll('.reveal');
    
    const revealOnScroll = () => {
      revealElements.forEach(el => {
        const elementTop = el.getBoundingClientRect().top;
        const windowHeight = window.innerHeight;
        
        if (elementTop < windowHeight - 100) {
          el.classList.add('active');
        }
      });
    };

    window.addEventListener('scroll', revealOnScroll);
    revealOnScroll(); // Initial check

    // Smooth scroll for anchor links
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', function (e) {
        e.preventDefault();
        const target = document.querySelector(this.getAttribute('href'));
        if (target) {
          target.scrollIntoView({
            behavior: 'smooth',
            block: 'start'
          });
          // Close mobile menu if open
          mobileMenu.classList.add('hidden');
        }
      });
    });

    // ===== ADMIN SYSTEM =====
    const loginModal = document.getElementById('login-modal');
    const adminModal = document.getElementById('admin-modal');
    const adminToggle = document.getElementById('admin-toggle');
    const loginForm = document.getElementById('login-form');
    const loginCloseBtn = document.getElementById('login-close');
    const adminCloseBtn = document.getElementById('admin-close');
    const adminLogoutBtn = document.getElementById('admin-logout');
    const adminUserSpan = document.getElementById('admin-user');

    // Demo admin account
    const demoAdmin = {
      email: 'admin@smpn1tabukan.sch.id',
      password: 'admin123'
    };

    // Admin Toggle
    adminToggle.addEventListener('click', () => {
      if (currentUser) {
        adminModal.classList.add('active');
      } else {
        loginModal.classList.add('active');
      }
    });

    // Close modals
    loginCloseBtn.addEventListener('click', () => loginModal.classList.remove('active'));
    adminCloseBtn.addEventListener('click', () => adminModal.classList.remove('active'));

    // Login form
    loginForm.addEventListener('submit', async (e) => {
      e.preventDefault();
      const email = document.getElementById('login-email').value;
      const password = document.getElementById('login-password').value;
      const errorDiv = document.getElementById('login-error');

      // Check against demo account or stored admins
      let isValid = false;
      
      if (email === demoAdmin.email && password === demoAdmin.password) {
        isValid = true;
      } else if (allAdmins.length > 0) {
        isValid = allAdmins.some(admin => admin.email === email && admin.password === password);
      }

      if (isValid) {
        currentUser = { email, role: 'admin' };
        adminUserSpan.textContent = `👤 ${email}`;
        loginModal.classList.remove('active');
        adminModal.classList.add('active');
        loadAdminPanel();
        adminInitialized = true;
        loadAdminsList();
      } else {
        errorDiv.textContent = '❌ Email atau password salah!';
        errorDiv.classList.remove('hidden');
        setTimeout(() => errorDiv.classList.add('hidden'), 3000);
      }
    });

    // Logout
    adminLogoutBtn.addEventListener('click', () => {
      currentUser = null;
      adminModal.classList.remove('active');
      loginForm.reset();
      document.getElementById('login-error').classList.add('hidden');
    });

    // Tab switching
    document.querySelectorAll('.admin-tab').forEach(tab => {
      tab.addEventListener('click', () => {
        const tabName = tab.getAttribute('data-tab');
        
        // Update active tab styling
        document.querySelectorAll('.admin-tab').forEach(t => {
          t.style.borderColor = 'transparent';
          t.style.color = 'rgba(248, 250, 252, 0.6)';
        });
        tab.style.borderColor = 'var(--primary-action)';
        tab.style.color = 'var(--text-color)';
        
        // Show/hide content
        document.querySelectorAll('.admin-tab-content').forEach(content => {
          if (content.getAttribute('data-tab') === tabName) {
            content.classList.remove('hidden');
          } else {
            content.classList.add('hidden');
          }
        });
      });
    });

    // Load admin panel with current data
    function loadAdminPanel() {
      document.getElementById('edit-school-name').value = document.getElementById('school-name').textContent;
      document.getElementById('edit-tagline').value = document.getElementById('tagline').textContent;
      document.getElementById('edit-welcome-title').value = 'Selamat Datang di Portal';
      document.getElementById('edit-footer-text').value = document.getElementById('footer-text').textContent;
    }

    // Save website changes
    document.getElementById('save-website-btn').addEventListener('click', async () => {
      const btn = event.target;
      const originalText = btn.textContent;
      btn.textContent = '⏳ Menyimpan...';
      btn.disabled = true;

      const updates = {
        school_name: document.getElementById('edit-school-name').value,
        tagline: document.getElementById('edit-tagline').value,
        welcome_title: document.getElementById('edit-welcome-title').value,
        footer_text: document.getElementById('edit-footer-text').value
      };

      // Update UI immediately
      if (window.elementSdk) {
        await window.elementSdk.setConfig(updates);
      }

      setTimeout(() => {
        btn.textContent = '✅ Tersimpan!';
        btn.style.background = 'rgba(34, 197, 94, 0.3)';
        setTimeout(() => {
          btn.textContent = originalText;
          btn.style.background = '';
          btn.disabled = false;
        }, 2000);
      }, 500);
    });

    // Article management
    document.getElementById('add-article-btn').addEventListener('click', () => {
      document.getElementById('article-form').reset();
      document.getElementById('article-modal').classList.add('active');
    });

    document.getElementById('article-close').addEventListener('click', () => {
      document.getElementById('article-modal').classList.remove('active');
    });

    document.getElementById('article-form').addEventListener('submit', async (e) => {
      e.preventDefault();
      const title = document.getElementById('article-title').value;
      const category = document.getElementById('article-category').value;
      const author = document.getElementById('article-author').value;
      const description = document.getElementById('article-description').value;

      const article = {
        id: Date.now().toString(),
        title,
        category,
        author,
        description,
        created_at: new Date().toISOString()
      };

      const result = await window.dataSdk.create(article);
      if (result.isOk) {
        document.getElementById('article-modal').classList.remove('active');
        showNotification('✅ Artikel berhasil ditambahkan!');
      }
    });

    // Admin accounts management
    document.getElementById('add-admin-btn').addEventListener('click', () => {
      document.getElementById('admin-add-form').reset();
      document.getElementById('admin-add-modal').classList.add('active');
    });

    document.getElementById('admin-add-close').addEventListener('click', () => {
      document.getElementById('admin-add-modal').classList.remove('active');
    });

    document.getElementById('admin-add-form').addEventListener('submit', async (e) => {
      e.preventDefault();
      const email = document.getElementById('new-admin-email').value;
      const password = document.getElementById('new-admin-password').value;

      const admin = {
        id: Date.now().toString(),
        email,
        password,
        role: 'admin',
        created_at: new Date().toISOString()
      };

      const result = await window.dataSdk.create(admin);
      if (result.isOk) {
        document.getElementById('admin-add-modal').classList.remove('active');
        showNotification('✅ Admin berhasil ditambahkan!');
      }
    });

    // Load admins list
    function loadAdminsList() {
      const list = document.getElementById('admins-list');
      list.innerHTML = '';

      allAdmins.forEach(admin => {
        const item = document.createElement('div');
        item.style.cssText = `background: var(--secondary-surface); padding: 1.5rem; border-radius: 0.75rem; display: flex; justify-content: space-between; align-items: center;`;
        item.innerHTML = `
          <div>
            <p style="color: var(--text-color); font-weight: 500;">${admin.email}</p>
            <p style="color: rgba(248, 250, 252, 0.6); font-size: 0.875rem;">ID: ${admin.id}</p>
          </div>
          <button class="delete-admin-btn" data-id="${admin.__backendId}" style="padding: 0.5rem 1rem; background: rgba(239, 68, 68, 0.2); color: #ef4444; border: none; border-radius: 0.5rem; cursor: pointer; font-size: 0.875rem;">
            🗑️ Hapus
          </button>
        `;
        list.appendChild(item);
      });

      document.querySelectorAll('.delete-admin-btn').forEach(btn => {
        btn.addEventListener('click', async (e) => {
          e.preventDefault();
          const id = btn.getAttribute('data-id');
          const admin = allAdmins.find(a => a.__backendId === id);
          
          if (confirm('Hapus admin ini? Tindakan ini tidak dapat dibatalkan.')) {
            const result = await window.dataSdk.delete(admin);
            if (result.isOk) {
              showNotification('✅ Admin berhasil dihapus!');
            }
          }
        });
      });
    }

    // Notification helper
    function showNotification(message) {
      const notif = document.createElement('div');
      notif.style.cssText = `
        position: fixed;
        top: 2rem;
        right: 2rem;
        background: rgba(34, 197, 94, 0.2);
        color: #22c55e;
        padding: 1rem 1.5rem;
        border-radius: 0.75rem;
        border: 1px solid #22c55e;
        z-index: 2000;
        animation: slideUp 0.3s ease;
      `;
      notif.textContent = message;
      document.body.appendChild(notif);
      setTimeout(() => notif.remove(), 3000);
    }

    // Close modals on overlay click
    document.querySelectorAll('.modal-overlay').forEach(overlay => {
      overlay.addEventListener('click', (e) => {
        if (e.target === overlay) {
          overlay.classList.remove('active');
        }
      });
    });

    // Initialize with demo admin on first load
    (async () => {
      await new Promise(resolve => setTimeout(resolve, 500));
    })();
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9d1c557df7d7fd65',t:'MTc3MTc0MDc2OS4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
