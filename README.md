# Valentine-<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Valentine 💖</title>

<style>
body{
    margin:0;
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    background:linear-gradient(135deg,#ff9a9e,#fad0c4);
    font-family: 'Poppins', sans-serif;
    overflow:hidden;
}

.card{
    width:360px;
    padding:30px;
    text-align:center;
    background:white;
    border-radius:18px;
    box-shadow:0 15px 30px rgba(0,0,0,0.2);
    position:relative;
    animation: pop 0.8s ease;
}

@keyframes pop{
    0%{transform:scale(0.6); opacity:0;}
    100%{transform:scale(1); opacity:1;}
}

h2{
    margin-bottom:30px;
}

button{
    padding:12px 30px;
    border:none;
    border-radius:30px;
    font-size:16px;
    cursor:pointer;
    transition:0.3s;
}

#yesBtn{
    background:#ff4d6d;
    color:white;
    animation: bounce 1.5s infinite;
}

@keyframes bounce{
    0%,100%{transform:translateY(0);}
    50%{transform:translateY(-6px);}
}

#noBtn{
    background:#eee;
    position:absolute;
}

#gifBox{
    display:none;
    margin-top:20px;
    animation: fade 1s ease;
}

@keyframes fade{
    from{opacity:0;}
    to{opacity:1;}
}

img{
    width:100%;
    border-radius:12px;
}
</style>
</head>

<body>

<div class="card" id="card">
    <h2>Hey, will you be my Valentine? 💘</h2>

    <button id="yesBtn">Yes 💕</button>
    <button id="noBtn">No 🙈</button>

    <div id="gifBox">
        <h3>Yayyyy 😍💖</h3>
        <img src="https://media.giphy.com/media/MDJ9IbxxvDUQM/giphy.gif">
    </div>
</div>

<script>
const noBtn = document.getElementById("noBtn");
const card = document.getElementById("card");
const yesBtn = document.getElementById("yesBtn");
const gifBox = document.getElementById("gifBox");

// initial position
noBtn.style.top = "65%";
noBtn.style.left = "55%";

function moveNo(){
    const maxX = card.clientWidth - noBtn.offsetWidth;
    const maxY = card.clientHeight - noBtn.offsetHeight;

    const x = Math.random() * maxX;
    const y = Math.random() * maxY;

    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";
}

noBtn.addEventListener("mouseover", moveNo);
noBtn.addEventListener("touchstart", moveNo);

yesBtn.addEventListener("click", ()=>{
    yesBtn.innerText = "I knew it 😘";
    gifBox.style.display = "block";
});
</script>

</body>
</html>
