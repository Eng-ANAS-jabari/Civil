<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CIVILTCTH 2 | المؤتمر الهندسي المتكامل</title>
    <!-- استيراد Tailwind CSS للتصميم العصري -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- استيراد الأيقونات -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <!-- استيراد الخطوط العربية -->
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;700&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Tajawal', sans-serif; scroll-behavior: smooth; }
        .hero-gradient { background: linear-gradient(135deg, #0f172a 0%, #1e3a8a 100%); }
        .glass { background: rgba(255, 255, 255, 0.9); backdrop-filter: blur(10px); }
        .upload-area { border: 2px dashed #cbd5e1; transition: all 0.3s; cursor: pointer; }
        .upload-area:hover { border-color: #3b82f6; background: #eff6ff; }
        .section-padding { padding-top: 5rem; padding-bottom: 5rem; }
        .tab-active { border-bottom: 4px solid #3b82f6; color: #1e40af; font-weight: bold; }
        .fade-in { animation: fadeIn 0.5s ease-in; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }
        .notification {
            position: fixed;
            top: 80px;
            left: 20px;
            background: #10b981;
            color: white;
            padding: 12px 24px;
            border-radius: 50px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.15);
            z-index: 1000;
            animation: slideIn 0.3s ease;
        }
        @keyframes slideIn {
            from { transform: translateX(100px); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }
        .online-users {
            position: fixed;
            bottom: 20px;
            left: 20px;
            background: white;
            padding: 8px 16px;
            border-radius: 50px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            font-size: 14px;
            z-index: 100;
        }
        .typing-indicator {
            background: #e5e7eb;
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 12px;
            display: inline-block;
            margin: 5px 0;
        }
    </style>
</head>
<body class="bg-slate-50 text-slate-900">

    <!-- إشعارات المزامنة -->
    <div id="syncNotification" class="notification hidden">
        <i class="fas fa-sync-alt ml-2 animate-spin"></i>
        <span id="syncMessage">جاري المزامنة...</span>
    </div>

    <!-- عدد المستخدمين المتصلين -->
    <div id="onlineUsers" class="online-users hidden">
        <i class="fas fa-users text-blue-600 ml-2"></i>
        <span id="onlineCount">0</span> مستخدم متصل
    </div>

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
                <a href="#live-feed" class="hover:text-green-600 transition">التغذية الحية</a>
                <a href="#admin-section" class="text-red-600 font-bold hover:underline">لوحة التحكم</a>
            </div>
        </div>
    </nav>

    <!-- الواجهة الرئيسية (Hero) -->
    <section class="hero-gradient min-h-[60vh] flex items-center pt-20 text-white relative text-center">
        <div class="container mx-auto px-6">
            <h1 class="text-5xl md:text-7xl font-extrabold mb-6 fade-in">CIVILTCTH 2</h1>
            <p class="text-2xl text-blue-300 mb-8 fade-in">مؤتمر الهندسة المدنية والتكنولوجيا الحديثة - الخليل</p>
            <div class="flex justify-center gap-4 fade-in">
                <a href="#register" class="bg-blue-600 px-8 py-3 rounded-xl font-bold hover:bg-blue-700 transition shadow-lg">سجل الآن</a>
                <a href="#gallery" class="bg-white/10 px-8 py-3 rounded-xl font-bold hover:bg-white/20 transition">مشاهدة المعرض</a>
            </div>
        </div>
    </section>

    <!-- تغذية حية للمؤتمر -->
    <section id="live-feed" class="section-padding bg-gradient-to-b from-blue-50 to-white">
        <div class="container mx-auto px-6">
            <h2 class="text-3xl font-bold mb-4 text-center">التغذية الحية للمؤتمر</h2>
            <p class="text-center text-slate-600 mb-8">آخر التحديثات والتفاعلات من الحضور</p>
            
            <div class="max-w-3xl mx-auto bg-white rounded-2xl shadow-lg overflow-hidden">
                <div class="bg-blue-600 text-white p-4 flex justify-between items-center">
                    <span><i class="fas fa-rss ml-2"></i> التحديثات المباشرة</span>
                    <span class="text-sm" id="lastUpdate">جاري التحديث...</span>
                </div>
                
                <div id="liveActivities" class="h-80 overflow-y-auto p-4 space-y-3">
                    <div class="text-center text-slate-400 py-10">
                        <i class="fas fa-sync-alt fa-spin text-3xl mb-2"></i>
                        <p>بانتظار النشاطات...</p>
                    </div>
                </div>
                
                <!-- نموذج إضافة تحديث حي (للمستخدمين) -->
                <div class="border-t p-4 bg-slate-50">
                    <form id="liveForm" class="flex gap-2">
                        <input type="text" id="liveMessage" placeholder="شارك بتعليق أو تحديث..." class="flex-1 px-4 py-2 rounded-xl border focus:ring-2 focus:ring-blue-500 outline-none">
                        <button type="submit" class="bg-blue-600 text-white px-6 py-2 rounded-xl hover:bg-blue-700 transition">
                            <i class="fas fa-paper-plane"></i>
                        </button>
                    </form>
                    <div id="typingIndicator" class="typing-indicator hidden">
                        <span class="text-slate-600">شخص يكتب...</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- قسم الأجندة الديناميكي -->
    <section id="agenda" class="section-padding bg-white">
        <div class="container mx-auto px-6">
            <h2 class="text-3xl font-bold mb-12 text-center underline decoration-blue-500 underline-offset-8">أجندة المؤتمر</h2>
            
            <!-- شريط تقدم الأجندة -->
            <div class="max-w-4xl mx-auto mb-8 bg-slate-100 rounded-full h-2.5">
                <div id="agendaProgress" class="bg-blue-600 h-2.5 rounded-full transition-all duration-500" style="width: 0%"></div>
            </div>
            
            <div class="grid md:grid-cols-2 gap-12 max-w-6xl mx-auto">
                <!-- اليوم الأول -->
                <div class="space-y-6">
                    <h3 class="text-2xl font-bold text-blue-800 border-b-2 border-blue-100 pb-2">
                        <i class="fas fa-calendar-day ml-2"></i> اليوم الأول
                        <span class="text-sm bg-blue-100 text-blue-800 px-3 py-1 rounded-full mr-2" id="day1Count">0</span>
                    </h3>
                    <div id="agenda-day1" class="space-y-4">
                        <p class="text-slate-400 italic">بانتظار إضافة الفقرات...</p>
                    </div>
                </div>
                <!-- اليوم الثاني -->
                <div class="space-y-6">
                    <h3 class="text-2xl font-bold text-indigo-800 border-b-2 border-indigo-100 pb-2">
                        <i class="fas fa-calendar-check ml-2"></i> اليوم الثاني
                        <span class="text-sm bg-indigo-100 text-indigo-800 px-3 py-1 rounded-full mr-2" id="day2Count">0</span>
                    </h3>
                    <div id="agenda-day2" class="space-y-4">
                        <p class="text-slate-400 italic">بانتظار إضافة الفقرات...</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- نموذج التسجيل -->
    <section id="register" class="section-padding bg-blue-50">
        <div class="container mx-auto px-6 max-w-4xl">
            <div class="bg-white p-8 md:p-12 rounded-[2.5rem] shadow-xl border border-blue-100">
                <h2 class="text-3xl font-bold text-center mb-8">نموذج التسجيل</h2>
                
                <!-- عداد المسجلين المباشر -->
                <div class="flex justify-center mb-6">
                    <div class="bg-green-100 text-green-800 px-6 py-2 rounded-full">
                        <i class="fas fa-users ml-2"></i>
                        عدد المسجلين: <span id="liveRegistrantCount">0</span>
                    </div>
                </div>
                
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
            
            <!-- صور المؤتمر الأول (ثابتة كمثال) -->
            <div id="gallery-tech1" class="grid grid-cols-2 md:grid-cols-4 gap-4">
                <img src="https://images.unsplash.com/photo-1581094794329-c8112a89af12?q=80&w=400" class="rounded-xl h-48 w-full object-cover">
                <img src="https://images.unsplash.com/photo-1503387762-592dea58ef21?q=80&w=400" class="rounded-xl h-48 w-full object-cover">
            </div>
            
            <!-- صور المؤتمر الثاني (مرفوعة من المسؤول) -->
            <div id="gallery-tech2" class="hidden grid grid-cols-2 md:grid-cols-4 gap-4">
                <p id="empty-msg" class="col-span-full text-center text-slate-400 py-10 italic">المسؤول لم يرفع صوراً بعد...</p>
            </div>
            
            <!-- مؤشر التمرير السريع للصور -->
            <div id="galleryScroll" class="hidden fixed bottom-4 right-4 bg-blue-600 text-white px-4 py-2 rounded-full shadow-lg">
                <i class="fas fa-arrow-right ml-2"></i> صور جديدة
            </div>
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
                <!-- مؤشرات حية -->
                <div class="grid grid-cols-3 gap-4">
                    <div class="bg-white p-4 rounded-xl shadow-sm border border-blue-200 text-center">
                        <div class="text-3xl font-bold text-blue-600" id="adminLiveCount">0</div>
                        <div class="text-sm">مستخدم متصل</div>
                    </div>
                    <div class="bg-white p-4 rounded-xl shadow-sm border border-green-200 text-center">
                        <div class="text-3xl font-bold text-green-600" id="adminRegCount">0</div>
                        <div class="text-sm">تسجيل جديد</div>
                    </div>
                    <div class="bg-white p-4 rounded-xl shadow-sm border border-purple-200 text-center">
                        <div class="text-3xl font-bold text-purple-600" id="adminPhotoCount">0</div>
                        <div class="text-sm">صورة مرفوعة</div>
                    </div>
                </div>

                <!-- 1. إدارة الأجندة -->
                <div class="bg-white p-8 rounded-3xl shadow-sm border border-green-200">
                    <h3 class="text-2xl font-bold mb-6 text-green-800">إدارة الأجندة</h3>
                    <form id="agendaForm" class="grid md:grid-cols-4 gap-4">
                        <input type="text" id="agendaTitle" placeholder="الموضوع" required class="px-4 py-2 border rounded-lg">
                        <input type="time" id="agendaTime" placeholder="الوقت" required class="px-4 py-2 border rounded-lg">
                        <select id="agendaDay" class="px-4 py-2 border rounded-lg">
                            <option value="1">اليوم الأول</option>
                            <option value="2">اليوم الثاني</option>
                        </select>
                        <button type="submit" id="agendaBtn" class="bg-green-600 text-white rounded-lg font-bold">إضافة الفقرة</button>
                    </form>
                    <div id="agendaList" class="mt-6 space-y-2 max-h-60 overflow-y-auto"></div>
                </div>

                <!-- 2. رفع الصور -->
                <div class="bg-white p-8 rounded-3xl shadow-sm border border-blue-200">
                    <h3 class="text-2xl font-bold mb-6 text-blue-800">رفع صور المؤتمر الثاني</h3>
                    <form id="uploadForm" class="space-y-4">
                        <div id="dropZone" class="upload-area p-8 text-center rounded-2xl bg-slate-50">
                            <input type="file" id="fileInput" accept="image/*" class="hidden" multiple>
                            <div id="uploadPrompt"><i class="fas fa-cloud-upload-alt text-3xl text-blue-500 mb-2"></i><br>إضغط هنا لاختيار صورة</div>
                            <img id="imgPreview" class="hidden max-h-48 mx-auto mt-4 rounded-xl shadow">
                        </div>
                        <input type="text" id="upCaption" placeholder="وصف الصورة" class="w-full px-4 py-2 border rounded-lg">
                        <button type="submit" id="upBtn" class="w-full bg-blue-700 text-white py-3 rounded-xl font-bold">نشر الصورة</button>
                    </form>
                </div>

                <!-- 3. إحصائيات المسجلين -->
                <div class="bg-white p-8 rounded-3xl shadow-sm border">
                    <h3 class="text-2xl font-bold mb-6">قائمة المسجلين (<span id="totalCount">0</span>)</h3>
                    <div class="overflow-x-auto">
                        <table class="w-full text-right">
                            <thead class="bg-slate-50 border-b">
                                <tr>
                                    <th class="p-3">الاسم</th>
                                    <th class="p-3">البريد الإلكتروني</th>
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

    <!-- إعدادات Firebase -->
    <script>
        window.__firebase_config = {
            apiKey: "AIzaSyB_1PxYZ4zF8q8Q4zF8q8Q4zF8q8Q4zF8q8", // استبدل بمفاتيحك
            authDomain: "your-project.firebaseapp.com",
            projectId: "your-project",
            storageBucket: "your-project.appspot.com",
            messagingSenderId: "123456789",
            appId: "1:123456789:web:abc123"
        };
        window.__app_id = 'civiltcth2-main-v1';
    </script>

    <!-- الجزء البرمجي مع المزامنة الكاملة -->
    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
        import { getFirestore, collection, addDoc, onSnapshot, query, orderBy, deleteDoc, doc, serverTimestamp, limit, where, updateDoc, increment, getDocs } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";
        import { getAuth, signInAnonymously, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";
        import { getDatabase, ref, onValue, set, push, serverTimestamp as rtServerTimestamp, onDisconnect } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-database.js";

        // إعدادات Firebase
        const firebaseConfig = window.__firebase_config;
        const app = initializeApp(firebaseConfig);
        const db = getFirestore(app);
        const rtdb = getDatabase(app);
        const auth = getAuth(app);
        const appId = window.__app_id;

        // متغيرات عامة
        let currentUser = null;
        let userId = null;
        let typingTimeout = null;
        let lastActivityTime = Date.now();

        // دوال المساعدة
        function showNotification(message, isSuccess = true) {
            const notification = document.getElementById('syncNotification');
            const messageEl = document.getElementById('syncMessage');
            
            if(notification && messageEl) {
                messageEl.innerText = message;
                notification.classList.remove('hidden');
                notification.style.background = isSuccess ? '#10b981' : '#ef4444';
                
                setTimeout(() => {
                    notification.classList.add('hidden');
                }, 3000);
            }
        }

        function showSyncStatus(message) {
            showNotification(message, true);
        }

        // المصادقة الصامتة
        signInAnonymously(auth).catch(console.error);
        
        onAuthStateChanged(auth, async (user) => {
            if(user) {
                currentUser = user;
                userId = user.uid;
                
                // تسجيل المستخدم في Realtime Database للمستخدمين المتصلين
                const userStatusRef = ref(rtdb, 'status/' + userId);
                const connectedRef = ref(rtdb, '.info/connected');
                
                onValue(connectedRef, (snap) => {
                    if (snap.val() === true) {
                        // المستخدم متصل
                        const con = push(ref(rtdb, 'connections'));
                        onDisconnect(con).remove();
                        
                        // تحديث حالة المستخدم
                        set(userStatusRef, {
                            online: true,
                            lastSeen: Date.now(),
                            lastActivity: Date.now()
                        });
                        
                        onDisconnect(userStatusRef).set({
                            online: false,
                            lastSeen: Date.now()
                        });
                    }
                });
                
                // مراقبة عدد المستخدمين المتصلين
                const onlineCountRef = ref(rtdb, 'status');
                onValue(onlineCountRef, (snap) => {
                    let online = 0;
                    snap.forEach(child => {
                        if(child.val().online === true) online++;
                    });
                    
                    document.getElementById('onlineCount').innerText = online;
                    document.getElementById('adminLiveCount').innerText = online;
                    document.getElementById('onlineUsers').classList.remove('hidden');
                });
                
                // بدء المزامنة
                syncAgenda();
                syncGallery();
                syncAdminStats();
                syncLiveActivities();
                startTypingDetection();
                updateLastActivity();
            }
        });

        // تحديث آخر نشاط للمستخدم
        function updateLastActivity() {
            if(userId) {
                const userStatusRef = ref(rtdb, 'status/' + userId);
                set(userStatusRef, {
                    online: true,
                    lastSeen: Date.now(),
                    lastActivity: Date.now()
                });
            }
        }

        // مراقبة الكتابة
        function startTypingDetection() {
            const input = document.getElementById('liveMessage');
            if(input) {
                input.addEventListener('input', () => {
                    if(userId) {
                        const typingRef = ref(rtdb, 'typing/' + userId);
                        set(typingRef, {
                            isTyping: true,
                            timestamp: Date.now()
                        });
                        
                        clearTimeout(typingTimeout);
                        typingTimeout = setTimeout(() => {
                            set(typingRef, { isTyping: false });
                        }, 2000);
                    }
                });
            }
            
            // مراقبة من يكتب
            const typingRef = ref(rtdb, 'typing');
            onValue(typingRef, (snap) => {
                let typingCount = 0;
                snap.forEach(child => {
                    if(child.val().isTyping === true && child.key !== userId) {
                        typingCount++;
                    }
                });
                
                const indicator = document.getElementById('typingIndicator');
                if(indicator) {
                    if(typingCount > 0) {
                        indicator.classList.remove('hidden');
                        indicator.innerHTML = typingCount === 1 ? 
                            '<span class="text-slate-600">شخص يكتب...</span>' : 
                            `<span class="text-slate-600">${typingCount} أشخاص يكتبون...</span>`;
                    } else {
                        indicator.classList.add('hidden');
                    }
                }
            });
        }

        // 1. التغذية الحية
        async function syncLiveActivities() {
            const q = query(
                collection(db, 'artifacts', appId, 'public', 'data', 'activities'),
                orderBy('createdAt', 'desc'),
                limit(50)
            );
            
            onSnapshot(q, (snap) => {
                const container = document.getElementById('liveActivities');
                const lastUpdate = document.getElementById('lastUpdate');
                
                if(!container) return;
                
                // تحديث وقت آخر تحديث
                if(lastUpdate) {
                    lastUpdate.innerText = new Date().toLocaleTimeString('ar-EG');
                }
                
                // عرض النشاطات
                if(snap.empty) {
                    container.innerHTML = '<div class="text-center text-slate-400 py-10"><i class="fas fa-comments text-3xl mb-2"></i><p>لا توجد نشاطات بعد...</p></div>';
                    return;
                }
                
                container.innerHTML = '';
                snap.forEach(doc => {
                    const activity = doc.data();
                    const div = document.createElement('div');
                    div.className = "bg-slate-50 p-3 rounded-xl fade-in border-r-4 border-blue-400";
                    
                    const time = activity.createdAt?.toDate ? 
                        activity.createdAt.toDate().toLocaleTimeString('ar-EG') : 
                        'الآن';
                    
                    div.innerHTML = `
                        <div class="flex justify-between items-start">
                            <div>
                                <span class="font-bold text-blue-800">${activity.user || 'مستخدم'}</span>
                                <p class="text-slate-700">${activity.message}</p>
                            </div>
                            <span class="text-xs text-slate-500">${time}</span>
                        </div>
                    `;
                    
                    container.appendChild(div);
                });
                
                // تمرير تلقائي لآخر تحديث
                container.scrollTop = 0;
            });
        }

        // إضافة نشاط حي
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
                showSyncStatus('تم نشر التحديث');
                
                // إيقاف مؤشر الكتابة
                if(userId) {
                    const typingRef = ref(rtdb, 'typing/' + userId);
                    set(typingRef, { isTyping: false });
                }
                
            } catch(e) {
                console.error(e);
                showNotification('فشل في النشر', false);
            }
        });

        // 2. إدارة الأجندة مع المزامنة
        document.getElementById('agendaForm')?.addEventListener('submit', async (e) => {
            e.preventDefault();
            const btn = document.getElementById('agendaBtn');
            btn.disabled = true;
            
            try {
                const docRef = await addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'agenda'), {
                    title: document.getElementById('agendaTitle').value,
                    time: document.getElementById('agendaTime').value,
                    day: document.getElementById('agendaDay').value,
                    createdAt: serverTimestamp()
                });
                
                // إضافة نشاط في التغذية الحية
                await addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'activities'), {
                    message: `تم إضافة فقرة جديدة: ${document.getElementById('agendaTitle').value}`,
                    user: 'المسؤول',
                    userId: 'admin',
                    createdAt: serverTimestamp()
                });
                
                e.target.reset();
                showSyncStatus('تم إضافة الفقرة بنجاح');
            } catch(e) { 
                console.error(e);
                showNotification('حدث خطأ في الإضافة', false);
            }
            btn.disabled = false;
        });

        function syncAgenda() {
            const q = query(collection(db, 'artifacts', appId, 'public', 'data', 'agenda'), orderBy('time'));
            
            onSnapshot(q, (snap) => {
                const day1 = document.getElementById('agenda-day1');
                const day2 = document.getElementById('agenda-day2');
                const agendaList = document.getElementById('agendaList');
                const day1Count = document.getElementById('day1Count');
                const day2Count = document.getElementById('day2Count');
                
                let count1 = 0, count2 = 0;
                
                if(day1 && day2) {
                    day1.innerHTML = ''; 
                    day2.innerHTML = '';
                }
                if(agendaList) agendaList.innerHTML = '';

                snap.forEach(doc => {
                    const item = {id: doc.id, ...doc.data()};
                    
                    if(item.day == "1") count1++;
                    else count2++;
                    
                    // عرض في الصفحة الرئيسية
                    if(day1 && day2) {
                        const div = document.createElement('div');
                        div.className = "p-4 bg-white rounded-xl shadow-sm border-r-4 fade-in " + (item.day == "1" ? "border-blue-500" : "border-indigo-500");
                        div.innerHTML = `<div><span class="text-sm font-bold text-slate-500">${item.time}</span><p class="font-bold text-slate-800">${item.title}</p></div>`;
                        
                        if(item.day == "1") day1.appendChild(div);
                        else day2.appendChild(div);
                    }
                    
                    // عرض في لوحة التحكم
                    if(agendaList) {
                        const div = document.createElement('div');
                        div.className = "flex justify-between items-center p-2 bg-slate-50 rounded hover:bg-slate-100 transition";
                        div.innerHTML = `
                            <span><span class="font-bold">${item.time}</span> - ${item.title} (اليوم ${item.day == "1" ? 'الأول' : 'الثاني'})</span>
                            <button onclick="deleteAgendaItem('${item.id}')" class="text-red-500 hover:text-red-700"><i class="fas fa-trash"></i></button>
                        `;
                        agendaList.appendChild(div);
                    }
                });
                
                // تحديث العدادات
                if(day1Count) day1Count.innerText = count1;
                if(day2Count) day2Count.innerText = count2;
                
                // تحديث شريط التقدم
                updateAgendaProgress(count1 + count2);
            });
        }

        // تحديث شريط تقدم الأجندة
        function updateAgendaProgress(total) {
            const now = new Date();
            const currentHour = now.getHours();
            const currentMinute = now.getMinutes();
            const currentTime = `${currentHour.toString().padStart(2,'0')}:${currentMinute.toString().padStart(2,'0')}`;
            
            // حساب الفقرات التي مضى وقتها
            let passed = 0;
            const items = document.querySelectorAll('#agenda-day1 .border-r-4, #agenda-day2 .border-r-4');
            items.forEach(item => {
                const timeSpan = item.querySelector('span');
                if(timeSpan) {
                    const itemTime = timeSpan.innerText;
                    if(itemTime < currentTime) passed++;
                }
            });
            
            const progress = total > 0 ? (passed / total) * 100 : 0;
            const progressBar = document.getElementById('agendaProgress');
            if(progressBar) {
                progressBar.style.width = `${progress}%`;
            }
        }

        // 3. معرض الصور مع مزامنة
        window.switchGallery = (type) => {
            document.getElementById('gallery-tech1').classList.toggle('hidden', type !== 'tech1');
            document.getElementById('gallery-tech2').classList.toggle('hidden', type !== 'tech2');
            document.getElementById('tab-tech1').classList.toggle('tab-active', type === 'tech1');
            document.getElementById('tab-tech2').classList.toggle('tab-active', type === 'tech2');
        };

        const fileInput = document.getElementById('fileInput');
        document.getElementById('dropZone')?.addEventListener('click', () => fileInput.click());
        
        fileInput?.addEventListener('change', (e) => {
            const files = e.target.files;
            if(files && files[0]) {
                const reader = new FileReader();
                reader.onload = (ev) => {
                    document.getElementById('imgPreview').src = ev.target.result;
                    document.getElementById('imgPreview').classList.remove('hidden');
                    document.getElementById('uploadPrompt').innerHTML = '<i class="fas fa-check-circle text-green-500 text-3xl"></i><br>تم اختيار الصورة';
                };
                reader.readAsDataURL(files[0]);
            }
        });

        document.getElementById('uploadForm')?.addEventListener('submit', async (e) => {
            e.preventDefault();
            const img = document.getElementById('imgPreview').src;
            if(!img || img === '') return alert("اختر صورة أولاً");
            
            try {
                await addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'gallery_v2'), {
                    image: img,
                    caption: document.getElementById('upCaption').value,
                    createdAt: serverTimestamp()
                });
                
                // إضافة نشاط في التغذية الحية
                await addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'activities'), {
                    message: `تم إضافة صورة جديدة: ${document.getElementById('upCaption').value || 'بدون وصف'}`,
                    user: 'المسؤول',
                    userId: 'admin',
                    createdAt: serverTimestamp()
                });
                
                e.target.reset();
                document.getElementById('imgPreview').classList.add('hidden');
                document.getElementById('uploadPrompt').innerHTML = '<i class="fas fa-cloud-upload-alt text-3xl text-blue-500 mb-2"></i><br>إضغط هنا لاختيار صورة';
                
                showSyncStatus('تم رفع الصورة بنجاح');
            } catch(e) {
                console.error(e);
                showNotification('حدث خطأ في رفع الصورة', false);
            }
        });

        function syncGallery() {
            const q = query(collection(db, 'artifacts', appId, 'public', 'data', 'gallery_v2'), orderBy('createdAt', 'desc'));
            
            onSnapshot(q, (snap) => {
                const grid = document.getElementById('gallery-tech2');
                const empty = document.getElementById('empty-msg');
                const photoCount = document.getElementById('adminPhotoCount');
                
                if(!grid || !empty) return;
                
                const docs = snap.docs.map(d => ({id: d.id, ...d.data()}));
                
                if(photoCount) photoCount.innerText = docs.length;
                
                if(docs.length > 0) {
                    empty.classList.add('hidden');
                    grid.innerHTML = '';
                    docs.forEach(p => {
                        const div = document.createElement('div');
                        div.className = "bg-white p-2 rounded-xl border shadow-sm fade-in hover:shadow-lg transition";
                        div.innerHTML = `<img src="${p.image}" class="rounded-lg h-40 w-full object-cover mb-1" onclick="openImage('${p.image}')"><p class="text-xs text-center truncate">${p.caption || ''}</p>`;
                        grid.appendChild(div);
                    });
                    
                    // إظهار إشعار بالصور الجديدة
                    const scrollIndicator = document.getElementById('galleryScroll');
                    if(scrollIndicator) {
                        scrollIndicator.classList.remove('hidden');
                        setTimeout(() => scrollIndicator.classList.add('hidden'), 3000);
                    }
                } else {
                    empty.classList.remove('hidden');
                }
            });
        }

        // فتح الصورة في نافذة جديدة
        window.openImage = (src) => {
            window.open(src, '_blank');
        };

        // 4. إدارة التسجيل مع عداد مباشر
        document.getElementById('regForm')?.addEventListener('submit', async (e) => {
            e.preventDefault();
            const btn = document.getElementById('regBtn');
            btn.disabled = true;
            
            try {
                await addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'registrants'), {
                    name: document.getElementById('fullName').value,
                    email: document.getElementById('email').value,
                    phone: document.getElementById('phone').value,
                    track: document.getElementById('track').value,
                    createdAt: serverTimestamp()
                });
                
                // إضافة نشاط في التغذية الحية
                await addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'activities'), {
                    message: `تسجيل جديد: ${document.getElementById('fullName').value}`,
                    user: 'نظام التسجيل',
                    userId: 'system',
                    createdAt: serverTimestamp()
                });
                
                e.target.reset();
                showNotification('تم تسجيلك بنجاح!', true);
            } catch(e) { 
                console.error(e);
                showNotification('حدث خطأ في التسجيل', false);
            }
            btn.disabled = false;
        });

        function syncAdminStats() {
            const q = query(collection(db, 'artifacts', appId, 'public', 'data', 'registrants'), orderBy('createdAt', 'desc'));
            
            onSnapshot(q, (snap) => {
                const list = snap.docs.map(d => ({id: d.id, ...d.data()}));
                document.getElementById('totalCount').innerText = list.length;
                document.getElementById('liveRegistrantCount').innerText = list.length;
                document.getElementById('adminRegCount').innerText = list.length;
                
                const table = document.getElementById('registrantsTable');
                if(!table) return;
                
                table.innerHTML = '';
                list.forEach(r => {
                    const tr = document.createElement('tr');
                    tr.className = "border-b text-sm hover:bg-slate-50 transition";
                    
                    const time = r.createdAt?.toDate ? 
                        r.createdAt.toDate().toLocaleString('ar-EG') : 
                        '';
                    
                    tr.innerHTML = `
                        <td class="p-3 font-bold">${r.name || ''}</td>
                        <td class="p-3">${r.email || ''}</td>
                        <td class="p-3">${r.phone || ''}</td>
                        <td class="p-3">${r.track || ''}</td>
                        <td class="p-3">
                            <button class="text-red-500 delete-btn hover:text-red-700" data-id="${r.id}">
                                <i class="fas fa-trash"></i>
                            </button>
                        </td>
                    `;
                    table.appendChild(tr);
                });
                
                // إضافة وظيفة الحذف للمسؤول
                document.querySelectorAll('.delete-btn').forEach(btn => {
                    btn.addEventListener('click', async () => {
                        if(confirm("هل أنت متأكد من حذف هذا التسجيل؟")) {
                            try {
                                await deleteDoc(doc(db, 'artifacts', appId, 'public', 'data', 'registrants', btn.dataset.id));
                                
                                // إضافة نشاط حذف
                                await addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'activities'), {
                                    message: `تم حذف تسجيل`,
                                    user: 'المسؤول',
                                    userId: 'admin',
                                    createdAt: serverTimestamp()
                                });
                                
                                showSyncStatus('تم الحذف بنجاح');
                            } catch(e) {
                                console.error(e);
                                showNotification('حدث خطأ في الحذف', false);
                            }
                        }
                    });
                });
            });
        }

        // حذف عنصر من الأجندة
        window.deleteAgendaItem = async (id) => {
            if(confirm("هل أنت متأكد من حذف هذه الفقرة؟")) {
                try {
                    await deleteDoc(doc(db, 'artifacts', appId, 'public', 'data', 'agenda', id));
                    
                    // إضافة نشاط حذف
                    await addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'activities'), {
                        message: `تم حذف فقرة من الأجندة`,
                        user: 'المسؤول',
                        userId: 'admin',
                        createdAt: serverTimestamp()
                    });
                    
                    showSyncStatus('تم الحذف بنجاح');
                } catch(e) {
                    console.error(e);
                    showNotification('حدث خطأ في الحذف', false);
                }
            }
        };

        // تسجيل الدخول للمسؤول
        window.checkAdmin = () => {
            const password = document.getElementById('adminPass').value;
            if(password === "123456") {
                document.getElementById('admin-login').classList.add('hidden');
                document.getElementById('admin-content').classList.remove('hidden');
                
                // تسجيل دخول المسؤول في النشاطات
                addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'activities'), {
                    message: `دخل المسؤول إلى لوحة التحكم`,
                    user: 'نظام',
                    userId: 'system',
                    createdAt: serverTimestamp()
                }).catch(console.error);
                
            } else {
                alert("كلمة المرور خاطئة!");
            }
        };
        
        window.logoutAdmin = () => {
            document.getElementById('admin-login').classList.remove('hidden');
            document.getElementById('admin-content').classList.add('hidden');
            document.getElementById('adminPass').value = '';
            
            // تسجيل خروج المسؤول
            addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'activities'), {
                message: `خرج المسؤول من لوحة التحكم`,
                user: 'نظام',
                userId: 'system',
                createdAt: serverTimestamp()
            }).catch(console.error);
        };

        // تحديث دوري للنشاط
        setInterval(updateLastActivity, 30000); // كل 30 ثانية
        setInterval(() => updateAgendaProgress(), 60000); // كل دقيقة

        // مراقبة التغييرات في Firestore
        const collections = ['agenda', 'gallery_v2', 'registrants', 'activities'];
        collections.forEach(col => {
            const q = query(collection(db, 'artifacts', appId, 'public', 'data', col), limit(1));
            onSnapshot(q, () => {
                // مجرد تحديث للإشارة إلى وجود تغيير
                updateLastActivity();
            });
        });

    </script>
</body>
</html>
