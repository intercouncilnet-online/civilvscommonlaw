<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>القانون المدني مقابل القانون العرفي</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Noto+Naskh+Arabic:wght@400;500;600;700&family=Amiri:wght@400;700&display=swap" rel="stylesheet">
<style>
:root {
  --navy: #0D1B2A;
  --navy2: #162233;
  --navy3: #1E2E42;
  --gold: #C9973A;
  --gold2: #E8B84B;
  --gold3: #F5D07A;
  --cream: #F5F0E8;
  --text: #E8E0D0;
  --text2: #A89880;
  --border: rgba(201,151,58,0.25);
  --border2: rgba(201,151,58,0.5);
  --success: #2ECC71;
  --danger: #E74C3C;
  --card: rgba(22,34,51,0.95);
}
*{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;}

body{
  font-family:'Noto Naskh Arabic',serif;
  background:var(--navy);
  color:var(--text);
  min-height:100vh;
  background-image:
    radial-gradient(ellipse at 15% 10%, rgba(201,151,58,0.08) 0%, transparent 50%),
    radial-gradient(ellipse at 85% 90%, rgba(201,151,58,0.05) 0%, transparent 50%),
    repeating-linear-gradient(0deg, transparent, transparent 80px, rgba(255,255,255,0.01) 80px, rgba(255,255,255,0.01) 81px);
}

/* ===== SCREENS ===== */
.screen{display:none;animation:fadeUp .4s ease;}
.screen.active{display:block;}
@keyframes fadeUp{from{opacity:0;transform:translateY(16px);}to{opacity:1;transform:translateY(0);}}

