<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>For Neha ❤️</title>

<style>
    body {
        margin: 0;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        font-family: 'Poppins', sans-serif;
        background: linear-gradient(135deg, #ff9a9e, #fad0c4);
        overflow: hidden;
        text-align: center;
    }

    .container {
        background: white;
        padding: 40px 60px;
        border-radius: 20px;
        box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        position: relative;
    }

    h1 {
        color: #ff4d6d;
        font-size: 28px;
    }

    .buttons {
        margin-top: 30px;
        position: relative;
        height: 100px;
    }

    button {
        padding: 12px 30px;
        font-size: 18px;
        border: none;
        border-radius: 30px;
        cursor: pointer;
        position: absolute;
        transition: all 0.3s ease;
    }

    #yesBtn {
        background: #ff4d6d;
        color: white;
        left: 30%;
    }

    #noBtn {
        background: #444;
        color: white;
        left: 60%;
    }

    .celebration {
        display: none;
        margin-top: 20px;
        font-size: 24px;
        color: #ff4d6d;
        animation: pop 1s ease forwards;
    }

    @keyframes pop {
        0% { transform: scale(0); opacity: 0; }
        100% { transform: scale(1); opacity: 1; }
    }

    .heart {
        position: absolute;
        font-size: 20px;
        color: red;
        animation: float 4s linear infinite;
    }

    @keyframes float {
        from { transform: translateY(0) rotate(0deg); opacity: 1; }
        to { transform: translateY(-800px) rotate(360deg); opacity: 0; }
    }
</style>
</head>

<body>

<div class="container">
    <h1>NEHA, will you be my Valentine? 💖</h1>
    <div class="buttons">
        <button id="yesBtn">YES 💘</button>
        <button id="noBtn">NO 🙈</button>
    </div>
    <div class="celebration" id="celebration">
        YAYYYY!!! 💖💍✨ I love youuu Nehaaa 💕
    </div>
</div>

<script>
    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");
    const celebration = document.getElementById("celebration");

    // Make NO button run away toward YES
    noBtn.addEventListener("mouseover", () => {
        const x = Math.random() * 200 - 100;
        const y = Math.random() * 200 - 100;
        noBtn.style.transform = `translate(${x}px, ${y}px)`;
    });

    // YES button celebration
    yesBtn.addEventListener("click", () => {
        celebration.style.display = "block";
        launchHearts();
    });

    function launchHearts() {
        for (let i = 0; i < 30; i++) {
            const heart = document.createElement("div");
            heart.classList.add("heart");
            heart.innerHTML = "❤️";
            heart.style.left = Math.random() * window.innerWidth + "px";
            heart.style.bottom = "0px";
            heart.style.fontSize = (Math.random() * 20 + 20) + "px";
            heart.style.animationDuration = (Math.random() * 2 + 2) + "s";
            document.body.appendChild(heart);

            setTimeout(() => heart.remove(), 4000);
        }
    }
</script>

</body>
</html>
