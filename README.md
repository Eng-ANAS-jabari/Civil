<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CIVILTCTH 2 | المؤتمر الهندسي المتكامل</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;500;700;800&display=swap" rel="stylesheet">
    <style>
        * {
            font-family: 'Tajawal', sans-serif;
            scroll-behavior: smooth;
        }
        
        :root {
            --primary: #1e3a8a;
            --secondary: #0f172a;
            --accent: #3b82f6;
        }

        body {
            background: linear-gradient(135deg, #f8fafc 0%, #f1f5f9 100%);
        }

        .glass {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(0,0,0,0.05);
        }

        .hero-gradient {
            background: linear-gradient(145deg, #0f172a 0%, #1e3a8a 60%, #2563eb 100%);
            position: relative;
            overflow: hidden;
        }

        .hero-gradient::before {
            content: '';
            position: absolute;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 50%);
            animation: rotate 20s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .card-hover {
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .card-hover:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 30px -10px rgba(0,0,0,0.15);
        }

        .upload-area {
            border: 2px dashed #cbd5e1;
            transition: all 0.3s;
            cursor: pointer;
            background: #f8fafc;
        }

        .upload-area:hover {
            border-color: var(--accent);
            background: #eff6ff;
            transform: scale(1.02);
        }

        .upload-area.dragover {
            border-color: #22c55e;
            background: #f0fdf4;
        }

        .section-padding {
            padding: 6rem 1.5rem;
        }

        .tab-active {
            border-bottom: 4px solid var(--accent);
            color: var(--primary);
            font-weight: 700;
        }

        .fade-in {
            animation: fadeInUp 0.6s ease forwards;
            opacity: 0;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .notification {
            position: fixed;
            top: 90px;
            left: 20px;
            background: #10b981;
            color: white;
            padding: 14px 28px;
            border-radius: 50px;
            box-shadow: 0 10px 25px -5px rgba(16, 185, 129, 0.4);
            z-index: 1000;
            animation: slideInLeft 0.4s ease;
            font-weight: 500;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .notification.error {
            background: #ef4444;
            box-shadow: 0 10px 25px -5px rgba(239, 68, 68, 0.4);
        }

        @keyframes slideInLeft {
            from {
                transform: translateX(-100px);
                opacity: 0;
            }
            to {
                transform: translateX(0);
                opacity: 1;
            }
        }

        .online-users {
            position: fixed;
            bottom: 20px;
            left: 20px;
            background: white;
            padding: 10px 20px;
            border-radius: 50px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            font-size: 14px;
            z-index: 100;
            border: 1px solid #e2e8f0;
            transition: all 0.3s;
        }

        .online-users:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 25px -5px rgba(0,0,0,0.2);
        }

        .typing-indicator {
            background: #e2e8f0;
            padding: 6px 16px;
            border-radius: 30px;
            font-size: 13px;
            display: inline-block;
            margin: 8px 0;
            animation: pulse 1.5s infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.7; }
        }

        .live-activity {
            transition: all 0.3s;
            border-right: 4px solid var(--accent);
        }

        .live-activity:hover {
            background: #f1f5f9;
        }

        .progress-bar {
            height: 6px;
            background: #e2e8f0;
            border-radius: 10px;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--accent), #2563eb);
            transition: width 0.5s ease;
            border-radius: 10px;
        }

        .admin-card {
            background: white;
            border-radius: 24px;
            padding: 24px;
            box-shadow: 0 10px 30px -5px rgba(0,0,0,0.1);
            border: 1px solid rgba(0,0,0,0.05);
        }

        .stat-card {
            background: linear-gradient(145deg, white, #f8fafc);
            border-radius: 20px;
            padding: 20px;
            text-align: center;
            border: 1px solid #e2e8f0;
            transition: all 0.3s;
        }

        .stat-card:hover {
            transform: translateY(-5px);
            border-color: var(--accent);
        }

        .btn-primary {
            background: linear-gradient(145deg, var(--accent), #2563eb);
            color: white;
            padding: 12px 30px;
            border-radius: 12px;
            font-weight: 600;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 20px -5px rgba(59, 130, 246, 0.5);
        }

        .btn-secondary {
            background: white;
            color: var(--primary);
            padding: 12px 30px;
            border-radius: 12px;
            font-weight: 600;
            transition: all 0.3s;
            border: 2px solid #e2e8f0;
            cursor: pointer;
        }

        .btn-secondary:hover {
            border-color: var(--accent);
            background: #f8fafc;
        }

        input, select, textarea {
            transition: all 0.3s;
            border: 2px solid #e2e8f0;
        }

        input:focus, select:focus, textarea:focus {
            border-color: var(--accent);
            box-shadow: 0 0 0 4px rgba(59, 130, 246, 0.1);
            outline: none;
        }

        .gallery-item {
            position: relative;
            overflow: hidden;
            border-radius: 16px;
            cursor: pointer;
        }

        .gallery-item img {
            transition: all 0.5s;
        }

        .gallery-item:hover img {
            transform: scale(1.1);
        }

        .gallery-item .overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(to top, rgba(0,0,0,0.8), transparent);
            color: white;
            padding: 20px;
            transform: translateY(100%);
            transition: all 0.3s;
        }

        .gallery-item:hover .overlay {
            transform: translateY(0);
        }

        @media (max-width: 768px) {
            .section-padding {
                padding: 4rem 1rem;
            }
            
            .notification {
                top: 70px;
                left: 10px;
                right: 10px;
                border-radius: 12px;
            }
        }
    </style>
</head>
<body class="antialiased">

    <!-- إشعارات -->
    <div id="notification" class="notification hidden">
        <i class="fas fa-check-circle text-xl"></i>
        <span id="notificationMessage"></span>
    </div>

    <!-- مؤشر المستخدمين المتصلين -->
    <div id="onlineUsers" class="online-users hidden">
        <i class="fas fa-users text-blue-600 ml-2"></i>
        <span id="onlineCount">0</span> مستخدم متصل
    </div>

    <!-- شريط التنقل -->
    <nav class="fixed w-full z-50 glass shadow-sm py-3">
        <div class="container mx-auto px-4 md:px-6">
            <div class="flex justify-between items-center">
                <div class="flex items-center gap-3">
                    <div class="w-10 h-10 bg-gradient-to-br from-blue-600 to-blue-800 rounded-xl flex items-center justify-center shadow-lg">
                        <i class="fas fa-microchip text-white text-xl"></i>
                    </div>
                    <span class="text-xl md:text-2xl font-extrabold text-slate-800">CIVILTCTH <span class="text-blue-600">2</span></span>
                </div>
                
                <!-- القائمة للشاشات الكبيرة -->
                <div class="hidden lg:flex items-center gap-8">
                    <a href="#agenda" class="text-slate-600 hover:text-blue-600 transition font-medium">الأجندة</a>
                    <a href="#register" class="text-slate-600 hover:text-blue-600 transition font-medium">التسجيل</a>
                    <a href="#gallery" class="text-slate-600 hover:text-blue-600 transition font-medium">المعرض</a>
                    <a href="#live" class="text-slate-600 hover:text-blue-600 transition font-medium">المباشر</a>
                    <a href="#admin" class="bg-red-50 text-red-600 px-5 py-2 rounded-xl font-bold hover:bg-red-100 transition border border-red-200">
                        <i class="fas fa-crown ml-2"></i>لوحة التحكم
                    </a>
                </div>

                <!-- زر القائمة للجوال -->
                <button class="lg:hidden text-2xl text-slate-700" onclick="toggleMobileMenu()">
                    <i class="fas fa-bars"></i>
                </button>
            </div>

            <!-- القائمة المنسدلة للجوال -->
            <div id="mobileMenu" class="hidden lg:hidden mt-4 pb-4 space-y-3">
                <a href="#agenda" class="block py-2 text-slate-600 hover:text-blue-600 transition font-medium" onclick="toggleMobileMenu()">الأجندة</a>
                <a href="#register" class="block py-2 text-slate-600 hover:text-blue-600 transition font-medium" onclick="toggleMobileMenu()">التسجيل</a>
                <a href="#gallery" class="block py-2 text-slate-600 hover:text-blue-600 transition font-medium" onclick="toggleMobileMenu()">المعرض</a>
                <a href="#live" class="block py-2 text-slate-600 hover:text-blue-600 transition font-medium" onclick="toggleMobileMenu()">المباشر</a>
                <a href="#admin" class="block py-2 text-red-600 font-bold hover:bg-red-50 px-3 rounded-lg" onclick="toggleMobileMenu()">لوحة التحكم</a>
            </div>
        </div>
    </nav>

    <!-- القسم الرئيسي -->
    <section class="hero-gradient min-h-screen flex items-center pt-20 text-white relative overflow-hidden">
        <div class="container mx-auto px-4 md:px-6 relative z-10">
            <div class="max-w-4xl mx-auto text-center">
                <div class="inline-block bg-white/10 backdrop-blur-lg px-6 py-2 rounded-full mb-8 border border-white/20">
                    <span class="text-sm font-medium">المؤتمر الهندسي الثاني</span>
                </div>
                <h1 class="text-5xl md:text-7xl lg:text-8xl font-extrabold mb-6 leading-tight">
                    CIVIL<span class="text-blue-300">TCTH</span> 2
                </h1>
                <p class="text-xl md:text-2xl text-blue-200 mb-12 max-w-2xl mx-auto">
                    حيث تلتقي الهندسة بالتكنولوجيا في مدينة الخليل
                </p>
                <div class="flex flex-col sm:flex-row justify-center gap-4">
                    <a href="#register" class="btn-primary text-lg">
                        <i class="fas fa-user-plus ml-2"></i>سجل الآن
                    </a>
                    <a href="#gallery" class="btn-secondary text-lg bg-white/10 text-white border-white/20 hover:bg-white/20">
                        <i class="fas fa-images ml-2"></i>استعرض المعرض
                    </a>
                </div>
                
                <!-- إحصائيات سريعة -->
                <div class="grid grid-cols-3 gap-4 max-w-2xl mx-auto mt-16">
                    <div class="text-center">
                        <div class="text-3xl font-bold text-blue-300" id="heroRegistrants">0</div>
                        <div class="text-sm text-blue-200">مسجل</div>
                    </div>
                    <div class="text-center">
                        <div class="text-3xl font-bold text-blue-300" id="heroSessions">0</div>
                        <div class="text-sm text-blue-200">جلسة</div>
                    </div>
                    <div class="text-center">
                        <div class="text-3xl font-bold text-blue-300" id="heroImages">0</div>
                        <div class="text-sm text-blue-200">صورة</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- التغذية المباشرة -->
    <section id="live" class="section-padding bg-gradient-to-b from-blue-50 to-white">
        <div class="container mx-auto px-4 md:px-6">
            <div class="text-center mb-12">
                <h2 class="text-4xl font-bold mb-4">التغذية المباشرة</h2>
                <p class="text-slate-600 text-lg">آخر التحديثات والتفاعلات من الحضور</p>
            </div>
            
            <div class="max-w-3xl mx-auto">
                <div class="bg-white rounded-3xl shadow-2xl overflow-hidden border border-slate-100">
                    <div class="bg-gradient-to-l from-blue-600 to-blue-800 text-white p-5">
                        <div class="flex justify-between items-center">
                            <div class="flex items-center gap-3">
                                <i class="fas fa-rss text-xl"></i>
                                <span class="font-bold">التحديثات المباشرة</span>
                            </div>
                            <div class="flex items-center gap-3">
                                <span class="text-sm bg-white/20 px-3 py-1 rounded-full" id="lastUpdate">
                                    <i class="fas fa-sync-alt fa-spin ml-1"></i>تحديث
                                </span>
                                <span class="w-2 h-2 bg-green-400 rounded-full animate-pulse"></span>
                            </div>
                        </div>
                    </div>
                    
                    <div id="liveActivities" class="h-96 overflow-y-auto p-5 space-y-3 bg-slate-50">
                        <div class="text-center text-slate-400 py-12">
                            <i class="fas fa-comments text-5xl mb-3 opacity-30"></i>
                            <p>جاري تحميل النشاطات...</p>
                        </div>
                    </div>
                    
                    <div class="border-t p-5 bg-white">
                        <form id="liveForm" class="flex gap-3">
                            <input type="text" id="liveMessage" 
                                   placeholder="شارك بتعليق أو سؤال..." 
                                   class="flex-1 px-5 py-3 rounded-xl border-2 border-slate-200 focus:border-blue-500 transition"
                                   maxlength="200">
                            <button type="submit" 
                                    class="bg-blue-600 text-white px-6 py-3 rounded-xl hover:bg-blue-700 transition shadow-lg hover:shadow-xl">
                                <i class="fas fa-paper-plane"></i>
                            </button>
                        </form>
                        <div id="typingIndicator" class="typing-indicator hidden mt-3">
                            <i class="fas fa-pencil-alt ml-2 text-slate-500"></i>
                            <span class="text-slate-600">شخص يكتب...</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- الأجندة -->
    <section id="agenda" class="section-padding bg-white">
        <div class="container mx-auto px-4 md:px-6">
            <div class="text-center mb-12">
                <h2 class="text-4xl font-bold mb-4">أجندة المؤتمر</h2>
                <p class="text-slate-600 text-lg">جدول الجلسات والفعاليات</p>
            </div>
            
            <!-- شريط التقدم -->
            <div class="max-w-4xl mx-auto mb-10">
                <div class="flex justify-between text-sm text-slate-500 mb-2">
                    <span>بداية المؤتمر</span>
                    <span>التقدم: <span id="progressPercent">0</span>%</span>
                    <span>نهاية المؤتمر</span>
                </div>
                <div class="progress-bar">
                    <div id="agendaProgress" class="progress-fill" style="width: 0%"></div>
                </div>
            </div>
            
            <div class="grid md:grid-cols-2 gap-8 max-w-6xl mx-auto">
                <!-- اليوم الأول -->
                <div class="bg-slate-50 rounded-3xl p-6 card-hover">
                    <div class="flex items-center justify-between mb-6">
                        <h3 class="text-2xl font-bold text-blue-800">
                            <i class="fas fa-sun ml-2"></i> اليوم الأول
                        </h3>
                        <span class="bg-blue-100 text-blue-800 px-4 py-1 rounded-full text-sm font-bold" id="day1Count">0</span>
                    </div>
                    <div id="agenda-day1" class="space-y-4">
                        <div class="text-center text-slate-400 py-8">
                            <i class="fas fa-calendar-alt text-3xl mb-2 opacity-30"></i>
                            <p>لا توجد فقرات بعد</p>
                        </div>
                    </div>
                </div>
                
                <!-- اليوم الثاني -->
                <div class="bg-slate-50 rounded-3xl p-6 card-hover">
                    <div class="flex items-center justify-between mb-6">
                        <h3 class="text-2xl font-bold text-indigo-800">
                            <i class="fas fa-moon ml-2"></i> اليوم الثاني
                        </h3>
                        <span class="bg-indigo-100 text-indigo-800 px-4 py-1 rounded-full text-sm font-bold" id="day2Count">0</span>
                    </div>
                    <div id="agenda-day2" class="space-y-4">
                        <div class="text-center text-slate-400 py-8">
                            <i class="fas fa-calendar-alt text-3xl mb-2 opacity-30"></i>
                            <p>لا توجد فقرات بعد</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- نموذج التسجيل -->
    <section id="register" class="section-padding bg-gradient-to-b from-blue-50 to-white">
        <div class="container mx-auto px-4 md:px-6 max-w-4xl">
            <div class="bg-white rounded-[3rem] shadow-2xl overflow-hidden border border-blue-100">
                <!-- رأس النموذج -->
                <div class="bg-gradient-to-l from-blue-600 to-blue-800 text-white p-8 text-center">
                    <i class="fas fa-user-plus text-5xl mb-4"></i>
                    <h2 class="text-3xl font-bold mb-2">نموذج التسجيل</h2>
                    <p class="text-blue-200">سجل الآن لحجز مقعدك في المؤتمر</p>
                </div>
                
                <!-- العداد المباشر -->
                <div class="bg-blue-50 p-4 flex justify-center border-b">
                    <div class="bg-white px-6 py-2 rounded-full shadow-sm">
                        <i class="fas fa-users text-blue-600 ml-2"></i>
                        <span class="font-bold">عدد المسجلين:</span>
                        <span id="liveRegistrantCount" class="text-blue-600 font-bold mr-1">0</span>
                    </div>
                </div>
                
                <!-- النموذج -->
                <form id="regForm" class="p-8 md:p-10 grid md:grid-cols-2 gap-6">
                    <div class="space-y-2">
                        <label class="text-sm font-bold text-slate-700 block">الاسم الكامل</label>
                        <input type="text" id="fullName" required 
                               class="w-full px-5 py-3 rounded-xl border-2 border-slate-200 focus:border-blue-500 transition"
                               placeholder="أدخل اسمك الثلاثي">
                    </div>
                    
                    <div class="space-y-2">
                        <label class="text-sm font-bold text-slate-700 block">البريد الإلكتروني</label>
                        <input type="email" id="email" required 
                               class="w-full px-5 py-3 rounded-xl border-2 border-slate-200 focus:border-blue-500 transition"
                               placeholder="example@domain.com">
                    </div>
                    
                    <div class="space-y-2">
                        <label class="text-sm font-bold text-slate-700 block">رقم الهاتف</label>
                        <input type="tel" id="phone" required 
                               class="w-full px-5 py-3 rounded-xl border-2 border-slate-200 focus:border-blue-500 transition"
                               placeholder="059xxxxxxxx">
                    </div>
                    
                    <div class="space-y-2">
                        <label class="text-sm font-bold text-slate-700 block">مسار المشاركة</label>
                        <select id="track" class="w-full px-5 py-3 rounded-xl border-2 border-slate-200 focus:border-blue-500 transition">
                            <option value="attendee">حضور فقط</option>
                            <option value="bridge">مسابقة الجسور</option>
                            <option value="hackathon">هكاثون عين سارة</option>
                        </select>
                    </div>
                    
                    <button type="submit" id="regBtn" 
                            class="md:col-span-2 btn-primary text-lg py-4">
                        <i class="fas fa-check-circle ml-2"></i>
                        تأكيد التسجيل
                    </button>
                </form>
            </div>
        </div>
    </section>

    <!-- معرض الصور -->
    <section id="gallery" class="section-padding bg-white">
        <div class="container mx-auto px-4 md:px-6">
            <div class="text-center mb-12">
                <h2 class="text-4xl font-bold mb-4">معرض الصور</h2>
                <p class="text-slate-600 text-lg">لقطات من المؤتمر السابق والحالي</p>
            </div>
            
            <!-- أزرار التبديل -->
            <div class="flex justify-center gap-4 mb-10">
                <button onclick="switchGallery('tech1')" 
                        id="tab-tech1" 
                        class="px-6 py-3 rounded-xl font-bold transition tab-active">
                    <i class="fas fa-images ml-2"></i>
                    المؤتمر الأول
                </button>
                <button onclick="switchGallery('tech2')" 
                        id="tab-tech2" 
                        class="px-6 py-3 rounded-xl font-bold transition bg-slate-100 text-slate-600 hover:bg-slate-200">
                    <i class="fas fa-camera ml-2"></i>
                    المؤتمر الثاني (الحالي)
                </button>
            </div>
            
            <!-- صور المؤتمر الأول -->
            <div id="gallery-tech1" class="grid grid-cols-2 md:grid-cols-4 gap-4">
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1581094794329-c8112a89af12?w=400" class="w-full h-48 object-cover">
                </div>
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1503387762-592dea58ef21?w=400" class="w-full h-48 object-cover">
                </div>
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1581094794329-c8112a89af12?w=400" class="w-full h-48 object-cover">
                </div>
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1503387762-592dea58ef21?w=400" class="w-full h-48 object-cover">
                </div>
            </div>
            
            <!-- صور المؤتمر الثاني -->
            <div id="gallery-tech2" class="hidden grid grid-cols-2 md:grid-cols-4 gap-4">
                <p id="empty-msg" class="col-span-full text-center text-slate-400 py-16">
                    <i class="fas fa-cloud-upload-alt text-5xl mb-3 opacity-30"></i>
                    <br>لم يتم رفع صور بعد...
                </p>
            </div>
        </div>
    </section>

    <!-- لوحة تحكم المسؤول -->
    <section id="admin" class="section-padding bg-slate-100">
        <div class="container mx-auto px-4 md:px-6">
            <!-- شاشة تسجيل الدخول -->
            <div id="admin-login" class="max-w-md mx-auto text-center">
                <div class="bg-white rounded-3xl p-8 shadow-xl border border-red-100">
                    <div class="w-20 h-20 bg-red-100 rounded-2xl mx-auto mb-4 flex items-center justify-center">
                        <i class="fas fa-crown text-red-600 text-3xl"></i>
                    </div>
                    <h2 class="text-2xl font-bold mb-6 text-red-800">لوحة تحكم المسؤول</h2>
                    <input type="password" id="adminPass" placeholder="كلمة المرور" 
                           class="w-full px-5 py-3 rounded-xl border-2 border-slate-200 mb-4 text-center">
                    <button onclick="checkAdmin()" 
                            class="w-full bg-red-600 text-white py-3 rounded-xl font-bold hover:bg-red-700 transition shadow-lg">
                        <i class="fas fa-lock-open ml-2"></i>
                        دخول
                    </button>
                </div>
            </div>

            <!-- محتوى لوحة التحكم -->
            <div id="admin-content" class="hidden space-y-8">
                <!-- الإحصائيات -->
                <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
                    <div class="stat-card">
                        <i class="fas fa-users text-3xl text-blue-600 mb-2"></i>
                        <div class="text-3xl font-bold text-blue-600" id="adminLiveCount">0</div>
                        <div class="text-sm text-slate-500">متصلاً الآن</div>
                    </div>
                    <div class="stat-card">
                        <i class="fas fa-user-check text-3xl text-green-600 mb-2"></i>
                        <div class="text-3xl font-bold text-green-600" id="adminRegCount">0</div>
                        <div class="text-sm text-slate-500">مسجل</div>
                    </div>
                    <div class="stat-card">
                        <i class="fas fa-image text-3xl text-purple-600 mb-2"></i>
                        <div class="text-3xl font-bold text-purple-600" id="adminPhotoCount">0</div>
                        <div class="text-sm text-slate-500">صورة</div>
                    </div>
                    <div class="stat-card">
                        <i class="fas fa-clock text-3xl text-orange-600 mb-2"></i>
                        <div class="text-3xl font-bold text-orange-600" id="adminSessionCount">0</div>
                        <div class="text-sm text-slate-500">جلسة</div>
                    </div>
                </div>

                <!-- إدارة الأجندة -->
                <div class="admin-card">
                    <h3 class="text-2xl font-bold mb-6 text-green-800">
                        <i class="fas fa-calendar-plus ml-2"></i>
                        إدارة الأجندة
                    </h3>
                    <form id="agendaForm" class="grid md:grid-cols-4 gap-4 mb-8">
                        <input type="text" id="agendaTitle" placeholder="عنوان الفقرة" required 
                               class="px-4 py-3 rounded-xl border-2 border-slate-200">
                        <input type="time" id="agendaTime" required 
                               class="px-4 py-3 rounded-xl border-2 border-slate-200">
                        <select id="agendaDay" class="px-4 py-3 rounded-xl border-2 border-slate-200">
                            <option value="1">اليوم الأول</option>
                            <option value="2">اليوم الثاني</option>
                        </select>
                        <button type="submit" id="agendaBtn" 
                                class="bg-green-600 text-white py-3 rounded-xl font-bold hover:bg-green-700 transition">
                            <i class="fas fa-plus ml-2"></i>
                            إضافة
                        </button>
                    </form>
                    
                    <div id="agendaList" class="space-y-2 max-h-80 overflow-y-auto p-2 bg-slate-50 rounded-xl">
                        <p class="text-center text-slate-400 py-4">لا توجد فقرات مضافة</p>
                    </div>
                </div>

                <!-- رفع الصور -->
                <div class="admin-card">
                    <h3 class="text-2xl font-bold mb-6 text-blue-800">
                        <i class="fas fa-cloud-upload-alt ml-2"></i>
                        رفع صور المؤتمر الثاني
                    </h3>
                    <form id="uploadForm" class="space-y-4">
                        <div id="dropZone" class="upload-area p-8 text-center rounded-2xl">
                            <input type="file" id="fileInput" accept="image/*" class="hidden" multiple>
                            <div id="uploadPrompt">
                                <i class="fas fa-cloud-upload-alt text-4xl text-blue-500 mb-3"></i>
                                <br>
                                <span class="font-medium">إضغط أو أسحب الصورة هنا</span>
                                <p class="text-sm text-slate-500 mt-2">JPG, PNG, GIF حتى 5MB</p>
                            </div>
                            <img id="imgPreview" class="hidden max-h-48 mx-auto mt-4 rounded-xl shadow-lg">
                        </div>
                        <input type="text" id="upCaption" placeholder="وصف الصورة (اختياري)" 
                               class="w-full px-4 py-3 rounded-xl border-2 border-slate-200">
                        <button type="submit" id="upBtn" 
                                class="w-full bg-blue-700 text-white py-4 rounded-xl font-bold text-lg hover:bg-blue-800 transition">
                            <i class="fas fa-upload ml-2"></i>
                            نشر الصورة
                        </button>
                    </form>
                </div>

                <!-- قائمة المسجلين -->
                <div class="admin-card">
                    <h3 class="text-2xl font-bold mb-6">
                        <i class="fas fa-list ml-2"></i>
                        قائمة المسجلين (<span id="totalCount">0</span>)
                    </h3>
                    <div class="overflow-x-auto">
                        <table class="w-full text-right">
                            <thead class="bg-slate-50 border-b">
                                <tr>
                                    <th class="p-3">الاسم</th>
                                    <th class="p-3">البريد</th>
                                    <th class="p-3">الهاتف</th>
                                    <th class="p-3">المسار</th>
                                    <th class="p-3"></th>
                                </tr>
                            </thead>
                            <tbody id="registrantsTable" class="divide-y"></tbody>
                        </table>
                    </div>
                </div>
                
                <div class="text-center">
                    <button onclick="logoutAdmin()" 
                            class="text-red-600 font-bold underline hover:text-red-800 transition">
                        <i class="fas fa-sign-out-alt ml-2"></i>
                        تسجيل الخروج
                    </button>
                </div>
            </div>
        </div>
    </section>

    <footer class="bg-slate-900 text-white py-12 text-center">
        <div class="container mx-auto px-4">
            <div class="w-16 h-16 bg-blue-600/20 rounded-2xl mx-auto mb-4 flex items-center justify-center">
                <i class="fas fa-microchip text-blue-400 text-3xl"></i>
            </div>
            <p class="text-lg font-bold mb-2">CIVILTCTH 2</p>
            <p class="text-slate-400 text-sm">© 2025 كلية الهندسة والتكنولوجيا - جامعة الخليل</p>
        </div>
    </footer>

    <!-- Firebase Config -->
    <script>
        window.__firebase_config = {
            apiKey: "YOUR_API_KEY",
            authDomain: "YOUR_AUTH_DOMAIN",
            projectId: "YOUR_PROJECT_ID",
            storageBucket: "YOUR_STORAGE_BUCKET",
            messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
            appId: "YOUR_APP_ID"
        };
        window.__app_id = 'civiltcth2-main-v1';
    </script>

    <!-- Main Script -->
    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
        import { getFirestore, collection, addDoc, onSnapshot, query, orderBy, deleteDoc, doc, serverTimestamp, limit, where, Timestamp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";
        import { getAuth, signInAnonymously, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";
        import { getDatabase, ref, onValue, set, push, onDisconnect } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-database.js";

        // تهيئة Firebase
        const app = initializeApp(window.__firebase_config);
        const db = getFirestore(app);
        const rtdb = getDatabase(app);
        const auth = getAuth(app);
        const appId = window.__app_id;

        // متغيرات عامة
        let currentUser = null;
        let userId = null;
        let typingTimeout = null;

        // دوال مساعدة
        function showNotification(message, isSuccess = true) {
            const notification = document.getElementById('notification');
            const messageEl = document.getElementById('notificationMessage');
            
            if(notification && messageEl) {
                messageEl.innerText = message;
                notification.classList.remove('hidden', 'error');
                if(!isSuccess) notification.classList.add('error');
                
                setTimeout(() => {
                    notification.classList.add('hidden');
                }, 3000);
            }
        }

        function showSuccess(message) {
            showNotification(message, true);
        }

        function showError(message) {
            showNotification(message, false);
        }

        // قائمة الجوال
        window.toggleMobileMenu = () => {
            const menu = document.getElementById('mobileMenu');
            menu.classList.toggle('hidden');
        };

        // المصادقة
        signInAnonymously(auth).catch(error => {
            console.error("Auth error:", error);
            showError("خطأ في الاتصال");
        });
        
        onAuthStateChanged(auth, (user) => {
            if(user) {
                currentUser = user;
                userId = user.uid;
                
                // تسجيل التواجد
                const statusRef = ref(rtdb, 'status/' + userId);
                const connectedRef = ref(rtdb, '.info/connected');
                
                onValue(connectedRef, (snap) => {
                    if(snap.val() === true) {
                        set(statusRef, {
                            online: true,
                            lastSeen: Date.now(),
                            lastActive: Date.now()
                        });
                        
                        onDisconnect(statusRef).set({
                            online: false,
                            lastSeen: Date.now()
                        });
                    }
                });
                
                // مراقبة عدد المتصلين
                const onlineRef = ref(rtdb, 'status');
                onValue(onlineRef, (snap) => {
                    let count = 0;
                    snap.forEach(child => {
                        if(child.val().online) count++;
                    });
                    
                    document.getElementById('onlineCount').innerText = count;
                    document.getElementById('adminLiveCount').innerText = count;
                    document.getElementById('onlineUsers').classList.remove('hidden');
                });
                
                // بدء المزامنة
                syncLiveFeed();
                syncAgenda();
                syncGallery();
                syncRegistrants();
                syncStats();
                initTyping();
            }
        });

        // التغذية المباشرة
        function syncLiveFeed() {
            const q = query(
                collection(db, 'artifacts', appId, 'public', 'data', 'activities'),
                orderBy('createdAt', 'desc'),
                limit(50)
            );
            
            onSnapshot(q, (snap) => {
                const container = document.getElementById('liveActivities');
                const lastUpdate = document.getElementById('lastUpdate');
                
                if(!container) return;
                
                lastUpdate.innerHTML = '<i class="fas fa-check ml-1"></i>' + 
                    new Date().toLocaleTimeString('ar-EG', {hour: '2-digit', minute:'2-digit'});
                
                if(snap.empty) {
                    container.innerHTML = '<div class="text-center text-slate-400 py-12"><i class="fas fa-comments text-5xl mb-3 opacity-30"></i><p>لا توجد تحديثات بعد</p></div>';
                    return;
                }
                
                container.innerHTML = '';
                snap.forEach(doc => {
                    const activity = doc.data();
                    const time = activity.createdAt?.toDate ? 
                        activity.createdAt.toDate().toLocaleTimeString('ar-EG', {hour: '2-digit', minute:'2-digit'}) : 
                        'الآن';
                    
                    const div = document.createElement('div');
                    div.className = "bg-white p-4 rounded-xl shadow-sm border-r-4 border-blue-500 fade-in live-activity";
                    div.innerHTML = `
                        <div class="flex justify-between items-start">
                            <div>
                                <span class="font-bold text-blue-800">${activity.user || 'مشارك'}</span>
                                <p class="text-slate-700 mt-1">${activity.message}</p>
                            </div>
                            <span class="text-xs text-slate-400 bg-slate-100 px-2 py-1 rounded">${time}</span>
                        </div>
                    `;
                    container.appendChild(div);
                });
                
                container.scrollTop = 0;
            });
        }

        // مراقبة الكتابة
        function initTyping() {
            const input = document.getElementById('liveMessage');
            if(!input) return;
            
            input.addEventListener('input', () => {
                if(!userId) return;
                
                const typingRef = ref(rtdb, 'typing/' + userId);
                set(typingRef, { isTyping: true, timestamp: Date.now() });
                
                clearTimeout(typingTimeout);
                typingTimeout = setTimeout(() => {
                    set(typingRef, { isTyping: false });
                }, 2000);
            });
            
            // مراقبة الآخرين
            const typingRef = ref(rtdb, 'typing');
            onValue(typingRef, (snap) => {
                let count = 0;
                snap.forEach(child => {
                    if(child.val().isTyping && child.key !== userId) count++;
                });
                
                const indicator = document.getElementById('typingIndicator');
                if(indicator) {
                    if(count > 0) {
                        indicator.classList.remove('hidden');
                        indicator.innerHTML = count === 1 ? 
                            '<i class="fas fa-pencil-alt ml-2 text-slate-500"></i><span class="text-slate-600">شخص يكتب...</span>' : 
                            `<i class="fas fa-pencil-alt ml-2 text-slate-500"></i><span class="text-slate-600">${count} أشخاص يكتبون...</span>`;
                    } else {
                        indicator.classList.add('hidden');
                    }
                }
            });
        }

        // إرسال رسالة حية
        document.getElementById('liveForm')?.addEventListener('submit', async (e) => {
            e.preventDefault();
            const message = document.getElementById('liveMessage').value.trim();
            if(!message) return;
            
            try {
                await addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'activities'), {
                    message: message,
                    user: 'مشارك',
                    userId: userId,
                    createdAt: serverTimestamp()
                });
                
                e.target.reset();
                showSuccess('تم نشر تعليقك');
                
                if(userId) {
                    set(ref(rtdb, 'typing/' + userId), { isTyping: false });
                }
                
            } catch(error) {
                console.error(error);
                showError('فشل في النشر');
            }
        });

        // الأجندة
        document.getElementById('agendaForm')?.addEventListener('submit', async (e) => {
            e.preventDefault();
            
            const title = document.getElementById('agendaTitle').value;
            const time = document.getElementById('agendaTime').value;
            const day = document.getElementById('agendaDay').value;
            
            if(!title || !time) return;
            
            try {
                await addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'agenda'), {
                    title: title,
                    time: time,
                    day: day,
                    createdAt: serverTimestamp()
                });
                
                // إضافة نشاط
                await addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'activities'), {
                    message: `تم إضافة فقرة جديدة: ${title}`,
                    user: 'المسؤول',
                    userId: 'admin',
                    createdAt: serverTimestamp()
                });
                
                e.target.reset();
                showSuccess('تم إضافة الفقرة');
                
            } catch(error) {
                console.error(error);
                showError('فشلت الإضافة');
            }
        });

        function syncAgenda() {
            const q = query(collection(db, 'artifacts', appId, 'public', 'data', 'agenda'), orderBy('time'));
            
            onSnapshot(q, (snap) => {
                const day1 = document.getElementById('agenda-day1');
                const day2 = document.getElementById('agenda-day2');
                const agendaList = document.getElementById('agendaList');
                const day1Count = document.getElementById('day1Count');
                const day2Count = document.getElementById('day2Count');
                const heroSessions = document.getElementById('heroSessions');
                
                let count1 = 0, count2 = 0;
                
                if(day1) day1.innerHTML = '';
                if(day2) day2.innerHTML = '';
                if(agendaList) agendaList.innerHTML = '';

                snap.forEach(doc => {
                    const item = {id: doc.id, ...doc.data()};
                    
                    if(item.day == "1") count1++;
                    else count2++;
                    
                    // عرض في الصفحة الرئيسية
                    if(day1 && day2) {
                        const div = document.createElement('div');
                        div.className = "bg-white p-4 rounded-xl shadow-sm border-r-4 fade-in " + 
                            (item.day == "1" ? "border-blue-500" : "border-indigo-500");
                        div.innerHTML = `
                            <div class="flex items-center gap-3">
                                <span class="text-sm font-bold text-slate-500 bg-slate-100 px-2 py-1 rounded">${item.time}</span>
                                <p class="font-bold text-slate-800">${item.title}</p>
                            </div>
                        `;
                        
                        if(item.day == "1") day1.appendChild(div);
                        else day2.appendChild(div);
                    }
                    
                    // عرض في لوحة التحكم
                    if(agendaList) {
                        const div = document.createElement('div');
                        div.className = "flex justify-between items-center p-3 bg-white rounded-lg hover:bg-slate-50 transition border";
                        div.innerHTML = `
                            <div>
                                <span class="text-sm font-bold text-blue-600 bg-blue-50 px-2 py-1 rounded ml-2">${item.time}</span>
                                <span class="font-medium">${item.title}</span>
                                <span class="text-xs text-slate-500 mr-2">(اليوم ${item.day == "1" ? 'الأول' : 'الثاني'})</span>
                            </div>
                            <button onclick="deleteAgendaItem('${item.id}')" class="text-red-500 hover:text-red-700 p-2">
                                <i class="fas fa-trash"></i>
                            </button>
                        `;
                        agendaList.appendChild(div);
                    }
                });
                
                if(day1Count) day1Count.innerText = count1;
                if(day2Count) day2Count.innerText = count2;
                if(heroSessions) heroSessions.innerText = count1 + count2;
                if(document.getElementById('adminSessionCount')) 
                    document.getElementById('adminSessionCount').innerText = count1 + count2;
                
                updateProgress(count1 + count2);
            });
        }

        function updateProgress(total) {
            const now = new Date();
            const currentTime = `${now.getHours().toString().padStart(2,'0')}:${now.getMinutes().toString().padStart(2,'0')}`;
            
            let passed = 0;
            document.querySelectorAll('#agenda-day1 .border-r-4, #agenda-day2 .border-r-4').forEach(item => {
                const timeSpan = item.querySelector('span');
                if(timeSpan && timeSpan.innerText < currentTime) passed++;
            });
            
            const percent = total > 0 ? Math.round((passed / total) * 100) : 0;
            const progressBar = document.getElementById('agendaProgress');
            const percentSpan = document.getElementById('progressPercent');
            
            if(progressBar) progressBar.style.width = `${percent}%`;
            if(percentSpan) percentSpan.innerText = percent;
        }

        // حذف من الأجندة
        window.deleteAgendaItem = async (id) => {
            if(!confirm('تأكيد حذف الفقرة؟')) return;
            
            try {
                await deleteDoc(doc(db, 'artifacts', appId, 'public', 'data', 'agenda', id));
                showSuccess('تم الحذف');
            } catch(error) {
                console.error(error);
                showError('فشل الحذف');
            }
        };

        // معرض الصور
        window.switchGallery = (type) => {
            const tech1 = document.getElementById('gallery-tech1');
            const tech2 = document.getElementById('gallery-tech2');
            const tab1 = document.getElementById('tab-tech1');
            const tab2 = document.getElementById('tab-tech2');
            
            if(tech1 && tech2) {
                tech1.classList.toggle('hidden', type !== 'tech1');
                tech2.classList.toggle('hidden', type !== 'tech2');
            }
            
            if(tab1 && tab2) {
                if(type === 'tech1') {
                    tab1.classList.add('tab-active');
                    tab2.classList.remove('tab-active');
                    tab2.classList.add('bg-slate-100', 'text-slate-600');
                } else {
                    tab2.classList.add('tab-active');
                    tab1.classList.remove('tab-active');
                    tab1.classList.add('bg-slate-100', 'text-slate-600');
                }
            }
        };

        // رفع الصور
        const dropZone = document.getElementById('dropZone');
        const fileInput = document.getElementById('fileInput');
        
        if(dropZone) {
            dropZone.addEventListener('click', () => fileInput.click());
            
            dropZone.addEventListener('dragover', (e) => {
                e.preventDefault();
                dropZone.classList.add('dragover');
            });
            
            dropZone.addEventListener('dragleave', () => {
                dropZone.classList.remove('dragover');
            });
            
            dropZone.addEventListener('drop', (e) => {
                e.preventDefault();
                dropZone.classList.remove('dragover');
                
                const files = e.dataTransfer.files;
                if(files.length > 0) handleImageSelect(files[0]);
            });
        }

        fileInput?.addEventListener('change', (e) => {
            if(e.target.files.length > 0) handleImageSelect(e.target.files[0]);
        });

        function handleImageSelect(file) {
            if(!file.type.startsWith('image/')) {
                showError('الملف يجب أن يكون صورة');
                return;
            }
            
            if(file.size > 5 * 1024 * 1024) {
                showError('حجم الصورة يجب أن أقل من 5MB');
                return;
            }
            
            const reader = new FileReader();
            reader.onload = (e) => {
                const preview = document.getElementById('imgPreview');
                const prompt = document.getElementById('uploadPrompt');
                
                if(preview && prompt) {
                    preview.src = e.target.result;
                    preview.classList.remove('hidden');
                    prompt.innerHTML = '<i class="fas fa-check-circle text-green-500 text-3xl"></i><br><span class="font-medium">تم اختيار الصورة</span>';
                }
            };
            reader.readAsDataURL(file);
        }

        document.getElementById('uploadForm')?.addEventListener('submit', async (e) => {
            e.preventDefault();
            
            const preview = document.getElementById('imgPreview');
            const caption = document.getElementById('upCaption').value;
            
            if(!preview || !preview.src || preview.src === '') {
                showError('اختر صورة أولاً');
                return;
            }
            
            try {
                await addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'gallery_v2'), {
                    image: preview.src,
                    caption: caption || 'صورة من المؤتمر',
                    createdAt: serverTimestamp()
                });
                
                await addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'activities'), {
                    message: `تم إضافة صورة جديدة: ${caption || 'من المؤتمر'}`,
                    user: 'المسؤول',
                    userId: 'admin',
                    createdAt: serverTimestamp()
                });
                
                // إعادة تعيين النموذج
                e.target.reset();
                preview.classList.add('hidden');
                document.getElementById('uploadPrompt').innerHTML = '<i class="fas fa-cloud-upload-alt text-4xl text-blue-500 mb-3"></i><br><span class="font-medium">إضغط أو أسحب الصورة هنا</span><p class="text-sm text-slate-500 mt-2">JPG, PNG, GIF حتى 5MB</p>';
                
                showSuccess('تم رفع الصورة');
                
            } catch(error) {
                console.error(error);
                showError('فشل الرفع');
            }
        });

        function syncGallery() {
            const q = query(collection(db, 'artifacts', appId, 'public', 'data', 'gallery_v2'), orderBy('createdAt', 'desc'));
            
            onSnapshot(q, (snap) => {
                const grid = document.getElementById('gallery-tech2');
                const empty = document.getElementById('empty-msg');
                const heroImages = document.getElementById('heroImages');
                
                if(!grid) return;
                
                const docs = snap.docs.map(d => d.data());
                
                if(heroImages) heroImages.innerText = docs.length;
                if(document.getElementById('adminPhotoCount')) 
                    document.getElementById('adminPhotoCount').innerText = docs.length;
                
                if(docs.length > 0) {
                    if(empty) empty.classList.add('hidden');
                    grid.innerHTML = '';
                    
                    docs.forEach(img => {
                        const div = document.createElement('div');
                        div.className = "gallery-item";
                        div.innerHTML = `
                            <img src="${img.image}" class="w-full h-48 object-cover">
                            <div class="overlay">
                                <p class="text-sm">${img.caption || 'صورة من المؤتمر'}</p>
                            </div>
                        `;
                        div.onclick = () => window.open(img.image, '_blank');
                        grid.appendChild(div);
                    });
                } else {
                    if(empty) empty.classList.remove('hidden');
                }
            });
        }

        // التسجيل
        document.getElementById('regForm')?.addEventListener('submit', async (e) => {
            e.preventDefault();
            
            const name = document.getElementById('fullName').value;
            const email = document.getElementById('email').value;
            const phone = document.getElementById('phone').value;
            const track = document.getElementById('track').value;
            
            try {
                await addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'registrants'), {
                    name: name,
                    email: email,
                    phone: phone,
                    track: track,
                    createdAt: serverTimestamp()
                });
                
                await addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'activities'), {
                    message: `تسجيل جديد: ${name}`,
                    user: 'نظام التسجيل',
                    userId: 'system',
                    createdAt: serverTimestamp()
                });
                
                e.target.reset();
                showSuccess('تم تسجيلك بنجاح');
                
            } catch(error) {
                console.error(error);
                showError('فشل التسجيل');
            }
        });

        function syncRegistrants() {
            const q = query(collection(db, 'artifacts', appId, 'public', 'data', 'registrants'), orderBy('createdAt', 'desc'));
            
            onSnapshot(q, (snap) => {
                const list = snap.docs.map(d => ({id: d.id, ...d.data()}));
                const count = list.length;
                
                document.getElementById('totalCount').innerText = count;
                document.getElementById('liveRegistrantCount').innerText = count;
                document.getElementById('heroRegistrants').innerText = count;
                document.getElementById('adminRegCount').innerText = count;
                
                const table = document.getElementById('registrantsTable');
                if(!table) return;
                
                table.innerHTML = '';
                list.forEach(r => {
                    const tr = document.createElement('tr');
                    tr.className = "hover:bg-slate-50 transition";
                    tr.innerHTML = `
                        <td class="p-3 font-medium">${r.name || ''}</td>
                        <td class="p-3 text-slate-600">${r.email || ''}</td>
                        <td class="p-3 text-slate-600">${r.phone || ''}</td>
                        <td class="p-3"><span class="bg-blue-50 text-blue-600 px-2 py-1 rounded text-sm">${r.track || 'حضور'}</span></td>
                        <td class="p-3">
                            <button class="text-red-500 hover:text-red-700 delete-btn" data-id="${r.id}">
                                <i class="fas fa-trash"></i>
                            </button>
                        </td>
                    `;
                    table.appendChild(tr);
                });
                
                // حذف
                document.querySelectorAll('.delete-btn').forEach(btn => {
                    btn.addEventListener('click', async () => {
                        if(!confirm('تأكيد حذف هذا التسجيل؟')) return;
                        
                        try {
                            await deleteDoc(doc(db, 'artifacts', appId, 'public', 'data', 'registrants', btn.dataset.id));
                            showSuccess('تم الحذف');
                        } catch(error) {
                            console.error(error);
                            showError('فشل الحذف');
                        }
                    });
                });
            });
        }

        function syncStats() {
            // إحصائيات إضافية
        }

        // دخول المسؤول
        window.checkAdmin = () => {
            const pass = document.getElementById('adminPass').value;
            if(pass === "123456") {
                document.getElementById('admin-login').classList.add('hidden');
                document.getElementById('admin-content').classList.remove('hidden');
                
                addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'activities'), {
                    message: 'دخل المسؤول إلى لوحة التحكم',
                    user: 'نظام',
                    userId: 'system',
                    createdAt: serverTimestamp()
                }).catch(console.error);
                
            } else {
                showError('كلمة المرور خاطئة');
            }
        };
        
        window.logoutAdmin = () => {
            document.getElementById('admin-login').classList.remove('hidden');
            document.getElementById('admin-content').classList.add('hidden');
            document.getElementById('adminPass').value = '';
            
            addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'activities'), {
                message: 'خرج المسؤول من لوحة التحكم',
                user: 'نظام',
                userId: 'system',
                createdAt: serverTimestamp()
            }).catch(console.error);
        };

        // تحديث التقدم كل دقيقة
        setInterval(() => {
            const total = parseInt(document.getElementById('day1Count')?.innerText || 0) + 
                         parseInt(document.getElementById('day2Count')?.innerText || 0);
            updateProgress(total);
        }, 60000);
    </script>
</body>
</html>
