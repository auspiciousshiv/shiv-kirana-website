<!DOCTYPE html>
<html lang="hi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Shiv Kirana & General Store — Luhari Kalan</title>
<link href="https://fonts.googleapis.com/css2?family=Baloo+2:wght@600;800&family=Poppins:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --indigo: #1B3A5C;
    --marigold: #FF9F1C;
    --green: #2BAE66;
    --paper: #FFFDF8;
    --brick: #E63946;
  }
  *{margin:0;padding:0;box-sizing:border-box}
  body{background:var(--paper);font-family:'Poppins',sans-serif;color:#2A2420}
  nav{position:fixed;top:0;width:100%;background:rgba(27,58,92,0.9);backdrop-filter:blur(10px);padding:15px 20px;display:flex;justify-content:space-between;z-index:100}
 .brand{color:white;font-family:'Baloo 2';font-size:1.2rem;font-weight:800}
 .status{display:flex;align-items:center;gap:8px;color:white;font-size:0.85rem}
 .dot{width:10px;height:10px;border-radius:50%;background:var(--green);animation:pulse 2s infinite}
  @keyframes pulse{0%,100%{box-shadow:0 0 0 0 rgba(43,174,102,0.5)}50%{box-shadow:0 0 0 8px rgba(43,174,102,0)}}
 .hero{height:90vh;position:relative;overflow:hidden;display:flex;align-items:center;justify-content:center;text-align:center;color:white}
 .slides{position:absolute;top:0;left:0;width:100%;height:100%}
 .slide{position:absolute;width:100%;height:100%;background-size:cover;background-position:center;opacity:0;transition:opacity 1.5s ease-in-out}
 .slide.active{opacity:1}
 .slide::after{content:'';position:absolute;inset:0;background:linear-gradient(rgba(27,58,92,0.7),rgba(27,58,92,0.7))}
 .hero-content{position:relative;z-index:2;padding:2rem}
 .badge{display:inline-block;background:var(--marigold);color:var(--indigo);padding:6px 15px;border-radius:20px;font-weight:600;margin-bottom:15px}
 .hero-content h1{font-family:'Baloo 2';font-size:clamp(2.5rem,8vw,4rem);margin:10px 0}
 .hero-content h1 span{color:var(--marigold)}
 .hero-content p{font-size:1.1rem;opacity:0.9}
 .section{padding:4rem 1.5rem;max-width:1100px;margin:auto}
 .section h2{text-align:center;font-family:'Baloo 2';font-size:2rem;color:var(--indigo);margin-bottom:10px}
 .search{max-width:500px;margin:2rem auto}
 .search input{width:100%;padding:14px 20px;border:2px solid #ddd;border-radius:30px;font-size:1rem;outline:none}
 .search input:focus{border-color:var(--marigold)}
 .grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:20px}
 .card{background:white;border-radius:16px;padding:18px;box-shadow:0 4px 15px rgba(0,0,0,0.08);transition:transform 0.3s}
 .card:hover{transform:translateY(-5px)}
 .card.icon{font-size:2.5rem;margin-bottom:10px}
 .card h3{color:var(--indigo);margin-bottom:5px}
 .price-list{margin:10px 0}
 .price-list div{display:flex;justify-content:space-between;padding:6px 0;border-bottom:1px dashed #eee;font-size:0.9rem}
 .whatsapp-btn{background:var(--green);color:white;border:none;padding:10px;width:100%;border-radius:10px;font-weight:600;cursor:pointer}
 .float-btn{position:fixed;bottom:20px;right:20px;display:flex;flex-direction:column;gap:12px;z-index:99}
 .float-btn a{background:var(--green);color:white;padding:14px 18px;border-radius:50px;text-decoration:none;font-weight:600;box-shadow:0 5px 20px rgba(43,174,102,0.4)}
 .float-btn a.call{background:var(--brick)}
  footer{background:var(--indigo);color:white;text-align:center;padding:2rem;margin-top:3rem}
</style>
</head>
<body>

<nav>
  <div class="brand">🛒 Shiv Kirana</div>
  <div class="status"><span class="dot" id="dot"></span><span id="status">Checking...</span></div>
</nav>

<section class="hero">
  <div class="slides">
    <div class="slide active" style="background-image:url('https://images.unsplash.com/photo-1542838132-92c53300491e?q=80&w=1200')"></div>
    <div class="slide" style="background-image:url('https://images.unsplash.com/photo-1555529669-e69e7aa0ba9d?q=80&w=1200')"></div>
    <div class="slide" style="background-image:url('https://images.unsplash.com/photo-1608198093002-ad4e005484ec?q=80&w=1200')"></div>
  </div>
  <div class="hero-content">
    <div class="badge">Luhari Kalan · Bhilwara</div>
    <h1>Shiv Kirana <span>&</span> General Store</h1>
    <p>Har saman ek hi jagah • Ghar baithe Delivery Available</p>
  </div>
</section>

<section class="section">
  <h2>Hamare Products</h2>
  <div class="search"><input id="search" placeholder="🔍 Kya chahiye? Aata, Tel, Biscuit..."></div>
  <div class="grid" id="grid">
    <div class="card" data-key="atta rice dal">
      <div class="icon">🌾</div><h3>Aata, Chawal & Dal</h3>
      <div class="price-list">
        <div><span>Aata 10kg</span><b>₹380</b></div>
        <div><span>Basmati 5kg</span><b>₹450</b></div>
        <div><span>Toor Dal 1kg</span><b>₹140</b></div>
      </div>
      <button class="whatsapp-btn" onclick="order('Aata Chawal Dal')">WhatsApp Order</button>
    </div>
    <div class="card" data-key="tel masala">
      <div class="icon">🌶️</div><h3>Tel & Masale</h3>
      <div class="price-list">
        <div><span>Refined 1L</span><b>₹150</b></div>
        <div><span>Sarson Tel 1L</span><b>₹170</b></div>
        <div><span>Haldi 100g</span><b>₹35</b></div>
      </div>
      <button class="whatsapp-btn" onclick="order('Tel Masale')">WhatsApp Order</button>
    </div>
    <div class="card" data-key="biscuit chips">
      <div class="icon">🍪</div><h3>Snacks & Biscuit</h3>
      <div class="price-list">
        <div><span>Parle-G</span><b>₹10</b></div>
        <div><span>Chips</span><b>₹20</b></div>
        <div><span>Namkeen 200g</span><b>₹40</b></div>
      </div>
      <button class="whatsapp-btn" onclick="order('Snacks')">WhatsApp Order</button>
    </div>
    <div class="card" data-key="cold drink">
      <div class="icon">🥤</div><h3>Cold Drinks</h3>
      <div class="price-list">
        <div><span>Coke 750ml</span><b>₹40</b></div>
        <div><span>Juice 200ml</span><b>₹20</b></div>
        <div><span>Water 1L</span><b>₹20</b></div>
      </div>
      <button class="whatsapp-btn" onclick="order('Cold Drinks')">WhatsApp Order</button>
    </div>
  </div>
</section>

<div class="float-btn">
  <a href="https://wa.me/919950148618?text=Namaste%20Shiv%20Kirana%20se%20order%20karna%20hai" target="_blank">💬 WhatsApp</a>
  <a href="tel:+919950148618" class="call">📞 Call</a>
</div>

<footer>
  <p>📍 Luhari Kalan Rd, near PHC, Luhari Khurd, Rajasthan 311201</p>
  <p>📞 +91 99501 48618 | ⏰ Subah 6:30 se Raat 9:30</p>
  <p style="margin-top:10px;opacity:0.7">© 2026 Shiv Kirana & General Store</p>
</footer>

<script>
  let currentSlide = 0;
  const slides = document.querySelectorAll('.slide');
  setInterval(() => {
    slides[currentSlide].classList.remove('active');
    currentSlide = (currentSlide + 1) % slides.length;
    slides[currentSlide].classList.add('active');
  }, 4000);
  function status(){
    let h=new Date().getHours();
    let open=h>=6.5 && h<21.5;
    document.getElementById('dot').style.background=open?'#2BAE66':'#E63946';
    document.getElementById('status').textContent=open?'Open Now':'Closed Now';
  }
  status();setInterval(status,60000);
  document.getElementById('search').oninput=e=>{
    let q=e.target.value.toLowerCase();
    document.querySelectorAll('.card').forEach(c=>{
      c.style.display=c.dataset.key.includes(q)?'block':'none';
    })
  }
  function order(item){
    window.open(`https://wa.me/919950148618?text=Namaste,%20mujhe%20${item}%20chahiye%20Shiv%20Kirana%20se`);
  }
</script>

</body>
</html>
