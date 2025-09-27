<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PT Maju Bersama - Beranda</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body {
            box-sizing: border-box;
        }
        .gradient-bg {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }
        .card-shadow {
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }
        .error-message {
            display: none;
            color: #ef4444;
            font-size: 0.875rem;
            margin-top: 0.25rem;
        }
        .success-message {
            display: none;
            background-color: #10b981;
            color: white;
            padding: 1rem;
            border-radius: 0.5rem;
            margin-bottom: 1rem;
        }
        .form-data-display {
            display: none;
            background-color: #f3f4f6;
            border: 1px solid #d1d5db;
            border-radius: 0.5rem;
            padding: 1rem;
            margin-top: 1rem;
        }
        .mobile-menu {
            display: none;
        }
        .mobile-menu.active {
            display: block;
        }
        .page-section {
            display: none;
        }
        .page-section.active {
            display: block;
        }
        .hero-banner {
            background: linear-gradient(rgba(102, 126, 234, 0.8), rgba(118, 75, 162, 0.8)), 
                        url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 600"><rect fill="%23f0f9ff" width="1200" height="600"/><circle fill="%23dbeafe" cx="200" cy="150" r="80"/><circle fill="%23bfdbfe" cx="800" cy="300" r="120"/><circle fill="%23dbeafe" cx="1000" cy="100" r="60"/><rect fill="%23bfdbfe" x="300" y="400" width="200" height="100" rx="10"/><rect fill="%23dbeafe" x="600" y="450" width="150" height="80" rx="8"/></svg>');
            background-size: cover;
            background-position: center;
        }
        .profile-banner {
            background: linear-gradient(rgba(16, 185, 129, 0.8), rgba(5, 150, 105, 0.8)), 
                        url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 400"><rect fill="%23ecfdf5" width="1200" height="400"/><polygon fill="%23d1fae5" points="0,400 300,300 600,350 900,250 1200,300 1200,400"/><circle fill="%23a7f3d0" cx="150" cy="100" r="40"/><circle fill="%23bbf7d0" cx="450" cy="150" r="60"/><circle fill="%23a7f3d0" cx="750" cy="80" r="35"/><circle fill="%23bbf7d0" cx="1050" cy="120" r="50"/></svg>');
            background-size: cover;
            background-position: center;
        }
    </style>
