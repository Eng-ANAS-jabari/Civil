<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CIVILTCTH 2 | المؤتمر الهندسي المتكامل</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;500;700;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #1e40af;
            --secondary: #3b82f6;
            --accent: #ef4444;
        }
        body { font-family: 'Tajawal', sans-serif; scroll-behavior: smooth; overflow-x: hidden; }
        .hero-gradient { background: radial-gradient(circle at top right, #1e3a8a, #0f172a); }
        .glass { background: rgba(255, 255, 255, 0.85); backdrop-filter: blur(12px); border-bottom: 1px solid rgba(255,255,255,0.2); }
        .card-hover { transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1); }
        .card-hover:hover { transform: translateY(-5px); box-shadow: 0 20px 25px -5px rgb(0 0 0 / 0.1); }
        .upload-area { border: 2px dashed #cbd5e1; transition: all 0.3s ease; }
        .upload-area.active { border-color: var(--secondary); background: #eff6ff; }
        .custom-scrollbar::-webkit-scrollbar { width: 6px; }
        .custom-scrollbar::-webkit-scrollbar-track { background: #f1f1f1; }
        .custom-scrollbar::-webkit-scrollbar-thumb { background: #cbd5e1; border-radius: 10px; }
        .section-title::after { content: ''; display: block; width: 60px; height: 4px; background: var(--secondary); margin: 10px auto; border-radius: 2px; }
        
        /* Animations */
        @keyframes fadeIn { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }
        .fade-in { animation: fadeIn 0.6s ease-out forwards; }
    </style>
</head>
<body class="bg-slate-50 text-slate-900 custom-scrollbar">

    <!-- Navbar -->
    <nav class="fixed w-full z-50 glass shadow-sm py-4">
        <div class="container mx-auto px-6 flex justify-between items-center">
            <div class="flex items-center gap-3">
                <div class="bg-blue-700 p-2 rounded-lg shadow-lg">
                    <i class="fas fa-city text-white text-xl"></i>
                </div>
                <span class="text-2xl font-black tracking-tighter text-slate-800">CIVILTCTH <span class="text-blue-600">2</span></span>
            </div>
            <div class="hidden md:flex space-x-reverse space-x-8 font-semibold">
                <a href="#agenda" class="text-slate-600 hover:text-blue-600 transition">الأجندة</a>
                <a href="#register" class="text-slate-600 hover:text-blue-600 transition">التسجيل</a>
                <a href="#gallery" class="text-slate-600 hover:text-blue-600 transition">المعرض</a>
                <a href="#admin-section" class="bg-red-50 text-red-600 px-4 py-1 rounded-full border border-red-100 hover:bg-red-600 hover:text-white transition">الإدارة</a>
            </div>
            <button class="md:hidden text-2xl text-slate-800"><i class="fas fa-bars"></i></button>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero-gradient min-h-[85vh] flex items-center pt-24 text-white relative overflow-hidden">
        <div class="absolute inset-0 opacity-10">
            <div class="absolute top-0 left-0 w-96 h-96 bg-blue-500 rounded-full mix-blend-multiply filter blur-3xl"></div>
            <div class="absolute bottom-0 right-0 w-96 h-96 bg-indigo-500 rounded-full mix-blend-multiply filter blur-3xl"></div>
        </div>
        <div class="container mx-auto px-6 relative z-10 text-center">
            <span class="bg-blue-500/20 text-blue-300 px-4 py-2 rounded-full text-sm font-bold mb-6 inline-block border border-blue-500/30">تحت رعاية جامعة بوليتكنك فلسطين</span>
            <h1 class="text-5xl md:text-8xl font-black mb-6 leading-tight">الهندسة المدنية <br><span class="text-transparent bg-clip-text bg-gradient-to-r from-blue-400 to-indigo-300">والتكنولوجيا الحديثة</span></h1>
            <p class="text-xl md:text-2xl text-slate-300 mb-10 max-w-2xl mx-auto leading-relaxed">المؤتمر الهندسي المتكامل في نسخته الثانية - الخليل 2025</p>
            <div class="flex flex-col sm:flex-row justify-center gap-5">
                <a href="#register" class="bg-blue-600 px-10 py-4 rounded-2xl font-bold text-lg hover:bg-blue-700 transition shadow-[0_10px_20px_rgba(37,99,235,0.3)] flex items-center justify-center gap-2">
                    <i class="fas fa-user-plus"></i> سجل حضورك الآن
                </a>
                <a href="#gallery" class="bg-white/10 backdrop-blur-md border border-white/20 px-10 py-4 rounded-2xl font-bold text-lg hover:bg-white/20 transition flex items-center justify-center gap-2">
                    <i class="fas fa-images"></i> معرض الصور
                </a>
            </div>
        </div>
    </section>

    <!-- Agenda Section -->
    <section id="agenda" class="py-24 bg-white">
        <div class="container mx-auto px-6">
            <h2 class="text-4xl font-extrabold text-center mb-4 section-title">أجندة المؤتمر</h2>
            <p class="text-center text-slate-500 mb-16">تابع تفاصيل الفقرات والجلسات العلمية</p>
            
            <div class="grid lg:grid-cols-2 gap-16 max-w-7xl mx-auto">
                <!-- Day 1 -->
                <div class="fade-in">
                    <div class="flex items-center gap-4 mb-8">
                        <div class="w-12 h-12 bg-blue-100 text-blue-700 rounded-2xl flex items-center justify-center text-xl shadow-inner">
                            <i class="fas fa-sun"></i>
                        </div>
                        <h3 class="text-2xl font-black text-slate-800">اليوم الأول <span class="text-sm font-normal text-slate-400 block mt-1">المواضيع التقنية والافتتاح</span></h3>
                    </div>
                    <div id="agenda-day1" class="space-y-6 relative border-r-2 border-slate-100 pr-8">
                        <!-- Items injected by JS -->
                    </div>
                </div>

                <!-- Day 2 -->
                <div class="fade-in" style="animation-delay: 0.2s">
                    <div class="flex items-center gap-4 mb-8">
                        <div class="w-12 h-12 bg-indigo-100 text-indigo-700 rounded-2xl flex items-center justify-center text-xl shadow-inner">
                            <i class="fas fa-moon"></i>
                        </div>
                        <h3 class="text-2xl font-black text-slate-800">اليوم الثاني <span class="text-sm font-normal text-slate-400 block mt-1">المسابقات والعروض الختامية</span></h3>
                    </div>
                    <div id="agenda-day2" class="space-y-6 relative border-r-2 border-slate-100 pr-8">
                        <!-- Items injected by JS -->
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Registration -->
    <section id="register" class="py-24 bg-slate-50">
        <div class="container mx-auto px-6">
            <div class="max-w-5xl mx-auto bg-white rounded-[3rem] shadow-2xl shadow-blue-900/5 overflow-hidden border border-slate-100">
                <div class="grid md:grid-cols-5">
                    <div class="md:col-span-2 bg-blue-700 p-12 text-white flex flex-col justify-center">
                        <h2 class="text-3xl font-bold mb-6">انضم إلينا</h2>
                        <p class="text-blue-100 mb-8 leading-relaxed">كن جزءاً من أكبر تجمع هندسي في فلسطين. احجز مقعدك الآن وشارك في الورشات والمسابقات.</p>
                        <ul class="space-y-4">
                            <li class="flex items-center gap-3"><i class="fas fa-check-circle text-blue-300"></i> شهادات حضور معتمدة</li>
                            <li class="flex items-center gap-3"><i class="fas fa-check-circle text-blue-300"></i> جوائز نقدية للمسابقات</li>
                            <li class="flex items-center gap-3"><i class="fas fa-check-circle text-blue-300"></i> تواصل مع شركات رائدة</li>
                        </ul>
                    </div>
                    <div class="md:col-span-3 p-12">
                        <form id="regForm" class="space-y-6">
                            <div class="grid md:grid-cols-2 gap-6">
                                <div class="space-y-2">
                                    <label class="text-sm font-bold text-slate-700 pr-2">الاسم الكامل</label>
                                    <input type="text" id="fullName" required class="w-full px-5 py-3 rounded-xl bg-slate-50 border-none ring-1 ring-slate-200 focus:ring-2 focus:ring-blue-500 outline-none transition" placeholder="أدخل اسمك الثلاثي">
                                </div>
                                <div class="space-y-2">
                                    <label class="text-sm font-bold text-slate-700 pr-2">رقم التواصل</label>
                                    <input type="tel" id="phone" required class="w-full px-5 py-3 rounded-xl bg-slate-50 border-none ring-1 ring-slate-200 focus:ring-2 focus:ring-blue-500 outline-none transition" placeholder="05x-xxxxxxx">
                                </div>
                            </div>
                            <div class="space-y-2">
                                <label class="text-sm font-bold text-slate-700 pr-2">البريد الإلكتروني</label>
                                <input type="email" id="email" required class="w-full px-5 py-3 rounded-xl bg-slate-50 border-none ring-1 ring-slate-200 focus:ring-2 focus:ring-blue-500 outline-none transition" placeholder="name@example.com">
                            </div>
                            <div class="space-y-2">
                                <label class="text-sm font-bold text-slate-700 pr-2">المسار المطلوب</label>
                                <select id="track" class="w-full px-5 py-3 rounded-xl bg-slate-50 border-none ring-1 ring-slate-200 focus:ring-2 focus:ring-blue-500 outline-none transition">
                                    <option value="attendee">حضور جلسات المؤتمر</option>
                                    <option value="bridge">مسابقة الجسور الخشبية</option>
                                    <option value="hackathon">هكاثون التكنولوجيا المدنية</option>
                                </select>
                            </div>
                            <button type="submit" id="regBtn" class="w-full bg-slate-900 text-white py-4 rounded-xl font-bold text-lg hover:bg-blue-600 transition shadow-lg flex items-center justify-center gap-2">
                                تأكيد تسجيل البيانات <i class="fas fa-paper-plane"></i>
                            </button>
                        </form>
                        <div id="regStatus" class="mt-6 hidden text-center p-4 rounded-xl"></div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Gallery -->
    <section id="gallery" class="py-24 bg-white">
        <div class="container mx-auto px-6">
            <h2 class="text-4xl font-extrabold text-center mb-4 section-title">معرض الصور</h2>
            <div class="flex justify-center mb-12">
                <div class="inline-flex bg-slate-100 p-1.5 rounded-2xl">
                    <button onclick="switchGallery('tech1')" id="tab-tech1" class="px-8 py-2.5 rounded-xl font-bold transition tab-active">النسخة الأولى</button>
                    <button onclick="switchGallery('tech2')" id="tab-tech2" class="px-8 py-2.5 rounded-xl font-bold transition">النسخة الثانية</button>
                </div>
            </div>
            
            <div id="gallery-tech1" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
                <!-- Static Placeholders -->
                <div class="group relative overflow-hidden rounded-3xl h-64 bg-slate-200 card-hover">
                    <img src="https://images.unsplash.com/photo-1581094794329-c8112a89af12?auto=format&fit=crop&w=600" class="w-full h-full object-cover transition duration-500 group-hover:scale-110">
                    <div class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent opacity-0 group-hover:opacity-100 transition duration-300 flex items-end p-6">
                        <p class="text-white font-medium">افتتاح النسخة الأولى</p>
                    </div>
                </div>
                <div class="group relative overflow-hidden rounded-3xl h-64 bg-slate-200 card-hover">
                    <img src="https://images.unsplash.com/photo-1503387762-592dea58ef21?auto=format&fit=crop&w=600" class="w-full h-full object-cover transition duration-500 group-hover:scale-110">
                    <div class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent opacity-0 group-hover:opacity-100 transition duration-300 flex items-end p-6">
                        <p class="text-white font-medium">المشاريع الهندسية</p>
                    </div>
                </div>
            </div>
            
            <div id="gallery-tech2" class="hidden grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6 min-h-[300px]">
                <!-- Dynamic Content -->
                <div id="empty-msg" class="col-span-full flex flex-col items-center justify-center text-slate-400 py-20">
                    <i class="fas fa-camera-retro text-5xl mb-4"></i>
                    <p class="italic">لم يتم رفع صور لهذا المؤتمر بعد</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Admin Panel -->
    <section id="admin-section" class="py-24 bg-slate-900 text-white">
        <div class="container mx-auto px-6">
            <div id="admin-login" class="max-w-md mx-auto text-center p-12 bg-white/5 backdrop-blur-xl rounded-[2.5rem] border border-white/10">
                <div class="w-20 h-20 bg-red-600/20 text-red-500 rounded-full flex items-center justify-center text-3xl mx-auto mb-6">
                    <i class="fas fa-lock"></i>
                </div>
                <h2 class="text-3xl font-bold mb-2">منطقة المسؤول</h2>
                <p class="text-slate-400 mb-8 italic">يرجى إدخال رمز الوصول للإدارة</p>
                <input type="password" id="adminPass" placeholder="••••••" class="w-full bg-slate-800 border-none ring-1 ring-white/10 px-6 py-4 rounded-2xl mb-6 text-center text-2xl tracking-[1em] focus:ring-red-500 outline-none transition">
                <button onclick="checkAdmin()" class="w-full bg-red-600 hover:bg-red-700 text-white py-4 rounded-2xl font-bold transition shadow-xl">تحقق من الهوية</button>
            </div>

            <div id="admin-content" class="hidden space-y-10">
                <div class="flex flex-col md:flex-row justify-between items-center gap-6 mb-10">
                    <h2 class="text-4xl font-black">لوحة الإدارة <span class="text-blue-500">Live</span></h2>
                    <button onclick="logoutAdmin()" class="bg-white/10 hover:bg-red-600 px-6 py-2 rounded-xl transition flex items-center gap-2 border border-white/10">
                        <i class="fas fa-sign-out-alt"></i> تسجيل الخروج
                    </button>
                </div>

                <div class="grid lg:grid-cols-2 gap-10">
                    <!-- Agenda Manager -->
                    <div class="bg-white/5 p-10 rounded-[2.5rem] border border-white/10">
                        <h3 class="text-2xl font-bold mb-8 flex items-center gap-3">
                            <i class="fas fa-calendar-plus text-green-500"></i> تنظيم الأجندة
                        </h3>
                        <form id="agendaForm" class="space-y-4">
                            <input type="text" id="agendaTitle" placeholder="عنوان الفقرة أو الجلسة" required class="w-full bg-slate-800 border-none px-5 py-4 rounded-xl outline-none focus:ring-2 focus:ring-green-500">
                            <div class="grid grid-cols-2 gap-4">
                                <input type="time" id="agendaTime" required class="w-full bg-slate-800 border-none px-5 py-4 rounded-xl outline-none focus:ring-2 focus:ring-green-500">
                                <select id="agendaDay" class="w-full bg-slate-800 border-none px-5 py-4 rounded-xl outline-none focus:ring-2 focus:ring-green-500">
                                    <option value="1">اليوم الأول</option>
                                    <option value="2">اليوم الثاني</option>
                                </select>
                            </div>
                            <button type="submit" class="w-full bg-green-600 hover:bg-green-700 py-4 rounded-xl font-bold transition">نشر في الموقع</button>
                        </form>
                    </div>

                    <!-- Photo Uploader -->
                    <div class="bg-white/5 p-10 rounded-[2.5rem] border border-white/10">
                        <h3 class="text-2xl font-bold mb-8 flex items-center gap-3">
                            <i class="fas fa-cloud-upload-alt text-blue-500"></i> مركز الرفع
                        </h3>
                        <form id="uploadForm" class="space-y-4">
                            <div id="dropZone" class="upload-area h-48 flex flex-col items-center justify-center rounded-2xl bg-slate-800/50 hover:bg-slate-800 transition group cursor-pointer">
                                <input type="file" id="fileInput" accept="image/*" class="hidden">
                                <div id="uploadPrompt" class="text-center group-hover:scale-110 transition duration-300">
                                    <i class="fas fa-image text-4xl mb-2 text-slate-500"></i>
                                    <p class="text-slate-400">اضغط لرفع صورة</p>
                                </div>
                                <img id="imgPreview" class="hidden h-full w-full object-cover rounded-2xl">
                            </div>
                            <input type="text" id="upCaption" placeholder="وصف الصورة (اختياري)" class="w-full bg-slate-800 border-none px-5 py-4 rounded-xl outline-none focus:ring-2 focus:ring-blue-500">
                            <button type="submit" class="w-full bg-blue-600 hover:bg-blue-700 py-4 rounded-xl font-bold transition">نشر في المعرض</button>
                        </form>
                    </div>
                </div>

                <!-- Stats Table -->
                <div class="bg-white/5 p-10 rounded-[2.5rem] border border-white/10">
                    <div class="flex justify-between items-center mb-10">
                        <h3 class="text-2xl font-bold">قائمة الحضور</h3>
                        <div class="bg-blue-600 px-4 py-1 rounded-full text-sm font-bold">إجمالي: <span id="totalCount">0</span></div>
                    </div>
                    <div class="overflow-x-auto">
                        <table class="w-full text-right">
                            <thead class="bg-white/5">
                                <tr>
                                    <th class="p-5 font-bold rounded-r-2xl">الاسم</th>
                                    <th class="p-5 font-bold">التواصل</th>
                                    <th class="p-5 font-bold">المسار</th>
                                    <th class="p-5 font-bold rounded-l-2xl text-center">التحكم</th>
                                </tr>
                            </thead>
                            <tbody id="registrantsTable" class="divide-y divide-white/5">
                                <!-- Data injected by JS -->
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <footer class="bg-slate-950 text-slate-500 py-16 text-center border-t border-white/5">
        <div class="container mx-auto px-6">
            <div class="mb-8">
                <span class="text-2xl font-black text-white">CIVILTCTH 2</span>
            </div>
            <p class="max-w-md mx-auto mb-8">جميع الحقوق محفوظة © 2025 - لجنة التنظيم المركزية لمؤتمر الهندسة والتكنولوجيا الحديثة.</p>
            <div class="flex justify-center gap-6 text-xl">
                <a href="#" class="hover:text-white transition"><i class="fab fa-facebook"></i></a>
                <a href="#" class="hover:text-white transition"><i class="fab fa-linkedin"></i></a>
                <a href="#" class="hover:text-white transition"><i class="fab fa-instagram"></i></a>
            </div>
        </div>
    </footer>

    <!-- Firebase Logic -->
    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
        import { getFirestore, collection, addDoc, onSnapshot, deleteDoc, doc, serverTimestamp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";
        import { getAuth, signInAnonymously, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";

        const firebaseConfig = JSON.parse(__firebase_config);
        const app = initializeApp(firebaseConfig);
        const db = getFirestore(app);
        const auth = getAuth(app);
        const appId = typeof __app_id !== 'undefined' ? __app_id : 'civiltcth2-advanced-v2';

        // Auth
        signInAnonymously(auth);
        onAuthStateChanged(auth, user => {
            if(user) {
                initRealtimeSync();
            }
        });

        function initRealtimeSync() {
            syncAgenda();
            syncGallery();
            syncRegistrants();
        }

        // --- Agenda Sync ---
        function syncAgenda() {
            onSnapshot(collection(db, 'artifacts', appId, 'public', 'data', 'agenda'), (snap) => {
                const day1 = document.getElementById('agenda-day1');
                const day2 = document.getElementById('agenda-day2');
                day1.innerHTML = ''; day2.innerHTML = '';
                
                const items = snap.docs.map(d => ({id: d.id, ...d.data()}));
                items.sort((a,b) => (a.time || '').localeCompare(b.time || ''));

                items.forEach(item => {
                    const card = document.createElement('div');
                    card.className = "group relative p-6 bg-slate-50 rounded-2xl border-r-4 " + 
                                     (item.day == "1" ? "border-blue-500" : "border-indigo-500") + 
                                     " flex justify-between items-center transition hover:bg-white hover:shadow-md";
                    card.innerHTML = `
                        <div class="flex items-center gap-5">
                            <span class="text-blue-600 font-bold bg-white px-3 py-1 rounded-lg shadow-sm border border-slate-100">${item.time}</span>
                            <div>
                                <h4 class="font-bold text-slate-800 text-lg">${item.title}</h4>
                            </div>
                        </div>
                        ${!document.getElementById('admin-content').classList.contains('hidden') ? 
                          `<button onclick="window.deleteData('agenda', '${item.id}')" class="text-slate-300 hover:text-red-500 transition"><i class="fas fa-trash-alt"></i></button>` : ''}
                    `;
                    if(item.day == "1") day1.appendChild(card);
                    else day2.appendChild(card);
                });
            });
        }

        // --- Gallery Sync ---
        function syncGallery() {
            onSnapshot(collection(db, 'artifacts', appId, 'public', 'data', 'gallery_v2'), (snap) => {
                const grid = document.getElementById('gallery-tech2');
                const empty = document.getElementById('empty-msg');
                const docs = snap.docs.map(d => ({id: d.id, ...d.data()}));
                
                if(docs.length > 0) {
                    empty.classList.add('hidden');
                    grid.innerHTML = '';
                    docs.forEach(p => {
                        grid.innerHTML += `
                            <div class="group relative overflow-hidden rounded-3xl h-64 bg-slate-200 card-hover shadow-lg">
                                <img src="${p.image}" class="w-full h-full object-cover">
                                <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-black/20 to-transparent opacity-0 group-hover:opacity-100 transition duration-300 flex flex-col justify-end p-6">
                                    <p class="text-white font-medium mb-3">${p.caption || 'بدون وصف'}</p>
                                    ${!document.getElementById('admin-content').classList.contains('hidden') ? 
                                    `<button onclick="window.deleteData('gallery_v2', '${p.id}')" class="bg-red-600 text-white w-full py-2 rounded-xl text-sm font-bold shadow-lg"><i class="fas fa-trash"></i> حذف الصورة</button>` : ''}
                                </div>
                            </div>`;
                    });
                } else {
                    empty.classList.remove('hidden');
                    grid.innerHTML = '<div id="empty-msg" class="col-span-full flex flex-col items-center justify-center text-slate-400 py-20"><i class="fas fa-camera-retro text-5xl mb-4"></i><p class="italic">لم يتم رفع صور مؤخراً</p></div>';
                }
            });
        }

        // --- Registrants Sync ---
        function syncRegistrants() {
            onSnapshot(collection(db, 'artifacts', appId, 'public', 'data', 'registrants'), (snap) => {
                const list = snap.docs.map(d => ({id: d.id, ...d.data()}));
                document.getElementById('totalCount').innerText = list.length;
                const table = document.getElementById('registrantsTable');
                table.innerHTML = '';
                list.sort((a,b) => (b.time || 0) - (a.time || 0)).forEach(r => {
                    const tr = document.createElement('tr');
                    tr.className = "hover:bg-white/5 transition group";
                    tr.innerHTML = `
                        <td class="p-5 font-bold text-white">${r.name}</td>
                        <td class="p-5 text-slate-400">${r.phone}</td>
                        <td class="p-5"><span class="bg-blue-600/20 text-blue-400 px-3 py-1 rounded-full text-xs font-bold">${r.track}</span></td>
                        <td class="p-5 text-center">
                            <button onclick="window.deleteData('registrants', '${r.id}')" class="text-slate-600 hover:text-red-500 transition opacity-0 group-hover:opacity-100"><i class="fas fa-trash-alt"></i></button>
                        </td>
                    `;
                    table.appendChild(tr);
                });
            });
        }

        // Global Operations
        window.deleteData = async (col, id) => {
            if(confirm("هل أنت متأكد من الحذف النهائي؟")) {
                await deleteDoc(doc(db, 'artifacts', appId, 'public', 'data', col, id));
            }
        };

        // Form Handlers
        document.getElementById('regForm').onsubmit = async (e) => {
            e.preventDefault();
            const btn = document.getElementById('regBtn');
            btn.innerHTML = '<i class="fas fa-spinner fa-spin"></i> جاري التسجيل...';
            btn.disabled = true;
            
            try {
                await addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'registrants'), {
                    name: document.getElementById('fullName').value,
                    email: document.getElementById('email').value,
                    phone: document.getElementById('phone').value,
                    track: document.getElementById('track').value,
                    time: Date.now()
                });
                
                const status = document.getElementById('regStatus');
                status.className = "mt-6 p-4 rounded-xl bg-green-500/10 text-green-600 font-bold block";
                status.innerHTML = '<i class="fas fa-check-circle ml-2"></i> تم تسجيلك بنجاح! ننتظر حضورك.';
                e.target.reset();
            } catch(err) {
                console.error(err);
                alert("حدث خطأ في الاتصال، حاول مرة أخرى.");
            }
            btn.innerHTML = 'تأكيد تسجيل البيانات <i class="fas fa-paper-plane"></i>';
            btn.disabled = false;
        };

        document.getElementById('agendaForm').onsubmit = async (e) => {
            e.preventDefault();
            await addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'agenda'), {
                title: document.getElementById('agendaTitle').value,
                time: document.getElementById('agendaTime').value,
                day: document.getElementById('agendaDay').value
            });
            e.target.reset();
        };

        document.getElementById('uploadForm').onsubmit = async (e) => {
            e.preventDefault();
            const img = document.getElementById('imgPreview').src;
            if(!img || img.length < 500) return alert("يرجى اختيار صورة أولاً");
            
            await addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'gallery_v2'), {
                image: img,
                caption: document.getElementById('upCaption').value,
                time: Date.now()
            });
            
            e.target.reset();
            document.getElementById('imgPreview').classList.add('hidden');
            document.getElementById('uploadPrompt').classList.remove('hidden');
        };

        // File/Image Preview
        const fileInput = document.getElementById('fileInput');
        document.getElementById('dropZone').onclick = () => fileInput.click();
        fileInput.onchange = (e) => {
            const file = e.target.files[0];
            if(file) {
                if(file.size > 2 * 1024 * 1024) return alert("حجم الصورة كبير جداً (أقل من 2MB)");
                const reader = new FileReader();
                reader.onload = (ev) => {
                    document.getElementById('imgPreview').src = ev.target.result;
                    document.getElementById('imgPreview').classList.remove('hidden');
                    document.getElementById('uploadPrompt').classList.add('hidden');
                };
                reader.readAsDataURL(file);
            }
        };

        // UI Helpers
        window.switchGallery = (type) => {
            document.getElementById('gallery-tech1').classList.toggle('hidden', type !== 'tech1');
            document.getElementById('gallery-tech2').classList.toggle('hidden', type !== 'tech2');
            document.getElementById('tab-tech1').className = "px-8 py-2.5 rounded-xl font-bold transition " + (type === 'tech1' ? "bg-white shadow text-blue-600" : "text-slate-500");
            document.getElementById('tab-tech2').className = "px-8 py-2.5 rounded-xl font-bold transition " + (type === 'tech2' ? "bg-white shadow text-blue-600" : "text-slate-500");
        };

        window.checkAdmin = () => {
            if(document.getElementById('adminPass').value === "123456") {
                document.getElementById('admin-login').classList.add('hidden');
                document.getElementById('admin-content').classList.remove('hidden');
                initRealtimeSync();
            } else {
                alert("رمز الوصول غير صحيح!");
            }
        };

        window.logoutAdmin = () => {
            document.getElementById('admin-login').classList.remove('hidden');
            document.getElementById('admin-content').classList.add('hidden');
            document.getElementById('adminPass').value = '';
            initRealtimeSync();
        };

        // Init tabs
        switchGallery('tech1');
    </script>
</body>
</html>
