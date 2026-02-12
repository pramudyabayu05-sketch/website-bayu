# website-bayu
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<title>Profil Spesial 💗💙</title>

<style>
body {
    margin: 0;
    font-family: "Segoe UI", sans-serif;
    background: linear-gradient(to right, #fbc2eb, #a6c1ee);
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}

.container {
    background: white;
    width: 90%;
    max-width: 420px;
    padding: 30px;
    border-radius: 20px;
    box-shadow: 0 10px 25px rgba(0,0,0,0.2);
    text-align: center;
}

h1 {
    color: #e84393;
}

input {
    width: 90%;
    padding: 10px;
    margin: 7px 0;
    border-radius: 10px;
    border: 1px solid #ccc;
    font-size: 15px;
}

button {
    background: linear-gradient(to right, #fd79a8, #74b9ff);
    color: white;
    border: none;
    padding: 12px 25px;
    border-radius: 25px;
    font-size: 15px;
    cursor: pointer;
    margin-top: 15px;
}

button:hover {
    opacity: 0.9;
}

.slide {
    display: none;
}

.active {
    display: block;
}

p {
    color: #444;
    line-height: 1.6;
    font-size: 16px;
}

.notice {
    background: #ffeaa7;
    padding: 10px;
    border-radius: 10px;
    margin: 10px 0;
    display: none;
    font-size: 14px;
}

.highlight {
    color: #e84393;
    font-weight: bold;
}
</style>
</head>

<body>

<div class="container">

<!-- SLIDE 1 -->
<div class="slide active" id="slide1">
    <h1>Slide 1 🌸</h1>

    <input type="text" id="nama" placeholder="Nama">
    <input type="number" id="umur" placeholder="Umur">

    <button onclick="goSlide2()">Lanjut ➡️</button>
</div>

<!-- SLIDE 2 -->
<div class="slide" id="slide2">
    <h1>Slide 2 🌈</h1>

    <input type="text" id="warna" placeholder="Warna Favorit">
    <input type="number" id="sepatu" placeholder="Ukuran Sepatu">
    <input type="date" id="lahir">
    <input type="text" id="food" placeholder="Makanan Favorit">
    <input type="text" id="drink" placeholder="Minuman Favorit">

    <div class="notice" id="notice">
        🎉 Selamat! Kamu sudah mengisi Slide 1 & 2 😊
    </div>

    <button onclick="goSlide3()">Lanjut ➡️</button>
    <br><br>
    <button onclick="back1()">⬅️ Kembali</button>
</div>

<!-- SLIDE 3 -->
<div class="slide" id="slide3">
    <h1>Deskripsi ✨</h1>

    <p id="hasil"></p>

    <button onclick="back2()">⬅️ Kembali</button>
</div>

</div>

<script>

function goSlide2() {

    let nama = document.getElementById("nama").value;
    let umur = document.getElementById("umur").value;

    if(nama === "" || umur === "") {
        alert("Isi nama dan umur dulu ya 😊");
        return;
    }

    document.getElementById("slide1").classList.remove("active");
    document.getElementById("slide2").classList.add("active");
}

function goSlide3() {

    let warna = document.getElementById("warna").value;
    let sepatu = document.getElementById("sepatu").value;
    let lahir = document.getElementById("lahir").value;
    let food = document.getElementById("food").value;
    let drink = document.getElementById("drink").value;

    if(warna === "" || sepatu === "" || lahir === "" || food === "" || drink === "") {
        alert("Lengkapi dulu datanya ya 😄");
        return;
    }

    // Tampilkan notifikasi
    document.getElementById("notice").style.display = "block";

    setTimeout(() => {
        document.getElementById("slide2").classList.remove("active");
        document.getElementById("slide3").classList.add("active");
    }, 1200);

    let nama = document.getElementById("nama").value;
    let umur = document.getElementById("umur").value;

    let teks = `
    <span class="highlight">${nama}</span> (${umur} tahun) adalah sosok yang
    memiliki pesona alami dan kepribadian yang hangat 😊💗<br><br>

    Dengan warna favorit ${warna}, 
    ia menunjukkan selera yang lembut dan elegan 🌸💙<br><br>

    Ia dikenal sebagai pribadi yang:
    pintar, berwawasan luas, ulet,
    pekerja keras, rajin, dan selalu
    berusaha memberikan yang terbaik ✨📚<br><br>

    Dalam kesehariannya, 
    ${nama} adalah pribadi yang mandiri,
    konsisten dalam tujuan,
    dan tidak mudah menyerah 💪🌟<br><br>

    Kesukaannya pada ${food} dan ${drink}
    menunjukkan sisi sederhana namun
    menyenangkan 😋🥤<br><br>

    Secara keseluruhan,
    ${nama} adalah pribadi yang patut
    dibanggakan dan layak
    mendapatkan masa depan yang cerah 🌈💖
    `;

    document.getElementById("hasil").innerHTML = teks;
}

function back1() {
    document.getElementById("slide2").classList.remove("active");
    document.getElementById("slide1").classList.add("active");
}

function back2() {
    document.getElementById("slide3").classList.remove("active");
    document.getElementById("slide2").classList.add("active");
}

</script>

</body>
</html>
