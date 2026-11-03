# <!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PRASBHARA JATINEGARA (SBK JATNER) - Official Web & Database System</title>
    
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts: Poppins -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">

    <style>
        body {
            font-family: 'Poppins', sans-serif;
            background-color: #0f172a;
            color: #f8fafc;
        }
        .bg-prasbhara {
            background: linear-gradient(135deg, #1e293b 0%, #0f172a 100%);
        }
        .card-gold-glow {
            box-shadow: 0 0 15px rgba(234, 179, 8, 0.15);
            border: 1px solid rgba(234, 179, 8, 0.2);
        }
        .card-gold-glow:hover {
            box-shadow: 0 0 25px rgba(234, 179, 8, 0.3);
            border-color: rgba(234, 179, 8, 0.5);
        }
        .custom-scrollbar::-webkit-scrollbar {
            width: 6px;
            height: 6px;
        }
        .custom-scrollbar::-webkit-scrollbar-track {
            background: #1e293b;
        }
        .custom-scrollbar::-webkit-scrollbar-thumb {
            background: #eab308;
            border-radius: 4px;
        }
    </style>
</head>
<body class="min-h-screen flex flex-col justify-between selection:bg-yellow-500 selection:text-slate-900">

    <!-- NAVBAR HEADER -->
    <header class="sticky top-0 z-40 bg-slate-900/90 backdrop-blur-md border-b border-slate-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between">
            <!-- Logo & Brand -->
            <div class="flex items-center space-x-3">
                <div id="nav-logo-container" class="w-12 h-12 rounded-full bg-yellow-500/20 border-2 border-yellow-500 flex items-center justify-center overflow-hidden">
                    <i class="fa-solid fa-shield-halved text-yellow-500 text-2xl"></i>
                </div>
                <div>
                    <h1 id="brand-title" class="text-lg font-bold text-yellow-500 leading-tight">PRASBHARA JATINEGARA</h1>
                    <p id="brand-subtitle" class="text-xs text-slate-400">Pramuka Saka Bhayangkara Jatinegara</p>
                </div>
            </div>

            <!-- Navigation Links -->
            <nav class="hidden md:flex items-center space-x-6">
                <a href="#home" class="text-sm font-medium hover:text-yellow-500 transition">Beranda</a>
                <a href="#krida" class="text-sm font-medium hover:text-yellow-500 transition">Daftar Krida</a>
                <a href="#recap" class="text-sm font-medium hover:text-yellow-500 transition">Recap Kegiatan</a>
                <button onclick="openRegistrationModal()" class="px-4 py-2 text-xs font-semibold rounded-lg bg-yellow-500 text-slate-950 hover:bg-yellow-400 transition shadow-lg shadow-yellow-500/20">
                    <i class="fa-solid fa-user-plus mr-1"></i> Daftar Anggota
                </button>
            </nav>

            <!-- Admin Button -->
            <div class="flex items-center space-x-2">
                <button onclick="checkAdminStatusAndOpen()" class="px-3 py-2 text-xs font-medium rounded-lg bg-slate-800 border border-slate-700 hover:bg-slate-700 text-slate-300 transition flex items-center space-x-2">
                    <i class="fa-solid fa-user-shield text-yellow-500"></i>
                    <span id="nav-admin-btn-text">Login Admin</span>
                </button>
            </div>
        </div>
    </header>

    <!-- HERO BANNER -->
    <section id="home" class="relative py-16 md:py-24 bg-gradient-to-b from-slate-900 via-slate-800 to-slate-900 border-b border-slate-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col md:flex-row items-center justify-between gap-12">
            <div class="md:w-1/2 space-y-6 text-center md:text-left">
                <div class="inline-flex items-center space-x-2 bg-yellow-500/10 border border-yellow-500/30 px-3 py-1 rounded-full text-yellow-500 text-xs font-semibold">
                    <i class="fa-solid fa-award"></i>
                    <span id="hero-badge">OFFICIAL PORTAL - SBK JATNER</span>
                </div>
                <h2 id="hero-title" class="text-3xl sm:text-4xl lg:text-5xl font-extrabold text-white leading-tight">
                    Mewujudkan Generasi Muda <span class="text-yellow-500">Tangguh & Pelopor</span> Kamtibmas
                </h2>
                <p id="hero-desc" class="text-slate-400 text-sm md:text-base leading-relaxed">
                    Satu Wadah Pembinaan Pramuka Penegak dan Pandega dalam bidang Kehayangkaraan di bawah naungan Polsek Jatinegara & Kwarran Jatinegara.
                </p>
                <div class="flex flex-wrap justify-center md:justify-start gap-4">
                    <button onclick="openRegistrationModal()" class="px-6 py-3 rounded-xl bg-yellow-500 text-slate-950 font-bold hover:bg-yellow-400 transition shadow-lg shadow-yellow-500/20 text-sm">
                        <i class="fa-solid fa-paper-plane mr-2"></i> Daftar Sekarang
                    </button>
                    <a id="ig-link-btn" href="https://www.instagram.com/saka.bhayangkarajatinegara" target="_blank" class="px-6 py-3 rounded-xl bg-slate-800 border border-slate-700 text-slate-200 font-semibold hover:bg-slate-700 transition text-sm flex items-center">
                        <i class="fa-brands fa-instagram text-pink-500 text-lg mr-2"></i> Instagram Resmi
                    </a>
                </div>
            </div>

            <!-- Profile Avatar Card -->
            <div class="md:w-1/2 flex justify-center">
                <div class="relative w-64 h-64 sm:w-80 sm:h-80 rounded-2xl bg-gradient-to-tr from-yellow-500/20 to-slate-800 p-2 card-gold-glow flex flex-col items-center justify-center text-center">
                    <div id="hero-logo-large" class="w-28 h-28 sm:w-36 sm:h-36 rounded-full bg-slate-900 border-4 border-yellow-500 flex items-center justify-center overflow-hidden mb-4 shadow-xl">
                        <i class="fa-solid fa-shield-halved text-yellow-500 text-5xl"></i>
                    </div>
                    <h3 id="card-hero-title" class="font-bold text-lg text-white">PRASBHARA JATINEGARA</h3>
                    <p id="card-hero-sub" class="text-xs text-yellow-500 font-medium">SBK JATNER • JATINEGARA</p>
                </div>
            </div>
        </div>
    </section>

    <!-- SECTION KRIDA -->
    <section id="krida" class="py-16 bg-slate-950 border-b border-slate-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-2xl mx-auto mb-12">
                <h2 class="text-2xl sm:text-3xl font-bold text-white">Daftar Krida SBK JATNER</h2>
                <p class="text-slate-400 text-sm mt-2">Bidang keahlian dan spesialisasi pembinaan di Prasbhara Jatinegara</p>
            </div>

            <div id="krida-container" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
                <!-- Krida Cards Rendered Dynamically -->
            </div>
        </div>
    </section>

    <!-- SECTION RECAP KEGIATAN INSTAGRAM -->
    <section id="recap" class="py-16 bg-slate-900 border-b border-slate-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex flex-col md:flex-row md:items-center justify-between mb-8">
                <div>
                    <h2 class="text-2xl sm:text-3xl font-bold text-white">Recap Kegiatan Feed</h2>
                    <p class="text-slate-400 text-sm mt-1">Dokumentasi & postingan resmi @saka.bhayangkarajatinegara</p>
                </div>
                <!-- Live Sync Status Widget -->
                <div class="mt-4 md:mt-0 flex items-center space-x-3 bg-slate-800 px-4 py-2 rounded-xl border border-slate-700">
                    <span class="relative flex h-3 w-3">
                      <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-emerald-400 opacity-75"></span>
                      <span class="relative inline-flex rounded-full h-3 w-3 bg-emerald-500"></span>
                    </span>
                    <span class="text-xs text-slate-300 font-medium">IG Sync: <span id="sync-status-text" class="text-emerald-400 font-bold">Connected</span></span>
                    <button onclick="triggerManualSync()" class="text-xs text-yellow-500 hover:underline font-semibold ml-2">
                        <i class="fa-solid fa-rotate mr-1"></i> Sync
                    </button>
                </div>
            </div>

            <div id="recap-container" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <!-- IG Recap Posts Rendered Dynamically -->
            </div>
        </div>
    </section>

    <!-- FOOTER -->
    <footer class="bg-slate-950 py-8 border-t border-slate-800 text-center text-xs text-slate-500">
        <div class="max-w-7xl mx-auto px-4">
            <p>© 2026 PRASBHARA JATINEGARA (SBK JATNER). All Rights Reserved.</p>
        </div>
    </footer>

    <!-- MODAL PENDAFTARAN -->
    <div id="reg-modal" class="fixed inset-0 z-50 bg-black/75 backdrop-blur-sm hidden flex items-center justify-center p-4 overflow-y-auto">
        <div class="bg-slate-900 border border-slate-700 rounded-2xl max-w-lg w-full p-6 space-y-4 relative my-8">
            <button onclick="closeRegistrationModal()" class="absolute top-4 right-4 text-slate-400 hover:text-white">
                <i class="fa-solid fa-xmark text-xl"></i>
            </button>
            <div class="text-center">
                <h3 class="text-xl font-bold text-white">Formulir Pendaftaran</h3>
                <p class="text-xs text-slate-400">Calon Anggota PRASBHARA JATINEGARA</p>
            </div>

            <form id="reg-form" onsubmit="handleRegistrationSubmit(event)" class="space-y-3">
                <div>
                    <label class="block text-xs font-medium text-slate-300 mb-1">Nama Lengkap</label>
                    <input type="text" id="reg-nama" required class="w-full bg-slate-800 border border-slate-700 rounded-lg px-3 py-2 text-sm text-white focus:outline-none focus:border-yellow-500" placeholder="Masukkan nama lengkap">
                </div>
                <div class="grid grid-cols-2 gap-3">
                    <div>
                        <label class="block text-xs font-medium text-slate-300 mb-1">Umur (Tahun)</label>
                        <input type="number" id="reg-umur" required class="w-full bg-slate-800 border border-slate-700 rounded-lg px-3 py-2 text-sm text-white focus:outline-none focus:border-yellow-500" placeholder="Contoh: 16">
                    </div>
                    <div>
                        <label class="block text-xs font-medium text-slate-300 mb-1">Asal Sekolah</label>
                        <input type="text" id="reg-sekolah" required class="w-full bg-slate-800 border border-slate-700 rounded-lg px-3 py-2 text-sm text-white focus:outline-none focus:border-yellow-500" placeholder="SMA / SMK / MA">
                    </div>
                </div>
                <div>
                    <label class="block text-xs font-medium text-slate-300 mb-1">Tempat, Tanggal Lahir (TTL)</label>
                    <input type="text" id="reg-ttl" required class="w-full bg-slate-800 border border-slate-700 rounded-lg px-3 py-2 text-sm text-white focus:outline-none focus:border-yellow-500" placeholder="Jakarta, 12 Januari 2008">
                </div>
                <div>
                    <label class="block text-xs font-medium text-slate-300 mb-1">Alamat Lengkap</label>
                    <textarea id="reg-alamat" rows="2" required class="w-full bg-slate-800 border border-slate-700 rounded-lg px-3 py-2 text-sm text-white focus:outline-none focus:border-yellow-500" placeholder="Alamat rumah lengkap"></textarea>
                </div>
                <div>
                    <label class="block text-xs font-medium text-slate-300 mb-1">Pas Foto (Format Gambar)</label>
                    <input type="file" id="reg-foto" accept="image/*" onchange="previewPhotoInput(this)" class="w-full text-xs text-slate-400 file:mr-4 file:py-2 file:px-4 file:rounded-lg file:border-0 file:text-xs file:font-semibold file:bg-yellow-500 file:text-slate-950 hover:file:bg-yellow-400">
                    <div id="foto-preview-container" class="mt-2 hidden flex justify-center">
                        <img id="foto-preview" class="w-20 h-24 object-cover rounded border border-yellow-500">
                    </div>
                </div>
                <button type="submit" class="w-full py-3 bg-yellow-500 text-slate-950 font-bold rounded-xl hover:bg-yellow-400 transition text-sm shadow-lg shadow-yellow-500/20 mt-2">
                    <i class="fa-solid fa-paper-plane mr-1"></i> Kirim Pendaftaran
                </button>
            </form>
        </div>
    </div>

    <!-- MODAL LOGIN ADMIN -->
    <div id="login-modal" class="fixed inset-0 z-50 bg-black/80 backdrop-blur-sm hidden flex items-center justify-center p-4">
        <div class="bg-slate-900 border border-slate-700 rounded-2xl max-w-sm w-full p-6 space-y-4 relative">
            <button onclick="closeLoginModal()" class="absolute top-4 right-4 text-slate-400 hover:text-white">
                <i class="fa-solid fa-xmark text-xl"></i>
            </button>
            <div class="text-center">
                <div class="w-12 h-12 bg-yellow-500/20 text-yellow-500 rounded-full flex items-center justify-center mx-auto mb-2">
                    <i class="fa-solid fa-lock text-xl"></i>
                </div>
                <h3 class="text-xl font-bold text-white">Login Administrator</h3>
                <p class="text-xs text-slate-400">Masuk untuk mengelola database pendaftaran SBK JATNER</p>
            </div>

            <form onsubmit="handleLoginSubmit(event)" class="space-y-3">
                <div>
                    <label class="block text-xs font-medium text-slate-300 mb-1">Username</label>
                    <input type="text" id="login-user" required class="w-full bg-slate-800 border border-slate-700 rounded-lg px-3 py-2 text-sm text-white focus:outline-none focus:border-yellow-500">
                </div>
                <div>
                    <label class="block text-xs font-medium text-slate-300 mb-1">Password</label>
                    <input type="password" id="login-pass" required class="w-full bg-slate-800 border border-slate-700 rounded-lg px-3 py-2 text-sm text-white focus:outline-none focus:border-yellow-500">
                </div>
                <button type="submit" class="w-full py-2.5 bg-yellow-500 text-slate-950 font-bold rounded-xl hover:bg-yellow-400 transition text-sm">
                    Masuk Admin
                </button>
            </form>
        </div>
    </div>

    <!-- MODAL ADMIN DASHBOARD -->
    <div id="admin-dashboard-modal" class="fixed inset-0 z-50 bg-black/90 backdrop-blur-md hidden flex flex-col p-4 md:p-8">
        <div class="bg-slate-900 border border-slate-800 rounded-2xl flex-1 flex flex-col overflow-hidden max-w-7xl mx-auto w-full">
            <!-- Header Admin -->
            <div class="p-4 border-b border-slate-800 flex items-center justify-between bg-slate-950">
                <div class="flex items-center space-x-3">
                    <i class="fa-solid fa-sliders text-yellow-500 text-xl"></i>
                    <h3 class="font-bold text-white text-base md:text-lg">Admin Control Center - SBK JATNER</h3>
                </div>
                <div class="flex items-center space-x-2">
                    <button onclick="adminLogout()" class="px-3 py-1.5 bg-red-500/20 text-red-400 border border-red-500/30 rounded-lg text-xs font-medium hover:bg-red-500/30 transition">
                        <i class="fa-solid fa-right-from-bracket mr-1"></i> Logout
                    </button>
                    <button onclick="closeAdminDashboard()" class="text-slate-400 hover:text-white p-2">
                        <i class="fa-solid fa-xmark text-xl"></i>
                    </button>
                </div>
            </div>

            <!-- Tabs Admin -->
            <div class="bg-slate-800/50 p-2 border-b border-slate-800 flex space-x-2 overflow-x-auto custom-scrollbar">
                <button onclick="switchAdminTab('db')" id="tab-btn-db" class="px-4 py-2 rounded-lg text-xs font-bold bg-yellow-500 text-slate-950">Database Pendaftar</button>
                <button onclick="switchAdminTab('krida')" id="tab-btn-krida" class="px-4 py-2 rounded-lg text-xs font-bold text-slate-300 hover:bg-slate-700">Kelola Krida</button>
                <button onclick="switchAdminTab('profil')" id="tab-btn-profil" class="px-4 py-2 rounded-lg text-xs font-bold text-slate-300 hover:bg-slate-700">Ubah Profil Web</button>
                <button onclick="switchAdminTab('sync')" id="tab-btn-sync" class="px-4 py-2 rounded-lg text-xs font-bold text-slate-300 hover:bg-slate-700">Auto-Sync IG</button>
            </div>

            <!-- Tab Content Body -->
            <div class="flex-1 overflow-y-auto p-4 md:p-6 custom-scrollbar">
                <!-- TAB 1: DATABASE -->
                <div id="tab-content-db" class="space-y-4">
                    <div class="flex flex-col md:flex-row justify-between items-center gap-4">
                        <h4 class="font-bold text-white text-sm">Data Pendaftaran Masuk (<span id="db-count">0</span>)</h4>
                        <div class="flex items-center space-x-2">
                            <button onclick="exportToCSV()" class="px-3 py-2 bg-emerald-600 text-white rounded-lg text-xs font-semibold hover:bg-emerald-500 transition">
                                <i class="fa-solid fa-file-excel mr-1"></i> Ekspor CSV
                            </button>
                            <button onclick="clearAllData()" class="px-3 py-2 bg-red-600/30 text-red-400 border border-red-500/30 rounded-lg text-xs font-semibold hover:bg-red-600 hover:text-white transition">
                                Clear All
                            </button>
                        </div>
                    </div>
                    <div class="overflow-x-auto border border-slate-800 rounded-xl">
                        <table class="w-full text-left text-xs text-slate-300">
                            <thead class="bg-slate-950 text-slate-400 uppercase font-semibold">
                                <tr>
                                    <th class="p-3">Foto</th>
                                    <th class="p-3">Nama Lengkap</th>
                                    <th class="p-3">Umur</th>
                                    <th class="p-3">Asal Sekolah</th>
                                    <th class="p-3">TTL</th>
                                    <th class="p-3">Alamat</th>
                                    <th class="p-3 text-right">Aksi</th>
                                </tr>
                            </thead>
                            <tbody id="db-table-body" class="divide-y divide-slate-800 bg-slate-900/50">
                                <!-- Data rows -->
                            </tbody>
                        </table>
                    </div>
                </div>

                <!-- TAB 2: KELOLA KRIDA -->
                <div id="tab-content-krida" class="hidden space-y-6">
                    <div class="flex justify-between items-center">
                        <h4 class="font-bold text-white text-sm">Kelola Daftar Krida PRASBHARA</h4>
                        <button onclick="add