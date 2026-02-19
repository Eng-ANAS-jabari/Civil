<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CIVILTCTH 2 | المؤتمر الهندسي المتكامل</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;700&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Tajawal', sans-serif; scroll-behavior: smooth; }
        .hero-gradient { background: linear-gradient(135deg, #0f172a 0%, #1e3a8a 100%); }
        .glass { background: rgba(255, 255, 255, 0.9); backdrop-filter: blur(10px); }
        .upload-area { border: 2px dashed #cbd5e1; transition: all 0.3s; cursor: pointer; }
        .upload-area:hover { border-color: #3b82f6; background: #eff6ff; }
        .section-padding { padding-top: 5rem; padding-bottom: 5rem; }
        .tab-active { border-bottom: 4px solid #3b82f6; color: #1e40af; font-weight: bold; }
    </style>
</head>
<body class="bg-slate-50 text-slate-900">

    <!-- Navigation -->
    <nav class="fixed w-full z-50 glass shadow-md py-3">
        <div class="container mx-auto px-6 flex justify-between items-center">
            <div class="flex items-center gap-2">
                <i class="fas fa-microchip text-blue-700 text-3xl"></i>
                <span class="text-2xl font-bold text-slate-800">CIVILTCTH 2</span>
            </div>
            <div class="hidden lg:flex space-x-reverse space-x-6 font-medium">
                <a href="#agenda" class="hover:text-blue-600 transition">الأجندة</a>
                <a href="#register" class="hover:text-blue-600 transition">التسجيل</a>
                <a href="#gallery" class="hover:text-blue-600 transition">المعرض</a>
                <a href="#admin-section" class="text-red-600 font-bold hover:underline">لوحة التحكم</a>
            </div>
        </div>
    </nav>

    <!-- Hero -->
    <section class="hero-gradient min-h-[60vh] flex items-center pt-20 text-white relative">
        <div class="container mx-auto px-6 text-center">
            <h1 class="text-5xl md:text-7xl font-extrabold mb-6">CIVILTCTH 2</h1>
            <p class="text-2xl text-blue-300 mb-8">مؤتمر الهندسة المدنية والتكنولوجيا الحديثة - الخليل</p>
            <div class="flex justify-center gap-4">
                <a href="#register" class="bg-blue-600 px-8 py-3 rounded-xl font-bold hover:bg-blue-700 transition shadow-lg">سجل الآن</a>
                <a href="#gallery" class="bg-white/10 px-8 py-3 rounded-xl font-bold hover:bg-white/20 transition">مشاهدة المعرض</a>
            </div>
        </div>
    </section>

    <!-- Agenda Section (Dynamic) -->
    <section id="agenda" class="section-padding bg-white">
        <div class="container mx-auto px-6">
            <h2 class="text-3xl font-bold mb-12 text-center underline decoration-blue-500 underline-offset-8">أجندة المؤتمر</h2>
            <div class="grid md:grid-cols-2 gap-12 max-w-6xl mx-auto">
                
                <!-- Day 1 List -->
                <div class="space-y-6">
                    <h3 class="text-2xl font-bold text-blue-800 border-b-2 border-blue-100 pb-2"><i class="fas fa-calendar-day ml-2"></i> اليوم الأول</h3>
                    <div id="agenda-day1" class="space-y-4">
                        <p class="text-slate-400 italic">بانتظار إضافة الفقرات من قبل المسؤول...</p>
                    </div>
                </div>

                <!-- Day 2 List -->
                <div class="space-y-6">
                    <h3 class="text-2xl font-bold text-indigo-800 border-b-2 border-indigo-100 pb-2"><i class="fas fa-calendar-check ml-2"></i> اليوم الثاني</h3>
                    <div id="agenda-day2" class="space-y-4">
                        <p class="text-slate-400 italic">بانتظار إضافة الفقرات من قبل المسؤول...</p>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- Registration -->
    <section id="register" class="section-padding bg-blue-50">
        <div class="container mx-auto px-6 max-w-4xl">
            <div class="bg-white p-8 md:p-12 rounded-[2.5rem] shadow-xl border border-blue-100">
                <h2 class="text-3xl font-bold text-center mb-8">نموذج التسجيل</h2>
                <form id="regForm" class="grid md:grid-cols-2 gap-6">
                    <input type="text" id="fullName" placeholder="الاسم الكامل" required class="w-full px-4 py-3 rounded-xl border focus:ring-2 focus:ring-blue-500 outline-none">
                    <input type="email" id="email" placeholder="البريد الإلكتروني" required class="w-full px-4 py-3 rounded-xl border focus:ring-2 focus:ring-blue-500 outline-none">
                    <input type="tel" id="phone" placeholder="رقم الهاتف" required class="w-full px-4 py-3 rounded-xl border focus:ring-2 focus:ring-blue-500 outline-none">
                    <select id="track" class="w-full px-4 py-3 rounded-xl border focus:ring-2 focus:ring-blue-500 outline-none">
                        <option value="attendee">حضور فقط</option>
                        <option value="bridge">مسابقة الجسور</option>
                        <option value="hackathon">هكاثون عين سارة</option>
                    </select>
                    <button type="submit" id="regBtn" class="md:col-span-2 bg-blue-600 text-white py-4 rounded-xl font-bold text-lg hover:bg-blue-700 transition">إرسال التسجيل</button>
                </form>
                <div id="regStatus" class="mt-4 hidden text-center p-3 rounded-lg font-bold"></div>
            </div>
        </div>
    </section>

    <!-- Photo Gallery Section -->
    <section id="gallery" class="section-padding bg-white">
        <div class="container mx-auto px-6">
            <h2 class="text-3xl font-bold text-center mb-12">معرض الصور</h2>
            <div class="flex justify-center gap-8 mb-12 border-b">
                <button onclick="switchGallery('tech1')" id="tab-tech1" class="pb-4 px-4 transition tab-active">Civil Tech 1</button>
                <button onclick="switchGallery('tech2')" id="tab-tech2" class="pb-4 px-4 transition">Civil Tech 2 (الحالي)</button>
            </div>
            <div id="gallery-tech1" class="grid grid-cols-2 md:grid-cols-4 gap-4">
                <img src="https://images.unsplash.com/photo-1581094794329-c8112a89af12?q=80&w=400" class="rounded-xl h-48 w-full object-cover shadow-sm">
                <img src="https://images.unsplash.com/photo-1503387762-592dea58ef21?q=80&w=400" class="rounded-xl h-48 w-full object-cover shadow-sm">
            </div>
            <div id="gallery-tech2" class="hidden grid grid-cols-2 md:grid-cols-4 gap-4">
                <p id="empty-msg" class="col-span-full text-center text-slate-400 py-10 italic">سيقوم المسؤول برفع صور المؤتمر قريباً...</p>
            </div>
        </div>
    </section>

    <!-- Admin Panel -->
    <section id="admin-section" class="section-padding bg-slate-100 border-t-4 border-red-500">
        <div class="container mx-auto px-6">
            <div id="admin-login" class="text-center max-w-md mx-auto">
                <h2 class="text-2xl font-bold mb-4 text-red-700">لوحة تحكم المسؤول</h2>
                <input type="password" id="adminPass" placeholder="كلمة المرور" class="w-full px-4 py-2 rounded border mb-4 outline-none">
                <button onclick="checkAdmin()" class="bg-red-600 text-white px-10 py-2 rounded font-bold shadow-md">دخول</button>
            </div>

            <div id="admin-content" class="hidden space-y-12">
                
                <!-- 1. Agenda Manager -->
                <div class="bg-white p-8 rounded-3xl shadow-sm border border-green-200">
                    <h3 class="text-2xl font-bold mb-6 text-green-800"><i class="fas fa-tasks ml-2"></i> إدارة الأجندة</h3>
                    <form id="agendaForm" class="grid md:grid-cols-4 gap-4">
                        <input type="text" id="agendaTitle" placeholder="عنوان الفقرة" required class="px-4 py-2 border rounded-lg">
                        <input type="text" id="agendaTime" placeholder="الوقت (مثلاً 09:00 - 10:00)" required class="px-4 py-2 border rounded-lg">
                        <select id="agendaDay" class="px-4 py-2 border rounded-lg">
                            <option value="1">اليوم الأول</option>
                            <option value="2">اليوم الثاني</option>
                        </select>
                        <button type="submit" id="agendaBtn" class="bg-green-600 text-white rounded-lg font-bold hover:bg-green-700">إضافة الفقرة</button>
                    </form>
                </div>

                <!-- 2. Photo Upload -->
                <div class="bg-white p-8 rounded-3xl shadow-sm border border-blue-200">
                    <h3 class="text-2xl font-bold mb-6 text-blue-800"><i class="fas fa-upload ml-2"></i> رفع صور المؤتمر الثاني</h3>
                    <form id="uploadForm" class="space-y-4">
                        <div id="dropZone" class="upload-area p-8 text-center rounded-2xl bg-slate-50">
                            <input type="file" id="fileInput" accept="image/*" class="hidden">
                            <div id="uploadPrompt">إضغط لاختيار صورة</div>
                            <img id="imgPreview" class="hidden max-h-48 mx-auto mt-4 rounded-xl shadow">
                        </div>
                        <input type="text" id="upCaption" placeholder="وصف الصورة" class="w-full px-4 py-2 border rounded-lg">
                        <button type="submit" id="upBtn" class="w-full bg-blue-700 text-white py-3 rounded-xl font-bold">نشر الصورة</button>
                    </form>
                </div>

                <!-- 3. Registrants Stats -->
                <div class="bg-white p-8 rounded-3xl shadow-sm border">
                    <h3 class="text-2xl font-bold mb-6">المسجلين (<span id="totalCount">0</span>)</h3>
                    <div class="overflow-x-auto">
                        <table class="w-full text-right">
                            <thead class="bg-slate-50 border-b">
                                <tr>
                                    <th class="p-3">الاسم</th>
                                    <th class="p-3">الهاتف</th>
                                    <th class="p-3">المسار</th>
                                </tr>
                            </thead>
                            <tbody id="registrantsTable"></tbody>
                        </table>
                    </div>
                </div>
                
                <div class="text-center">
                    <button onclick="logoutAdmin()" class="text-red-600 font-bold underline">خروج</button>
                </div>
            </div>
        </div>
    </section>

    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
        import { getFirestore, collection, addDoc, onSnapshot, query, orderBy, deleteDoc, doc } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";
        import { getAuth, signInAnonymously, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";

        const firebaseConfig = JSON.parse(__firebase_config);
        const app = initializeApp(firebaseConfig);
        const db = getFirestore(app);
        const auth = getAuth(app);
        const appId = typeof __app_id !== 'undefined' ? __app_id : 'civiltcth2-dynamic-agenda';

        let user = null;

        signInAnonymously(auth);
        onAuthStateChanged(auth, u => {
            user = u;
            if(user) {
                syncAgenda();
                syncGallery();
                syncAdminStats();
            }
        });

        // 1. Agenda Management
        document.getElementById('agendaForm').onsubmit = async (e) => {
            e.preventDefault();
            const btn = document.getElementById('agendaBtn');
            btn.disabled = true;
            try {
                await addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'agenda'), {
                    title: document.getElementById('agendaTitle').value,
                    time: document.getElementById('agendaTime').value,
                    day: document.getElementById('agendaDay').value,
                    createdAt: new Date().toISOString()
                });
                e.target.reset();
            } catch(e) { console.error(e); }
            btn.disabled = false;
        };

        function syncAgenda() {
            onSnapshot(collection(db, 'artifacts', appId, 'public', 'data', 'agenda'), (snap) => {
                const day1 = document.getElementById('agenda-day1');
                const day2 = document.getElementById('agenda-day2');
                day1.innerHTML = ''; day2.innerHTML = '';
                
                const items = snap.docs.map(d => ({id: d.id, ...d.data()}));
                items.sort((a,b) => a.time.localeCompare(b.time)); // Sorting by time string

                items.forEach(item => {
                    const card = document.createElement('div');
                    card.className = "p-4 bg-white rounded-xl shadow-sm border-r-4 " + (item.day == "1" ? "border-blue-500" : "border-indigo-500");
                    card.innerHTML = `
                        <div class="flex justify-between items-start">
                            <div>
                                <span class="text-sm font-bold ${item.day == "1" ? "text-blue-600" : "text-indigo-600"}">${item.time}</span>
                                <p class="font-bold text-slate-800">${item.title}</p>
                            </div>
                            <!-- Admin only delete button logic could go here if needed -->
                        </div>
                    `;
                    if(item.day == "1") day1.appendChild(card);
                    else day2.appendChild(card);
                });

                if(day1.innerHTML === '') day1.innerHTML = '<p class="text-slate-400 italic text-sm">لا يوجد فقرات مضافة بعد.</p>';
                if(day2.innerHTML === '') day2.innerHTML = '<p class="text-slate-400 italic text-sm">لا يوجد فقرات مضافة بعد.</p>';
            });
        }

        // 2. Tabs & Admin Auth
        window.switchGallery = (type) => {
            const t1 = document.getElementById('gallery-tech1');
            const t2 = document.getElementById('gallery-tech2');
            const btn1 = document.getElementById('tab-tech1');
            const btn2 = document.getElementById('tab-tech2');
            if(type === 'tech1') { t1.classList.remove('hidden'); t2.classList.add('hidden'); btn1.classList.add('tab-active'); btn2.classList.remove('tab-active'); }
            else { t1.classList.add('hidden'); t2.classList.remove('hidden'); btn1.classList.remove('tab-active'); btn2.classList.add('tab-active'); }
        };

        window.checkAdmin = () => {
            if(document.getElementById('adminPass').value === "123456") {
                document.getElementById('admin-login').classList.add('hidden');
                document.getElementById('admin-content').classList.remove('hidden');
            } else alert("خطأ!");
        };
        window.logoutAdmin = () => {
            document.getElementById('admin-login').classList.remove('hidden');
            document.getElementById('admin-content').classList.add('hidden');
        };

        // 3. Sync Registrants & Gallery (Previous Logic)
        document.getElementById('regForm').onsubmit = async (e) => {
            e.preventDefault();
            await addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'registrants'), {
                name: document.getElementById('fullName').value,
                email: document.getElementById('email').value,
                phone: document.getElementById('phone').value,
                track: document.getElementById('track').value,
                time: new Date().toISOString()
            });
            document.getElementById('regStatus').className = "mt-4 p-3 rounded-lg bg-green-100 text-green-700 block";
            document.getElementById('regStatus').innerText = "تم التسجيل!";
            e.target.reset();
        };

        const fileInput = document.getElementById('fileInput');
        document.getElementById('dropZone').onclick = () => fileInput.click();
        fileInput.onchange = (e) => {
            const file = e.target.files[0];
            if(file) {
                const reader = new FileReader();
                reader.onload = (ev) => {
                    document.getElementById('imgPreview').src = ev.target.result;
                    document.getElementById('imgPreview').classList.remove('hidden');
                };
                reader.readAsDataURL(file);
            }
        };

        document.getElementById('uploadForm').onsubmit = async (e) => {
            e.preventDefault();
            const img = document.getElementById('imgPreview').src;
            if(!img) return;
            await addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'gallery_v2'), {
                image: img, caption: document.getElementById('upCaption').value, time: new Date().toISOString()
            });
            e.target.reset();
            document.getElementById('imgPreview').classList.add('hidden');
            alert("تم الرفع!");
        };

        function syncGallery() {
            onSnapshot(collection(db, 'artifacts', appId, 'public', 'data', 'gallery_v2'), (snap) => {
                const grid = document.getElementById('gallery-tech2');
                const empty = document.getElementById('empty-msg');
                const docs = snap.docs.map(d => d.data());
                if(docs.length > 0) {
                    empty.classList.add('hidden');
                    grid.innerHTML = '';
                    docs.forEach(p => {
                        grid.innerHTML += `<div class="bg-white p-1 rounded-xl border shadow-sm"><img src="${p.image}" class="rounded-lg h-40 w-full object-cover"><p class="text-[10px] text-center mt-1 truncate">${p.caption}</p></div>`;
                    });
                }
            });
        }

        function syncAdminStats() {
            onSnapshot(collection(db, 'artifacts', appId, 'public', 'data', 'registrants'), (snap) => {
                const list = snap.docs.map(d => d.data());
                document.getElementById('totalCount').innerText = list.length;
                const table = document.getElementById('registrantsTable');
                table.innerHTML = '';
                list.forEach(r => {
                    table.innerHTML += `<tr class="border-b text-sm"><td class="p-3 font-bold">${r.name}</td><td class="p-3">${r.phone}</td><td class="p-3 text-blue-600">${r.track}</td></tr>`;
                });
            });
        }
    </script>
</body>
</html>
