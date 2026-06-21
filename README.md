# HOX3
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>HØX</title>

<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;700;900&display=swap" rel="stylesheet">

<style>

/* ================= RESET ================= */
*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:'Inter',sans-serif;
}

html{
scroll-behavior:smooth;
}

body{
background:#050505;
color:white;
overflow-x:hidden;
cursor:none;
}

/* ================= BACKGROUND ================= */
.bg{
position:fixed;
inset:0;
z-index:-2;
background:
radial-gradient(circle at 20% 30%, rgba(255,0,0,.12), transparent 35%),
radial-gradient(circle at 80% 70%, rgba(255,0,0,.08), transparent 40%),
#050505;
}

/* noise layer */
.bg::after{
content:"";
position:absolute;
inset:0;
background-image:url("https://www.transparenttextures.com/patterns/noise.png");
opacity:.04;
}

/* ================= CURSOR ================= */
.cursor{
position:fixed;
width:14px;
height:14px;
border-radius:50%;
background:#ff2a2a;
transform:translate(-50%,-50%);
pointer-events:none;
z-index:9999;
box-shadow:0 0 20px rgba(255,0,0,.6);
}

/* ================= INTRO ================= */
#intro{
position:fixed;
inset:0;
display:flex;
justify-content:center;
align-items:center;
background:#050505;
z-index:99999;
}

.intro-text{
font-size:clamp(3rem,10vw,8rem);
font-weight:900;
letter-spacing:14px;
animation:zoom 1.2s ease;
}

@keyframes zoom{
from{transform:scale(.6);opacity:0;}
to{transform:scale(1);opacity:1;}
}

/* ================= NAV ================= */
nav{
position:fixed;
top:0;
width:100%;
padding:25px 8%;
display:flex;
justify-content:space-between;
align-items:center;
backdrop-filter:blur(20px);
background:rgba(0,0,0,.25);
z-index:1000;
}

.logo{
font-size:28px;
font-weight:900;
letter-spacing:5px;
}

.menu{
display:flex;
gap:30px;
}

.menu a{
color:white;
text-decoration:none;
opacity:.7;
transition:.3s;
}

.menu a:hover{
opacity:1;
color:#ff2a2a;
}

/* ================= HERO ================= */
.hero{
height:100vh;
display:flex;
justify-content:center;
align-items:center;
text-align:center;
padding:20px;
}

.hero h1{
font-size:clamp(4rem,10vw,9rem);
font-weight:900;
}

.hero p{
margin-top:20px;
opacity:.85;
line-height:1.8;
max-width:700px;
}

/* ================= SECTIONS ================= */
section{
padding:120px 8%;
}

/* TITLE */
.title{
font-size:3rem;
margin-bottom:40px;
position:relative;
}

.title::after{
content:"";
position:absolute;
bottom:-10px;
left:0;
width:70px;
height:3px;
background:#ff2a2a;
}

/* ================= ABOUT ================= */
.about-text p{
line-height:2;
opacity:.9;
font-size:1.05rem;
}

/* ================= CONTACT ================= */
.contact-box{
display:flex;
flex-wrap:wrap;
gap:25px;
}

.contact-card{
flex:1;
min-width:260px;
padding:30px;
border-radius:20px;
background:rgba(255,255,255,.03);
border:1px solid rgba(255,255,255,.05);
transition:.3s;
}

.contact-card:hover{
transform:translateY(-6px);
box-shadow:0 0 25px rgba(255,0,0,.2);
}

/* ================= REVEAL ================= */
.reveal{
opacity:0;
transform:translateY(40px);
filter:blur(6px);
}

.reveal.show{
opacity:1;
transform:translateY(0);
filter:blur(0);
transition:1s ease;
}

/* ================= FOOTER ================= */
footer{
padding:50px;
text-align:center;
opacity:.5;
}

/* ================= RESPONSIVE ================= */
@media(max-width:900px){
.menu{display:none;}
}

</style>
</head>

<body>

<!-- INTRO -->
<div id="intro">
<div class="intro-text">HØX</div>
</div>

<div class="cursor"></div>
<div class="bg"></div>

<!-- NAV -->
<nav>
<div class="logo">HØX</div>
<div class="menu">
<a href="#about">About</a>
<a href="#contact">Contact</a>
</div>
</nav>

