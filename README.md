<!DOCTYPE html>?
<!-- <head>
<meta charset="UTF-8"> -->
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Graphic Cafe - پلیر موزیک حرفه‌ای</title>
<style>
* { margin:0; padding:0; box-sizing:border-box; }

body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background: linear-gradient(135deg, #0d0d0d, #1a1a2e);
  color: #0f0505;
  line-height: 1.6;
}


/* 
.player-box {
    width: 90%;
    max-width: 420px;
    background: #111;
    padding: 25px;
    border-radius: 22px;
    text-align: center;
    transform: rotateY(-12deg) rotateX(6deg);
    transition: 0.8s;
    box-shadow:
      0 25px 40px rgba(0,0,0,0.6),
      inset 0 0 30px rgba(0,255,70,0.15);
  } */
/* 
  .player-box:hover {
    transform: rotateY(0deg) rotateX(0deg) scale(1.03);
    box-shadow:
      0 35px 60px rgba(0,0,0,0.7),
      inset 0 0 40px rgba(0,255,70,0.25);
  }

  .cover {
    width: 100%;
    border-radius: 18px;
    overflow: hidden;
    margin-bottom: 20px;
    box-shadow: 0 10px 20px rgba(0,255,70,0.3);
  } */

/* هدر */
header {
  width: 100%;
  padding: 20px 0;
  text-align: center;
  background: rgba(0,0,0,0.4);
  backdrop-filter: blur(10px);
  position: sticky;
  top: 0;
  z-index: 100;
}
header h1 { font-size: 28px; color: #00ffc1; text-shadow:0 0 8px #00ffc1; }

/* بخش اصلی */
main { display: flex; flex-direction: column; align-items: center; padding: 50px 20px; }

/* پلیر موزیک */
.player-box {
  width: 100%;
  max-width: 480px;
  background: rgba(255,255,255,0.05);
  backdrop-filter: blur(28px);
  border-radius: 40px;
  padding: 40px 35px;
  text-align: center;
  box-shadow: 0 25px 80px rgba(0,0,0,0.7), 0 0 50px rgba(0,255,160,0.2);
  border: 1px solid rgba(255,255,255,0.1);
  position: relative;
  overflow: hidden;
  transition: all 0.4s ease;
  margin-bottom: 50px;
}
.player-box::before {
  content: '';
  position: absolute;
  top: -50%;
  left: -50%;
  width: 200%;
  height: 200%;
  background: radial-gradient(circle at center, rgba(0,255,160,0.15), transparent 70%);
  animation: rotateBg 8s linear infinite;
  z-index: 0;
}
@keyframes rotateBg {0%{transform:rotate(0deg);}100%{transform:rotate(360deg);}}

/* اسم آهنگ */
h1{
  background: linear-gradient(90deg,#00ffc1,#1db954,#00ffc1);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  font-weight: 800;
  font-size: 30px;
  margin-bottom: 12px;
  text-shadow: 0 0 15px rgba(0,255,160,0.4);
  position: relative; z-index: 1;
  animation: shine 2s linear infinite;
}
@keyframes shine {0%{background-position:0% 50%;}100%{background-position:200% 50%;}}

p { color:#cfcfcf; font-size:15px; margin:0 0 25px 0; line-height:1.5; position:relative; z-index:1; }

/* موج صوتی */
.wave {
  display:flex;
  justify-content:center;
  align-items:flex-end;
  margin:30px 0;
  position:relative;
  z-index:1;
}
.wave div {
  width:8px; height:20px;
  margin:0 4px;
  background:linear-gradient(to top,#1db954,#00ffc1);
  border-radius:5px;
  animation:waveAnim 1s infinite ease-in-out;
}
.wave div:nth-child(2){animation-delay:0.1s;} 
.wave div:nth-child(3){animation-delay:0.2s;}
.wave div:nth-child(4){animation-delay:0.3s;} 
.wave div:nth-child(5){animation-delay:0.4s;}
@keyframes waveAnim {0%{height:15px;}50%{height:60px;}100%{height:15px;}}

audio { width:100%; outline:none; border-radius:22px; margin-top:20px; box-shadow:0 8px 25px rgba(0,0,0,0.5); z-index:1; position:relative; }

.site-link { margin-top:25px; font-size:14px; color:#00ffa1; line-height:1.5; text-shadow:0 0 8px #00ffa1; font-weight:500; position:relative; z-index:1; transition:all 0.3s ease; }
.site-link:hover { color:#1db954; text-shadow:0 0 15px #1db954,0 0 25px #00ffc1; }

.animated-name {
  margin:40px 0 0 0; font-size:44px; font-weight:900;
  background:linear-gradient(90deg,#00ffc1,#1db954,#00ffc1);
  -webkit-background-clip:text; -webkit-text-fill-color:transparent;
  text-transform:uppercase; letter-spacing:1px;
  text-shadow:0 0 20px #00ffa1,0 0 40px #1db954;
  animation:pulse 1.5s infinite alternate,glow 2s infinite alternate,shine 2s linear infinite;
  position:relative; z-index:1;
}
@keyframes pulse{0%{transform:scale(1);}50%{transform:scale(1.28) rotate(-1deg);}100%{transform:scale(1);}}
@keyframes glow{0%{text-shadow:0 0 5px #00ffa1,0 0 10px #00ffa1,0 0 25px #1db954;}50%{text-shadow:0 0 25px #00ffa1,0 0 45px #00ffa1,0 0 60px #1db954;}100%{text-shadow:0 0 5px #00ffa1,0 0 10px #00ffa1,0 0 25px #1db954;}}
@keyframes shine{0%{background-position:0% 50%;}100%{background-position:200% 50%;}}
.player-box:hover{transform:translateY(-10px);box-shadow:0 35px 90px rgba(0,0,0,0.85),0 0 70px rgba(0,255,160,0.5);}

/* گالری موزیک‌ها */
.gallery {
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(140px,1fr));
  gap:20px;
  width:100%;
  max-width:900px;
  margin-bottom:50px;
}
.gallery .item {
  background:rgba(255,255,255,0.05);
  backdrop-filter:blur(15px);
  border-radius:20px;
  padding:15px;
  text-align:center;
  transition:transform 0.3s, box-shadow 0.3s;
  cursor:pointer;
}
.gallery .item:hover { transform:translateY(-5px); box-shadow:0 15px 40px rgba(0,255,160,0.5);}
.gallery img { width:100%; border-radius:15px; margin-bottom:10px; }
.gallery button { background:#1db954; border:none; padding:8px 15px; border-radius:12px; color:#fff; cursor:pointer; transition:0.3s;}
.gallery button:hover{background:#00ffc1;}

/* اشتراک اجتماعی */
.social {
  display:flex;
  gap:15px;
  margin-bottom:50px;
}
.social a {
  display:flex; justify-content:center; align-items:center;
  width:45px; height:45px;
  background:rgba(46, 148, 43, 0.05);
  border-radius:50%;
  color:#13a17e;
  font-size:20px;
  text-decoration:none;
  transition:0.3s;
}
.social a:hover { background:#1db954; color:#fff; transform:scale(1.1); }

/* فوتر */
footer { width:100%; padding:25px 0; text-align:center; background: rgba(0,0,0,0.4); backdrop-filter:blur(10px); font-size:14px; color:#00ffc1; position:relative; z-index:1; }
footer a { color:#1db954; text-decoration:none; font-weight:600; }
footer a:hover { text-shadow:0 0 10px #316b5d; }

/* ریسپانسیو */
@media(max-width:600px){ h2{font-size:26px;} .animated-name{font-size:36px;} .player-box{padding:30px 20px;} .gallery{grid-template-columns:repeat(auto-fit,minmax(120px,1fr));} }
</style>
</head>
<body>

<header>
  <h1>Graphic Cafe</h1>
</header>

<main>
  <!-- پلیر اصلی -->
  <div class="player-box" id="mainPlayer">
    <h1>Happy birthday my friend</h1>
   
    <div class="wave"><div></div><div></div><div></div><div></div><div></div></div>
    <audio controls id="mainAudio">
      <source src="Miram Bala Salamti (Remix) ( GandomMusic.ir ).mp3" type="audio/mpeg">
    </audio>
   
    <div class="animated-name">اسما</div>
  </div>
 <div class="site-link" style="color: #45e99c; text-align: center;">
     
     جهت سفارش بیشتر و دیدن نمونه‌ها با این شماره تماس بگیرید یا به ایدی درج شده در تلگرام پیام بدید 
     <br>
     
      
      <strong>09907069965
         <br>
          
        @charlotte_0990  <br>
        هستیمCafeGraphic منتظر سفارشات جذابتون در 
      </strong>
    </div>
  <!-- گالری موزیک‌ها
  <div class="gallery">
    <div class="item" data-src="music1.mp3" data-title="آهنگ ۱" data-text="متن آهنگ ۱">
      <img src="album1.jpg" alt="آلبوم ۱">
      <button>پخش</button>
    </div>
    <div class="item" data-src="music2.mp3" data-title="آهنگ ۲" data-text="متن آهنگ ۲">
      <img src="album2.jpg" alt="آلبوم ۲">
      <button>پخش</button>
    </div>
    <div class="item" data-src="music3.mp3" data-title="آهنگ ۳" data-text="متن آهنگ ۳">
      <img src="album3.jpg" alt="آلبوم ۳">
      <button>پخش</button>
    </div>
    <div class="item" data-src="music4.mp3" data-title="آهنگ ۴" data-text="متن آهنگ ۴">
      <img src="album4.jpg" alt="آلبوم ۴">
      <button>پخش</button>
    </div>
  </div> -->

  <!-- اشتراک اجتماعی
  <div class="social">
    <a href="#"><i>F</i></a>
    <a href="#"><i>T</i></a>
    <a href="#"><i>I</i></a>
  </div> -->
</main>

<footer>
  © 2025  Cafe-Graphic | <a href="tel:09907069965">تماس با ما</a>
</footer>

<script>
// جاوااسکریپت برای پخش موزیک انتخاب شده
const galleryItems = document.querySelectorAll('.gallery .item');
const mainAudio = document.getElementById('mainAudio');
const mainTitle = document.querySelector('#mainPlayer h2');
const mainText = document.querySelector('#mainPlayer p');

galleryItems.forEach(item => {
  item.addEventListener('click', () => {
    const src = item.getAttribute('data-src');
    const title = item.getAttribute('data-title');
    const text = item.getAttribute('data-text');

    mainAudio.src = src;
    mainAudio.play();
    mainTitle.textContent = title;
    mainText.textContent = text;
  });
});
</script>

</body>
</html>
