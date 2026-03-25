<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AI Speaking App</title>

<style>
body{
  font-family: Arial;
  background:#0f172a;
  color:white;
  text-align:center;
  padding:20px;
}

.container{
  max-width:400px;
  margin:auto;
  background:#1e293b;
  padding:20px;
  border-radius:20px;
}

button{
  padding:10px 20px;
  margin:10px;
  border:none;
  border-radius:10px;
  cursor:pointer;
}

.mic{background:red;color:white;}
.recording{background:green !important;}

.hidden{display:none;}

.bar{
  width:100%;
  height:10px;
  background:#334155;
  margin:5px 0;
}
.fill{
  height:10px;
  background:lime;
  width:0%;
}

.history{
  margin-top:20px;
  text-align:left;
}
.item{
  background:#334155;
  padding:10px;
  margin-bottom:10px;
  border-radius:10px;
}
</style>
</head>

<body>

<h1>🎤 AI Speaking Practice</h1>

<div class="container">

<div id="practice">
  <h3 id="question"></h3>
  <button id="mic" class="mic">🎤 Start</button>
  <p id="timer">0s</p>
  <button onclick="stopRec
