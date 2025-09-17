<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>نظام تسجيل الأفكار والملاحظات - الإصدار المبدع</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700;900&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #6a11cb;
            --secondary: #2575fc;
            --accent: #ff4e50;
            --dark: #1e1e2e;
            --light: #f8f9fa;
            --gray: #6c757d;
            --success: #28a745;
            --warning: #ffc107;
            --danger: #dc3545;
            --radius: 16px;
            --shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
            --transition: all 0.3s ease;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Cairo', sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: #333;
            min-height: 100vh;
            padding: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
            overflow-x: hidden;
        }
        
        .container {
            width: 100%;
            max-width: 1600px;
            margin: 0 auto;
        }
        
        header {
            text-align: center;
            margin-bottom: 30px;
            color: white;
            padding: 20px;
            width: 100%;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: var(--radius);
            border: 1px solid rgba(255, 255, 255, 0.2);
            position: relative;
            overflow: hidden;
        }
        
        header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, rgba(255,255,255,0) 60%);
            transform: rotate(30deg);
        }
        
        h1 {
            font-size: 2.5rem;
            margin-bottom: 15px;
            text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.3);
            font-weight: 900;
            background: linear-gradient(to right, #fff, #e0e0e0);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            position: relative;
            display: inline-block;
        }
        
        h1::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 100%;
            height: 4px;
            background: linear-gradient(to right, var(--accent), var(--primary));
            border-radius: 2px;
        }
        
        .description {
            font-size: 1.2rem;
            max-width: 1000px;
            margin: 0 auto;
            color: rgba(255, 255, 255, 0.9);
        }
        
        .content {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
            width: 100%;
        }
        
        .form-section {
            flex: 1;
            min-width: 300px;
            background: rgba(255, 255, 255, 0.95);
            border-radius: var(--radius);
            padding: 25px;
            box-shadow: var(--shadow);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.3);
            position: relative;
            overflow: hidden;
        }
        
        .form-section::before {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(to left, var(--primary), var(--secondary));
        }
        
        .records-section {
            flex: 2;
            min-width: 300px;
            background: rgba(255, 255, 255, 0.95);
            border-radius: var(--radius);
            padding: 25px;
            box-shadow: var(--shadow);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.3);
            max-height: 70vh;
            overflow-y: auto;
            position: relative;
        }
        
        .records-section::before {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(to left, var(--accent), var(--warning));
        }
        
        h2 {
            color: var(--primary);
            margin-bottom: 20px;
            padding-bottom: 15px;
            border-bottom: 2px solid #eee;
            text-align: center;
            font-size: 1.8rem;
            font-weight: 700;
            position: relative;
        }
        
        h2::after {
            content: '';
            position: absolute;
            bottom: -2px;
            right: 0;
            width: 60px;
            height: 4px;
            background: var(--primary);
            border-radius: 2px;
        }
        
        .form-group {
            margin-bottom: 20px;
            position: relative;
        }
        
        label {
            display: block;
            margin-bottom: 10px;
            font-weight: 600;
            color: #555;
            font-size: 1.1rem;
        }
        
        select, textarea, input[type="text"], input[type="date"], input[type="file"], input[type="password"] {
            width: 100%;
            padding: 15px;
            border: 2px solid #ddd;
            border-radius: 12px;
            font-size: 1rem;
            transition: var(--transition);
            background: rgba(255, 255, 255, 0.9);
        }
        
        select:focus, textarea:focus, input:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 4px rgba(106, 17, 203, 0.2);
            transform: translateY(-2px);
        }
        
        textarea {
            min-height: 150px;
            resize: vertical;
        }
        
        button {
            background: linear-gradient(to right, var(--primary), var(--secondary));
            color: white;
            border: none;
            padding: 16px 20px;
            border-radius: 12px;
            cursor: pointer;
            font-size: 1.1rem;
            font-weight: 600;
            width: 100%;
            transition: var(--transition);
            box-shadow: 0 8px 16px rgba(106, 17, 203, 0.3);
            position: relative;
            overflow: hidden;
        }
        
        button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: 0.5s;
        }
        
        button:hover::before {
            left: 100%;
        }
        
        button:hover {
            transform: translateY(-5px);
            box-shadow: 0 12px 24px rgba(106, 17, 203, 0.4);
        }
        
        button:active {
            transform: translateY(0);
        }
        
        .record-card {
            background: linear-gradient(to bottom right, #fff, #f8f9fa);
            border-radius: var(--radius);
            padding: 20px;
            margin-bottom: 20px;
            box-shadow: var(--shadow);
            border-left: 6px solid var(--primary);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }
        
        .record-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(106, 17, 203, 0.03) 0%, rgba(37, 117, 252, 0.03) 100%);
            z-index: 0;
        }
        
        .record-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
        }
        
        .record-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 15px;
            align-items: flex-start;
            position: relative;
            z-index: 1;
        }
        
        .employee-info {
            display: flex;
            align-items: center;
            gap: 12px;
        }
        
        .employee-avatar {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            object-fit: cover;
            border: 3px solid var(--primary);
            cursor: pointer;
            transition: var(--transition);
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }
        
        .employee-avatar:hover {
            transform: scale(1.1);
            border-color: var(--secondary);
        }
        
        .employee-details {
            display: flex;
            flex-direction: column;
        }
        
        .employee-name {
            font-weight: bold;
            color: var(--primary);
            font-size: 1.2rem;
            margin-bottom: 5px;
        }
        
        .record-date {
            color: var(--gray);
            font-size: 0.9rem;
        }
        
        .record-content {
            color: #555;
            line-height: 1.7;
            font-size: 1rem;
            margin: 15px 0;
            padding: 15px;
            background: rgba(106, 17, 203, 0.05);
            border-radius: 12px;
            border-right: 3px solid var(--primary);
            position: relative;
            z-index: 1;
        }
        
        .blurred {
            filter: blur(8px);
            user-select: none;
            pointer-events: none;
        }
        
        .protected-content {
            position: relative;
        }
        
        .protected-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            border-radius: 12px;
            color: white;
            cursor: pointer;
            z-index: 10;
        }
        
        .protected-overlay i {
            font-size: 2rem;
            margin-bottom: 10px;
        }
        
        .protected-overlay span {
            font-size: 1rem;
            text-align: center;
            max-width: 80%;
        }
        
        .record-media {
            margin-top: 15px;
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            position: relative;
            z-index: 1;
        }
        
        .media-item {
            width: 120px;
            height: 120px;
            border-radius: 12px;
            overflow: hidden;
            cursor: pointer;
            position: relative;
            transition: var(--transition);
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.1);
        }
        
        .media-item:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
        }
        
        .media-item img, .media-item video {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .media-type-icon {
            position: absolute;
            bottom: 8px;
            right: 8px;
            background: rgba(0, 0, 0, 0.7);
            color: white;
            border-radius: 50%;
            width: 28px;
            height: 28px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1rem;
        }
        
        .filters {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin-bottom: 20px;
        }
        
        .filter-group {
            flex: 1;
            min-width: 200px;
        }
        
        .search-box {
            margin-bottom: 20px;
            position: relative;
        }
        
        .search-box input {
            width: 100%;
            padding: 15px 50px 15px 15px;
            border: 2px solid #ddd;
            border-radius: 12px;
            font-size: 1rem;
        }
        
        .search-box i {
            position: absolute;
            right: 15px;
            top: 50%;
            transform: translateY(-50%);
            color: var(--gray);
            font-size: 1.2rem;
        }
        
        .filter-actions {
            display: flex;
            gap: 12px;
            margin-top: 10px;
            flex-wrap: wrap;
        }
        
        .filter-actions button {
            padding: 10px 16px;
            font-size: 1rem;
        }
        
        .btn-secondary {
            background: linear-gradient(to right, var(--gray), #868e96);
        }
        
        .access-panel {
            background: rgba(255, 255, 255, 0.95);
            border-radius: var(--radius);
            padding: 20px;
            margin-top: 25px;
            box-shadow: var(--shadow);
            text-align: center;
            width: 100%;
        }
        
        .access-form {
            display: flex;
            gap: 12px;
            justify-content: center;
            align-items: center;
            flex-wrap: wrap;
        }
        
        .access-form input {
            flex: 1;
            min-width: 200px;
        }
        
        .access-form button {
            width: auto;
        }
        
        /* Modal styles */
        .modal {
            display: none;
            position: fixed;
            z-index: 10000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.95);
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            visibility: hidden;
            transition: opacity 0.4s, visibility 0.4s;
            padding: 20px;
        }
        
        .modal.active {
            opacity: 1;
            visibility: visible;
        }
        
        .modal-content {
            max-width: 90%;
            max-height: 90%;
            position: relative;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.5);
        }
        
        .modal-content img, .modal-content video {
            max-width: 100%;
            max-height: 80vh;
            display: block;
            margin: 0 auto;
        }
        
        .close-modal {
            position: absolute;
            top: 20px;
            right: 20px;
            color: white;
            font-size: 35px;
            cursor: pointer;
            background: rgba(0, 0, 0, 0.7);
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
            z-index: 10001;
        }
        
        .close-modal:hover {
            transform: rotate(90deg) scale(1.1);
            background: rgba(255, 0, 0, 0.7);
        }
        
        .no-records {
            text-align: center;
            padding: 30px;
            font-size: 1.2rem;
            color: var(--gray);
            background: rgba(255, 255, 255, 0.7);
            border-radius: var(--radius);
            margin: 15px 0;
        }
        
        .stats {
            display: flex;
            gap: 15px;
            margin-top: 15px;
            flex-wrap: wrap;
            justify-content: center;
        }
        
        .stat-box {
            flex: 1;
            min-width: 150px;
            background: rgba(255, 255, 255, 0.9);
            padding: 15px;
            border-radius: var(--radius);
            text-align: center;
            box-shadow: var(--shadow);
        }
        
        .stat-value {
            font-size: 2rem;
            font-weight: 700;
            color: var(--primary);
            margin: 8px 0;
        }
        
        .stat-label {
            font-size: 1rem;
            color: var(--gray);
        }
        
        .access-modal {
            display: none;
            position: fixed;
            z-index: 10002;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.8);
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            visibility: hidden;
            transition: opacity 0.4s, visibility 0.4s;
            padding: 20px;
        }
        
        .access-modal.active {
            opacity: 1;
            visibility: visible;
        }
        
        .access-modal-content {
            background: white;
            padding: 30px;
            border-radius: var(--radius);
            width: 90%;
            max-width: 400px;
            text-align: center;
            box-shadow: var(--shadow);
        }
        
        .access-modal h3 {
            color: var(--primary);
            margin-bottom: 15px;
            font-size: 1.5rem;
        }
        
        .access-modal-input {
            display: flex;
            flex-direction: column;
            gap: 12px;
            margin: 20px 0;
        }
        
        .access-modal-input input {
            width: 100%;
        }
        
        .access-modal-input button {
            width: 100%;
        }
        
        /* Floating action button */
        .fab {
            position: fixed;
            bottom: 20px;
            left: 20px;
            width: 60px;
            height: 60px;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 6px 15px rgba(0, 0, 0, 0.3);
            cursor: pointer;
            z-index: 1000;
            transition: var(--transition);
        }
        
        .fab:hover {
            transform: scale(1.1) rotate(90deg);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.4);
        }
        
        /* Responsive adjustments */
        @media (max-width: 1200px) {
            h1 {
                font-size: 2.2rem;
            }
            
            .description {
                font-size: 1.1rem;
            }
        }
        
        @media (max-width: 992px) {
            .content {
                flex-direction: column;
            }
            
            .form-section, .records-section {
                width: 100%;
            }
            
            .records-section {
                max-height: none;
            }
            
            h1 {
                font-size: 2rem;
            }
        }
        
        @media (max-width: 768px) {
            body {
                padding: 15px;
            }
            
            header {
                padding: 15px;
            }
            
            h1 {
                font-size: 1.8rem;
            }
            
            .description {
                font-size: 1rem;
            }
            
            .form-section, .records-section {
                padding: 20px;
            }
            
            .record-header {
                flex-direction: column;
            }
            
            .employee-info {
                margin-bottom: 10px;
            }
            
            .filters {
                flex-direction: column;
            }
            
            .filter-group {
                min-width: 100%;
            }
            
            .access-form {
                flex-direction: column;
            }
            
            .access-form input {
                width: 100%;
            }
            
            .stat-box {
                min-width: 120px;
            }
            
            .stat-value {
                font-size: 1.7rem;
            }
        }
        
        @media (max-width: 576px) {
            h1 {
                font-size: 1.6rem;
            }
            
            h2 {
                font-size: 1.5rem;
            }
            
            .employee-avatar {
                width: 50px;
                height: 50px;
            }
            
            .employee-name {
                font-size: 1.1rem;
            }
            
            .media-item {
                width: 100px;
                height: 100px;
            }
            
            .filter-actions {
                flex-direction: column;
            }
            
            .filter-actions button {
                width: 100%;
            }
            
            .fab {
                bottom: 15px;
                left: 15px;
                width: 50px;
                height: 50px;
            }
        }
        
        /* Animation for new records */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .record-card {
            animation: fadeIn 0.5s ease-out;
        }
        
        /* Custom scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        
        ::-webkit-scrollbar-track {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
        }
        
        ::-webkit-scrollbar-thumb {
            background: var(--primary);
            border-radius: 10px;
        }
        
        ::-webkit-scrollbar-thumb:hover {
            background: var(--secondary);
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1><i class="fas fa-lightbulb"></i> نظام تسجيل الأفكار والملاحظات</h1>
            <p class="description">شارك أفكارك وملاحظاتك لتحسين بيئة العمل. جميع المدخلات مسجلة باسمك ومرتبطة بتاريخ الإدخال.</p>
            
            <div class="stats">
                <div class="stat-box">
                    <div class="stat-label">إجمالي الملاحظات</div>
                    <div class="stat-value" id="totalRecords">0</div>
                </div>
                <div class="stat-box">
                    <div class="stat-label">عدد الموظفين</div>
                    <div class="stat-value">8</div>
                </div>
                <div class="stat-box">
                    <div class="stat-label">ملاحظات هذا الشهر</div>
                    <div class="stat-value" id="monthRecords">0</div>
                </div>
            </div>
        </header>
        
        <div class="content">
            <section class="form-section">
                <h2><i class="fas fa-pencil-alt"></i> اضافة فكرة أو ملاحظة جديدة</h2>
                <form id="recordForm">
                    <div class="form-group">
                        <label for="employee">اسم الموظف:</label>
                        <select id="employee" required>
                            <option value="">اختر اسم الموظف</option>
                            <option value="حسن عز">حسن عز</option>
                            <option value="محمد عبدالراضي">محمد عبدالراضي</option>
                            <option value="محمد نصار">محمد نصار</option>
                            <option value="علي">علي</option>
                            <option value="روماني">روماني</option>
                            <option value="علاء">علاء</option>
                            <option value="عبدالرحمن">عبدالرحمن</option>
                            <option value="عصمت">عصمت</option>
                        </select>
                    </div>
                    
                    <div class="form-group">
                        <label for="content">الفكرة أو الملاحظة:</label>
                        <textarea id="content" placeholder="اكتب فكرتك أو ملاحظتك هنا..." required></textarea>
                    </div>
                    
                    <div class="form-group">
                        <label for="media">إضافة صورة أو فيديو (اختياري):</label>
                        <input type="file" id="media" accept="image/*,video/*">
                    </div>
                    
                    <button type="submit"><i class="fas fa-plus-circle"></i> إضافة الملاحظة</button>
                </form>
            </section>
            
            <section class="records-section">
                <h2><i class="fas fa-history"></i> الأفكار والملاحظات المسجلة</h2>
                
                <div class="filters">
                    <div class="filter-group">
                        <label for="searchInput">بحث في النص:</label>
                        <div class="search-box">
                            <input type="text" id="searchInput" placeholder="ابحث في الأفكار والملاحظات...">
                            <i class="fas fa-search"></i>
                        </div>
                    </div>
                    
                    <div class="filter-group">
                        <label for="employeeFilter">تصفية حسب الموظف:</label>
                        <select id="employeeFilter">
                            <option value="">جميع الموظفين</option>
                            <option value="حسن عز">حسن عز</option>
                            <option value="محمد عبدالراضي">محمد عبدالراضي</option>
                            <option value="محمد نصار">محمد نصار</option>
                            <option value="علي">علي</option>
                            <option value="روماني">روماني</option>
                            <option value="علاء">علاء</option>
                            <option value="عبدالرحمن">عبدالرحمن</option>
                            <option value="عصمت">عصمت</option>
                        </select>
                    </div>
                    
                    <div class="filter-group">
                        <label for="dateFilter">تصفية حسب التاريخ:</label>
                        <input type="date" id="dateFilter">
                    </div>
                </div>
                
                <div class="filter-actions">
                    <button type="button" id="applyFilters"><i class="fas fa-filter"></i> تطبيق الفلاتر</button>
                    <button type="button" id="resetFilters" class="btn-secondary"><i class="fas fa-redo"></i> إعادة الضبط</button>
                </div>
                
                <div id="recordsList">
                    <!-- سيتم عرض السجلات هنا -->
                </div>
            </section>
        </div>
        
        <div class="access-panel">
            <h3><i class="fas fa-lock"></i> الوصول إلى المحتوى المحمي</h3>
            <p>لصاحب العمل فقط: أدخل كود الوصول لعرض المحتوى والوسائط:</p>
            <div class="access-form">
                <input type="password" id="accessCode" placeholder="أدخل كود الوصول الخاص بك...">
                <button type="button" id="submitCode"><i class="fas fa-key"></i> فتح المحتوى</button>
            </div>
        </div>
    </div>

    <!-- Modal for media view -->
    <div class="modal" id="mediaModal">
        <span class="close-modal" id="closeModal">&times;</span>
        <div class="modal-content">
            <img id="modalImage" src="" alt="">
            <video id="modalVideo" controls style="display: none;"></video>
        </div>
    </div>

    <!-- Access Modal -->
    <div class="access-modal" id="accessModal">
        <div class="access-modal-content">
            <h3><i class="fas fa-lock"></i> المحتوى محمي</h3>
            <p>يجب إدخال كود الوصول لعرض هذا المحتوى</p>
            <div class="access-modal-input">
                <input type="password" id="modalAccessCode" placeholder="كود الوصول السري">
                <button type="button" id="modalSubmitCode">فتح المحتوى</button>
            </div>
            <button type="button" class="btn-secondary" id="closeAccessModal">إلغاء</button>
        </div>
    </div>

    <!-- Floating action button for mobile -->
    <div class="fab" id="fabButton">
        <i class="fas fa-key"></i>
    </div>

    <script>
        // صور افتراضية للموظفين (يمكن استبدالها بالصور الحقيقية)
        const employeeAvatars = {
            'حسن عز': 'https://randomuser.me/api/portraits/men/32.jpg',
            'محمد عبدالراضي': 'https://randomuser.me/api/portraits/men/22.jpg',
            'محمد نصار': 'https://randomuser.me/api/portraits/men/45.jpg',
            'علي': 'https://randomuser.me/api/portraits/men/67.jpg',
            'روماني': 'https://randomuser.me/api/portraits/men/29.jpg',
            'علاء': 'https://randomuser.me/api/portraits/men/51.jpg',
            'عبدالرحمن': 'https://randomuser.me/api/portraits/men/36.jpg',
            'عصمت': 'https://randomuser.me/api/portraits/men/41.jpg'
        };

        // حالة الوصول إلى المحتوى
        let hasAccess = false;
        const SECRET_CODE = "toys506070";

        document.addEventListener('DOMContentLoaded', function() {
            const recordForm = document.getElementById('recordForm');
            const recordsList = document.getElementById('recordsList');
            const searchInput = document.getElementById('searchInput');
            const employeeFilter = document.getElementById('employeeFilter');
            const dateFilter = document.getElementById('dateFilter');
            const applyFilters = document.getElementById('applyFilters');
            const resetFilters = document.getElementById('resetFilters');
            const mediaInput = document.getElementById('media');
            const mediaModal = document.getElementById('mediaModal');
            const modalImage = document.getElementById('modalImage');
            const modalVideo = document.getElementById('modalVideo');
            const closeModal = document.getElementById('closeModal');
            const totalRecords = document.getElementById('totalRecords');
            const monthRecords = document.getElementById('monthRecords');
            const accessCode = document.getElementById('accessCode');
            const submitCode = document.getElementById('submitCode');
            const accessModal = document.getElementById('accessModal');
            const modalAccessCode = document.getElementById('modalAccessCode');
            const modalSubmitCode = document.getElementById('modalSubmitCode');
            const closeAccessModal = document.getElementById('closeAccessModal');
            const fabButton = document.getElementById('fabButton');
            
            // تحميل السجلات المحفوظة عند بدء التشغيل
            loadRecords();
            updateStats();
            
            // إضافة سجل جديد
            recordForm.addEventListener('submit', function(e) {
                e.preventDefault();
                
                const employee = document.getElementById('employee').value;
                const content = document.getElementById('content').value;
                const mediaFile = mediaInput.files[0];
                
                if (!employee || !content) {
                    alert('يرجى اختيار اسم الموظف وكتابة الفكرة أو الملاحظة');
                    return;
                }
                
                if (mediaFile) {
                    const reader = new FileReader();
                    reader.onload = function(e) {
                        addRecord(employee, content, e.target.result, mediaFile.type);
                    };
                    reader.readAsDataURL(mediaFile);
                } else {
                    addRecord(employee, content);
                }
                
                recordForm.reset();
            });
            
            // تطبيق الفلاتر
            applyFilters.addEventListener('click', function() {
                loadRecords();
            });
            
            // إعادة ضبط الفلاتر
            resetFilters.addEventListener('click', function() {
                searchInput.value = '';
                employeeFilter.value = '';
                dateFilter.value = '';
                loadRecords();
            });
            
            // فتح وإغلاق Modal
            closeModal.addEventListener('click', function() {
                mediaModal.classList.remove('active');
                modalVideo.style.display = 'none';
                modalVideo.pause();
            });
            
            // التحقق من كود الوصول من اللوحة الرئيسية
            submitCode.addEventListener('click', function() {
                if (accessCode.value === SECRET_CODE) {
                    hasAccess = true;
                    alert('تم منح الوصول بنجاح! يمكنك الآن رؤية المحتوى والوسائط.');
                    loadRecords();
                    accessCode.value = '';
                } else {
                    alert('كود الوصول غير صحيح. يرجى المحاولة مرة أخرى.');
                    accessCode.value = '';
                }
            });
            
            // التحقق من كود الوصول من Modal
            modalSubmitCode.addEventListener('click', function() {
                if (modalAccessCode.value === SECRET_CODE) {
                    hasAccess = true;
                    accessModal.classList.remove('active');
                    alert('تم منح الوصول بنجاح! يمكنك الآن رؤية المحتوى والوسائط.');
                    loadRecords();
                    modalAccessCode.value = '';
                } else {
                    alert('كود الوصول غير صحيح. يرجى المحاولة مرة أخرى.');
                    modalAccessCode.value = '';
                }
            });
            
            // إغلاق Modal الوصول
            closeAccessModal.addEventListener('click', function() {
                accessModal.classList.remove('active');
                modalAccessCode.value = '';
            });
            
            // فتح لوحة الوصول من زر الفاب
            fabButton.addEventListener('click', function() {
                accessModal.classList.add('active');
                modalAccessCode.focus();
            });
            
            // دالة لإضافة سجل جديد
            function addRecord(employee, content, mediaData = null, mediaType = null) {
                const records = getRecords();
                const now = new Date();
                const newRecord = {
                    id: Date.now(),
                    employee: employee,
                    content: content,
                    date: now.toLocaleString('ar-EG'),
                    timestamp: now.getTime(),
                    media: mediaData,
                    mediaType: mediaType
                };
                
                records.unshift(newRecord);
                localStorage.setItem('employeeRecords', JSON.stringify(records));
                loadRecords();
                updateStats();
            }
            
            // دالة لتحميل السجلات
            function loadRecords() {
                const records = getRecords();
                const searchTerm = searchInput.value;
                const employeeValue = employeeFilter.value;
                const dateValue = dateFilter.value;
                
                if (records.length === 0) {
                    recordsList.innerHTML = '<p class="no-records">لا توجد أفكار أو ملاحظات مسجلة بعد.</p>';
                    return;
                }
                
                let filteredRecords = records;
                
                // تطبيق فلتر النص
                if (searchTerm) {
                    filteredRecords = filteredRecords.filter(record => 
                        record.content.includes(searchTerm)
                    );
                }
                
                // تطبيق فلتر الموظف
                if (employeeValue) {
                    filteredRecords = filteredRecords.filter(record => 
                        record.employee === employeeValue
                    );
                }
                
                // تطبيق فلتر التاريخ
                if (dateValue) {
                    const selectedDate = new Date(dateValue);
                    filteredRecords = filteredRecords.filter(record => {
                        const recordDate = new Date(record.timestamp);
                        return recordDate.toDateString() === selectedDate.toDateString();
                    });
                }
                
                recordsList.innerHTML = '';
                
                if (filteredRecords.length === 0) {
                    recordsList.innerHTML = '<p class="no-records">لا توجد نتائج تطابق معايير البحث.</p>';
                    return;
                }
                
                filteredRecords.forEach(record => {
                    const recordElement = document.createElement('div');
                    recordElement.classList.add('record-card');
                    
                    let mediaHTML = '';
                    if (record.media) {
                        const isImage = record.mediaType.startsWith('image');
                        if (hasAccess) {
                            mediaHTML = `
                                <div class="record-media">
                                    <div class="media-item" onclick="openMedia('${record.media}', '${record.mediaType}')">
                                        ${isImage ? 
                                            `<img src="${record.media}" alt="Media">` : 
                                            `<video src="${record.media}"></video>`
                                        }
                                        <div class="media-type-icon">
                                            <i class="fas ${isImage ? 'fa-image' : 'fa-video'}"></i>
                                        </div>
                                    </div>
                                </div>
                            `;
                        } else {
                            mediaHTML = `
                                <div class="record-media">
                                    <div class="media-item blurred" onclick="requestAccess()">
                                        ${isImage ? 
                                            `<img src="${record.media}" alt="Media">` : 
                                            `<video src="${record.media}"></video>`
                                        }
                                        <div class="media-type-icon">
                                            <i class="fas ${isImage ? 'fa-image' : 'fa-video'}"></i>
                                        </div>
                                    </div>
                                </div>
                            `;
                        }
                    }
                    
                    const contentHTML = hasAccess ? 
                        `<div class="record-content">${record.content}</div>` :
                        `<div class="record-content protected-content">
                            <div class="blurred">${record.content}</div>
                            <div class="protected-overlay" onclick="requestAccess()">
                                <i class="fas fa-lock"></i>
                                <span>المحتوى محمي. انقر لإدخال كود الوصول</span>
                            </div>
                        </div>`;
                    
                    recordElement.innerHTML = `
                        <div class="record-header">
                            <div class="employee-info">
                                <img class="employee-avatar" src="${employeeAvatars[record.employee]}" alt="${record.employee}">
                                <div class="employee-details">
                                    <span class="employee-name">${record.employee}</span>
                                    <span class="record-date">${record.date}</span>
                                </div>
                            </div>
                        </div>
                        ${contentHTML}
                        ${mediaHTML}
                    `;
                    recordsList.appendChild(recordElement);
                });
            }
            
            // دالة للحصول على السجلات من localStorage
            function getRecords() {
                return JSON.parse(localStorage.getItem('employeeRecords') || '[]');
            }
            
            // دالة لتحديث الإحصائيات
            function updateStats() {
                const records = getRecords();
                const now = new Date();
                const currentMonth = now.getMonth();
                const currentYear = now.getFullYear();
                
                totalRecords.textContent = records.length;
                
                const monthRecordsCount = records.filter(record => {
                    const recordDate = new Date(record.timestamp);
                    return recordDate.getMonth() === currentMonth && recordDate.getFullYear() === currentYear;
                }).length;
                
                monthRecords.textContent = monthRecordsCount;
            }
            
            // دالة لفتح الوسائط في Modal
            window.openMedia = function(mediaSrc, mediaType) {
                if (!hasAccess) {
                    requestAccess();
                    return;
                }
                
                const isImage = mediaType.startsWith('image');
                
                if (isImage) {
                    modalImage.src = mediaSrc;
                    modalImage.style.display = 'block';
                    modalVideo.style.display = 'none';
                } else {
                    modalVideo.src = mediaSrc;
                    modalVideo.style.display = 'block';
                    modalImage.style.display = 'none';
                }
                
                mediaModal.classList.add('active');
            };
            
            // طلب الوصول
            window.requestAccess = function() {
                accessModal.classList.add('active');
                modalAccessCode.focus();
            };
        });
    </script>
</body>
</html>
