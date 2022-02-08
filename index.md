<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0">     
<title></title>
<style type="text/css">
.watch{
position:relative;
aspect-ratio:1/1;
box-shadow:0px 2px 6px grey;
border-radius:50%;
transform:rotate(-90deg);
font-size:8px;
color:cyan;
font-weight:bold;

}
.hour{display:flex; justify-content:center; align-items:center;position:absolute;z-index:2;transition:1s linear; width:6px; height:80px; background:radial-gradient(circle farthest-side at 0% 0%,rgba(0,255,23,1) 0%,rgba(13, 29, 209,1) 90%);transform-origin: bottom ; transform:rotate(90deg) ; bottom:50%; left:50%;transform-style:preserve-3d; border-radius:50px;}
.minute{display:flex; justify-content:center;align-items:center;position:absolute;z-index:3;transition:1s linear; width:4px; height:120px; background:radial-gradient(circle farthest-side at 0% 0%,rgba(0,255,200,1) 0%,rgba(13, 29, 209,.5) 90%); transform-origin:bottom;transform:rotate(90deg);bottom:50%; left:50%; transform-style:preserve-3d;border-radius:50px;}
.second{display:flex; justify-content:center;align-items:center;position:absolute;z-index:4;transition:1s linear; width:2px;height:140px; background:radial-gradient(circle farthest-side at 0% 0%,rgba(0,26,0,1) 0%,rgba(13, 29, 209,0.5) 90%);transform-origin:bottom ;transform:rotate(90deg);bottom:50%; left:50%;transform-style:preserve-3d;border-radius:50px;}
.smallcircle{
display:flex;
justify-content:center;
align-items:center;
position:absolute;
bottom:43%;
left:43%;
height:50px;
width:50px;
border-radius:50%;
background:radial-gradient(silver,rgba(13, 29, 209,0.8));
z-index:5;
box-shadow:0px 2px 3px grey;
transform:rotate(90deg);
}
.wat{
background-image:url("/storage/emulated/0/Download/6787730_preview.png");
background-position:center;
background-repeat:no-repeat;
background-size:100% auto;

}
</style>
</head>
<body>
<div class="wat">
<div class="watch">
<div class="smallcircle"></div>
<div class="hour"></div>
<div class="minute"></div>
<div class="second"></div>
<div class="secnd"></div>
</div>
</div>
<script type="text/javascript">

var secondHand = document.querySelector('.second');
var minsHand = document.querySelector('.minute');
var hourHand = document.querySelector('.hour');
var tab = document.querySelector(".smallcircle");
var secnd = document.querySelector(".secnd");

function setDate() {
  var now = new Date();
  var seconds = now.getSeconds();
  var mins = now.getMinutes();
  var hour = now.getHours();

  if(hour==0){
  hour=12;

  }
  if(hour>12){
  hour = hour-12;

  }

  tab.innerHTML=hour+":"+mins+":"+seconds;
  
  var secondsDegrees = ((seconds / 60) * 360) + 90;
  secondHand.style.transform = "rotate("+secondsDegrees+"deg)";
  
  var minsDegrees = ((mins / 60) * 360) + ((seconds/60)*6) + 90;
  minsHand.style.transform = "rotate("+minsDegrees+"deg)";

  
  var hourDegrees = ((hour / 12) * 360) + ((mins/60)*30) + 90;
  hourHand.style.transform = "rotate("+hourDegrees+"deg)";

}

setInterval(setDate, 1000);

setDate();

</script>
</body>
</html>
