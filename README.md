<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Best Sis Ever 💜</title>

<style>
:root{
    --bg-light:#f3e5f5;
    --bg-dark:#1a1026;
    --text-light:#4a148c;
    --text-dark:#f3e5f5;
}

body{
    margin:0;
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    background:var(--bg-light);
    font-family:'Segoe UI',sans-serif;
    overflow:hidden;
    transition:0.5s;
}

body.night{
    background:var(--bg-dark);
    color:var(--text-dark);
}

.container{
    text-align:center;
    z-index:2;
    padding:25px;
}

h1{
    font-size:2.6rem;
    color:var(--text-light);
    transition:0.5s;
}

body.night h1{
    color:var(--text-dark);
}

.buttons{
    display:flex;
    gap:20px;
    justify-content:center;
    flex-wrap:wrap;
}

button{
    border:none;
    border-radius:50px;
    padding:14px 28px;
    font-size:1.3rem;
    cursor:pointer;
    font-weight:bold;
    transition:0.3s;
}

.yes-button{
    background:#7b1fa2;
    color:white;
    box-shadow:0 8px 20px rgba(123,31,162,0.4);
}

.no-button{
    background:#9e9e9e;
    color:white;
}

.hidden{display:none;}

.popup{
    position:fixed;
    top:50%;
    left:50%;
    transform:translate(-50%,-50%) scale(0);
    background:white;
    padding:30px;
    border-radius:20px;
    font-size:2rem;
    animation:pop 0.6s forwards;
    z-index:5;
}

@keyframes pop{
    to{transform:translate(-50%,-50%) scale(1);}
}

.heart,.flower{
    position:fixed;
    font-size:24px;
    animation:fall 4s linear forwards;
    z-index:1;
}

@keyframes fall{
    from{top:-10%;opacity:1;}
    to{top:110%;opacity:0;}
}

.toggle{
    position:fixed;
    top:15px;
    right:15px;
    background:#00000055;
    color:white;
    padding:10px 15px;
    border-radius:30px;
    cursor:pointer;
    z-index:10;
}
</style>
</head>

<body>

<div class="toggle" onclick="toggleNight()">🌙 Night</div>

<audio id="bgm" loop>
    <source src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_7b1c5d6fd8.mp3">
</audio>

<div id="question-view" class="container">
    <h1>Want to resubscribe my brother subscription?? 💜</h1>
    <div class="buttons">
        <button class="yes-button" onclick="handleYes()">Of course! 🥰</button>
        <button class="no-button" onclick="handleNo()">mmH... ?</button>
    </div>
</div>

<div id="success-view" class="container hidden">
    <h1>Let me take refund 😹🤣</h1>
    <p style="font-size:1.3rem;margin-top:15px;">
        I know life gets competitive,<br>
        but I will always be there,<br>
        watching you and praising your efforts 💖
    </p>
</div>

<script>
let messageIndex=0;
const messages=[
    "mmH... ?",
    "Are you really sure?",
    "But I'm your favorite brother!",
    "I'll share my snacks!",
    "I'll help with chores? (maybe)",
    "Don't be mean!",
    "Please? I'll be really nice!",
    "I'll tell Mom you're the best!",
    "Fine, I'll eat all the pizza myself...",
    "Just kidding! Say yes, sis! ✨"
];

function handleNo(){
    const noBtn=document.querySelector(".no-button");
    const yesBtn=document.querySelector(".yes-button");

    noBtn.textContent=messages[messageIndex];
    messageIndex=(messageIndex+1)%messages.length;

    yesBtn.style.fontSize=
        parseFloat(getComputedStyle(yesBtn).fontSize)*1.25+"px";
}

function handleYes(){
    document.getElementById("question-view").classList.add("hidden");
    document.getElementById("success-view").classList.remove("hidden");
    document.getElementById("bgm").play();

    const popup=document.createElement("div");
    popup.className="popup";
    popup.innerText="Correct Answer 💖✨";
    document.body.appendChild(popup);

    setInterval(shower,300);
}

function shower(){
    const el=document.createElement("div");
    el.className=Math.random()>0.5?"heart":"flower";
    el.innerText=Math.random()>0.5?"💖":"🌸";
    el.style.left=Math.random()*100+"vw";
    el.style.fontSize=(20+Math.random()*30)+"px";
    document.body.appendChild(el);
    setTimeout(()=>el.remove(),4000);
}

function toggleNight(){
    document.body.classList.toggle("night");
}
</script>

</body>
</html>
