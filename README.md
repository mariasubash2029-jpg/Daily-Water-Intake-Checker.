<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Daily Water Intake Checker</title>
<link rel="stylesheet" href="style.css">
</head>
<body>
<div class="container">
<div class="icon"> </div>
<h1>Water Intake Checker</h1>
<p>Check whether your daily water intake is healthy.</p>
<input type="number" id="water" placeholder="Enter glasses of water">
<button onclick="checkWater()">Check Now</button>
<div class="progress">
<div class="bar" id="bar">0%</div>
</div>
<div id="result"></div>
<div class="tips">
<h3>Hydration Tips</h3>
<ul>
<li>Drink at least 8 glasses daily.</li>
<li>Carry a water bottle.</li>
<li>Drink more water during summer.</li>
<li>Eat fruits rich in water.</li>
</ul>
</div>
<div class="footer">
Project using HTML, CSS & JavaScript
</div>
</div>
<script src="script.js"></script>
</body>
</html>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family: Arial, sans-serif;
}

body{
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    background:linear-gradient(to right,#74ebd5,#9face6);
}

.container{
    width:400px;
    background:white;
    padding:30px;
    border-radius:20px;
    text-align:center;
    box-shadow:0 8px 20px rgba(0,0,0,0.2);
}

h1{
    color:#0077b6;
    margin-bottom:10px;
}

p{
    color:#555;
    margin-bottom:20px;
}

.icon{
    font-size:60px;
    margin-bottom:10px;
}

input{
    width:100%;
    padding:12px;
    border:2px solid #90e0ef;
    border-radius:10px;
    font-size:16px;
    margin-top:10px;
}

button{
    width:100%;
    padding:12px;
    margin-top:20px;
    border:none;
    border-radius:10px;
    background:#0077b6;
    color:white;
    font-size:18px;
    cursor:pointer;
}

button:hover{
    background:#023e8a;
}

#result{
    margin-top:20px;
    font-size:18px;
    font-weight:bold;
}

.progress{
    width:100%;
    height:25px;
    background:#ddd;
    border-radius:20px;
    margin-top:20px;
}

.bar{
    height:25px;
    width:0%;
    background:#00b4d8;
    border-radius:20px;
    color:white;
    text-align:center;
    line-height:25px;
}

.tips{
    margin-top:25px;
    text-align:left;
    background:#f1f9ff;
    padding:15px;
    border-radius:10px;
}

.tips h3{
    color:#0077b6;
    margin-bottom:10px;
}

.tips ul{
    padding-left:20px;
}

.footer{
    margin-top:20px;
    color:gray;
    font-size:14px;
}
function checkWater() {

    var glasses;
    var result;
    var bar;
    var percent;

    glasses = document.getElementById("water").value;

    result = document.getElementById("result");

    bar = document.getElementById("bar");

    percent = (glasses / 8) * 100;

    if (percent > 100) {
        percent = 100;
    }

    bar.style.width = percent + "%";

    bar.innerHTML = percent + "%";

    if (glasses == "") {

        result.innerHTML = "Please enter the number of glasses";

        result.style.color = "orange";
    }

    else if (glasses < 4) {

        result.innerHTML = "Drink more water";

        result.style.color = "red";
    }

    else if (glasses < 8) {

        result.innerHTML = "Good, but drink a little more water";

        result.style.color = "blue";
    }

    else {

        result.innerHTML = "Excellent! Water intake is sufficient";

        result.style.color = "green";
    }

}
