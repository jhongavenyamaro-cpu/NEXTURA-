<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<meta name="theme-color" content="#100820">
<title>NEXTURA — Gaming Universe</title>
<style>
:root{--bg:#0b0614;--panel:#171027;--panel2:#21143a;--purple:#9b5cff;--pink:#ec4cff;--cyan:#59e5ff;--text:#f7f1ff;--muted:#b8a9ce;--line:#382653}
*{box-sizing:border-box}body{margin:0;background:radial-gradient(circle at 20% 0%,#29134c 0,transparent 35%),radial-gradient(circle at 90% 20%,#241044 0,transparent 30%),var(--bg);color:var(--text);font:15px system-ui,-apple-system,Segoe UI,sans-serif;min-height:100vh}
button,input,textarea,select{font:inherit}button{cursor:pointer;border:0;border-radius:12px;padding:11px 15px;background:linear-gradient(110deg,var(--purple),var(--pink));color:white;font-weight:700}
button.secondary{background:#2a1c40;border:1px solid var(--line)}button.danger{background:#63243d}
input,textarea,select{width:100%;padding:12px;border-radius:10px;border:1px solid var(--line);background:#0f0a1b;color:var(--text);outline:none}textarea{min-height:90px;resize:vertical}
header{position:sticky;top:0;z-index:5;background:#0b0614eF;border-bottom:1px solid var(--line);backdrop-filter:blur(12px);padding:13px 5%;display:flex;align-items:center;justify-content:space-between;gap:12px}
.logo{font-size:23px;font-weight:950;letter-spacing:2px;color:#fff;text-shadow:0 0 14px var(--purple)}.logo span{color:var(--cyan)}
.wrap{max-width:1100px;margin:auto;padding:25px 18px 70px}.hero{padding:30px 24px;border:1px solid #58347d;border-radius:22px;background:linear-gradient(120deg,#261344dd,#140c24ee);box-shadow:0 0 35px #8e40ff22}.hero h1{font-size:clamp(32px,7vw,58px);line-height:1.02;margin:8px 0}.hero p{color:var(--muted);max-width:650px}.eyebrow{color:var(--cyan);font-weight:800;letter-spacing:2px;font-size:12px}.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:15px;margin-top:16px}.card,.panel{background:linear-gradient(145deg,#1b1230,#120d20);border:1px solid var(--line);border-radius:17px;padding:17px}.card h3{margin:8px 0}.card p,.muted{color:var(--muted)}.game-art{height:115px;border-radius:12px;background:linear-gradient(135deg,#5122a0,#c13eac 55%,#2c9ab4);display:grid;place-items:center;font-size:42px;margin-bottom:12px}.tag{display:inline-block;border:1px solid #694694;color:#d9baff;border-radius:30px;padding:4px 9px;font-size:11px;margin:2px}.section-head{display:flex;align-items:center;justify-content:space-between;gap:10px;margin:28px 0 10px}.section-head h2{margin:0}.tabs{display:flex;gap:7px;overflow:auto;padding:14px 0}.tabs button{white-space:nowrap;background:#211633;border:1px solid var(--line)}.tabs button.active{background:linear-gradient(110deg,var(--purple),var(--pink));border-color:transparent}.hidden{display:none!important}.form{max-width:460px;margin:35px auto}.form>*{margin-bottom:12px}.notice{padding:12px;border-radius:10px;background:#211633;color:#d9c9ee;border:1px solid var(--line);font-size:13px}.row{display:flex;gap:9px;align-items:center;flex-wrap:wrap}.row>*{flex:1}.small{font-size:12px}.chatlog{height:240px;overflow:auto;background:#0e0918;border:1px solid var(--line);border-radius:12px;padding:12px;margin:12px 0}.msg{padding:8px 10px;margin:7px 0;border-radius:10px;background:#211633;max-width:90%;overflow-wrap:anywhere}.msg b{color:var(--cyan)}footer{text-align:center;color:#88799c;padding:30px 12px;font-size:12px}.profile-icon{width:42px;height:42px;border-radius:50%;display:grid;place-items:center;background:linear-gradient(135deg,var(--purple),var(--pink));font-weight:900}
@media(max-width:600px){header{padding:12px 4%}.wrap{padding:17px 13px 50px}.hero{padding:23px 18px}.section-head{align-items:flex-start}}
</style>
</head>
<body>
<header><div class="logo">NEXT<span>URA</span></div><div class="row" style="flex:0 1 auto"><span id="headerUser" class="small muted"></span><button id="logoutBtn" class="secondary hidden">Log out</button></div></header>
<main class="wrap">
<section id="authView" class="form panel">
 <div class="eyebrow">WELCOME TO THE FUTURE</div><h1>Enter NEXTURA</h1><p class="muted">One account. Play, create, share, and connect.</p>
 <div class="tabs"><button id="loginTab" class="active">Log in</button><button id="registerTab" class="secondary">Create account</button></div>
 <form id="authForm">
  <input id="username" placeholder="Username" autocomplete="username" required maxlength="20">
  <input id="password" placeholder="Password (at least 6 characters)" type="password" autocomplete="current-password" required minlength="6">
  <button id="authSubmit" type="submit" style="width:100%">Log in</button>
 </form>
 <div id="authMessage" class="small muted"></div>
 <div class="notice">Demo version: accounts are stored only in this browser on this device. Do not use a real password or share personal information.</div>
</section>
<section id="appView" class="hidden">
 <div class="hero"><div class="eyebrow">YOUR NEXT LEVEL STARTS HERE</div><h1>PLAY. CREATE.<br><span style="color:var(--cyan)">CONNECT.</span></h1><p>Discover community games, build your own ideas, and meet other creators in the NEXTURA universe.</p><div class="row" style="max-width:450px"><button onclick="showSection('games')">Explore games</button><button class="secondary" onclick="showSection('studio')">Open Creator Studio</button></div></div>
 <nav class="tabs" aria-label="Main navigation">
  <button class="active" data-section="games">🎮 Games</button><button data-section="studio">🛠 Creator Studio</button><button data-section="chat">💬 Community chat</button><button data-section="profile">👤 Profile</button>
 </nav>
 <section id="games" class="page">
  <div class="section-head"><h2>Game universe</h2><span class="tag">COMMUNITY PICKS</span></div>
  <div id="gameGrid" class="grid"></div>
 </section>
 <section id="studio" class="page hidden">
  <div class="section-head"><h2>Creator Studio</h2><span class="tag">BUILD SOMETHING NEW</span></div>
  <div class="panel">
   <h3>Publish a game listing</h3><p class="muted small">Add a game idea or a playable web-game link. Uploaded links are shown to users; this demo does not host game files.</p>
   <form id="gameForm">
    <input id="gameName" placeholder="Game title" maxlength="35" required>
    <select id="gameCategory"><option>Adventure</option><option>Action</option><option>Strategy</option><option>Racing</option><option>Creative</option><option>Other</option></select>
    <textarea id="gameDescription" placeholder="Describe your game..." maxlength="240" required></textarea>
    <input id="gameUrl" type="url" placeholder="Optional game URL (https://...)">
    <button type="submit">＋ Publish game</button>
   </form>
  </div>
  <div class="section-head"><h2>Your creations</h2></div><div id="myGames" class="grid"></div>
 </section>
 <section id="chat" class="page hidden">
  <div class="section-head"><h2>Community chat</h2><span class="tag">LOCAL DEMO CHAT</span></div>
  <div class="panel"><p class="muted small">This is a local demonstration chat. Messages are visible only in this browser and are not sent to other users.</p>
   <div id="chatLog" class="chatlog" aria-live="polite"></div>
   <form id="chatForm" class="row"><input id="chatInput" placeholder="Write a friendly message..." maxlength="180" required><button>Send</button></form>
   <p class="small muted">Keep chats kind. Never share your address, phone number, school details, passwords, or private photos.</p>
  </div>
 </section>
 <section id="profile" class="page hidden">
  <div class="section-head"><h2>Your profile</h2></div>
  <div class="panel"><div class="row" style="justify-content:flex-start"><div class="profile-icon" id="avatar">N</div><div><h3 id="profileName" style="margin:0"></h3><span class="muted small">NEXTURA member · Player & Creator</span></div></div>
   <p class="muted">Your account can both play games and publish game listings. You do not need separate player and developer accounts.</p>
   <button class="secondary" onclick="showSection('studio')">Manage creations</button>
  </div>
 </section>
</section>
</main>
<footer>NEXTURA · A community gaming prototype · Be kind, create safely.</footer>
<script>
const $=id=>document.getElementById(id);
const get=(key, fallback)=>{try{return JSON.parse(localStorage.getItem(key))??fallback}catch{return fallback}};
const set=(key,val)=>localStorage.setItem(key,JSON.stringify(val));
let current=get('nx_current',null), mode='login';
let games=get('nx_games',[
 {id:'starter1',name:'Neon Quest',category:'Adventure',description:'Explore a glowing world and discover new paths.',owner:'NEXTURA',url:'',icon:'🌌'},
 {id:'starter2',name:'Battle Tactics',category:'Strategy',description:'Plan your moves and challenge your own high score.',owner:'NEXTURA',url:'',icon:'⚡'},
 {id:'starter3',name:'Sky Racers',category:'Racing',description:'A fast-paced racing concept through neon skies.',owner:'NEXTURA',url:'',icon:'🏎️'}
]);
let messages=get('nx_messages',[]);
function showAuth(){ $('authView').classList.remove('hidden');$('appView').classList.add('hidden');$('logoutBtn').classList.add('hidden');$('headerUser').textContent=''; }
function showApp(){ $('authView').classList.add('hidden');$('appView').classList.remove('hidden');$('logoutBtn').classList.remove('hidden');$('headerUser').textContent='Hi, '+current+'!';$('profileName').textContent=current;$('avatar').textContent=current[0].toUpperCase();renderGames();renderChat(); }
function showSection(name){document.querySelectorAll('.page').forEach(p=>p.classList.add('hidden'));$(name).classList.remove('hidden');document.querySelectorAll('[data-section]').forEach(b=>b.classList.toggle('active',b.dataset.section===name));if(name==='studio')renderMyGames();}
document.querySelectorAll('[data-section]').forEach(b=>b.addEventListener('click',()=>showSection(b.dataset.section)));
$('loginTab').onclick=()=>setMode('login');$('registerTab').onclick=()=>setMode('register');
function setMode(m){mode=m;$('loginTab').classList.toggle('active',m==='login');$('registerTab').classList.toggle('active',m==='register');$('authSubmit').textContent=m==='login'?'Log in':'Create account';$('password').autocomplete=m==='login'?'current-password':'new-password';$('authMessage').textContent='';}
$('authForm').addEventListener('submit',e=>{e.preventDefault();const name=$('username').value.trim(),pass=$('password').value;if(!/^[a-zA-Z0-9_]{3,20}$/.test(name)){ $('authMessage').textContent='Username must be 3–20 characters: letters, numbers, or underscore.';return;}if(pass.length<6){$('authMessage').textContent='Use at least 6 characters for this demo password.';return;}let users=get('nx_users',{});if(mode==='register'){if(users[name]){$('authMessage').textContent='That username is already taken on this device.';return;}users[name]=pass;set('nx_users',users);}else if(users[name]!==pass){$('authMessage').textContent='Username or password is incorrect on this device.';return;}current=name;set('nx_current',current);showApp();});
$('logoutBtn').onclick=()=>{current=null;set('nx_current',null);showAuth();};
function escapeHTML(s){return String(s).replace(/[&<>"']/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));}
function gameCard(g){const safeUrl=(g.url&&/^https:\/\/[^\s]+$/i.test(g.url))?g.url:'';return `<article class="card"><div class="game-art">${g.icon||'🎮'}</div><span class="tag">${escapeHTML(g.category)}</span><h3>${escapeHTML(g.name)}</h3><p>${escapeHTML(g.description)}</p><p class="small">Creator: ${escapeHTML(g.owner)}</p>${safeUrl?`<a href="${escapeHTML(safeUrl)}" target="_blank" rel="noopener noreferrer"><button>Open game ↗</button></a>`:'<button class="secondary" disabled title="A playable link has not been added">Coming soon</button>'}</article>`;}
function renderGames(){$('gameGrid').innerHTML=games.map(gameCard).join('');renderMyGames();}
function renderMyGames(){let mine=games.filter(g=>g.owner===current);$('myGames').innerHTML=mine.length?mine.map(g=>`<div class="card"><h3>${escapeHTML(g.name)}</h3><p class="muted">${escapeHTML(g.category)} · ${escapeHTML(g.description)}</p><button class="danger" onclick="deleteGame('${g.id}')">Delete listing</button></div>`).join(''):'<div class="notice">You have not published a game yet. Create your first listing above!</div>';}
$('gameForm').addEventListener('submit',e=>{e.preventDefault();const url=$('gameUrl').value.trim();if(url&&!/^https:\/\/[^\s]+$/i.test(url)){alert('Please use a valid HTTPS link.');return;}games.unshift({id:'g'+Date.now(),name:$('gameName').value.trim(),category:$('gameCategory').value,description:$('gameDescription').value.trim(),owner:current,url,icon:['🎮','🚀','🧩','⚔️','🏎️','🌟'][Math.floor(Math.random()*6)]});set('nx_games',games);$('gameForm').reset();renderGames();renderMyGames();alert('Your game listing has been published on this device!');});
function deleteGame(id){games=games.filter(g=>!(g.id===id&&g.owner===current));set('nx_games',games);renderGames();renderMyGames();}
function renderChat(){$('chatLog').innerHTML=messages.map(m=>`<div class="msg"><b>${escapeHTML(m.user)}:</b> ${escapeHTML(m.text)}</div>`).join('')||'<p class="muted small">No messages yet. Say hello!</p>';$('chatLog').scrollTop=$('chatLog').scrollHeight;}
$('chatForm').addEventListener('submit',e=>{e.preventDefault();const text=$('chatInput').value.trim();if(!text)return;messages.push({user:current,text});messages=messages.slice(-60);set('nx_messages',messages);$('chatInput').value='';renderChat();});
if(current)showApp();else showAuth();
</script>
</body></html>