/* ===== WELCOME SCREEN ===== */
#welcomeScreen{
  min-height:100vh;
  display:flex;flex-direction:column;align-items:center;justify-content:center;
  padding:2rem;text-align:center;
}
.welcome-badge{
  display:inline-block;
  border:1px solid var(--gold);
  color:var(--gold);
  font-size:.75rem;letter-spacing:.12em;
  padding:.35rem 1.2rem;border-radius:2rem;
  margin-bottom:1.5rem;
  text-transform:uppercase;
}
.welcome-title{
  font-family:'Playfair Display',serif;
  font-size:clamp(1.8rem,5vw,3.2rem);
  color:#fff;line-height:1.2;margin-bottom:.5rem;
  text-shadow:0 2px 20px rgba(201,151,58,.3);
}
.welcome-sub{
  font-family:'Amiri',serif;
  font-size:clamp(1.1rem,3vw,1.6rem);
  color:var(--gold2);margin-bottom:1.5rem;
}
.welcome-desc{
  max-width:560px;color:var(--text2);
  font-size:.95rem;line-height:1.9;margin-bottom:2rem;
}
.meta-pills{
  display:flex;gap:.75rem;flex-wrap:wrap;justify-content:center;margin-bottom:2.5rem;
}
.pill{
  background:var(--navy3);border:1px solid var(--border2);
  padding:.4rem 1rem;border-radius:2rem;font-size:.82rem;color:var(--gold3);
}
.btn-start{
  background:linear-gradient(135deg,var(--gold),#A87830);
  color:var(--navy);font-family:'Noto Naskh Arabic',serif;
  font-size:1.05rem;font-weight:700;
  padding:.9rem 3rem;border:none;border-radius:2rem;
  cursor:pointer;transition:all .25s;
  box-shadow:0 4px 24px rgba(201,151,58,.35);
}
.btn-start:hover{transform:translateY(-2px);box-shadow:0 8px 32px rgba(201,151,58,.45);}
.instructor-note{margin-top:2rem;font-size:.82rem;color:var(--text2);}
.instructor-note strong{color:var(--gold3);}

/* Decorative scales */
.scales{font-size:4rem;margin-bottom:1.5rem;filter:drop-shadow(0 4px 12px rgba(201,151,58,.4));}

/* ===== MAIN LAYOUT ===== */
#mainScreen{padding:0;}

.top-bar{
  background:rgba(13,27,42,.95);
  border-bottom:1px solid var(--border);
  padding:1rem 2rem;
  display:flex;align-items:center;gap:1rem;
  position:sticky;top:0;z-index:100;
  backdrop-filter:blur(10px);
}
.top-bar-title{font-family:'Playfair Display',serif;font-size:1rem;color:var(--gold2);flex:1;}
.timer-badge{
  background:var(--navy3);border:1px solid var(--border);
  padding:.3rem .9rem;border-radius:2rem;
  font-size:.82rem;color:var(--gold3);white-space:nowrap;
}
.progress-wrap{flex:2;max-width:220px;}
.prog-bar{height:5px;background:var(--navy3);border-radius:3px;overflow:hidden;}
.prog-fill{height:100%;background:linear-gradient(90deg,var(--gold),var(--gold2));border-radius:3px;transition:width .5s;}
.prog-label{font-size:.7rem;color:var(--text2);margin-top:.3rem;text-align:center;}

/* ===== SIDEBAR + CONTENT ===== */
.layout{display:flex;min-height:calc(100vh - 57px);}

.sidebar{
  width:240px;flex-shrink:0;
  background:var(--navy2);
  border-left:1px solid var(--border);
  padding:1.5rem 0;
  position:sticky;top:57px;height:calc(100vh - 57px);
  overflow-y:auto;
}
.sidebar-section{padding:.5rem 1.25rem;font-size:.7rem;color:var(--text2);letter-spacing:.1em;text-transform:uppercase;margin-top:.5rem;}
.mod-item{
  display:flex;align-items:center;gap:.6rem;
  padding:.6rem 1.25rem;
  cursor:pointer;transition:all .2s;
  font-size:.88rem;color:var(--text2);border-right:3px solid transparent;
}
.mod-item:hover{background:rgba(201,151,58,.07);color:var(--text);}
.mod-item.active{color:var(--gold2);border-right-color:var(--gold);background:rgba(201,151,58,.1);}
.mod-item.done .mod-dot{background:var(--success);}
.mod-item.locked{opacity:.4;cursor:default;}
.mod-dot{
  width:20px;height:20px;border-radius:50%;
  background:var(--navy3);border:1.5px solid var(--border2);
  display:flex;align-items:center;justify-content:center;
  font-size:.65rem;flex-shrink:0;
  transition:all .3s;
}
.mod-item.active .mod-dot{background:var(--gold);border-color:var(--gold);color:var(--navy);}
.mod-item.done .mod-dot{border-color:var(--success);}

.content{flex:1;padding:2rem;max-width:720px;}

/* ===== MODULE CARD ===== */
.mod-page{display:none;}
.mod-page.active{display:block;animation:fadeUp .35s ease;}

.mod-header{margin-bottom:2rem;}
.mod-badge{
  display:inline-block;font-size:.72rem;letter-spacing:.1em;
  background:rgba(201,151,58,.15);color:var(--gold);
  border:1px solid var(--border2);padding:.25rem .85rem;border-radius:2rem;
  margin-bottom:.75rem;text-transform:uppercase;
}
.mod-title{font-family:'Playfair Display',serif;font-size:1.75rem;color:#fff;margin-bottom:.5rem;}
.mod-meta{font-size:.82rem;color:var(--text2);}

.lesson-block{
  background:var(--card);border:1px solid var(--border);
  border-radius:14px;padding:1.5rem;margin-bottom:1.25rem;
  backdrop-filter:blur(8px);
}
.lesson-block h3{
  font-family:'Amiri',serif;font-size:1.2rem;
  color:var(--gold2);margin-bottom:.85rem;
  padding-bottom:.5rem;border-bottom:1px solid var(--border);
}
.lesson-block p{font-size:.93rem;line-height:1.95;color:var(--text);margin-bottom:.75rem;}
.lesson-block p:last-child{margin-bottom:0;}

.highlight-box{
  background:rgba(201,151,58,.08);
  border-right:3px solid var(--gold);
  border-radius:0 8px 8px 0;
  padding:.85rem 1rem;margin:1rem 0;
  font-size:.9rem;line-height:1.85;
}
.highlight-box strong{color:var(--gold2);}

.compare-table{width:100%;border-collapse:collapse;margin:1rem 0;font-size:.88rem;}
.compare-table th{
  background:rgba(201,151,58,.15);color:var(--gold2);
  padding:.7rem 1rem;text-align:right;font-weight:600;
  border-bottom:2px solid var(--gold);
}
.compare-table td{
  padding:.65rem 1rem;border-bottom:1px solid var(--border);
  line-height:1.7;vertical-align:top;
}
.compare-table tr:last-child td{border-bottom:none;}
.compare-table tr:hover td{background:rgba(201,151,58,.04);}

.key-point{
  display:flex;gap:.75rem;
  padding:.75rem 1rem;
  background:rgba(30,46,66,.8);
  border-radius:8px;margin-bottom:.6rem;
  font-size:.9rem;line-height:1.75;
}
.kp-icon{flex-shrink:0;font-size:1rem;margin-top:.1rem;}

/* ===== QUIZ ===== */
.quiz-wrap{
  background:var(--card);border:1px solid var(--border2);
  border-radius:14px;padding:1.5rem;margin-top:1.5rem;
}
.quiz-wrap h3{
  font-family:'Amiri',serif;font-size:1.1rem;color:var(--gold2);
  margin-bottom:1.25rem;padding-bottom:.5rem;border-bottom:1px solid var(--border);
}
.q-block{margin-bottom:1.25rem;}
.q-text{font-size:.93rem;font-weight:600;margin-bottom:.75rem;line-height:1.65;color:#fff;}
.q-num{
  display:inline-block;background:var(--gold);color:var(--navy);
  font-size:.7rem;padding:.15rem .55rem;border-radius:1rem;margin-left:.4rem;font-weight:700;
}
.q-opts{display:flex;flex-direction:column;gap:.45rem;}
.q-opt{
  display:flex;align-items:center;gap:.7rem;
  padding:.65rem .9rem;
  background:var(--navy3);border:1.5px solid var(--border);
  border-radius:8px;cursor:pointer;transition:all .2s;
  font-size:.88rem;line-height:1.5;
}
.q-opt:hover{border-color:var(--gold2);background:rgba(201,151,58,.08);}
.q-opt.correct{border-color:var(--success);background:rgba(46,204,113,.1);color:#a8ffcb;}
.q-opt.wrong{border-color:var(--danger);background:rgba(231,76,60,.1);color:#ffb3b3;}
.q-opt.disabled{cursor:default;}
.opt-lbl{
  width:24px;height:24px;border-radius:50%;
  background:var(--navy2);border:1.5px solid var(--border2);
  display:flex;align-items:center;justify-content:center;
  font-size:.75rem;font-weight:700;flex-shrink:0;transition:all .2s;
}
.q-opt.correct .opt-lbl{background:var(--success);border-color:var(--success);color:#fff;}
.q-opt.wrong .opt-lbl{background:var(--danger);border-color:var(--danger);color:#fff;}
.q-feedback{
  display:none;margin-top:.6rem;padding:.55rem .85rem;
  border-radius:7px;font-size:.84rem;line-height:1.6;
}
.q-feedback.show{display:block;}
.q-feedback.ok{background:rgba(46,204,113,.1);border:1px solid rgba(46,204,113,.3);color:#a8ffcb;}
.q-feedback.no{background:rgba(231,76,60,.1);border:1px solid rgba(231,76,60,.3);color:#ffb3b3;}

.quiz-score{
  display:none;margin-top:1rem;
  padding:1rem 1.25rem;border-radius:10px;
  background:rgba(201,151,58,.1);border:1px solid var(--border2);
  text-align:center;font-size:.95rem;
}
.quiz-score.show{display:block;}
.quiz-score .sc-num{font-family:'Amiri',serif;font-size:2rem;color:var(--gold2);font-weight:700;}

/* ===== NAV BUTTONS ===== */
.mod-nav{display:flex;gap:1rem;margin-top:2rem;justify-content:space-between;}
.btn{
  padding:.7rem 1.75rem;border-radius:8px;border:none;
  font-family:'Noto Naskh Arabic',serif;font-size:.92rem;
  cursor:pointer;font-weight:600;transition:all .2s;
}
.btn-primary{background:linear-gradient(135deg,var(--gold),#A87830);color:var(--navy);}
.btn-primary:hover{transform:translateY(-1px);box-shadow:0 4px 16px rgba(201,151,58,.35);}
.btn-secondary{background:var(--navy3);color:var(--text);border:1px solid var(--border);}
.btn-secondary:hover{border-color:var(--gold2);}
.btn-success{background:linear-gradient(135deg,#27AE60,#1a7a42);color:#fff;}
.btn-success:hover{transform:translateY(-1px);box-shadow:0 4px 16px rgba(39,174,96,.35);}

/* ===== FINAL TEST ===== */
.final-header{
  text-align:center;margin-bottom:2rem;
  padding:2rem;background:var(--card);
  border:1px solid var(--border2);border-radius:14px;
}
.final-header .big-icon{font-size:3rem;margin-bottom:.75rem;}
.final-header h2{font-family:'Playfair Display',serif;font-size:1.6rem;color:#fff;margin-bottom:.5rem;}
.final-header p{font-size:.9rem;color:var(--text2);line-height:1.7;}

/* ===== CERTIFICATE SCREEN ===== */
#certScreen{
  min-height:100vh;display:flex;flex-direction:column;
  align-items:center;justify-content:center;padding:2rem;text-align:center;
}
.cert-congrats{font-size:3rem;margin-bottom:1rem;}
.cert-title{font-family:'Playfair Display',serif;font-size:1.8rem;color:#fff;margin-bottom:.5rem;}
.cert-sub{color:var(--text2);font-size:.95rem;margin-bottom:2rem;line-height:1.7;}
.cert-form{
  background:var(--card);border:1px solid var(--border2);
  border-radius:16px;padding:2rem;max-width:440px;width:100%;
  margin-bottom:1.5rem;
}
.cert-form label{display:block;font-size:.85rem;color:var(--gold3);margin-bottom:.4rem;text-align:right;}
.cert-form input{
  width:100%;padding:.7rem 1rem;background:var(--navy3);
  border:1.5px solid var(--border2);border-radius:8px;
  color:var(--text);font-family:'Noto Naskh Arabic',serif;
  font-size:.95rem;margin-bottom:1rem;transition:border .2s;
}
.cert-form input:focus{outline:none;border-color:var(--gold2);}
.cert-form input::placeholder{color:var(--text2);}
.score-summary{
  background:rgba(201,151,58,.1);border:1px solid var(--border2);
  border-radius:10px;padding:1rem 1.5rem;margin-bottom:1rem;
  font-size:.9rem;color:var(--text2);
}
.score-summary .big-score{font-family:'Amiri',serif;font-size:2.5rem;color:var(--gold2);font-weight:700;display:block;}
.btn-download{
  background:linear-gradient(135deg,var(--gold),#A87830);
  color:var(--navy);font-family:'Noto Naskh Arabic',serif;
  font-size:1rem;font-weight:700;
  padding:.85rem 2.5rem;border:none;border-radius:2rem;
  cursor:pointer;transition:all .25s;
  box-shadow:0 4px 24px rgba(201,151,58,.35);
  width:100%;
}
.btn-download:hover{transform:translateY(-2px);}
.fail-screen{
  min-height:100vh;display:flex;flex-direction:column;
  align-items:center;justify-content:center;padding:2rem;text-align:center;
}
.fail-icon{font-size:3rem;margin-bottom:1rem;}

@media(max-width:640px){
  .sidebar{display:none;}
  .content{padding:1rem;}
  .compare-table{font-size:.78rem;}
  .compare-table td,.compare-table th{padding:.5rem .6rem;}
}
</style>
</head>
<body>

<!-- ===== WELCOME ===== -->
<div id="welcomeScreen" class="screen active">
  <div class="scales">⚖️</div>
  <div class="welcome-badge">International Council Lebanon</div>
  <div class="welcome-title">Civil Law vs Common Law</div>
  <div class="welcome-sub">القانون المدني مقابل القانون العرفي</div>
  <div class="welcome-desc">
    دورة تعليمية ذاتية تُعرّفك على النظامين القانونيين الأكثر انتشاراً في العالم، أوجه التشابه والاختلاف، والتطبيقات العملية في سياق القانون المقارن.
  </div>
  <div class="meta-pills">
    <span class="pill">⏱ مدة الدورة: ساعة واحدة</span>
    <span class="pill">📚 ٤ وحدات تعليمية</span>
    <span class="pill">🎯 اختبار قصير بعد كل وحدة</span>
    <span class="pill">🏆 شهادة إتمام</span>
    <span class="pill">🌐 بالعربية</span>
  </div>
  <button class="btn-start" onclick="startCourse()">ابدأ الدورة الآن ←</button>
  <div class="instructor-note">أستاذ المادة: <strong>نبيل الجوهري</strong> &nbsp;|&nbsp; <strong>International Council Lebanon</strong></div>
</div>

<!-- ===== MAIN SCREEN ===== -->
<div id="mainScreen" class="screen">
  <div class="top-bar">
    <div class="top-bar-title">⚖️ Civil Law vs Common Law</div>
    <div class="progress-wrap">
      <div class="prog-bar"><div class="prog-fill" id="progFill" style="width:0%"></div></div>
      <div class="prog-label" id="progLabel">الوحدة ١ من ٤</div>
    </div>
    <div class="timer-badge" id="timerBadge">⏱ 60:00</div>
  </div>

  <div class="layout">
    <!-- Sidebar -->
    <div class="sidebar">
      <div class="sidebar-section">الوحدات التعليمية</div>
      <div class="mod-item active" id="sNav0" onclick="goMod(0)">
        <div class="mod-dot" id="sDot0">١</div>
        <span>المفاهيم الأساسية</span>
      </div>
      <div class="mod-item locked" id="sNav1" onclick="goMod(1)">
        <div class="mod-dot" id="sDot1">٢</div>
        <span>المصادر والتدوين</span>
      </div>
      <div class="mod-item locked" id="sNav2" onclick="goMod(2)">
        <div class="mod-dot" id="sDot2">٣</div>
        <span>دور القضاء والسوابق</span>
      </div>
      <div class="mod-item locked" id="sNav3" onclick="goMod(3)">
        <div class="mod-dot" id="sDot3">٤</div>
        <span>التطبيقات والمقارنة</span>
      </div>
      <div class="sidebar-section">الاختبار النهائي</div>
      <div class="mod-item locked" id="sNavFinal" onclick="goMod('final')">
        <div class="mod-dot" id="sDotFinal">🎯</div>
        <span>الاختبار النهائي</span>
      </div>
    </div>

    <!-- Content -->
    <div class="content">

      <!-- ========== MODULE 0 ========== -->
      <div class="mod-page active" id="mod0">
        <div class="mod-header">
          <div class="mod-badge">الوحدة الأولى · 15 دقيقة</div>
          <div class="mod-title">المفاهيم الأساسية</div>
          <div class="mod-meta">نشأة النظامين وجغرافيا الانتشار</div>
        </div>

        <div class="lesson-block">
          <h3>ما هو القانون المدني؟ Civil Law</h3>
          <p>القانون المدني (Civil Law) هو نظام قانوني يرتكز على <strong>قواعد مدوّنة ومقنّنة</strong> تُصدرها السلطة التشريعية في شكل مجلّات وقوانين مكتوبة. يعود أصله إلى <strong>القانون الروماني</strong>، ولا سيما مجموعة قوانين جوستينيان (القرن السادس الميلادي)، ثم تطور عبر النابليونية وتدوين القانون الفرنسي عام ١٨٠٤.</p>
          <div class="highlight-box">
            <strong>المبدأ الجوهري:</strong> القانون مكتوب ومنظّم سلفاً، والقاضي يُطبّقه لا يصنعه. كل حق وواجب يجب أن يُستند إلى نص مكتوب.
          </div>
          <p>ينتشر القانون المدني اليوم في <strong>فرنسا، ألمانيا، إيطاليا، إسبانيا، معظم دول أمريكا اللاتينية، اليابان، ومعظم دول العالم العربي</strong> بما فيها لبنان ومصر والمغرب.</p>
        </div>

        <div class="lesson-block">
          <h3>ما هو القانون العرفي؟ Common Law</h3>
          <p>القانون العرفي (Common Law) هو نظام قانوني يرتكز على <strong>السوابق القضائية</strong> (Precedents) التي تُشكّل قاعدة ملزمة للمحاكم اللاحقة. نشأ في <strong>إنجلترا</strong> في القرن الحادي عشر بعد الفتح النورماندي، وانتشر مع الإمبراطورية البريطانية.</p>
          <div class="highlight-box">
            <strong>المبدأ الجوهري:</strong> "Stare Decisis" – الوقوف على المقرر. القاضي ملزم باتباع الأحكام السابقة للمحاكم الأعلى درجة في نفس المسألة.
          </div>
          <p>ينتشر القانون العرفي في <strong>المملكة المتحدة، الولايات المتحدة، كندا، أستراليا، الهند، ونيجيريا</strong> وكثير من الدول التي كانت جزءاً من الإمبراطورية البريطانية.</p>
        </div>

        <div class="lesson-block">
          <h3>الانتشار الجغرافي</h3>
          <table class="compare-table">
            <thead><tr><th>القانون المدني</th><th>القانون العرفي</th><th>أنظمة مختلطة</th></tr></thead>
            <tbody>
              <tr><td>فرنسا، ألمانيا، إيطاليا</td><td>إنجلترا، ويلز، أيرلندا</td><td>إسكوتلندا</td></tr>
              <tr><td>لبنان، مصر، المغرب</td><td>الولايات المتحدة (ماعدا لويزيانا)</td><td>لويزيانا (USA)</td></tr>
              <tr><td>اليابان، كوريا الجنوبية</td><td>كندا (ماعدا كيبيك)</td><td>كيبيك (كندا)</td></tr>
              <tr><td>معظم أمريكا اللاتينية</td><td>أستراليا، نيوزيلندا، الهند</td><td>جنوب أفريقيا</td></tr>
            </tbody>
          </table>
        </div>

        <!-- QUIZ 0 -->
        <div class="quiz-wrap" id="quiz0">
          <h3>🧠 اختبار الوحدة الأولى</h3>
          <div id="qb0">

            <div class="q-block" id="q0-0">
              <div class="q-text"><span class="q-num">١</span> ما الأصل التاريخي الرئيسي للقانون المدني؟</div>
              <div class="q-opts">
                <div class="q-opt" onclick="qa(this,0,0,false,'الصحيح: القانون الروماني وليس الإغريقي.')"><div class="opt-lbl">أ</div> القانون الإغريقي</div>
                <div class="q-opt" onclick="qa(this,0,0,true,'صحيح! القانون المدني يرتكز على القانون الروماني ومجموعة جوستينيان.')"><div class="opt-lbl">ب</div> القانون الروماني</div>
                <div class="q-opt" onclick="qa(this,0,0,false,'الصحيح: القانون الروماني.')"><div class="opt-lbl">ج</div> القانون الإنجليزي</div>
                <div class="q-opt" onclick="qa(this,0,0,false,'الصحيح: القانون الروماني.')"><div class="opt-lbl">د</div> الشريعة الإسلامية</div>
              </div>
              <div class="q-feedback"></div>
            </div>

            <div class="q-block" id="q0-1">
              <div class="q-text"><span class="q-num">٢</span> ما مبدأ "Stare Decisis"؟</div>
              <div class="q-opts">
                <div class="q-opt" onclick="qa(this,0,1,false,'هذا وصف للقانون المدني.')"><div class="opt-lbl">أ</div> تطبيق القانون المكتوب حرفياً</div>
                <div class="q-opt" onclick="qa(this,0,1,false,'الصحيح: الالتزام بالسوابق القضائية.')"><div class="opt-lbl">ب</div> حق القاضي بإلغاء القانون</div>
                <div class="q-opt" onclick="qa(this,0,1,true,'صحيح! Stare Decisis يعني الالتزام بالسوابق القضائية للمحاكم الأعلى درجة.')"><div class="opt-lbl">ج</div> الالتزام بالسوابق القضائية</div>
                <div class="q-opt" onclick="qa(this,0,1,false,'الصحيح: الالتزام بالسوابق القضائية.')"><div class="opt-lbl">د</div> حق البرلمان بتفسير الأحكام</div>
              </div>
              <div class="q-feedback"></div>
            </div>

            <div class="q-block" id="q0-2">
              <div class="q-text"><span class="q-num">٣</span> أي من هذه الدول تتبع القانون العرفي؟</div>
              <div class="q-opts">
                <div class="q-opt" onclick="qa(this,0,2,false,'لبنان يتبع القانون المدني.')"><div class="opt-lbl">أ</div> لبنان</div>
                <div class="q-opt" onclick="qa(this,0,2,false,'فرنسا أصل القانون المدني.')"><div class="opt-lbl">ب</div> فرنسا</div>
                <div class="q-opt" onclick="qa(this,0,2,true,'صحيح! أستراليا ورثت القانون العرفي الإنجليزي.')"><div class="opt-lbl">ج</div> أستراليا</div>
                <div class="q-opt" onclick="qa(this,0,2,false,'اليابان تتبع القانون المدني.')"><div class="opt-lbl">د</div> اليابان</div>
              </div>
              <div class="q-feedback"></div>
            </div>

          </div>
          <div class="quiz-score" id="qs0">
            <div class="sc-num" id="qsn0"></div>
            <div id="qsm0"></div>
          </div>
        </div>

        <div class="mod-nav">
          <div></div>
          <button class="btn btn-primary" id="btn0Next" onclick="nextMod(0)" disabled>التالي: المصادر والتدوين ←</button>
        </div>
      </div>

      <!-- ========== MODULE 1 ========== -->
      <div class="mod-page" id="mod1">
        <div class="mod-header">
          <div class="mod-badge">الوحدة الثانية · 15 دقيقة</div>
          <div class="mod-title">المصادر والتدوين</div>
          <div class="mod-meta">كيف يُصنع القانون في كل نظام؟</div>
        </div>

        <div class="lesson-block">
          <h3>مصادر القانون المدني</h3>
          <p>في نظام القانون المدني، تُشكّل <strong>التشريعات المكتوبة</strong> المصدر الأول والرئيسي للقانون. تُصدرها السلطة التشريعية وتأخذ شكل قوانين ومجلّات منظّمة ومبوّبة.</p>
          <div class="key-point"><span class="kp-icon">📜</span><span><strong>المجلّة المدنية (Code Civil):</strong> صدرت في فرنسا عام ١٨٠٤ في عهد نابليون، وأثّرت في تشريعات أكثر من ٢٠ دولة.</span></div>
          <div class="key-point"><span class="kp-icon">📘</span><span><strong>المجلّة التجارية، الجزائية، الإجرائية:</strong> كل فرع من فروع القانون له مجلّة مستقلة ومنظّمة.</span></div>
          <div class="key-point"><span class="kp-icon">⚖️</span><span><strong>الفقه القانوني (Doctrine):</strong> آراء الفقهاء والأساتذة مصدر تفسيري مهم في القانون المدني.</span></div>
          <div class="key-point"><span class="kp-icon">📋</span><span><strong>القضاء:</strong> يُطبّق القانون ولا يصنعه، لكن قراراته تُشكّل مرجعاً تفسيرياً غير ملزم.</span></div>
        </div>

        <div class="lesson-block">
          <h3>مصادر القانون العرفي</h3>
          <p>في نظام القانون العرفي، تتعدد المصادر وتتداخل، لكن <strong>السوابق القضائية</strong> تحتل الصدارة بوصفها مصدراً ملزماً.</p>
          <div class="key-point"><span class="kp-icon">⚖️</span><span><strong>السوابق القضائية (Case Law / Precedents):</strong> أحكام المحاكم العليا ملزمة للمحاكم الأدنى في المسائل المتماثلة.</span></div>
          <div class="key-point"><span class="kp-icon">📜</span><span><strong>التشريعات المكتوبة (Statutes):</strong> موجودة لكنها تُكمّل القانون العرفي ولا تحلّ محله بالكامل.</span></div>
          <div class="key-point"><span class="kp-icon">📖</span><span><strong>العرف القانوني (Custom):</strong> الممارسات الموروثة والمتعارف عليها تُعدّ مصدراً قانونياً معترفاً به.</span></div>
          <div class="key-point"><span class="kp-icon">🎓</span><span><strong>الفقه (Legal Commentary):</strong> أقل إلزاماً مقارنةً بالقانون المدني، لكنه يُستأنس به.</span></div>
        </div>

        <div class="lesson-block">
          <h3>مقارنة هيكل المصادر</h3>
          <table class="compare-table">
            <thead><tr><th>المعيار</th><th>القانون المدني</th><th>القانون العرفي</th></tr></thead>
            <tbody>
              <tr><td>المصدر الأول</td><td>التشريع المكتوب (Code)</td><td>السوابق القضائية</td></tr>
              <tr><td>دور القضاء</td><td>تطبيق النص</td><td>صنع القانون وتطبيقه</td></tr>
              <tr><td>دور الفقه</td><td>كبير وتفسيري</td><td>محدود وغير ملزم</td></tr>
              <tr><td>التدوين</td><td>شامل ومنظّم</td><td>جزئي وغير منهجي</td></tr>
              <tr><td>المرونة</td><td>أقل مرونة (تحتاج تعديل تشريعي)</td><td>أكثر مرونة (يتطور بالأحكام)</td></tr>
            </tbody>
          </table>
        </div>

        <div class="lesson-block">
          <h3>القانون اللبناني نموذجاً</h3>
          <p>لبنان يتبع نظام القانون المدني بتأثير فرنسي واضح. أُصدر <strong>قانون الموجبات والعقود اللبناني عام ١٩٣٢</strong> مستوحى من المجلّة الفرنسية، كما يُطبّق نظام المجلّات المتخصصة في التجارة والإجراءات المدنية والجنائية.</p>
          <div class="highlight-box">
            <strong>استثناء مهم:</strong> قانون الأحوال الشخصية في لبنان يخضع للطوائف الدينية المختلفة، مما يجعله نظاماً مختلطاً في هذا الفرع تحديداً.
          </div>
        </div>

        <!-- QUIZ 1 -->
        <div class="quiz-wrap" id="quiz1">
          <h3>🧠 اختبار الوحدة الثانية</h3>
          <div id="qb1">
            <div class="q-block" id="q1-0">
              <div class="q-text"><span class="q-num">١</span> ما المصدر الأول للقانون في نظام القانون المدني؟</div>
              <div class="q-opts">
                <div class="q-opt" onclick="qa(this,1,0,false,'السوابق القضائية هي مصدر القانون العرفي.')"><div class="opt-lbl">أ</div> السوابق القضائية</div>
                <div class="q-opt" onclick="qa(this,1,0,true,'صحيح! التشريع المكتوب (Code) هو المصدر الأول في القانون المدني.')"><div class="opt-lbl">ب</div> التشريع المكتوب</div>
                <div class="q-opt" onclick="qa(this,1,0,false,'العرف مصدر ثانوي.')"><div class="opt-lbl">ج</div> العرف القانوني</div>
                <div class="q-opt" onclick="qa(this,1,0,false,'الفقه مصدر تفسيري لا أول.')"><div class="opt-lbl">د</div> آراء الفقهاء</div>
              </div>
              <div class="q-feedback"></div>
            </div>
            <div class="q-block" id="q1-1">
              <div class="q-text"><span class="q-num">٢</span> متى صدرت المجلّة المدنية الفرنسية (Code Civil)؟</div>
              <div class="q-opts">
                <div class="q-opt" onclick="qa(this,1,1,false,'الصحيح: ١٨٠٤.')"><div class="opt-lbl">أ</div> ١٧٨٩</div>
                <div class="q-opt" onclick="qa(this,1,1,true,'صحيح! صدرت Code Civil عام ١٨٠٤ في عهد نابليون.')"><div class="opt-lbl">ب</div> ١٨٠٤</div>
                <div class="q-opt" onclick="qa(this,1,1,false,'الصحيح: ١٨٠٤.')"><div class="opt-lbl">ج</div> ١٨٥٠</div>
                <div class="q-opt" onclick="qa(this,1,1,false,'الصحيح: ١٨٠٤.')"><div class="opt-lbl">د</div> ١٩٠٠</div>
              </div>
              <div class="q-feedback"></div>
            </div>
            <div class="q-block" id="q1-2">
              <div class="q-text"><span class="q-num">٣</span> ما ميزة القانون العرفي من حيث المرونة؟</div>
              <div class="q-opts">
                <div class="q-opt" onclick="qa(this,1,2,false,'العكس صحيح.')"><div class="opt-lbl">أ</div> أقل مرونة لأنه مدوّن بالكامل</div>
                <div class="q-opt" onclick="qa(this,1,2,false,'الصحيح: يتطور بالأحكام.')"><div class="opt-lbl">ب</div> يحتاج برلماناً لتعديله</div>
                <div class="q-opt" onclick="qa(this,1,2,true,'صحيح! القانون العرفي أكثر مرونة لأنه يتطور عبر الأحكام القضائية دون انتظار تشريع.')"><div class="opt-lbl">ج</div> يتطور بالأحكام القضائية</div>
                <div class="q-opt" onclick="qa(this,1,2,false,'الصحيح: يتطور بالأحكام.')"><div class="opt-lbl">د</div> لا يتغير أبداً</div>
              </div>
              <div class="q-feedback"></div>
            </div>
          </div>
          <div class="quiz-score" id="qs1"><div class="sc-num" id="qsn1"></div><div id="qsm1"></div></div>
        </div>

        <div class="mod-nav">
          <button class="btn btn-secondary" onclick="goMod(0)">→ السابق</button>
          <button class="btn btn-primary" id="btn1Next" onclick="nextMod(1)" disabled>التالي: دور القضاء ←</button>
        </div>
      </div>

      <!-- ========== MODULE 2 ========== -->
      <div class="mod-page" id="mod2">
        <div class="mod-header">
          <div class="mod-badge">الوحدة الثالثة · 15 دقيقة</div>
          <div class="mod-title">دور القضاء والسوابق</div>
          <div class="mod-meta">القاضي: مطبّق أم صانع للقانون؟</div>
        </div>

        <div class="lesson-block">
          <h3>القاضي في القانون المدني</h3>
          <p>في نظام القانون المدني، يُعدّ القاضي <strong>"فم القانون"</strong> (La bouche de la loi) على حد تعبير مونتيسكيو. دوره الأساسي هو تطبيق النص القانوني المكتوب على النزاع المعروض أمامه.</p>
          <div class="key-point"><span class="kp-icon">📖</span><span><strong>التفسير الضيق:</strong> القاضي يلتزم بروح النص وحرفيته، ولا يبتكر حلولاً تخرج عن إطار التشريع.</span></div>
          <div class="key-point"><span class="kp-icon">🔗</span><span><strong>غير ملزم بالسوابق:</strong> أحكام المحاكم السابقة مرجع تفسيري لا إلزام قانوني، ويحق للقاضي الانحراف عنها مع التسبيب.</span></div>
          <div class="key-point"><span class="kp-icon">👨‍⚖️</span><span><strong>دور نشط في التحقيق:</strong> في معظم دول القانون المدني، القاضي يقود التحقيق ويستجوب الشهود (النظام الاتهامي-التنقيبي).</span></div>
        </div>

        <div class="lesson-block">
          <h3>القاضي في القانون العرفي</h3>
          <p>في نظام القانون العرفي، القاضي <strong>يصنع القانون</strong> (Judge-made Law). قراراته في القضايا الجديدة تُصبح سوابق ملزمة للمحاكم الأدنى، مما يجعله شريكاً فعلياً في صياغة القانون.</p>
          <div class="key-point"><span class="kp-icon">⚖️</span><span><strong>Ratio Decidendi:</strong> مبرر الحكم القانوني، وهو الجزء الملزم من القرار القضائي الذي يصبح سابقة.</span></div>
          <div class="key-point"><span class="kp-icon">💬</span><span><strong>Obiter Dicta:</strong> ملاحظات القاضي الاستطرادية، غير ملزمة لكنها مؤثرة ومرجعية.</span></div>
          <div class="key-point"><span class="kp-icon">🏛️</span><span><strong>النظام الاتهامي (Adversarial):</strong> المحاكمة مباراة بين طرفين متكافئين أمام قاضٍ محايد لا يتدخل في التحقيق.</span></div>
        </div>

        <div class="lesson-block">
          <h3>هرم السوابق القضائية في القانون العرفي</h3>
          <div class="key-point"><span class="kp-icon">👑</span><span><strong>المحكمة العليا (Supreme Court):</strong> أحكامها ملزمة لجميع المحاكم الأدنى في الدولة. لا تلتزم بأحكامها السابقة لكنها نادراً ما تنحرف عنها.</span></div>
          <div class="key-point"><span class="kp-icon">⬆️</span><span><strong>محاكم الاستئناف:</strong> أحكامها ملزمة للمحاكم الابتدائية في نطاقها الجغرافي.</span></div>
          <div class="key-point"><span class="kp-icon">📋</span><span><strong>المحاكم الابتدائية:</strong> ملزمة بأحكام الجهات الأعلى، وأحكامها ليست سوابق ملزمة.</span></div>
          <div class="highlight-box">
            <strong>مثال:</strong> في قضية Donoghue v Stevenson (١٩٣٢) أمام مجلس اللوردات البريطاني، أُرسيت قاعدة المسؤولية التقصيرية عن الإهمال وأصبحت سابقة ملزمة حتى اليوم في جميع الدول التي تتبع القانون العرفي.
          </div>
        </div>

        <div class="lesson-block">
          <h3>مقارنة دور القضاء</h3>
          <table class="compare-table">
            <thead><tr><th>المعيار</th><th>القانون المدني</th><th>القانون العرفي</th></tr></thead>
            <tbody>
              <tr><td>دور القاضي</td><td>تطبيق النص</td><td>تطبيق + صنع القانون</td></tr>
              <tr><td>إلزامية الأحكام</td><td>غير ملزمة (إرشادية)</td><td>ملزمة (Stare Decisis)</td></tr>
              <tr><td>أسلوب المحاكمة</td><td>تنقيبي (Inquisitorial)</td><td>اتهامي (Adversarial)</td></tr>
              <tr><td>دور القاضي بالتحقيق</td><td>نشط ومتدخل</td><td>محايد وسلبي</td></tr>
              <tr><td>مصدر التطور</td><td>التشريع والفقه</td><td>الأحكام القضائية</td></tr>
            </tbody>
          </table>
        </div>

        <!-- QUIZ 2 -->
        <div class="quiz-wrap" id="quiz2">
          <h3>🧠 اختبار الوحدة الثالثة</h3>
          <div id="qb2">
            <div class="q-block" id="q2-0">
              <div class="q-text"><span class="q-num">١</span> ما معنى "Ratio Decidendi"؟</div>
              <div class="q-opts">
                <div class="q-opt" onclick="qa(this,2,0,false,'هذا وصف Obiter Dicta.')"><div class="opt-lbl">أ</div> الملاحظات الاستطرادية غير الملزمة</div>
                <div class="q-opt" onclick="qa(this,2,0,true,'صحيح! Ratio Decidendi هو مبرر الحكم الملزم الذي يصبح سابقة.')"><div class="opt-lbl">ب</div> مبرر الحكم الملزم القابل للتحول لسابقة</div>
                <div class="q-opt" onclick="qa(this,2,0,false,'الصحيح: مبرر الحكم الملزم.')"><div class="opt-lbl">ج</div> النص القانوني المكتوب</div>
                <div class="q-opt" onclick="qa(this,2,0,false,'الصحيح: مبرر الحكم الملزم.')"><div class="opt-lbl">د</div> رأي الفقيه القانوني</div>
              </div>
              <div class="q-feedback"></div>
            </div>
            <div class="q-block" id="q2-1">
              <div class="q-text"><span class="q-num">٢</span> ما أسلوب المحاكمة السائد في دول القانون المدني؟</div>
              <div class="q-opts">
                <div class="q-opt" onclick="qa(this,2,1,false,'الاتهامي سمة القانون العرفي.')"><div class="opt-lbl">أ</div> Adversarial – اتهامي</div>
                <div class="q-opt" onclick="qa(this,2,1,true,'صحيح! النظام التنقيبي سائد في دول القانون المدني حيث القاضي نشط في التحقيق.')"><div class="opt-lbl">ب</div> Inquisitorial – تنقيبي</div>
                <div class="q-opt" onclick="qa(this,2,1,false,'الصحيح: تنقيبي.')"><div class="opt-lbl">ج</div> التحكيم الإلزامي</div>
                <div class="q-opt" onclick="qa(this,2,1,false,'الصحيح: تنقيبي.')"><div class="opt-lbl">د</div> لا يوجد نظام محدد</div>
              </div>
              <div class="q-feedback"></div>
            </div>
            <div class="q-block" id="q2-2">
              <div class="q-text"><span class="q-num">٣</span> في القانون العرفي، أحكام أي جهة تُعدّ ملزمة لجميع المحاكم الأدنى؟</div>
              <div class="q-opts">
                <div class="q-opt" onclick="qa(this,2,2,false,'الصحيح: المحكمة العليا.')"><div class="opt-lbl">أ</div> المحاكم الابتدائية</div>
                <div class="q-opt" onclick="qa(this,2,2,false,'الصحيح: المحكمة العليا.')"><div class="opt-lbl">ب</div> هيئة التحكيم</div>
                <div class="q-opt" onclick="qa(this,2,2,true,'صحيح! أحكام المحكمة العليا (Supreme Court) ملزمة لجميع المحاكم الأدنى.')"><div class="opt-lbl">ج</div> المحكمة العليا (Supreme Court)</div>
                <div class="q-opt" onclick="qa(this,2,2,false,'الصحيح: المحكمة العليا.')"><div class="opt-lbl">د</div> البرلمان</div>
              </div>
              <div class="q-feedback"></div>
            </div>
          </div>
          <div class="quiz-score" id="qs2"><div class="sc-num" id="qsn2"></div><div id="qsm2"></div></div>
        </div>

        <div class="mod-nav">
          <button class="btn btn-secondary" onclick="goMod(1)">→ السابق</button>
          <button class="btn btn-primary" id="btn2Next" onclick="nextMod(2)" disabled>التالي: التطبيقات والمقارنة ←</button>
        </div>
      </div>

      <!-- ========== MODULE 3 ========== -->
      <div class="mod-page" id="mod3">
        <div class="mod-header">
          <div class="mod-badge">الوحدة الرابعة · 15 دقيقة</div>
          <div class="mod-title">التطبيقات العملية والمقارنة الشاملة</div>
          <div class="mod-meta">كيف يؤثر النظام القانوني على الممارسة اليومية؟</div>
        </div>

        <div class="lesson-block">
          <h3>تأثير النظام على العقود التجارية</h3>
          <p>يؤثر النظام القانوني المتبع تأثيراً مباشراً في كيفية صياغة العقود وتفسيرها عند النزاع.</p>
          <div class="key-point"><span class="kp-icon">📑</span><span><strong>في القانون المدني:</strong> العقود قد تكون أقصر لأن القانون المدوّن يملأ الفراغات التعاقدية. المحكمة تستند إلى نصوص المجلّة أولاً.</span></div>
          <div class="key-point"><span class="kp-icon">📄</span><span><strong>في القانون العرفي:</strong> العقود أطول وأكثر تفصيلاً لأن الأطراف يجب أن يُوضّحوا كل شرط صراحةً، إذ لا مجلّة شاملة تسدّ الثغرات.</span></div>
          <div class="highlight-box">
            <strong>مثال عملي:</strong> عقد إيجار في فرنسا ٣ صفحات، نفس العقد في لندن قد يصل إلى ٢٠ صفحة – لأن قانون الإيجار الفرنسي يُكمّل تلقائياً ما لم يُذكر.
          </div>
        </div>

        <div class="lesson-block">
          <h3>الأنظمة المختلطة (Mixed Legal Systems)</h3>
          <p>لا يوجد نظام صافٍ تماماً في العالم الحديث. كثير من الدول تمزج بين النظامين بدرجات متفاوتة.</p>
          <div class="key-point"><span class="kp-icon">🏴󠁧󠁢󠁳󠁣󠁴󠁿</span><span><strong>إسكوتلندا:</strong> القانون الخاص مدني بتأثير روماني، القانون الجنائي عرفي بريطاني.</span></div>
          <div class="key-point"><span class="kp-icon">🇨🇦</span><span><strong>كيبيك – كندا:</strong> القانون المدني يحكم العلاقات الخاصة، القانون العرفي الفيدرالي يحكم الأمور الجنائية والتجارة الدولية.</span></div>
          <div class="key-point"><span class="kp-icon">🌍</span><span><strong>جنوب أفريقيا:</strong> مزيج من القانون الروماني-الهولندي والقانون العرفي الإنجليزي.</span></div>
          <div class="key-point"><span class="kp-icon">🇱🇧</span><span><strong>لبنان:</strong> أساسه مدني فرنسي، لكن قانون الأحوال الشخصية يتبع المرجعيات الطائفية وأحياناً قواعد عرفية.</span></div>
        </div>

        <div class="lesson-block">
          <h3>الجدول المقارن الشامل</h3>
          <table class="compare-table">
            <thead><tr><th>المعيار</th><th>القانون المدني</th><th>القانون العرفي</th></tr></thead>
            <tbody>
              <tr><td>الأصل</td><td>روماني – جوستينيان</td><td>إنجليزي – نورماندي</td></tr>
              <tr><td>الانتشار</td><td>أوروبا القارية، العرب، آسيا</td><td>بريطانيا، أمريكا، كومنولث</td></tr>
              <tr><td>المصدر الأول</td><td>التشريع المكتوب</td><td>السوابق القضائية</td></tr>
              <tr><td>دور القاضي</td><td>مطبّق</td><td>مطبّق وصانع</td></tr>
              <tr><td>المحاكمة</td><td>تنقيبية</td><td>اتهامية</td></tr>
              <tr><td>طول العقود</td><td>أقصر عادةً</td><td>أطول وأكثر تفصيلاً</td></tr>
              <tr><td>التدريب القانوني</td><td>يركز على النصوص والفقه</td><td>يركز على القضايا والحالات</td></tr>
              <tr><td>التنبؤية</td><td>أعلى (النص واضح)</td><td>تعتمد على القضاة</td></tr>
              <tr><td>التطور</td><td>يحتاج تشريعاً جديداً</td><td>يتطور بالأحكام</td></tr>
            </tbody>
          </table>
        </div>

        <div class="lesson-block">
          <h3>أيهما أفضل؟</h3>
          <p>لا إجابة مطلقة. لكل نظام مزاياه وعيوبه في سياقات مختلفة:</p>
          <div class="key-point"><span class="kp-icon">✅</span><span><strong>القانون المدني يتميز بـ:</strong> الوضوح والتنظيم وسهولة الاطلاع، وهو مناسب لبيئات تحتاج استقرار قانوني وتنبؤاً عالياً.</span></div>
          <div class="key-point"><span class="kp-icon">✅</span><span><strong>القانون العرفي يتميز بـ:</strong> المرونة والتكيّف السريع مع المستجدات، وهو مناسب لبيئات الأعمال الديناميكية والتجارة الدولية.</span></div>
          <div class="highlight-box">
            <strong>التوجه الحديث:</strong> التقارب بين النظامين (Convergence). القانون العرفي يُدوّن أكثر، والقانون المدني يستعير من السوابق. الاتحاد الأوروبي نموذج للتوفيق بين النظامين.
          </div>
        </div>

        <!-- QUIZ 3 -->
        <div class="quiz-wrap" id="quiz3">
          <h3>🧠 اختبار الوحدة الرابعة</h3>
          <div id="qb3">
            <div class="q-block" id="q3-0">
              <div class="q-text"><span class="q-num">١</span> لماذا تكون العقود التجارية أطول في دول القانون العرفي؟</div>
              <div class="q-opts">
                <div class="q-opt" onclick="qa(this,3,0,false,'الصحيح: غياب المجلّة يستوجب التفصيل.')"><div class="opt-lbl">أ</div> لأن القانون العرفي يوجب ذلك صراحةً</div>
                <div class="q-opt" onclick="qa(this,3,0,true,'صحيح! غياب مجلّة مدوّنة تسدّ الفراغات يجبر الأطراف على التفصيل الكامل في العقد.')"><div class="opt-lbl">ب</div> لأنه لا توجد مجلّة قانونية تسدّ الفراغات</div>
                <div class="q-opt" onclick="qa(this,3,0,false,'الصحيح: غياب المجلّة.')"><div class="opt-lbl">ج</div> لأن المحامين يفضلون العقود الطويلة</div>
                <div class="q-opt" onclick="qa(this,3,0,false,'الصحيح: غياب المجلّة.')"><div class="opt-lbl">د</div> لأن اللغة الإنجليزية تحتاج مزيداً من الكلمات</div>
              </div>
              <div class="q-feedback"></div>
            </div>
            <div class="q-block" id="q3-1">
              <div class="q-text"><span class="q-num">٢</span> ما مثال على نظام قانوني مختلط؟</div>
              <div class="q-opts">
                <div class="q-opt" onclick="qa(this,3,1,false,'إنجلترا قانون عرفي بحت.')"><div class="opt-lbl">أ</div> إنجلترا</div>
                <div class="q-opt" onclick="qa(this,3,1,false,'فرنسا قانون مدني بحت.')"><div class="opt-lbl">ب</div> فرنسا</div>
                <div class="q-opt" onclick="qa(this,3,1,true,'صحيح! إسكوتلندا تمزج القانون المدني الروماني مع القانون العرفي الإنجليزي.')"><div class="opt-lbl">ج</div> إسكوتلندا</div>
                <div class="q-opt" onclick="qa(this,3,1,false,'الصحيح: إسكوتلندا.')"><div class="opt-lbl">د</div> أستراليا</div>
              </div>
              <div class="q-feedback"></div>
            </div>
            <div class="q-block" id="q3-2">
              <div class="q-text"><span class="q-num">٣</span> ما التوجه القانوني الحديث على المستوى الدولي؟</div>
              <div class="q-opts">
                <div class="q-opt" onclick="qa(this,3,2,false,'الصحيح: التقارب بين النظامين.')"><div class="opt-lbl">أ</div> انتشار القانون المدني والقضاء على العرفي</div>
                <div class="q-opt" onclick="qa(this,3,2,false,'الصحيح: التقارب.')"><div class="opt-lbl">ب</div> انتشار القانون العرفي وتراجع المدني</div>
                <div class="q-opt" onclick="qa(this,3,2,true,'صحيح! التوجه الحديث هو التقارب بين النظامين، حيث يقترب كل منهما من الآخر.')"><div class="opt-lbl">ج</div> التقارب والاقتراب بين النظامين</div>
                <div class="q-opt" onclick="qa(this,3,2,false,'الصحيح: التقارب.')"><div class="opt-lbl">د</div> الانعزال التام لكل نظام</div>
              </div>
              <div class="q-feedback"></div>
            </div>
          </div>
          <div class="quiz-score" id="qs3"><div class="sc-num" id="qsn3"></div><div id="qsm3"></div></div>
        </div>

        <div class="mod-nav">
          <button class="btn btn-secondary" onclick="goMod(2)">→ السابق</button>
          <button class="btn btn-primary" id="btn3Next" onclick="nextMod(3)" disabled>الاختبار النهائي ←</button>
        </div>
      </div>

      <!-- ========== FINAL TEST ========== -->
      <div class="mod-page" id="modFinal">
        <div class="final-header">
          <div class="big-icon">🎯</div>
          <h2>الاختبار النهائي</h2>
          <p>١٥ سؤالاً يشمل جميع الوحدات · نسبة النجاح ٦٠٪ فأكثر<br>المدة: ١٥ دقيقة</p>
        </div>

        <div class="quiz-wrap">
          <h3>📝 أجب عن جميع الأسئلة</h3>
          <div id="finalQuestions">

            <div class="q-block" id="fq0">
              <div class="q-text"><span class="q-num">١</span> ما النظام القانوني الذي يرتكز على السوابق القضائية الملزمة؟</div>
              <div class="q-opts">
                <div class="q-opt" onclick="fqa(this,0,false,'الصحيح: القانون العرفي.')"><div class="opt-lbl">أ</div> القانون المدني</div>
                <div class="q-opt" onclick="fqa(this,0,true,'صحيح!')"><div class="opt-lbl">ب</div> القانون العرفي</div>
                <div class="q-opt" onclick="fqa(this,0,false,'')"><div class="opt-lbl">ج</div> الشريعة الإسلامية</div>
                <div class="q-opt" onclick="fqa(this,0,false,'')"><div class="opt-lbl">د</div> القانون الدولي</div>
              </div><div class="q-feedback"></div>
            </div>

            <div class="q-block" id="fq1">
              <div class="q-text"><span class="q-num">٢</span> أيّ دولة هي مهد القانون العرفي؟</div>
              <div class="q-opts">
                <div class="q-opt" onclick="fqa(this,1,false,'')"><div class="opt-lbl">أ</div> فرنسا</div>
                <div class="q-opt" onclick="fqa(this,1,false,'')"><div class="opt-lbl">ب</div> روما</div>
                <div class="q-opt" onclick="fqa(this,1,true,'صحيح! نشأ القانون العرفي في إنجلترا بعد الفتح النورماندي.')"><div class="opt-lbl">ج</div> إنجلترا</div>
                <div class="q-opt" onclick="fqa(this,1,false,'')"><div class="opt-lbl">د</div> الولايات المتحدة</div>
              </div><div class="q-feedback"></div>
            </div>

            <div class="q-block" id="fq2">
              <div class="q-text"><span class="q-num">٣</span> ما معنى "Obiter Dicta"؟</div>
              <div class="q-opts">
                <div class="q-opt" onclick="fqa(this,2,false,'هذا Ratio Decidendi.')"><div class="opt-lbl">أ</div> مبرر الحكم الملزم</div>
                <div class="q-opt" onclick="fqa(this,2,true,'صحيح! Obiter Dicta: الملاحظات الاستطرادية غير الملزمة في الحكم القضائي.')"><div class="opt-lbl">ب</div> الملاحظات الاستطرادية غير الملزمة</div>
                <div class="q-opt" onclick="fqa(this,2,false,'')"><div class="opt-lbl">ج</div> نص القانون المكتوب</div>
                <div class="q-opt" onclick="fqa(this,2,false,'')"><div class="opt-lbl">د</div> حكم المحكمة الدستورية</div>
              </div><div class="q-feedback"></div>
            </div>

            <div class="q-block" id="fq3">
              <div class="q-text"><span class="q-num">٤</span> أيّ من هذه الدول تتبع نظاماً قانونياً مختلطاً؟</div>
              <div class="q-opts">
                <div class="q-opt" onclick="fqa(this,3,false,'')"><div class="opt-lbl">أ</div> ألمانيا</div>
                <div class="q-opt" onclick="fqa(this,3,false,'')"><div class="opt-lbl">ب</div> أستراليا</div>
                <div class="q-opt" onclick="fqa(this,3,true,'صحيح! لويزيانا تمزج القانون المدني (الفرنسي) مع القانون العرفي الفيدرالي الأمريكي.')"><div class="opt-lbl">ج</div> لويزيانا (USA)</div>
                <div class="q-opt" onclick="fqa(this,3,false,'')"><div class="opt-lbl">د</div> المملكة المتحدة (إنجلترا)</div>
              </div><div class="q-feedback"></div>
            </div>

            <div class="q-block" id="fq4">
              <div class="q-text"><span class="q-num">٥</span> في أي نظام القاضي "مطبّق للقانون" لا "صانعه"؟</div>
              <div class="q-opts">
                <div class="q-opt" onclick="fqa(this,4,true,'صحيح! في القانون المدني القاضي يطبق النص ولا يصنع القانون.')"><div class="opt-lbl">أ</div> القانون المدني</div>
                <div class="q-opt" onclick="fqa(this,4,false,'')"><div class="opt-lbl">ب</div> القانون العرفي</div>
                <div class="q-opt" onclick="fqa(this,4,false,'')"><div class="opt-lbl">ج</div> كلاهما</div>
                <div class="q-opt" onclick="fqa(this,4,false,'')"><div class="opt-lbl">د</div> لا أيٌّ منهما</div>
              </div><div class="q-feedback"></div>
            </div>

            <div class="q-block" id="fq5">
              <div class="q-text"><span class="q-num">٦</span> ما الأسلوب القضائي في دول القانون العرفي؟</div>
              <div class="q-opts">
                <div class="q-opt" onclick="fqa(this,5,false,'')"><div class="opt-lbl">أ</div> تنقيبي (Inquisitorial)</div>
                <div class="q-opt" onclick="fqa(this,5,true,'صحيح! النظام الاتهامي (Adversarial) سمة القانون العرفي.')"><div class="opt-lbl">ب</div> اتهامي (Adversarial)</div>
                <div class="q-opt" onclick="fqa(this,5,false,'')"><div class="opt-lbl">ج</div> تحكيمي</div>
                <div class="q-opt" onclick="fqa(this,5,false,'')"><div class="opt-lbl">د</div> توافقي</div>
              </div><div class="q-feedback"></div>
            </div>

            <div class="q-block" id="fq6">
              <div class="q-text"><span class="q-num">٧</span> متى صدر قانون الموجبات والعقود اللبناني؟</div>
              <div class="q-opts">
                <div class="q-opt" onclick="fqa(this,6,false,'')"><div class="opt-lbl">أ</div> ١٩٢٠</div>
                <div class="q-opt" onclick="fqa(this,6,true,'صحيح! صدر قانون الموجبات والعقود اللبناني عام ١٩٣٢.')"><div class="opt-lbl">ب</div> ١٩٣٢</div>
                <div class="q-opt" onclick="fqa(this,6,false,'')"><div class="opt-lbl">ج</div> ١٩٤٦</div>
                <div class="q-opt" onclick="fqa(this,6,false,'')"><div class="opt-lbl">د</div> ١٩٥٠</div>
              </div><div class="q-feedback"></div>
            </div>

            <div class="q-block" id="fq7">
              <div class="q-text"><span class="q-num">٨</span> في القانون العرفي، الجزء الملزم الذي يصبح سابقة هو:</div>
              <div class="q-opts">
                <div class="q-opt" onclick="fqa(this,7,false,'')"><div class="opt-lbl">أ</div> Obiter Dicta</div>
                <div class="q-opt" onclick="fqa(this,7,true,'صحيح! Ratio Decidendi هو الجزء الملزم.')"><div class="opt-lbl">ب</div> Ratio Decidendi</div>
                <div class="q-opt" onclick="fqa(this,7,false,'')"><div class="opt-lbl">ج</div> Code Civil</div>
                <div class="q-opt" onclick="fqa(this,7,false,'')"><div class="opt-lbl">د</div> Statute</div>
              </div><div class="q-feedback"></div>
            </div>

            <div class="q-block" id="fq8">
              <div class="q-text"><span class="q-num">٩</span> لماذا تكون العقود التجارية في دول القانون المدني أقصر عادةً؟</div>
              <div class="q-opts">
                <div class="q-opt" onclick="fqa(this,8,false,'')"><div class="opt-lbl">أ</div> لأن المحامين أقل كفاءة</div>
                <div class="q-opt" onclick="fqa(this,8,true,'صحيح! المجلّة القانونية تسدّ الفراغات تلقائياً فلا حاجة للتفصيل.')"><div class="opt-lbl">ب</div> لأن المجلّة المدوّنة تسدّ الفراغات التعاقدية</div>
                <div class="q-opt" onclick="fqa(this,8,false,'')"><div class="opt-lbl">ج</div> لأن القانون يحظر العقود الطويلة</div>
                <div class="q-opt" onclick="fqa(this,8,false,'')"><div class="opt-lbl">د</div> لا فرق في الطول</div>
              </div><div class="q-feedback"></div>
            </div>

            <div class="q-block" id="fq9">
              <div class="q-text"><span class="q-num">١٠</span> ما النظام القانوني الأكثر مرونة في التكيف مع المستجدات؟</div>
              <div class="q-opts">
                <div class="q-opt" onclick="fqa(this,9,false,'')"><div class="opt-lbl">أ</div> القانون المدني</div>
                <div class="q-opt" onclick="fqa(this,9,true,'صحيح! القانون العرفي يتطور بالأحكام دون انتظار تشريع جديد.')"><div class="opt-lbl">ب</div> القانون العرفي</div>
                <div class="q-opt" onclick="fqa(this,9,false,'')"><div class="opt-lbl">ج</div> كلاهما بالتساوي</div>
                <div class="q-opt" onclick="fqa(this,9,false,'')"><div class="opt-lbl">د</div> لا أيٌّ منهما</div>
              </div><div class="q-feedback"></div>
            </div>

            <div class="q-block" id="fq10">
              <div class="q-text"><span class="q-num">١١</span> القانون اللبناني مستوحى بشكل رئيسي من:</div>
              <div class="q-opts">
                <div class="q-opt" onclick="fqa(this,10,false,'')"><div class="opt-lbl">أ</div> القانون الإنجليزي العرفي</div>
                <div class="q-opt" onclick="fqa(this,10,true,'صحيح! القانون اللبناني مستوحى من القانون المدني الفرنسي.')"><div class="opt-lbl">ب</div> القانون المدني الفرنسي</div>
                <div class="q-opt" onclick="fqa(this,10,false,'')"><div class="opt-lbl">ج</div> القانون الألماني</div>
                <div class="q-opt" onclick="fqa(this,10,false,'')"><div class="opt-lbl">د</div> القانون العثماني بالكامل</div>
              </div><div class="q-feedback"></div>
            </div>

            <div class="q-block" id="fq11">
              <div class="q-text"><span class="q-num">١٢</span> أيّ مجموعة قوانين أسّست للقانون المدني الروماني؟</div>
              <div class="q-opts">
                <div class="q-opt" onclick="fqa(this,11,false,'')"><div class="opt-lbl">أ</div> مجموعة هامورابي</div>
                <div class="q-opt" onclick="fqa(this,11,true,'صحيح! مجموعة جوستينيان (القرن ٦ م) هي الأساس.')"><div class="opt-lbl">ب</div> مجموعة جوستينيان</div>
                <div class="q-opt" onclick="fqa(this,11,false,'')"><div class="opt-lbl">ج</div> Code Civil النابليوني</div>
                <div class="q-opt" onclick="fqa(this,11,false,'')"><div class="opt-lbl">د</div> Magna Carta</div>
              </div><div class="q-feedback"></div>
            </div>

            <div class="q-block" id="fq12">
              <div class="q-text"><span class="q-num">١٣</span> دور الفقه القانوني (Doctrine) في القانون المدني هو:</div>
              <div class="q-opts">
                <div class="q-opt" onclick="fqa(this,12,false,'')"><div class="opt-lbl">أ</div> ملزم للقضاء</div>
                <div class="q-opt" onclick="fqa(this,12,true,'صحيح! الفقه في القانون المدني مصدر تفسيري مؤثر لكنه غير ملزم.')"><div class="opt-lbl">ب</div> تفسيري مؤثر لكن غير ملزم</div>
                <div class="q-opt" onclick="fqa(this,12,false,'')"><div class="opt-lbl">ج</div> لا دور له</div>
                <div class="q-opt" onclick="fqa(this,12,false,'')"><div class="opt-lbl">د</div> بديل عن التشريع</div>
              </div><div class="q-feedback"></div>
            </div>

            <div class="q-block" id="fq13">
              <div class="q-text"><span class="q-num">١٤</span> Donoghue v Stevenson (١٩٣٢) أرست مبدأ:</div>
              <div class="q-opts">
                <div class="q-opt" onclick="fqa(this,13,false,'')"><div class="opt-lbl">أ</div> حرية التعاقد</div>
                <div class="q-opt" onclick="fqa(this,13,false,'')"><div class="opt-lbl">ب</div> المساواة أمام القانون</div>
                <div class="q-opt" onclick="fqa(this,13,true,'صحيح! هذه القضية أرست مبدأ المسؤولية التقصيرية عن الإهمال.')"><div class="opt-lbl">ج</div> المسؤولية التقصيرية عن الإهمال</div>
                <div class="q-opt" onclick="fqa(this,13,false,'')"><div class="opt-lbl">د</div> سرية العقود</div>
              </div><div class="q-feedback"></div>
            </div>

            <div class="q-block" id="fq14">
              <div class="q-text"><span class="q-num">١٥</span> ما التوجه العالمي الحديث في العلاقة بين النظامين؟</div>
              <div class="q-opts">
                <div class="q-opt" onclick="fqa(this,14,false,'')"><div class="opt-lbl">أ</div> الفصل التام بينهما</div>
                <div class="q-opt" onclick="fqa(this,14,false,'')"><div class="opt-lbl">ب</div> انتصار القانون المدني</div>
                <div class="q-opt" onclick="fqa(this,14,false,'')"><div class="opt-lbl">ج</div> انتصار القانون العرفي</div>
                <div class="q-opt" onclick="fqa(this,14,true,'صحيح! التوجه الحديث هو التقارب والتأثير المتبادل بين النظامين.')"><div class="opt-lbl">د</div> التقارب والتأثير المتبادل</div>
              </div><div class="q-feedback"></div>
            </div>

          </div>

          <div class="quiz-score" id="finalScore" style="display:none;margin-top:1.5rem;">
            <div class="sc-num" id="finalScoreNum"></div>
            <div id="finalScoreMsg"></div>
          </div>
        </div>

        <div class="mod-nav">
          <button class="btn btn-secondary" onclick="goMod(3)">→ السابق</button>
          <button class="btn btn-success" id="btnSubmitFinal" onclick="submitFinal()" disabled>إرسال الاختبار النهائي</button>
        </div>
      </div>

    </div><!-- end content -->
  </div><!-- end layout -->
</div><!-- end mainScreen -->

<!-- ===== CERTIFICATE SCREEN ===== -->
<div id="certScreen" class="screen">
  <div class="cert-congrats">🏆</div>
  <div class="cert-title">تهانينا! اجتزت الدورة بنجاح</div>
  <div class="cert-sub">لقد أكملت دورة <strong>Civil Law vs Common Law</strong> بنجاح.<br>أدخل بياناتك لتنزيل شهادتك الرسمية.</div>

  <div class="score-summary">
    <span class="big-score" id="certScoreDisplay">–</span>
    نتيجتك في الاختبار النهائي
  </div>

  <div class="cert-form">
    <label>الاسم الكامل (كما تريده على الشهادة)</label>
    <input type="text" id="certFullName" placeholder="مثال: Ahmad Khalil" />
    <label>البريد الإلكتروني</label>
    <input type="email" id="certEmail" placeholder="your@email.com" />
    <button class="btn-download" onclick="downloadCert()">⬇️ تنزيل الشهادة</button>
  </div>
  <button class="btn btn-secondary" onclick="goMod(0);showScreen('mainScreen')" style="margin-top:1rem;">← مراجعة الدورة</button>
</div>

<!-- ===== FAIL SCREEN ===== -->
<div id="failScreen" class="screen">
  <div class="fail-icon">📚</div>
  <div class="cert-title" style="color:#fff;">لم تتجاوز النسبة المطلوبة</div>
  <div class="cert-sub">النسبة المطلوبة للنجاح ٦٠٪. راجع الوحدات وأعد المحاولة.</div>
  <div class="score-summary" style="margin:1.5rem 0;">
    <span class="big-score" id="failScoreDisplay" style="color:var(--danger);">–</span>
    نتيجتك في الاختبار النهائي
  </div>
  <button class="btn btn-primary" onclick="retryFinal()" style="margin:.5rem;">إعادة الاختبار النهائي</button>
  <br>
  <button class="btn btn-secondary" onclick="goMod(0);showScreen('mainScreen')" style="margin:.5rem;">مراجعة الوحدات</button>
</div>

<script>
// ===== STATE =====
let modScores = [null, null, null, null]; // quiz scores per module
let modDone = [false,false,false,false];
let finalAnswers = new Array(15).fill(null); // null=unanswered
let finalCorrect = 0;
let timerInterval;
let secondsLeft = 3600;
let finalScorePct = 0;

// ===== SCREENS =====
function showScreen(id) {
  document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
  document.getElementById(id).classList.add('active');
}

function startCourse() {
  showScreen('mainScreen');
  startTimer();
}

// ===== TIMER =====
function startTimer() {
  timerInterval = setInterval(() => {
    secondsLeft--;
    const m = Math.floor(secondsLeft / 60).toString().padStart(2,'0');
    const s = (secondsLeft % 60).toString().padStart(2,'0');
    document.getElementById('timerBadge').textContent = `⏱ ${m}:${s}`;
    if (secondsLeft <= 0) clearInterval(timerInterval);
  }, 1000);
}

// ===== NAVIGATION =====
function goMod(idx) {
  document.querySelectorAll('.mod-page').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.mod-item').forEach(i => i.classList.remove('active'));

  if (idx === 'final') {
    document.getElementById('modFinal').classList.add('active');
    document.getElementById('sNavFinal').classList.add('active');
  } else {
    const nav = document.getElementById('sNav'+idx);
    if (nav && nav.classList.contains('locked')) return;
    document.getElementById('mod'+idx).classList.add('active');
    if (nav) nav.classList.add('active');
    updateProgress(idx);
  }
  document.querySelector('.content').scrollTop = 0;
  window.scrollTo({top:0,behavior:'smooth'});
}

function updateProgress(idx) {
  const pct = Math.round(((idx+1)/4)*100);
  document.getElementById('progFill').style.width = pct + '%';
  document.getElementById('progLabel').textContent = `الوحدة ${arabicNum(idx+1)} من ٤`;
}

function arabicNum(n) {
  return ['١','٢','٣','٤','٥'][n-1] || n;
}

function nextMod(idx) {
  // unlock next
  const nextIdx = idx + 1;
  if (nextIdx < 4) {
    const nextNav = document.getElementById('sNav'+nextIdx);
    nextNav.classList.remove('locked');
    goMod(nextIdx);
  } else {
    // unlock final
    document.getElementById('sNavFinal').classList.remove('locked');
    goMod('final');
  }
}

// ===== MODULE QUIZZES =====
let modAnswered = [[0,0,0],[0,0,0],[0,0,0],[0,0,0]]; // [mod][q] = answered?
let modCorrectCount = [0,0,0,0];
let modTotalAnswered = [0,0,0,0];

function qa(el, modIdx, qIdx, correct, feedback) {
  const qBlock = el.closest('.q-block');
  if (qBlock.classList.contains('answered')) return;
  qBlock.classList.add('answered');
  qBlock.querySelectorAll('.q-opt').forEach(o => { o.classList.add('disabled'); o.onclick=null; });
  const fb = qBlock.querySelector('.q-feedback');
  if (correct) {
    el.classList.add('correct');
    fb.className='q-feedback show ok';
    fb.textContent = '✅ ' + feedback;
    modCorrectCount[modIdx]++;
  } else {
    el.classList.add('wrong');
    fb.className='q-feedback show no';
    fb.textContent = '❌ ' + feedback;
  }
  modTotalAnswered[modIdx]++;
  if (modTotalAnswered[modIdx] === 3) {
    showModScore(modIdx);
  }
}

function showModScore(idx) {
  const c = modCorrectCount[idx];
  const scoreEl = document.getElementById('qs'+idx);
  scoreEl.classList.add('show');
  scoreEl.style.display='block';
  document.getElementById('qsn'+idx).textContent = c + '/٣';
  let msg = c===3 ? '🏆 ممتاز! أجبت بشكل صحيح على جميع الأسئلة.' :
            c===2 ? '👍 جيد جداً! إجابتان صحيحتان.' :
            c===1 ? '📚 إجابة واحدة صحيحة. راجع الوحدة مجدداً.' :
                    '🔄 راجع الوحدة بعناية قبل المتابعة.';
  document.getElementById('qsm'+idx).textContent = msg;

  // enable next button + mark sidebar done
  const btn = document.getElementById('btn'+idx+'Next');
  if (btn) btn.disabled = false;
  const nav = document.getElementById('sNav'+idx);
  nav.classList.add('done');
  nav.querySelector('.mod-dot').textContent = '✓';
}

// ===== FINAL QUIZ =====
let finalAnswered = new Array(15).fill(false);
let finalCorrectArr = new Array(15).fill(false);
let finalTotalAnswered = 0;

function fqa(el, qIdx, correct, feedback) {
  const qBlock = el.closest('.q-block');
  if (qBlock.classList.contains('answered')) return;
  qBlock.classList.add('answered');
  qBlock.querySelectorAll('.q-opt').forEach(o => { o.classList.add('disabled'); o.onclick=null; });
  const fb = qBlock.querySelector('.q-feedback');
  if (correct) {
    el.classList.add('correct');
    fb.className='q-feedback show ok';
    fb.textContent = '✅ ' + (feedback || 'إجابة صحيحة!');
    finalCorrectArr[qIdx] = true;
  } else {
    el.classList.add('wrong');
    fb.className='q-feedback show no';
    fb.textContent = '❌ ' + (feedback || 'إجابة خاطئة.');
  }
  finalAnswered[qIdx] = true;
  finalTotalAnswered++;
  if (finalTotalAnswered === 15) {
    document.getElementById('btnSubmitFinal').disabled = false;
  }
}

function submitFinal() {
  finalCorrect = finalCorrectArr.filter(Boolean).length;
  finalScorePct = Math.round((finalCorrect/15)*100);

  const scoreEl = document.getElementById('finalScore');
  scoreEl.classList.add('show');
  scoreEl.style.display='block';
  document.getElementById('finalScoreNum').textContent = finalCorrect + '/١٥ (' + finalScorePct + '%)';
  document.getElementById('btnSubmitFinal').disabled = true;

  setTimeout(() => {
    if (finalScorePct >= 60) {
      document.getElementById('certScoreDisplay').textContent = finalCorrect + '/١٥ (' + finalScorePct + '%)';
      showScreen('certScreen');
    } else {
      document.getElementById('failScoreDisplay').textContent = finalCorrect + '/١٥ (' + finalScorePct + '%)';
      showScreen('failScreen');
    }
  }, 1800);
}

function retryFinal() {
  // reset final
  finalAnswered = new Array(15).fill(false);
  finalCorrectArr = new Array(15).fill(false);
  finalTotalAnswered = 0;
  document.querySelectorAll('#finalQuestions .q-block').forEach(b => {
    b.classList.remove('answered');
    b.querySelectorAll('.q-opt').forEach(o => {
      o.classList.remove('correct','wrong','disabled');
    });
    b.querySelectorAll('.q-opt').forEach((o,i) => {
      // re-attach onclick by re-rendering is complex; just re-enable clicks
      o.style.pointerEvents = 'auto';
      o.classList.remove('disabled');
    });
    const fb = b.querySelector('.q-feedback');
    fb.className='q-feedback'; fb.textContent='';
  });
  // re-attach click handlers
  reattachFinalHandlers();
  document.getElementById('finalScore').style.display='none';
  document.getElementById('finalScore').classList.remove('show');
  document.getElementById('btnSubmitFinal').disabled = true;
  showScreen('mainScreen');
  goMod('final');
}

function reattachFinalHandlers() {
  const data = [
    [false,true,false,false],[false,false,true,false],[false,true,false,false],
    [false,false,true,false],[true,false,false,false],[false,true,false,false],
    [false,true,false,false],[false,true,false,false],[false,true,false,false],
    [false,true,false,false],[false,true,false,false],[false,true,false,false],
    [false,true,false,false],[false,false,true,false],[false,false,false,true]
  ];
  const feedbacks = [
    ['الصحيح: القانون العرفي.','صحيح!','',''],
    ['','','صحيح! نشأ في إنجلترا بعد الفتح النورماندي.',''],
    ['هذا Ratio Decidendi.','صحيح! Obiter Dicta: الملاحظات الاستطرادية غير الملزمة.','',''],
    ['','','صحيح! لويزيانا تمزج القانون المدني مع العرفي.',''],
    ['صحيح! في القانون المدني القاضي يطبق النص.','','',''],
    ['','صحيح! النظام الاتهامي سمة القانون العرفي.','',''],
    ['','صحيح! صدر عام ١٩٣٢.','',''],
    ['','صحيح! Ratio Decidendi هو الجزء الملزم.','',''],
    ['','صحيح! المجلّة تسدّ الفراغات.','',''],
    ['','صحيح! يتطور بالأحكام.','',''],
    ['','صحيح! مستوحى من القانون المدني الفرنسي.','',''],
    ['','صحيح! مجموعة جوستينيان.','',''],
    ['','صحيح! الفقه تفسيري غير ملزم.','',''],
    ['','','صحيح! أرست المسؤولية التقصيرية عن الإهمال.',''],
    ['','','','صحيح! التقارب والتأثير المتبادل.']
  ];
  for(let i=0;i<15;i++){
    const block = document.getElementById('fq'+i);
    const opts = block.querySelectorAll('.q-opt');
    opts.forEach((opt,j) => {
      const correct = data[i][j];
      const fb = feedbacks[i][j];
      opt.onclick = function(){ fqa(this, i, correct, fb); };
    });
  }
}

// ===== CERTIFICATE =====
function downloadCert() {
  const name = document.getElementById('certFullName').value.trim() || 'المشارك';
  const email = document.getElementById('certEmail').value.trim();
  if (!name) { alert('الرجاء إدخال الاسم الكامل'); return; }

  const today = new Date();
  const dateStr = today.toLocaleDateString('en-GB', { year:'numeric', month:'long', day:'numeric' });
  const score = finalCorrect + '/15 (' + finalScorePct + '%)';

  const certHTML = `<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=EB+Garamond:ital,wght@0,400;0,600;1,400&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box;}
body{width:297mm;height:210mm;display:flex;align-items:center;justify-content:center;background:#F8F4EC;font-family:'EB Garamond',serif;}
.cert{
  width:280mm;height:195mm;
  background:#fff;
  position:relative;
  display:flex;flex-direction:column;align-items:center;justify-content:center;
  padding:2.5rem 4rem;text-align:center;
}
/* Outer frame */
.cert::before{
  content:'';position:absolute;inset:10px;
  border:2px solid #0D1B2A;
}
.cert::after{
  content:'';position:absolute;inset:16px;
  border:1px solid #C9973A;
}
/* Corners */
.c{position:absolute;width:40px;height:40px;border-color:#C9973A;border-style:solid;}
.tl{top:8px;left:8px;border-width:3px 0 0 3px;}
.tr{top:8px;right:8px;border-width:3px 3px 0 0;}
.bl{bottom:8px;left:8px;border-width:0 0 3px 3px;}
.br{bottom:8px;right:8px;border-width:0 3px 3px 0;}
/* Background pattern */
.bg{
  position:absolute;inset:0;
  background-image:radial-gradient(circle at 20% 50%, rgba(13,27,42,.03) 0%, transparent 60%),
    radial-gradient(circle at 80% 50%, rgba(201,151,58,.04) 0%, transparent 60%);
}
.inner{position:relative;z-index:1;width:100%;}
.council{font-size:.7rem;letter-spacing:.25em;color:#0D1B2A;text-transform:uppercase;margin-bottom:.3rem;}
.org{font-family:'Playfair Display',serif;font-size:1.6rem;color:#0D1B2A;font-weight:700;margin-bottom:.15rem;}
.org-sub{font-size:.72rem;letter-spacing:.12em;color:#7A6A50;margin-bottom:.9rem;text-transform:uppercase;}
.divider{width:60%;height:1px;background:linear-gradient(90deg,transparent,#C9973A,transparent);margin:0 auto .9rem;}
.presents{font-size:.88rem;color:#5A4A2A;margin-bottom:.35rem;font-style:italic;}
.recipient{font-family:'Playfair Display',serif;font-size:2rem;color:#0D1B2A;margin-bottom:.25rem;font-weight:700;}
.underline{width:260px;height:1px;background:#C9973A;margin:0 auto .7rem;}
.completed{font-size:.88rem;color:#5A4A2A;margin-bottom:.25rem;font-style:italic;}
.course{font-family:'Playfair Display',serif;font-size:1.15rem;color:#0D1B2A;font-weight:700;margin-bottom:.2rem;}
.course-ar{font-size:.85rem;color:#7A6A50;margin-bottom:.2rem;}
.duration{font-size:.75rem;color:#7A6A50;margin-bottom:.8rem;letter-spacing:.05em;}
.score-badge{
  display:inline-block;
  background:linear-gradient(135deg,#C9973A,#A87830);
  color:#fff;padding:.25rem 1rem;border-radius:2rem;
  font-size:.75rem;font-weight:600;margin-bottom:.9rem;letter-spacing:.05em;
}
.footer{display:flex;justify-content:space-between;width:100%;align-items:flex-end;margin-top:.5rem;}
.sig{text-align:center;flex:1;}
.sig-line{width:130px;height:1px;background:#0D1B2A;margin:0 auto .25rem;}
.sig-name{font-family:'Playfair Display',serif;font-size:.88rem;color:#0D1B2A;font-weight:700;}
.sig-title{font-size:.65rem;color:#7A6A50;margin-top:.1rem;}
.date-blk{text-align:center;flex:1;}
.date-lbl{font-size:.65rem;color:#7A6A50;letter-spacing:.05em;text-transform:uppercase;}
.date-val{font-size:.82rem;color:#0D1B2A;font-weight:600;margin-top:.15rem;}
.seal{
  width:55px;height:55px;border-radius:50%;
  border:2px solid #C9973A;
  display:flex;align-items:center;justify-content:center;
  font-size:1.6rem;flex:0 0 55px;
  background:radial-gradient(circle,#FFF8E7,#F5ECD0);
  box-shadow:0 0 0 3px rgba(201,151,58,.2);
}
@media print{body{margin:0;}}
</style>
</head>
<body>
<div class="cert">
  <div class="c tl"></div><div class="c tr"></div>
  <div class="c bl"></div><div class="c br"></div>
  <div class="bg"></div>
  <div class="inner">
    <div class="council">International Council Lebanon</div>
    <div class="org">International Council Lebanon</div>
    <div class="org-sub">Certificate of Completion</div>
    <div class="divider"></div>
    <div class="presents">This certificate is proudly presented to</div>
    <div class="recipient">${name}</div>
    <div class="underline"></div>
    <div class="completed">for successfully completing the course</div>
    <div class="course">Civil Law vs Common Law Systems</div>
    <div class="course-ar">القانون المدني مقابل القانون العرفي</div>
    <div class="duration">1-Hour Professional Development Course</div>
    <div class="score-badge">Score: ${score}</div>
    <div class="footer">
      <div class="sig">
        <div class="sig-line"></div>
        <div class="sig-name">Nabil Al Jawhari</div>
        <div class="sig-title">Course Instructor</div>
      </div>
      <div class="seal">⚖️</div>
      <div class="sig">
        <div class="sig-line"></div>
        <div class="sig-name">International Council</div>
        <div class="sig-title">Lebanon</div>
      </div>
    </div>
    <div class="date-blk" style="margin-top:.5rem;">
      <div class="date-lbl">Date of Issue</div>
      <div class="date-val">${dateStr}</div>
    </div>
  </div>
</div>
<script>window.onload=()=>{window.print();}<\/script>
</body></html>`;

  const blob = new Blob([certHTML], {type:'text/html'});
  const url = URL.createObjectURL(blob);
  const a = document.createElement('a');
  a.href = url;
  a.download = 'ICL-Certificate-' + name.replace(/\s+/g,'-') + '.html';
  a.click();
  URL.revokeObjectURL(url);
}

// Init
document.getElementById('welcomeScreen').classList.add('active');
</script>
</body>
</html>
