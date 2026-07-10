<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>رسالة ❤️</title>

<style>
body {
    margin: 0;
    height: 100vh;
    overflow: hidden;
    background: linear-gradient(135deg, #ff9a9e, #fad0c4);
    font-family: Arial;
    display: flex;
    justify-content: center;
    align-items: center;
}

.box {
    background: rgba(255,255,255,0.9);
    padding: 30px;
    border-radius: 25px;
    text-align: center;
    width: 80%;
    max-width: 400px;
}

h1 {
    color: #e91e63;
}

button {
    background: #e91e63;
    color: white;
    border: none;
    padding: 12px 20px;
    margin: 8px;
    border-radius: 25px;
    font-size: 16px;
}

#msg {
    display: none;
    line-height: 1.8;
    color: #444;
}

.heart {
    position: absolute;
    color: red;
    font-size: 25px;
    animation: fall 6s linear infinite;
}

@keyframes fall {
    from {
        transform: translateY(-100px);
        opacity: 1;
    }
    to {
        transform: translateY(110vh);
        opacity: 0;
    }
}
</style>
</head>

<body>

<div class="box">

<h1>إلى شخص مميز ❤️</h1>

<button onclick="openMsg()">💌 افتحي الرسالة</button>

<button onclick="toggleMusic()">🎵 شغّل / أوقف الموسيقى</button>

<p id="msg">
ما نحبش نخسر شخص كان عندو مكانة كبيرة في قلبي...  
يمكن صرات أخطاء، بصح نتمنى نصلحو ونرجعو نضحكو كيما قبل ❤️
</p>

<audio id="music" loop>
    <source src="music.mp3" type="audio/mpeg">
</audio>

</div>


<script>

function openMsg(){
    document.getElementById("msg").style.display="block";
}


let music = document.getElementById("music");

function toggleMusic(){
    if(music.paused){
        music.play();
    } else {
        music.pause();
    }
}


function createHeart(){
    let heart = document.createElement("div");
    heart.className = "heart";
    heart.innerHTML = "❤️";
    heart.style.left = Math.random()*100 + "vw";
    heart.style.animationDuration = (3 + Math.random()*5) + "s";
    heart.style.fontSize = (15 + Math.random()*30) + "px";

    document.body.appendChild(heart);

    setTimeout(()=>{
        heart.remove();
    },8000);
}

setInterval(createHeart,300);

</script>

</body>
</html>