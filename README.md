
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>الواجهة الرسمية | جامعة عين شمس - الدليل الشامل</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=IBM+Plex+Sans+Arabic:wght@300;500;700&family=Reem+Kufi:wght@700&family=Amiri:ital,wght@1,700&display=swap');

        :root {
            --bg-color: #050505;
            --accent-blue: #007aff;
            --accent-green: #34c759;
            --accent-gold: #ffb300;
            --accent-orange: #e67e22;
            --accent-red: #ff3b30;
            --accent-purple: #af52de;
            --accent-emerald: #2ecc71;
            --accent-coral: #ff6b6b;
            --accent-sky: #5dade2; 
            --glass-bg: rgba(255, 255, 255, 0.05);
            --text-gray: #aaa;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            min-height: 100vh;
            background-color: var(--bg-color);
            display: flex;
            align-items: center;
            justify-content: center;
            font-family: 'IBM Plex Sans Arabic', sans-serif;
            color: white;
            padding: 40px 0;
        }

        .light-glow {
            position: fixed;
            top: -10%;
            left: -10%;
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, rgba(0, 122, 255, 0.12) 0%, transparent 70%);
            z-index: 0;
        }

        .main-frame {
            position: relative;
            z-index: 1;
            width: 95%;
            max-width: 750px;
            background: var(--glass-bg);
            backdrop-filter: blur(30px) saturate(200%);
            -webkit-backdrop-filter: blur(30px) saturate(200%);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 40px;
            padding: 40px 20px;
            box-shadow: 0 40px 100px rgba(0,0,0,0.8);
        }

        .page { display: none; animation: slideIn 0.5s ease; }
        .active { display: block; }
        @keyframes slideIn { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }

        /* --- الواجهة الرئيسية --- */
        .header-section { text-align: center; margin-bottom: 25px; }
        .header-section h1 { font-family: 'Reem Kufi', sans-serif; font-size: 2.2rem; background: linear-gradient(to bottom, #fff, #888); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
        .badge { background: rgba(0, 122, 255, 0.1); color: var(--accent-blue); padding: 6px 20px; border-radius: 50px; font-size: 0.85rem; font-weight: 700; border: 1px solid rgba(0, 122, 255, 0.2); margin-top: 10px; display: inline-block; }
        
        .names-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 8px; margin-top: 20px; }
        .name-row { background: rgba(255, 255, 255, 0.02); border: 1px solid rgba(255, 255, 255, 0.05); padding: 12px; border-radius: 15px; text-align: center; font-size: 0.85rem; }

        .nav-container { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin-top: 30px; }
        .nav-card { padding: 15px; border-radius: 20px; cursor: pointer; text-align: center; border: 1px solid rgba(255,255,255,0.1); transition: 0.3s; display: flex; flex-direction: column; align-items: center; justify-content: center; gap: 5px; font-size: 0.9rem; }
        .nav-card.green { background: rgba(52, 199, 89, 0.15); color: var(--accent-green); }
        .nav-card.gold { background: rgba(255, 179, 0, 0.15); color: var(--accent-gold); }
        .nav-card.orange { background: rgba(230, 126, 34, 0.15); color: var(--accent-orange); }
        .nav-card.red { background: rgba(255, 59, 48, 0.15); color: var(--accent-red); }
        .nav-card.purple { background: rgba(175, 82, 222, 0.15); color: var(--accent-purple); }
        .nav-card.emerald { background: rgba(46, 204, 113, 0.15); color: var(--accent-emerald); }
        .nav-card.coral { background: rgba(255, 107, 107, 0.15); color: var(--accent-coral); }
        .nav-card.sky { background: rgba(93, 173, 226, 0.15); color: var(--accent-sky); }
        .nav-card:hover { transform: translateY(-5px); background: rgba(255,255,255,0.15); }

        /* --- تنسيقات الأكورديون والمحتوى --- */
        .back-btn { background: rgba(255,255,255,0.1); border: none; color: white; padding: 10px 20px; border-radius: 50px; cursor: pointer; margin-bottom: 20px; transition: 0.3s; }
        .back-btn:hover { background: var(--accent-blue); }
        .acc-item { background: rgba(255, 255, 255, 0.03); border: 1px solid rgba(255, 255, 255, 0.07); border-radius: 20px; margin-bottom: 12px; overflow: hidden; }
        .acc-btn { width: 100%; padding: 20px; background: none; border: none; color: inherit; text-align: right; cursor: pointer; display: flex; justify-content: space-between; font-family: inherit; font-weight: bold; font-size: 1rem; }
        .acc-content { max-height: 0; overflow: hidden; transition: max-height 0.5s cubic-bezier(0, 1, 0, 1); background: rgba(0,0,0,0.2); }
        .content-inner { padding: 20px; line-height: 1.8; color: #ddd; font-size: 0.95rem; }

        h3 { color: var(--accent-green); margin: 15px 0 10px 0; border-right: 4px solid var(--accent-gold); padding-right: 10px; }
        .highlight { color: #ff453a; font-weight: bold; }
        .info-card { background: rgba(0, 122, 255, 0.05); border-right: 5px solid var(--accent-blue); padding: 15px; border-radius: 5px; margin: 15px 0; color: #eee; }
        .detail-box { background: rgba(52, 199, 89, 0.05); padding: 15px; border-radius: 10px; margin: 10px 0; border: 1px solid rgba(52,199,89,0.1); }
        .math-box { background: rgba(255, 59, 48, 0.05); border: 1px dashed var(--accent-red); padding: 20px; border-radius: 15px; margin: 20px 0; font-family: 'Courier New', Courier, monospace; color: #ff9f0a; }
        
        .process-box { background: rgba(175, 82, 222, 0.05); border: 1px solid rgba(175, 82, 222, 0.2); padding: 15px; border-radius: 15px; margin: 15px 0; }
        .organ-tag { display: inline-block; background: var(--accent-purple); color: white; padding: 2px 12px; border-radius: 20px; font-size: 0.85rem; margin-bottom: 10px; font-weight: bold; }
        .table-style { width: 100%; border-collapse: collapse; margin: 15px 0; background: rgba(255,255,255,0.02); border-radius: 10px; overflow: hidden; font-size: 0.85rem; }
        .table-style th, .table-style td { border: 1px solid rgba(255,255,255,0.1); padding: 12px; text-align: center; }
        .table-style th { background-color: rgba(255,255,255,0.05); color: var(--accent-gold); }

        ul, ol { padding-right: 20px; }
        li { margin-bottom: 8px; }
        .signature { font-family: 'Amiri', serif; font-size: 1.6rem; color: var(--accent-blue); text-align: center; margin-top: 30px; display: block; }
    </style>
</head>
<body>

    <div class="light-glow"></div>

    <div class="main-frame">
        
        <div id="namesPage" class="page active">
            <div class="header-section">
                <h1>جامعة عين شمس</h1>
                <p class="university-info">كلية التربية النوعية • الفرقة الأولى</p>
                <div class="badge">( إعداد الطلاب )</div>
            </div>
            <div class="names-grid">
                <div class="name-row">عبدالرحمن مصطفى عويس</div>
                <div class="name-row">عمر ابراهيم كمال ابراهيم</div>
                <div class="name-row">محمد مصطفى غريب احمد</div>
                <div class="name-row">عبدالرحمن محمود محمد</div>
                <div class="name-row">مهتدي ايمن محمود حسن</div>
                <div class="name-row">محمود عبد الجواد طنطاوي</div>
                <div class="name-row">شهد احمد ابراهيم محمد</div>
                <div class="name-row">لوجينا حسام أبوبكر غريب</div>
                <div class="name-row">فرح محمد سعد محمد</div>
                <div class="name-row">فاطمه صابر احمد سليمان</div>
            </div>
            <div class="nav-container">
                <div class="nav-card green" onclick="showPage('coursePage')">📘 <span>مقرر أسس الغذاء</span></div>
                <div class="nav-card gold" onclick="showPage('detailPage')">💡 <span>شرح الباب الأول</span></div>
                <div class="nav-card orange" onclick="showPage('secondChapterPage')">🍊 <span>شرح الباب الثاني</span></div>
                <div class="nav-card red" onclick="showPage('thirdChapterPage')">🔥 <span>شرح الباب الثالث</span></div>
                <div class="nav-card purple" onclick="showPage('fourthChapterPage')">🧬 <span>شرح الباب الرابع</span></div>
                <div class="nav-card emerald" onclick="showPage('fifthChapterPage')">🥗 <span>شرح الباب الخامس</span></div>
                <div class="nav-card coral" onclick="showPage('sixthChapterPage')">🛡️ <span>شرح الباب السادس</span></div>
                <div class="nav-card sky" onclick="showPage('conceptsPage')">📚 <span>المفاهيم والمراجع</span></div>
            </div>
        </div>

        <div id="coursePage" class="page">
            <button class="back-btn" onclick="showPage('namesPage')">← العودة للرئيسية</button>
            <h2 style="text-align:center; margin-bottom:20px; color:var(--accent-green);">الدليل الشامل للمقرر</h2>
            
            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">الباب الأول: العناصر الكبرى <span>+</span></button>
                <div class="acc-content"><div class="content-inner">
                    <strong>الكربوهيدرات:</strong> المصدر الأول للطاقة، تمد الدماغ بحوالي 140جم جلوكوز يومياً.<br>
                    <strong>البروتينات:</strong> المادة العضوية الوحيدة المحتوية على نيتروجين (16%)، ضرورية لبناء الأنسجة.<br>
                    <strong>الدهون:</strong> توفر 9 سعرات لكل جرام، وتحمل الفيتامينات الذائبة (A, D, E, K).
                </div></div>
            </div>
            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">الباب الثاني: العناصر الصغرى <span>+</span></button>
                <div class="acc-content"><div class="content-inner">
                    <strong>الفيتامينات:</strong> ذائبة في الماء (C, B) وذائبة في الدهون (A, D, E, K).<br>
                    <strong>الأملاح:</strong> الكالسيوم والفوسفور للعظام، الحديد للهيموجلوبين، واليود للغدة الدرقية.
                </div></div>
            </div>
            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">الباب الثالث: التمثيل الغذائي <span>+</span></button>
                <div class="acc-content"><div class="content-inner">
                    <ul>
                        <li><strong>الهدم (Catabolism):</strong> تكسير الروابط لإنتاج الطاقة.</li>
                        <li><strong>البناء (Anabolism):</strong> ترميم الخلايا وبناء الأنسجة.</li>
                        <li><strong>BMR:</strong> معدل الأيض الأساسي في حالة الراحة التامة.</li>
                    </ul>
                </div></div>
            </div>
            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">الباب الرابع: الهضم والامتصاص <span>+</span></button>
                <div class="acc-content"><div class="content-inner">
                    <ul>
                        <li><strong>المعدة:</strong> وسط حامضي (pH 1.5-2) لهضم البروتينات.</li>
                        <li><strong>الأمعاء:</strong> الوسط القاعدي والامتصاص النهائي عبر الخملات.</li>
                    </ul>
                </div></div>
            </div>
            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">الباب الخامس: أمراض سوء التغذية <span>+</span></button>
                <div class="acc-content"><div class="content-inner">
                    <ul>
                        <li><strong>كواشيوركر:</strong> نقص بروتين حاد.</li>
                        <li><strong>مارزمس:</strong> نقص شامل في الطاقة والبروتين.</li>
                    </ul>
                </div></div>
            </div>
            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">الباب السادس: سلامة الغذاء <span>+</span></button>
                <div class="acc-content"><div class="content-inner">
                    <p><strong>منطقة الخطر:</strong> تنشط البكتيريا بين 5 و 60 درجة مئوية.</p>
                    <p><strong>الحفظ:</strong> يتم عبر التبريد، التجميد، أو البسترة.</p>
                </div></div>
            </div>
        </div>

        <div id="detailPage" class="page">
            <button class="back-btn" onclick="showPage('namesPage')">← العودة</button>
            <h2 style="text-align:center; color:var(--accent-gold); margin-bottom:20px;">الشرح التفصيلي للباب الأول</h2>
            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">1. الكربوهيدرات (التفصيل الكامل) <span>+</span></button>
                <div class="acc-content"><div class="content-inner">
                    <h3>أولاً: التعريف والتركيب</h3>
                    <p>تتكون من (C, H, O) بنسبة (1:2:1). تسمى مائيات الكربون. الوظيفة الكيميائية: مركبات بوليهيدروكسي ألديهيدية أو كيتونية.</p>
                    <h3>ثانياً: التصنيف الدقيق</h3>
                    <strong>1. الأحادية:</strong> الجلوكوز (سكر الدم)، الفركتوز (سكر الفاكهة)، الجالاكتوز.<br>
                    <strong>2. الثنائية:</strong> السكروز (سكر مائدة)، اللاكتوز (سكر حليب)، المالتوز (سكر شعير).<br>
                    <strong>3. العديدة:</strong> النشا، الجليكوجين (النشا الحيواني يُخزن في الكبد 100جم والعضلات 400جم)، الألياف (ذائبة وغير ذائبة).
                    <div class="info-card"><strong>Protein Sparing:</strong> الكربوهيدرات تحمي البروتين من الاحتراق ليتفرغ لبناء الأنسجة.</div>
                </div></div>
            </div>
            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">2. البروتينات (التفصيل الكامل) <span>+</span></button>
                <div class="acc-content"><div class="content-inner">
                    <h3>أولاً: التركيب الكيميائي</h3>
                    <p>تتكون من أحماض أمينية مرتبطة بروابط ببتيدية. تحتوي على <span class="highlight">النيتروجين N</span> بنسبة ثابتة (16%).</p>
                    <h3>ثانياً: الأحماض الأمينية</h3>
                    <ul>
                        <li><strong>أساسية (9 أحماض):</strong> لا يصنعها الجسم (ليسين، تريبتوفان).</li>
                        <li><strong>غير أساسية:</strong> يصنعها الجسم.</li>
                    </ul>
                    <div class="detail-box"><strong>بروتينات كاملة:</strong> مصادر حيوانية (البيض هو المقياس الذهبي).</div>
                </div></div>
            </div>
            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">3. الدهون (التفصيل الكامل) <span>+</span></button>
                <div class="acc-content"><div class="content-inner">
                    <p>الجرام الواحد يعطي <span class="highlight">9 سعرات حرارية</span>.</p>
                    <h3>الأنواع:</h3>
                    <ul>
                        <li><strong>مشبعة:</strong> صلبة (حيوانية).</li>
                        <li><strong>غير مشبعة:</strong> سائلة (أوميجا 3 و 6).</li>
                    </ul>
                    <div class="info-card"><strong>وظائف فسيولوجية:</strong> امتصاص فيتامينات (A, D, E, K)، الحماية للأعضاء، والعزل الحراري.</div>
                </div></div>
            </div>
        </div>

        <div id="secondChapterPage" class="page">
            <button class="back-btn" onclick="showPage('namesPage')">← العودة</button>
            <h2 style="text-align:center; color:var(--accent-orange); margin-bottom:20px;">الباب الثاني: العناصر الغذائية الصغرى</h2>
            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">1. الفيتامينات الذائبة في الدهون (A, D, E, K) <span>+</span></button>
                <div class="acc-content"><div class="content-inner">
                    <p>تتميز هذه المجموعة بأنها تُخزن في دهون الجسم والكبد.</p>
                    <h3>فيتامين A (الريتينول)</h3><p>للرؤية والمناعة. نقصه يسبب العشى الليلي.</p>
                    <h3>فيتامين D (الشمس)</h3><p>لامتصاص الكالسيوم. نقصه يسبب الكساح.</p>
                </div></div>
            </div>
            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">2. الفيتامينات الذائبة في الماء (C & B) <span>+</span></button>
                <div class="acc-content"><div class="content-inner">
                    <h3>فيتامين C</h3><p>للكولاجين والتئام الجروح. نقصه يسبب الاسقربوط.</p>
                </div></div>
            </div>
        </div>

        <div id="thirdChapterPage" class="page">
            <button class="back-btn" onclick="showPage('namesPage')">← العودة</button>
            <h2 style="text-align:center; color:var(--accent-red); margin-bottom:20px;">الباب الثالث: التمثيل الغذائي وتوازن الطاقة</h2>
            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">1. مفهوم التمثيل الغذائي <span>+</span></button>
                <div class="acc-content"><div class="content-inner">
                    <p>الهدم (Catabolism): تكسير لإنتاج الطاقة. البناء (Anabolism): بناء الخلايا.</p>
                </div></div>
            </div>
            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">2. حساب الـ BMR <span>+</span></button>
                <div class="acc-content"><div class="content-inner">
                    <div class="math-box">الرجال: 1 × الوزن × 24 | النساء: 0.9 × الوزن × 24</div>
                </div></div>
            </div>
        </div>

        <div id="fourthChapterPage" class="page">
            <button class="back-btn" onclick="showPage('namesPage')">← العودة</button>
            <h2 style="text-align:center; color:var(--accent-purple); margin-bottom:20px;">الباب الرابع: الهضم والامتصاص (Digestion & Absorption)</h2>
            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">1. مفهوم الهضم وأنواعه <span>+</span></button>
                <div class="acc-content">
                    <div class="content-inner">
                        <p>الهضم هو عملية تحويل جزيئات الغذاء الكبيرة والمعقدة إلى جزيئات صغيرة ذائبة ليسهل امتصاصها عبر أغشية الخلايا.</p>
                        <ul>
                            <li><strong>الهضم الميكانيكي:</strong> مثل تقطيع الطعام بالأسنان وحركة المعدة.</li>
                            <li><strong>الهضم الكيميائي:</strong> تدخل الإنزيمات والعصارات لتحليل الروابط الكيميائية.</li>
                        </ul>
                    </div>
                </div>
            </div>
            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">2. رحلة الغذاء في القناة الهضمية <span>+</span></button>
                <div class="acc-content">
                    <div class="content-inner">
                        <div class="process-box"><span class="organ-tag">1. الفم</span><p>يبدأ هضم <span class="highlight">النشويات</span> بفعل التيالين.</p></div>
                        <div class="process-box"><span class="organ-tag">2. المعدة</span><p>يبدأ هضم <span class="highlight">البروتينات</span> بفعل الببسين وحمض HCl.</p></div>
                        <div class="process-box"><span class="organ-tag">3. الأمعاء الدقيقة</span><p>المحطة النهائية لهضم كافة العناصر والامتصاص عبر الخملات.</p></div>
                    </div>
                </div>
            </div>
            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">3. جدول الإنزيمات <span>+</span></button>
                <div class="acc-content">
                    <div class="content-inner">
                        <table class="table-style">
                            <thead><tr><th>المادة</th><th>الإنزيم</th><th>الناتج</th></tr></thead>
                            <tbody>
                                <tr><td>النشويات</td><td>الأميليز</td><td>جلوكوز</td></tr>
                                <tr><td>البروتينات</td><td>الببسين/التريبسين</td><td>أحماض أمينية</td></tr>
                                <tr><td>الدهون</td><td>الليبيز+الصفراء</td><td>أحماض دهنية</td></tr>
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
        </div>

        <div id="fifthChapterPage" class="page">
            <button class="back-btn" onclick="showPage('namesPage')">← العودة</button>
            <h2 style="text-align:center; color:var(--accent-emerald); margin-bottom:20px;">الباب الخامس: تخطيط الوجبات</h2>
            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">1. أسس تخطيط الوجبات <span>+</span></button>
                <div class="acc-content">
                    <div class="content-inner">
                        <ul>
                            <li><span class="highlight">الكفاية:</span> توفير سعرات وعناصر كافية.</li>
                            <li><span class="highlight">التوازن:</span> عدم طغيان عنصر على آخر.</li>
                            <li><span class="highlight">الاعتدال:</span> كميات معقولة من السكريات.</li>
                            <li><span class="highlight">التنوع:</span> أطعمة مختلفة من نفس المجموعة.</li>
                        </ul>
                    </div>
                </div>
            </div>
            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">2. نظام الطبق الصحي (MyPlate) <span>+</span></button>
                <div class="acc-content">
                    <div class="content-inner">
                        <table class="table-style">
                            <thead><tr><th>القسم</th><th>النسبة</th><th>أمثلة</th></tr></thead>
                            <tbody>
                                <tr><td style="color: #2ecc71;">الخضروات/الفواكه</td><td>50%</td><td>سلطة، فواكه</td></tr>
                                <tr><td style="color: #e67e22;">الحبوب</td><td>25%</td><td>خبز أسمر، أرز</td></tr>
                                <tr><td style="color: #ff3b30;">البروتين</td><td>25%</td><td>لحوم، بقوليات</td></tr>
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
        </div>

        <div id="sixthChapterPage" class="page">
            <button class="back-btn" onclick="showPage('namesPage')">← العودة</button>
            <h2 style="text-align:center; color:var(--accent-coral); margin-bottom:20px;">الباب السادس: سلامة وحفظ الغذاء</h2>
            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">1. أنواع تلوث الغذاء (Food Contamination) <span>+</span></button>
                <div class="acc-content">
                    <div class="content-inner">
                        <p>تلوث الغذاء هو وجود أي مادة غريبة تجعله غير صالح. ينقسم إلى:</p>
                        <ul>
                            <li><strong>تلوث ميكروبيولوجي:</strong> بكتيريا وفيروسات (مثل السالمونيلا).</li>
                            <li><strong>تلوث كيميائي:</strong> بقايا مبيدات ومنظفات.</li>
                            <li><strong>تلوث فيزيائي:</strong> زجاج، خشب، أو شعر.</li>
                        </ul>
                    </div>
                </div>
            </div>
            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">2. درجة الحرارة وسلامة الغذاء <span>+</span></button>
                <div class="acc-content">
                    <div class="content-inner">
                        <div class="math-box" style="color:var(--accent-coral); border-color:var(--accent-coral);">منطقة الخطر (Danger Zone): بين 5°C و 60°C</div>
                        <div class="info-card">في هذه المنطقة تتضاعف البكتيريا بسرعة كبيرة.</div>
                        <ul>
                            <li><strong>التبريد:</strong> أقل من 5°C.</li>
                            <li><strong>التجميد:</strong> أقل من -18°C.</li>
                            <li><strong>الطهي الجيد:</strong> أعلى من 75°C.</li>
                        </ul>
                    </div>
                </div>
            </div>
            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">3. طرق حفظ الغذاء (Food Preservation) <span>+</span></button>
                <div class="acc-content">
                    <div class="content-inner">
                        <h3>أولاً: الطرق الفيزيائية</h3>
                        <div class="detail-box"><strong>البسترة:</strong> تسخين ثم تبريد فجائي لقتل الميكروبات.</div>
                        <div class="detail-box"><strong>التجفيف:</strong> إزالة الرطوبة.</div>
                        <h3>ثانياً: الطرق الكيميائية</h3>
                        <p>التمليح، التسكير، التدخين، واستخدام المواد الحافظة.</p>
                    </div>
                </div>
            </div>
            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">4. القواعد الخمس لسلامة الغذاء <span>+</span></button>
                <div class="acc-content">
                    <div class="content-inner">
                        <div class="info-card">
                            <ol>
                                <li>النظافة المستمرة.</li>
                                <li>الفصل بين النيئ والمطبوخ.</li>
                                <li>الطهي الجيد.</li>
                                <li>الحفاظ على الحرارة.</li>
                                <li>استخدام مياه ومواد خام آمنة.</li>
                            </ol>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div id="conceptsPage" class="page">
            <button class="back-btn" onclick="showPage('namesPage')">← العودة</button>
            <h2 style="text-align:center; color:var(--accent-sky); margin-bottom:25px;">📚 المفاهيم والمراجع العلمية</h2>
            
            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">📖 القاموس الشامل للمصطلحات العلمية <span>+</span></button>
                <div class="acc-content">
                    <div class="content-inner">
                        <table class="table-style">
                            <thead><tr><th>المصطلح</th><th>التعريف العلمي</th></tr></thead>
                            <tbody>
                                <tr><td>علم التغذية</td><td>العلم الذي يبحث في علاقة الغذاء بالكائن الحي، ويشمل التناول والهضم والامتصاص.</td></tr>
                                <tr><td>المغذيات</td><td>المواد الكيميائية التي يعتمد عليها الجسم في الطاقة والنمو والترميم.</td></tr>
                                <tr><td>BMR</td><td>أقل قدر من الطاقة يحتاجه الجسم للوظائف الحيوية أثناء الراحة.</td></tr>
                                <tr><td>السعر الحراري</td><td>وحدة قياس الطاقة الموجودة في الغذاء.</td></tr>
                                <tr><td>الجليكوجين</td><td>الصورة التي يخزن بها الجسم الكربوهيدرات داخل الكبد والعضلات.</td></tr>
                                <tr><td>الأحماض الأمينية الأساسية</td><td>أحماض لا يستطيع الجسم تصنيعها ويجب الحصول عليها من الغذاء.</td></tr>
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>

            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">🍕 دليل المذاكرة التطبيقي (الخميرة والبيتزا) <span>+</span></button>
                <div class="acc-content">
                    <div class="content-inner">
                        <h3>🧪 علم أساسيات الخميرة</h3>
                        <p>كائنات حية دقيقة وحيدة الخلية، غنية بفيتامين B المركب والبروتينات.</p>
                        <div class="detail-box"><strong>الأنواع:</strong> خميرة بيرة طازجة، خميرة جافة (Yeast).</div>
                        <div class="math-box">Sucrose → Glucose + Fructose → Alcohol + CO2</div>
                        <h3>🍞 تكنولوجيا عجين البيتزا</h3>
                        <ul>
                            <li>الطريقة البطيئة (Slow)، المعتدلة، الخلط العنيف (Fast).</li>
                        </ul>
                        <div class="info-card"><strong>المقادير:</strong> دقيق، ملح، زيت، خميرة، سكر، حليب، بيضة.</div>
                        <h3>🔥 مراحل النمو والخبز</h3>
                        <ol>
                            <li>نشاط الخميرة، التخمير الأول، التخمير الثاني، مرحلة التشكيل.</li>
                        </ol>
                        <div class="math-box" style="color:#ff7675;">يجب تجنب زيادة التخمير</div>
                    </div>
                </div>
            </div>

            <div class="acc-item">
                <button class="acc-btn" onclick="toggleAcc(this)">🥗 الربط الأكاديمي (تغذية + سلامة) <span>+</span></button>
                <div class="acc-content">
                    <div class="content-inner">
                        <div class="info-card"><strong>الخاصية الأسموزية:</strong> لا يوضع الملح فوق الخميرة مباشرة لأنه يسحب الماء من خلاياها.</div>
                        <div class="detail-box"><strong>القيمة الغذائية:</strong> الأنشوجة ترفع أوميجا 3، والجبن يوفر الكالسيوم، وزيت الزيتون يوفر دهوناً غير مشبعة.</div>
                        <div class="math-box">العجين المبلل بيئة خصبة للبكتيريا (يجب الحذر من منطقة الخطر).</div>
                    </div>
                </div>
            </div>
        </div>

        <span class="signature">حقوق الطبع والنشر محفوظة فقط للمطور ("𝐵𝑜𝑑𝑎")</span>
    </div>

    <script>
        function showPage(id) {
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.getElementById(id).classList.add('active');
            window.scrollTo({top: 0, behavior: 'smooth'});
        }

        function toggleAcc(btn) {
            const content = btn.nextElementSibling;
            const isOpen = content.style.maxHeight;
            const parentPage = btn.closest('.page');
            
            parentPage.querySelectorAll('.acc-content').forEach(c => {
                c.style.maxHeight = null;
                if(c.previousElementSibling.querySelector('span')) {
                    c.previousElementSibling.querySelector('span').innerText = '+';
                }
            });

            if (!isOpen) {
                content.style.maxHeight = content.scrollHeight + "px";
                btn.querySelector('span').innerText = '−';
            }
        }
    </script>
</body>
</html>
