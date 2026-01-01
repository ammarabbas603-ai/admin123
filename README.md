<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<title>سما بغداد</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body {
  margin:0;
  font-family: Arial, sans-serif;
  background:#f5f5f5;
  direction: rtl;
}

header {
  background:#222;
  color:#fff;
  padding:15px;
  text-align:center;
}

nav a {
  color:#fff;
  margin:0 10px;
  text-decoration:none;
  font-weight:bold;
}

section {
  padding:30px;
}

.products {
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
  gap:20px;
}

.card {
  background:#fff;
  padding:15px;
  border-radius:10px;
  box-shadow:0 2px 6px rgba(0,0,0,.1);
  text-align:center;
}

.card img {
  width:100%;
  border-radius:10px;
}

.card h3 {
  margin:10px 0;
}

.btn {
  display:inline-block;
  margin:5px;
  padding:10px 15px;
  border-radius:8px;
  color:#fff;
  text-decoration:none;
}

.whatsapp {
  background:#25D366;
}

.call {
  background:#007bff;
}

/* أزرار ثابتة */
.floating-buttons {
  position: fixed;
  bottom: 20px;
  right: 20px;
  display:flex;
  flex-direction:column;
  gap:10px;
  z-index:9999;
}

.floating-buttons a {
  width:55px;
  height:55px;
  border-radius:50%;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:26px;
  color:#fff;
  text-decoration:none;
  box-shadow:0 4px 8px rgba(0,0,0,.3);
}

footer {
  background:#222;
  color:#fff;
  text-align:center;
  padding:15px;
}
</style>
</head>

<body>

<header>
  <h1>🛍️ سما بغداد</h1>
  <nav>
    <a href="#home">الرئيسية</a>
    <a href="#products">المنتجات</a>
    <a href="#contact">تواصل معنا</a>
  </nav>
</header>

<section id="home">
  <h2>مرحبًا بكم</h2>
  <p>نقدم لكم أفضل المنتجات بأسعار مناسبة. للطلب تواصل معنا مباشرة.</p>
</section>

<section id="products">
  <h2>المنتجات</h2>
  <div class="products">

    

    <div class="card">
      <img src="https://via.placeholder.com/300" alt="منتج">
      <h3>اسم المنتج</h3>

    
      <a class="btn whatsapp" href="https://wa.me/9647700034404">واتساب</a>
      <a class="btn call" href="tel:07700034404">اتصال</a>
    </div>

  </div>
</section>

<section id="contact">
  <h2>تواصل معنا</h2>
  <p>📞 الهاتف: 07700034404</p>
  <p>📧 البريد: samabaghdad125@gmail.com</p>
  <p>📍 العنوان: بغداد – عويريج</p>
</section>

<footer>
  <p>© 2026 سما بغداد</p>
</footer>

<!-- أزرار ثابتة -->
<div class="floating-buttons">
  <a class="whatsapp" href="https://wa.me/9647700034404" target="_blank">💬</a>
  <a class="call" href="tel:07700034404">📞</a>
</div>

</body>
</html>

