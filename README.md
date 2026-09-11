```
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Hacker Interface</title>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    background: #000;
    color: #00ff66;
    font-family: "Courier New", monospace;
    overflow: hidden;
}

/* Matrix */
#matrix {
    position: fixed;
    inset: 0;
    z-index: -3;
    opacity: .35;
}

/* Scanlines */
body::after {
    content: "";
    position: fixed;
    inset: 0;
    pointer-events: none;
    background: repeating-linear-gradient(
        to bottom,
        rgba(0,255,100,.03) 0px,
        rgba(0,255,100,.03) 1px,
        transparent 2px,
        transparent 4px
    );
    z-index: 10;
}

/* Glow */
body::before {
    content: "";
    position: fixed;
    inset: 0;
    pointer-events: none;
    box-shadow: inset 0 0 120px #00ff3322;
    z-index: 9;
}

.container {
    width: 90%;
    max-width: 900px;
    margin: 10vh auto;
    padding: 35px;
    border: 1px solid #00ff66;
    background: rgba(0, 10, 5, .82);
    box-shadow:
        0 0 15px #00ff66,
        inset 0 0 25px #00ff6622;
    animation: appear 1.5s ease;
}

@keyframes appear {
    from {
        opacity: 0;
        transform: scale(.95);
    }
    to {
        opacity: 1;
        transform: scale(1);
    }
}

h1 {
    font-size: clamp(30px, 7vw, 70px);
    text-align: center;
    letter-spacing: 8px;
    margin-bottom: 20px;
    animation: glitch 1.5s infinite;
}

@keyframes glitch {
    0%, 90%, 100% {
        text-shadow: 0 0 10px #00ff66;
        transform: translate(0);
    }

    92% {
        text-shadow:
            3px 0 #ff003c,
            -3px 0 #00ffff;
        transform: translate(-2px, 1px);
    }

    94% {
        text-shadow:
            -3px 0 #ff003c,
            3px 0 #00ffff;
        transform: translate(2px, -1px);
    }
}

.subtitle {
    text-align: center;
    color: #66ff99;
    margin-bottom: 30px;
}

.terminal {
    background: #020b05;
    border: 1px solid #00aa44;
    padding: 20px;
    min-height: 220px;
    box-shadow: inset 0 0 20px #00ff6611;
}

.line {
    margin: 10px 0;
    white-space: nowrap;
    overflow: hidden;
}

.prompt {
    color: #00ffff;
}

.cursor {
    display: inline-block;
    width: 9px;
    height: 18px;
    background: #00ff66;
    vertical-align: middle;
    animation: blink .7s infinite;
}

@keyframes blink {
    50% {
        opacity: 0;
    }
}

.buttons {
    display: flex;
    justify-content: center;
    gap: 15px;
    margin-top: 25px;
    flex-wrap: wrap;
}

button {
    background: transparent;
    color: #00ff66;
    border: 1px solid #00ff66;
    padding: 12px 25px;
    font-family: inherit;
    cursor: pointer;
    transition: .3s;
}

button:hover {
    background: #00ff66;
    color: #000;
    box-shadow: 0 0 25px #00ff66;
    transform: translateY(-3px);
}

.status {
    margin-top: 25px;
    text-align: center;
    color: #00ffff;
    animation: pulse 1.5s infinite;
}

@keyframes pulse {
    50% {
        opacity: .4;
    }
}

/* Partículas */
.particle {
    position: fixed;
    width: 2px;
    height: 2px;
    background: #00ff66;
    box-shadow: 0 0 8px #00ff66;
    animation: float linear infinite;
    pointer-events: none;
}

@keyframes float {
    from {
        transform: translateY(100vh);
        opacity: 0;
    }

    20% {
        opacity: 1;
    }

    to {
        transform: translateY(-10vh);
        opacity: 0;
    }
}
</style>
</head>

<body>

<canvas id="matrix"></canvas>

<div class="container">

    <h1>HACKER</h1>

    <div class="subtitle">
        SYSTEM // CYBER INTERFACE
    </div>

    <div class="terminal" id="terminal">
        <div class="line">
            <span class="prompt">root@system:~$</span> initializing...
        </div>

        <div class="line">
            <span class="prompt">root@system:~$</span> loading interface...
        </div>

        <div class="line">
            <span class="prompt">root@system:~$</span> connection established
        </div>

        <div class="line">
            <span class="prompt">root@system:~$</span>
            <span id="typing"></span><span class="cursor"></span>
        </div>
    </div>

    <div class="buttons">
        <button onclick="runCommand('ACCESS GRANTED')">
            ACCESS
        </button>

        <button onclick="runCommand('SYSTEM SCANNING...')">
            SCAN
        </button>

        <button onclick="runCommand('SECURE MODE ENABLED')">
            SECURE
        </button>
    </div>

    <div class="status">
        ● SYSTEM ONLINE
    </div>

</div>

<script>
/* Matrix Effect */
const canvas = document.getElementById("matrix");
const ctx = canvas.getContext("2d");

canvas.width = window.innerWidth;
canvas.height = window.innerHeight;

const chars =
"01ABCDEFGHIJKLMNOPQRSTUVWXYZ#$%&@<>[]{}";

const fontSize = 14;
let columns = Math.floor(canvas.width / fontSize);
let drops = Array(columns).fill(1);

function matrix() {
    ctx.fillStyle = "rgba(0, 0, 0, 0.08)";
    ctx.fillRect(0, 0, canvas.width, canvas.height);

    ctx.fillStyle = "#00ff66";
    ctx.font = fontSize + "px monospace";

    for (let i = 0; i < drops.length; i++) {
        const char = chars[
            Math.floor(Math.random() * chars.length)
        ];

        ctx.fillText(char, i * fontSize, drops[i] * fontSize);

        if (
            drops[i] * fontSize > canvas.height &&
            Math.random() > .975
        ) {
            drops[i] = 0;
        }

        drops[i]++;
    }
}

setInterval(matrix, 40);

window.addEventListener("resize", () => {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;

    columns = Math.floor(canvas.width / fontSize);
    drops = Array(columns).fill(1);
});

/* Typing Effect */
const messages = [
    "waiting for command...",
    "welcome to the network...",
    "system ready...",
    "enter command..."
];

let messageIndex = 0;
let charIndex = 0;

function typeText() {
    const element = document.getElementById("typing");
    const text = messages[messageIndex];

    element.textContent = text.substring(0, charIndex);

    charIndex++;

    if (charIndex > text.length) {
        setTimeout(() => {
            charIndex = 0;
            messageIndex =
                (messageIndex + 1) % messages.length;
        }, 1800);

        return;
    }

    setTimeout(typeText, 70);
}

typeText();

/* Buttons */
function runCommand(command) {
    const terminal = document.getElementById("terminal");

    const line = document.createElement("div");
    line.className = "line";

    line.innerHTML =
        `<span class="prompt">root@system:~$</span> ${command}`;

    terminal.appendChild(line);

    terminal.scrollTop = terminal.scrollHeight;

    setTimeout(() => {
        line.style.color = "#00ffff";
    }, 100);
}

/* Particles */
for (let i = 0; i < 80; i++) {
    const particle = document.createElement("div");

    particle.className = "particle";

    particle.style.left =
        Math.random() * 100 + "vw";

    particle.style.animationDuration =
        (3 + Math.random() * 8) + "s";

    particle.style.animationDelay =
        Math.random() * 8 + "s";

    document.body.appendChild(particle);
}
</script>

</body>
</html>
```
