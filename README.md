<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,user-scalable=no">
<title>V0ID</title>
<Firebase SDKs (Compat GameHubtatic.com/firebasejs/10.8.0/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.8.0/firebase-firestore-compat.js"></script>
<style>
:root{--bg:#0b0f17;--panel:#121927;--panel2:#182235;--border:#263249;--text:#f4f7fb;--muted:#93a1b8;--accent:#7c5cff}
*{box-sizing:border-box}body{margin:0;height:100vh;overflow:hidden;font-family:system-ui,-apple-system,sans-serif;color:var(--text);background:var(--bg)}
.app{display:flex;height:100vh}.side{width:235px;background:#0c111c;border-right:1px solid var(--border);padding:18px 12px;display:flex;flex-direction:column}
.logo{font-size:20px;font-weight:800;padding:5px 10px 22px}.logo b{display:inline-grid;place-items:center;width:34px;height:34px;border-radius:10px;background:linear-gradient(135deg,#7c5cff,#19c3ff);margin-right:8px}
label{font-size:11px;color:#68758b;text-transform:uppercase;font-weight:800;padding:10px 12px 6px}
.nav{border:0;background:transparent;color:#aeb9ca;text-align:left;padding:11px 12px;border-radius:10px;margin:2px 0;cursor:pointer}.nav:hover,.nav.active{background:#1a2440;color:white}
.spacer{flex:1}.mini{border-top:1px solid var(--border);padding:14px 6px;display:flex;gap:9px;align-items:center}.avatar{width:38px;height:38px;border-radius:50%;background:#2a3760;display:grid;place-items:center;font-weight:800;flex:none}.miniName{font-size:13px;font-weight:700}
.main{flex:1;display:flex;flex-direction:column;min-width:0}.top{height:66px;border-bottom:1px solid var(--border);display:flex;align-items:center;justify-content:space-between;padding:0 24px}.title{font-size:20px;font-weight:800}.online{font-size:12px;color:#7de5a6}
.content{padding:24px;overflow:auto;flex:1}.view{display:none;max-width:1100px;margin:auto}.view.active{display:block}
.hero,.settings{background:linear-gradient(135deg,#151d35,#121927);border:1px solid var(--border);border-radius:16px;padding:25px;margin-bottom:20px}.hero h1{margin:0 0 7px}.hero p,.settings p{color:var(--muted)}
.games{display:grid;grid-template-columns:repeat(auto-fill,minmax(190px,1fr));gap:15px}.game{background:var(--panel);border:1px solid var(--border);border-radius:14px;padding:13px}.thumb{height:115px;border-radius:10px;background:#202a43;display:grid;place-items:center;font-size:40px;margin-bottom:10px}.game h3{margin:0 0 5px}.game p{font-size:12px;color:var(--muted);height:34px}.play,.save,.send{border:0;background:var(--accent);color:white;font-weight:800;border-radius:9px;padding:10px;cursor:pointer}.play{width:100%}
.notes-list{display:grid;gap:12px;max-width:600px;margin:20px auto}
.note-card{background:var(--panel);border:1px solid var(--border);border-radius:13px;padding:16px}
.note-card h3{margin:0 0 7px}.note-card p{white-space:pre-wrap;color:#c5cedd;margin:0 0 12px;line-height:1.5}.note-actions{display:flex;justify-content:flex-end}
.delete-note{border:0;background:#39202a;color:#ff9aaa;border-radius:8px;padding:7px 11px;cursor:pointer}

/* Chat Styles */
.chat{height:calc(100vh - 160px);border:1px solid var(--border);border-radius:15px;overflow:hidden;background:#111827;display:flex;flex-direction:column}
.chathead{padding:14px 17px;border-bottom:1px solid var(--border);display:flex;justify-content:space-between;align-items:center}.chathead small{color:var(--muted)}
.messages{flex:1;overflow:auto;padding:18px}.msg{display:flex;gap:9px;margin-bottom:15px}.msg .avatar{width:34px;height:34px;font-size:12px}.meta{font-size:12px;color:#8290a7;margin-bottom:4px}.bubble{background:var(--panel2);padding:9px 12px;border-radius:5px 12px 12px 12px;max-width:min(650px,75vw);word-break:break-word}
.composer{display:flex;gap:8px;padding:11px;border-top:1px solid var(--border)}.composer input{flex:1;background:#0b111d;color:white;border:1px solid var(--border);padding:11px;border-radius:9px;outline:0}.send{padding:0 18px}

.math-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(320px,1fr));gap:15px;margin-top:20px}
.math-card{background:var(--panel);border:1px solid var(--border);border-radius:14px;padding:18px}
.math-card h3{margin:0 0 10px;font-size:16px;color:var(--text)}
.math-card input,.math-card select{width:100%;background:#0b111d;color:white;border:1px solid var(--border);padding:9px;border-radius:8px;outline:0;margin-bottom:8px}
.math-card button{width:100%;border:0;background:var(--accent);color:white;font-weight:700;border-radius:8px;padding:8px;cursor:pointer;margin-top:4px}
.math-result{margin-top:10px;padding:8px;background:#080d16;border-radius:8px;font-size:13px;color:#7de5a6;border:1px solid var(--border);word-break:break-all}

.calculator{max-width:390px;margin:auto;background:var(--panel);border:1px solid var(--border);border-radius:16px;padding:16px}
.calc-display{width:100%;height:65px;background:#080d16;color:white;border:1px solid var(--border);border-radius:10px;padding:10px;text-align:right;font-size:27px;margin-bottom:12px}
.calc-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:8px}
.calc-grid button{height:58px;border:1px solid var(--border);border-radius:10px;background:var(--panel2);color:white;font-size:18px;font-weight:700;cursor:pointer}
.calc-grid button:hover{background:#26334d}.calc-grid .equals{background:var(--accent);border-color:var(--accent)}
.settings{max-width:600px;margin:auto}
.status{font-size:11px;color:#7de5a6;margin-top:3px}.hint{font-size:12px;color:#77859c;margin-top:12px}
@media(max-width:700px){.side{width:70px;padding:14px 7px}.logo{font-size:0;text-align:center}.logo b{margin:0}.nav{font-size:0;text-align:center}.nav::first-letter{font-size:18px}.mini{justify-content:center}.mini div:not(.avatar){display:none}.content{padding:14px}.top{padding:0 14px}}
</style>
</head>
<body>
<div class="app">
<aside class="side">
  <div class="logo"><b>🎮</b><span>V0ID</span></div>
  <label>Categories</label>
  <button class="nav active" data-view="home">🏠 Home</button>
  <button class="nav" data-view="action">⚔️ Action</button>
  <button class="nav" data-view="puzzle">🧩 Puzzle</button>
  <button class="nav" data-view="arcade">👾 Arcade</button>
  <button class="nav" data-view="chat">💬 Chat</button>
  <button class="nav" data-view="notes">📝 Notes</button>
  <button class="nav" data-view="math">➗ Math Hub</button>
  <div class="spacer"></div>
  <button class="nav" data-view="settings">⚙️ Settings</button>
  <div class="mini"><div class="avatar" id="miniAvatar">😀</div><div><div class="miniName" id="miniName"></div><div class="status">Online</div></div></div>
</aside>
<main class="main">
<header class="top"><div class="title" id="title">Home</div><div class="online" id="connection">● Ready</div></header>
<section class="content">
<div class="view active" id="home"><div class="hero"><h1>Welcome to GameHub 🎮</h1><p>Choose a category and play.</p></div><div class="games" id="homeGames"></div></div>
<div class="view" id="action"><div class="hero"><h1>⚔️ Action</h1><p>Fast-paced games.</p></div><div class="games" id="actionGames"></div></div>
<div class="view" id="puzzle"><div class="hero"><h1>🧩 Puzzle</h1><p>Brain games.</p></div><div class="games" id="puzzleGames"></div></div>
<div class="view" id="arcade"><div class="hero"><h1>👾 Arcade</h1><p>Classic quick games.</p></div><div class="games" id="arcadeGames"></div></div>

<div class="view" id="chat">
  <div class="hero">
    <h1>💬 Chromebook Cloud Chat</h1>
    <p>Live cross-device chat via Firebase Cloud Database.</p>
  </div>
  <div class="chat">
    <div class="chathead">
      <small>Status: Firebase Cloud Sync</small>
      <span id="chatStatusBadge" style="font-size:11px; color:#7de5a6;">Connected Live</span>
    </div>
    <div class="messages" id="chatMessages"></div>
    <div class="composer">
      <input id="chatInput" placeholder="Type a message..." maxlength="200">
      <button class="send" id="sendChat">Send</button>
    </div>
  </div>
</div>

<div class="view" id="notes">
  <div class="hero"><h1>📝 Notes</h1><p>Create and save notes directly in your browser.</p></div>
  <div class="settings">
    <div class="field"><span>Note title</span><input id="noteTitle" maxlength="80" placeholder="My note"></div>
    <div class="field"><span>Note</span><textarea id="noteText" maxlength="5000" placeholder="Write your note here..." style="width:100%;min-height:150px;resize:vertical;background:#0b111d;color:white;border:1px solid var(--border);padding:11px;border-radius:9px;outline:0;font:inherit"></textarea></div>
    <button class="save" id="addNote">Add Note</button>
  </div>
  <div class="notes-list" id="notesList"></div>
</div>

<div class="view" id="math">
  <div class="hero"><h1>➗ Advanced Math Hub</h1><p>Standard calculator plus 25+ specific math calculators and tools.</p></div>
  
  <div class="calculator" style="margin-bottom:30px;">
    <input id="calcDisplay" class="calc-display" readonly value="0">
    <div class="calc-grid">
      <button data-calc="clear">C</button><button data-calc="back">⌫</button><button data-value="%">%</button><button data-value="/">÷</button>
      <button data-value="7">7</button><button data-value="8">8</button><button data-value="9">9</button><button data-value="*">×</button>
      <button data-value="4">4</button><button data-value="5">5</button><button data-value="6">6</button><button data-value="-">−</button>
      <button data-value="1">1</button><button data-value="2">2</button><button data-value="3">3</button><button data-value="+">+</button>
      <button data-value="(">(</button><button data-value="0">0</button><button data-value=")">)</button><button data-calc="equals" class="equals">=</button>
    </div>
  </div>

  <h2 style="margin-top:20px;">25+ Quick Math & Conversion Tools</h2>
  <div class="math-grid">
    <div class="math-card"><h3>1. Percentage (%)</h3><input id="p1" placeholder="What is X%"><input id="p2" placeholder="Of this number"><button onclick="calcPct()">Calculate</button><div class="math-result" id="rPct">Result: -</div></div>
    <div class="math-card"><h3>2. Square Root</h3><input id="sqrtIn" placeholder="Enter number"><button onclick="calcSqrt()">Calculate</button><div class="math-result" id="rSqrt">Result: -</div></div>
    <div class="math-card"><h3>3. Exponent (Base^Exp)</h3><input id="baseIn" placeholder="Base"><input id="expIn" placeholder="Exponent"><button onclick="calcPow()">Calculate</button><div class="math-result" id="rPow">Result: -</div></div>
    <div class="math-card"><h3>4. Pythagorean (Hypotenuse c)</h3><input id="pytA" placeholder="Side a"><input id="pytB" placeholder="Side b"><button onclick="calcPyt()">Find Hypotenuse</button><div class="math-result" id="rPyt">Result: -</div></div>
    <div class="math-card"><h3>5. Circle Area</h3><input id="cirR" placeholder="Radius (r)"><button onclick="calcCircle()">Calculate Area</button><div class="math-result" id="rCir">Result: -</div></div>
    <div class="math-card"><h3>6. Mean / Average</h3><input id="meanIn" placeholder="Comma-separated numbers (e.g. 10,20,30)"><button onclick="calcMean()">Calculate Mean</button><div class="math-result" id="rMean">Result: -</div></div>
    <div class="math-card"><h3>7. Quadratic Roots (ax^2+bx+c)</h3><input id="quadA" placeholder="a"><input id="quadB" placeholder="b"><input id="quadC" placeholder="c"><button onclick="calcQuad()">Solve X</button><div class="math-result" id="rQuad">Result: -</div></div>
    <div class="math-card"><h3>8. Fahrenheit to Celsius</h3><input id="fahrIn" placeholder="Degrees Fahrenheit"><button onclick="calcTemp()">Convert to °C</button><div class="math-result" id="rTemp">Result: -</div></div>
    <div class="math-card"><h3>9. Celsius to Fahrenheit</h3><input id="celsIn" placeholder="Degrees Celsius"><button onclick="calcTemp2()">Convert to °F</button><div class="math-result" id="rTemp2">Result: -</div></div>
    <div class="math-card"><h3>10. Simple Interest</h3><input id="siP" placeholder="Principal"><input id="siR" placeholder="Rate (%)"><input id="siT" placeholder="Time (Years)"><button onclick="calcSI()">Calculate Interest</button><div class="math-result" id="rSI">Result: -</div></div>
    <div class="math-card"><h3>11. Speed Finder (Dist / Time)</h3><input id="sdDist" placeholder="Distance"><input id="sdTime" placeholder="Time"><button onclick="calcSpeed()">Find Speed</button><div class="math-result" id="rSpeed">Result: -</div></div>
    <div class="math-card"><h3>12. Factorial (n!)</h3><input id="factIn" placeholder="Integer n (max 170)"><button onclick="calcFact()">Calculate</button><div class="math-result" id="rFact">Result: -</div></div>
    <div class="math-card"><h3>13. Greatest Common Divisor</h3><input id="gcd1" placeholder="Number 1"><input id="gcd2" placeholder="Number 2"><button onclick="calcGCD()">Find GCD</button><div class="math-result" id="rGCD">Result: -</div></div>
    <div class="math-card"><h3>14. Least Common Multiple</h3><input id="lcm1" placeholder="Number 1"><input id="lcm2" placeholder="Number 2"><button onclick="calcLCM()">Find LCM</button><div class="math-result" id="rLCM">Result: -</div></div>
    <div class="math-card"><h3>15. BMI Calculator (Metric)</h3><input id="bmiKg" placeholder="Weight (kg)"><input id="bmiM" placeholder="Height (m)"><button onclick="calcBMI()">Calculate BMI</button><div class="math-result" id="rBMI">Result: -</div></div>
    <div class="math-card"><h3>16. Triangle Area</h3><input id="triB" placeholder="Base"><input id="triH" placeholder="Height"><button onclick="calcTri()">Calculate Area</button><div class="math-result" id="rTri">Result: -</div></div>
    <div class="math-card"><h3>17. Rectangle Perimeter</h3><input id="recL" placeholder="Length"><input id="recW" placeholder="Width"><button onclick="calcPerim()">Calculate Perimeter</button><div class="math-result" id="rPerim">Result: -</div></div>
    <div class="math-card"><h3>18. Line Slope (x1,y1 to x2,y2)</h3><input id="sl1" placeholder="x1, y1 (comma separated)"><input id="sl2" placeholder="x2, y2 (comma separated)"><button onclick="calcSlope()">Find Slope</button><div class="math-result" id="rSlope">Result: -</div></div>
    <div class="math-card"><h3>19. 2D Point Distance</h3><input id="pt1" placeholder="x1, y1"><input id="pt2" placeholder="x2, y2"><button onclick="calcDist()">Find Distance</button><div class="math-result" id="rDist">Result: -</div></div>
    <div class="math-card"><h3>20. Simplify Fraction</h3><input id="fracN" placeholder="Numerator"><input id="fracD" placeholder="Denominator"><button onclick="calcFrac()">Simplify</button><div class="math-result" id="rFrac">Result: -</div></div>
    <div class="math-card"><h3>21. Logarithm (Log10)</h3><input id="logIn" placeholder="Number"><button onclick="calcLog()">Calculate Log10</button><div class="math-result" id="rLog">Result: -</div></div>
    <div class="math-card"><h3>22. Natural Log (ln)</h3><input id="lnIn" placeholder="Number"><button onclick="calcLn()">Calculate ln</button><div class="math-result" id="rLn">Result: -</div></div>
    <div class="math-card"><h3>23. % Change (Old to New)</h3><input id="pcOld" placeholder="Original Value"><input id="pcNew" placeholder="New Value"><button onclick="calcPctChange()">Calculate % Change</button><div class="math-result" id="rPctChange">Result: -</div></div>
    <div class="math-card"><h3>24. Modulus (A mod B)</h3><input id="modA" placeholder="A"><input id="modB" placeholder="B"><button onclick="calcMod()">Find Remainder</button><div class="math-result" id="rMod">Result: -</div></div>
    <div class="math-card"><h3>25. Cube Volume</h3><input id="cubeS" placeholder="Side length (s)"><button onclick="calcCube()">Calculate Volume</button><div class="math-result" id="rCube">Result: -</div></div>
    <div class="math-card"><h3>26. Sphere Volume</h3><input id="sphR" placeholder="Radius (r)"><button onclick="calcSphere()">Calculate Volume</button><div class="math-result" id="rSph">Result: -</div></div>
  </div>
</div>

<div class="view" id="settings"><div class="settings"><h2>⚙️ Profile</h2><p>Your name and emoji are used across GameHub.</p><div class="field"><span>Display name</span><input id="name" style="width:100%;background:#0b111d;color:white;border:1px solid var(--border);padding:11px;border-radius:9px;outline:0"></div><div class="field"><span>Profile emoji</span><select id="emoji" style="width:100%;background:#0b111d;color:white;border:1px solid var(--border);padding:11px;border-radius:9px;outline:0"><option>😀</option><option>😎</option><option>👾</option><option>🎮</option><option>🦊</option><option>🐸</option><option>🤖</option><option>🐱</option><option>🐼</option><option>🚀</option></select></div><button class="save" id="save">Save Profile</button><div class="hint">Your profile is stored in this browser.</div></div></div>
</section></main></div>

<script>
const games=[
["Neon Runner","🏃","Dodge obstacles.","action"],["Space Defender","🚀","Protect your ship.","action"],["Dungeon Dash","⚔️","Survive the dungeon.","action"],
["Color Match","🎨","Match the colors.","puzzle"],["2048 Mini","🔢","Combine tiles.","puzzle"],["Memory Flip","🃏","Find matching pairs.","puzzle"],
["Block Breaker","🧱","Break the blocks.","arcade"],["Snake","🐍","Grow without crashing.","arcade"],["Star Catcher","⭐","Catch falling stars.","arcade"]];
const esc=s=>String(s).replace(/[&<>"']/g,c=>({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#039;"}[c]));
function renderGames(){
  ["home","action","puzzle","arcade"].forEach(cat=>{
    document.getElementById(cat+"Games").innerHTML=games.filter(g=>cat==="home"||g[3]===cat).map(g=>`<div class="game"><div class="thumb">${g[1]}</div><h3>${esc(g[0])}</h3><p>${esc(g[2])}</p><button class="play" onclick="alert('${esc(g[0])} launched!')">Play</button></div>`).join("");
  });
}

let profile=JSON.parse(localStorage.getItem("gamehubProfile")||"null")||{name:"User"+Math.floor(1000+Math.random()*9000),emoji:"😀"};
const miniName=document.getElementById("miniName");
const miniAvatar=document.getElementById("miniAvatar");
const nameInput=document.getElementById("name");
const emojiSelect=document.getElementById("emoji");
const titleEl=document.getElementById("title");

function renderProfile(){
  miniName.textContent=profile.name;
  miniAvatar.textContent=profile.emoji;
  nameInput.value=profile.name;
  emojiSelect.value=profile.emoji;
}

document.querySelectorAll(".nav").forEach(b=>b.onclick=()=>{
  document.querySelectorAll(".nav").forEach(x=>x.classList.remove("active"));
  b.classList.add("active");
  document.querySelectorAll(".view").forEach(x=>x.classList.remove("active"));
  document.getElementById(b.dataset.view).classList.add("active");
  titleEl.textContent=b.textContent.trim().replace(/^.\s*/,"");
});

document.getElementById("save").onclick=()=>{
  profile={name:nameInput.value.trim()||"User"+Math.floor(1000+Math.random()*9000),emoji:emojiSelect.value};
  localStorage.setItem("gamehubProfile",JSON.stringify(profile));
  renderProfile();
};

// --- FIREBASE CLOUD CHAT CONFIGURATION ---
const firebaseConfig = {
  apiKey: "AIzaSyAF7B7qYDrUi-C5_6LCjQfoXRrH95QmIio",
  authDomain: "v14a-bb967.firebaseapp.com",
  projectId: "v14a-bb967",
  storageBucket: "v14a-bb967.firebasestorage.app",
  messagingSenderId: "226123648400",
  appId: "1:226123648400:web:089323e070661a87c4b715",
  measurementId: "G-R9Q24182LC"
};

firebase.initializeApp(firebaseConfig);
const db = firebase.firestore();
const chatMessages = document.getElementById("chatMessages");
const chatInput = document.getElementById("chatInput");

function appendMessage(sender, emoji, text) {
  const msgDiv = document.createElement("div");
  msgDiv.className = "msg";
  msgDiv.innerHTML = `
    <div class="avatar">${emoji}</div>
    <div>
      <div class="meta">${esc(sender)}</div>
      <div class="bubble">${esc(text)}</div>
    </div>
  `;
  chatMessages.appendChild(msgDiv);
  chatMessages.scrollTop = chatMessages.scrollHeight;
}

document.getElementById("sendChat").onclick = async () => {
  const text = chatInput.value.trim();
  if (!text) return;
  
  try {
    await db.collection("gamehub_messages").add({
      sender: profile.name,
      emoji: profile.emoji,
      text: text,
      timestamp: firebase.firestore.FieldValue.serverTimestamp()
    });
    chatInput.value = "";
  } catch (err) {
    alert("Error sending message. Ensure Firestore database is created in Firebase Console.");
  }
};

chatInput.onkeydown = (e) => {
  if (e.key === "Enter") document.getElementById("sendChat").click();
};

// Real-time listener for incoming messages ordered by time
db.collection("gamehub_messages")
  .orderBy("timestamp", "asc")
  .limitToLast(50)
  .onSnapshot(snapshot => {
    chatMessages.innerHTML = "";
    snapshot.forEach(doc => {
      const data = doc.data();
      appendMessage(data.sender || "Anon", data.emoji || "😀", data.text);
    });
  });

// Notes
let notes = JSON.parse(localStorage.getItem("gamehubNotes") || "[]");
function renderNotes(){
  const list=document.getElementById("notesList");
  if(!notes.length){list.innerHTML='<div style="color:var(--muted);text-align:center;">No notes yet. Add your first note above.</div>';return;}
  list.innerHTML=notes.map((n,i)=>`<div class="note-card"><h3>${esc(n.title)}</h3><p>${esc(n.text)}</p><div class="note-actions"><button class="delete-note" onclick="deleteNote(${i})">Delete</button></div></div>`).join("");
}
function deleteNote(i){notes.splice(i,1);localStorage.setItem("gamehubNotes",JSON.stringify(notes));renderNotes();}
document.getElementById("addNote").onclick=()=>{
  const title=document.getElementById("noteTitle").value.trim() || "Untitled Note";
  const text=document.getElementById("noteText").value.trim();
  if(!text) return;
  notes.unshift({title,text});
  localStorage.setItem("gamehubNotes",JSON.stringify(notes));
  document.getElementById("noteTitle").value="";
  document.getElementById("noteText").value="";
  renderNotes();
};

// Standard calculator logic
let expression="";
const display=document.getElementById("calcDisplay");
function updateCalc(){display.value=expression || "0";}
function calculate(){
  try{
    let exp=expression.replace(/%/g,"/100");
    if(!/^[0-9+\-*/().\s.]+$/.test(exp)) throw new Error();
    const result=Function('"use strict"; return ('+exp+')')();
    if(!Number.isFinite(result)) throw new Error();
    expression=String(Math.round(result*1000000000000)/1000000000000);
    updateCalc();
  }catch{display.value="Error";expression="";setTimeout(updateCalc,800);}
}
document.querySelectorAll("[data-value]").forEach(btn=>{btn.onclick=()=>{expression+=btn.dataset.value;updateCalc();};});
document.querySelectorAll("[data-calc]").forEach(btn=>{
  btn.onclick=()=>{
    const action=btn.dataset.calc;
    if(action==="clear") expression="";
    if(action==="back") expression=expression.slice(0,-1);
    if(action==="equals") calculate();
    updateCalc();
  };
});

// Math Toolkit Functions
function calcPct(){let a=parseFloat(document.getElementById('p1').value),b=parseFloat(document.getElementById('p2').value);document.getElementById('rPct').innerText="Result: "+(isNaN(a)||isNaN(b)?"Invalid input":(a/100)*b);}
function calcSqrt(){let n=parseFloat(document.getElementById('sqrtIn').value);document.getElementById('rSqrt').innerText="Result: "+(isNaN(n)||n<0?"Invalid input":Math.sqrt(n));}
function calcPow(){let b=parseFloat(document.getElementById('baseIn').value),e=parseFloat(document.getElementById('expIn').value);document.getElementById('rPow').innerText="Result: "+(isNaN(b)||isNaN(e)?"Invalid input":Math.pow(b,e));}
function calcPyt(){let a=parseFloat(document.getElementById('pytA').value),b=parseFloat(document.getElementById('pytB').value);document.getElementById('rPyt').innerText="Result: "+(isNaN(a)||isNaN(b)?"Invalid input":Math.sqrt(a*a+b*b));}
function calcCircle(){let r=parseFloat(document.getElementById('cirR').value);document.getElementById('rCir').innerText="Result: "+(isNaN(r)||r<0?"Invalid input":Math.PI*r*r);}
function calcMean(){let arr=document.getElementById('meanIn').value.split(',').map(Number);let sum=arr.reduce((x,y)=>x+y,0);document.getElementById('rMean').innerText="Result: "+(arr.some(isNaN)||arr.length===0?"Invalid input":sum/arr.length);}
function calcQuad(){let a=parseFloat(document.getElementById('quadA').value),b=parseFloat(document.getElementById('quadB').value),c=parseFloat(document.getElementById('quadC').value);let d=b*b-4*a*c;if(isNaN(d)||a===0){document.getElementById('rQuad').innerText="Result: Invalid or a=0";}else if(d<0){document.getElementById('rQuad').innerText="Result: Complex roots";}else{let x1=(-b+Math.sqrt(d))/(2*a),x2=(-b-Math.sqrt(d))/(2*a);document.getElementById('rQuad').innerText=`Result: x1 = ${x1}, x2 = ${x2}`;}}
function calcTemp(){let f=parseFloat(document.getElementById('fahrIn').value);document.getElementById('rTemp').innerText="Result: "+(isNaN(f)?"Invalid input":(f-32)*5/9+" °C");}
function calcTemp2(){let c=parseFloat(document.getElementById('celsIn').value);document.getElementById('rTemp2').innerText="Result: "+(isNaN(c)?"Invalid input":(c*9/5)+32+" °F");}
function calcSI(){let p=parseFloat(document.getElementById('siP').value),r=parseFloat(document.getElementById('siR').value),t=parseFloat(document.getElementById('siT').value);document.getElementById('rSI').innerText="Result: "+(isNaN(p)||isNaN(r)||isNaN(t)?"Invalid input":(p*r*t)/100);}
function calcSpeed(){let d=parseFloat(document.getElementById('sdDist').value),t=parseFloat(document.getElementById('sdTime').value);document.getElementById('rSpeed').innerText="Result: "+(isNaN(d)||isNaN(t)||t===0?"Invalid input":d/t);}
function calcFact(){let n=parseInt(document.getElementById('factIn').value);if(isNaN(n)||n<0||n>170){document.getElementById('rFact').innerText="Result: Invalid (0-170)";return;}let f=1;for(let i=2;i<=n;i++)f*=i;document.getElementById('rFact').innerText="Result: "+f;}
function gcd(a,b){return b==0?a:gcd(b,a%b);}
function calcGCD(){let a=parseInt(document.getElementById('gcd1').value),b=parseInt(document.getElementById('gcd2').value);document.getElementById('rGCD').innerText="Result: "+(isNaN(a)||isNaN(b)?"Invalid input":gcd(a,b));}
function calcLCM(){let a=parseInt(document.getElementById('lcm1').value),b=parseInt(document.getElementById('lcm2').value);document.getElementById('rLCM').innerText="Result: "+(isNaN(a)||isNaN(b)||a===0||b===0?"Invalid input":Math.abs(a*b)/gcd(a,b));}
function calcBMI(){let w=parseFloat(document.getElementById('bmiKg').value),h=parseFloat(document.getElementById('bmiM').value);document.getElementById('rBMI').innerText="Result: "+(isNaN(w)||isNaN(h)||h===0?"Invalid input":w/(h*h));}
function calcTri(){let b=parseFloat(document.getElementById('triB').value),h=parseFloat(document.getElementById('triH').value);document.getElementById('rTri').innerText="Result: "+(isNaN(b)||isNaN(h)?"Invalid input":0.5*b*h);}
function calcPerim(){let l=parseFloat(document.getElementById('recL').value),w=parseFloat(document.getElementById('recW').value);document.getElementById('rPerim').innerText="Result: "+(isNaN(l)||isNaN(w)?"Invalid input":2*(l+w));}
function calcSlope(){try{let p1=document.getElementById('sl1').value.split(',').map(Number),p2=document.getElementById('sl2').value.split(',').map(Number);let s=(p2[1]-p1[1])/(p2[0]-p1[0]);document.getElementById('rSlope').innerText="Result: "+(isNaN(s)?"Invalid input":s);}catch{document.getElementById('rSlope').innerText="Result: Error";}}
function calcDist(){try{let p1=document.getElementById('pt1').value.split(',').map(Number),p2=document.getElementById('pt2').value.split(',').map(Number);let d=Math.sqrt(Math.pow(p2[0]-p1[0],2)+Math.pow(p2[1]-p1[1],2));document.getElementById('rDist').innerText="Result: "+(isNaN(d)?"Invalid input":d);}catch{document.getElementById('rDist').innerText="Result: Error";}}
function calcFrac(){let n=parseInt(document.getElementById('fracN').value),d=parseInt(document.getElementById('fracD').value);if(isNaN(n)||isNaN(d)||d===0){document.getElementById('rFrac').innerText="Result: Invalid";return;}let g=gcd(Math.abs(n),Math.abs(d));document.getElementById('rFrac').innerText=`Result: ${n/g} / ${d/g}`;;}
function calcLog(){let n=parseFloat(document.getElementById('logIn').value);document.getElementById('rLog').innerText="Result: "+(isNaN(n)||n<=0?"Invalid input":Math.log10(n));}
function calcLn(){let n=parseFloat(document.getElementById('lnIn').value);document.getElementById('rLn').innerText="Result: "+(isNaN(n)||n<=0?"Invalid input":Math.log(n));}
function calcPctChange(){let o=parseFloat(document.getElementById('pcOld').value),n=parseFloat(document.getElementById('pcNew').value);document.getElementById('rPctChange').innerText="Result: "+(isNaN(o)||isNaN(n)||o===0?"Invalid input":((n-o)/o)*100+"%");}
function calcMod(){let a=parseFloat(document.getElementById('modA').value),b=parseFloat(document.getElementById('modB').value);document.getElementById('rMod').innerText="Result: "+(isNaN(a)||isNaN(b)||b===0?"Invalid input":a%b);}
function calcCube(){let s=parseFloat(document.getElementById('cubeS').value);document.getElementById('rCube').innerText="Result: "+(isNaN(s)||s<0?"Invalid input":Math.pow(s,3));}
function calcSphere(){let r=parseFloat(document.getElementById('sphR').value);document.getElementById('rSph').innerText="Result: "+(isNaN(r)||r<0?"Invalid input":(4/3)*Math.PI*Math.pow(r,3));}

renderGames();
renderProfile();
renderNotes();
updateCalc();
</script>
</body>
</html>
