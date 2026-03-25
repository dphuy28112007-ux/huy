<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AI Speaking Pro</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">

<style>
body{
  font-family:'Poppins',sans-serif;
  background:linear-gradient(135deg,#0f172a,#1e293b);
  color:white;
  text-align:center;
  padding:20px;
}

.card{
  background:#1e293b;
  padding:20px;
  border-radius:20px;
  box-shadow:0 10px 30px rgba(0,0,0,0.3);
  max-width:400px;
  margin:auto;
}

button{
  padding:12px 20px;
  border:none;
  border-radius:12px;
  margin:10px;
  cursor:pointer;
  font-weight:bold;
}

.mic{background:#ef4444;color:white;}
.recording{background:#22c55e !important;}

.hidden{display:none;}

.bar{
  width:100%;
  height:10px;
  background:#334155;
  border-radius:10px;
  overflow:hidden;
}
.fill{
  height:10px;
  background:#22c55e;
  width:0%;
}

.history{
  margin-top:20px;
  text-align:left;
  max-height:200px;
  overflow:auto;
}

.history-item{
  background:#334155;
  padding:10px;
  border-radius:10px;
  margin-bottom:10px;
}
</style>
</head>

<body>

<h1>🎤 AI Speaking Pro</h1>

<div class="card">

<div id="practice">
  <h3 id="question"></h3>
  <button class="mic" id="mic">🎤 Start</button>
  <p id="timer">0s</p>
  <button onclick="stopRec()">Stop</button>
</div>

<div id="loading" class="hidden">
  <p>⏳ AI analyzing...</p>
</div>

<div id="result" class="hidden">
  <h3>Result</h3>

  <p>Pronunciation</p>
  <div class="bar"><div id="p1" class="fill"></div></div>
