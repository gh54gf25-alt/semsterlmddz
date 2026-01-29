# semsterlmddz
حساب معدل جامعي 
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>النظام الشامل لحساب المعدل الجامعي</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #1a237e;
            --secondary: #283593;
            --accent: #3949ab;
            --success: #2e7d32;
            --warning: #ff8f00;
            --danger: #c62828;
            --light: #f5f5f5;
            --dark: #0d1b2a;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Cairo', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #f5f7fa 0%, #e4e9f7 100%);
            color: #333;
            line-height: 1.6;
            min-height: 100vh;
        }
        
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
        }
        
        /* Header */
        .header {
            background: linear-gradient(135deg, var(--primary), var(--accent));
            color: white;
            padding: 25px;
            border-radius: 15px;
            margin-bottom: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            text-align: center;
        }
        
        .header h1 {
            font-size: 2.5rem;
            margin-bottom: 10px;
        }
        
        .header h2 {
            font-size: 1.3rem;
            opacity: 0.9;
            margin-bottom: 15px;
        }
        
        .system-info {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-top: 15px;
            flex-wrap: wrap;
        }
        
        .info-item {
            background: rgba(255,255,255,0.1);
            padding: 8px 15px;
            border-radius: 20px;
            font-size: 0.9rem;
        }
        
        /* Navigation */
        .tabs-container {
            background: white;
            border-radius: 10px;
            margin-bottom: 30px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
        }
        
        .tabs {
            display: flex;
            background: #f8f9fa;
            padding: 0 20px;
            border-bottom: 2px solid #e0e0e0;
        }
        
        .tab {
            padding: 15px 25px;
            cursor: pointer;
            font-weight: 600;
            color: #666;
            border-bottom: 3px solid transparent;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .tab:hover {
            color: var(--accent);
            background: #f0f2ff;
        }
        
        .tab.active {
            color: var(--accent);
            border-bottom: 3px solid var(--accent);
            background: white;
        }
        
        .tab-content {
            padding: 30px;
        }
        
        /* Search and Filter */
        .search-filter {
            background: white;
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 30px;
            box-shadow: 0 3px 10px rgba(0,0,0,0.05);
        }
        
        .filter-row {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            margin-bottom: 15px;
        }
        
        /* Form Controls */
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--dark);
        }
        
        .form-control {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
            background: #f8f9fa;
            transition: all 0.3s;
        }
        
        .form-control:focus {
            border-color: var(--accent);
            box-shadow: 0 0 0 3px rgba(57, 73, 171, 0.1);
            outline: none;
            background: white;
        }
        
        /* Subject Cards */
        .subjects-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }
        
        .subject-card {
            background: white;
            border-radius: 15px;
            padding: 20px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
            transition: transform 0.3s, box-shadow 0.3s;
            border: 1px solid #e0e0e0;
        }
        
        .subject-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.15);
        }
        
        .subject-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 2px solid #f0f0f0;
        }
        
        .subject-title {
            font-size: 1.2rem;
            font-weight: 700;
            color: var(--primary);
        }
        
        .subject-coefficient {
            background: var(--accent);
            color: white;
            padding: 5px 12px;
            border-radius: 20px;
            font-weight: 600;
        }
        
        /* Marks Grid */
        .marks-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
            margin-bottom: 15px;
        }
        
        .mark-item {
            background: #f8f9fa;
            padding: 15px;
            border-radius: 10px;
        }
        
        .mark-label {
            font-weight: 600;
            color: #555;
            margin-bottom: 5px;
            display: flex;
            justify-content: space-between;
        }
        
        .percentage {
            color: var(--accent);
            font-weight: 700;
        }
        
        input[type="number"] {
            width: 100%;
            padding: 8px 12px;
            border: 1px solid #ddd;
            border-radius: 6px;
            font-size: 16px;
            text-align: center;
        }
        
        /* Results Section */
        .results-section {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 30px;
            border-radius: 15px;
            margin-top: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        }
        
        .results-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }
        
        .result-card {
            background: rgba(255,255,255,0.1);
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            backdrop-filter: blur(10px);
        }
        
        .result-value {
            font-size: 2.2rem;
            font-weight: 700;
            margin: 10px 0;
        }
        
        /* Action Buttons */
        .action-buttons {
            display: flex;
            gap: 15px;
            margin-top: 20px;
            flex-wrap: wrap;
        }
        
        .btn {
            padding: 12px 24px;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }
        
        .btn-primary {
            background: var(--accent);
            color: white;
        }
        
        .btn-primary:hover {
            background: var(--secondary);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(57, 73, 171, 0.3);
        }
        
        .btn-success {
            background: var(--success);
            color: white;
        }
        
        .btn-danger {
            background: var(--danger);
            color: white;
        }
        
        .btn-outline {
            background: transparent;
            border: 2px solid var(--accent);
            color: var(--accent);
        }
        
        /* Table */
        .summary-table {
            width: 100%;
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 3px 10px rgba(0,0,0,0.05);
            margin-top: 20px;
        }
        
        .summary-table th {
            background: var(--light);
            padding: 15px;
            font-weight: 700;
            color: var(--dark);
            border-bottom: 2px solid #e0e0e0;
        }
        
        .summary-table td {
            padding: 12px 15px;
            border-bottom: 1px solid #eee;
            text-align: center;
        }
        
        .summary-table tr:hover {
            background: #f9f9f9;
        }
        
        /* Footer */
        .footer {
            text-align: center;
            padding: 30px;
            margin-top: 50px;
            color: #666;
            background: white;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }
        
        /* Animation */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .fade-in {
            animation: fadeIn 0.5s ease;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .container {
                padding: 10px;
            }
            
            .header h1 {
                font-size: 1.8rem;
            }
            
            .tabs {
                flex-direction: column;
            }
            
            .tab {
                justify-content: center;
            }
            
            .subjects-container {
                grid-template-columns: 1fr;
            }
            
            .marks-grid {
                grid-template-columns: 1fr;
            }
            
            .results-grid {
                grid-template-columns: 1fr;
            }
            
            .filter-row {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header -->
        <div class="header">
            <h1><i class="fas fa-university"></i> النظام الشامل لحساب المعدل الجامعي</h1>
            <h2>حاسبة متكاملة لجميع التخصصات والمستويات مع TD و TP والمعاملات</h2>
            <div class="system-info">
                <div class="info-item">نظام LMD</div>
                <div class="info-item">نظام الكلاسيكي</div>
                <div class="info-item">TD / TP</div>
                <div class="info-item">المعاملات الموزونة</div>
            </div>
        </div>
        
        <!-- Navigation -->
        <div class="tabs-container">
            <div class="tabs">
                <div class="tab active" onclick="switchTab('calculator')">
                    <i class="fas fa-calculator"></i> حاسبة المعدل
                </div>
                <div class="tab" onclick="switchTab('subjects')">
                    <i class="fas fa-book"></i> إدارة المواد
                </div>
                <div class="tab" onclick="switchTab('settings')">
                    <i class="fas fa-cog"></i> الإعدادات
                </div>
                <div class="tab" onclick="switchTab('results')">
                    <i class="fas fa-chart-bar"></i> النتائج
                </div>
            </div>
            
            <!-- Calculator Tab -->
            <div id="calculator" class="tab-content active">
                <div class="search-filter">
                    <div class="filter-row">
                        <div class="form-group">
                            <label><i class="fas fa-graduation-cap"></i> التخصص</label>
                            <select id="specialization" class="form-control" onchange="loadSubjects()">
                                <option value="">اختر التخصص</option>
                                <option value="mathematics">الرياضيات</option>
                                <option value="physics">الفيزياء</option>
                                <option value="chemistry">الكيمياء</option>
                                <option value="engineering">الهندسة</option>
                                <option value="computer">الإعلام الآلي</option>
                                <option value="biology">علوم الطبيعة والحياة</option>
                                <option value="medicine">الطب</option>
                                <option value="law">القانون</option>
                                <option value="economy">الاقتصاد</option>
                                <option value="other">أخرى</option>
                            </select>
                        </div>
                        
                        <div class="form-group">
                            <label><i class="fas fa-layer-group"></i> المستوى</label>
                            <select id="level" class="form-control" onchange="loadSubjects()">
                                <option value="">اختر المستوى</option>
                                <option value="s1">السداسي الأول</option>
                                <option value="s2">السداسي الثاني</option>
                                <option value="s3">السداسي الثالث</option>
                                <option value="s4">السداسي الرابع</option>
                                <option value="s5">السداسي الخامس</option>
                                <option value="s6">السداسي السادس</option>
                                <option value="l1">السنة الأولى</option>
                                <option value="l2">السنة الثانية</option>
                                <option value="l3">السنة الثالثة</option>
                                <option value="m1">ماستر 1</option>
                                <option value="m2">ماستر 2</option>
                            </select>
                        </div>
                        
                        <div class="form-group">
                            <label><i class="fas fa-balance-scale"></i> نظام التقييم</label>
                            <select id="gradingSystem" class="form-control">
                                <option value="lmd">نظام LMD</option>
                                <option value="classic">نظام كلاسيكي</option>
                                <option value="credit">نظام الساعات المعتمدة</option>
                            </select>
                        </div>
                    </div>
                </div>
                
                <div id="subjectsContainer" class="subjects-container">
                    <!-- Subjects will be loaded here -->
                </div>
                
                <div class="action-buttons">
                    <button class="btn btn-primary" onclick="addSubjectCard()">
                        <i class="fas fa-plus"></i> إضافة مادة
                    </button>
                    <button class="btn btn-success" onclick="calculateAverage()">
                        <i class="fas fa-calculator"></i> حساب المعدل
                    </button>
                    <button class="btn btn-outline" onclick="resetAll()">
                        <i class="fas fa-redo"></i> إعادة تعيين
                    </button>
                </div>
            </div>
            
            <!-- Results Tab -->
            <div id="results" class="tab-content">
                <div class="results-section">
                    <h2><i class="fas fa-chart-line"></i> النتائج النهائية</h2>
                    
                    <div class="results-grid">
                        <div class="result-card">
                            <div><i class="fas fa-calculator"></i> المعدل الفصلي</div>
                            <div class="result-value" id="semesterAverage">0.00</div>
                            <div>/20</div>
                        </div>
                        
                        <div class="result-card">
                            <div><i class="fas fa-chart-bar"></i> المعدل التراكمي</div>
                            <div class="result-value" id="cumulativeAverage">0.00</div>
                            <div>/20</div>
                        </div>
                        
                        <div class="result-card">
                            <div><i class="fas fa-weight"></i> مجموع المعاملات</div>
                            <div class="result-value" id="totalCoefficients">0</div>
                            <div>معامل</div>
                        </div>
                        
                        <div class="result-card">
                            <div><i class="fas fa-star"></i> التقدير</div>
                            <div class="result-value" id="grade">-</div>
                            <div id="gradeText">غير محسوب</div>
                        </div>
                    </div>
                </div>
                
                <table class="summary-table">
                    <thead>
                        <tr>
                            <th>المادة</th>
                            <th>المعامل</th>
                            <th>TD</th>
                            <th>TP</th>
                            <th>الاختبار</th>
                            <th>المعدل</th>
                            <th>الحالة</th>
                        </tr>
                    </thead>
                    <tbody id="summaryTableBody">
                        <!-- Summary will be filled here -->
                    </tbody>
                </table>
                
                <div class="action-buttons" style="margin-top: 30px;">
                    <button class="btn btn-primary" onclick="exportResults()">
                        <i class="fas fa-download"></i> تصدير النتائج
                    </button>
                    <button class="btn btn-success" onclick="printResults()">
                        <i class="fas fa-print"></i> طباعة النتائج
                    </button>
                </div>
            </div>
        </div>
        
        <!-- Footer -->
        <div class="footer">
            <h3><i class="fas fa-info-circle"></i> معلومات عن النظام</h3>
            <p>هذا النظام يدعم جميع التخصصات والمستويات الجامعية مع حساب TD و TP والمعاملات الموزونة</p>
            <p>يمكن استخدامه لـ: السنة الأولى جامعي، ليسانس، ماستر، دكتوراه، وجميع التخصصات العلمية والأدبية</p>
            <p>© 2023 النظام الشامل لحساب المعدل الجامعي | تم التطوير بلغات الويب الحديثة</p>
        </div>
    </div>

    <!-- JavaScript -->
    <script>
        // بيانات المواد لكل تخصص ومستوى
        const subjectsData = {
            mathematics: {
                s1: [
                    { name: "رياضيات 1", coefficient: 4, tdPercentage: 0.3, tpPercentage: 0.2, examPercentage: 0.5 },
                    { name: "فيزياء 1", coefficient: 3, tdPercentage: 0.3, tpPercentage: 0.2, examPercentage: 0.5 },
                    { name: "برمجة 1", coefficient: 3, tdPercentage: 0.4, tpPercentage: 0.2, examPercentage: 0.4 }
                ],
                s2: [
                    { name: "رياضيات 2", coefficient: 4, tdPercentage: 0.3, tpPercentage: 0.2, examPercentage: 0.5 },
                    { name: "فيزياء 2", coefficient: 3, tdPercentage: 0.3, tpPercentage: 0.2, examPercentage: 0.5 },
                    { name: "برمجة 2", coefficient: 3, tdPercentage: 0.4, tpPercentage: 0.2, examPercentage: 0.4 }
                ],
                s3: [
                    { name: "رياضيات 3", coefficient: 4, tdPercentage: 0.4, tpPercentage: 0, examPercentage: 0.6 },
                    { name: "ميكانيكا عقلانية", coefficient: 3, tdPercentage: 0.4, tpPercentage: 0, examPercentage: 0.6 },
                    { name: "ميكانيكا الموائع 1", coefficient: 3, tdPercentage: 0.4, tpPercentage: 0, examPercentage: 0.6 },
                    { name: "علم القياس", coefficient: 2, tdPercentage: 0, tpPercentage: 0.4, examPercentage: 0.6 }
                ]
            },
            physics: {
                s1: [
                    { name: "ميكانيكا", coefficient: 4, tdPercentage: 0.3, tpPercentage: 0.2, examPercentage: 0.5 },
                    { name: "كهرباء", coefficient: 3, tdPercentage: 0.3, tpPercentage: 0.3, examPercentage: 0.4 },
                    { name: "فيزياء حديثة", coefficient: 3, tdPercentage: 0.3, tpPercentage: 0.2, examPercentage: 0.5 }
                ],
                s3: [
                    { name: "ميكانيكا الكم", coefficient: 4, tdPercentage: 0.4, tpPercentage: 0.2, examPercentage: 0.4 },
                    { name: "الكهرومغناطيسية", coefficient: 3, tdPercentage: 0.3, tpPercentage: 0.3, examPercentage: 0.4 },
                    { name: "فيزياء الجوامد", coefficient: 3, tdPercentage: 0.4, tpPercentage: 0.2, examPercentage: 0.4 }
                ]
            },
            engineering: {
                s1: [
                    { name: "رياضيات هندسية", coefficient: 4, tdPercentage: 0.3, tpPercentage: 0.1, examPercentage: 0.6 },
                    { name: "فيزياء هندسية", coefficient: 3, tdPercentage: 0.3, tpPercentage: 0.2, examPercentage: 0.5 },
                    { name: "رسم هندسي", coefficient: 2, tdPercentage: 0.2, tpPercentage: 0.4, examPercentage: 0.4 }
                ]
            },
            computer: {
                s1: [
                    { name: "خوارزميات", coefficient: 4, tdPercentage: 0.4, tpPercentage: 0.2, examPercentage: 0.4 },
                    { name: "برمجة كائنية", coefficient: 3, tdPercentage: 0.3, tpPercentage: 0.3, examPercentage: 0.4 },
                    { name: "قواعد بيانات", coefficient: 3, tdPercentage: 0.3, tpPercentage: 0.3, examPercentage: 0.4 }
                ],
                s3: [
                    { name: "ذكاء اصطناعي", coefficient: 4, tdPercentage: 0.4, tpPercentage: 0.2, examPercentage: 0.4 },
                    { name: "شبكات حاسوب", coefficient: 3, tdPercentage: 0.3, tpPercentage: 0.3, examPercentage: 0.4 },
                    { name: "أمن معلومات", coefficient: 3, tdPercentage: 0.4, tpPercentage: 0.2, examPercentage: 0.4 }
                ]
            }
        };
        
        // المتغيرات العامة
        let subjects = [];
        let currentSubjectId = 0;
        
        // تهيئة الصفحة
        document.addEventListener('DOMContentLoaded', function() {
            loadSampleSubjects();
            updateResults();
        });
        
        // تبديل التبويبات
        function switchTab(tabName) {
            // إخفاء جميع المحتويات
            document.querySelectorAll('.tab-content').forEach(content => {
                content.classList.remove('active');
            });
            
            // إزالة النشاط من جميع الألسنة
            document.querySelectorAll('.tab').forEach(tab => {
                tab.classList.remove('active');
            });
            
            // إظهار المحتوى المختار
            document.getElementById(tabName).classList.add('active');
            
            // إضافة النشاط للسان المختار
            event.target.closest('.tab').classList.add('active');
            
            // تحديث النتائج إذا كان تبويب النتائج
            if (tabName === 'results') {
                updateResults();
            }
        }
        
        // تحميل المواد حسب التخصص والمستوى
        function loadSubjects() {
            const specialization = document.getElementById('specialization').value;
            const level = document.getElementById('level').value;
            
            if (!specialization || !level) return;
            
            const container = document.getElementById('subjectsContainer');
            container.innerHTML = '';
            
            if (subjectsData[specialization] && subjectsData[specialization][level]) {
                subjectsData[specialization][level].forEach((subject, index) => {
                    addSubjectCard(subject);
                });
            } else {
                // إضافة مواد افتراضية إذا لم توجد بيانات
                for (let i = 0; i < 4; i++) {
                    addSubjectCard();
                }
            }
        }
        
        // إضافة بطاقة مادة جديدة
        function addSubjectCard(subjectData = null) {
            currentSubjectId++;
            const subjectId = currentSubjectId;
            
            const defaultData = {
                name: `المادة ${subjectId}`,
                coefficient: 3,
                tdPercentage: 0.3,
                tpPercentage: 0.2,
                examPercentage: 0.5
            };
            
            const data = subjectData || defaultData;
            
            const card = document.createElement('div');
            card.className = 'subject-card fade-in';
            card.id = `subjectCard${subjectId}`;
            card.innerHTML = `
                <div class="subject-header">
                    <div class="subject-title">
                        <input type="text" class="form-control subject-name" value="${data.name}" 
                               style="border: none; background: transparent; padding: 0; font-size: 1.2rem;">
                    </div>
                    <div class="subject-coefficient">
                        معامل: 
                        <input type="number" class="coefficient-input" value="${data.coefficient}" min="0.5" max="10" step="0.5"
                               style="width: 60px; border: none; background: transparent; color: white; text-align: center;">
                    </div>
                </div>
                
                <div class="marks-grid">
                    <div class="mark-item">
                        <div class="mark-label">
                            <span>TD (مراقبة مستمرة)</span>
                            <span class="percentage">${(data.tdPercentage * 100)}%</span>
                        </div>
                        <input type="number" class="td-mark" min="0" max="20" step="0.25" placeholder="0-20">
                        <input type="range" class="td-percentage" min="0" max="100" value="${data.tdPercentage * 100}" step="5" style="width: 100%; margin-top: 5px;">
                    </div>
                    
                    <div class="mark-item">
                        <div class="mark-label">
                            <span>TP (أعمال تطبيقية)</span>
                            <span class="percentage">${(data.tpPercentage * 100)}%</span>
                        </div>
                        <input type="number" class="tp-mark" min="0" max="20" step="0.25" placeholder="0-20">
                        <input type="range" class="tp-percentage" min="0" max="100" value="${data.tpPercentage * 100}" step="5" style="width: 100%; margin-top: 5px;">
                    </div>
                    
                    <div class="mark-item">
                        <div class="mark-label">
                            <span>الاختبار النهائي</span>
                            <span class="percentage">${(data.examPercentage * 100)}%</span>
                        </div>
                        <input type="number" class="exam-mark" min="0" max="20" step="0.25" placeholder="0-20">
                        <input type="range" class="exam-percentage" min="0" max="100" value="${data.examPercentage * 100}" step="5" style="width: 100%; margin-top: 5px;">
                    </div>
                    
                    <div class="mark-item">
                        <div class="mark-label">
                            <span>المعدل النهائي</span>
                            <span class="percentage">100%</span>
                        </div>
                        <input type="number" class="final-mark" min="0" max="20" step="0.01" readonly style="background: #e8f4ff; font-weight: bold;">
                    </div>
                </div>
                
                <div style="margin-top: 15px; display: flex; justify-content: space-between;">
                    <button class="btn btn-danger" onclick="removeSubjectCard(${subjectId})" style="padding: 8px 15px;">
                        <i class="fas fa-trash"></i> حذف
                    </button>
                    <button class="btn btn-outline" onclick="calculateSubjectAverage(${subjectId})" style="padding: 8px 15px;">
                        <i class="fas fa-calculator"></i> حساب
                    </button>
                </div>
            `;
            
            document.getElementById('subjectsContainer').appendChild(card);
            
            // إضافة المستمعين للأحداث
            const inputs = card.querySelectorAll('input[type="number"], input[type="range"]');
            inputs.forEach(input => {
                input.addEventListener('input', () => calculateSubjectAverage(subjectId));
            });
            
            // إضافة المادة للمصفوفة
            subjects.push({
                id: subjectId,
                name: data.name,
                coefficient: data.coefficient,
                tdMark: 0,
                tpMark: 0,
                examMark: 0,
                finalMark: 0,
                tdPercentage: data.tdPercentage,
                tpPercentage: data.tpPercentage,
                examPercentage: data.examPercentage
            });
        }
        
        // حذف بطاقة مادة
        function removeSubjectCard(subjectId) {
            const card = document.getElementById(`subjectCard${subjectId}`);
            if (card) card.remove();
            
            subjects = subjects.filter(subject => subject.id !== subjectId);
            updateResults();
        }
        
        // حساب معدل مادة واحدة
        function calculateSubjectAverage(subjectId) {
            const card = document.getElementById(`subjectCard${subjectId}`);
            if (!card) return;
            
            const tdMark = parseFloat(card.querySelector('.td-mark').value) || 0;
            const tpMark = parseFloat(card.querySelector('.tp-mark').value) || 0;
            const examMark = parseFloat(card.querySelector('.exam-mark').value) || 0;
            const tdPercentage = (parseFloat(card.querySelector('.td-percentage').value) || 0) / 100;
            const tpPercentage = (parseFloat(card.querySelector('.tp-percentage').value) || 0) / 100;
            const examPercentage = (parseFloat(card.querySelector('.exam-percentage').value) || 0) / 100;
            const coefficient = parseFloat(card.querySelector('.coefficient-input').value) || 0;
            const name = card.querySelector('.subject-name').value;
            
            // تحديث النسب المئوية
            card.querySelector('.td-percentage + .percentage').textContent = `${(tdPercentage * 100)}%`;
            card.querySelector('.tp-percentage + .percentage').textContent = `${(tpPercentage * 100)}%`;
            card.querySelector('.exam-percentage + .percentage').textContent = `${(examPercentage * 100)}%`;
            
            // حساب المعدل النهائي
            const totalPercentage = tdPercentage + tpPercentage + examPercentage;
            const weightedAverage = totalPercentage > 0 ? 
                (tdMark * tdPercentage + tpMark * tpPercentage + examMark * examPercentage) / totalPercentage : 0;
            
            card.querySelector('.final-mark').value = weightedAverage.toFixed(2);
            
            // تحديث بيانات المادة
            const subjectIndex = subjects.findIndex(s => s.id === subjectId);
            if (subjectIndex !== -1) {
                subjects[subjectIndex] = {
                    ...subjects[subjectIndex],
                    name: name,
                    coefficient: coefficient,
                    tdMark: tdMark,
                    tpMark: tpMark,
                    examMark: examMark,
                    finalMark: weightedAverage,
                    tdPercentage: tdPercentage,
                    tpPercentage: tpPercentage,
                    examPercentage: examPercentage
                };
            }
            
            updateResults();
        }
        
        // حساب المعدل العام
        function calculateAverage() {
            let totalWeightedMarks = 0;
            let totalCoefficients = 0;
            let hasValidSubjects = false;
            
            subjects.forEach(subject => {
                if (subject.finalMark > 0) {
                    totalWeightedMarks += subject.finalMark * subject.coefficient;
                    totalCoefficients += subject.coefficient;
                    hasValidSubjects = true;
                }
            });
            
            if (!hasValidSubjects) {
                alert('الرجاء إدخال علامات لبعض المواد على الأقل');
                return;
            }
            
            const average = totalCoefficients > 0 ? totalWeightedMarks / totalCoefficients : 0;
            
            // تحديث واجهة النتائج
            document.getElementById('semesterAverage').textContent = average.toFixed(2);
            document.getElementById('totalCoefficients').textContent = totalCoefficients.toFixed(1);
            
            // حساب المعدل التراكمي (في تطبيق حقيقي، سيتم حمله من قاعدة بيانات)
            const cumulative = calculateCumulativeAverage(average, totalCoefficients);
            document.getElementById('cumulativeAverage').textContent = cumulative.toFixed(2);
            
            // تحديث التقدير
            updateGrade(average);
            
            // تحديث جدول الملخص
            updateSummaryTable();
            
            // الانتقال لتبويب النتائج
            switchTab('results');
        }
        
        // حساب المعدل التراكمي (محاكاة)
        function calculateCumulativeAverage(currentAverage, currentCoefficients) {
            // في التطبيق الحقيقي، سيتم تحميل البيانات من التخزين
            const previousData = JSON.parse(localStorage.getItem('previousAverages')) || [
                { average: 14.5, coefficients: 12 },
                { average: 15.2, coefficients: 14 }
            ];
            
            // إضافة المعدل الحالي
            previousData.push({
                average: currentAverage,
                coefficients: currentCoefficients
            });
            
            // حفظ البيانات
            localStorage.setItem('previousAverages', JSON.stringify(previousData));
            
            // حساب المعدل التراكمي
            let totalWeighted = 0;
            let totalCoeffs = 0;
            
            previousData.forEach(semester => {
                totalWeighted += semester.average * semester.coefficients;
                totalCoeffs += semester.coefficients;
            });
            
            return totalCoeffs > 0 ? totalWeighted / totalCoeffs : 0;
        }
        
        // تحديث التقدير
        function updateGrade(average) {
            const gradeElement = document.getElementById('grade');
            const gradeTextElement = document.getElementById('gradeText');
            
            if (average >= 18) {
                gradeElement.textContent = 'ممتاز جداً';
                gradeElement.style.color = '#1b5e20';
                gradeTextElement.textContent = 'معدل ممتاز جداً';
            } else if (average >= 16) {
                gradeElement.textContent = 'ممتاز';
                gradeElement.style.color = '#2e7d32';
                gradeTextElement.textContent = 'معدل ممتاز';
            } else if (average >= 14) {
                gradeElement.textContent = 'جيد جداً';
                gradeElement.style.color = '#388e3c';
                gradeTextElement.textContent = 'معدل جيد جداً';
            } else if (average >= 12) {
                gradeElement.textContent = 'جيد';
                gradeElement.style.color = '#43a047';
                gradeTextElement.textContent = 'معدل جيد';
            } else if (average >= 10) {
                gradeElement.textContent = 'مقبول';
                gradeElement.style.color = '#ff9800';
                gradeTextElement.textContent = 'معدل مقبول';
            } else {
                gradeElement.textContent = 'راسب';
                gradeElement.style.color = '#d32f2f';
                gradeTextElement.textContent = 'يجب إعادة السنة';
            }
        }
        
        // تحديث جدول الملخص
        function updateSummaryTable() {
            const tbody = document.getElementById('summaryTableBody');
            tbody.innerHTML = '';
            
            subjects.forEach(subject => {
                const row = document.createElement('tr');
                const status = subject.finalMark >= 10 ? 
                    '<span style="color: green;">ناجح</span>' : 
                    '<span style="color: red;">راسب</span>';
                
                row.innerHTML = `
                    <td>${subject.name}</td>
                    <td>${subject.coefficient}</td>
                    <td>${subject.tdMark.toFixed(2)}</td>
                    <td>${subject.tpMark.toFixed(2)}</td>
                    <td>${subject.examMark.toFixed(2)}</td>
                    <td><strong>${subject.finalMark.toFixed(2)}</strong></td>
                    <td>${status}</td>
                `;
                tbody.appendChild(row);
            });
        }
        
        // تحديث النتائج
        function updateResults() {
            // هذه الدالة تستدعى عند تحميل تبويب النتائج
            calculateAverage();
        }
        
        // تحميل مواد نموذجية
        function loadSampleSubjects() {
            // تحميل مثال من الصورة المرفقة (السداسي الثالث - رياضيات)
            const sampleSubjects = [
                {
                    name: "رياضيات 3",
                    coefficient: 4,
                    tdPercentage: 0.4,
                    tpPercentage: 0,
                    examPercentage: 0.6
                },
                {
                    name: "ميكانيكا عقلانية",
                    coefficient: 3,
                    tdPercentage: 0.4,
                    tpPercentage: 0,
                    examPercentage: 0.6
                },
                {
                    name: "ميكانيكا الموائع 1",
                    coefficient: 3,
                    tdPercentage: 0.4,
                    tpPercentage: 0,
                    examPercentage: 0.6
                },
                {
                    name: "علم القياس",
                    coefficient: 2,
                    tdPercentage: 0,
                    tpPercentage: 0.4,
                    examPercentage: 0.6
                }
            ];
            
            // تعيين التخصص والمستوى تلقائياً
            document.getElementById('specialization').value = 'mathematics';
            document.getElementById('level').value = 's3';
            
            // إضافة المواد النموذجية
            sampleSubjects.forEach(subject => {
                addSubjectCard(subject);
            });
            
            // إضافة علامات افتراضية للتوضيح
            setTimeout(() => {
                subjects.forEach((subject, index) => {
                    const card = document.getElementById(`subjectCard${subject.id}`);
                    if (card) {
                        const marks = [15, 12, 14, 16]; // علامات افتراضية
                        card.querySelector('.td-mark').value = index !== 3 ? 14 + Math.random() * 4 : 0;
                        card.querySelector('.tp-mark').value = index === 3 ? 15 + Math.random() * 3 : 0;
                        card.querySelector('.exam-mark').value = marks[index] || 14;
                        calculateSubjectAverage(subject.id);
                    }
                });
            }, 100);
        }
        
        // إعادة تعيين كل شيء
        function resetAll() {
            if (confirm('هل تريد إعادة تعيين جميع البيانات؟')) {
                document.getElementById('subjectsContainer').innerHTML = '';
                subjects = [];
                currentSubjectId = 0;
                loadSampleSubjects();
            }
        }
        
        // تصدير النتائج
        function exportResults() {
            const data = {
                subjects: subjects,
                specialization: document.getElementById('specialization').value,
                level: document.getElementById('level').value,
                semesterAverage: document.getElementById('semesterAverage').textContent,
                cumulativeAverage: document.getElementById('cumulativeAverage').textContent,
                exportDate: new Date().toISOString()
            };
            
            const dataStr = JSON.stringify(data, null, 2);
            const dataUri = 'data:application/json;charset=utf-8,'+ encodeURIComponent(dataStr);
            
            const exportFileDefaultName = `university-results-${new Date().toISOString().split('T')[0]}.json`;
            
            const linkElement = document.createElement('a');
            linkElement.setAttribute('href', dataUri);
            linkElement.setAttribute('download', exportFileDefaultName);
            linkElement.click();
        }
        
        // طباعة النتائج
        function printResults() {
            window.print();
        }
    </script>
</body>
</html>
