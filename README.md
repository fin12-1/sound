
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>dandi muach - Music Player</title>

<style>

body{
    margin:0;
    font-family: Arial, Helvetica, sans-serif;
    background:#121212;
    color:white;
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
}

.player{
    background:#181818;
    padding:30px;
    border-radius:15px;
    width:320px;
    text-align:center;
    box-shadow:0 10px 30px rgba(0,0,0,0.6);
}

.cover{
    width:220px;
    height:220px;
    border-radius:10px;
    object-fit:cover;
    margin-bottom:20px;
}

.title{
    font-size:20px;
    font-weight:bold;
}

.artist{
    color:#b3b3b3;
    margin-bottom:20px;
}

.controls{
    margin-top:15px;
}

button{
    background:#1db954;
    border:none;
    color:white;
    font-size:18px;
    padding:12px 20px;
    border-radius:50px;
    cursor:pointer;
}

button:hover{
    background:#1ed760;
}

.progress{
    width:100%;
    margin-top:20px;
}

</style>
</head>

<body>

<div class="player">

<img src="dndi.jfif" class="cover">

<div class="title">dandi muach</div>
<div class="artist">gufron</div>

<audio id="audio">
<source src="sahur.mp3" type="audio/mpeg">
</audio>

<input type="range" id="progress" class="progress" value="0">

<div class="controls">
<button onclick="playPause()">▶ Play</button>
</div>

</div>

<script>

let audio = document.getElementById("audio");
let progress = document.getElementById("progress");

function playPause(){
    if(audio.paused){
        audio.play();
    }else{
        audio.pause();
    }
}

audio.addEventListener("timeupdate", function(){
    progress.value = (audio.currentTime / audio.duration) * 100;
});

progress.addEventListener("input", function(){
    audio.currentTime = (progress.value / 100) * audio.duration;
});

</script>

</body>
</html>
