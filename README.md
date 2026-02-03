<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>My Valentine 💗</title>

<style>
    body {
        margin: 0;
        font-family: 'Segoe UI', sans-serif;
        background: linear-gradient(135deg, #ff5fa2, #ffb6d5, #ffd1e8);
        color: white;
        text-align: center;
        overflow: hidden;
    }

    .container {
        padding: 30px;
        position: relative;
        z-index: 2;
    }

    h1 {
        font-size: 2.7em;
        margin-bottom: 10px;
    }

    p {
        font-size: 1.2em;
        max-width: 650px;
        margin: auto;
        line-height: 1.6;
    }

    .photos {
        margin: 25px 0;
    }

    .photos img {
        width: 130px;
        height: 130px;
        object-fit: cover;
        border-radius: 22px;
        margin: 8px;
        border: 3px solid #fff;
        box-shadow: 0 0 15px rgba(255,255,255,0.5);
    }

    .question {
        font-size: 2em;
        margin: 25px 0;
    }

    button {
        font-size: 1.2em;
        padding: 12px 30px;
        margin: 10px;
        border: none;
        border-radius: 30px;
        cursor: pointer;
    }

    #yesBtn {
        background-color: #ff2f92;
        color: white;
        box-shadow: 0 0 15px rgba(255,47,146,0.6);
    }

    #noBtn {
        background-color: #ff6fae;
        color: white;
        position: absolute;
    }

    #result {
        margin-top: 20px;
        font-size: 1.9em;
        display: none;
    }

    /* Floating animation */
    .float {
        position: fixed;
        bottom: -20px;
        animation: floatUp linear infinite;
        opacity: 0.8;
    }

    @keyframes floatUp {
        0% {
            transform: translateY(0) scale(1);
            opacity: 0.8;
        }
        100% {
            transform: translateY(-110vh) scale(1.6);
            opacity: 0;
        }
    }
</style>
</head>

<body>

<!-- Background Music -->
<audio autoplay loop>
    <source src="music.mp3" type="audio/mpeg">
</audio>

<div class="container">
    <h1>Hey Naaanyy 💕</h1>

    <p>
        I’m sorry Nanny for making you worry by my words 🥺💗  
        I promise I’ll always be there for youuu  
        and make youuu the happiest version of my life.  
        <br><br>
        Loovee yoouu naaanniiee 😙💖  
        <br>
        – Yours, Jammuu 💞
    </p>

    <div class="photos">
        <img src="photo1.jpg">
        <img src="photo2.jpg">
        <img src="photo3.jpg">
    </div>

    <div class="question">Will you be my Valentine? 💘</div>

    <button id="yesBtn" onclick="yesClicked()">Yes 💖</button>
    <button id="noBtn"
            onmouseover="moveNo()"
            ontouchstart="moveNo()"
            onclick="moveNo()">
        No 😅
    </button>

    <div id="result">Yayyy! You made my heart melt 💋💞</div>
</div>

<script>
    function yesClicked() {
        document.getElementById("result").style.display = "block";
    }

    function moveNo() {
        const noBtn = document.getElementById("noBtn");
        const maxX = window.innerWidth - noBtn.offsetWidth - 20;
        const maxY = window.innerHeight - noBtn.offsetHeight - 20;
        noBtn.style.left = Math.random() * maxX + "px";
        noBtn.style.top = Math.random() * maxY + "px";
    }

    // Floating hearts & kisses
    setInterval(() => {
        const emoji = document.createElement("div");
        emoji.className = "float";
        emoji.innerHTML = Math.random() > 0.5 ? "💗" : "💋";
        emoji.style.left = Math.random() * window.innerWidth + "px";
        emoji.style.fontSize = (Math.random() * 20 + 20) + "px";
        emoji.style.animationDuration = (Math.random() * 3 + 4) + "s";
        document.body.appendChild(emoji);

        setTimeout(() => {
            emoji.remove();
        }, 7000);
    }, 350);
</script>

</body>
</html>
