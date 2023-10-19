# Javascript-Saat-ve-Kar-lama
body {
  background: black;
}

.clock {
  position: relative;
  text-align: center;
  color: #e98208;
  font-size: 60px;
  font-family:Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  letter-spacing: 7px;
}

.text1 {
  position: relative;
  text-align: center;
  color: #e98208;
  font-size: 50px;
  font-family:Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  letter-spacing: 7px;
}

.text2 {
  position: relative;
  text-align: center;
  color: #e98208;
  font-size: 40px;
  font-family:Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  letter-spacing: 7px;
  margin-right: 100px;
  margin-left: 100px;
}

img {
  margin-top: 120px;
  width: 17%;
}
 35 changes: 35 additions & 0 deletions35  
index.html
@@ -0,0 +1,35 @@
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="css/style.css" />
    <link
      rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/bootstrap@4.6.0/dist/css/bootstrap.min.css"
      integrity="sha384-B0vP5xmATw1+K9KRQjQERJvTumQW0nPEzvF6L/Z6nronJ3oUOFUFpCjEUQouq2+l"
      crossorigin="anonymous"
    />
    <title>Kodluyoruz Javascript Saat Ödevi</title>
  </head>
  <body class="bg-dark">
    <div class="text-center">
      <img
        src="https://cdn.sanity.io/images/9kdepi1d/production/65c832d202a503b15d99e628f4313782f3ef50db-300x62.png"
        alt=""
        class="rounded"
      />
      <div class="text1 text-center">
        Merhaba, <strong><span id="myName"></span></strong>! Hoş geldin!
      </div>
      <div id="myClock" class="clock" onload="showTime()"></div>
      <div class="text2 text-center">
        tarihinde
        <strong>Kodluyoruz Frontend Web Development Patikası</strong>'nın
        Javascript bölümü 1. Ödevindesiniz.
      </div>
    </div>
    <script src="js/clock.js"></script>
  </body>
</html>
 28 changes: 28 additions & 0 deletions28  
js/clock.js
@@ -0,0 +1,28 @@
function askName() {
    var name = prompt("Adınız nedir?");
    document.getElementById("myName").innerText = name;
}

function showTime() {
    var date = new Date();
    var h = date.getHours();
    var m = date.getMinutes();
    var s = date.getSeconds();
    var weekdayNumber = date.getDay();

    var arrayOfWeekdays = ["Pazar", "Pazartesi", "Salı", "Çarşamba", "Perşembe", "Cuma", "Cumartesi"]
    var weekdayName = arrayOfWeekdays[weekdayNumber]

    h = h < 10 ? "0" + h : h;
    m = m < 10 ? "0" + m : m;
    s = s < 10 ? "0" + s : s;

    var time = h + ":" + m + ":" + s + " " + weekdayName;
    document.getElementById("myClock").innerText = time;
    document.getElementById("myClock").textContent = time;

    setTimeout(showTime, 1000);
}

askName();
showTime();