<!-- HERO -->
<section class="hero">
<div>
<h1 class="reveal">HØX</h1>
<p class="reveal">
لا أسعى للفت الانتباه... بل أسعى لصناعة شيء يستحق أن يُتذكر.
</p>
</div>
</section>

<!-- ABOUT -->
<section id="about">
<h2 class="title reveal">About</h2>

<p class="reveal">
HØX

أنا حسن.

في عالمٍ يتشابه فيه الكثيرون، أفضّل أن أصنع طريقي الخاص. شغفي بالتصميم والأنمي دفعني إلى بناء أعمال تعكس القوة، الدقة، والتفاصيل التي يصعب تجاهلها. هذا الموقع هو مساحة تجمع أفكاري وإبداعي، حيث تتحول الرؤية إلى واقع، وتتحول الفكرة إلى عمل يترك أثره.

لا أسعى للفت الانتباه... بل أسعى لصناعة شيء يستحق أن يُتذكر.
</p>
</section>

<!-- CONTACT -->
<section id="contact">
<h2 class="title reveal">Contact</h2>

<div class="contact-box">

<div class="contact-card reveal">
<h3>TikTok</h3>
<a href="https://tiktok.com/@hox0.10">@hox0.10</a>
</div>

<div class="contact-card reveal">
<h3>Discord</h3>
hsnx_313
</div>

</div>
</section>

<footer class="reveal">© HØX</footer>

</body>
</html>
<script>

/* ================= CURSOR FOLLOW ================= */
const cursor = document.querySelector(".cursor");

document.addEventListener("mousemove",(e)=>{
cursor.style.left = e.clientX + "px";
cursor.style.top = e.clientY + "px";
});

/* ================= REVEAL ON SCROLL ================= */
const observer = new IntersectionObserver((entries)=>{
entries.forEach(entry=>{
if(entry.isIntersecting){
entry.target.classList.add("show");
}
});
});

document.querySelectorAll(".reveal").forEach(el=>{
observer.observe(el);
});

/* ================= INTRO REMOVE ================= */
setTimeout(()=>{
document.getElementById("intro").style.opacity = "0";
document.getElementById("intro").style.transition = "1s ease";

setTimeout(()=>{
document.getElementById("intro").remove();
},1000);

},2200);

/* ================= CLICK RIPPLE ================= */
document.addEventListener("click",(e)=>{
const ripple = document.createElement("div");

ripple.style.position = "fixed";
ripple.style.left = e.clientX + "px";
ripple.style.top = e.clientY + "px";
ripple.style.width = "10px";
ripple.style.height = "10px";
ripple.style.borderRadius = "50%";
ripple.style.background = "rgba(255,42,42,0.6)";
ripple.style.transform = "translate(-50%,-50%)";
ripple.style.animation = "rippleAnim .6s ease-out forwards";
ripple.style.zIndex = "9999";

document.body.appendChild(ripple);

setTimeout(()=>ripple.remove(),600);
});

/* ================= SOUND SYSTEM ================= */
const clickSound = new Audio("https://cdn.pixabay.com/download/audio/2022/03/01/audio_6b4d8b1d1b.mp3");
const introSound = new Audio("https://cdn.pixabay.com/download/audio/2022/03/15/audio_c8a1f3b7d7.mp3");

clickSound.volume = 0.4;
introSound.volume = 0.6;

/* تشغيل صوت عند أول تفاعل */
let started = false;

function startAudio(){
if(started) return;
started = true;

introSound.play().catch(()=>{});
}

document.addEventListener("click", startAudio);

/* ================= CLICK SOUND ================= */
document.addEventListener("click", ()=>{
clickSound.currentTime = 0;
clickSound.play().catch(()=>{});
});

/* ================= SMOOTH NAV CLICK ================= */
document.querySelectorAll("a").forEach(link=>{
link.addEventListener("click", ()=>{
clickSound.currentTime = 0;
clickSound.play().catch(()=>{});
});
});

/* ================= SMALL FX ================= */
document.addEventListener("mousemove",(e)=>{
cursor.style.transform = "translate(-50%,-50%) scale(1.2)";
setTimeout(()=>{
cursor.style.transform = "translate(-50%,-50%) scale(1)";
},80);
});

</script>

<style>

/* ripple animation */
@keyframes rippleAnim{
to{
transform:translate(-50%,-50%) scale(14);
opacity:0;
}
}

</style>
