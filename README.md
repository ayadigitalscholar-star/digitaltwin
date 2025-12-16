<!doctype html>
<html lang="ar" dir="rtl" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>منصة تكنولوجيا التعليم الرقمي</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <script src="/_sdk/data_sdk.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;800;900&amp;display=swap" rel="stylesheet">
  <style>
    body {
      box-sizing: border-box;
      font-family: 'Tajawal', sans-serif;
    }
    
    :root {
      --primary: #1a237e;
      --primary-light: #283593;
      --secondary: #0d47a1;
      --gold: #c9a227;
      --gold-light: #d4af37;
      --accent: #b71c1c;
      --success: #2e7d32;
      --danger: #c62828;
    }
    
    .official-gradient {
      background: linear-gradient(135deg, #1a237e 0%, #283593 30%, #0d47a1 60%, #1a237e 100%);
    }
    
    .gold-gradient {
      background: linear-gradient(135deg, #d4af37 0%, #f4d03f 50%, #d4af37 100%);
    }
    
    .glass {
      background: rgba(255, 255, 255, 0.1);
      backdrop-filter: blur(20px);
      border: 1px solid rgba(255, 255, 255, 0.2);
    }
    
    .glass-dark {
      background: rgba(0, 0, 0, 0.3);
      backdrop-filter: blur(20px);
      border: 1px solid rgba(255, 255, 255, 0.1);
    }
    
    .card {
      background: white;
      border-radius: 20px;
      box-shadow: 0 10px 40px rgba(0, 0, 0, 0.1);
      transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    }
    
    .card:hover {
      transform: translateY(-5px);
      box-shadow: 0 20px 60px rgba(0, 0, 0, 0.15);
    }
    
    .sidebar-item {
      transition: all 0.3s ease;
      border-right: 4px solid transparent;
      position: relative;
      overflow: hidden;
    }
    
    .sidebar-item::before {
      content: '';
      position: absolute;
      top: 0;
      right: 0;
      width: 0;
      height: 100%;
      background: linear-gradient(90deg, rgba(212, 175, 55, 0.2), transparent);
      transition: width 0.3s ease;
    }
    
    .sidebar-item:hover::before,
    .sidebar-item.active::before {
      width: 100%;
    }
    
    .sidebar-item:hover,
    .sidebar-item.active {
      border-right-color: #d4af37;
      background: rgba(212, 175, 55, 0.1);
    }
    
    .btn-primary {
      background: linear-gradient(135deg, #1a365d 0%, #0c1929 100%);
      transition: all 0.3s ease;
      position: relative;
      overflow: hidden;
    }
    
    .btn-primary::after {
      content: '';
      position: absolute;
      top: -50%;
      left: -50%;
      width: 200%;
      height: 200%;
      background: linear-gradient(45deg, transparent, rgba(255,255,255,0.1), transparent);
      transform: rotate(45deg);
      transition: all 0.5s ease;
    }
    
    .btn-primary:hover::after {
      left: 100%;
    }
    
    .btn-primary:hover {
      transform: translateY(-3px);
      box-shadow: 0 10px 30px rgba(26, 54, 93, 0.4);
    }
    
    .btn-gold {
      background: linear-gradient(135deg, #d4af37 0%, #f4d03f 100%);
      color: #0c1929;
      transition: all 0.3s ease;
    }
    
    .btn-gold:hover {
      transform: translateY(-3px);
      box-shadow: 0 10px 30px rgba(212, 175, 55, 0.4);
    }
    
    .form-input {
      background: #f8fafc;
      border: 2px solid #e2e8f0;
      transition: all 0.3s ease;
    }
    
    .form-input:focus {
      border-color: #1a365d;
      background: white;
      box-shadow: 0 0 0 4px rgba(26, 54, 93, 0.1);
    }
    
    .progress-bar {
      background: #e2e8f0;
      border-radius: 10px;
      overflow: hidden;
    }
    
    .progress-fill {
      background: linear-gradient(90deg, #1a365d 0%, #d4af37 100%);
      height: 100%;
      border-radius: 10px;
      transition: width 0.8s cubic-bezier(0.4, 0, 0.2, 1);
    }
    
    .toast {
      transform: translateX(120%);
      transition: transform 0.5s cubic-bezier(0.68, -0.55, 0.265, 1.55);
    }
    
    .toast.show {
      transform: translateX(0);
    }
    
    .fade-in {
      animation: fadeIn 0.6s ease forwards;
    }
    
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
    
    .slide-up {
      animation: slideUp 0.5s ease forwards;
    }
    
    @keyframes slideUp {
      from { opacity: 0; transform: translateY(40px); }
      to { opacity: 1; transform: translateY(0); }
    }
    
    .pulse-glow {
      animation: pulseGlow 2s ease-in-out infinite;
    }
    
    @keyframes pulseGlow {
      0%, 100% { box-shadow: 0 0 20px rgba(212, 175, 55, 0.3); }
      50% { box-shadow: 0 0 40px rgba(212, 175, 55, 0.6); }
    }
    
    .float {
      animation: float 4s ease-in-out infinite;
    }
    
    @keyframes float {
      0%, 100% { transform: translateY(0) rotate(0deg); }
      50% { transform: translateY(-15px) rotate(2deg); }
    }
    
    .rotate-slow {
      animation: rotateSlow 20s linear infinite;
    }
    
    @keyframes rotateSlow {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
    }
    
    .gradient-text {
      background: linear-gradient(135deg, #d4af37, #f4d03f, #d4af37);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
    
    .face-scanner {
      position: relative;
      overflow: hidden;
    }
    
    .face-scanner::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      height: 3px;
      background: linear-gradient(90deg, transparent, #d4af37, transparent);
      animation: scan 2s ease-in-out infinite;
    }
    
    @keyframes scan {
      0%, 100% { top: 0; opacity: 1; }
      50% { top: calc(100% - 3px); opacity: 0.5; }
    }
    
    .face-frame {
      position: absolute;
      width: 70%;
      height: 80%;
      top: 10%;
      left: 15%;
      border: 3px dashed rgba(212, 175, 55, 0.5);
      border-radius: 50%;
    }
    
    .face-corner {
      position: absolute;
      width: 30px;
      height: 30px;
      border-color: #d4af37;
      border-style: solid;
    }
    
    .face-corner.tl { top: 10%; left: 15%; border-width: 4px 0 0 4px; border-radius: 10px 0 0 0; }
    .face-corner.tr { top: 10%; right: 15%; border-width: 4px 4px 0 0; border-radius: 0 10px 0 0; }
    .face-corner.bl { bottom: 10%; left: 15%; border-width: 0 0 4px 4px; border-radius: 0 0 0 10px; }
    .face-corner.br { bottom: 10%; right: 15%; border-width: 0 4px 4px 0; border-radius: 0 0 10px 0; }
    
    .status-dot {
      animation: statusPulse 2s ease-in-out infinite;
    }
    
    @keyframes statusPulse {
      0%, 100% { opacity: 1; transform: scale(1); }
      50% { opacity: 0.5; transform: scale(1.2); }
    }
    
    .loading-ring {
      width: 60px;
      height: 60px;
      border: 4px solid rgba(212, 175, 55, 0.2);
      border-top-color: #d4af37;
      border-radius: 50%;
      animation: spin 1s linear infinite;
    }
    
    @keyframes spin {
      to { transform: rotate(360deg); }
    }
    
    .modal-overlay {
      background: rgba(0, 0, 0, 0.8);
      backdrop-filter: blur(10px);
    }
    
    .quiz-option {
      transition: all 0.3s ease;
    }
    
    .quiz-option:hover {
      transform: translateX(-10px);
    }
    
    .quiz-option.correct {
      background: linear-gradient(135deg, #dcfce7, #bbf7d0) !important;
      border-color: #22c55e !important;
    }
    
    .quiz-option.wrong {
      background: linear-gradient(135deg, #fee2e2, #fecaca) !important;
      border-color: #ef4444 !important;
    }
    
    .badge-shine {
      position: relative;
      overflow: hidden;
    }
    
    .badge-shine::after {
      content: '';
      position: absolute;
      top: -50%;
      left: -50%;
      width: 200%;
      height: 200%;
      background: linear-gradient(45deg, transparent 30%, rgba(255,255,255,0.3) 50%, transparent 70%);
      animation: shine 3s ease-in-out infinite;
    }
    
    @keyframes shine {
      0% { transform: translateX(-100%) rotate(45deg); }
      100% { transform: translateX(100%) rotate(45deg); }
    }
    
    .stat-card {
      position: relative;
      overflow: hidden;
    }
    
    .stat-card::before {
      content: '';
      position: absolute;
      top: -50%;
      right: -50%;
      width: 100%;
      height: 100%;
      background: radial-gradient(circle, currentColor 0%, transparent 70%);
      opacity: 0.05;
    }
    
    .countdown {
      font-variant-numeric: tabular-nums;
      font-feature-settings: "tnum";
    }
    
    .reminder-urgent { border-right: 5px solid #ef4444; }
    .reminder-today { border-right: 5px solid #f59e0b; }
    .reminder-upcoming { border-right: 5px solid #3b82f6; }
    
    .file-card:hover {
      transform: translateY(-5px) scale(1.02);
    }
    
    .tab-active {
      background: linear-gradient(135deg, #1a365d, #0c1929);
      color: white;
    }
    
    ::-webkit-scrollbar {
      width: 8px;
      height: 8px;
    }
    
    ::-webkit-scrollbar-track {
      background: #f1f5f9;
      border-radius: 10px;
    }
    
    ::-webkit-scrollbar-thumb {
      background: linear-gradient(180deg, #1a365d, #d4af37);
      border-radius: 10px;
    }
    
    .video-container {
      position: relative;
      border-radius: 20px;
      overflow: hidden;
    }
    
    video {
      transform: scaleX(-1);
    }
    
    .capture-flash {
      animation: flash 0.3s ease;
    }
    
    @keyframes flash {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.3; }
    }

    .shake {
      animation: shake 0.5s ease;
    }

    @keyframes shake {
      0%, 100% { transform: translateX(0); }
      25% { transform: translateX(-10px); }
      75% { transform: translateX(10px); }
    }

    .success-checkmark {
      animation: checkmark 0.5s ease;
    }

    @keyframes checkmark {
      0% { transform: scale(0); }
      50% { transform: scale(1.2); }
      100% { transform: scale(1); }
    }
  </style>
  <style>@view-transition { navigation: auto; }</style>
 </head>
 <body class="h-full overflow-auto bg-slate-100"><!-- شاشة التحميل الأولية -->
  <div id="loadingScreen" class="fixed inset-0 official-gradient flex items-center justify-center z-50">
   <div class="text-center">
    <div class="relative w-32 h-32 mx-auto mb-8">
     <div class="absolute inset-0 border-4 border-amber-400/30 rounded-full"></div>
     <div class="absolute inset-0 border-4 border-transparent border-t-amber-400 rounded-full animate-spin"></div>
     <div class="absolute inset-4 border-4 border-transparent border-t-amber-300 rounded-full animate-spin" style="animation-direction: reverse; animation-duration: 1.5s;"></div>
     <div class="absolute inset-0 flex items-center justify-center"><span class="text-4xl">🎓</span>
     </div>
    </div>
    <h2 class="text-white text-2xl font-bold mb-2">جاري تحميل المنصة</h2>
    <p class="text-amber-300">منصة تكنولوجيا التعليم الرقمي</p>
    <div class="mt-6 w-64 mx-auto">
     <div class="progress-bar h-2">
      <div class="progress-fill" id="loadingProgress" style="width: 0%"></div>
     </div>
    </div>
   </div>
  </div><!-- ==================== شاشة تسجيل الدخول ==================== -->
  <main id="loginScreen" class="min-h-full flex items-center justify-center p-4 official-gradient relative overflow-hidden hidden"><!-- خلفية زخرفية -->
   <div class="absolute inset-0 overflow-hidden pointer-events-none">
    <div class="absolute top-20 right-20 w-96 h-96 bg-amber-500/10 rounded-full blur-3xl"></div>
    <div class="absolute bottom-20 left-20 w-80 h-80 bg-blue-500/10 rounded-full blur-3xl"></div>
    <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[800px] h-[800px] opacity-5">
     <svg viewbox="0 0 200 200" class="w-full h-full rotate-slow"><defs>
       <pattern id="grid" width="20" height="20" patternunits="userSpaceOnUse">
        <path d="M 20 0 L 0 0 0 20" fill="none" stroke="#d4af37" stroke-width="0.5" />
       </pattern>
      </defs> <rect width="100%" height="100%" fill="url(#grid)" />
     </svg>
    </div>
   </div>
   <div class="w-full max-w-lg relative z-10"><!-- شعار الجامعة -->
    <header class="text-center text-white mb-8">
     <div class="w-32 h-32 mx-auto mb-6 rounded-full bg-gradient-to-br from-amber-400 via-yellow-400 to-amber-500 p-1.5 pulse-glow shadow-2xl">
      <div class="w-full h-full rounded-full bg-gradient-to-br from-[#1a237e] to-[#283593] flex items-center justify-center relative overflow-hidden">
       <div class="absolute inset-0 bg-[url('data:image/svg+xml,%3Csvg width=\" 60\ height="\&quot;60\&quot;" viewbox="\&quot;0" 0 60 xmlns="\&quot;http://www.w3.org/2000/svg\&quot;%3E%3Cg" fill="\&quot;none\&quot;" fill-rule="\&quot;evenodd\&quot;%3E%3Cg" fill-opacity="\&quot;0.1\&quot;%3E%3Cpath" d="\&quot;M36" 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30v0h-2v4h-4v2h4v4h2v6h4v4h-4zm6 34v-4h4v4h0v2h4v4h2v-4h4v-2h6zm6 4v0h4v4h0v2h4v4h2v6h4v4h6z\ %3e%3c g%3e%3c svg%3e)] opacity-30></div>
       <svg class="w-20 h-20 text-amber-400 relative z-10" viewbox="0 0 100 100" fill="currentColor"><path d="M50 5L90 25V45L50 65L10 45V25L50 5Z" fill="none" stroke="currentColor" stroke-width="3" /> <circle cx="50" cy="35" r="14" fill="currentColor" /> <path d="M50 65V92M25 85H75" stroke="currentColor" stroke-width="5" stroke-linecap="round" /> <path d="M20 25L50 40L80 25" stroke="currentColor" stroke-width="2" opacity="0.6" /> <circle cx="50" cy="92" r="4" fill="currentColor" />
       </svg>
      </div>
     </div>
     <h1 id="universityName" class="text-3xl font-bold mb-2">جامعة جنوب الوادي</h1>
     <p id="facultyName" class="text-amber-300 text-lg mb-1">كلية التربية النوعية</p>
     <p class="text-blue-200 text-sm">قسم تكنولوجيا التعليم</p>
     <div class="mt-4 inline-block px-6 py-3 glass rounded-full">
      <h2 id="platformTitle" class="text-xl gradient-text font-bold">منصة التعليم الرقمي</h2>
     </div>
    </header><!-- بطاقة تسجيل الدخول -->
    <div class="card p-8 relative overflow-hidden">
     <div class="absolute top-0 left-0 right-0 h-2 gold-gradient"></div><!-- تبويبات -->
     <nav class="flex mb-8 bg-gray-100 rounded-2xl p-1.5"><button onclick="showLoginTab('login')" id="loginTabBtn" class="flex-1 py-3 rounded-xl font-bold text-sm transition-all tab-active"> تسجيل الدخول </button> <button onclick="showLoginTab('register')" id="registerTabBtn" class="flex-1 py-3 rounded-xl font-bold text-sm transition-all text-gray-500"> إنشاء حساب </button>
     </nav><!-- نموذج تسجيل الدخول -->
     <form id="loginForm" class="space-y-5">
      <div><label for="loginId" class="block text-sm font-bold text-gray-700 mb-2"> <span class="inline-block ml-2">👤</span>الرقم الجامعي / رقم الموظف </label> <input type="text" id="loginId" placeholder="مثال: 2024001234" class="w-full p-4 form-input rounded-xl focus:outline-none" required>
      </div>
      <div><label for="loginPassword" class="block text-sm font-bold text-gray-700 mb-2"> <span class="inline-block ml-2">🔒</span>كلمة المرور </label>
       <div class="relative"><input type="password" id="loginPassword" placeholder="••••••••" class="w-full p-4 form-input rounded-xl focus:outline-none pl-12" required> <button type="button" onclick="togglePassword('loginPassword', this)" class="absolute left-4 top-1/2 -translate-y-1/2 text-gray-400 hover:text-gray-600 text-xl"> 👁️ </button>
       </div>
      </div><!-- خيار الدخول بالوجه -->
      <div class="flex items-center justify-center"><button type="button" onclick="showFaceLogin()" class="flex items-center gap-3 px-6 py-3 bg-gradient-to-r from-purple-100 to-indigo-100 text-purple-700 rounded-xl font-bold hover:shadow-lg transition-all"> <span class="text-2xl">📷</span> <span>الدخول ببصمة الوجه</span> </button>
      </div><button type="submit" id="loginBtn" class="w-full py-4 btn-primary text-white rounded-xl font-bold text-lg flex items-center justify-center gap-3"> <span>تسجيل الدخول</span> <span>←</span> </button>
     </form><!-- نموذج إنشاء حساب -->
     <form id="registerForm" class="space-y-4 hidden">
      <div class="grid grid-cols-2 gap-4">
       <div class="col-span-2"><label for="regRole" class="block text-sm font-bold text-gray-700 mb-2">نوع الحساب</label> <select id="regRole" class="w-full p-4 form-input rounded-xl focus:outline-none" required> <option value="">اختر نوع الحساب</option> <option value="student">👨‍🎓 طالب</option> <option value="teacher">👨‍🏫 عضو هيئة تدريس</option> </select>
       </div>
       <div class="col-span-2"><label for="regName" class="block text-sm font-bold text-gray-700 mb-2">الاسم الكامل</label> <input type="text" id="regName" placeholder="الاسم ثلاثي" class="w-full p-4 form-input rounded-xl focus:outline-none" required>
       </div>
       <div><label for="regId" class="block text-sm font-bold text-gray-700 mb-2">الرقم الجامعي</label> <input type="text" id="regId" placeholder="2024001234" class="w-full p-4 form-input rounded-xl focus:outline-none" required>
       </div>
       <div><label for="regEmail" class="block text-sm font-bold text-gray-700 mb-2">البريد الإلكتروني</label> <input type="email" id="regEmail" placeholder="example@edu.eg" class="w-full p-4 form-input rounded-xl focus:outline-none" required>
       </div>
       <div class="col-span-2"><label for="regPassword" class="block text-sm font-bold text-gray-700 mb-2">كلمة المرور</label>
        <div class="relative"><input type="password" id="regPassword" placeholder="6 أحرف على الأقل" class="w-full p-4 form-input rounded-xl focus:outline-none pl-12" required minlength="6"> <button type="button" onclick="togglePassword('regPassword', this)" class="absolute left-4 top-1/2 -translate-y-1/2 text-gray-400 text-xl">👁️</button>
        </div>
       </div>
       <div class="col-span-2 hidden" id="studentFields"><label for="regLevel" class="block text-sm font-bold text-gray-700 mb-2">الفرقة الدراسية</label> <select id="regLevel" class="w-full p-4 form-input rounded-xl focus:outline-none"> <option value="1">الفرقة الأولى</option> <option value="2">الفرقة الثانية</option> <option value="3">الفرقة الثالثة</option> <option value="4">الفرقة الرابعة</option> </select>
       </div>
      </div><!-- تسجيل بصمة الوجه -->
      <div class="p-5 bg-gradient-to-br from-purple-50 to-indigo-50 rounded-2xl border-2 border-dashed border-purple-200">
       <div class="text-center"><span class="text-4xl block mb-3">📷</span>
        <h4 class="font-bold text-purple-800 mb-2">تسجيل بصمة الوجه (اختياري)</h4>
        <p class="text-sm text-purple-600 mb-4">للدخول السريع بدون كلمة مرور</p><button type="button" onclick="showFaceRegistration()" class="px-6 py-3 bg-purple-600 text-white rounded-xl font-bold hover:bg-purple-700 transition-all"> تسجيل بصمة الوجه </button>
        <p id="faceRegStatus" class="text-sm text-green-600 mt-3 hidden">✅ تم تسجيل بصمة الوجه بنجاح</p>
       </div>
      </div><button type="submit" id="registerBtn" class="w-full py-4 btn-gold rounded-xl font-bold text-lg flex items-center justify-center gap-3"> <span>إنشاء الحساب</span> <span>✨</span> </button>
     </form>
     <p id="authError" class="text-red-500 text-sm text-center mt-4 hidden font-bold"></p>
    </div>
    <footer class="text-center mt-6">
     <p class="text-white/50 text-sm">© 2025 جميع الحقوق محفوظة - كلية التربية النوعية</p>
    </footer>
   </div>
  </main><!-- ==================== Modal بصمة الوجه ==================== -->
  <div id="faceModal" class="fixed inset-0 modal-overlay hidden items-center justify-center z-50 p-4">
   <div class="bg-white rounded-3xl w-full max-w-lg shadow-2xl overflow-hidden">
    <div class="bg-gradient-to-r from-purple-600 to-indigo-600 text-white p-6">
     <div class="flex items-center justify-between">
      <div>
       <h3 class="font-bold text-xl" id="faceModalTitle">بصمة الوجه</h3>
       <p class="text-purple-200 text-sm mt-1" id="faceModalSubtitle">ضع وجهك داخل الإطار</p>
      </div><button onclick="closeFaceModal()" class="p-2 hover:bg-white/20 rounded-xl transition-colors">
       <svg class="w-6 h-6" fill="none" stroke="currentColor" viewbox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
       </svg></button>
     </div>
    </div>
    <div class="p-6">
     <div class="video-container bg-gray-900 rounded-2xl overflow-hidden relative aspect-[4/3]">
      <video id="faceVideo" autoplay playsinline class="w-full h-full object-cover"></video>
      <canvas id="faceCanvas" class="hidden"></canvas><!-- إطار الوجه -->
      <div class="absolute inset-0 face-scanner">
       <div class="face-corner tl"></div>
       <div class="face-corner tr"></div>
       <div class="face-corner bl"></div>
       <div class="face-corner br"></div>
      </div><!-- حالة المسح -->
      <div id="scanStatus" class="absolute bottom-4 left-4 right-4 text-center">
       <div class="glass-dark rounded-xl px-4 py-3">
        <p class="text-white font-bold" id="scanStatusText">جاري تشغيل الكاميرا...</p>
       </div>
      </div>
     </div>
     <div class="mt-6 space-y-3"><button onclick="captureFace()" id="captureBtn" class="w-full py-4 btn-primary text-white rounded-xl font-bold text-lg flex items-center justify-center gap-3 disabled:opacity-50" disabled> <span class="text-2xl">📸</span> <span id="captureBtnText">التقاط صورة الوجه</span> </button>
      <div id="faceActions" class="hidden space-y-3"><button onclick="confirmFace()" class="w-full py-4 bg-green-500 hover:bg-green-600 text-white rounded-xl font-bold text-lg flex items-center justify-center gap-3"> <span>✅</span> <span>تأكيد</span> </button> <button onclick="retakeFace()" class="w-full py-3 bg-gray-200 text-gray-700 rounded-xl font-bold flex items-center justify-center gap-3"> <span>🔄</span> <span>إعادة التقاط</span> </button>
      </div>
     </div>
     <p class="text-center text-gray-500 text-sm mt-4">💡 تأكد من إضاءة جيدة ووجهك واضح داخل الإطار</p>
    </div>
   </div>
  </div><!-- ==================== المنصة الرئيسية ==================== -->
  <div id="mainPlatform" class="h-full hidden"><!-- الشريط الجانبي -->
   <aside id="sidebar" class="fixed right-0 top-0 h-full w-72 bg-gradient-to-b from-[#1a237e] via-[#283593] to-[#1a237e] z-40 shadow-2xl overflow-y-auto"><!-- معلومات المستخدم -->
    <div class="p-6 border-b border-white/10">
     <div class="flex items-center gap-4">
      <div class="relative">
       <div class="w-16 h-16 rounded-2xl bg-gradient-to-br from-amber-400 to-amber-600 p-0.5">
        <div class="w-full h-full rounded-2xl bg-slate-800 flex items-center justify-center"><span id="sidebarAvatar" class="text-3xl">🎓</span>
        </div>
       </div>
       <div class="absolute -bottom-1 -right-1 w-5 h-5 bg-green-500 rounded-full border-2 border-slate-800 status-dot"></div>
      </div>
      <div class="flex-1 min-w-0">
       <h3 id="sidebarName" class="font-bold text-white truncate">اسم المستخدم</h3>
       <p id="sidebarRole" class="text-sm text-blue-300">الدور</p>
      </div>
     </div><!-- إحصائيات الطالب -->
     <div id="studentSidebarStats" class="mt-5 p-4 bg-white/5 rounded-2xl hidden">
      <div class="flex items-center justify-between text-sm mb-3"><span class="text-gray-400">المستوى</span> <span class="text-amber-400 font-bold" id="userLevel">1</span>
      </div>
      <div class="progress-bar h-3 mb-2">
       <div class="progress-fill" id="xpProgress" style="width: 0%"></div>
      </div>
      <div class="flex items-center justify-between text-xs text-gray-500"><span id="currentXP">0 XP</span> <span>1000 XP</span>
      </div>
      <div class="grid grid-cols-2 gap-3 mt-4">
       <div class="text-center p-3 bg-white/5 rounded-xl"><span class="text-xl">⭐</span>
        <p class="text-amber-400 font-bold mt-1" id="sidebarPoints">0</p>
        <p class="text-xs text-gray-500">نقطة</p>
       </div>
       <div class="text-center p-3 bg-white/5 rounded-xl"><span class="text-xl">🔥</span>
        <p class="text-orange-400 font-bold mt-1" id="sidebarStreak">0</p>
        <p class="text-xs text-gray-500">يوم متتالي</p>
       </div>
      </div>
     </div>
    </div><!-- القائمة -->
    <nav class="p-4">
     <p class="text-xs text-gray-500 mb-4 px-3 font-bold tracking-wider">القائمة الرئيسية</p>
     <div class="space-y-2" id="sidebarMenu"></div>
    </nav><!-- تسجيل الخروج -->
    <div class="absolute bottom-0 left-0 right-0 p-4 border-t border-white/10 bg-[#1a237e]/50"><button onclick="logout()" class="w-full p-4 rounded-xl text-right flex items-center gap-4 hover:bg-red-500/20 text-red-400 transition-all group"> <span class="text-xl group-hover:scale-110 transition-transform">🚪</span> <span class="font-bold">تسجيل الخروج</span> </button>
    </div>
   </aside><!-- المحتوى الرئيسي -->
   <div class="mr-72 min-h-full"><!-- الهيدر -->
    <header class="bg-gradient-to-l from-[#1a237e] via-[#283593] to-[#0d47a1] text-white p-6 sticky top-0 z-30 shadow-xl">
     <div class="absolute bottom-0 left-0 right-0 h-1 gold-gradient"></div>
     <div class="flex items-center justify-between">
      <div>
       <h1 id="pageTitle" class="text-2xl font-bold">لوحة التحكم</h1>
       <p class="text-blue-200 mt-1">الفصل الدراسي الأول 2025/2026</p>
      </div>
      <div class="flex items-center gap-6">
       <div id="headerDateTime" class="text-left hidden md:block">
        <p class="text-xs text-blue-200" id="headerDate">التاريخ</p>
        <p class="text-xl font-bold countdown" id="headerTime">00:00:00</p>
       </div>
      </div>
     </div>
    </header><!-- المحتوى -->
    <main class="p-6" id="mainContent"><!-- يتم تحميله ديناميكياً -->
    </main>
   </div>
  </div><!-- ==================== Modal إضافة محتوى ==================== -->
  <div id="addContentModal" class="fixed inset-0 modal-overlay hidden items-center justify-center z-50 p-4">
   <div class="bg-white rounded-3xl w-full max-w-lg shadow-2xl overflow-hidden">
    <div class="bg-gradient-to-r from-blue-600 to-indigo-600 text-white p-6">
     <div class="flex items-center justify-between">
      <h3 class="font-bold text-xl">📤 إضافة محتوى جديد</h3><button onclick="closeModal('addContentModal')" class="p-2 hover:bg-white/20 rounded-xl">✕</button>
     </div>
    </div>
    <form id="contentForm" class="p-6 space-y-5">
     <div><label for="contentCourse" class="block text-sm font-bold text-gray-700 mb-2">المقرر</label> <select id="contentCourse" class="w-full p-4 form-input rounded-xl focus:outline-none" required></select>
     </div>
     <div><label for="contentType" class="block text-sm font-bold text-gray-700 mb-2">نوع المحتوى</label> <select id="contentType" class="w-full p-4 form-input rounded-xl focus:outline-none" required> <option value="video">🎥 فيديو (YouTube)</option> <option value="pdf">📄 ملف PDF</option> <option value="link">🔗 رابط خارجي</option> <option value="assignment">📝 تكليف / واجب</option> </select>
     </div>
     <div><label for="contentTitle" class="block text-sm font-bold text-gray-700 mb-2">العنوان</label> <input type="text" id="contentTitle" placeholder="عنوان المحتوى" class="w-full p-4 form-input rounded-xl focus:outline-none" required>
     </div>
     <div><label for="contentUrl" class="block text-sm font-bold text-gray-700 mb-2">الرابط</label> <input type="url" id="contentUrl" placeholder="https://..." class="w-full p-4 form-input rounded-xl focus:outline-none" required>
     </div>
     <div><label for="contentDesc" class="block text-sm font-bold text-gray-700 mb-2">الوصف (اختياري)</label> <textarea id="contentDesc" rows="3" placeholder="وصف مختصر..." class="w-full p-4 form-input rounded-xl focus:outline-none resize-none"></textarea>
     </div><button type="submit" class="w-full py-4 btn-primary text-white rounded-xl font-bold text-lg"> إضافة المحتوى </button>
    </form>
   </div>
  </div><!-- ==================== Modal إضافة تذكير ==================== -->
  <div id="addReminderModal" class="fixed inset-0 modal-overlay hidden items-center justify-center z-50 p-4">
   <div class="bg-white rounded-3xl w-full max-w-lg shadow-2xl overflow-hidden">
    <div class="bg-gradient-to-r from-amber-500 to-orange-500 text-white p-6">
     <div class="flex items-center justify-between">
      <h3 class="font-bold text-xl">⏰ إضافة تذكير</h3><button onclick="closeModal('addReminderModal')" class="p-2 hover:bg-white/20 rounded-xl">✕</button>
     </div>
    </div>
    <form id="reminderForm" class="p-6 space-y-5">
     <div><label for="reminderTitle" class="block text-sm font-bold text-gray-700 mb-2">عنوان التذكير</label> <input type="text" id="reminderTitle" placeholder="مثال: تسليم البحث" class="w-full p-4 form-input rounded-xl focus:outline-none" required>
     </div>
     <div><label for="reminderCourse" class="block text-sm font-bold text-gray-700 mb-2">المقرر (اختياري)</label> <select id="reminderCourse" class="w-full p-4 form-input rounded-xl focus:outline-none"> <option value="">عام</option> </select>
     </div>
     <div><label for="reminderDeadline" class="block text-sm font-bold text-gray-700 mb-2">الموعد النهائي</label> <input type="datetime-local" id="reminderDeadline" class="w-full p-4 form-input rounded-xl focus:outline-none" required>
     </div>
     <div><label for="reminderPriority" class="block text-sm font-bold text-gray-700 mb-2">الأولوية</label> <select id="reminderPriority" class="w-full p-4 form-input rounded-xl focus:outline-none" required> <option value="urgent">🔴 عاجل</option> <option value="today">🟡 مهم</option> <option value="upcoming">🔵 عادي</option> </select>
     </div><button type="submit" class="w-full py-4 btn-gold rounded-xl font-bold text-lg"> إضافة التذكير </button>
    </form>
   </div>
  </div><!-- ==================== Modal الدرجات ==================== -->
  <div id="addGradeModal" class="fixed inset-0 modal-overlay hidden items-center justify-center z-50 p-4">
   <div class="bg-white rounded-3xl w-full max-w-lg shadow-2xl overflow-hidden">
    <div class="bg-gradient-to-r from-green-600 to-emerald-600 text-white p-6">
     <div class="flex items-center justify-between">
      <h3 class="font-bold text-xl">📊 إضافة درجة</h3><button onclick="closeModal('addGradeModal')" class="p-2 hover:bg-white/20 rounded-xl">✕</button>
     </div>
    </div>
    <form id="gradeForm" class="p-6 space-y-5">
     <div><label for="gradeStudent" class="block text-sm font-bold text-gray-700 mb-2">الطالب</label> <select id="gradeStudent" class="w-full p-4 form-input rounded-xl focus:outline-none" required></select>
     </div>
     <div><label for="gradeCourse" class="block text-sm font-bold text-gray-700 mb-2">المقرر</label> <select id="gradeCourse" class="w-full p-4 form-input rounded-xl focus:outline-none" required></select>
     </div>
     <div><label for="gradeType" class="block text-sm font-bold text-gray-700 mb-2">نوع الدرجة</label> <select id="gradeType" class="w-full p-4 form-input rounded-xl focus:outline-none" required> <option value="quiz">اختبار قصير</option> <option value="midterm">اختبار منتصف الفصل</option> <option value="final">اختبار نهائي</option> <option value="assignment">واجب / تكليف</option> <option value="participation">مشاركة</option> </select>
     </div>
     <div><label for="gradeValue" class="block text-sm font-bold text-gray-700 mb-2">الدرجة</label> <input type="number" id="gradeValue" min="0" max="100" placeholder="0 - 100" class="w-full p-4 form-input rounded-xl focus:outline-none" required>
     </div><button type="submit" class="w-full py-4 bg-green-600 hover:bg-green-700 text-white rounded-xl font-bold text-lg"> حفظ الدرجة </button>
    </form>
   </div>
  </div><!-- ==================== Modal المكافآت ==================== -->
  <div id="bonusModal" class="fixed inset-0 modal-overlay hidden items-center justify-center z-50 p-4">
   <div class="bg-white rounded-3xl w-full max-w-md shadow-2xl overflow-hidden">
    <div class="bg-gradient-to-r from-amber-500 to-yellow-500 text-white p-6">
     <div class="flex items-center justify-between">
      <h3 class="font-bold text-xl">⭐ إضافة نقاط مكافأة</h3><button onclick="closeModal('bonusModal')" class="p-2 hover:bg-white/20 rounded-xl">✕</button>
     </div>
    </div>
    <form id="bonusForm" class="p-6 space-y-5">
     <div class="text-center p-4 bg-gradient-to-br from-blue-50 to-indigo-50 rounded-2xl"><span class="text-4xl block mb-2">🎓</span>
      <p class="font-bold text-lg" id="bonusStudentName">اسم الطالب</p><input type="hidden" id="bonusStudentId">
     </div>
     <div><label for="bonusAmount" class="block text-sm font-bold text-gray-700 mb-2">عدد النقاط</label>
      <div class="grid grid-cols-4 gap-2 mb-3"><button type="button" onclick="setBonusAmount(50)" class="py-3 bg-amber-100 text-amber-700 rounded-xl font-bold hover:bg-amber-200">+50</button> <button type="button" onclick="setBonusAmount(100)" class="py-3 bg-amber-100 text-amber-700 rounded-xl font-bold hover:bg-amber-200">+100</button> <button type="button" onclick="setBonusAmount(250)" class="py-3 bg-amber-100 text-amber-700 rounded-xl font-bold hover:bg-amber-200">+250</button> <button type="button" onclick="setBonusAmount(500)" class="py-3 bg-amber-100 text-amber-700 rounded-xl font-bold hover:bg-amber-200">+500</button>
      </div><input type="number" id="bonusAmount" min="1" max="10000" placeholder="أو أدخل رقماً" class="w-full p-4 form-input rounded-xl focus:outline-none" required>
     </div>
     <div><label for="bonusReason" class="block text-sm font-bold text-gray-700 mb-2">سبب المكافأة</label> <select id="bonusReason" class="w-full p-4 form-input rounded-xl focus:outline-none" required> <option value="تميز أكاديمي">🌟 تميز أكاديمي</option> <option value="مشاركة فعالة">💬 مشاركة فعالة</option> <option value="مساعدة الزملاء">🤝 مساعدة الزملاء</option> <option value="إنجاز مشروع">📊 إنجاز مشروع</option> <option value="سلوك متميز">⭐ سلوك متميز</option> <option value="تفوق في الاختبار">📝 تفوق في الاختبار</option> <option value="حضور مثالي">✅ حضور مثالي</option> <option value="أخرى">📌 أخرى</option> </select>
     </div><button type="submit" class="w-full py-4 bg-gradient-to-r from-amber-500 to-yellow-500 text-white rounded-xl font-bold text-lg hover:shadow-lg transition-all"> ✨ إضافة المكافأة </button>
    </form>
   </div>
  </div><!-- ==================== Toast ==================== -->
  <div id="toast" class="toast fixed bottom-6 left-6 bg-white rounded-2xl p-5 shadow-2xl border-r-4 border-green-500 z-50 max-w-sm">
   <div class="flex items-center gap-4"><span id="toastIcon" class="text-4xl">✅</span>
    <div>
     <p id="toastMessage" class="font-bold text-gray-800">تمت العملية بنجاح</p>
     <p id="toastSubMessage" class="text-sm text-gray-500 mt-1"></p>
    </div>
   </div>
  </div><!-- ==================== JavaScript ==================== -->
  <script>
    // ========== المتغيرات العامة ==========
    const defaultConfig = {
      platform_name: 'منصة التعليم الرقمي',
      university_name: 'جامعة جنوب الوادي',
      faculty_name: 'كلية التربية النوعية'
    };
    
    let allData = [];
    let currentUser = null;
    let isLoading = false;
    let faceMode = null; // 'login' or 'register'
    let capturedFaceData = null;
    let videoStream = null;

    // المقررات الثابتة
    const courses = [
      { id: 'mental-health', name: 'الصح�� النفسية', icon: '🧠', color: 'emerald', hours: 3 },
      { id: 'digitization', name: 'الرقمنة التعليمية', icon: '💻', color: 'blue', hours: 3 },
      { id: 'environment', name: 'الثقافة البيئية', icon: '🌍', color: 'green', hours: 3 },
      { id: 'quality', name: 'ضمان الجودة', icon: '⭐', color: 'purple', hours: 3 },
      { id: 'english', name: 'قراءات إنجليزية', icon: '🇬🇧', color: 'red', hours: 3 },
      { id: 'design', name: 'التصميم التعليمي', icon: '🎨', color: 'amber', hours: 3 }
    ];

    const badges = [
      { id: 'beginner', name: 'المبتدئ', icon: '🌟', desc: 'أول تسجيل دخول', xp: 0 },
      { id: 'persistent', name: 'المثابر', icon: '🔥', desc: '7 أيام متتالية', xp: 500 },
      { id: 'excellent', name: 'المتفوق', icon: '🏆', desc: 'درجة كاملة', xp: 1000 },
      { id: 'reader', name: 'القارئ', icon: '📚', desc: '10 محاضرات', xp: 1500 },
      { id: 'punctual', name: 'المنتظم', icon: '⏰', desc: 'حضور 100%', xp: 2000 },
      { id: 'helper', name: 'المساعد', icon: '🤝', desc: 'مساعدة الزملاء', xp: 2500 }
    ];

    // أسئلة الاختبارات
    const quizQuestions = {
      'design': [
        { q: 'ما هو نموذج التصميم التعليمي الأكثر شيوعاً؟', options: ['ADDIE', 'ASSURE', 'Dick & Carey', 'Kemp'], correct: 0 },
        { q: 'ما المرحلة الأولى في نموذج ADDIE؟', options: ['التصميم', 'التحليل', 'التطوير', 'التقويم'], correct: 1 },
        { q: 'أي مما يلي ليس من عناصر التصميم التعليمي؟', options: ['الأهداف', 'المحتوى', 'التقويم', 'الميزانية'], correct: 3 }
      ],
      'digitization': [
        { q: 'ما هو نظام إدارة التعلم LMS؟', options: ['برنامج لإدارة المحتوى', 'منصة للتعلم الإلكتروني', 'تطبيق للاختبارات', 'م��قع للتواصل'], correct: 1 },
        { q: 'أي مما يلي مثال على LMS؟', options: ['Word', 'Moodle', 'Photoshop', 'Excel'], correct: 1 },
        { q: 'ما المقصود بالتعلم المدمج؟', options: ['التعلم عن بعد فقط', 'التعلم الوجاهي فقط', 'الدمج بين الوجاهي والإلكتروني', 'التعلم الذاتي'], correct: 2 }
      ],
      'mental-health': [
        { q: 'ما هي الصحة النفسية؟', options: ['غياب المرض العقلي', 'حالة من الرفاهية', 'القدرة على العمل', 'كل ما سبق'], correct: 3 },
        { q: 'أي مما يلي يؤثر سلباً على الصحة النفسية؟', options: ['ممارسة الرياضة', 'التواصل الاجتماعي', 'الضغوط المستمرة', 'النوم الكافي'], correct: 2 }
      ],
      'quality': [
        { q: 'ما هو الهدف الرئيسي لضمان الجودة؟', options: ['تقليل التكاليف', 'تحسين الأداء', 'زيادة الأرباح', '��قليل الموظفين'], correct: 1 },
        { q: 'أي معيار من معايير الجودة في التعليم؟', options: ['عدد الطلاب', 'جودة المخرجات', 'حجم المبنى', 'عمر الجامعة'], correct: 1 }
      ]
    };

    // ========== تهيئة التطبيق ==========
    const dataHandler = {
      onDataChanged(data) {
        allData = data;
        if (currentUser) {
          refreshCurrentUserData();
          updateSidebarStats();
        }
      }
    };

    async function initApp() {
      try {
        // شريط التحميل
        const progressBar = document.getElementById('loadingProgress');
        let progress = 0;
        const progressInterval = setInterval(() => {
          progress += Math.random() * 15;
          if (progress > 90) progress = 90;
          progressBar.style.width = progress + '%';
        }, 200);

        // تهيئة Element SDK
        if (window.elementSdk) {
          window.elementSdk.init({
            defaultConfig,
            onConfigChange: async (config) => {
              document.getElementById('platformTitle').textContent = config.platform_name || defaultConfig.platform_name;
              document.getElementById('universityName').textContent = config.university_name || defaultConfig.university_name;
              document.getElementById('facultyName').textContent = config.faculty_name || defaultConfig.faculty_name;
            },
            mapToCapabilities: () => ({ recolorables: [], borderables: [], fontEditable: undefined, fontSizeable: undefined }),
            mapToEditPanelValues: (config) => new Map([
              ['platform_name', config.platform_name || defaultConfig.platform_name],
              ['university_name', config.university_name || defaultConfig.university_name],
              ['faculty_name', config.faculty_name || defaultConfig.faculty_name]
            ])
          });
        }

        // تهيئة Data SDK
        const initResult = await window.dataSdk.init(dataHandler);
        if (!initResult.isOk) {
          console.error('Failed to initialize Data SDK');
        }

        clearInterval(progressInterval);
        progressBar.style.width = '100%';

        setTimeout(() => {
          document.getElementById('loadingScreen').classList.add('hidden');
          document.getElementById('loginScreen').classList.remove('hidden');
          startDateTime();
        }, 500);

      } catch (error) {
        console.error('Init error:', error);
      }
    }

    // ========== نظام المصادقة ==========
    function showLoginTab(tab) {
      const loginForm = document.getElementById('loginForm');
      const registerForm = document.getElementById('registerForm');
      const loginBtn = document.getElementById('loginTabBtn');
      const registerBtn = document.getElementById('registerTabBtn');
      
      document.getElementById('authError').classList.add('hidden');
      
      if (tab === 'login') {
        loginForm.classList.remove('hidden');
        registerForm.classList.add('hidden');
        loginBtn.classList.add('tab-active');
        loginBtn.classList.remove('text-gray-500');
        registerBtn.classList.remove('tab-active');
        registerBtn.classList.add('text-gray-500');
      } else {
        loginForm.classList.add('hidden');
        registerForm.classList.remove('hidden');
        registerBtn.classList.add('tab-active');
        registerBtn.classList.remove('text-gray-500');
        loginBtn.classList.remove('tab-active');
        loginBtn.classList.add('text-gray-500');
      }
    }

    function togglePassword(inputId, btn) {
      const input = document.getElementById(inputId);
      if (input.type === 'password') {
        input.type = 'text';
        btn.textContent = '🙈';
      } else {
        input.type = 'password';
        btn.textContent = '👁️';
      }
    }

    document.getElementById('regRole').addEventListener('change', function() {
      document.getElementById('studentFields').classList.toggle('hidden', this.value !== 'student');
    });

    // تسجيل الدخول
    document.getElementById('loginForm').addEventListener('submit', async function(e) {
      e.preventDefault();
      
      const userId = document.getElementById('loginId').value.trim();
      const password = document.getElementById('loginPassword').value;
      
      const user = allData.find(d => d.type === 'user' && d.user_id === userId && d.password === password);
      
      if (user) {
        currentUser = user;
        loginSuccess();
      } else {
        showAuthError('الرقم الجامعي أو كلمة المرور غير صحيحة');
        document.getElementById('loginForm').classList.add('shake');
        setTimeout(() => document.getElementById('loginForm').classList.remove('shake'), 500);
      }
    });

    // إنشاء حساب
    document.getElementById('registerForm').addEventListener('submit', async function(e) {
      e.preventDefault();
      
      if (isLoading) return;
      
      const role = document.getElementById('regRole').value;
      const name = document.getElementById('regName').value.trim();
      const userId = document.getElementById('regId').value.trim();
      const email = document.getElementById('regEmail').value.trim();
      const password = document.getElementById('regPassword').value;
      const level = document.getElementById('regLevel').value;
      
      // التحقق من عدم التكرار
      if (allData.find(d => d.type === 'user' && d.user_id === userId)) {
        showAuthError('هذا الرقم مسجل بالفعل، جرب تسجيل الدخول');
        return;
      }
      
      if (allData.length >= 999) {
        showAuthError('تم الوصول للحد الأقصى من المستخدمين');
        return;
      }
      
      isLoading = true;
      const btn = document.getElementById('registerBtn');
      btn.innerHTML = '<div class="loading-ring mx-auto"></div>';
      
      const newUser = {
        type: 'user',
        user_id: userId,
        password: password,
        name: name,
        email: email,
        role: role,
        level: role === 'student' ? level : '',
        points: 0,
        xp: 0,
        streak: 0,
        face_data: capturedFaceData || '',
        created_at: new Date().toISOString()
      };
      
      const result = await window.dataSdk.create(newUser);
      
      isLoading = false;
      btn.innerHTML = '<span>إنشاء الحساب</span><span>✨</span>';
      
      if (result.isOk) {
        showToast('تم إنشاء الحساب بنجاح! 🎉', '✅', '��مكنك تسجيل الدخول الآن');
        showLoginTab('login');
        document.getElementById('loginId').value = userId;
        this.reset();
        capturedFaceData = null;
        document.getElementById('faceRegStatus').classList.add('hidden');
      } else {
        showAuthError('حدث خطأ أثناء إنشاء الحساب');
      }
    });

    function showAuthError(message) {
      const error = document.getElementById('authError');
      error.textContent = message;
      error.classList.remove('hidden');
    }

    function loginSuccess() {
      document.getElementById('loginScreen').classList.add('hidden');
      document.getElementById('mainPlatform').classList.remove('hidden');
      
      // تحديث الشريط الجانبي
      document.getElementById('sidebarName').textContent = currentUser.name;
      document.getElementById('sidebarRole').textContent = currentUser.role === 'teacher' 
        ? '👨‍🏫 عضو هيئة تدريس' 
        : `👨‍🎓 طالب - الفرقة ${getArabicLevel(currentUser.level)}`;
      document.getElementById('sidebarAvatar').textContent = currentUser.role === 'teacher' ? '👨‍🏫' : '🎓';
      
      if (currentUser.role === 'student') {
        document.getElementById('studentSidebarStats').classList.remove('hidden');
        updateSidebarStats();
      }
      
      buildSidebar();
      showSection('home');
      showToast(`مرحباً ${currentUser.name.split(' ')[0]}! 👋`, '✅', 'تم تسجيل الدخول بنجاح');
    }

    function logout() {
      currentUser = null;
      capturedFaceData = null;
      document.getElementById('mainPlatform').classList.add('hidden');
      document.getElementById('loginScreen').classList.remove('hidden');
      document.getElementById('loginForm').reset();
      document.getElementById('studentSidebarStats').classList.add('hidden');
    }

    function getArabicLevel(level) {
      return { '1': 'الأولى', '2': 'الثانية', '3': 'الثالثة', '4': 'الرابعة' }[level] || level;
    }

    function refreshCurrentUserData() {
      const updated = allData.find(d => d.type === 'user' && d.user_id === currentUser.user_id);
      if (updated) currentUser = updated;
    }

    function updateSidebarStats() {
      if (!currentUser || currentUser.role !== 'student') return;
      
      const xp = currentUser.xp || 0;
      const points = currentUser.points || 0;
      const level = Math.floor(xp / 1000) + 1;
      
      document.getElementById('sidebarPoints').textContent = points.toLocaleString();
      document.getElementById('currentXP').textContent = `${xp % 1000} XP`;
      document.getElementById('userLevel').textContent = level;
      document.getElementById('xpProgress').style.width = `${(xp % 1000) / 10}%`;
      document.getElementById('sidebarStreak').textContent = currentUser.streak || 0;
    }

    // ========== نظام بصمة الوجه ==========
    function showFaceLogin() {
      faceMode = 'login';
      document.getElementById('faceModalTitle').textContent = 'تسجيل الدخول ببصمة الوجه';
      document.getElementById('faceModalSubtitle').textContent = 'ضع وجهك داخل الإطار للتعرف عليك';
      document.getElementById('captureBtnText').textContent = 'التقاط وتسجيل الدخول';
      openFaceModal();
    }

    function showFaceRegistration() {
      faceMode = 'register';
      document.getElementById('faceModalTitle').textContent = 'تسجيل بصمة الوجه';
      document.getElementById('faceModalSubtitle').textContent = 'ضع وجهك داخل الإطار لتسجيل البصمة';
      document.getElementById('captureBtnText').textContent = 'التقاط صورة الوجه';
      openFaceModal();
    }

    async function openFaceModal() {
      document.getElementById('faceModal').classList.remove('hidden');
      document.getElementById('faceModal').classList.add('flex');
      document.getElementById('captureBtn').disabled = true;
      document.getElementById('scanStatusText').textContent = 'جاري تشغيل الكاميرا...';
      document.getElementById('faceActions').classList.add('hidden');
      document.getElementById('captureBtn').classList.remove('hidden');
      
      try {
        videoStream = await navigator.mediaDevices.getUserMedia({ 
          video: { facingMode: 'user', width: 640, height: 480 } 
        });
        
        const video = document.getElementById('faceVideo');
        video.srcObject = videoStream;
        
        video.onloadedmetadata = () => {
          document.getElementById('captureBtn').disabled = false;
          document.getElementById('scanStatusText').textContent = '✅ الكاميرا جاهزة - ضع وجهك داخل الإطار';
        };
      } catch (error) {
        document.getElementById('scanStatusText').textContent = '❌ تعذر الوصول للكاميرا';
        console.error('Camera error:', error);
      }
    }

    function closeFaceModal() {
      document.getElementById('faceModal').classList.add('hidden');
      document.getElementById('faceModal').classList.remove('flex');
      
      if (videoStream) {
        videoStream.getTracks().forEach(track => track.stop());
        videoStream = null;
      }
      
      const video = document.getElementById('faceVideo');
      video.srcObject = null;
    }

    function captureFace() {
      const video = document.getElementById('faceVideo');
      const canvas = document.getElementById('faceCanvas');
      const ctx = canvas.getContext('2d');
      
      canvas.width = video.videoWidth;
      canvas.height = video.videoHeight;
      
      // انعكاس الصورة أفقياً
      ctx.translate(canvas.width, 0);
      ctx.scale(-1, 1);
      ctx.drawImage(video, 0, 0);
      
      // تأثير الفلاش
      video.classList.add('capture-flash');
      setTimeout(() => video.classList.remove('capture-flash'), 300);
      
      // الحصول على بيانات الصورة
      capturedFaceData = canvas.toDataURL('image/jpeg', 0.8);
      
      document.getElementById('scanStatusText').textContent = '📸 تم التقاط الصورة بنجاح!';
      
      if (faceMode === 'login') {
        // محاولة تسجيل الدخول بالوجه
        attemptFaceLogin();
      } else {
        // إظهار خيارات التأكيد
        document.getElementById('captureBtn').classList.add('hidden');
        document.getElementById('faceActions').classList.remove('hidden');
      }
    }

    function attemptFaceLogin() {
      // البحث عن مستخدم لديه بصمة وجه
      const usersWithFace = allData.filter(d => d.type === 'user' && d.face_data);
      
      if (usersWithFace.length === 0) {
        document.getElementById('scanStatusText').textContent = '❌ لا يوجد حسابات مسجلة ببصمة الوجه';
        setTimeout(() => {
          document.getElementById('scanStatusText').textContent = '✅ الكاميرا جاهزة - ضع وجهك داخل الإطار';
        }, 2000);
        return;
      }
      
      // محاكاة التعرف على الوجه (في الواقع سيحتاج لـ AI)
      // هنا نفترض أن أول مستخدم لديه بصمة هو المطابق
      document.getElementById('scanStatusText').textContent = '🔍 جاري التحقق من الهوية...';
      
      setTimeout(() => {
        const matchedUser = usersWithFace[0]; // في الواقع سيكون هناك مقارنة حقيقية
        
        if (matchedUser) {
          currentUser = matchedUser;
          closeFaceModal();
          loginSuccess();
        } else {
          document.getElementById('scanStatusText').textContent = '��� لم يتم التعرف على الوجه';
        }
      }, 1500);
    }

    function confirmFace() {
      if (faceMode === 'register') {
        document.getElementById('faceRegStatus').classList.remove('hidden');
        closeFaceModal();
        showToast('تم تسجيل بصمة الوجه', '✅', 'يمكنك الآن الدخول بالوجه');
      }
    }

    function retakeFace() {
      capturedFaceData = null;
      document.getElementById('faceActions').classList.add('hidden');
      document.getElementById('captureBtn').classList.remove('hidden');
      document.getElementById('scanStatusText').textContent = '✅ الكاميرا جاهزة - ضع وجهك داخل الإطار';
    }

    // ========== بناء الواجهة ==========
    function buildSidebar() {
      const menu = document.getElementById('sidebarMenu');
      let items = [
        { id: 'home', icon: '🏠', label: 'لوحة التحكم' },
        { id: 'courses', icon: '📚', label: 'المقررات' }
      ];
      
      if (currentUser.role === 'teacher') {
        items.push(
          { id: 'content', icon: '📂', label: 'إدارة المحتوى' },
          { id: 'students', icon: '👥', label: 'الطلاب' },
          { id: 'attendance-manage', icon: '📋', label: 'إدارة الحضور' },
          { id: 'grades', icon: '📊', label: 'الدرجات' }
        );
      } else {
        items.push(
          { id: 'quizzes', icon: '📝', label: 'الاختبارات' },
          { id: 'achievements', icon: '🏆', label: 'الإنجازات' },
          { id: 'attendance', icon: '📷', label: 'تسجيل الحضور' },
          { id: 'my-grades', icon: '📊', label: 'درجاتي' }
        );
      }
      
      items.push({ id: 'reminders', icon: '⏰', label: 'التذكيرات' });
      
      menu.innerHTML = items.map(item => `
        <button onclick="showSection('${item.id}')" data-section="${item.id}" 
          class="sidebar-item w-full p-4 rounded-xl text-right flex items-center gap-4 text-white">
          <span class="text-xl">${item.icon}</span>
          <span class="font-medium">${item.label}</span>
        </button>
      `).join('');
    }

    function showSection(section) {
      document.querySelectorAll('.sidebar-item').forEach(btn => btn.classList.remove('active'));
      document.querySelector(`[data-section="${section}"]`)?.classList.add('active');
      
      const titles = {
        'home': 'لوحة التحكم',
        'courses': 'المقررات الدراسية',
        'content': 'إدارة المحتوى',
        'students': 'إدارة الطلاب',
        'attendance-manage': 'إدارة الحضور',
        'grades': 'إدارة الدرجات',
        'quizzes': 'الاختبارات',
        'achievements': 'الإنجازات',
        'attendance': 'تسجيل الحضور',
        'my-grades': 'درجاتي',
        'reminders': 'التذكيرات'
      };
      
      document.getElementById('pageTitle').textContent = titles[section] || section;
      
      const content = document.getElementById('mainContent');
      
      switch(section) {
        case 'home': renderHome(); break;
        case 'courses': renderCourses(); break;
        case 'content': renderContent(); break;
        case 'students': renderStudents(); break;
        case 'attendance-manage': renderAttendanceManage(); break;
        case 'grades': renderGrades(); break;
        case 'quizzes': renderQuizzes(); break;
        case 'achievements': renderAchievements(); break;
        case 'attendance': renderAttendance(); break;
        case 'my-grades': renderMyGrades(); break;
        case 'reminders': renderReminders(); break;
        default: content.innerHTML = '<p class="text-center text-gray-500">الصفحة غير موجودة</p>';
      }
    }

    // ========== الصفحة الرئيسية ==========
    function renderHome() {
      if (currentUser.role === 'teacher') {
        renderTeacherHome();
      } else {
        renderStudentHome();
      }
    }

    function renderTeacherHome() {
      const students = allData.filter(d => d.type === 'user' && d.role === 'student').length;
      const contents = allData.filter(d => d.type === 'content').length;
      const todayAttendance = allData.filter(d => d.type === 'attendance' && d.attendance_date === new Date().toISOString().split('T')[0]).length;
      
      document.getElementById('mainContent').innerHTML = `
        <div class="fade-in space-y-6">
          <div class="card p-6 border-r-4 border-amber-500">
            <div class="flex items-center gap-4">
              <div class="w-16 h-16 rounded-2xl bg-gradient-to-br from-amber-100 to-amber-200 flex items-center justify-center">
                <span class="text-3xl">👨‍🏫</span>
              </div>
              <div>
                <h1 class="text-2xl font-bold">مرحباً د/ ${currentUser.name.split(' ')[0]}</h1>
                <p class="text-gray-500">لوحة تحكم عضو هيئة التدريس</p>
              </div>
            </div>
          </div>
          
          <div class="grid grid-cols-2 lg:grid-cols-4 gap-5">
            <div class="card stat-card p-6 border-r-4 border-blue-500 cursor-pointer" onclick="showSection('students')">
              <p class="text-gray-500 text-sm">الطلاب</p>
              <h3 class="text-4xl font-bold mt-2">${students}</h3>
              <span class="text-3xl absolute top-4 left-4 opacity-20">👥</span>
            </div>
            <div class="card stat-card p-6 border-r-4 border-green-500 cursor-pointer" onclick="showSection('content')">
              <p class="text-gray-500 text-sm">المحتوى</p>
              <h3 class="text-4xl font-bold mt-2">${contents}</h3>
              <span class="text-3xl absolute top-4 left-4 opacity-20">📂</span>
            </div>
            <div class="card stat-card p-6 border-r-4 border-purple-500">
              <p class="text-gray-500 text-sm">المقررات</p>
              <h3 class="text-4xl font-bold mt-2">${courses.length}</h3>
              <span class="text-3xl absolute top-4 left-4 opacity-20">📚</span>
            </div>
            <div class="card stat-card p-6 border-r-4 border-amber-500 cursor-pointer" onclick="showSection('attendance-manage')">
              <p class="text-gray-500 text-sm">حضور ا��يوم</p>
              <h3 class="text-4xl font-bold mt-2">${todayAttendance}</h3>
              <span class="text-3xl absolute top-4 left-4 opacity-20">✅</span>
            </div>
          </div>
          
          <div class="card p-6">
            <h2 class="font-bold text-xl mb-5">⚡ إجراءات سريعة</h2>
            <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
              <button onclick="openModal('addContentModal'); populateCourses('contentCourse')" 
                class="p-5 bg-gradient-to-br from-blue-50 to-blue-100 rounded-2xl text-center hover:shadow-lg transition-all">
                <span class="text-4xl block mb-3">📤</span>
                <span class="font-bold">رفع محتوى</span>
              </button>
              <button onclick="showSection('attendance-manage')" 
                class="p-5 bg-gradient-to-br from-green-50 to-green-100 rounded-2xl text-center hover:shadow-lg transition-all">
                <span class="text-4xl block mb-3">📋</span>
                <span class="font-bold">تسجيل حضور</span>
              </button>
              <button onclick="openModal('addReminderModal'); populateCourses('reminderCourse')" 
                class="p-5 bg-gradient-to-br from-amber-50 to-amber-100 rounded-2xl text-center hover:shadow-lg transition-all">
                <span class="text-4xl block mb-3">⏰</span>
                <span class="font-bold">إضافة تذكير</span>
              </button>
              <button onclick="openGradeModal()" 
                class="p-5 bg-gradient-to-br from-purple-50 to-purple-100 rounded-2xl text-center hover:shadow-lg transition-all">
                <span class="text-4xl block mb-3">📊</span>
                <span class="font-bold">إضافة درجة</span>
              </button>
            </div>
          </div>
        </div>
      `;
    }

    function renderStudentHome() {
      const myAttendance = allData.filter(d => d.type === 'attendance' && d.user_id === currentUser.user_id).length;
      const myQuizzes = allData.filter(d => d.type === 'quiz_result' && d.user_id === currentUser.user_id).length;
      const earnedBadges = allData.filter(d => d.type === 'badge' && d.user_id === currentUser.user_id).length;
      
      document.getElementById('mainContent').innerHTML = `
        <div class="fade-in space-y-6">
          <div class="card p-6 border-r-4 border-amber-500 relative overflow-hidden">
            <div class="absolute top-0 left-0 w-64 h-64 bg-amber-500/5 rounded-full -translate-x-1/2 -translate-y-1/2"></div>
            <div class="flex items-center justify-between flex-wrap gap-4 relative">
              <div class="flex items-center gap-4">
                <div class="w-16 h-16 rounded-2xl bg-gradient-to-br from-amber-100 to-amber-200 flex items-center justify-center">
                  <span class="text-3xl">���</span>
                </div>
                <div>
                  <h1 class="text-2xl font-bold">مرحباً <span class="gradient-text">${currentUser.name.split(' ')[0]}</span></h1>
                  <p class="text-gray-500">الفرقة ${getArabicLevel(currentUser.level)} - تكنولوجيا التعليم</p>
                </div>
              </div>
              <button onclick="showSection('quizzes')" class="px-6 py-3 btn-primary text-white rounded-xl flex items-center gap-2">
                <span>📝</span><span class="font-bold">اختبار سريع</span>
              </button>
            </div>
          </div>
          
          <div class="grid grid-cols-2 lg:grid-cols-4 gap-5">
            <div class="card stat-card p-6 border-r-4 border-blue-500 cursor-pointer" onclick="showSection('courses')">
              <p class="text-gray-500 text-sm">المقررات</p>
              <h3 class="text-4xl font-bold mt-2">${courses.length}</h3>
              <span class="text-3xl absolute top-4 left-4 opacity-20">📚</span>
            </div>
            <div class="card stat-card p-6 border-r-4 border-green-500 cursor-pointer" onclick="showSection('achievements')">
              <p class="text-gray-500 text-sm">النقاط</p>
              <h3 class="text-4xl font-bold mt-2">${(currentUser.points || 0).toLocaleString()}</h3>
              <span class="text-3xl absolute top-4 left-4 opacity-20">⭐</span>
            </div>
            <div class="card stat-card p-6 border-r-4 border-purple-500 cursor-pointer" onclick="showSection('achievements')">
              <p class="text-gray-500 text-sm">الشارات</p>
              <h3 class="text-4xl font-bold mt-2">${earnedBadges}</h3>
              <span class="text-3xl absolute top-4 left-4 opacity-20">🏅</span>
            </div>
            <div class="card stat-card p-6 border-r-4 border-amber-500 cursor-pointer" onclick="showSection('attendance')">
              <p class="text-gray-500 text-sm">أيام الحضور</p>
              <h3 class="text-4xl font-bold mt-2">${myAttendance}</h3>
              <span class="text-3xl absolute top-4 left-4 opacity-20">✅</span>
            </div>
          </div>
          
          <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
            <div class="card p-6">
              <h2 class="font-bold text-xl mb-5 flex items-center gap-2">📚 المقررات</h2>
              <div class="space-y-3">
                ${courses.slice(0, 4).map(c => `
                  <div class="p-4 bg-gradient-to-r from-${c.color}-50 to-${c.color}-100 rounded-xl cursor-pointer hover:shadow-lg transition-all" onclick="viewCourse('${c.id}')">
                    <div class="flex items-center gap-4">
                      <div class="w-12 h-12 bg-${c.color}-200 rounded-xl flex items-center justify-center">
                        <span class="text-2xl">${c.icon}</span>
                      </div>
                      <div class="flex-1">
                        <p class="font-bold">${c.name}</p>
                        <p class="text-sm text-gray-500">${c.hours} ساعات معتمدة</p>
                      </div>
                      <span class="text-gray-400">←</span>
                    </div>
                  </div>
                `).join('')}
              </div>
            </div>
            
            <div class="card p-6">
              <h2 class="font-bold text-xl mb-5 flex items-center gap-2">⏰ التذكيرات القادمة</h2>
              ${renderHomeReminders()}
            </div>
          </div>
        </div>
      `;
    }

    function renderHomeReminders() {
      const reminders = allData.filter(d => d.type === 'reminder' && !d.reminder_completed).slice(0, 4);
      
      if (reminders.length === 0) {
        return '<p class="text-gray-500 text-center py-8">لا توجد تذكيرات 📭</p>';
      }
      
      const priorityColors = { urgent: 'red', today: 'amber', upcoming: 'blue' };
      const priorityIcons = { urgent: '🔴', today: '🟡', upcoming: '🔵' };
      
      return `<div class="space-y-3">${reminders.map(r => `
        <div class="p-4 bg-${priorityColors[r.reminder_priority] || 'gray'}-50 rounded-xl reminder-${r.reminder_priority || 'upcoming'}">
          <div class="flex items-center gap-3">
            <span class="text-xl">${priorityIcons[r.reminder_priority] || '📌'}</span>
            <div class="flex-1">
              <p class="font-bold">${r.reminder_title}</p>
              <p class="text-sm text-gray-500">${formatDeadline(r.reminder_deadline)}</p>
            </div>
          </div>
        </div>
      `).join('')}</div>`;
    }

    // ========== المقررات ==========
    function renderCourses() {
      document.getElementById('mainContent').innerHTML = `
        <div class="fade-in">
          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
            ${courses.map(c => {
              const contentCount = allData.filter(d => d.type === 'content' && d.course_id === c.id).length;
              return `
                <div class="card overflow-hidden cursor-pointer group" onclick="viewCourse('${c.id}')">
                  <div class="h-32 bg-gradient-to-br from-${c.color}-500 to-${c.color}-700 flex items-center justify-center relative">
                    <span class="text-5xl group-hover:scale-110 transition-transform">${c.icon}</span>
                    <div class="absolute top-3 left-3 px-3 py-1 glass rounded-full text-white text-xs font-bold">${c.hours} ساعات</div>
                  </div>
                  <div class="p-5">
                    <h3 class="font-bold text-lg mb-2">${c.name}</h3>
                    <p class="text-sm text-gray-500 mb-4">${contentCount} محتوى متاح</p>
                    <button class="w-full py-3 bg-${c.color}-100 text-${c.color}-700 rounded-xl font-bold hover:bg-${c.color}-200 transition-all">
                      عرض المحتوى ←
                    </button>
                  </div>
                </div>
              `;
            }).join('')}
          </div>
        </div>
      `;
    }

    function viewCourse(courseId) {
      const course = courses.find(c => c.id === courseId);
      const content = allData.filter(d => d.type === 'content' && d.course_id === courseId);
      const typeIcons = { video: '🎥', pdf: '📄', link: '��', assignment: '📝' };
      
      document.getElementById('mainContent').innerHTML = `
        <div class="fade-in">
          <button onclick="showSection('courses')" class="mb-6 text-blue-600 font-bold flex items-center gap-2 hover:gap-3 transition-all">
            → العودة للمقررات
          </button>
          
          <div class="card p-6 mb-6">
            <div class="flex items-center gap-5">
              <div class="w-20 h-20 bg-${course.color}-100 rounded-2xl flex items-center justify-center">
                <span class="text-4xl">${course.icon}</span>
              </div>
              <div>
                <h1 class="text-2xl font-bold">${course.name}</h1>
                <p class="text-gray-500">${course.hours} ساعات معتمدة • ${content.length} محتوى</p>
              </div>
            </div>
          </div>
          
          ${currentUser.role === 'teacher' ? `
            <button onclick="openModal('addContentModal'); document.getElementById('contentCourse').value='${courseId}'" 
              class="mb-6 px-6 py-3 btn-primary text-white rounded-xl font-bold flex items-center gap-2">
              ➕ إضافة محتوى جديد
            </button>
          ` : ''}
          
          ${content.length === 0 ? `
            <div class="card p-12 text-center">
              <span class="text-6xl block mb-4">📭</span>
              <p class="text-gray-500 text-lg">لا يوجد محتوى متاح حالياً</p>
            </div>
          ` : `
            <div class="space-y-4">
              ${content.map(c => `
                <div class="card file-card p-5 transition-all">
                  <div class="flex items-center gap-5">
                    <div class="w-14 h-14 bg-blue-100 rounded-xl flex items-center justify-center">
                      <span class="text-2xl">${typeIcons[c.content_type] || '📁'}</span>
                    </div>
                    <div class="flex-1">
                      <h3 class="font-bold text-lg">${c.content_title}</h3>
                      <p class="text-sm text-gray-500">${c.content_description || 'بدون وصف'}</p>
                    </div>
                    <a href="${c.content_url}" target="_blank" rel="noopener noreferrer" 
                      class="px-5 py-2 bg-blue-500 text-white rounded-xl font-bold hover:bg-blue-600 transition-all">
                      ${c.content_type === 'video' ? 'مشاهدة' : c.content_type === 'pdf' ? 'تحميل' : 'فتح'} ←
                    </a>
                    ${currentUser.role === 'teacher' ? `
                      <button onclick="deleteContent('${c.__backendId}')" class="p-3 text-red-500 hover:bg-red-50 rounded-xl">🗑️</button>
                    ` : ''}
                  </div>
                </div>
              `).join('')}
            </div>
          `}
        </div>
      `;
    }

    // ========== إدارة المحتوى ==========
    function renderContent() {
      const content = allData.filter(d => d.type === 'content');
      const typeIcons = { video: '🎥', pdf: '📄', link: '🔗', assignment: '📝' };
      
      document.getElementById('mainContent').innerHTML = `
        <div class="fade-in">
          <div class="flex items-center justify-between mb-6 flex-wrap gap-4">
            <h2 class="text-xl font-bold">📂 جميع المحتوى (${content.length})</h2>
            <button onclick="openModal('addContentModal'); populateCourses('contentCourse')" 
              class="px-6 py-3 btn-primary text-white rounded-xl font-bold flex items-center gap-2">
              ➕ إضافة محتوى
            </button>
          </div>
          
          ${content.length === 0 ? `
            <div class="card p-12 text-center">
              <span class="text-6xl block mb-4">📭</span>
              <p class="text-gray-500 text-lg mb-4">لم تقم برفع أي محتوى بعد</p>
              <button onclick="openModal('addContentModal'); populateCourses('contentCourse')" class="px-6 py-3 btn-gold rounded-xl font-bold">
                ابدأ برفع المحتوى الآن
              </button>
            </div>
          ` : `
            <div class="space-y-4">
              ${content.map(c => {
                const course = courses.find(co => co.id === c.course_id);
                return `
                  <div class="card file-card p-5">
                    <div class="flex items-center gap-5">
                      <div class="w-14 h-14 bg-${course?.color || 'gray'}-100 rounded-xl flex items-center justify-center">
                        <span class="text-2xl">${typeIcons[c.content_type] || '📁'}</span>
                      </div>
                      <div class="flex-1">
                        <h3 class="font-bold text-lg">${c.content_title}</h3>
                        <p class="text-sm text-gray-500">${course?.name || 'غير محدد'} • ${c.content_type}</p>
                      </div>
                      <a href="${c.content_url}" target="_blank" rel="noopener noreferrer" class="px-4 py-2 bg-blue-100 text-blue-700 rounded-lg font-bold">معاينة</a>
                      <button onclick="deleteContent('${c.__backendId}')" class="px-4 py-2 bg-red-100 text-red-700 rounded-lg font-bold hover:bg-red-200">حذف</button>
                    </div>
                  </div>
                `;
              }).join('')}
            </div>
          `}
        </div>
      `;
    }

    async function deleteContent(id) {
      const item = allData.find(d => d.__backendId === id);
      if (!item) return;
      
      const result = await window.dataSdk.delete(item);
      if (result.isOk) {
        showToast('تم حذف المحتوى', '✅', '');
      }
    }

    // ========== الطلاب ==========
    function renderStudents() {
      const students = allData.filter(d => d.type === 'user' && d.role === 'student')
        .sort((a, b) => (b.points || 0) - (a.points || 0));
      
      document.getElementById('mainContent').innerHTML = `
        <div class="fade-in space-y-6">
          <!-- إحصائيات سريعة -->
          <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
            <div class="card p-5 text-center border-r-4 border-blue-500">
              <span class="text-3xl block mb-2">👥</span>
              <p class="text-3xl font-bold text-blue-600">${students.length}</p>
              <p class="text-sm text-gray-500">إجمالي الطلاب</p>
            </div>
            <div class="card p-5 text-center border-r-4 border-green-500">
              <span class="text-3xl block mb-2">✅</span>
              <p class="text-3xl font-bold text-green-600">${allData.filter(d => d.type === 'attendance').length}</p>
              <p class="text-sm text-gray-500">سجلات الحضور</p>
            </div>
            <div class="card p-5 text-center border-r-4 border-amber-500">
              <span class="text-3xl block mb-2">⭐</span>
              <p class="text-3xl font-bold text-amber-600">${students.reduce((sum, s) => sum + (s.points || 0), 0).toLocaleString()}</p>
              <p class="text-sm text-gray-500">إجمالي النقاط</p>
            </div>
            <div class="card p-5 text-center border-r-4 border-purple-500">
              <span class="text-3xl block mb-2">📝</span>
              <p class="text-3xl font-bold text-purple-600">${allData.filter(d => d.type === 'quiz_result').length}</p>
              <p class="text-sm text-gray-500">الاختبارات المكتملة</p>
            </div>
          </div>

          <div class="card p-6">
            <div class="flex items-center justify-between mb-6">
              <h2 class="font-bold text-xl">👥 قائمة الطلاب (${students.length})</h2>
              <div class="flex gap-2">
                <span class="px-4 py-2 bg-gradient-to-r from-blue-600 to-indigo-600 text-white rounded-xl text-sm font-bold">
                  🎓 قسم تكنولوجيا التعليم
                </span>
              </div>
            </div>
            
            ${students.length === 0 ? `
              <p class="text-gray-500 text-center py-12">لا يوجد طلاب مسجلين بعد</p>
            ` : `
              <div class="space-y-4">
                ${students.map((s, index) => {
                  const attendance = allData.filter(d => d.type === 'attendance' && d.user_id === s.user_id).length;
                  const quizzes = allData.filter(d => d.type === 'quiz_result' && d.user_id === s.user_id).length;
                  const rankIcon = index === 0 ? '🥇' : index === 1 ? '🥈' : index === 2 ? '🥉' : `#${index + 1}`;
                  const isTop3 = index < 3;
                  
                  return `
                    <div class="p-5 ${isTop3 ? 'bg-gradient-to-r from-amber-50 to-yellow-50 border-2 border-amber-200' : 'bg-gray-50'} rounded-2xl transition-all hover:shadow-lg">
                      <div class="flex items-center gap-4 flex-wrap">
                        <div class="w-14 h-14 ${isTop3 ? 'bg-gradient-to-br from-amber-400 to-yellow-500' : 'bg-blue-100'} rounded-2xl flex items-center justify-center text-2xl font-bold ${isTop3 ? 'text-white' : ''}">
                          ${rankIcon}
                        </div>
                        <div class="w-14 h-14 bg-gradient-to-br from-blue-500 to-indigo-600 rounded-2xl flex items-center justify-center">
                          <span class="text-2xl">🎓</span>
                        </div>
                        <div class="flex-1 min-w-[200px]">
                          <p class="font-bold text-lg flex items-center gap-2">
                            ${s.name}
                            ${isTop3 ? '<span class="px-2 py-0.5 bg-amber-500 text-white text-xs rounded-full">متفوق</span>' : ''}
                          </p>
                          <p class="text-sm text-gray-500">${s.user_id} • الفرقة ${getArabicLevel(s.level)}</p>
                        </div>
                        <div class="flex items-center gap-3 flex-wrap">
                          <div class="text-center px-4 py-2 bg-amber-100 rounded-xl">
                            <p class="text-xl font-bold text-amber-700">${(s.points || 0).toLocaleString()}</p>
                            <p class="text-xs text-amber-600">نقطة</p>
                          </div>
                          <div class="text-center px-4 py-2 bg-green-100 rounded-xl">
                            <p class="text-xl font-bold text-green-700">${attendance}</p>
                            <p class="text-xs text-green-600">حضور</p>
                          </div>
                          <div class="text-center px-4 py-2 bg-purple-100 rounded-xl">
                            <p class="text-xl font-bold text-purple-700">${quizzes}</p>
                            <p class="text-xs text-purple-600">اختبار</p>
                          </div>
                        </div>
                        <div class="flex gap-2">
                          <button onclick="openBonusModal('${s.user_id}', '${s.name}')" 
                            class="px-4 py-2 bg-gradient-to-r from-amber-500 to-yellow-500 text-white rounded-xl font-bold text-sm hover:shadow-lg transition-all">
                            ⭐ مكافأة
                          </button>
                          <button onclick="makeFirstPlace('${s.user_id}')" 
                            class="px-4 py-2 bg-gradient-to-r from-blue-600 to-indigo-600 text-white rounded-xl font-bold text-sm hover:shadow-lg transition-all">
                            🏆 المركز الأول
                          </button>
                        </div>
                      </div>
                    </div>
                  `;
                }).join('')}
              </div>
            `}
          </div>
        </div>
      `;
    }

    // ========== الحضور ==========
    function renderAttendance() {
      const myAttendance = allData.filter(d => d.type === 'attendance' && d.user_id === currentUser.user_id);
      const today = new Date().toISOString().split('T')[0];
      const attendedToday = myAttendance.some(a => a.attendance_date === today);
      
      document.getElementById('mainContent').innerHTML = `
        <div class="fade-in">
          <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
            <div class="card p-6">
              <h3 class="font-bold text-xl mb-6">📷 تسجيل الحضور</h3>
              
              ${attendedToday ? `
                <div class="text-center py-12">
                  <div class="w-28 h-28 mx-auto mb-6 bg-green-100 rounded-full flex items-center justify-center success-checkmark">
                    <span class="text-5xl">✅</span>
                  </div>
                  <h4 class="text-2xl font-bold text-green-600 mb-2">تم تسجيل حضورك اليوم</h4>
                  <p class="text-gray-500">شكراً لالتزامك! 🎉</p>
                </div>
              ` : `
                <div class="text-center py-8">
                  <div class="w-36 h-36 mx-auto mb-8 bg-gradient-to-br from-purple-100 to-indigo-100 rounded-full flex items-center justify-center border-4 border-dashed border-purple-300">
                    <span class="text-6xl">📷</span>
                  </div>
                  <p class="text-gray-500 mb-6">اختر طريقة تسجيل الحضور</p>
                  <div class="space-y-3">
                    <button onclick="recordAttendanceWithFace()" 
                      class="w-full py-4 bg-gradient-to-r from-purple-600 to-indigo-600 text-white rounded-xl font-bold text-lg flex items-center justify-center gap-3">
                      <span>📸</span> تسجيل ببصمة الوجه
                    </button>
                    <button onclick="recordAttendance()" id="manualAttendanceBtn"
                      class="w-full py-4 btn-primary text-white rounded-xl font-bold text-lg flex items-center justify-center gap-3">
                      <span>✅</span> تسجيل يدوي
                    </button>
                  </div>
                </div>
              `}
            </div>
            
            <div class="card p-6">
              <h3 class="font-bold text-xl mb-6">📋 سجل الحضور</h3>
              <div class="space-y-3 max-h-80 overflow-y-auto">
                ${myAttendance.length === 0 ? '<p class="text-gray-500 text-center py-8">لا يوجد سجلات ح��ور</p>' :
                  myAttendance.slice(-10).reverse().map(a => `
                    <div class="flex items-center gap-4 p-4 bg-green-50 rounded-xl">
                      <span class="text-2xl">${a.attendance_method === 'face' ? '📸' : '✅'}</span>
                      <div class="flex-1">
                        <p class="font-bold">${formatDate(a.attendance_date)}</p>
                        <p class="text-xs text-gray-500">${a.attendance_method === 'face' ? 'بصمة الوجه' : 'تسجيل يدوي'}</p>
                      </div>
                      <span class="px-3 py-1 bg-green-200 text-green-800 rounded-lg text-sm font-bold">حضور</span>
                    </div>
                  `).join('')
                }
              </div>
              
              <div class="mt-6 p-5 bg-gradient-to-br from-slate-800 to-slate-900 rounded-2xl text-white">
                <div class="flex items-center justify-between mb-3">
                  <span class="font-medium">نسبة الحضور</span>
                  <span class="text-2xl font-bold text-green-400">${myAttendance.length > 0 ? Math.min(Math.round((myAttendance.length / 30) * 100), 100) : 0}%</span>
                </div>
                <div class="progress-bar h-3 bg-slate-700">
                  <div class="progress-fill" style="width: ${myAttendance.length > 0 ? Math.min((myAttendance.length / 30) * 100, 100) : 0}%"></div>
                </div>
              </div>
            </div>
          </div>
        </div>
      `;
    }

    async function recordAttendanceWithFace() {
      faceMode = 'attendance';
      document.getElementById('faceModalTitle').textContent = 'تسجيل الحضور ببصمة الوجه';
      document.getElementById('faceModalSubtitle').textContent = 'ضع وجهك داخل الإطار لتسجيل الحضور';
      document.getElementById('captureBtnText').textContent = 'تسجيل الحضور';
      
      openFaceModal();
      
      // تعديل سلوك الالتقاط للحضور
      const originalCapture = captureFace;
      window.captureFace = async function() {
        const video = document.getElementById('faceVideo');
        const canvas = document.getElementById('faceCanvas');
        const ctx = canvas.getContext('2d');
        
        canvas.width = video.videoWidth;
        canvas.height = video.videoHeight;
        ctx.translate(canvas.width, 0);
        ctx.scale(-1, 1);
        ctx.drawImage(video, 0, 0);
        
        video.classList.add('capture-flash');
        setTimeout(() => video.classList.remove('capture-flash'), 300);
        
        document.getElementById('scanStatusText').textContent = '🔍 جاري التحقق...';
        
        setTimeout(async () => {
          closeFaceModal();
          await recordAttendance('face');
          window.captureFace = originalCapture;
        }, 1000);
      };
    }

    async function recordAttendance(method = 'manual') {
      if (allData.length >= 999) {
        showToast('تم ��لوصول للحد الأقصى', '⚠️', '');
        return;
      }
      
      const btn = document.getElementById('manualAttendanceBtn');
      if (btn) {
        btn.disabled = true;
        btn.innerHTML = '<div class="loading-ring mx-auto"></div>';
      }
      
      const result = await window.dataSdk.create({
        type: 'attendance',
        user_id: currentUser.user_id,
        attendance_date: new Date().toISOString().split('T')[0],
        attendance_status: 'present',
        attendance_method: method,
        created_at: new Date().toISOString()
      });
      
      if (result.isOk) {
        await addPoints(10);
        showToast('تم تسجيل حضورك بنجاح! 🎉', '✅', '+10 نقاط');
      } else {
        showToast('حدث خطأ', '❌', '');
      }
    }

    function renderAttendanceManage() {
      const students = allData.filter(d => d.type === 'user' && d.role === 'student');
      const today = new Date().toISOString().split('T')[0];
      
      document.getElementById('mainContent').innerHTML = `
        <div class="fade-in">
          <div class="card p-6">
            <div class="flex items-center justify-between mb-6">
              <h3 class="font-bold text-xl">📋 تسجيل حضور الطلاب</h3>
              <span class="px-4 py-2 bg-blue-100 text-blue-700 rounded-xl font-bold">${formatDate(today)}</span>
            </div>
            
            ${students.length === 0 ? '<p class="text-gray-500 text-center py-12">لا يوجد طلاب مسجلين</p>' : `
              <div class="space-y-3">
                ${students.map(s => {
                  const attended = allData.some(d => d.type === 'attendance' && d.user_id === s.user_id && d.attendance_date === today);
                  return `
                    <div class="flex items-center gap-4 p-4 bg-gray-50 rounded-xl">
                      <div class="w-14 h-14 bg-blue-100 rounded-xl flex items-center justify-center">🎓</div>
                      <div class="flex-1">
                        <p class="font-bold text-lg">${s.name}</p>
                        <p class="text-sm text-gray-500">${s.user_id} - الفرقة ${getArabicLevel(s.level)}</p>
                      </div>
                      ${attended ? `
                        <span class="px-5 py-2 bg-green-100 text-green-700 rounded-xl font-bold">✅ حاضر</span>
                      ` : `
                        <button onclick="markStudentAttendance('${s.user_id}')" class="px-5 py-2 bg-blue-500 text-white rounded-xl font-bold hover:bg-blue-600 transition-all">
                          تسجيل حضور
                        </button>
                      `}
                    </div>
                  `;
                }).join('')}
              </div>
            `}
          </div>
        </div>
      `;
    }

    async function markStudentAttendance(userId) {
      if (allData.length >= 999) return;
      
      const result = await window.dataSdk.create({
        type: 'attendance',
        user_id: userId,
        attendance_date: new Date().toISOString().split('T')[0],
        attendance_status: 'present',
        attendance_method: 'teacher',
        created_by: currentUser.user_id,
        created_at: new Date().toISOString()
      });
      
      if (result.isOk) {
        showToast('تم تسجيل الحضور', '✅', '');
      }
    }

    // ========== الاختبارات ==========
    let currentQuiz = null;
    let quizIndex = 0;
    let quizScore = 0;

    function renderQuizzes() {
      document.getElementById('mainContent').innerHTML = `
        <div class="fade-in">
          <div class="card p-6 mb-6">
            <h2 class="font-bold text-xl mb-5">📝 اختر مقرراً للاختبار</h2>
            <div class="grid grid-cols-3 md:grid-cols-6 gap-4">
              ${courses.map(c => {
                const hasQuiz = quizQuestions[c.id];
                return `
                  <button onclick="${hasQuiz ? `startQuiz('${c.id}')` : ''}" 
                    class="p-5 ${hasQuiz ? `bg-${c.color}-100 hover:bg-${c.color}-200 cursor-pointer` : 'bg-gray-100 opacity-50 cursor-not-allowed'} rounded-2xl text-center transition-all">
                    <span class="text-3xl block mb-2">${c.icon}</span>
                    <p class="text-xs font-bold">${c.name.split(' ')[0]}</p>
                    ${!hasQuiz ? '<p class="text-xs text-gray-400 mt-1">قريباً</p>' : ''}
                  </button>
                `;
              }).join('')}
            </div>
          </div>
          
          <div class="card p-6">
            <h2 class="font-bold text-xl mb-5">📊 نتائجك السابقة</h2>
            ${renderQuizResults()}
          </div>
        </div>
      `;
    }

    function renderQuizResults() {
      const results = allData.filter(d => d.type === 'quiz_result' && d.user_id === currentUser.user_id);
      
      if (results.length === 0) {
        return '<p class="text-gray-500 text-center py-8">لم تجر أي اختبارات بعد 📭</p>';
      }
      
      return `<div class="space-y-3">${results.map(r => {
        const course = courses.find(c => c.id === r.quiz_course);
        const percentage = Math.round((r.quiz_score / r.quiz_total) * 100);
        return `
          <div class="flex items-center gap-4 p-4 bg-gray-50 rounded-xl">
            <span class="text-3xl">${course?.icon || '📝'}</span>
            <div class="flex-1">
              <p class="font-bold">${course?.name || 'اختبار'}</p>
              <p class="text-sm text-gray-500">${new Date(r.created_at).toLocaleDateString('ar-EG')}</p>
            </div>
            <div class="text-center">
              <p class="text-3xl font-bold ${percentage >= 70 ? 'text-green-600' : 'text-red-500'}">${percentage}%</p>
              <p class="text-xs text-gray-500">${r.quiz_score}/${r.quiz_total}</p>
            </div>
          </div>
        `;
      }).join('')}</div>`;
    }

    function startQuiz(courseId) {
      currentQuiz = { courseId, questions: quizQuestions[courseId] };
      quizIndex = 0;
      quizScore = 0;
      showQuestion();
    }

    function showQuestion() {
      const q = currentQuiz.questions[quizIndex];
      const course = courses.find(c => c.id === currentQuiz.courseId);
      
      document.getElementById('mainContent').innerHTML = `
        <div class="fade-in">
          <div class="card p-8 max-w-2xl mx-auto">
            <div class="flex items-center justify-between mb-6">
              <h3 class="font-bold text-lg">${course.icon} ${course.name}</h3>
              <span class="px-4 py-2 bg-blue-100 text-blue-700 rounded-full font-bold">
                ${quizIndex + 1} / ${currentQuiz.questions.length}
              </span>
            </div>
            
            <div class="progress-bar h-3 mb-8">
              <div class="progress-fill" style="width: ${((quizIndex + 1) / currentQuiz.questions.length) * 100}%"></div>
            </div>
            
            <p class="text-xl font-bold mb-8 p-5 bg-gray-50 rounded-2xl">${q.q}</p>
            
            <div class="space-y-4" id="quizOptions">
              ${q.options.map((opt, i) => `
                <button onclick="selectAnswer(${i})" class="quiz-option w-full p-5 text-right bg-gray-50 hover:bg-blue-50 border-2 border-gray-200 hover:border-blue-300 rounded-2xl transition-all">
                  <span class="inline-block w-10 h-10 bg-gray-200 rounded-full text-center leading-10 ml-4 font-bold">${['أ', 'ب', 'ج', 'د'][i]}</span>
                  ${opt}
                </button>
              `).join('')}
            </div>
          </div>
        </div>
      `;
    }

    function selectAnswer(index) {
      const q = currentQuiz.questions[quizIndex];
      const options = document.querySelectorAll('.quiz-option');
      
      options.forEach((opt, i) => {
        opt.disabled = true;
        opt.onclick = null;
        if (i === q.correct) opt.classList.add('correct');
        else if (i === index) opt.classList.add('wrong');
      });
      
      if (index === q.correct) quizScore++;
      
      setTimeout(() => {
        quizIndex++;
        if (quizIndex < currentQuiz.questions.length) {
          showQuestion();
        } else {
          endQuiz();
        }
      }, 1500);
    }

    async function endQuiz() {
      const percentage = Math.round((quizScore / currentQuiz.questions.length) * 100);
      const course = courses.find(c => c.id === currentQuiz.courseId);
      
      if (allData.length < 999) {
        await window.dataSdk.create({
          type: 'quiz_result',
          user_id: currentUser.user_id,
          quiz_course: currentQuiz.courseId,
          quiz_score: quizScore,
          quiz_total: currentQuiz.questions.length,
          created_at: new Date().toISOString()
        });
        
        await addPoints(quizScore * 10);
      }
      
      document.getElementById('mainContent').innerHTML = `
        <div class="fade-in">
          <div class="card p-10 max-w-md mx-auto text-center">
            <div class="w-32 h-32 mx-auto mb-8 ${percentage >= 70 ? 'bg-green-100' : 'bg-red-100'} rounded-full flex items-center justify-center">
              <span class="text-6xl">${percentage >= 70 ? '🎉' : '😔'}</span>
            </div>
            <h3 class="text-3xl font-bold mb-2">${percentage >= 70 ? 'أحسنت!' : 'حاول مرة أخرى'}</h3>
            <p class="text-gray-500 mb-8">نتيجتك في اختبار ${course.name}</p>
            
            <div class="text-6xl font-bold ${percentage >= 70 ? 'text-green-600' : 'text-red-500'} mb-8">
              ${percentage}%
            </div>
            
            <p class="text-gray-500 mb-8">${quizScore} إجابات صحيحة من ${currentQuiz.questions.length}</p>
            
            <div class="flex gap-4 justify-center">
              <button onclick="startQuiz('${currentQuiz.courseId}')" class="px-8 py-4 btn-primary text-white rounded-xl font-bold">
                🔄 إعادة
              </button>
              <button onclick="showSection('quizzes')" class="px-8 py-4 bg-gray-200 text-gray-700 rounded-xl font-bold">
                اختبار آخر
              </button>
            </div>
          </div>
        </div>
      `;
    }

    // ========== الإنجازات ==========
    function renderAchievements() {
      const earnedBadgeIds = allData.filter(d => d.type === 'badge' && d.user_id === currentUser.user_id).map(b => b.badge_id);
      const students = allData.filter(d => d.type === 'user' && d.role === 'student')
        .sort((a, b) => (b.points || 0) - (a.points || 0))
        .slice(0, 10);
      
      document.getElementById('mainContent').innerHTML = `
        <div class="fade-in space-y-6">
          <div class="grid grid-cols-2 md:grid-cols-4 gap-5">
            <div class="card p-6 text-center bg-gradient-to-br from-amber-50 to-yellow-50 border-2 border-amber-200">
              <span class="text-5xl block mb-3">⭐</span>
              <p class="text-4xl font-bold text-amber-600">${(currentUser.points || 0).toLocaleString()}</p>
              <p class="text-gray-500">النقاط</p>
            </div>
            <div class="card p-6 text-center bg-gradient-to-br from-purple-50 to-indigo-50 border-2 border-purple-200">
              <span class="text-5xl block mb-3">🏅</span>
              <p class="text-4xl font-bold text-purple-600">${earnedBadgeIds.length}</p>
              <p class="text-gray-500">الشارات</p>
            </div>
            <div class="card p-6 text-center bg-gradient-to-br from-blue-50 to-cyan-50 border-2 border-blue-200">
              <span class="text-5xl block mb-3">📊</span>
              <p class="text-4xl font-bold text-blue-600">${currentUser.xp || 0}</p>
              <p class="text-gray-500">XP</p>
            </div>
            <div class="card p-6 text-center bg-gradient-to-br from-green-50 to-emerald-50 border-2 border-green-200">
              <span class="text-5xl block mb-3">🎯</span>
              <p class="text-4xl font-bold text-green-600">${Math.floor((currentUser.xp || 0) / 1000) + 1}</p>
              <p class="text-gray-500">المستوى</p>
            </div>
          </div>
          
          <div class="card p-6">
            <h3 class="font-bold text-xl mb-6">🏅 الشارات</h3>
            <div class="grid grid-cols-3 md:grid-cols-6 gap-4">
              ${badges.map(b => {
                const earned = earnedBadgeIds.includes(b.id);
                return `
                  <div class="p-5 rounded-2xl text-center ${earned ? 'bg-gradient-to-br from-amber-100 to-yellow-100 border-2 border-amber-300 badge-shine' : 'bg-gray-100 opacity-50'}">
                    <span class="text-4xl block mb-2">${b.icon}</span>
                    <p class="text-sm font-bold">${b.name}</p>
                    <p class="text-xs text-gray-500 mt-1">${b.desc}</p>
                  </div>
                `;
              }).join('')}
            </div>
          </div>
          
          <div class="card p-6 overflow-hidden relative">
            <div class="absolute top-0 left-0 right-0 h-2 bg-gradient-to-r from-amber-400 via-yellow-400 to-amber-400"></div>
            <h3 class="font-bold text-xl mb-6 flex items-center gap-3">
              <span class="text-3xl">🏆</span> 
              لوحة المتصدرين
              <span class="px-3 py-1 bg-amber-100 text-amber-700 rounded-full text-sm">أفضل 10</span>
            </h3>
            ${students.length === 0 ? '<p class="text-gray-500 text-center py-8">لا يوجد طلاب بعد</p>' : `
              <div class="space-y-3">
                ${students.map((s, i) => {
                  const isYou = s.user_id === currentUser.user_id;
                  const isTop3 = i < 3;
                  return `
                    <div class="flex items-center gap-4 p-4 ${isYou ? 'bg-gradient-to-r from-amber-100 via-yellow-100 to-amber-100 border-2 border-amber-400 shadow-lg' : isTop3 ? 'bg-gradient-to-r from-amber-50 to-yellow-50' : 'bg-gray-50'} rounded-2xl transition-all hover:scale-[1.02]">
                      <div class="w-14 h-14 flex items-center justify-center font-bold text-2xl ${i === 0 ? 'bg-gradient-to-br from-amber-400 to-yellow-500 text-white rounded-2xl shadow-lg' : i === 1 ? 'bg-gradient-to-br from-gray-300 to-gray-400 text-white rounded-2xl' : i === 2 ? 'bg-gradient-to-br from-amber-600 to-amber-700 text-white rounded-2xl' : 'text-gray-500'}">
                        ${i < 3 ? ['🥇', '🥈', '🥉'][i] : i + 1}
                      </div>
                      <div class="w-14 h-14 ${isYou ? 'bg-gradient-to-br from-amber-400 to-yellow-500' : 'bg-gradient-to-br from-blue-500 to-indigo-600'} rounded-2xl flex items-center justify-center text-2xl shadow-lg">
                        ${isYou ? '👑' : '🎓'}
                      </div>
                      <div class="flex-1">
                        <p class="font-bold text-lg flex items-center gap-2 ${isYou ? 'text-amber-700' : ''}">
                          ${s.name} 
                          ${isYou ? '<span class="px-2 py-0.5 bg-amber-500 text-white text-xs rounded-full animate-pulse">أنت 👈</span>' : ''}
                          ${i === 0 ? '<span class="px-2 py-0.5 bg-gradient-to-r from-amber-500 to-yellow-500 text-white text-xs rounded-full">الأول 🏆</span>' : ''}
                        </p>
                        <p class="text-sm text-gray-500">الفرقة ${getArabicLevel(s.level)} • المستوى ${Math.floor((s.xp || 0) / 1000) + 1}</p>
                      </div>
                      <div class="text-center">
                        <p class="text-2xl font-bold ${isYou ? 'text-amber-600' : isTop3 ? 'text-amber-700' : 'text-gray-700'}">${(s.points || 0).toLocaleString()}</p>
                        <p class="text-xs text-gray-500">نقطة</p>
                      </div>
                    </div>
                  `;
                }).join('')}
              </div>
            `}
          </div>
        </div>
      `;
    }

    async function addPoints(amount) {
      const userRecord = allData.find(d => d.type === 'user' && d.user_id === currentUser.user_id);
      if (userRecord) {
        const newPoints = (userRecord.points || 0) + amount;
        const newXp = (userRecord.xp || 0) + amount;
        await window.dataSdk.update({
          ...userRecord,
          points: newPoints,
          xp: newXp
        });
      }
    }

    // وظيفة للدكتور لجعل طالب في المركز الأول
    async function makeFirstPlace(studentId) {
      const students = allData.filter(d => d.type === 'user' && d.role === 'student');
      const maxPoints = Math.max(...students.map(s => s.points || 0), 0);
      
      const student = allData.find(d => d.type === 'user' && d.user_id === studentId);
      if (student) {
        const newPoints = maxPoints + 1000; // نقاط إضافية للتصدر
        await window.dataSdk.update({
          ...student,
          points: newPoints,
          xp: (student.xp || 0) + 500
        });
        showToast(`تم ترقية ${student.name} للمركز الأول! 🥇`, '🏆', '+1000 نقطة');
      }
    }

    // إضافة نقاط مكافأة خاصة
    async function addBonusPoints(studentId, amount, reason) {
      const student = allData.find(d => d.type === 'user' && d.user_id === studentId);
      if (student) {
        await window.dataSdk.update({
          ...student,
          points: (student.points || 0) + amount,
          xp: (student.xp || 0) + Math.floor(amount / 2)
        });
        showToast(`تم إضافة ${amount} نقطة مكافأة`, '⭐', reason);
      }
    }

    // ========== الدرجات ==========
    function renderGrades() {
      document.getElementById('mainContent').innerHTML = `
        <div class="fade-in">
          <div class="flex items-center justify-between mb-6">
            <h2 class="text-xl font-bold">📊 إدارة الدرجات</h2>
            <button onclick="openGradeModal()" class="px-6 py-3 btn-primary text-white rounded-xl font-bold flex items-center gap-2">
              ➕ إضافة درجة
            </button>
          </div>
          
          <div class="card p-6">
            ${renderGradesTable()}
          </div>
        </div>
      `;
    }

    function renderGradesTable() {
      const grades = allData.filter(d => d.type === 'grade');
      
      if (grades.length === 0) {
        return '<p class="text-gray-500 text-center py-12">لم يتم إضافة درجات بعد</p>';
      }
      
      const gradeTypes = {
        quiz: 'اختبار قصير',
        midterm: 'منتصف الفصل',
        final: 'نهائي',
        assignment: 'واجب',
        participation: 'مشاركة'
      };
      
      return `
        <div class="overflow-x-auto">
          <table class="w-full">
            <thead>
              <tr class="bg-gray-50">
                <th class="p-4 text-right font-bold">الطالب</th>
                <th class="p-4 text-right font-bold">المقرر</th>
                <th class="p-4 text-right font-bold">النوع</th>
                <th class="p-4 text-right font-bold">الدرجة</th>
              </tr>
            </thead>
            <tbody>
              ${grades.map(g => {
                const student = allData.find(d => d.type === 'user' && d.user_id === g.user_id);
                const course = courses.find(c => c.id === g.course_id);
                return `
                  <tr class="border-t">
                    <td class="p-4 font-bold">${student?.name || 'غير معروف'}</td>
                    <td class="p-4">${course?.name || 'غير محدد'}</td>
                    <td class="p-4">${gradeTypes[g.grade_type] || g.grade_type}</td>
                    <td class="p-4">
                      <span class="px-3 py-1 ${g.grade_value >= 70 ? 'bg-green-100 text-green-700' : 'bg-red-100 text-red-700'} rounded-full font-bold">
                        ${g.grade_value}%
                      </span>
                    </td>
                  </tr>
                `;
              }).join('')}
            </tbody>
          </table>
        </div>
      `;
    }

    function renderMyGrades() {
      const myGrades = allData.filter(d => d.type === 'grade' && d.user_id === currentUser.user_id);
      
      const gradeTypes = {
        quiz: 'اختبار قصير',
        midterm: 'منتصف الفصل',
        final: 'نهائي',
        assignment: 'واجب',
        participation: 'مشاركة'
      };
      
      document.getElementById('mainContent').innerHTML = `
        <div class="fade-in">
          <div class="card p-6">
            <h2 class="font-bold text-xl mb-6">📊 درجاتي</h2>
            
            ${myGrades.length === 0 ? '<p class="text-gray-500 text-center py-12">لا توجد درجات مسجلة بعد</p>' : `
              <div class="space-y-4">
                ${myGrades.map(g => {
                  const course = courses.find(c => c.id === g.course_id);
                  return `
                    <div class="flex items-center gap-4 p-5 bg-gray-50 rounded-xl">
                      <div class="w-14 h-14 bg-${course?.color || 'gray'}-100 rounded-xl flex items-center justify-center">
                        <span class="text-2xl">${course?.icon || '📊'}</span>
                      </div>
                      <div class="flex-1">
                        <p class="font-bold text-lg">${course?.name || 'غير محدد'}</p>
                        <p class="text-sm text-gray-500">${gradeTypes[g.grade_type] || g.grade_type}</p>
                      </div>
                      <div class="text-center">
                        <p class="text-4xl font-bold ${g.grade_value >= 70 ? 'text-green-600' : 'text-red-500'}">${g.grade_value}%</p>
                      </div>
                    </div>
                  `;
                }).join('')}
              </div>
            `}
          </div>
        </div>
      `;
    }

    function openGradeModal() {
      populateStudents('gradeStudent');
      populateCourses('gradeCourse');
      openModal('addGradeModal');
    }

    document.getElementById('gradeForm').addEventListener('submit', async function(e) {
      e.preventDefault();
      
      if (allData.length >= 999) {
        showToast('تم الوصول للحد الأقصى', '⚠️', '');
        return;
      }
      
      const result = await window.dataSdk.create({
        type: 'grade',
        user_id: document.getElementById('gradeStudent').value,
        course_id: document.getElementById('gradeCourse').value,
        grade_type: document.getElementById('gradeType').value,
        grade_value: parseInt(document.getElementById('gradeValue').value),
        created_at: new Date().toISOString(),
        created_by: currentUser.user_id
      });
      
      if (result.isOk) {
        showToast('تم حفظ الدرجة', '✅', '');
        closeModal('addGradeModal');
        this.reset();
      }
    });

    // ========== التذكيرات ==========
    function renderReminders() {
      const reminders = allData.filter(d => d.type === 'reminder');
      const priorityColors = { urgent: 'red', today: 'amber', upcoming: 'blue' };
      const priorityIcons = { urgent: '🔴', today: '🟡', upcoming: '🔵' };
      
      document.getElementById('mainContent').innerHTML = `
        <div class="fade-in">
          <div class="flex items-center justify-between mb-6">
            <h2 class="text-xl font-bold">⏰ التذكيرات</h2>
            <button onclick="openModal('addReminderModal'); populateCourses('reminderCourse')" 
              class="px-6 py-3 btn-gold rounded-xl font-bold flex items-center gap-2">
              ➕ إضافة تذكير
            </button>
          </div>
          
          ${reminders.length === 0 ? `
            <div class="card p-12 text-center">
              <span class="text-6xl block mb-4">📭</span>
              <p class="text-gray-500 text-lg">لا توجد تذكيرات</p>
            </div>
          ` : `
            <div class="space-y-4">
              ${reminders.map(r => {
                const color = priorityColors[r.reminder_priority] || 'gray';
                return `
                  <div class="card p-5 reminder-${r.reminder_priority || 'upcoming'} ${r.reminder_completed ? 'opacity-50' : ''}">
                    <div class="flex items-center gap-4">
                      <span class="text-3xl">${priorityIcons[r.reminder_priority] || '📌'}</span>
                      <div class="flex-1">
                        <p class="font-bold text-lg ${r.reminder_completed ? 'line-through' : ''}">${r.reminder_title}</p>
                        <p class="text-sm text-gray-500">${formatDeadline(r.reminder_deadline)}</p>
                      </div>
                      ${!r.reminder_completed ? `
                        <button onclick="completeReminder('${r.__backendId}')" class="px-5 py-2 bg-green-100 text-green-700 rounded-xl font-bold hover:bg-green-200">
                          ✓ إتمام
                        </button>
                      ` : ''}
                      <button onclick="deleteReminder('${r.__backendId}')" class="px-5 py-2 bg-red-100 text-red-700 rounded-xl font-bold hover:bg-red-200">
                        🗑���
                      </button>
                    </div>
                  </div>
                `;
              }).join('')}
            </div>
          `}
        </div>
      `;
    }

    async function completeReminder(id) {
      const reminder = allData.find(d => d.__backendId === id);
      if (reminder) {
        await window.dataSdk.update({ ...reminder, reminder_completed: true });
        showToast('تم إتمام المهمة', '✅', '+5 نقاط');
        if (currentUser.role === 'student') await addPoints(5);
      }
    }

    async function deleteReminder(id) {
      const reminder = allData.find(d => d.__backendId === id);
      if (reminder) {
        await window.dataSdk.delete(reminder);
        showToast('تم حذف التذكير', '✅', '');
      }
    }

    // ========== النماذج ==========
    document.getElementById('contentForm').addEventListener('submit', async function(e) {
      e.preventDefault();
      
      if (allData.length >= 999) {
        showToast('تم الوصول للحد الأقصى', '⚠️', '');
        return;
      }
      
      const btn = this.querySelector('button[type="submit"]');
      btn.innerHTML = '<div class="loading-ring mx-auto"></div>';
      
      const result = await window.dataSdk.create({
        type: 'content',
        course_id: document.getElementById('contentCourse').value,
        content_type: document.getElementById('contentType').value,
        content_title: document.getElementById('contentTitle').value,
        content_url: document.getElementById('contentUrl').value,
        content_description: document.getElementById('contentDesc').value,
        created_at: new Date().toISOString(),
        created_by: currentUser.user_id
      });
      
      btn.innerHTML = 'إضافة المحتوى';
      
      if (result.isOk) {
        showToast('تم إضافة المحتوى', '✅', '');
        closeModal('addContentModal');
        this.reset();
      }
    });

    document.getElementById('reminderForm').addEventListener('submit', async function(e) {
      e.preventDefault();
      
      if (allData.length >= 999) {
        showToast('تم الوصول للحد الأقصى', '⚠️', '');
        return;
      }
      
      const result = await window.dataSdk.create({
        type: 'reminder',
        reminder_title: document.getElementById('reminderTitle').value,
        course_id: document.getElementById('reminderCourse').value,
        reminder_deadline: document.getElementById('reminderDeadline').value,
        reminder_priority: document.getElementById('reminderPriority').value,
        reminder_completed: false,
        created_at: new Date().toISOString(),
        created_by: currentUser.user_id
      });
      
      if (result.isOk) {
        showToast('تم إضافة التذكير', '✅', '');
        closeModal('addReminderModal');
        this.reset();
      }
    });

    // ========== الأدوات المساعدة ==========
    function openModal(id) {
      document.getElementById(id).classList.remove('hidden');
      document.getElementById(id).classList.add('flex');
    }

    function closeModal(id) {
      document.getElementById(id).classList.add('hidden');
      document.getElementById(id).classList.remove('flex');
    }

    function populateCourses(selectId) {
      const select = document.getElementById(selectId);
      select.innerHTML = '<option value="">اختر المقرر</option>' + 
        courses.map(c => `<option value="${c.id}">${c.icon} ${c.name}</option>`).join('');
    }

    function populateStudents(selectId) {
      const students = allData.filter(d => d.type === 'user' && d.role === 'student');
      const select = document.getElementById(selectId);
      select.innerHTML = '<option value="">اختر الطالب</option>' + 
        students.map(s => `<option value="${s.user_id}">${s.name}</option>`).join('');
    }

    function showToast(message, icon = '✅', subMessage = '') {
      const toast = document.getElementById('toast');
      document.getElementById('toastMessage').textContent = message;
      document.getElementById('toastIcon').textContent = icon;
      document.getElementById('toastSubMessage').textContent = subMessage;
      
      toast.style.borderColor = icon === '✅' ? '#22c55e' : icon === '❌' ? '#ef4444' : '#f59e0b';
      toast.classList.add('show');
      setTimeout(() => toast.classList.remove('show'), 4000);
    }

    function formatDate(dateStr) {
      return new Date(dateStr).toLocaleDateString('ar-EG', { 
        weekday: 'long', 
        year: 'numeric', 
        month: 'long', 
        day: 'numeric' 
      });
    }

    function formatDeadline(deadline) {
      if (!deadline) return '';
      const date = new Date(deadline);
      const now = new Date();
      const diff = Math.floor((date - now) / (1000 * 60 * 60 * 24));
      
      if (diff < 0) return '⏰ منتهي';
      if (diff === 0) return '📅 اليوم';
      if (diff === 1) return '📅 غداً';
      return `📅 بعد ${diff} أيام`;
    }

    function startDateTime() {
      function update() {
        const now = new Date();
        const days = ['الأحد', 'الإثنين', 'الثلاثاء', 'الأربعاء', 'الخميس', 'الجمعة', 'السبت'];
        const months = ['يناير', 'فبراير', 'مارس', 'أبريل', 'مايو', 'يونيو', 'يوليو', 'أغسطس', 'سبتمبر', 'أكتوبر', 'نوفمبر', 'ديسمبر'];
        
        const dateEl = document.getElementById('headerDate');
        const timeEl = document.getElementById('headerTime');
        
        if (dateEl) dateEl.textContent = `${days[now.getDay()]}، ${now.getDate()} ${months[now.getMonth()]}`;
        if (timeEl) timeEl.textContent = now.toLocaleTimeString('ar-EG');
      }
      
      update();
      setInterval(update, 1000);
    }

    // وظائف المكافآت
    function openBonusModal(studentId, studentName) {
      document.getElementById('bonusStudentId').value = studentId;
      document.getElementById('bonusStudentName').textContent = studentName;
      document.getElementById('bonusAmount').value = '';
      openModal('bonusModal');
    }

    function setBonusAmount(amount) {
      document.getElementById('bonusAmount').value = amount;
    }

    document.getElementById('bonusForm').addEventListener('submit', async function(e) {
      e.preventDefault();
      
      const studentId = document.getElementById('bonusStudentId').value;
      const amount = parseInt(document.getElementById('bonusAmount').value);
      const reason = document.getElementById('bonusReason').value;
      
      await addBonusPoints(studentId, amount, reason);
      closeModal('bonusModal');
      
      // تحديث الصفحة
      if (document.querySelector('[data-section="students"]')?.classList.contains('active')) {
        renderStudents();
      }
    });

    // تشغيل التطبيق
    initApp();
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9af14a74f0fc7c52',t:'MTc2NTkyMDcyMC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
