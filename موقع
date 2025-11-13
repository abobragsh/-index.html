<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <title>موقعنا الحديث – نسخة تفاعلية</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <!-- خطوط Google -->
  <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;600;900&display=swap" rel="stylesheet">

  <style>
    /*========= 1. إعدادات عامة =========*/
    :root{
      --primary:#00c2ff;
      --dark:#0a0f1a;
      --light:#ffffff;
      --gray:#b0b8c5;
      --radius:12px;
      --transition:.45s cubic-bezier(.25,.8,.25,1);
    }
    *{
      margin:0;
      padding:0;
      box-sizing:border-box;
    }
    body{
      font-family:'Cairo',sans-serif;
      background:var(--dark);
      color:var(--light);
      overflow-x:hidden;
      scroll-behavior: smooth;
    }
    section{
      min-height:100vh;
      display:flex;
      align-items:center;
      justify-content:center;
      padding:4rem 1rem;
      position:relative;
    }
    .container{
      width:100%;
      max-width:1100px;
      margin:auto;
    }
    h1,h2,h3{ font-weight:900; margin-bottom:1rem; line-height:1.3;}
    p{ line-height:1.7; margin-bottom:1.5rem;}
    img{ max-width:100%; display:block;}
    .btn{
      background:var(--primary);
      color:#fff;
      border:none;
      padding:.9rem 2.2rem;
      border-radius:var(--radius);
      font-size:1.1rem;
      cursor:pointer;
      transition:var(--transition);
      transform:translateY(0);
    }
    .btn:hover{ transform:translateY(-4px); box-shadow:0 10px 25px rgba(0,194,255,.35); }

    /*========= 2. الهيدر =========*/
    header{
      position:fixed;
      top:0; left:0; right:0;
      padding:1rem 2rem;
      z-index:1000;
      transition:var(--transition);
    }
    header.scrolled{ background:rgba(10,15,26,.85); backdrop-filter:blur(10px);}
    nav{
      display:flex;
      align-items:center;
      justify-content:space-between;
    }
    .logo{ font-size:1.5rem; font-weight:900; color:var(--primary);}
    .nav-links{
      list-style:none;
      display:flex;
      gap:1.5rem;
    }
    .nav-links a{
      color:var(--light);
      text-decoration:none;
      position:relative;
      padding:.25rem 0;
    }
    .nav-links a::after{
      content:'';
      position:absolute;
      bottom:0; right:0; width:0; height:2px;
      background:var(--primary);
      transition:width var(--transition);
    }
    .nav-links a.active::after,
    .nav-links a:hover::after{ width:100%;}
    .hamburger{
      display:none;
      flex-direction:column;
      gap:5px;
      cursor:pointer;
    }
    .hamburger span{
      width:28px;
      height:3px;
      background:var(--light);
      border-radius:2px;
      transition:var(--transition);
    }

    /*========= 3. Hero Section =========*/
    #hero{
      background:url('https://source.unsplash.com/random/1920x1080?technology,dark') center/cover no-repeat;
      position:relative;
    }
    #hero::after{
      content:'';
      position:absolute;
      inset:0;
      background:rgba(10,15,26,.65);
    }
    .hero-content{
      position:relative;
      z-index:2;
      text-align:center;
      animation:fadeUp 1s ease forwards;
    }
    @keyframes fadeUp{
      from{ opacity:0; transform:translateY(40px);}
      to{ opacity:1; transform:translateY(0);}
    }
    .hero-content h1{ font-size:clamp(2.2rem,5vw,4rem);}
    .hero-content p{ font-size:1.2rem; color:var(--gray);}

    /*========= 4. معرض الصور =========*/
    .gallery{
      display:grid;
      grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
      gap:1.2rem;
    }
    .gallery-item{
      position:relative;
      overflow:hidden;
      border-radius:var(--radius);
      cursor:pointer;
      transition:var(--transition);
    }
    .gallery-item img{
      transition:var(--transition);
      filter:brightness(.75);
    }
    .gallery-item:hover img{ transform:scale(1.1); filter:brightness(1);}
    .overlay{
      position:absolute;
      inset:0;
      background:rgba(0,0,0,.55);
      display:flex;
      align-items:flex-end;
      padding:1.2rem;
      opacity:0;
      transition:opacity var(--transition);
    }
    .gallery-item:hover .overlay{ opacity:1;}
    .overlay h3{ margin:0; font-size:1.1rem;}

    /*========= 5. الأرقام المتحركة =========*/
    .stats{
      display:flex;
      gap:2rem;
      flex-wrap:wrap;
      justify-content:center;
    }
    .stat-box{
      text-align:center;
      flex:1 1 180px;
    }
    .stat-box h2{
      font-size:2.5rem;
      color:var(--primary);
    }
    .stat-box p{ color:var(--gray);}

    /*========= 6. النموذج التدريجي =========*/
    .form-wrapper{
      background:rgba(255,255,255,.04);
      padding:2rem;
      border-radius:var(--radius);
      max-width:600px;
      margin:auto;
    }
    .form-field{
      margin-bottom:1.2rem;
      opacity:0;
      transform:translateY(20px);
      animation:fadeIn .6s ease forwards;
    }
    @keyframes fadeIn{ to{ opacity:1; transform:translateY(0);}}
    .form-field label{ display:block; margin-bottom:.4rem; color:var(--gray);}
    .form-field input,
    .form-field textarea{
      width:100%;
      padding:.9rem 1rem;
      border:1px solid var(--gray);
      background:transparent;
      color:var(--light);
      border-radius:var(--radius);
      transition:border-color var(--transition);
    }
    .form-field input:focus,
    .form-field textarea:focus{
      outline:none;
      border-color:var(--primary);
    }
    .error{ border-color:#ff4d4d !important;}
    .success-msg{
      display:none;
      text-align:center;
      color:#4dffb4;
      margin-top:1rem;
    }

    /*========= 7. Modal Gallery =========*/
    .modal{
      position:fixed;
      inset:0;
      background:rgba(0,0,0,.85);
      display:flex;
      align-items:center;
      justify-content:center;
      z-index:2000;
      opacity:0;
      pointer-events:none;
      transition:opacity var(--transition);
    }
    .modal.active{ opacity:1; pointer-events:auto;}
    .modal img{ max-height:85vh; border-radius:var(--radius);}
    .modal-close{
      position:absolute;
      top:2rem; right:2rem;
      font-size:2.2rem;
      color:#fff;
      cursor:pointer;
      transition:transform var(--transition);
    }
    .modal-close:hover{ transform:rotate(90deg);}

    /*========= 8. responsive =========*/
    @media(max-width:768px){
      .nav-links{ display:none;}
      .hamburger{ display:flex;}
    }
  </style>
</head>

<body>

  <!--========= الهيدر =========-->
  <header id="header">
    <nav class="container">
      <div class="logo">موقعنا</div>
      <ul class="nav-links">
        <li><a href="#hero" class="nav-link active">الرئيسية</a></li>
        <li><a href="#services" class="nav-link">خدماتنا</a></li>
        <li><a href="#about" class="nav-link">من نحن</a></li>
        <li><a href="#contact" class="nav-link">تواصل</a></li>
      </ul>
      <div class="hamburger" id="hamburger">
        <span></span><span></span><span></span>
      </div>
    </nav>
  </header>

  <!--========= Hero Section =========-->
  <section id="hero">
    <div class="hero-content">
      <h1>نصنع أفكارك رقمية</h1>
      <p>حلول تقنية مبتكرة مع تجربة مستخدم لا تُنسى</p>
      <button class="btn" onclick="scrollToSection('#contact')">ابدأ الآن</button>
    </div>
  </section>

  <!--========= Services / Gallery =========-->
  <section id="services">
    <div class="container">
      <h2>أعمالنا</h2>
      <div class="gallery" id="gallery">
        <!-- يتم ملؤه ديناميكياً -->
      </div>
    </div>
  </section>

  <!--========= About / Stats =========-->
  <section id="about">
    <div class="container">
      <h2>إحصائياتنا</h2>
      <div class="stats">
        <div class="stat-box">
          <h2 data-target="250">0</h2>
          <p>عميل سعيد</p>
        </div>
        <div class="stat-box">
          <h2 data-target="1200">0</h2>
          <p>مشروع مُنجز</p>
        </div>
        <div class="stat-box">
          <h2 data-target="15">0</h2>
          <p>عام من الخبرة</p>
        </div>
      </div>
    </div>
  </section>

  <!--========= Contact =========-->
  <section id="contact">
    <div class="container">
      <h2>تواصل معنا</h2>
      <div class="form-wrapper">
        <form id="contactForm" novalidate>
          <div class="form-field" style="animation-delay:.1s">
            <label>الاسم الكامل</label>
            <input type="text" name="name" required>
            <span class="error-msg"></span>
          </div>
          <div class="form-field" style="animation-delay:.2s">
            <label>البريد الإلكتروني</label>
            <input type="email" name="email" required>
            <span class="error-msg"></span>
          </div>
          <div class="form-field" style="animation-delay:.3s">
            <label>الرسالة</label>
            <textarea name="message" rows="4" required></textarea>
            <span class="error-msg"></span>
          </div>
          <button type="submit" class="btn">إرسال</button>
          <div class="success-msg">تم الإرسال بنجاح! ✨</div>
        </form>
      </div>
    </div>
  </section>

  <!--========= Modal Gallery =========-->
  <div class="modal" id="modal">
    <span class="modal-close" id="modalClose">&times;</span>
    <img src="" alt="" id="modalImg">
  </div>

  <!--========= JavaScript =========-->
  <script>
    /*------------- 1. متغيرات عامة -------------*/
    const header     = document.getElementById('header');
    const navLinks   = document.querySelectorAll('.nav-link');
    const hamburger  = document.getElementById('hamburger');
    const gallery    = document.getElementById('gallery');
    const modal      = document.getElementById('modal');
    const modalImg   = document.getElementById('modalImg');
    const modalClose = document.getElementById('modalClose');
    const form       = document.getElementById('contactForm');

    /*------------- 2. وضع صور عشوائية بالمعرض -------------*/
    const imgs = [];
    for(let i=0;i<6;i++){
      imgs.push(`https://source.unsplash.com/random/800x600?technology,${i}`);
    }
    gallery.innerHTML = imgs.map(src=>`
      <div class="gallery-item">
        <img src="${src}" alt="عمل">
        <div class="overlay"><h3>مشروع مميز</h3></div>
      </div>`).join('');

    /*------------- 3. فتح/غلق المودال -------------*/
    const galleryItems = document.querySelectorAll('.gallery-item img');
    galleryItems.forEach(img=>{
      img.addEventListener('click',()=>{
        modalImg.src = img.src;
        modal.classList.add('active');
      });
    });
    modalClose.addEventListener('click',()=> modal.classList.remove('active'));
    modal.addEventListener('click',e=>{ if(e.target===modal) modal.classList.remove('active'); });

    /*------------- 4. تغيير خلفية الهيدر عند التمرير -------------*/
    window.addEventListener('scroll',()=>{
      header.classList.toggle('scrolled', window.scrollY > 50);
    });

    /*------------- 5. تحديث الروابط النشطة -------------*/
    const sections = document.querySelectorAll('section');
    window.addEventListener('scroll',()=>{
      let cur = '';
      sections.forEach(sec=>{
        const top = sec.offsetTop - 100;
        if(scrollY >= top) cur = sec.getAttribute('id');
      });
      navLinks.forEach(link=>{
        link.classList.toggle('active', link.getAttribute('href').slice(1) === cur);
      });
    });

    /*------------- 6. عداد الأرقام عند الظهور -------------*/
    const counters = document.querySelectorAll('.stat-box h2');
    const speed = 200;
    const countUp = (el)=>{
      const target = +el.getAttribute('data-target');
      const increment = target / speed;
      const update = ()=>{
        const count = +el.innerText;
        if(count < target){
          el.innerText = Math.ceil(count + increment);
          setTimeout(update,20);
        }else{
          el.innerText = target;
        }
      };
      update();
    };
    const obsOptions = { threshold:.6 };
    const observer = new IntersectionObserver((entries)=>{
      entries.forEach(ent=>{
        if(ent.isIntersecting){
          countUp(ent.target);
          observer.unobserve(ent.target);
        }
      });
    },obsOptions);
    counters.forEach(c=> observer.observe(c));

    /*------------- 7. التحقق من صحة النموذج -------------*/
    const fields = form.querySelectorAll('[required]');
    const showError = (input,msg)=>{
      input.classList.add('error');
      input.nextElementSibling.textContent = msg;
    };
    const clearError = (input)=>{
      input.classList.remove('error');
      input.nextElementSibling.textContent = '';
    };
    const validate = {
      name:  v => v.length >= 3 || 'الاسم يجب أن يكون 3 أحرف على الأقل',
      email: v => /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(v) || 'بريد غير صحيح',
      message:v => v.length >= 10 || 'أكتب رسالة أطول'
    };
    fields.forEach(input=>{
      input.addEventListener('blur',()=>{
        const rule = validate[input.name];
        if(rule && !rule(input.value)) showError(input,rule(input.value));
        else clearError(input);
      });
      input.addEventListener('focus',()=> clearError(input));
    });

    /*------------- 8. إرسال النموذج -------------*/
    form.addEventListener('submit',e=>{
      e.preventDefault();
      let valid = true;
      fields.forEach(inp=>{
        const rule = validate[inp.name];
        if(rule && !rule(inp.value)){ showError(inp,rule(inp.value)); valid=false;}
      });
      if(!valid) return;
      // محاكاة إرسال
      form.style.display = 'none';
      document.querySelector('.success-msg').style.display = 'block';
    });

    /*------------- 9. سكرول سلس عند الضغط على الروابط -------------*/
    const scrollToSection = selector => {
      document.querySelector(selector).scrollIntoView({ behavior:'smooth' });
    };
    navLinks.forEach(link=>{
      link.addEventListener('click',e=>{
        e.preventDefault();
        scrollToSection(link.getAttribute('href'));
      });
    });

    /*------------- 10. قائمة الموبايل -------------*/
    hamburger.addEventListener('click',()=>{
      document.querySelector('.nav-links').classList.toggle('open');
    });

  </script>
</body>
</html>
