# Zameeha
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Birthday Zameeha 🎂</title>

<style>
body {
    margin: 0;
    height: 100vh;
    background: linear-gradient(135deg, #ff4d6d, #ff8fab);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: Arial, sans-serif;
    text-align: center;
    overflow: hidden;
    color: white;
}

.card {
    background: rgba(0,0,0,0.3);
    padding: 20px;
    border-radius: 20px;
    width: 90%;
    max-width: 360px;
}

h1 {
    font-size: 2rem;
    margin-bottom: 10px;
}

button {
    width: 100%;
    padding: 12px;
    margin-top: 10px;
    font-size: 1rem;
    border: none;
    border-radius: 25px;
    background: white;
    color: #ff4d6d;
    font-weight: bold;
    cursor: pointer;
}

#cake {
    margin: 15px auto;
    width: 160px;
    display: flex;
    flex-direction: column-reverse;
    align-items: center;
}

.layer {
    width: 140px;
    height: 12px;
    margin: 2px 0;
    border-radius: 6px;
    animation: drop 0.4s ease forwards;
}

@keyframes drop {
    from { transform: translateY(-40px); opacity: 0; }
    to { transform: translateY(0); opacity: 1; }
}

.confetti {
    position: fixed;
    width: 8px;
    height: 8px;
    top: -10px;
    animation: fall linear infinite;
}

@keyframes fall {
    to {
        transform: translateY(110vh) rotate(360deg);
    }
}
</style>
</head>

<body>

<div class="card">
    <h1 id="title">🎁 Birthday Surprise</h1>

    <div id="cake"></div>

    <!-- CODE 1 -->
    <button onclick="stackCake()">🎂 Stack 17-Layer Cake</button>

    <!-- CODE 2 -->
    <button onclick="birthdayWish()">🎉 Wish + Music</button>
</div>

<audio id="song">
    <source src="https://www.soundjay.com/human/sounds/happy-birthday-song-01.mp3" type="audio/mpeg">
</audio>

<script>
/* -------- CODE 1 : CAKE STACKING -------- */
function stackCake() {
    const cake = document.getElementById("cake");
    cake.innerHTML = "";

    let layers = 17; // her age
    let i = 0;

    let interval = setInterval(() => {
        if (i >= layers) {
            clearInterval(interval);
            return;
        }

        const layer = document.createElement("div");
        layer.className = "layer";
        layer.style.background =
            `hsl(${Math.random() * 360}, 80%, 70%)`;

        cake.appendChild(layer);
        i++;
    }, 200);
}

/* -------- CODE 2 : WISH + MUSIC + CONFETTI -------- */
function birthdayWish() {
    document.getElementById("title").innerHTML =
        "🎂 Happy 17th Birthday Zameeha 🎉";

    document.getElementById("song").play();

    for (let i = 0; i < 50; i++) {
        const confetti = document.createElement("div");
        confetti.className = "confetti";
        confetti.style.left = Math.random() * 100 + "vw";
        confetti.style.background =
            `hsl(${Math.random() * 360},100%,70%)`;
        confetti.style.animationDuration =
            (Math.random() * 3 + 2) + "s";
        document.body.appendChild(confetti);

        setTimeout(() => confetti.remove(), 5000);
    }
}
</script>

</body>
</html>
