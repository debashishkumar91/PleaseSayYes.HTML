<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>For Neha ❤️</title>

<style>
    body {
        margin: 0;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        font-family: 'Segoe UI', sans-serif;
        overflow: hidden;
        text-align: center;

        /* 💖 HER PHOTO BACKGROUND */
        background: 
            linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), 
            url('neha.jpg') no-repeat center center/cover;
    }

    .container {
        background: rgba(255,255,255,0.9);
        padding: 40px;
        border-radius: 20px;
        box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        position: relative;
    }

    h1 {
        color: #ff4d6d;
        font-size: 28px;
        margin-bottom: 20px;
    }

    .buttons {
        margin-top: 20px;
        position: relative;
        height: 80px;
    }

    button {
        padding: 12px 25px;
        font-size: 18px;
        border: none;
        border-radius: 25px;
        cursor: pointer;
        transition: 0.3s;
        position: absolute;
    }

    #yesBtn {
        background: #ff4d6d;
        color: white;
        left: 30%;
    }

    #noBtn {
        background: #aaa;
        color: white;
        left: 55%;
    }

    .celebration {
        display: none;
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        pointer-events: none;
    }

    .heart {
        position: absolute;
        font-size: 24px;
        animation: float 4s linear infinite;
    }

    @keyframes float {
        from { transform: translateY(100vh) scale(1); opacity: 1; }
        to { transform: translateY(-10vh) scale(1.5); opacity: 0; }
    }

    .love-message {
        font-size: 26px;
        color: #ff4d6d;
        margin-top: 20px;
        display: none;
    }
</style>
</head>

<body>

<div class="container">
    <h1>NEHA, will you be my Valentine? ❤️</h1>
    <div class="buttons">
        <button id="yesBtn">YES 💖</button>
        <button id="noBtn">NO 😢</button>
    </div>
    <div class="love-message" id="loveMsg">YAYYY!! I Love You So Much 🥰💘</div>
</div>

<div class="celebration" id="celebration"></div>

<script>
const noBtn = document.getElementById("noBtn");
const yesBtn = document.getElementById("yesBtn");
const celebration = document.getElementById("celebration");
const loveMsg = document.getElementById("loveMsg");

function moveNoButton() {
    const x = Math.random() * (window.innerWidth - 100);
    const y = Math.random() * (window.innerHeight - 100);
    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";
}

noBtn.addEventListener("mouseover", moveNoButton);
noBtn.addEventListener("click", moveNoButton);

yesBtn.addEventListener("click", () => {
    loveMsg.style.display = "block";
    celebration.style.display = "block";
    startCelebration();
});

function startCelebration() {
    for (let i = 0; i < 60; i++) {
        const heart = document.createElement("div");
        heart.classList.add("heart");
        heart.innerHTML = "❤️";
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.animationDuration = (2 + Math.random() * 3) + "s";
        celebration.appendChild(heart);

        setTimeout(() => heart.remove(), 4000);
    }
}
</script>

</body>
</html>