</head>
<body class="bg-gray-50 font-sans">
    <!-- Navigation -->
    <nav class="bg-white shadow-lg sticky top-0 z-50">
        <div class="container mx-auto px-6">
            <div class="flex justify-between items-center py-4">
                <div class="text-2xl font-bold text-gray-800">PT Maju Bersama</div>
                
                <!-- Desktop Menu -->
                <div class="hidden md:flex space-x-8">
                    <a href="#" onclick="showPage('home')" class="nav-link text-gray-700 hover:text-blue-600 transition duration-200 font-medium">Home</a>
                    <a href="#" onclick="showPage('profile')" class="nav-link text-gray-700 hover:text-blue-600 transition duration-200 font-medium">Our Profile</a>
                    <a href="#" onclick="showPage('services')" class="nav-link text-gray-700 hover:text-blue-600 transition duration-200 font-medium">Services</a>
                    <a href="#" onclick="showPage('contact')" class="nav-link text-gray-700 hover:text-blue-600 transition duration-200 font-medium">Contact</a>
                </div>
                
                <!-- Mobile Menu Button -->
                <div class="md:hidden">
                    <button onclick="toggleMobileMenu()" class="text-gray-700 hover:text-blue-600">
                        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
                        </svg>
                    </button>
                </div>
            </div>
            
            <!-- Mobile Menu -->
            <div id="mobileMenu" class="mobile-menu md:hidden pb-4">
                <a href="#" onclick="showPage('home')" class="block py-2 text-gray-700 hover:text-blue-600 transition duration-200">Home</a>
                <a href="#" onclick="showPage('profile')" class="block py-2 text-gray-700 hover:text-blue-600 transition duration-200">Our Profile</a>
                <a href="#" onclick="showPage('services')" class="block py-2 text-gray-700 hover:text-blue-600 transition duration-200">Services</a>
                <a href="#" onclick="showPage('contact')" class="block py-2 text-gray-700 hover:text-blue-600 transition duration-200">Contact</a>
            </div>
        </div>
    </nav>

    <!-- Home Page -->
    <div id="homePage" class="page-section active">
        <!-- Hero Section -->
        <section class="hero-banner text-white py-20 md:py-32">
            <div class="container mx-auto px-6 text-center">
                <div class="mb-6">
                    <h1 id="welcomeMessage" class="text-3xl md:text-5xl lg:text-6xl font-bold mb-4">Hi Guest!</h1>
                    <p class="text-lg md:text-xl lg:text-2xl opacity-90 mb-8">Selamat datang di PT Maju Bersama</p>
                </div>
                <div class="mb-8">
                    <input type="text" id="nameInput" placeholder="Masukkan nama Anda" 
                           class="px-4 py-2 rounded-lg text-gray-800 mr-2 mb-2 md:mb-0 w-full md:w-auto">
                    <button onclick="updateWelcome()" 
                            class="bg-white text-blue-600 px-6 py-2 rounded-lg font-semibold hover:bg-gray-100 transition duration-200 w-full md:w-auto">
                        Update Sambutan
                    </button>
                </div>
                <p class="text-lg md:text-xl opacity-90">Solusi Terpercaya untuk Masa Depan yang Lebih Baik</p>
            </div>
        </section>

        <!-- Quick Info Section -->
        <section class="py-16 bg-white">
            <div class="container mx-auto px-6">
                <div class="grid md:grid-cols-3 gap-8">
                    <div class="text-center p-6">
                        <div class="bg-blue-100 w-16 h-16 rounded-full flex items-center justify-center mx-auto mb-4">
                            <span class="text-2xl">🏢</span>
                        </div>
                        <h3 class="text-xl font-semibold mb-2">15+ Tahun</h3>
                        <p class="text-gray-600">Pengalaman dalam industri</p>
                    </div>
                    <div class="text-center p-6">
                        <div class="bg-green-100 w-16 h-16 rounded-full flex items-center justify-center mx-auto mb-4">
                            <span class="text-2xl">👥</span>
                        </div>
                        <h3 class="text-xl font-semibold mb-2">500+ Klien</h3>
                        <p class="text-gray-600">Telah mempercayai layanan kami</p>
                    </div>
                    <div class="text-center p-6">
                        <div class="bg-purple-100 w-16 h-16 rounded-full flex items-center justify-center mx-auto mb-4">
                            <span class="text-2xl">🎯</span>
                        </div>
                        <h3 class="text-xl font-semibold mb-2">100%</h3>
                        <p class="text-gray-600">Komitmen kepuasan pelanggan</p>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- Profile Page -->
    <div id="profilePage" class="page-section">
        <!-- Profile Banner -->
        <section class="profile-banner text-white py-20 md:py-24">
            <div class="container mx-auto px-6 text-center">
                <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold mb-4">Profil Perusahaan</h1>
                <p class="text-lg md:text-xl opacity-90">Mengenal Lebih Dekat PT Maju Bersama</p>
            </div>
        </section>

        <!-- About Company -->
        <section class="py-16 bg-white">
            <div class="container mx-auto px-6">
                <div class="max-w-4xl mx-auto">
                    <h2 class="text-3xl md:text-4xl font-bold text-center text-gray-800 mb-12">Tentang Perusahaan</h2>
                    
                    <div class="grid lg:grid-cols-2 gap-12 items-center mb-16">
                        <div>
                            <h3 class="text-2xl font-semibold mb-6 text-gray-800">Sejarah Singkat</h3>
                            <p class="text-gray-600 mb-4 leading-relaxed">
                                PT Maju Bersama didirikan pada tahun 2009 dengan visi menjadi perusahaan terdepan dalam memberikan solusi inovatif. 
                                Berawal dari sebuah startup kecil dengan 5 karyawan, kini kami telah berkembang menjadi perusahaan dengan lebih dari 200 profesional berpengalaman.
                            </p>
                            <p class="text-gray-600 leading-relaxed">
                                Perjalanan kami dimulai dari keinginan sederhana untuk membantu bisnis berkembang melalui teknologi dan strategi yang tepat. 
                                Kini, kami bangga telah melayani lebih dari 500 klien dari berbagai industri di seluruh Indonesia.
                            </p>
                        </div>
                        <div class="bg-gradient-to-br from-green-400 to-blue-500 p-8 rounded-lg text-white">
                            <h4 class="text-xl font-semibold mb-4">Pencapaian Kami</h4>
                            <ul class="space-y-3">
                                <li class="flex items-center">
                                    <span class="mr-3">✅</span>
                                    <span>ISO 9001:2015 Certified</span>
                                </li>
                                <li class="flex items-center">
                                    <span class="mr-3">✅</span>
                                    <span>Best Innovation Award 2023</span>
                                </li>
                                <li class="flex items-center">
                                    <span class="mr-3">✅</span>
                                    <span>Top 100 Companies Indonesia</span>
                                </li>
                                <li class="flex items-center">
                                    <span class="mr-3">✅</span>
                                    <span>Customer Satisfaction 98%</span>
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Vision & Mission -->
        <section class="py-16 bg-gray-100">
            <div class="container mx-auto px-6">
                <h2 class="text-3xl md:text-4xl font-bold text-center text-gray-800 mb-12">Visi & Misi Perusahaan</h2>
                
                <div class="grid lg:grid-cols-2 gap-8 max-w-6xl mx-auto">
                    <!-- Vision -->
                    <div class="bg-white p-8 rounded-lg card-shadow">
                        <div class="text-center mb-6">
                            <div class="bg-blue-100 w-20 h-20 rounded-full flex items-center justify-center mx-auto mb-4">
                                <span class="text-3xl">🎯</span>
                            </div>
                            <h3 class="text-2xl font-bold text-gray-800">Visi</h3>
                        </div>
                        <p class="text-gray-600 text-center leading-relaxed text-lg">
                            "Menjadi perusahaan teknologi terdepan di Indonesia yang memberikan solusi inovatif dan berkelanjutan 
                            untuk membantu transformasi digital bisnis menuju masa depan yang lebih baik."
                        </p>
                    </div>

                    <!-- Mission -->
                    <div class="bg-white p-8 rounded-lg card-shadow">
                        <div class="text-center mb-6">
                            <div class="bg-green-100 w-20 h-20 rounded-full flex items-center justify-center mx-auto mb-4">
                                <span class="text-3xl">🚀</span>
                            </div>
                            <h3 class="text-2xl font-bold text-gray-800">Misi</h3>
                        </div>
                        <ul class="text-gray-600 space-y-3">
                            <li class="flex items-start">
                                <span class="text-green-500 mr-3 mt-1">•</span>
                                <span>Memberikan layanan berkualitas tinggi dengan teknologi terdepan</span>
                            </li>
                            <li class="flex items-start">
                                <span class="text-green-500 mr-3 mt-1">•</span>
                                <span>Mengembangkan solusi inovatif yang sesuai kebutuhan klien</span>
                            </li>
                            <li class="flex items-start">
                                <span class="text-green-500 mr-3 mt-1">•</span>
                                <span>Membangun kemitraan jangka panjang yang saling menguntungkan</span>
                            </li>
                            <li class="flex items-start">
                                <span class="text-green-500 mr-3 mt-1">•</span>
                                <span>Berkontribusi positif bagi kemajuan teknologi di Indonesia</span>
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <!-- Company Values -->
        <section class="py-16 bg-white">
            <div class="container mx-auto px-6">
                <h2 class="text-3xl md:text-4xl font-bold text-center text-gray-800 mb-12">Nilai-Nilai Perusahaan</h2>
                
                <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8 max-w-6xl mx-auto">
                    <div class="text-center p-6">
                        <div class="bg-purple-100 w-16 h-16 rounded-full flex items-center justify-center mx-auto mb-4">
                            <span class="text-2xl">⭐</span>
                        </div>
                        <h3 class="text-xl font-semibold mb-3 text-gray-800">Integritas</h3>
                        <p class="text-gray-600">Berkomitmen pada kejujuran dan transparansi dalam setiap tindakan</p>
                    </div>
                    
                    <div class="text-center p-6">
                        <div class="bg-yellow-100 w-16 h-16 rounded-full flex items-center justify-center mx-auto mb-4">
                            <span class="text-2xl">💡</span>
                        </div>
                        <h3 class="text-xl font-semibold mb-3 text-gray-800">Inovasi</h3>
                        <p class="text-gray-600">Selalu mencari cara baru dan kreatif untuk memberikan solusi terbaik</p>
                    </div>
                    
                    <div class="text-center p-6">
                        <div class="bg-red-100 w-16 h-16 rounded-full flex items-center justify-center mx-auto mb-4">
                            <span class="text-2xl">❤️</span>
                        </div>
                        <h3 class="text-xl font-semibold mb-3 text-gray-800">Kepuasan Pelanggan</h3>
                        <p class="text-gray-600">Mengutamakan kepuasan dan kesuksesan klien sebagai prioritas utama</p>
                    </div>
                    
                    <div class="text-center p-6">
                        <div class="bg-indigo-100 w-16 h-16 rounded-full flex items-center justify-center mx-auto mb-4">
                            <span class="text-2xl">🤝</span>
                        </div>
                        <h3 class="text-xl font-semibold mb-3 text-gray-800">Kolaborasi</h3>
                        <p class="text-gray-600">Membangun kerjasama yang solid dengan tim dan mitra bisnis</p>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- Services Page -->
    <div id="servicesPage" class="page-section">
        <section class="gradient-bg text-white py-20 md:py-24">
            <div class="container mx-auto px-6 text-center">
                <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold mb-4">Layanan Kami</h1>
                <p class="text-lg md:text-xl opacity-90">Solusi Komprehensif untuk Kebutuhan Bisnis Anda</p>
            </div>
        </section>

        <section class="py-16 bg-white">
            <div class="container mx-auto px-6">
                <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                    <div class="bg-white p-8 rounded-lg card-shadow hover:transform hover:scale-105 transition duration-300">
                        <div class="text-4xl mb-6">💼</div>
                        <h3 class="text-2xl font-semibold mb-4 text-gray-800">Konsultasi Bisnis</h3>
                        <p class="text-gray-600 mb-4">Memberikan solusi strategis untuk mengoptimalkan operasional bisnis Anda dengan pendekatan yang komprehensif.</p>
                        <ul class="text-sm text-gray-500 space-y-2">
                            <li>• Analisis proses bisnis</li>
                            <li>• Strategi pengembangan</li>
                            <li>• Optimasi operasional</li>
                        </ul>
                    </div>
                    
                    <div class="bg-white p-8 rounded-lg card-shadow hover:transform hover:scale-105 transition duration-300">
                        <div class="text-4xl mb-6">🔧</div>
                        <h3 class="text-2xl font-semibold mb-4 text-gray-800">Solusi Teknologi</h3>
                        <p class="text-gray-600 mb-4">Implementasi teknologi terdepan untuk meningkatkan efisiensi dan produktivitas perusahaan Anda.</p>
                        <ul class="text-sm text-gray-500 space-y-2">
                            <li>• Pengembangan aplikasi</li>
                            <li>• Sistem manajemen</li>
                            <li>• Integrasi teknologi</li>
                        </ul>
                    </div>
                    
                    <div class="bg-white p-8 rounded-lg card-shadow hover:transform hover:scale-105 transition duration-300">
                        <div class="text-4xl mb-6">📊</div>
                        <h3 class="text-2xl font-semibold mb-4 text-gray-800">Analisis Data</h3>
                        <p class="text-gray-600 mb-4">Mengubah data menjadi insight yang dapat mendorong pertumbuhan bisnis dan pengambilan keputusan yang tepat.</p>
                        <ul class="text-sm text-gray-500 space-y-2">
                            <li>• Business Intelligence</li>
                            <li>• Data visualization</li>
                            <li>• Predictive analytics</li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- Contact Page -->
    <div id="contactPage" class="page-section">
        <section class="gradient-bg text-white py-20 md:py-24">
            <div class="container mx-auto px-6 text-center">
                <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold mb-4">Hubungi Kami</h1>
                <p class="text-lg md:text-xl opacity-90">Kami Siap Mendengar dan Membantu Anda</p>
            </div>
        </section>

        <section class="py-16 bg-white">
            <div class="container mx-auto px-6">
                <div class="max-w-4xl mx-auto">
                    <div class="grid lg:grid-cols-2 gap-12">
                        <!-- Contact Info -->
                        <div>
                            <h2 class="text-3xl font-bold text-gray-800 mb-8">Informasi Kontak</h2>
                            <div class="space-y-6">
                                <div class="flex items-start">
                                    <div class="bg-blue-100 p-3 rounded-lg mr-4">
                                        <span class="text-xl">📍</span>
                                    </div>
                                    <div>
                                        <h3 class="font-semibold text-gray-800">Alamat</h3>
                                        <p class="text-gray-600">Jl. Sudirman No. 123, Jakarta Pusat 10220</p>
                                    </div>
                                </div>
                                
                                <div class="flex items-start">
                                    <div class="bg-green-100 p-3 rounded-lg mr-4">
                                        <span class="text-xl">📞</span>
                                    </div>
                                    <div>
                                        <h3 class="font-semibold text-gray-800">Telepon</h3>
                                        <p class="text-gray-600">(021) 1234-5678</p>
                                    </div>
                                </div>
                                
                                <div class="flex items-start">
                                    <div class="bg-purple-100 p-3 rounded-lg mr-4">
                                        <span class="text-xl">📧</span>
                                    </div>
                                    <div>
                                        <h3 class="font-semibold text-gray-800">Email</h3>
                                        <p class="text-gray-600">info@majubersama.co.id</p>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <!-- Contact Form -->
                        <div>
                            <h2 class="text-3xl font-bold text-gray-800 mb-8">Message Us</h2>
                            
                            <div id="successMessage" class="success-message">
                                Terima kasih! Pesan Anda telah berhasil dikirim. Tim kami akan segera menghubungi Anda.
                            </div>
                            
                            <div id="formDataDisplay" class="form-data-display">
                                <h3 class="font-semibold text-gray-800 mb-3">Data yang Dikirim:</h3>
                                <div id="displayedData"></div>
                            </div>
                            
                            <form id="contactForm" novalidate class="space-y-6">
                                <div>
                                    <label for="nama" class="block text-sm font-medium text-gray-700 mb-2">Nama Lengkap *</label>
                                    <input type="text" id="nama" name="nama" 
                                           class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent transition duration-200"
                                           placeholder="Masukkan nama lengkap Anda">
                                    <div id="namaError" class="error-message">Nama lengkap wajib diisi</div>
                                </div>

                                <div>
                                    <label for="email" class="block text-sm font-medium text-gray-700 mb-2">Email *</label>
                                    <input type="email" id="email" name="email" 
                                           class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent transition duration-200"
                                           placeholder="contoh@email.com">
                                    <div id="emailError" class="error-message">Email yang valid wajib diisi</div>
                                </div>

                                <div>
                                    <label for="telepon" class="block text-sm font-medium text-gray-700 mb-2">Nomor Telepon *</label>
                                    <input type="tel" id="telepon" name="telepon" 
                                           class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent transition duration-200"
                                           placeholder="08xxxxxxxxxx">
                                    <div id="teleponError" class="error-message">Nomor telepon yang valid wajib diisi</div>
                                </div>

                                <div>
                                    <label for="pesan" class="block text-sm font-medium text-gray-700 mb-2">Pesan *</label>
                                    <textarea id="pesan" name="pesan" rows="5" 
                                              class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent transition duration-200 resize-vertical"
                                              placeholder="Tuliskan pertanyaan atau kebutuhan Anda di sini..."></textarea>
                                    <div id="pesanError" class="error-message">Pesan wajib diisi (minimal 10 karakter)</div>
                                </div>

                                <button type="submit" 
                                        class="w-full bg-gradient-to-r from-blue-600 to-purple-600 text-white py-3 px-6 rounded-lg font-semibold hover:from-blue-700 hover:to-purple-700 transform hover:scale-105 transition duration-200 shadow-lg">
                                    Kirim Pesan
                                </button>
                            </form>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- Footer -->
    <footer class="bg-gray-800 text-white py-12">
        <div class="container mx-auto px-6">
            <div class="grid md:grid-cols-3 gap-8">
                <div>
                    <h3 class="text-2xl font-bold mb-4">PT Maju Bersama</h3>
                    <p class="text-gray-400 mb-4">Solusi terpercaya untuk masa depan yang lebih baik. Kami berkomitmen memberikan layanan terbaik untuk kesuksesan bisnis Anda.</p>
                </div>
                
                <div>
                    <h4 class="text-lg font-semibold mb-4">Kontak</h4>
                    <div class="space-y-2 text-gray-400">
                        <p>📍 Jl. Sudirman No. 123, Jakarta Pusat 10220</p>
                        <p>📞 (021) 1234-5678</p>
                        <p>📧 info@majubersama.co.id</p>
                    </div>
                </div>
                
                <div>
                    <h4 class="text-lg font-semibold mb-4">Jam Operasional</h4>
                    <div class="space-y-2 text-gray-400">
                        <p>Senin - Jumat: 08:00 - 17:00</p>
                        <p>Sabtu: 08:00 - 12:00</p>
                        <p>Minggu: Tutup</p>
                    </div>
                </div>
            </div>
            
            <div class="border-t border-gray-700 mt-8 pt-8 text-center">
                <p class="text-gray-500 text-sm">© 2024 PT Maju Bersama. Semua hak dilindungi.</p>
            </div>
        </div>
    </footer>

    <script>
        // Navigation Functions
        function showPage(pageId) {
            // Hide all pages
            const pages = document.querySelectorAll('.page-section');
            pages.forEach(page => page.classList.remove('active'));
            
            // Show selected page
            document.getElementById(pageId + 'Page').classList.add('active');
            
            // Update nav links
            const navLinks = document.querySelectorAll('.nav-link');
            navLinks.forEach(link => link.classList.remove('text-blue-600', 'font-bold'));
            
            // Close mobile menu
            document.getElementById('mobileMenu').classList.remove('active');
            
            // Scroll to top
            window.scrollTo(0, 0);
        }

        function toggleMobileMenu() {
            const mobileMenu = document.getElementById('mobileMenu');
            mobileMenu.classList.toggle('active');
        }

        // Welcome Message Function
        function updateWelcome() {
            const nameInput = document.getElementById('nameInput');
            const welcomeMessage = document.getElementById('welcomeMessage');
            const name = nameInput.value.trim();
            
            if (name) {
                welcomeMessage.textContent = `Hi ${name}!`;
                nameInput.value = '';
            } else {
                alert('Silakan masukkan nama Anda terlebih dahulu!');
            }
        }

        // Form Validation and Submission
        document.getElementById('contactForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Reset previous error states
            clearErrors();
            
            // Get form values
            const nama = document.getElementById('nama').value.trim();
            const email = document.getElementById('email').value.trim();
            const telepon = document.getElementById('telepon').value.trim();
            const pesan = document.getElementById('pesan').value.trim();
            
            let isValid = true;
            
            // Validate nama
            if (nama === '') {
                showError('namaError', 'Nama lengkap wajib diisi');
                isValid = false;
            } else if (nama.length < 2) {
                showError('namaError', 'Nama minimal 2 karakter');
                isValid = false;
            }
            
            // Validate email
            const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            if (email === '') {
                showError('emailError', 'Email wajib diisi');
                isValid = false;
            } else if (!emailRegex.test(email)) {
                showError('emailError', 'Format email tidak valid');
                isValid = false;
            }
            
            // Validate telepon
            const teleponRegex = /^(\+62|62|0)[0-9]{9,13}$/;
            if (telepon === '') {
                showError('teleponError', 'Nomor telepon wajib diisi');
                isValid = false;
            } else if (!teleponRegex.test(telepon)) {
                showError('teleponError', 'Format nomor telepon tidak valid (contoh: 08123456789)');
                isValid = false;
            }
            
            // Validate pesan
            if (pesan === '') {
                showError('pesanError', 'Pesan wajib diisi');
                isValid = false;
            } else if (pesan.length < 10) {
                showError('pesanError', 'Pesan minimal 10 karakter');
                isValid = false;
            }
            
            // If all validations pass
            if (isValid) {
                // Show success message
                document.getElementById('successMessage').style.display = 'block';
                
                // Display form data
                displayFormData(nama, email, telepon, pesan);
                
                // Reset form
                document.getElementById('contactForm').reset();
                
                // Scroll to success message
                document.getElementById('successMessage').scrollIntoView({ 
                    behavior: 'smooth', 
                    block: 'center' 
                });
                
                // Hide success message after 8 seconds
                setTimeout(() => {
                    document.getElementById('successMessage').style.display = 'none';
                    document.getElementById('formDataDisplay').style.display = 'none';
                }, 8000);
            }
        });

        function displayFormData(nama, email, telepon, pesan) {
            const displayDiv = document.getElementById('displayedData');
            const formDataDisplay = document.getElementById('formDataDisplay');
            
            displayDiv.innerHTML = `
                <div class="space-y-2">
                    <p><strong>Nama:</strong> ${nama}</p>
                    <p><strong>Email:</strong> ${email}</p>
                    <p><strong>Telepon:</strong> ${telepon}</p>
                    <p><strong>Pesan:</strong> ${pesan}</p>
                </div>
            `;
            
            formDataDisplay.style.display = 'block';
        }
        
        function showError(elementId, message) {
            const errorElement = document.getElementById(elementId);
            errorElement.textContent = message;
            errorElement.style.display = 'block';
            
            // Add red border to input
            const inputId = elementId.replace('Error', '');
            const inputElement = document.getElementById(inputId);
            inputElement.classList.add('border-red-500');
            inputElement.classList.remove('border-gray-300');
        }
        
        function clearErrors() {
            const errorElements = document.querySelectorAll('.error-message');
            errorElements.forEach(element => {
                element.style.display = 'none';
            });
            
            // Remove red borders
            const inputs = document.querySelectorAll('input, textarea');
            inputs.forEach(input => {
                input.classList.remove('border-red-500');
                input.classList.add('border-gray-300');
            });
        }
        
        // Real-time validation
        document.getElementById('nama').addEventListener('input', function() {
            if (this.value.trim().length >= 2) {
                document.getElementById('namaError').style.display = 'none';
                this.classList.remove('border-red-500');
                this.classList.add('border-gray-300');
            }
        });
        
        document.getElementById('email').addEventListener('input', function() {
            const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            if (emailRegex.test(this.value.trim())) {
                document.getElementById('emailError').style.display = 'none';
                this.classList.remove('border-red-500');
                this.classList.add('border-gray-300');
            }
        });
        
        document.getElementById('telepon').addEventListener('input', function() {
            const teleponRegex = /^(\+62|62|0)[0-9]{9,13}$/;
            if (teleponRegex.test(this.value.trim())) {
                document.getElementById('teleponError').style.display = 'none';
                this.classList.remove('border-red-500');
                this.classList.add('border-gray-300');
            }
        });
        
        document.getElementById('pesan').addEventListener('input', function() {
            if (this.value.trim().length >= 10) {
                document.getElementById('pesanError').style.display = 'none';
                this.classList.remove('border-red-500');
                this.classList.add('border-gray-300');
            }
        });

        // Initialize page
        document.addEventListener('DOMContentLoaded', function() {
            showPage('home');
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'98481e423609ce2e',t:'MTc1ODc3ODEwNy4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
