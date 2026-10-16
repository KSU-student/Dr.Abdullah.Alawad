<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0, user-scalable=yes">
  <title>د. عبدالله العواد | Dr. Abdullah Alawad</title>
  <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;800;900&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  
  <style>
    :root {
      --navy-dark: #090d16;
      --navy-card: #111827;
      --navy-border: #1e293b;
      --medical-blue: #0ea5e9;
      --gold-accent: #d97706;
      --gold-light: #fef3c7;
      --white: #ffffff;
      --text-muted: #94a3b8;
    }

    * { box-sizing: border-box; -webkit-tap-highlight-color: transparent; }

    body {
      margin: 0; padding: 0;
      font-family: 'Tajawal', sans-serif;
      background-color: var(--navy-dark);
      color: var(--white);
      min-height: 100vh;
      display: flex; flex-direction: column; align-items: center; justify-content: center;
      background-image: 
        radial-gradient(circle at 50% 0%, rgba(14, 165, 233, 0.15) 0%, transparent 60%),
        radial-gradient(circle at 50% 100%, rgba(217, 119, 6, 0.08) 0%, transparent 60%);
      background-attachment: fixed;
    }

    .container {
      width: 100%; max-width: 460px;
      padding: 24px 16px;
    }

    .profile-card {
      background: rgba(17, 24, 39, 0.92);
      border: 1.5px solid var(--navy-border);
      border-radius: 24px;
      padding: 30px 20px;
      text-align: center;
      box-shadow: 0 20px 50px rgba(0,0,0,0.6);
      backdrop-filter: blur(12px);
      position: relative;
    }

    .doctor-avatar-container {
      position: relative; width: 140px; height: 140px; margin: 0 auto 16px;
    }

    .doctor-avatar {
      width: 100%; height: 100%;
      border-radius: 50%;
      object-fit: cover;
      border: 3px solid var(--medical-blue);
      box-shadow: 0 0 25px rgba(14, 165, 233, 0.35);
    }

    .doctor-title-ar {
      font-size: 23px; font-weight: 900;
      color: #fff; margin: 0 0 2px;
      background: linear-gradient(180deg, #fff 40%, #e2e8f0 100%);
      -webkit-background-clip: text; background-clip: text; color: transparent;
    }

    .doctor-title-en {
      font-size: 14px; font-weight: 700;
      color: var(--medical-blue); margin-0 0 16px;
      letter-spacing: 0.5px; direction: ltr; display: inline-block;
    }

    .badge-label {
      background: rgba(14, 165, 233, 0.12);
      color: var(--medical-blue);
      border: 1px solid rgba(14, 165, 233, 0.3);
      padding: 4px 14px; border-radius: 20px;
      font-size: 12px; font-weight: 800;
      display: inline-block; margin-bottom: 14px;
    }

    .bio-box {
      background: rgba(255, 255, 255, 0.03);
      border-right: 3px solid var(--medical-blue);
      border-radius: 12px;
      padding: 14px;
      text-align: right;
      font-size: 13.5px;
      line-height: 1.8;
      color: #cbd5e1;
      margin-bottom: 20px;
    }

    .btn-action {
      width: 100%; padding: 13px;
      border-radius: 12px; border: none;
      font-weight: 800; font-size: 14.5px;
      cursor: pointer; font-family: inherit;
      display: flex; align-items: center; justify-content: center; gap: 8px;
      transition: 0.3s; margin-bottom: 12px;
    }

    .btn-social {
      background: rgba(255, 255, 255, 0.06);
      border: 1.5px solid var(--navy-border);
      color: #fff;
    }
    .btn-social:hover {
      background: rgba(14, 165, 233, 0.15);
      border-color: var(--medical-blue);
    }

    .btn-booking {
      background: linear-gradient(135deg, #0284c7, #0369a1);
      color: #fff;
      box-shadow: 0 4px 20px rgba(2, 132, 199, 0.4);
    }
    .btn-booking:hover { transform: translateY(-1px); }

    /* Modal - نافذة وسائل التواصل */
    .modal-overlay {
      position: fixed; inset: 0;
      background: rgba(0,0,0,0.8);
      backdrop-filter: blur(8px);
      z-index: 100;
      display: flex; align-items: center; justify-content: center;
      opacity: 0; pointer-events: none; transition: 0.3s;
    }
    .modal-overlay.active { opacity: 1; pointer-events: auto; }

    .modal-content {
      background: var(--navy-card);
      border: 1.5px solid var(--navy-border);
      border-radius: 20px;
      width: 90%; max-width: 380px;
      padding: 22px 18px;
      text-align: center;
      box-shadow: 0 20px 40px rgba(0,0,0,0.8);
    }

    .social-link-item {
      display: flex; align-items: center; justify-content: space-between;
      background: rgba(255,255,255,0.04);
      border: 1px solid var(--navy-border);
      padding: 12px 16px; border-radius: 12px;
      margin-bottom: 10px; color: #fff; text-decoration: none;
      font-weight: 700; transition: 0.25s;
    }
    .social-link-item:hover {
      background: rgba(14, 165, 233, 0.15);
      border-color: var(--medical-blue);
    }

    /* قسم نموذج الحجز */
    .form-group {
      text-align: right; margin-bottom: 12px;
    }
    .form-group label {
      display: block; font-size: 12px; font-weight: 700;
      color: var(--text-muted); margin-bottom: 4px;
    }
    .form-group input, .form-group textarea {
      width: 100%; padding: 11px 12px;
      border-radius: 10px; border: 1.5px solid var(--navy-border);
      background: rgba(9, 13, 22, 0.9); color: #fff;
      font-size: 14px; font-family: inherit; outline: none;
    }
    .form-group input:focus, .form-group textarea:focus {
      border-color: var(--medical-blue);
    }

    .form-status {
      font-size: 12px; text-align: center; margin-top: 8px; min-height: 18px;
    }

    .footer {
      text-align: center; font-size: 11px; color: var(--text-muted); margin-top: 18px;
    }
  </style>
</head>
<body>

  <div class="container">
    <div class="profile-card">
      
      <!-- صورة الدكتور -->
      <div class="doctor-avatar-container">
        <img src="Dr.png" alt="د. عبدالله العواد" class="doctor-avatar" onerror="this.onerror=null; this.src='Dr.JPG';">
      </div>

      <!-- الاسم والعنوان -->
      <h1 class="doctor-title-ar">د. عبدالله العواد</h1>
      <div class="doctor-title-en">Dr. Abdullah Alawad</div>
      <div><span class="badge-label">🩺 إستشاري القسطرة العصبية</span></div>

      <!-- السيرة والتعريف الطبي -->
      <div class="bio-box">
        متخصص في علاج السكتات الدماغية، نزيف الدماغ، تشوهات الأوعية الدموية، طنين الأذن، وغيرها من الحالات المعقدة عن طريق القسطرة العصبية المتقدمة.
      </div>

      <!-- زر وسائل التواصل الاجتماعي -->
      <button class="btn-action btn-social" onclick="openSocialModal()">
        <i class="fa-solid fa-share-nodes"></i> حسابات التواصل الاجتماعي
      </button>

      <div style="height: 10px;"></div>

      <!-- نموذج الحجز الطبي -->
      <div style="border-top: 1px dashed var(--navy-border); padding-top: 16px; margin-top: 10px;">
        <h3 style="font-size: 16px; font-weight: 800; margin: 0 0 12px; color: var(--medical-blue);">
          📅 حجز موعد استشارة
        </h3>

        <div class="form-group">
          <label>اسم المريض الكامل:</label>
          <input type="text" id="patientName" placeholder="أدخل اسمك الثلاثي">
        </div>

        <div class="form-group">
          <label>رقم الجوال:</label>
          <input type="tel" id="patientPhone" placeholder="05xxxxxxxx" maxlength="10">
        </div>

        <div class="form-group">
          <label>سبب الزيارة / ملاحظات (اختياري):</label>
          <textarea id="patientNotes" rows="2" placeholder="وصف مختصر للحالة..."></textarea>
        </div>

        <div id="statusMsg" class="form-status"></div>

        <button class="btn-action btn-booking" onclick="submitBooking()">
          <i class="fa-solid fa-calendar-check"></i> تأكيد إرسال الطلب
        </button>
      </div>

    </div>

    <div class="footer">
      جميع الحقوق محفوظة &copy; 2026 | العيادة الطبية للدكتور عبدالله العواد
    </div>
  </div>

  <!-- النافذة التفاعلية لحسابات التواصل الاجتماعي -->
  <div class="modal-overlay" id="socialModal">
    <div class="modal-content">
      <h3 style="margin-top: 0; font-size: 17px; font-weight: 800; color: #fff;">حسابات التواصل الاجتماعي</h3>
      <p style="font-size: 12px; color: var(--text-muted); margin-bottom: 16px;">للتواصل والمتابعة الطبية المباشرة عبر المنصات التالية:</p>

      <a href="https://x.com/aalboridy?s=11" target="_blank" class="social-link-item">
        <span><i class="fa-brands fa-x-twitter" style="font-size: 18px; margin-left: 8px;"></i> منصة X (تويتر سابقاً)</span>
        <i class="fa-solid fa-arrow-up-right-from-square" style="font-size: 12px;"></i>
      </a>

      <a href="https://www.linkedin.com/in/dr-abdullah-alawad-alboridy-345b8726/" target="_blank" class="social-link-item">
        <span><i class="fa-brands fa-linkedin" style="font-size: 18px; color: #0a66c2; margin-left: 8px;"></i> شبكة LinkedIn</span>
        <i class="fa-solid fa-arrow-up-right-from-square" style="font-size: 12px;"></i>
      </a>

      <button class="btn-action btn-social" style="margin-top: 14px; margin-bottom:0;" onclick="closeSocialModal()">
        إغلاق
      </button>
    </div>
  </div>

  <script>
    // وضعي رابط الـ Exec الممنوح لك من Apps Script هنا
    const SCRIPT_URL = "ضعِي_رابط_السكربت_الجديد_هنا";

    function openSocialModal() {
      document.getElementById('socialModal').classList.add('active');
    }

    function closeSocialModal() {
      document.getElementById('socialModal').classList.remove('active');
    }

    function normalizeDigits(s) {
      return s.replace(/[٠-٩]/g, d => '٠١٢٣٤٥٦٧٨٩'.indexOf(d))
              .replace(/[۰-۹]/g, d => '۰۱۲۳۴۵۶۷۸۹'.indexOf(d));
    }

    function submitBooking() {
      const name = document.getElementById('patientName').value.trim();
      const phone = normalizeDigits(document.getElementById('patientPhone').value.trim());
      const notes = document.getElementById('patientNotes').value.trim();
      const statusEl = document.getElementById('statusMsg');

      if (name.length < 5) {
        statusEl.style.color = "#f87171";
        statusEl.textContent = "فضلاً ادخل الاسم الثلاثي كاملاً.";
        return;
      }

      if (!/^05\d{8}$/.test(phone)) {
        statusEl.style.color = "#f87171";
        statusEl.textContent = "يرجى إدخال رقم جوال صحيح يبدأ بـ 05.";
        return;
      }

      statusEl.style.color = "#38bdf8";
      statusEl.textContent = "جاري تسجيل الحجز...";

      fetch(SCRIPT_URL, {
        method: 'POST',
        mode: 'no-cors',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({
          name: name,
          phone: phone,
          notes: notes || "حجز جديد"
        })
      }).then(() => {
        statusEl.style.color = "#4ade80";
        statusEl.textContent = "✔ تم تسجيل الحجز بنجاح! سيتم التواصل معكم قريباً.";
        document.getElementById('patientName').value = "";
        document.getElementById('patientPhone').value = "";
        document.getElementById('patientNotes').value = "";
      }).catch(err => {
        statusEl.style.color = "#f87171";
        statusEl.textContent = "حدث خطأ أثناء الإرسال، حاول مجدداً.";
      });
    }
  </script>
</body>
</html>
