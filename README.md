# Jana-
<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<title>رسالة حب</title>
<style>
    body {
        margin: 0;
        padding: 0;
        font-family: 'Arial', sans-serif;
        height: 100vh;
        background: linear-gradient(to bottom, #ff9a9e, #fad0c4);
        overflow: hidden;
        display: flex;
        justify-content: center;
        align-items: center;
        color: #fff;
    }

    #passwordBox, #message {
        background-color: rgba(0,0,0,0.6);
        padding: 30px;
        border-radius: 20px;
        text-align: center;
        z-index: 2;
        position: relative;
    }

    input[type="password"] {
        padding: 10px;
        border-radius: 10px;
        border: none;
        margin-top: 10px;
        font-size: 16px;
    }

    button {
        padding: 10px 20px;
        margin-top: 10px;
        border: none;
        border-radius: 10px;
        background-color: pink;
        color: #000;
        font-size: 16px;
        cursor: pointer;
    }

    #message {
        display: none;
        font-size: 20px;
    }

    .floating {
        position: absolute;
        animation: floatUp linear infinite;
        pointer-events: none;
    }

    @keyframes floatUp {
        0% { transform: translateY(0) rotate(0deg); }
        50% { transform: translateY(-150px) rotate(180deg); }
        100% { transform: translateY(-300px) rotate(360deg); }
    }
</style>
</head>
<body>

<div id="passwordBox">
    <h2>ادخلي كلمة المرور عشان تشوفي رسالتي 💖</h2>
    <input type="password" id="passInput" placeholder="كلمة المرور">
    <br>
    <button onclick="checkPassword()">افتح الرسالة</button>
</div>

<div id="message">
    <h1>أنا آسف يا حبيبتي اسف على كل حاجة حصلتلك بسببي ❤️</h1>
    <p>بحبك جدًا و مقدرش أعيش من غيرك 💕💖💘</p>
</div>

<script>
const correctPassword = "2062010";

function checkPassword() {
    const password = document.getElementById('passInput').value;
    if(password === correctPassword){
        document.getElementById('passwordBox').style.display = "none";
        document.getElementById('message').style.display = "block";
        createFloatingElements();
    } else {
        alert("كلمة المرور غلط 😢 حاول تاني!");
    }
}

function createFloatingElements() {
    const emojis = ['💖','❤️','💘','🐻','🧸']; // قلوب ودباديب
    for(let i=0; i<40; i++){
        const elem = document.createElement('div');
        elem.className = 'floating';
        elem.innerHTML = emojis[Math.floor(Math.random()*emojis.length)];
        elem.style.left = Math.random() * window.innerWidth + 'px';
        elem.style.fontSize = (20 + Math.random()*30) + 'px';
        elem.style.animationDuration = (4 + Math.random()*4) + 's';
        elem.style.opacity = 0.7 + Math.random()*0.3;
        document.body.appendChild(elem);

        // إزالة العنصر بعد انتهاء التحريك
        setTimeout(() => elem.remove(), 8000);
    }
    setTimeout(createFloatingElements, 500);
}
</script>

</body>
</html>
