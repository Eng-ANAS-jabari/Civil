<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CIVILTCTH 2 | مؤتمر حي</title>
    <!-- Tailwind -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <!-- Google Fonts -->
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

    <!-- قائمة التنقل -->
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
    <section class="hero-gradient min-h-[60vh] flex items-center pt-20 text-white relative text-center">
        <div class="container mx-auto px-6">
            <h1 class="text-5xl md:text-7xl font-extrabold mb-6">CIVILTCTH 2</h1>
            <p class="text-2xl text-blue-300 mb-8">مؤتمر الهندسة المدنية والتكنولوجيا الحديثة - الخليل</p>
            <div class="flex justify-center gap-4">
                <a href="#register" class="bg-blue-600 px-8 py-3 rounded-xl font-bold hover:bg-blue-700 transition shadow-lg">سجل الآن</a>
                <a href="#gallery" class="bg-white/10 px-8 py-3 rounded-xl font-bold hover:bg-white/20 transition">مشاهدة المعرض</a>
            </div>
        </div>
    </section>

    <!-- الأجندة -->
    <section id="agenda" class="section-padding bg-white">
        <div class="container mx-auto px-6">
            <h2 class="text-3xl font-bold mb-12 text-center underline decoration-blue-500 underline-offset-8">أجندة المؤتمر</h2>
            <div class="grid md:grid-cols-2 gap-12 max-w-6xl mx-auto">
                <div class="space-y-6">
                    <h3 class="text-2xl font-bold text-blue-800 border-b-2 border-blue-100 pb-2"><i class="fas fa-calendar-day ml-2"></i> اليوم الأول</h3>
                    <div id="agenda-day1" class="space-y-4"></div>
                </div>
                <div class="space-y-6">
                    <h3 class="text-2xl font-bold text-indigo-800 border-b-2 border-indigo-100 pb-2"><i class="fas fa-calendar-check ml-2"></i> اليوم الثاني</h3>
                    <div id="agenda-day2" class="space-y-4"></div>
                </div>
            </div>
        </div>
    </section>

    <!-- نموذج التسجيل -->
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

    <!-- معرض الصور -->
    <section id="gallery" class="section-padding bg-white">
        <div class="container mx-auto px-6">
            <h2 class="text-3xl font-bold text-center mb-12">معرض الصور</h2>
            <div class="flex justify-center gap-8 mb-12 border-b">
                <button onclick="switchGallery('tech1')" id="tab-tech1" class="pb-4 px-4 transition tab-active">Civil Tech 1</button>
                <button onclick="switchGallery('tech2')" id="tab-tech2" class="pb-4 px-4 transition">Civil Tech 2 (الحالي)</button>
            </div>
            <!-- صور المؤتمر الأول (ثابتة) -->
            <div id="gallery-tech1" class="grid grid-cols-2 md:grid-cols-4 gap-4">
                <img src="https://images.unsplash.com/photo-1581094794329-c8112a89af12?q=80&w=400" class="rounded-xl h-48 w-full object-cover">
                <img src="https://images.unsplash.com/photo-1503387762-592dea58ef21?q=80&w=400" class="rounded-xl h-48 w-full object-cover">
                <img src="https://images.unsplash.com/photo-1541888946425-d81bb19240f5?q=80&w=400" class="rounded-xl h-48 w-full object-cover">
                <img src="https://images.unsplash.com/photo-1581094794329-c8112a89af12?q=80&w=400" class="rounded-xl h-48 w-full object-cover">
            </div>
            <!-- صور المؤتمر الثاني (سحابية) -->
            <div id="gallery-tech2" class="hidden grid grid-cols-2 md:grid-cols-4 gap-4"></div>
        </div>
    </section>

    <!-- لوحة تحكم المسؤول -->
    <section id="admin-section" class="section-padding bg-slate-100 border-t-4 border-red-500">
        <div class="container mx-auto px-6">
            <div id="admin-login" class="text-center max-w-md mx-auto">
                <h2 class="text-2xl font-bold mb-4 text-red-700">لوحة تحكم المسؤول</h2>
                <input type="password" id="adminPass" placeholder="كلمة المرور" class="w-full px-4 py-2 rounded border mb-4 outline-none text-center">
                <button onclick="checkAdmin()" class="bg-red-600 text-white px-10 py-2 rounded font-bold shadow-md">دخول</button>
            </div>

            <div id="admin-content" class="hidden space-y-12">
                <!-- إدارة الأجندة -->
                <div class="bg-white p-8 rounded-3xl shadow-sm border border-green-200">
                    <h3 class="text-2xl font-bold mb-6 text-green-800">إدارة الأجندة</h3>
                    <form id="agendaForm" class="grid md:grid-cols-4 gap-4">
                        <input type="text" id="agendaTitle" placeholder="الموضوع" required class="px-4 py-2 border rounded-lg">
                        <input type="text" id="agendaTime" placeholder="الوقت (09:00)" required class="px-4 py-2 border rounded-lg">
                        <select id="agendaDay" class="px-4 py-2 border rounded-lg">
                            <option value="1">اليوم الأول</option>
                            <option value="2">اليوم الثاني</option>
                        </select>
                        <button type="submit" id="agendaBtn" class="bg-green-600 text-white rounded-lg font-bold">إضافة الفقرة</button>
                    </form>
                </div>

                <!-- رفع الصور -->
                <div class="bg-white p-8 rounded-3xl shadow-sm border border-blue-200">
                    <h3 class="text-2xl font-bold mb-6 text-blue-800">رفع صور المؤتمر الثاني</h3>
                    <form id="uploadForm" class="space-y-4">
                        <div id="dropZone" class="upload-area p-8 text-center rounded-2xl bg-slate-50">
                            <input type="file" id="fileInput" accept="image/*" class="hidden">
                            <div id="uploadPrompt">إضغط هنا لاختيار صورة</div>
                            <img id="imgPreview" class="hidden max-h-48 mx-auto mt-4 rounded-xl shadow">
                        </div>
                        <input type="text" id="upCaption" placeholder="وصف الصورة" class="w-full px-4 py-2 border rounded-lg">
                        <button type="submit" id="upBtn" class="w-full bg-blue-700 text-white py-3 rounded-xl font-bold">نشر الصورة</button>
                    </form>
                </div>

                <!-- قائمة المسجلين -->
                <div class="bg-white p-8 rounded-3xl shadow-sm border">
                    <h3 class="text-2xl font-bold mb-6">قائمة المسجلين (<span id="totalCount">0</span>)</h3>
                    <div class="overflow-x-auto">
                        <table class="w-full text-right">
                            <thead class="bg-slate-50 border-b">
                                <tr>
                                    <th class="p-3">الاسم</th>
                                    <th class="p-3">الهاتف</th>
                                    <th class="p-3">المسار</th>
                                    <th class="p-3">التحكم</th>
                                </tr>
                            </thead>
                            <tbody id="registrantsTable"></tbody>
                        </table>
                    </div>
                </div>
                
                <div class="text-center">
                    <button onclick="logoutAdmin()" class="text-red-600 font-bold underline">خروج من لوحة التحكم</button>
                </div>
            </div>
        </div>
    </section>

    <footer class="bg-slate-900 text-white py-12 text-center">
        <p>© 2025 مؤتمر CIVILTCTH 2 - كلية الهندسة والتكنولوجيا</p>
    </footer>

    <!-- استيراد Firebase -->
    <script type="module">
        // ========================= إعدادات Firebase =========================
        // قم بإنشاء مشروع على https://console.firebase.google.com/
        // ثم استبدل الكائن أدناه ببيانات الإعداد الخاصة بك
        const firebaseConfig = {
            apiKey: "YOUR_API_KEY",
            authDomain: "YOUR_AUTH_DOMAIN",
            projectId: "YOUR_PROJECT_ID",
            storageBucket: "YOUR_STORAGE_BUCKET",
            messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
            appId: "YOUR_APP_ID"
        };

        // استيراد مكتبات Firebase
        import { initializeApp } from "https://www.gstatic.com/firebasejs/10.8.0/firebase-app.js";
        import { 
            getFirestore, collection, addDoc, onSnapshot, query, orderBy, deleteDoc, doc, serverTimestamp 
        } from "https://www.gstatic.com/firebasejs/10.8.0/firebase-firestore.js";

        // تهيئة Firebase
        const app = initializeApp(firebaseConfig);
        const db = getFirestore(app);

        // ========================= دوال مساعدة =========================
        // دالة لعرض رسالة خطأ في حال فشل الاتصال (اختياري)
        function showError(msg) {
            console.error(msg);
            alert("حدث خطأ في الاتصال بقاعدة البيانات: " + msg);
        }

        // ========================= الأجندة =========================
        // الاستماع للتغييرات في مجموعة agenda
        const agendaRef = collection(db, "agenda");
        const qAgenda = query(agendaRef, orderBy("time"));

        onSnapshot(qAgenda, (snapshot) => {
            const day1El = document.getElementById('agenda-day1');
            const day2El = document.getElementById('agenda-day2');
            day1El.innerHTML = '';
            day2El.innerHTML = '';

            snapshot.forEach((doc) => {
                const item = { id: doc.id, ...doc.data() };
                const div = document.createElement('div');
                div.className = "p-4 bg-white rounded-xl shadow-sm border-r-4 " + (item.day == "1" ? "border-blue-500" : "border-indigo-500");
                div.innerHTML = `<div><span class="text-sm font-bold">${item.time}</span><p class="font-bold text-slate-800">${item.title}</p></div>`;
                
                if (item.day == "1") day1El.appendChild(div);
                else day2El.appendChild(div);
            });

            if (day1El.children.length === 0) {
                day1El.innerHTML = '<p class="text-slate-400 italic">بانتظار إضافة الفقرات...</p>';
            }
            if (day2El.children.length === 0) {
                day2El.innerHTML = '<p class="text-slate-400 italic">بانتظار إضافة الفقرات...</p>';
            }
        }, (error) => showError(error.message));

        // إضافة فقرة جديدة (من لوحة التحكم)
        document.getElementById('agendaForm').addEventListener('submit', async (e) => {
            e.preventDefault();
            const title = document.getElementById('agendaTitle').value.trim();
            const time = document.getElementById('agendaTime').value.trim();
            const day = document.getElementById('agendaDay').value;

            if (!title || !time) return;

            try {
                await addDoc(agendaRef, {
                    title,
                    time,
                    day,
                    createdAt: serverTimestamp()
                });
                e.target.reset();
            } catch (error) {
                showError(error.message);
            }
        });

        // ========================= التسجيل =========================
        const registrantsRef = collection(db, "registrants");

        document.getElementById('regForm').addEventListener('submit', async (e) => {
            e.preventDefault();
            const name = document.getElementById('fullName').value.trim();
            const email = document.getElementById('email').value.trim();
            const phone = document.getElementById('phone').value.trim();
            const track = document.getElementById('track').value;

            if (!name || !email || !phone) return;

            try {
                await addDoc(registrantsRef, {
                    name,
                    email,
                    phone,
                    track,
                    createdAt: serverTimestamp()
                });

                const status = document.getElementById('regStatus');
                status.className = "mt-4 p-3 rounded-lg bg-green-100 text-green-700 block text-center";
                status.innerText = "تم تسجيلك بنجاح!";
                e.target.reset();

                setTimeout(() => {
                    status.className = "mt-4 hidden";
                }, 3000);
            } catch (error) {
                showError(error.message);
            }
        });

        // عرض المسجلين في لوحة التحكم
        const qRegistrants = query(registrantsRef, orderBy("createdAt", "desc"));
        onSnapshot(qRegistrants, (snapshot) => {
            const tbody = document.getElementById('registrantsTable');
            const totalSpan = document.getElementById('totalCount');
            tbody.innerHTML = '';
            let count = 0;

            snapshot.forEach((doc) => {
                count++;
                const r = { id: doc.id, ...doc.data() };
                const tr = document.createElement('tr');
                tr.className = "border-b text-sm";
                tr.innerHTML = `
                    <td class="p-3 font-bold">${r.name}</td>
                    <td class="p-3">${r.phone}</td>
                    <td class="p-3">${r.track}</td>
                    <td class="p-3">
                        <button class="text-red-500 delete-btn" data-id="${r.id}"><i class="fa-solid fa-trash"></i></button>
                    </td>
                `;
                tbody.appendChild(tr);
            });

            totalSpan.innerText = count;

            // إضافة وظيفة الحذف لكل زر
            document.querySelectorAll('.delete-btn').forEach(btn => {
                btn.addEventListener('click', async () => {
                    if (confirm('هل أنت متأكد من حذف هذا المسجل؟')) {
                        try {
                            await deleteDoc(doc(db, "registrants", btn.dataset.id));
                        } catch (error) {
                            showError(error.message);
                        }
                    }
                });
            });
        }, (error) => showError(error.message));

        // ========================= معرض الصور (المؤتمر الثاني) =========================
        const galleryRef = collection(db, "gallery_v2");
        const qGallery = query(galleryRef, orderBy("createdAt", "desc"));

        onSnapshot(qGallery, (snapshot) => {
            const container = document.getElementById('gallery-tech2');
            container.innerHTML = '';

            if (snapshot.empty) {
                container.innerHTML = '<p id="empty-msg" class="col-span-full text-center text-slate-400 py-10 italic">المسؤول لم يرفع صوراً بعد...</p>';
            } else {
                snapshot.forEach((doc) => {
                    const item = doc.data();
                    const div = document.createElement('div');
                    div.className = "bg-white p-1 rounded-xl border shadow-sm";
                    div.innerHTML = `<img src="${item.image}" class="rounded-lg h-40 w-full object-cover"><p class="text-[10px] text-center mt-1 truncate">${item.caption || ''}</p>`;
                    container.appendChild(div);
                });
            }
        }, (error) => showError(error.message));

        // رفع الصور (تحويل الصورة إلى Base64 وتخزينها في Firestore)
        // ملاحظة: يفضل استخدام Storage للتخزين الفعلي للصور، لكن للتبسيط سنستخدم Base64
        const fileInput = document.getElementById('fileInput');
        const dropZone = document.getElementById('dropZone');
        const imgPreview = document.getElementById('imgPreview');
        const uploadPrompt = document.getElementById('uploadPrompt');

        dropZone.addEventListener('click', () => fileInput.click());

        fileInput.addEventListener('change', function(e) {
            const file = e.target.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = (ev) => {
                    imgPreview.src = ev.target.result;
                    imgPreview.classList.remove('hidden');
                    uploadPrompt.classList.add('hidden');
                };
                reader.readAsDataURL(file);
            }
        });

        document.getElementById('uploadForm').addEventListener('submit', async (e) => {
            e.preventDefault();
            const caption = document.getElementById('upCaption').value.trim();
            const imgSrc = imgPreview.src;

            if (!imgSrc || imgSrc === window.location.href) {
                alert('الرجاء اختيار صورة أولاً');
                return;
            }

            try {
                await addDoc(galleryRef, {
                    image: imgSrc,
                    caption: caption || 'بدون وصف',
                    createdAt: serverTimestamp()
                });

                e.target.reset();
                imgPreview.classList.add('hidden');
                uploadPrompt.classList.remove('hidden');
                fileInput.value = '';
                alert('تم رفع الصورة بنجاح');
            } catch (error) {
                showError(error.message);
            }
        });

        // ========================= دوال عامة (لأزرار HTML) =========================
        window.switchGallery = function(type) {
            const tech1 = document.getElementById('gallery-tech1');
            const tech2 = document.getElementById('gallery-tech2');
            const tab1 = document.getElementById('tab-tech1');
            const tab2 = document.getElementById('tab-tech2');

            if (type === 'tech1') {
                tech1.classList.remove('hidden');
                tech2.classList.add('hidden');
                tab1.classList.add('tab-active');
                tab2.classList.remove('tab-active');
            } else {
                tech1.classList.add('hidden');
                tech2.classList.remove('hidden');
                tab1.classList.remove('tab-active');
                tab2.classList.add('tab-active');
            }
        };

        window.checkAdmin = function() {
            const pass = document.getElementById('adminPass').value;
            if (pass === '123456') {
                document.getElementById('admin-login').classList.add('hidden');
                document.getElementById('admin-content').classList.remove('hidden');
            } else {
                alert('كلمة المرور خاطئة!');
            }
        };

        window.logoutAdmin = function() {
            document.getElementById('admin-login').classList.remove('hidden');
            document.getElementById('admin-content').classList.add('hidden');
        };
    </script>
</body>
</html>
