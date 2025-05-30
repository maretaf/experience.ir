<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>experience.ir - پلتفرم اشتراک تجربه و کار داوطلبانه</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        body {
            font-family: 'Vazirmatn', sans-serif;
        }
        @import url('https://cdn.jsdelivr.net/gh/rastikerdar/vazirmatn@v33.003/Vazirmatn-font-face.css');
        .modal {
            display: none; position: fixed; z-index: 100;
            left: 0; top: 0; width: 100%; height: 100%;
            overflow: auto; background-color: rgba(0,0,0,0.6);
        }
        .modal-content {
            background-color: #fefefe; margin: 8% auto; padding: 25px;
            border: 1px solid #888; width: 90%; max-width: 650px;
            border-radius: 0.75rem; box-shadow: 0 5px 15px rgba(0,0,0,0.3);
        }
        .close-button {
            color: #aaa; float: left; font-size: 30px; font-weight: bold;
        }
        .close-button:hover, .close-button:focus {
            color: black; text-decoration: none; cursor: pointer;
        }
        .hero-bg {
            background-image: url('https://placehold.co/1200x600/81e6d9/2c7a7b?text=ماجراجویی+در+تجربه‌ها'); /* Teal background */
            background-size: cover;
            background-position: center;
        }
        .profile-header-bg {
            background-size: cover;
            background-position: center;
            height: 200px;
        }
        .cta-button {
            transition: all 0.3s ease;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }
        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 12px rgba(0,0,0,0.15);
        }
        .spinner {
            border: 4px solid rgba(0, 0, 0, 0.1);
            width: 24px;
            height: 24px;
            border-radius: 50%;
            border-left-color: #09f;
            animation: spin 1s ease infinite;
            display: inline-block;
            margin-right: 8px;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        .ai-feature-button {
            background-color: #f0abfc; 
            color: #5b21b6; 
            border: 1px solid #d8b4fe;
        }
        .ai-feature-button:hover {
            background-color: #e9d5ff;
        }
        .site-section-card {
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .site-section-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }
    </style>
</head>
<body class="bg-gray-50 text-gray-800">

    <nav class="bg-gradient-to-r from-teal-500 to-cyan-600 p-4 shadow-lg sticky top-0 z-50">
        <div class="container mx-auto flex justify-between items-center">
            <a href="#" id="platform-logo-link" class="text-3xl font-bold text-white tracking-tight">تجربه‌<span class="text-yellow-300">.</span>آی‌آر</a>
            <div id="nav-visitor-links" class="hidden space-x-3 space-x-reverse">
                 <button id="nav-visitor-experience-center" class="text-white hover:text-yellow-300 px-3 py-2 rounded-md text-sm font-medium"><i class="fas fa-search-location mr-1"></i> کاوش تجربه‌ها</button>
                 <button id="nav-visitor-blog" class="text-white hover:text-yellow-300 px-3 py-2 rounded-md text-sm font-medium"><i class="fas fa-newspaper mr-1"></i> وبلاگ</button>
                 <button id="nav-visitor-contact" class="text-white hover:text-yellow-300 px-3 py-2 rounded-md text-sm font-medium"><i class="fas fa-address-book mr-1"></i> تماس با ما</button>
            </div>
            <div id="nav-user-actions" class="space-x-3 space-x-reverse">
                <button id="nav-experience-center" class="text-white hover:text-yellow-300 px-3 py-2 rounded-md text-sm font-medium hidden"><i class="fas fa-compass mr-1"></i> مرکز تجربه</button>
                <button id="nav-profile" class="text-white hover:text-yellow-300 px-3 py-2 rounded-md text-sm font-medium hidden"><i class="fas fa-user-circle mr-1"></i> پروفایل</button>
                <button id="nav-settings" class="text-white hover:text-yellow-300 px-3 py-2 rounded-md text-sm font-medium hidden"><i class="fas fa-cog mr-1"></i> تنظیمات</button>
                <button id="user-role-display" class="text-white px-3 py-2 rounded-md text-sm"></button>
                <button id="logout-button" class="text-white hover:text-red-300 px-3 py-2 rounded-md text-sm font-medium hidden"><i class="fas fa-sign-out-alt mr-1"></i> خروج</button>
            </div>
        </div>
    </nav>

    <div id="app" class="container mx-auto p-4 md:p-6 min-h-[calc(100vh-180px)]">

        <div id="landingView">
            <section class="hero-bg text-white py-20 md:py-32 rounded-lg shadow-xl">
                <div class="container mx-auto text-center bg-black bg-opacity-60 p-8 rounded-md">
                    <h2 class="text-4xl md:text-5xl font-extrabold mb-6 leading-tight">به <span class="text-yellow-300">experience.ir</span> خوش آمدید!</h2>
                    <p class="text-lg md:text-xl mb-8 max-w-2xl mx-auto">
                        ما باور داریم که ارزشمندترین دارایی‌ها، تجربه‌هایی هستند که کسب می‌کنیم و داستان‌هایی که برای گفتن داریم.
                        experience.ir پلی است میان شما و دنیاهای جدید؛ جایی برای یادگیری، خدمت و رشد.
                    </p>
                </div>
            </section>

            <section class="py-12 md:py-16 text-center">
                <h3 class="text-3xl font-bold mb-4 text-cyan-700">چشم‌انداز experience.ir</h3>
                <p class="text-lg text-gray-700 max-w-3xl mx-auto mb-10 leading-relaxed">
                    ما در experience.ir به دنبال ساختن جامعه‌ای جهانی از افراد کنجکاو، ماجراجو و مهربان هستیم... (متن کامل چشم‌انداز)
                </p>
            </section>

            <section id="siteSectionsPreview" class="py-12 md:py-16 bg-gray-100 rounded-lg shadow-inner">
                <h3 class="text-3xl font-bold mb-12 text-center text-teal-700">بخش‌های مختلف experience.ir را کشف کنید</h3>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-8 px-4 md:px-0">
                    <div id="preview-experience-center" class="site-section-card bg-white p-6 rounded-xl shadow-lg text-center cursor-pointer">
                        <img src="https://placehold.co/600x400/38b2ac/ffffff?text=مرکز+تجربه" alt="مرکز تجربه" class="w-full h-48 object-cover rounded-md mb-4">
                        <i class="fas fa-compass text-4xl text-teal-500 mb-3"></i>
                        <h4 class="text-xl font-semibold text-teal-600 mb-2">مرکز تجربه</h4>
                        <p class="text-sm text-gray-600">کاوش در میان صدها تجربه ناب و درخواست برای شرکت در آن‌ها.</p>
                    </div>
                    <div id="preview-blog" class="site-section-card bg-white p-6 rounded-xl shadow-lg text-center cursor-pointer">
                        <img src="https://placehold.co/600x400/667eea/ffffff?text=وبلاگ+تجربه‌ها" alt="وبلاگ تجربه‌ها" class="w-full h-48 object-cover rounded-md mb-4">
                        <i class="fas fa-newspaper text-4xl text-indigo-500 mb-3"></i>
                        <h4 class="text-xl font-semibold text-indigo-600 mb-2">وبلاگ تجربه‌ها</h4>
                        <p class="text-sm text-gray-600">داستان‌ها، راهنماها و نکاتی برای تجربه‌گرایان و تجربه‌فرمایان.</p>
                    </div>
                    <div id="preview-contact-us" class="site-section-card bg-white p-6 rounded-xl shadow-lg text-center cursor-pointer">
                         <img src="https://placehold.co/600x400/ed8936/ffffff?text=تماس+با+ما" alt="تماس با ما" class="w-full h-48 object-cover rounded-md mb-4">
                        <i class="fas fa-address-book text-4xl text-orange-500 mb-3"></i>
                        <h4 class="text-xl font-semibold text-orange-600 mb-2">تماس با ما</h4>
                        <p class="text-sm text-gray-600">با ما در ارتباط باشید و ما را در شبکه‌های اجتماعی دنبال کنید.</p>
                    </div>
                </div>
            </section>

            <section id="roleSelectionSection" class="py-12 md:py-16">
                <h3 class="text-3xl font-bold mb-10 text-center text-teal-700">به جامعه ما بپیوندید:</h3>
                <div class="flex flex-col md:flex-row justify-center items-center gap-8">
                    <button id="selectExperiencer" class="cta-button bg-gradient-to-br from-green-500 to-emerald-600 text-white font-bold py-4 px-8 rounded-xl shadow-lg text-xl hover:from-green-600 hover:to-emerald-700 w-full md:w-auto">
                        <i class="fas fa-hiking mr-3"></i>من یک <span class="font-extrabold">تجربه‌گرا</span> هستم
                        <span class="block text-sm font-normal mt-1">به دنبال ماجراجویی و یادگیری در سفر</span>
                    </button>
                    <span class="text-gray-500 text-lg font-medium hidden md:block">یا</span>
                    <button id="selectHost" class="cta-button bg-gradient-to-br from-purple-500 to-indigo-600 text-white font-bold py-4 px-8 rounded-xl shadow-lg text-xl hover:from-purple-600 hover:to-indigo-700 w-full md:w-auto">
                        <i class="fas fa-hands-helping mr-3"></i>من یک <span class="font-extrabold">تجربه‌فرما</span> هستم
                        <span class="block text-sm font-normal mt-1">میزبان تجربه‌گرایان در مقصد خود</span>
                    </button>
                </div>
            </section>
        </div>

        <div id="experienceCenterView" class="hidden">
            <h2 id="experienceCenterTitle" class="text-3xl font-semibold mb-8 text-center text-teal-700">تجربه‌های در جریان</h2>
            <div id="filterBar" class="bg-white p-4 md:p-6 rounded-lg shadow-md mb-8">
                <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-5 gap-4 items-end">
                    <div>
                        <label for="filterProvince" class="block text-sm font-medium text-gray-700">استان:</label>
                        <select id="filterProvince" class="mt-1 block w-full p-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                            <option value="">همه استان‌ها</option>
                        </select>
                    </div>
                    <div>
                        <label for="filterCity" class="block text-sm font-medium text-gray-700">شهر:</label>
                        <select id="filterCity" class="mt-1 block w-full p-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                            <option value="">همه شهرها</option>
                        </select>
                    </div>
                    <div>
                        <label for="filterDuration" class="block text-sm font-medium text-gray-700">مدت زمان (مثلا: ۲ هفته):</label>
                        <input type="text" id="filterDuration" placeholder="هر مدتی" class="mt-1 block w-full p-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    </div>
                    <div>
                        <label for="filterExperienceType" class="block text-sm font-medium text-gray-700">نوع تجربه:</label>
                        <select id="filterExperienceType" class="mt-1 block w-full p-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                            <option value="">همه انواع</option>
                        </select>
                    </div>
                    <div class="lg:col-span-1">
                        <label for="searchInput" class="block text-sm font-medium text-gray-700">جستجو:</label>
                        <input type="text" id="searchInput" placeholder="کلمه کلیدی..." class="mt-1 block w-full p-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    </div>
                </div>
                <div class="mt-4 flex flex-col sm:flex-row justify-end space-y-2 sm:space-y-0 sm:space-x-3 sm:space-x-reverse">
                    <button id="applyFiltersButton" class="w-full sm:w-auto bg-teal-500 hover:bg-teal-600 text-white font-semibold py-2 px-4 rounded-md transition"><i class="fas fa-filter mr-1"></i> اعمال فیلترها و جستجو</button>
                    <button id="clearFiltersButton" class="w-full sm:w-auto bg-gray-300 hover:bg-gray-400 text-gray-800 font-semibold py-2 px-4 rounded-md transition"><i class="fas fa-times mr-1"></i> پاک کردن همه</button>
                </div>
            </div>
            <div id="experienceCenterContent" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                </div>
        </div>
        
        <div id="postExperienceView" class="hidden mt-8 bg-white p-6 md:p-8 rounded-lg shadow-xl max-w-2xl mx-auto">
            </div>
        
        <div id="profileView" class="hidden mt-2">
            </div>
        
        <div id="settingsView" class="hidden mt-8 bg-white p-6 md:p-8 rounded-lg shadow-xl max-w-2xl mx-auto">
            </div>

        <div id="blogView" class="hidden mt-8 bg-white p-6 md:p-8 rounded-lg shadow-xl max-w-3xl mx-auto text-center">
            <img src="https://placehold.co/800x400/a0aec0/ffffff?text=تصویر+شاخص+وبلاگ" alt="وبلاگ" class="w-full h-64 object-cover rounded-md mb-6">
            <h2 class="text-3xl font-bold mb-6 text-indigo-700"><i class="fas fa-newspaper mr-2"></i>وبلاگ experience.ir</h2>
            <p class="text-gray-600 mb-8 leading-relaxed">
                به زودی در این بخش، مقالات، داستان‌های الهام‌بخش از تجربه‌گرایان و تجربه‌فرمایان، راهنماهای سفر و نکاتی برای کسب بهترین تجربه‌ها منتشر خواهد شد. با ما همراه باشید تا از آخرین نوشته‌ها مطلع شوید!
            </p>
            <button id="backToHomeFromBlog" class="bg-teal-500 hover:bg-teal-600 text-white font-semibold py-2 px-6 rounded-md transition"><i class="fas fa-arrow-right mr-1"></i> بازگشت به صفحه اصلی</button>
        </div>

        <div id="contactUsView" class="hidden mt-8 bg-white p-6 md:p-8 rounded-lg shadow-xl max-w-3xl mx-auto text-center">
            <img src="https://placehold.co/800x400/ecc94b/ffffff?text=ارتباط+با+ما" alt="تماس با ما" class="w-full h-64 object-cover rounded-md mb-6">
            <h2 class="text-3xl font-bold mb-6 text-orange-600"><i class="fas fa-address-book mr-2"></i>تماس با ما</h2>
            <p class="text-gray-700 mb-4">ما همیشه از شنیدن نظرات، پیشنهادات و سوالات شما خوشحال می‌شویم. </p>
            <p class="text-gray-600 mb-6 leading-relaxed">
                می‌توانید از طریق ایمیل <a href="mailto:info@tajrobeh.ir" class="text-teal-500 hover:underline">info@tajrobeh.ir</a> با ما در تماس باشید. (این یک آدرس ایمیل نمایشی است)
            </p>
            <h4 class="text-xl font-semibold text-gray-700 mb-3">ما را در شبکه‌های اجتماعی دنبال کنید:</h4>
            <div class="flex justify-center space-x-6 space-x-reverse text-3xl">
                <a href="#" class="text-pink-600 hover:text-pink-700 transition"><i class="fab fa-instagram"></i></a>
                <a href="#" class="text-blue-500 hover:text-blue-600 transition"><i class="fab fa-telegram-plane"></i></a>
                <a href="#" class="text-red-600 hover:text-red-700 transition"><i class="fab fa-youtube"></i></a>
                <a href="#" class="text-blue-700 hover:text-blue-800 transition"><i class="fab fa-linkedin"></i></a>
            </div>
             <button id="backToHomeFromContact" class="mt-8 bg-teal-500 hover:bg-teal-600 text-white font-semibold py-2 px-6 rounded-md transition"><i class="fas fa-arrow-right mr-1"></i> بازگشت به صفحه اصلی</button>
        </div>


    </div> <footer class="bg-gray-800 text-white text-center p-6 mt-10">
        <p class="text-sm">حقوق مادی و معنوی این سایت متعلق به همه افراد تجربه‌گرا در سطح کره زمین است.</p>
        <p class="text-xs mt-2">&copy; ۱۴۰۳ - experience.ir</p>
    </footer>

    <div id="experienceDetailModal" class="modal">
        </div>

    <div id="ratingModal" class="modal">
        </div>

    <div id="messageModal" class="modal">
        </div>


<script>
    // --- Mock Data ---
    let experiences = [
        {
            id: 1, hostId: 101, hostName: "باغ رویایی مهرگان", title: "کمک در برداشت میوه‌های ارگانیک و زندگی در طبیعت",
            location: "روستای سرسبز، دماوند", province: "تهران", city: "دماوند", experienceType: "کشاورزی",
            description: "ما یک باغ بزرگ و زیبا با محصولات ارگانیک داریم و برای فصل برداشت (سیب، گلابی، انگور) نیاز به کمک داریم...",
            offerings: "اقامت در کلبه چوبی دنج، سه وعده غذای سالم، آموزش باغبانی.",
            duration: "۲ هفته", postedDate: "۱۴۰۳/۰۲/۱۵", applicants: [202],
            reviews: [ { experiencerId: 201, experiencerName: "سارا احمدی", rating: 5, comment: "تجربه فوق‌العاده‌ای بود!" } ], status: "open"
        },
        {
            id: 2, hostId: 102, hostName: "اقامتگاه سنتی کویرانه", title: "همکاری در امور اقامتگاه بومگردی و راهنمای گردشگری",
            location: "قلب کویر، یزد", province: "یزد", city: "یزد", experienceType: "گردشگری",
            description: "به یک یا دو نفر با انگیزه، خوش‌برخورد برای کمک در امور پذیرایی، مدیریت رزروها و همراهی مهمانان در تورهای کویرگردی نیازمندیم...",
            offerings: "اقامت رایگان در اتاق اختصاصی، صبحانه و ناهار، شرکت رایگان در تورها.",
            duration: "۱ ماه", postedDate: "۱403/03/01", applicants: [201],
            reviews: [], status: "open"
        },
        {
            id: 3, hostId: 101, hostName: "باغ رویایی مهرگان", title: "مشارکت در ساخت و ساز اکو کمپ",
            location: "روستای سرسبز، دماوند", province: "تهران", city: "دماوند", experienceType: "فنی",
            description: "در حال توسعه یک بخش اکو کمپ در باغ هستیم و نیاز به کمک برای ساخت سازه‌های چوبی ساده داریم...",
            offerings: "اقامت، سه وعده غذا، استفاده از ابزارآلات.",
            duration: "۳ هفته", postedDate: "۱۴۰۳/۰۳/۲۰", applicants: [],
            reviews: [], status: "open"
        },
        {
            id: 4, hostId: 103, hostName: "کارگاه حصیربافی گیلانا", title: "یادگیری و کمک در بافت حصیر گیلانی",
            location: "روستای ساحلی، انزلی", province: "گیلان", city: "انزلی", experienceType: "هنری",
            description: "کارگاه کوچک ما به دنبال افرادی است که علاقه‌مند به یادگیری هنر اصیل حصیربافی گیلان باشند و در تولید محصولات کمک کنند...",
            offerings: "آموزش رایگان حصیربافی، اقامت در خانه روستایی، یک وعده غذای محلی.",
            duration: "۱۰ روز", postedDate: "۱۴۰۳/04/01", applicants: [],
            reviews: [], status: "open"
        },
        {
            id: 5, hostId: 104, hostName: "استارت‌آپ محتوای سبز", title: "تولید محتوا برای کمپین محیط زیستی",
            location: "دفتر مرکزی، شیراز", province: "فارس", city: "شیراز", experienceType: "تولیدمحتوا",
            description: "برای کمپین جدید آگاهی‌رسانی در مورد تفکیک زباله، به نویسندگان و گرافیست‌های خلاق برای تولید محتوای دیجیتال نیازمندیم...",
            offerings: "فضای کاری اشتراکی، ناهار، همکاری با تیم جوان و پویا.",
            duration: "۲ هفته", postedDate: "۱۴۰۳/04/05", applicants: [],
            reviews: [], status: "open"
        }
    ];

    let users = { 
        experiencers: [
            { id: 201, name: "سارا احمدی", email: "sara@example.com", bio: "عاشق سفر، طبیعت و یادگیری فرهنگ‌های جدید...", profileImageUrl: "https://placehold.co/150x150/e2e8f0/4a5568?text=سارا", headerImageUrl: "https://placehold.co/1000x250/a0aec0/ffffff?text=طبیعتگردی", skills: ["باغبانی", "آشپزی"], applications: [2], ratingsGiven: [], ratingsReceived: [ { fromId: 102, fromName: "اقامتگاه سنتی کویرانه", rating: 4, comment: "میزبان خوب بود.", type: "host_to_experiencer" } ] },
            { id: 202, name: "علی رضایی", email: "ali@example.com", bio: "نجار و نقاش ساختمان، به دنبال تجربه‌های متفاوت...", profileImageUrl: "https://placehold.co/150x150/ecc94b/94700c?text=علی", headerImageUrl: "https://placehold.co/1000x250/9ae6b4/ffffff?text=هنر", skills: ["نجاری", "نقاشی"], applications: [1], ratingsGiven: [], ratingsReceived: [] },
        ],
        hosts: [ 
            { id: 101, name: "باغ رویایی مهرگان", email: "mehregan@example.com", bio: "ما یک خانواده کشاورز هستیم...", profileImageUrl: "https://placehold.co/150x150/9f7aea/5a3c81?text=مهرگان", headerImageUrl: "https://placehold.co/1000x250/4fd1c5/ffffff?text=باغ+ما", location: "دماوند", experiencesPostedIds: [1, 3], ratingsGiven: [], ratingsReceived: [ { fromId: 202, fromName: "علی رضایی", rating: 5, comment: "تجربه عالی بود در باغ مهرگان.", type: "experiencer_to_host" }] },
            { id: 102, name: "اقامتگاه سنتی کویرانه", email: "kavir@example.com", bio: "عاشق کویر و فرهنگ غنی ایران...", profileImageUrl: "https://placehold.co/150x150/ed8936/9c4221?text=کویرانه", headerImageUrl: "https://placehold.co/1000x250/f6e05e/ffffff?text=کویر", location: "یزد", experiencesPostedIds: [2], ratingsGiven: [], ratingsReceived: [] },
            { id: 103, name: "کارگاه حصیربافی گیلانا", email: "gilana@example.com", bio: "هنر حصیربافی، میراث ماندگار ماست.", profileImageUrl: "https://placehold.co/150x150/48bb78/276749?text=گیلانا", headerImageUrl: "https://placehold.co/1000x250/68d391/ffffff?text=حصیربافی", location: "انزلی", experiencesPostedIds: [4], ratingsGiven: [], ratingsReceived: [] },
            { id: 104, name: "استارت‌آپ محتوای سبز", email: "sabz@example.com", bio: "برای زمینی سبزتر تلاش می‌کنیم.", profileImageUrl: "https://placehold.co/150x150/4299e1/2b6cb0?text=سبز", headerImageUrl: "https://placehold.co/1000x250/63b3ed/ffffff?text=محتوای+سبز", location: "شیراز", experiencesPostedIds: [5], ratingsGiven: [], ratingsReceived: [] }
        ]
    };
    
    let currentUser = null; 
    let currentViewingExperienceId = null;
    let currentRatingTarget = null;
    let currentFilters = { province: '', city: '', duration: '', experienceType: '', search: '' };


    // --- DOM Elements ---
    const landingView = document.getElementById('landingView');
    const experienceCenterView = document.getElementById('experienceCenterView');
    const experienceCenterTitle = document.getElementById('experienceCenterTitle');
    const experienceCenterContent = document.getElementById('experienceCenterContent'); // This is now the grid for cards
    const postExperienceView = document.getElementById('postExperienceView');
    const profileView = document.getElementById('profileView');
    const settingsView = document.getElementById('settingsView');
    const blogView = document.getElementById('blogView');
    const contactUsView = document.getElementById('contactUsView');
    
    const experienceDetailModalEl = document.getElementById('experienceDetailModal'); // Renamed to avoid conflict
    const ratingModalEl = document.getElementById('ratingModal'); // Renamed
    const messageModalEl = document.getElementById('messageModal'); // Renamed

    const platformLogoLink = document.getElementById('platform-logo-link');
    const userRoleDisplay = document.getElementById('user-role-display');
    const logoutButton = document.getElementById('logout-button');
    const navUserActions = document.getElementById('nav-user-actions');
    const navVisitorLinks = document.getElementById('nav-visitor-links');

    const navButtons = {
        experienceCenter: document.getElementById('nav-experience-center'),
        profile: document.getElementById('nav-profile'),
        settings: document.getElementById('nav-settings'),
    };
    
    // Filter bar elements
    const filterProvinceSelect = document.getElementById('filterProvince');
    const filterCitySelect = document.getElementById('filterCity');
    const filterDurationInput = document.getElementById('filterDuration');
    const filterExperienceTypeSelect = document.getElementById('filterExperienceType');
    const searchInput = document.getElementById('searchInput');
    const applyFiltersButton = document.getElementById('applyFiltersButton');
    const clearFiltersButton = document.getElementById('clearFiltersButton');


    // --- Gemini API Function (remains the same) ---
    async function generateTextWithGemini(prompt, spinnerElement, buttonElement) {
        if (spinnerElement) spinnerElement.classList.remove('hidden');
        if (buttonElement) buttonElement.disabled = true;
        const apiKey = ""; 
        const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=${apiKey}`;
        const payload = { contents: [{ role: "user", parts: [{ text: prompt }] }] };
        try {
            const response = await fetch(apiUrl, { method: 'POST', headers: { 'Content-Type': 'application/json' }, body: JSON.stringify(payload) });
            if (!response.ok) { const errorData = await response.json(); throw new Error(`API Error: ${errorData.error?.message || response.statusText}`); }
            const result = await response.json();
            if (result.candidates && result.candidates.length > 0 && result.candidates[0].content && result.candidates[0].content.parts && result.candidates[0].content.parts.length > 0) {
                return result.candidates[0].content.parts[0].text;
            } else { throw new Error("پاسخ غیرمنتظره از سرویس هوش مصنوعی."); }
        } catch (error) {
            console.error("Error calling Gemini API:", error);
            showMessage("خطا در ارتباط با هوش مصنوعی", `مشکلی در تولید متن پیش آمد: ${error.message}`, 'fas fa-robot text-red-500');
            return null;
        } finally {
            if (spinnerElement) spinnerElement.classList.add('hidden');
            if (buttonElement) buttonElement.disabled = false;
        }
    }

    // --- Utility Functions ---
    function showView(viewElement) {
        [landingView, experienceCenterView, postExperienceView, profileView, settingsView, blogView, contactUsView].forEach(v => v.classList.add('hidden'));
        if (viewElement) viewElement.classList.remove('hidden');
        window.scrollTo(0, 0); 
    }
    
    function updateNav() {
        if (currentUser) {
            navUserActions.classList.remove('hidden');
            navVisitorLinks.classList.add('hidden');
            Object.values(navButtons).forEach(btn => btn.classList.remove('hidden'));
            userRoleDisplay.textContent = `${currentUser.type === 'experiencer' ? 'تجربه‌گرا' : 'تجربه‌فرما'}: ${currentUser.name}`;
            logoutButton.classList.remove('hidden');
        } else {
            navUserActions.classList.add('hidden');
            navVisitorLinks.classList.remove('hidden');
            Object.values(navButtons).forEach(btn => btn.classList.add('hidden'));
            userRoleDisplay.textContent = "";
            logoutButton.classList.add('hidden');
        }
    }

    function openModal(modalId) { document.getElementById(modalId).style.display = 'block'; }
    function closeModal(modalId) { document.getElementById(modalId).style.display = 'none'; }
    
    function showMessage(title, text, iconClass = 'fas fa-info-circle text-teal-500') {
        messageModalEl.querySelector('#messageModalTitle').textContent = title;
        messageModalEl.querySelector('#messageModalText').textContent = text;
        messageModalEl.querySelector('#messageModalIcon').className = `text-5xl mb-4 ${iconClass}`;
        openModal('messageModal');
    }

    // --- Populate Filter Dropdowns ---
    function populateFilterDropdowns() {
        const provinces = [...new Set(experiences.map(exp => exp.province))].filter(Boolean);
        const cities = [...new Set(experiences.map(exp => exp.city))].filter(Boolean);
        const types = [...new Set(experiences.map(exp => exp.experienceType))].filter(Boolean);

        filterProvinceSelect.innerHTML = '<option value="">همه استان‌ها</option>';
        provinces.forEach(p => filterProvinceSelect.add(new Option(p, p)));

        filterCitySelect.innerHTML = '<option value="">همه شهرها</option>';
        cities.forEach(c => filterCitySelect.add(new Option(c, c)));
        
        filterExperienceTypeSelect.innerHTML = '<option value="">همه انواع</option>';
        types.forEach(t => filterExperienceTypeSelect.add(new Option(t, t)));
    }


    // --- Rendering Functions ---
    function renderAvailableExperiences(filteredExperiences = experiences) { 
        // If called by logged-in experiencer, title might change. For visitor, it's "تجربه‌های در جریان"
        if (currentUser && currentUser.type === 'experiencer') {
             experienceCenterTitle.textContent = "کاوش در میان تجربه‌های هیجان‌انگیز";
        } else {
             experienceCenterTitle.textContent = "تجربه‌های در جریان";
        }
       
        experienceCenterContent.innerHTML = ''; // Clear previous cards
        
        const experiencesToDisplay = filteredExperiences.filter(exp => exp.status === 'open');

        if (experiencesToDisplay.length === 0) {
            experienceCenterContent.innerHTML = '<p class="text-gray-500 col-span-full text-center py-8">متاسفانه با فیلترهای انتخابی، تجربه‌ای یافت نشد. لطفا فیلترها را تغییر دهید.</p>';
            return;
        }
        
        experiencesToDisplay.forEach(exp => {
            const card = document.createElement('div');
            card.className = 'bg-white p-5 rounded-xl shadow-lg hover:shadow-2xl transition-shadow duration-300 flex flex-col justify-between';
            card.innerHTML = `
                <div>
                    <h4 class="text-xl font-bold text-indigo-600 mb-2">${exp.title}</h4>
                    <p class="text-sm text-gray-600 mb-1"><i class="fas fa-user-tie mr-2 text-purple-500"></i>تجربه‌فرما: ${exp.hostName}</p>
                    <p class="text-sm text-gray-600 mb-2"><i class="fas fa-map-marker-alt mr-2 text-red-500"></i>${exp.city}, ${exp.province} - <i class="fas fa-clock mr-1 ml-1 text-blue-500"></i>مدت: ${exp.duration}</p>
                    <p class="text-sm text-gray-700 mb-1"><i class="fas fa-briefcase mr-2 text-green-500"></i>نوع: ${exp.experienceType}</p>
                    <p class="text-sm text-gray-700 mb-3 h-20 overflow-hidden relative after:content-[''] after:absolute after:bottom-0 after:right-0 after:w-full after:h-8 after:bg-gradient-to-t after:from-white after:to-transparent">${exp.description}</p>
                    <div class="text-xs text-gray-700 bg-gray-100 p-2 rounded-md mb-3">
                        <i class="fas fa-gift mr-1 text-green-500"></i> ${exp.offerings}
                    </div>
                </div>
                <button class="view-details-btn text-sm bg-teal-500 hover:bg-teal-600 text-white py-2 px-4 rounded-md w-full transition-colors" data-exp-id="${exp.id}">مشاهده جزئیات و ارسال درخواست</button>
            `;
            experienceCenterContent.appendChild(card);
        });

        document.querySelectorAll('.view-details-btn').forEach(button => {
            button.addEventListener('click', (e) => {
                const expId = parseInt(e.target.closest('[data-exp-id]').dataset.expId);
                showExperienceDetail(expId);
            });
        });
    }

    function renderMyPostedExperiences() { 
        // This function is for hosts and doesn't need the filter bar.
        // It will be displayed within the #experienceCenterView but the #filterBar should be hidden or not rendered for hosts.
        document.getElementById('filterBar').classList.add('hidden'); // Hide filter bar for hosts
        experienceCenterTitle.textContent = "مدیریت تجربه‌های ارسالی شما";
        experienceCenterContent.innerHTML = ''; // Clear previous content (like filter bar if it was part of it)

        const header = document.createElement('div');
        header.className = 'flex justify-between items-center mb-6 border-b pb-3';
        header.innerHTML = `
            <h3 class="text-2xl font-semibold text-purple-700">تجربه‌های ارسال شده توسط شما</h3>
            <button id="showPostExperienceFormButton" class="bg-green-500 hover:bg-green-600 text-white font-semibold py-2 px-4 rounded-md transition">
                <i class="fas fa-plus mr-1"></i> ایجاد تجربه جدید
            </button>
        `;
        experienceCenterContent.appendChild(header);
        // Ensure event listener is re-attached if this view is re-rendered
        header.querySelector('#showPostExperienceFormButton').addEventListener('click', () => {
            // Fill the actual postExperienceView div with its form content
            postExperienceView.innerHTML = document.getElementById('postExperienceViewTemplate').innerHTML;
            // Re-attach AI button listener
            postExperienceView.querySelector('#generateExpDescriptionButton').addEventListener('click', handleGenerateExpDescription);
            document.getElementById('postExperienceForm').reset();
            document.getElementById('expDescription').value = ''; 
            showView(postExperienceView);
        });


        const listContainer = document.createElement('div');
        listContainer.className = 'space-y-4';
        
        const myExps = experiences.filter(exp => exp.hostId === currentUser.id);

        if (myExps.length === 0) {
            listContainer.innerHTML = '<p class="text-gray-500 text-center py-8">شما هنوز تجربه‌ای ارسال نکرده‌اید.</p>';
        } else {
            myExps.forEach(exp => {
                const card = document.createElement('div');
                card.className = 'bg-white p-5 rounded-xl shadow-lg';
                card.innerHTML = `
                    <h4 class="text-xl font-bold text-purple-600">${exp.title}</h4>
                    <p class="text-sm text-gray-600 mb-1">مکان: ${exp.location} - تاریخ ارسال: ${exp.postedDate}</p>
                    <p class="text-sm text-gray-600 mb-2">وضعیت: <span class="${exp.status === 'open' ? 'text-green-600' : 'text-red-600'} font-semibold">${exp.status === 'open' ? 'باز' : 'بسته'}</span> - متقاضی: ${exp.applicants.length}</p>
                    <div class="mt-3 space-x-2 space-x-reverse">
                        <button class="text-xs bg-yellow-500 hover:bg-yellow-600 text-white py-1 px-3 rounded-md edit-exp-btn" data-exp-id="${exp.id}"><i class="fas fa-edit mr-1"></i>ویرایش</button>
                        <button class="text-xs bg-red-500 hover:bg-red-600 text-white py-1 px-3 rounded-md delete-exp-btn" data-exp-id="${exp.id}"><i class="fas fa-trash-alt mr-1"></i>حذف</button>
                    </div>
                `;
                listContainer.appendChild(card);
            });
        }
        experienceCenterContent.appendChild(listContainer);
    }

    function showExperienceDetail(expId) {
        const exp = experiences.find(e => e.id === expId);
        if (!exp) return;
        currentViewingExperienceId = expId;
        
        // Ensure the modal content is loaded (it's empty in HTML initially)
        experienceDetailModalEl.innerHTML = document.getElementById('experienceDetailModalTemplate').innerHTML;


        experienceDetailModalEl.querySelector('#modalExpTitle').textContent = exp.title;
        experienceDetailModalEl.querySelector('#modalExpHost').textContent = exp.hostName; 
        experienceDetailModalEl.querySelector('#modalExpLocation').textContent = `${exp.city}, ${exp.province}`;
        experienceDetailModalEl.querySelector('#modalExpDuration').textContent = exp.duration;
        experienceDetailModalEl.querySelector('#modalExpDescription').textContent = exp.description;
        experienceDetailModalEl.querySelector('#modalExpOfferings').textContent = exp.offerings;

        const reviewsListEl = experienceDetailModalEl.querySelector('#modalExpReviewsList');
        reviewsListEl.innerHTML = '';
        if (exp.reviews && exp.reviews.length > 0) {
            exp.reviews.forEach(review => {
                const li = document.createElement('li');
                li.className = 'bg-gray-50 p-2 rounded border text-xs';
                li.innerHTML = `<strong>${review.experiencerName} (${review.rating} <i class="fas fa-star text-yellow-400"></i>):</strong> ${review.comment}`;
                reviewsListEl.appendChild(li);
            });
        } else {
            reviewsListEl.innerHTML = '<li class="text-gray-500 text-xs">هنوز نظری ثبت نشده.</li>';
        }
        
        const applyButton = experienceDetailModalEl.querySelector('#applyForExperienceButton');
        if (currentUser && currentUser.type === 'experiencer') {
            applyButton.classList.remove('hidden');
            const userApplied = exp.applicants.includes(currentUser.id) || users.experiencers.find(u => u.id === currentUser.id)?.applications.includes(expId);
            if (userApplied) {
                 applyButton.textContent = "شما قبلا درخواست داده‌اید";
                 applyButton.disabled = true;
                 applyButton.className = 'bg-gray-400 text-white font-bold py-2 px-6 rounded-md cursor-not-allowed';
            } else {
                applyButton.textContent = "ارسال درخواست برای این تجربه";
                applyButton.disabled = false;
                applyButton.className = 'bg-green-500 hover:bg-green-600 text-white font-bold py-2 px-6 rounded-md transition';
            }
        } else if (!currentUser) { // Visitor can see the button but it should be disabled or prompt login
            applyButton.classList.remove('hidden');
            applyButton.textContent = "برای ارسال درخواست وارد شوید";
            applyButton.disabled = true; // Or redirect to login/role selection
            applyButton.className = 'bg-orange-400 text-white font-bold py-2 px-6 rounded-md cursor-not-allowed';
             applyButton.onclick = () => { closeModal('experienceDetailModal'); showView(landingView); document.getElementById('roleSelectionSection').scrollIntoView(); };

        } else { // Host viewing
            applyButton.classList.add('hidden');
        }
        // Re-attach close button event listener for the newly injected modal content
        experienceDetailModalEl.querySelector('.close-button').onclick = () => closeModal('experienceDetailModal');
        applyButton.onclick = handleApplyForExperience; // Re-attach specific handler

        openModal('experienceDetailModal');
    }
    
    function renderProfile() {
        if (!currentUser) return;
        // Ensure the profile view content is loaded
        profileView.innerHTML = document.getElementById('profileViewTemplate').innerHTML;
        
        let user, userTypeString, ratingsReceived, ratingsGiven, experienceCount, experienceCountLabel;

        if (currentUser.type === 'experiencer') {
            user = users.experiencers.find(u => u.id === currentUser.id);
            userTypeString = "تجربه‌گرا";
            ratingsReceived = user.ratingsReceived.filter(r => r.type === 'host_to_experiencer');
            ratingsGiven = user.ratingsGiven; 
            experienceCount = user.applications.length; 
            experienceCountLabel = "تجربه درخواست شده";
        } else { 
            user = users.hosts.find(u => u.id === currentUser.id);
            userTypeString = "تجربه‌فرما";
            ratingsReceived = user.ratingsReceived.filter(r => r.type === 'experiencer_to_host');
            ratingsGiven = user.ratingsGiven; 
            experienceCount = user.experiencesPostedIds.length;
            experienceCountLabel = "تجربه ایجاد شده";
        }

        profileView.querySelector('#profileHeader').style.backgroundImage = `url('${user.headerImageUrl || 'https://placehold.co/1000x250/667eea/ffffff?text=هدر+پروفایل'}')`;
        profileView.querySelector('#profileImage').src = user.profileImageUrl || 'https://placehold.co/150x150/cbd5e0/718096?text=عکس';
        profileView.querySelector('#profileName').textContent = user.name;
        profileView.querySelector('#profileRole').textContent = userTypeString;
        profileView.querySelector('#profileBio').textContent = user.bio || "بیوگرافی هنوز تکمیل نشده است.";
        
        const totalRating = ratingsReceived.reduce((sum, r) => sum + r.rating, 0);
        const avgRating = ratingsReceived.length > 0 ? (totalRating / ratingsReceived.length).toFixed(1) : "N/A";
        profileView.querySelector('#profileAvgRating').innerHTML = `${avgRating} ${avgRating !== "N/A" ? '<i class="fas fa-star"></i>' : ''}`;
        
        profileView.querySelector('#profileExperienceCount').textContent = experienceCount;
        profileView.querySelector('#profileExperienceCountLabel').textContent = experienceCountLabel;

        renderRatingsList(profileView.querySelector('#receivedRatingsContent'), ratingsReceived, true);
        renderRatingsList(profileView.querySelector('#givenRatingsContent'), ratingsGiven, false);
        
        setupRateOthersDropdown(); // This will also set up its related button

        // Setup tab buttons
        profileView.querySelectorAll('.profile-tab-button').forEach(button => {
            button.addEventListener('click', function() {
                profileView.querySelectorAll('.profile-tab-button').forEach(btn => {
                    btn.classList.remove('active-tab', 'text-teal-600', 'border-teal-500');
                    btn.classList.add('text-gray-500');
                });
                this.classList.add('active-tab', 'text-teal-600', 'border-teal-500');
                this.classList.remove('text-gray-500');

                profileView.querySelectorAll('.profile-tab-pane').forEach(pane => pane.classList.add('hidden'));
                profileView.querySelector('#' + this.dataset.tab + 'Content').classList.remove('hidden');
                
                if(this.dataset.tab === 'rateOthers') {
                    setupRateOthersDropdown(); 
                }
            });
        });
         // Activate the first tab by default
        profileView.querySelector('.profile-tab-button[data-tab="receivedRatings"]').classList.add('active-tab', 'text-teal-600', 'border-teal-500');
        profileView.querySelector('.profile-tab-button[data-tab="receivedRatings"]').classList.remove('text-gray-500');
        profileView.querySelector('#receivedRatingsContent').classList.remove('hidden');
        profileView.querySelector('#givenRatingsContent').classList.add('hidden');
        profileView.querySelector('#rateOthersContent').classList.add('hidden');


        showView(profileView);
    }

    function renderRatingsList(containerEl, ratings, isReceived) {
        // ... (same as before)
        containerEl.innerHTML = '';
        if (ratings.length === 0) {
            containerEl.innerHTML = `<p class="text-gray-500 text-center py-4">هنوز ${isReceived ? 'امتیازی دریافت نکرده‌اید.' : 'امتیازی ثبت نکرده‌اید.'}</p>`;
            return;
        }
        ratings.forEach(r => {
            const item = document.createElement('div');
            item.className = 'bg-gray-50 p-4 rounded-lg border border-gray-200 shadow-sm';
            let targetOrFromName = isReceived ? r.fromName : r.toName;
            let targetType = "";
            if (isReceived) { 
                targetType = r.type.startsWith("host") ? "تجربه‌فرما" : "تجربه‌گرا";
            } else { 
                if (r.type.endsWith("experience")) targetType = "تجربه";
                else if (r.type.endsWith("host")) targetType = "تجربه‌فرما";
                else if (r.type.endsWith("experiencer")) targetType = "تجربه‌گرا";
            }

            item.innerHTML = `
                <div class="flex justify-between items-start">
                    <p class="font-semibold text-gray-700">${isReceived ? 'از طرف' : 'به'}: ${targetOrFromName} <span class="text-xs text-blue-500">(${targetType})</span></p>
                    <span class="text-yellow-500 font-bold">${r.rating} <i class="fas fa-star"></i></span>
                </div>
                <p class="text-sm text-gray-600 mt-1">${r.comment}</p>
            `;
            containerEl.appendChild(item);
        });
    }
    
    function setupRateOthersDropdown() {
        // This function is called within renderProfile, so profileView elements are available
        const rateableItemsDropdown = profileView.querySelector('#rateableItemsDropdown');
        const rateInteractionTitle = profileView.querySelector('#rateInteractionTitle');
        const openRateModalButton = profileView.querySelector('#openRateModalButton');

        rateableItemsDropdown.innerHTML = '<option value="">-- انتخاب کنید --</option>';
        let canRateItems = [];

        // ... (logic for populating canRateItems remains the same as before) ...
        if (currentUser.type === 'experiencer') {
            const user = users.experiencers.find(u => u.id === currentUser.id);
            const appliedExpIds = user.applications;
            experiences.filter(exp => appliedExpIds.includes(exp.id) )
                .forEach(exp => {
                    const alreadyRatedHost = user.ratingsGiven.some(r => r.toId === exp.hostId && r.type === 'experiencer_to_host');
                    if (!alreadyRatedHost) {
                         canRateItems.push({id: exp.hostId, name: `تجربه‌فرما: ${exp.hostName} (برای تجربه: ${exp.title})`, type: 'host'});
                    }
                    const alreadyRatedExp = user.ratingsGiven.some(r => r.toId === exp.id && r.type === 'experiencer_to_experience');
                     if (!alreadyRatedExp) {
                         canRateItems.push({id: exp.id, name: `تجربه: ${exp.title} (ارائه شده توسط: ${exp.hostName})`, type: 'experience'});
                    }
                });
            if(canRateItems.length > 0) rateInteractionTitle.textContent = "امتیازدهی به تجربه‌فرما یا تجربه:";
            else rateInteractionTitle.textContent = "موردی برای امتیازدهی وجود ندارد.";

        } else { 
            const user = users.hosts.find(u => u.id === currentUser.id);
            const myExpIds = user.experiencesPostedIds;
            experiences.filter(exp => myExpIds.includes(exp.id) )
                .forEach(exp => {
                    exp.applicants.forEach(applicantId => {
                        const applicant = users.experiencers.find(ex => ex.id === applicantId);
                        if (applicant) {
                            const alreadyRated = user.ratingsGiven.some(r => r.toId === applicantId && r.type === 'host_to_experiencer' );
                             if (!alreadyRated) {
                                canRateItems.push({id: applicantId, name: `تجربه‌گر: ${applicant.name} (برای تجربه: ${exp.title})`, type: 'experiencer'});
                             }
                        }
                    });
                });
            if(canRateItems.length > 0) rateInteractionTitle.textContent = "امتیازدهی به تجربه‌گر:";
            else rateInteractionTitle.textContent = "موردی برای امتیازدهی وجود ندارد.";
        }
        
        if (canRateItems.length > 0) {
            canRateItems.forEach(item => {
                const option = document.createElement('option');
                option.value = JSON.stringify(item);
                option.textContent = item.name;
                rateableItemsDropdown.appendChild(option);
            });
            openRateModalButton.classList.remove('hidden');
            openRateModalButton.onclick = handleOpenRateModal; // Attach event listener
        } else {
            openRateModalButton.classList.add('hidden');
        }
    }

    function setupStarRating() {
        // This function is called when ratingModal is opened, so its elements are available
        const container = ratingModalEl.querySelector('#starRatingContainer');
        container.innerHTML = '';
        for (let i = 1; i <= 5; i++) {
            const star = document.createElement('i');
            star.classList.add('fas', 'fa-star', 'text-gray-300', 'text-3xl', 'cursor-pointer', 'hover:text-yellow-400', 'transition-colors');
            star.dataset.value = i;
            star.addEventListener('click', function() {
                ratingModalEl.querySelector('#ratingValue').value = this.dataset.value;
                updateStarDisplay(this.dataset.value);
            });
            container.appendChild(star);
        }
    }

    function updateStarDisplay(currentRating) {
        const stars = ratingModalEl.querySelectorAll('#starRatingContainer .fa-star');
        // ... (same as before)
        stars.forEach(star => {
            if (parseInt(star.dataset.value) <= parseInt(currentRating)) {
                star.classList.remove('text-gray-300');
                star.classList.add('text-yellow-400');
            } else {
                star.classList.remove('text-yellow-400');
                star.classList.add('text-gray-300');
            }
        });
    }
    
    // --- Event Handlers ---
    platformLogoLink.addEventListener('click', (e) => {
        e.preventDefault();
        showView(landingView);
    });
    
    document.getElementById('selectExperiencer').addEventListener('click', () => {
        currentUser = { type: 'experiencer', ...users.experiencers[0] }; 
        updateNav();
        document.getElementById('filterBar').classList.remove('hidden'); // Show filter bar
        renderAvailableExperiences();
        populateFilterDropdowns();
        showView(experienceCenterView);
    });

    document.getElementById('selectHost').addEventListener('click', () => { 
        currentUser = { type: 'host', ...users.hosts[0] }; 
        updateNav();
        renderMyPostedExperiences(); // This will hide filterBar internally
        showView(experienceCenterView);
    });
    
    logoutButton.addEventListener('click', () => {
        currentUser = null;
        updateNav();
        showView(landingView);
    });
    
    // Landing page section links
    document.getElementById('preview-experience-center').addEventListener('click', () => {
        document.getElementById('filterBar').classList.remove('hidden'); // Make sure filter bar is visible for visitors
        renderAvailableExperiences(); // Show all experiences initially
        populateFilterDropdowns();
        showView(experienceCenterView);
    });
    document.getElementById('preview-blog').addEventListener('click', () => showView(blogView));
    document.getElementById('preview-contact-us').addEventListener('click', () => showView(contactUsView));
    
    // Visitor Nav links
    document.getElementById('nav-visitor-experience-center').addEventListener('click', () => {
        document.getElementById('filterBar').classList.remove('hidden');
        renderAvailableExperiences();
        populateFilterDropdowns();
        showView(experienceCenterView);
    });
    document.getElementById('nav-visitor-blog').addEventListener('click', () => showView(blogView));
    document.getElementById('nav-visitor-contact').addEventListener('click', () => showView(contactUsView));


    // Back to home buttons from blog/contact
    document.getElementById('backToHomeFromBlog').addEventListener('click', () => showView(landingView));
    document.getElementById('backToHomeFromContact').addEventListener('click', () => showView(landingView));


    navButtons.experienceCenter.addEventListener('click', () => {
        if (!currentUser) return;
        if (currentUser.type === 'experiencer') {
            document.getElementById('filterBar').classList.remove('hidden');
            renderAvailableExperiences();
            populateFilterDropdowns();
        } else { 
            renderMyPostedExperiences(); // Hides filter bar
        }
        showView(experienceCenterView);
    });
    navButtons.profile.addEventListener('click', () => renderProfile());
    navButtons.settings.addEventListener('click', () => {
        // Ensure settings view content is loaded
        settingsView.innerHTML = document.getElementById('settingsViewTemplate').innerHTML;
        // Re-attach AI button listeners
        settingsView.querySelector('#generateBioButton').addEventListener('click', handleGenerateBio);
        settingsView.querySelector('#applyGeneratedBioButton').addEventListener('click', handleApplyGeneratedBio);

        settingsView.querySelector('#settingsGeneratedBio').value = '';
        settingsView.querySelector('#settingsBioKeywords').value = '';
        settingsView.querySelector('#applyGeneratedBioButton').classList.add('hidden');
        showView(settingsView);
    });
    
    // Handler for the AI button in postExperienceView (needs to be attached when form is shown)
    function handleGenerateExpDescription() {
        const title = postExperienceView.querySelector('#expTitle').value.trim();
        const keywords = postExperienceView.querySelector('#expKeywords').value.trim();
        const descriptionTextarea = postExperienceView.querySelector('#expDescription');
        const spinner = postExperienceView.querySelector('#generateExpDescriptionSpinner');
        const button = this; // 'this' refers to the button clicked

        if (!title) {
            showMessage("عنوان خالی", "لطفا ابتدا عنوان تجربه را وارد کنید.", 'fas fa-exclamation-circle text-orange-500');
            return;
        }
        let prompt = `یک توضیح کامل و جذاب برای یک فرصت تجربه‌محور با عنوان «${title}» بنویس. `;
        if (keywords) { prompt += `این تجربه شامل فعالیت‌هایی مانند ${keywords} است. `; }
        prompt += `توضیحات باید شامل وظایف اصلی، محیط و حال و هوای تجربه باشد و افراد علاقه‌مند را به شرکت در آن ترغیب کند. متن تولید شده باید حداقل ۷۰ کلمه باشد و به زبان فارسی روان نوشته شود.`;
        
        generateTextWithGemini(prompt, spinner, button).then(generatedDescription => {
            if (generatedDescription) {
                descriptionTextarea.value = generatedDescription;
                showMessage("توضیحات تولید شد", "توضیحات پیشنهادی در کادر مربوطه قرار گرفت.", 'fas fa-magic text-purple-500');
            }
        });
    }
    
    // Post Experience Form related (needs to be handled when form is visible)
    function setupPostExperienceForm() {
        const form = document.getElementById('postExperienceForm');
        if(form) { // Check if form exists in the current view
            form.onsubmit = function(e) {
                e.preventDefault();
                if (!currentUser || currentUser.type !== 'host') return;

                const newExp = {
                    id: Date.now(), hostId: currentUser.id, hostName: currentUser.name,
                    title: e.target.expTitle.value, location: e.target.expLocation.value,
                    description: e.target.expDescription.value, offerings: e.target.expOfferings.value,
                    duration: e.target.expDuration.value, postedDate: new Date().toLocaleDateString('fa-IR'),
                    applicants: [], reviews: [], status: "open",
                    // Add new fields from form if they exist (province, city, type - though not in this form yet)
                    province: e.target.expLocation.value.includes("تهران") ? "تهران" : "نامشخص", // Mock logic
                    city: e.target.expLocation.value.split("،")[1]?.trim() || e.target.expLocation.value, // Mock logic
                    experienceType: "عمومی" // Mock logic
                };
                experiences.unshift(newExp); 
                users.hosts.find(h => h.id === currentUser.id).experiencesPostedIds.push(newExp.id);
                
                renderMyPostedExperiences(); 
                showView(experienceCenterView);
                showMessage("موفقیت!", "تجربه شما با موفقیت ثبت شد.", 'fas fa-check-circle text-green-500');
            };
            form.querySelector('#cancelPostExperience').onclick = () => {
                renderMyPostedExperiences();
                showView(experienceCenterView);
            };
        }
    }
    
    // Attach listeners when postExperienceView becomes visible (e.g., inside showPostExperienceFormButton click)
    // This is now handled by re-injecting the form content and re-attaching listeners.
    // The main form submission and cancel are now part of the template injection logic.

    function handleApplyForExperience() {
        // This function is attached to the apply button in the experience detail modal
        if (!currentUser) { // Visitor trying to apply
             closeModal('experienceDetailModal');
             showMessage("ورود لازم است", "برای ارسال درخواست، لطفا ابتدا وارد حساب کاربری خود شوید یا یک حساب بسازید.", 'fas fa-user-lock text-orange-500');
             // Optionally, scroll to role selection
             setTimeout(() => {
                showView(landingView);
                document.getElementById('roleSelectionSection').scrollIntoView({ behavior: 'smooth' });
             }, 500);
             return;
        }

        if (currentUser.type !== 'experiencer' || !currentViewingExperienceId) return;

        const exp = experiences.find(e => e.id === currentViewingExperienceId);
        const user = users.experiencers.find(u => u.id === currentUser.id);

        if (exp && user && !exp.applicants.includes(user.id) && !user.applications.includes(exp.id)) {
            exp.applicants.push(user.id);
            user.applications.push(exp.id); 
            showMessage("درخواست ارسال شد!", `درخواست شما برای تجربه "${exp.title}" ارسال شد.`, 'fas fa-paper-plane text-blue-500');
            closeModal('experienceDetailModal');
        } else {
            showMessage("خطا", "شما قبلا درخواست داده‌اید یا مشکلی رخ داده.", 'fas fa-exclamation-triangle text-red-500');
        }
    }
    
    function handleOpenRateModal() {
        // This function is attached to the openRateModalButton in the profile view
        const selectedItemJSON = profileView.querySelector('#rateableItemsDropdown').value;
        if (!selectedItemJSON) {
            showMessage("انتخاب مورد", "لطفا یک مورد را برای امتیازدهی انتخاب کنید.", 'fas fa-hand-pointer text-orange-500');
            return;
        }
        currentRatingTarget = JSON.parse(selectedItemJSON);
        
        // Ensure rating modal content is loaded
        ratingModalEl.innerHTML = document.getElementById('ratingModalTemplate').innerHTML;
        ratingModalEl.querySelector('.close-button').onclick = () => closeModal('ratingModal');
        ratingModalEl.querySelector('#ratingForm').onsubmit = handleRatingFormSubmit;


        setupStarRating(); 
        updateStarDisplay(0); 

        const ratingModalTitleEl = ratingModalEl.querySelector('#ratingModalTitle');
        const ratingGuidanceEl = ratingModalEl.querySelector('#ratingGuidance');

        // ... (logic for setting title and guidance remains the same) ...
         if (currentRatingTarget.type === 'host') {
            ratingModalTitleEl.textContent = `امتیازدهی به تجربه‌فرما: ${currentRatingTarget.name.split('(برای تجربه:')[0].trim()}`;
            ratingGuidanceEl.textContent = "به مواردی مانند مهمان‌نوازی، شرایط اقامت و غذا، و تجربه کلی خود امتیاز دهید.";
        } else if (currentRatingTarget.type === 'experiencer') {
            ratingModalTitleEl.textContent = `امتیازدهی به تجربه‌گر: ${currentRatingTarget.name.split('(برای تجربه:')[0].trim()}`;
            ratingGuidanceEl.textContent = "ملاک رضایت بیش‌تر از کیفیت انجام کار، روی تعهد و رفتار مناسب است.";
        } else if (currentRatingTarget.type === 'experience') {
            ratingModalTitleEl.textContent = `امتیازدهی به تجربه: ${currentRatingTarget.name.split('(ارائه شده توسط:')[0].trim()}`;
            ratingGuidanceEl.textContent = "به کیفیت کلی تجربه، تطابق با توضیحات و ارزشی که برای شما داشته، امتیاز دهید.";
        }
        openModal('ratingModal');
    }
    
    function handleRatingFormSubmit(e) {
        e.preventDefault();
        const ratingValue = parseInt(ratingModalEl.querySelector('#ratingValue').value);
        const comment = ratingModalEl.querySelector('#ratingComment').value;

        if (ratingValue === 0) {
            showMessage("امتیاز ناقص", "لطفا امتیاز را (۱ تا ۵ ستاره) انتخاب کنید.", 'fas fa-star-half-alt text-yellow-500');
            return;
        }
        if (!comment.trim() || comment.trim().length < 10) {
            showMessage("نظر کوتاه", "لطفا نظر خود را با حداقل ۱۰ کاراکتر بنویسید.", 'fas fa-comment-dots text-orange-500');
            return;
        }

        // ... (rest of the rating submission logic remains the same) ...
        if (!currentUser || !currentRatingTarget) return;

        const newRating = {
            fromId: currentUser.id, fromName: currentUser.name, toId: currentRatingTarget.id,
            toName: currentRatingTarget.name, rating: ratingValue, comment: comment,
            type: `${currentUser.type}_to_${currentRatingTarget.type}`
        };
        
        if (currentUser.type === 'experiencer') {
            users.experiencers.find(u => u.id === currentUser.id).ratingsGiven.push(newRating);
        } else { 
            users.hosts.find(u => u.id === currentUser.id).ratingsGiven.push(newRating);
        }

        if (currentRatingTarget.type === 'experiencer') {
            users.experiencers.find(u => u.id === currentRatingTarget.id).ratingsReceived.push(newRating);
        } else if (currentRatingTarget.type === 'host') {
            users.hosts.find(u => u.id === currentRatingTarget.id).ratingsReceived.push(newRating);
        } else if (currentRatingTarget.type === 'experience') {
             const exp = experiences.find(ex => ex.id === currentRatingTarget.id);
             if(exp) exp.reviews.push({experiencerId: currentUser.id, experiencerName: currentUser.name, rating: ratingValue, comment: comment});
        }

        showMessage("ثبت شد!", "امتیاز و نظر شما با موفقیت ثبت گردید.", 'fas fa-check-circle text-green-500');
        closeModal('ratingModal');
        renderProfile(); 
    }


    // --- AI Feature Event Handlers (need to be attached when settingsView is shown) ---
    function handleGenerateBio() {
        const keywords = settingsView.querySelector('#settingsBioKeywords').value.trim();
        const spinner = settingsView.querySelector('#generateBioSpinner');
        const button = this; // 'this' is the button clicked
        const generatedBioTextarea = settingsView.querySelector('#settingsGeneratedBio');
        const applyButton = settingsView.querySelector('#applyGeneratedBioButton');


        if (!keywords) {
            showMessage("کلمات کلیدی خالی", "لطفا کلمات کلیدی برای بیوگرافی وارد کنید.", 'fas fa-exclamation-circle text-orange-500');
            return;
        }
        const userRole = currentUser.type === 'experiencer' ? 'تجربه‌گرا' : 'تجربه‌فرما';
        let prompt = `یک بیوگرافی کوتاه (حدود ۵۰ تا ۷۰ کلمه) و جذاب برای پروفایل یک فرد ${userRole} در پلتفرم «experience.ir» بنویس. `;
        prompt += `این فرد دارای این مشخصات است: «${keywords}». `;
        prompt += `بیوگرافی باید حس کنجکاوی و همکاری را منتقل کند و به زبان فارسی روان و صمیمی باشد.`;

        generateTextWithGemini(prompt, spinner, button).then(generatedBio => {
            if (generatedBio) {
                generatedBioTextarea.value = generatedBio;
                applyButton.classList.remove('hidden');
                showMessage("بیوگرافی تولید شد", "بیوگرافی پیشنهادی تولید شد. می‌توانید آن را اعمال کنید.", 'fas fa-user-edit text-purple-500');
            }
        });
    }

    function handleApplyGeneratedBio() {
        const newBio = settingsView.querySelector('#settingsGeneratedBio').value;
        const applyButton = this; // 'this' is the button clicked

        if (newBio && currentUser) {
            // ... (logic to update user's bio remains the same) ...
            if (currentUser.type === 'experiencer') {
                const user = users.experiencers.find(u => u.id === currentUser.id);
                if (user) user.bio = newBio;
            } else { 
                const user = users.hosts.find(u => u.id === currentUser.id);
                if (user) user.bio = newBio;
            }
            currentUser.bio = newBio; 
            showMessage("بیوگرافی اعمال شد", "بیوگرافی جدید در پروفایل شما ذخیره شد.", 'fas fa-check-circle text-green-500');
            applyButton.classList.add('hidden');
            if (!profileView.classList.contains('hidden')) {
                renderProfile();
            }
        }
    }
    
    // --- Filter and Search Logic ---
    applyFiltersButton.addEventListener('click', () => {
        currentFilters.province = filterProvinceSelect.value;
        currentFilters.city = filterCitySelect.value;
        currentFilters.duration = filterDurationInput.value.trim().toLowerCase();
        currentFilters.experienceType = filterExperienceTypeSelect.value;
        currentFilters.search = searchInput.value.trim().toLowerCase();
        
        let filtered = experiences.filter(exp => {
            const searchMatch = currentFilters.search === '' ||
                exp.title.toLowerCase().includes(currentFilters.search) ||
                exp.description.toLowerCase().includes(currentFilters.search) ||
                exp.location.toLowerCase().includes(currentFilters.search) ||
                exp.hostName.toLowerCase().includes(currentFilters.search) ||
                exp.experienceType.toLowerCase().includes(currentFilters.search);

            const provinceMatch = currentFilters.province === '' || exp.province === currentFilters.province;
            const cityMatch = currentFilters.city === '' || exp.city === currentFilters.city;
            const durationMatch = currentFilters.duration === '' || exp.duration.toLowerCase().includes(currentFilters.duration);
            const typeMatch = currentFilters.experienceType === '' || exp.experienceType === currentFilters.experienceType;

            return searchMatch && provinceMatch && cityMatch && durationMatch && typeMatch;
        });
        renderAvailableExperiences(filtered);
    });

    clearFiltersButton.addEventListener('click', () => {
        filterProvinceSelect.value = '';
        filterCitySelect.value = '';
        filterDurationInput.value = '';
        filterExperienceTypeSelect.value = '';
        searchInput.value = '';
        currentFilters = { province: '', city: '', duration: '', experienceType: '', search: '' };
        renderAvailableExperiences(experiences); // Show all
    });


    // --- Initial Setup ---
    // Store initial HTML content of views that are dynamically filled
    const viewTemplates = {
        postExperienceView: document.getElementById('postExperienceView').innerHTML,
        profileView: document.getElementById('profileView').innerHTML,
        settingsView: document.getElementById('settingsView').innerHTML,
        experienceDetailModal: document.getElementById('experienceDetailModal').innerHTML,
        ratingModal: document.getElementById('ratingModal').innerHTML,
        messageModal: document.getElementById('messageModal').innerHTML,
    };

    // Function to restore a view from its template
    function restoreViewContent(viewId) {
        const viewElement = document.getElementById(viewId);
        if (viewElement && viewTemplates[viewId]) {
            viewElement.innerHTML = viewTemplates[viewId];
        }
    }
    
    // Modify showView to restore content before showing, for views that need it
    const originalShowView = showView; // Keep a reference to the original
    showView = function(viewElement) {
        // Restore content for views that are heavily manipulated or have forms/modals inside
        if (viewElement.id === 'postExperienceView') restoreViewContent('postExperienceView');
        if (viewElement.id === 'profileView') restoreViewContent('profileView');
        if (viewElement.id === 'settingsView') restoreViewContent('settingsView');
        // Modals are handled slightly differently as their content is injected on demand
        
        originalShowView(viewElement); // Call the original showView logic

        // After showing, re-attach specific event listeners if necessary
        if (viewElement.id === 'postExperienceView') {
            postExperienceView.querySelector('#generateExpDescriptionButton').addEventListener('click', handleGenerateExpDescription);
            setupPostExperienceForm();
        }
        if (viewElement.id === 'settingsView') {
            settingsView.querySelector('#generateBioButton').addEventListener('click', handleGenerateBio);
            settingsView.querySelector('#applyGeneratedBioButton').addEventListener('click', handleApplyGeneratedBio);
        }
    };


    // Initial call
    showView(landingView); 
    updateNav();
    populateFilterDropdowns(); // Populate once at the start

    // Store templates for modals (since their content is dynamic)
    document.body.insertAdjacentHTML('beforeend', `<template id="experienceDetailModalTemplate">${experienceDetailModalEl.innerHTML}</template>`);
    document.body.insertAdjacentHTML('beforeend', `<template id="ratingModalTemplate">${ratingModalEl.innerHTML}</template>`);
    document.body.insertAdjacentHTML('beforeend', `<template id="postExperienceViewTemplate">${postExperienceView.innerHTML}</template>`);
    document.body.insertAdjacentHTML('beforeend', `<template id="profileViewTemplate">${profileView.innerHTML}</template>`);
    document.body.insertAdjacentHTML('beforeend', `<template id="settingsViewTemplate">${settingsView.innerHTML}</template>`);


    // Clear the initial content of dynamic views as they will be filled from templates
    postExperienceView.innerHTML = '';
    profileView.innerHTML = '';
    settingsView.innerHTML = '';
    experienceDetailModalEl.innerHTML = '';
    ratingModalEl.innerHTML = '';


    window.onclick = function(event) {
        if (event.target == experienceDetailModalEl) closeModal('experienceDetailModal');
        if (event.target == ratingModalEl) closeModal('ratingModal');
        if (event.target == messageModalEl) closeModal('messageModal');
    }

</script>

</body>
</html>
