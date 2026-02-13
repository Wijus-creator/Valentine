
 <!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Valentine Card</title>

<style>
body{
    margin:0;
    font-family: Arial, sans-serif;
    background: linear-gradient(to bottom, #ffc0cb, #ffe4ec);
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
}

.card{
    background:white;
    width:340px;
    border-radius:20px;
    padding:20px;
    text-align:center;
    box-shadow:0 5px 15px rgba(0,0,0,0.2);
}

img{
    width:150px;
    height:150px;
    object-fit:cover;
    border-radius:20px;
    border:4px solid #ffb6c1;
}

h1{
    color:#ff69b4;
    margin:15px 0 5px;
}

button{
    padding:10px 20px;
    border:none;
    border-radius:20px;
    cursor:pointer;
    margin:5px;
    font-weight:bold;
}

.btn-pink{
    background:#ff69b4;
    color:white;
}

.btn-green{
    background:#66cdaa;
    color:white;
}

.hidden{
    display:none;
}

.message{
    margin-top:15px;
    padding:10px;
    border:2px solid #ffb6c1;
    border-radius:15px;
    min-height:100px;
    text-align:left;
    font-size:14px;
    line-height:1.6;
}
</style>
</head>

<body>

<div class="card">

    <img id="photo" src="mahendri.jpg">

    </h1><h1>Happy Valentine's Day!</h1>
    <p>MAHENDRI💕</p>

    <button class="btn-pink" onclick="openMessage()">Buka Pesan</button>
    
    <div id="msgBox" class="message hidden">
        <span id="typingText"></span>
    </div>

</div>
<audio id="bgMusic" autoplay loop>
    <source src="audio.mp3" type="audio/mpeg">
</audio>
</audio>


<script>

const text = `Selamat Hari Valentine ya, Dik 🤍

Terima kasih sudah menjadi orang yang baik, tulus, dan selalu berusaha jadi pribadi yang lebih baik setiap harinya. Kakak bangga sekali punya adik seperti kamu.

Kalau hari ini kamu sedang merasa sedih, lelah, atau kecewa, ingat ya… kamu tidak sendirian. Ada kakak yang selalu mendoakan dan mendukungmu. Jangan biarkan satu hari yang buruk membuatmu merasa tidak berharga. Kamu itu kuat, kamu itu berharga, dan kamu pantas bahagia.

Teruslah jadi pribadi yang baik, jangan berubah hanya karena dunia kadang tidak adil. Tetap semangat mengejar mimpi-mimpimu. Tangisan hari ini bukan tanda kelemahan, tapi tanda kamu sedang belajar menjadi lebih kuat.

Terima kasih sudah hadir dalam hidup kakak.  
Semoga hatimu selalu dipenuhi cinta, kedamaian, dan harapan.

Selamat Hari Valentine, adikku 🤍✨`;

let index = 0;

function typeEffect(){
    if(index < text.length){
        document.getElementById("typingText").innerHTML += text.charAt(index) === "\n" ? "<br>" : text.charAt(index);
        index++;
        setTimeout(typeEffect, 25);
    }
}

function openMessage(){
    let box = document.getElementById("msgBox");
    box.classList.toggle("hidden");

    if(!box.classList.contains("hidden")){
        document.getElementById("typingText").innerHTML = "";
        index = 0;
        typeEffect();
    }
}

function changePhoto(){
    let url = prompt("Masukkan link foto baru:");
    if(url){
        document.getElementById("photo").src = url;
    }
}

/* Jika autoplay diblokir */
document.addEventListener("click", function(){
    document.getElementById("bgMusic").play();
});
</script>

</body>
</html>

