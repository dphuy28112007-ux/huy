Hi Buddy Full Ai Web App (complete)
· html
<!DOCTYPE html>
  askQuestion();
}


function askQuestion(){
  let q = "Tell me about your last trip";
  question.innerText = q;
  speak(q);
}


mic.onclick = ()=>{
  mic.classList.add("recording");
  rec.start();
  time=0;
  timerInterval=setInterval(()=>{
    time++;
    timer.innerText=time+"s";
  },1000);
}


function stopRec(){
  rec.stop();
  mic.classList.remove("recording");
  clearInterval(timerInterval);


  practice.classList.add("hidden");
  loading.classList.remove("hidden");


  analyze(finalText);
}


// ===== AI ANALYSIS =====
async function analyze(textInput){


  const res = await fetch("https://api.openai.com/v1/chat/completions",{
    method:"POST",
    headers:{
      "Content-Type":"application/json",
      "Authorization":"Bearer "+API_KEY
    },
    body:JSON.stringify({
      model:"gpt-4o-mini",
      messages:[
        {role:"system",content:"You are an English speaking examiner. Give scores (0-100) for pronunciation, fluency, vocabulary, grammar and short feedback."},
        {role:"user",content:textInput}
      ]
    })
  });


  const data = await res.json();
  let reply = data.choices[0].message.content;


  showResult(reply);
}


// ===== SHOW RESULT =====
function showResult(feedback){
  loading.classList.add("hidden");
  result.classList.remove("hidden");


  // random scores demo
  p1.style.width = Math.random()*100+"%";
  p2.style.width = Math.random()*100+"%";
  p3.style.width = Math.random()*100+"%";
  p4.style.width = Math.random()*100+"%";


  aiFeedback.innerText = feedback;
  speak(feedback);
}


function retry(){
  result.classList.add("hidden");
  practice.classList.remove("hidden");
}


function nextRound(){
  result.classList.add("hidden");
  practice.classList.remove("hidden");
  askQuestion();
}


</script>


</body>
</html>
