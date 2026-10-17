# Anas-Lamora

<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta name="theme-color" content="#090909">
<title>أنا ولمورة ❤️</title>
<style>
:root {
  --bg:#090909;
  --panel:#171512;
  --gold:#e1bd70;
  --text:#f8f1e4;
  --muted:#aaa093;
  --border:#46391f;
}
* { box-sizing:border-box; }
body {
  margin:0;
  background:radial-gradient(ellipse at top,#282012,var(--bg) 65%);
  color:var(--text);
  font-family:system-ui,Tahoma,sans-serif;
  min-height:100vh;
}
header { padding:22px 18px; text-align:center; }
header h1 { color:var(--gold); margin-bottom:6px; }
header p { color:var(--muted); }
main { max-width:720px; margin:auto; padding:12px; }
.card {
  background:var(--panel);
  border:1px solid var(--border);
  border-radius:18px;
  padding:18px;
  margin-bottom:14px;
}
h2,h3 { color:var(--gold); }
button,input,textarea {
  font:inherit;
  border-radius:11px;
  padding:11px;
}
button {
  background:#292114;
  border:1px solid var(--border);
  color:var(--text);
  cursor:pointer;
  margin:3px;
}
button:hover { border-color:var(--gold); }
input,textarea {
  width:100%;
  margin:6px 0;
  background:#090909;
  border:1px solid var(--border);
  color:white;
}
nav {
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:6px;
  margin-bottom:15px;
}
nav button { min-height:56px; }
.primary { background:var(--gold); color:#171006; }
.muted { color:var(--muted); line-height:1.8; }
.big { font-size:28px; color:var(--gold); }
.page { display:none; }
.page.active { display:block; }
.item {
  padding:10px 0;
  border-bottom:1px solid var(--border);
  overflow-wrap:anywhere;
}
footer {
  text-align:center;
  color:var(--muted);
  padding:20px;
  font-size:12px;
}
</style>
</head>
<body>
<header>
  <h1>♥ أنا ولمورة ♥</h1>
  <p>مساحتنا الخاصة — ذكريات، تعلّم وأحلام مشتركة</p>
</header>

<main>
<nav>
  <button onclick="show('home')">🏠 الرئيسية</button>
  <button onclick="show('together')">💌 مساحتنا</button>
  <button onclick="show('study')">📚 الدراسة</button>
  <button onclick="show('games')">🎮 الألعاب</button>
  <button onclick="show('chat')">💬 المراسلة</button>
  <button onclick="show('secret')">🔐 السرية</button>
  <button onclick="show('settings')">⚙️ الإعدادات</button>
</nav>

<section id="home" class="page active">
  <div class="card">
    <p>✨ أهلًا بكما في عالمكما الصغير</p>
    <h2 id="greeting">أنا ولمورة</h2>
    <p class="muted">مساحة تجمع اللحظات الجميلة والتطوّر الدراسي.</p>
    <div class="big">🔥 <span id="flame">0</span> نقطة</div>
    <p>عداد الأيام: <strong id="days">حدّد تاريخ البداية</strong></p>
    <button class="primary" onclick="show('together')">اكتشف مساحتنا</button>
  </div>
  <div class="card">
    <h3>💛 رسالة اليوم</h3>
    <p id="daily"></p>
    <button onclick="newMessage()">رسالة أخرى ✨</button>
  </div>
  <div class="card">
    <h3>🎯 هدف اليوم</h3>
    <p>أنجز مهمة صغيرة تقرّبك من حلمك.</p>
    <button onclick="show('study')">ابدأ الدراسة</button>
  </div>
</section>

<section id="together" class="page">
  <div class="card">
    <h2>💌 مساحتنا</h2>
    <label>اكتب رسالة لطيفة</label>
    <textarea id="loveInput" placeholder="رسالة من القلب..."></textarea>
    <button class="primary" onclick="saveLove()">حفظ الرسالة</button>
    <div id="loveList"></div>
  </div>
  <div class="card">
    <h3>📆 عداد الأيام</h3>
    <label>تاريخ البداية</label>
    <input id="startDate" type="date">
    <button onclick="setDate()">حفظ التاريخ</button>
  </div>
  <div class="card">
    <h3>✨ الذكريات</h3>
    <input id="memoryInput" placeholder="ذكرى تريد حفظها">
    <button onclick="addMemory()">حفظ الذكرى</button>
    <div id="memories"></div>
  </div>
</section>

<section id="study" class="page">
  <div class="card">
    <h2>📚 مساحة الدراسة</h2>
    <p class="muted">قسّم أهدافك إلى مهام صغيرة واحتفل بإنجازها.</p>
    <input id="taskInput" placeholder="مثال: مراجعة أساسيات بايثون">
    <button class="primary" onclick="addTask()">إضافة مهمة</button>
    <div id="tasks"></div>
  </div>
  <div class="card">
    <h3>⏳ مؤقّت التركيز</h3>
    <div class="big" id="clock">25:00</div>
    <button class="primary" onclick="startTimer()">ابدأ</button>
    <button onclick="pauseTimer()">إيقاف مؤقت</button>
    <button onclick="resetTimer()">إعادة</button>
  </div>
  <div class="card">
    <h3>📝 ملاحظاتي</h3>
    <textarea id="noteInput" placeholder="اكتب ملخصًا أو ملاحظة..."></textarea>
    <button onclick="saveNote()">حفظ الملاحظة</button>
    <div id="notes"></div>
  </div>
</section>

<section id="games" class="page">
  <div class="card">
    <h2>🎮 تحدّي المعرفة</h2>
    <p id="question">ما ناتج 3 × 4؟</p>
    <div id="answers"></div>
    <p>النقاط: <span id="score">0</span></p>
    <button onclick="nextQuestion()">سؤال جديد</button>
  </div>
  <div class="card">
    <h3>🔥 شعلة الحماسة</h3>
    <p class="muted">أضف نقطة بعد إتمام تحدٍّ أو هدف حقيقي.</p>
    <button class="primary" onclick="addFlame()">إنجاز جديد +1</button>
  </div>
</section>

<section id="chat" class="page">
  <div class="card">
    <h2>💬 مساحة المراسلة</h2>
    <p class="muted">
      هذه نسخة محلية للتجربة. الرسائل تُحفظ على هذا الجهاز فقط
      ولا تصل تلقائيًا إلى هاتف آخر.
    </p>
    <div id="chatList"></div>
    <textarea id="chatInput" placeholder="اكتب رسالتك..."></textarea>
    <button class="primary" onclick="sendChat()">إضافة الرسالة</button>
  </div>
</section>

<section id="secret" class="page">
  <div class="card">
    <h2>🔐 المساحة السرية</h2>
    <p class="muted">أنشئ رمزًا محليًا من أربعة أرقام.</p>
    <input id="pinInput" type="password" inputmode="numeric"
           maxlength="4" placeholder="رمز الدخول">
    <button class="primary" onclick="unlock()">دخول</button>
    <div id="secretArea" hidden>
      <textarea id="secretInput" placeholder="ملاحظة خاصة"></textarea>
      <button onclick="saveSecret()">حفظ النص</button>
    </div>
  </div>
</section>

<section id="settings" class="page">
  <div class="card">
    <h2>⚙️ التخصيص</h2>
    <label>اسمك</label>
    <input id="myName" placeholder="أنا">
    <label>اسم الطرف الآخر</label>
    <input id="partnerName" placeholder="لمورة">
    <button class="primary" onclick="saveNames()">حفظ الأسماء</button>
    <button onclick="exportData()">تصدير نسخة احتياطية</button>
  </div>
</section>
</main>

<footer>
  صُنع بحب ❤️ — بيانات هذه النسخة محفوظة محليًا في المتصفح.
</footer>

<script>
const $ = id => document.getElementById(id);
const get = (key, fallback) => {
  try {
    const value = localStorage.getItem("alm_" + key);
    return value === null ? fallback : JSON.parse(value);
  } catch { return fallback; }
};
const put = (key, value) =>
  localStorage.setItem("alm_" + key, JSON.stringify(value));

let flame = get("flame", 0);
let tasks = get("tasks", []);
let memories = get("memories", []);
let loves = get("loves", []);
let notes = get("notes", []);
let chats = get("chats", []);
let score = 0;
let questionIndex = 0;
let seconds = 1500;
let timer = null;
let startDate = get("startDate", "");
let pin = get("pin", "");
let unlocked = false;

const messages = [
  "وجودك يجعل الأيام أجمل ❤️",
  "كل خطوة صغيرة اليوم تقرّبنا من أحلامنا ✨",
  "أتمنى لك يومًا هادئًا ومليئًا بالنجاح.",
  "أجمل اللحظات هي التي نصنعها بقلوب طيبة 💛"
];
const quiz = [
  {q:"ما ناتج 3 × 4؟", a:["7","12","14"], c:1},
  {q:"ما الكلمة المستخدمة لتعريف دالة في بايثون؟", a:["func","def","loop"], c:1},
  {q:"ما الكوكب المعروف بالكوكب الأحمر؟", a:["المريخ","الزهرة","زحل"], c:0},
  {q:"كم دقيقة في ربع ساعة؟", a:["10","15","20"], c:1}
];

function show(id) {
  document.querySelectorAll(".page").forEach(p => p.classList.remove("active"));
  $(id).classList.add("active");
  if (id === "study") renderTasks();
  if (id === "together") { renderMemories(); renderLoves(); }
  if (id === "chat") renderChats();
  if (id === "games") renderQuestion();
  if (id === "home") updateHome();
}
function saveNames() {
  put("me", $("myName").value.trim() || "أنا");
  put("partner", $("partnerName").value.trim() || "لمورة");
  updateHome();
  alert("تم حفظ الأسماء");
}
function updateHome() {
  const me = get("me", "أنا"), partner = get("partner", "لمورة");
  $("greeting").textContent = me + " ❤️ " + partner;
  $("flame").textContent = flame;
  $("daily").textContent = messages[new Date().getDate() % messages.length];
  if (startDate) {
    const days = Math.max(0, Math.floor((Date.now() - new Date(startDate+"T00:00:00")) / 86400000));
    $("days").textContent = days + " يوم";
  } else $("days").textContent = "حدّد تاريخ البداية";
}
function newMessage() {
  $("daily").textContent = messages[Math.floor(Math.random()*messages.length)];
}
function setDate() {
  startDate = $("startDate").value;
  put("startDate", startDate);
  updateHome();
}
function saveLove() {
  const text = $("loveInput").value.trim();
  if (!text) return alert("اكتب رسالة أولًا");
  loves.unshift(text); put("loves", loves);
  $("loveInput").value = ""; renderLoves();
}
function renderLoves() {
  $("loveList").innerHTML = loves.map(t => `<div class="item">${escapeHTML(t)}</div>`).join("");
}
function addMemory() {
  const text = $("memoryInput").value.trim();
  if (!text) return;
  memories.unshift(text); put("memories", memories);
  $("memoryInput").value = ""; renderMemories();
}
function renderMemories() {
  $("memories").innerHTML = memories.map(t => `<div class="item">${escapeHTML(t)}</div>`).join("");
}
function addTask() {
  const text = $("taskInput").value.trim();
  if (!text) return alert("اكتب اسم المهمة");
  tasks.push({text, done:false}); put("tasks", tasks);
  $("taskInput").value = ""; renderTasks();
}
function renderTasks() {
  $("tasks").innerHTML = tasks.map((t,i) =>
    `<div class="item"><label><input type="checkbox" style="width:auto" ${t.done?"checked":""} onchange="toggleTask(${i})"> ${escapeHTML(t.text)}</label> <button onclick="deleteTask(${i})">حذف</button></div>`
  ).join("");
}
function toggleTask(i) {
  tasks[i].done = !tasks[i].done;
  if (tasks[i].done) addFlame(false);
  put("tasks", tasks); renderTasks();
}
function deleteTask(i) {
  tasks.splice(i,1); put("tasks",tasks); renderTasks();
}
function addFlame(showAlert=true) {
  flame++; put("flame",flame); $("flame").textContent=flame;
  if(showAlert) alert("أحسنت! أضيفت نقطة إلى شعلة الحماسة 🔥");
}
function saveNote() {
  const text = $("noteInput").value.trim();
  if (!text) return;
  notes.unshift(text); put("notes",notes);
  $("noteInput").value="";
  $("notes").innerHTML=notes.map(n=>`<div class="item">${escapeHTML(n)}</div>`).join("");
}
function renderQuestion() {
  const q=quiz[questionIndex % quiz.length];
  $("question").textContent=q.q;
  $("answers").innerHTML=q.a.map((a,i)=>
    `<button onclick="answer(${i})">${escapeHTML(a)}</button>`).join("");
  $("score").textContent=score;
}
function answer(i) {
  if(i===quiz[questionIndex%quiz.length].c) {
    score++; addFlame(false); alert("إجابة صحيحة! + نقطة 🔥");
  } else alert("محاولة جيدة! جرّب السؤال التالي.");
  questionIndex++; renderQuestion();
}
function nextQuestion() { questionIndex++; renderQuestion(); }
function updateClock() {
  $("clock").textContent =
    String(Math.floor(seconds/60)).padStart(2,"0")+":"+
    String(seconds%60).padStart(2,"0");
}
function startTimer() {
  if(timer) return;
  timer=setInterval(()=>{
    seconds--; updateClock();
    if(seconds<=0) {
      clearInterval(timer); timer=null; seconds=1500;
      addFlame(false); updateClock();
      alert("انتهت جلسة التركيز! خذ استراحة قصيرة.");
    }
  },1000);
}
function pauseTimer() { clearInterval(timer); timer=null; }
function resetTimer() { pauseTimer(); seconds=1500; updateClock(); }
function sendChat() {
  const text=$("chatInput").value.trim();
  if(!text) return;
  chats.push(text); put("chats",chats);
  $("chatInput").value=""; renderChats();
}
function renderChats() {
  $("chatList").innerHTML=chats.map(t=>`<div class="item">💬 ${escapeHTML(t)}</div>`).join("");
}
function unlock() {
  const value=$("pinInput").value;
  if(!/^\d{4}$/.test(value)) return alert("أدخل أربعة أرقام");
  if(!pin) { pin=value; put("pin",pin); unlocked=true; }
  else if(value===pin) unlocked=true;
  else return alert("الرمز غير صحيح");
  $("secretArea").hidden=!unlocked;
  $("secretInput").value=get("secretText","");
}
function saveSecret() {
  if(!unlocked) return;
  put("secretText",$("secretInput").value);
  alert("تم حفظ النص على هذا الجهاز");
}
function escapeHTML(s) {
  return String(s).replace(/[&<>"']/g,c=>({
    "&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"
  })[c]);
}
function exportData() {
  const data={};
  for(let i=0;i<localStorage.length;i++){
    const k=localStorage.key(i);
    if(k && k.startsWith("alm_")) data[k]=localStorage.getItem(k);
  }
  const blob=new Blob([JSON.stringify(data,null,2)],{type:"application/json"});
  const url=URL.createObjectURL(blob);
  const a=document.createElement("a");
  a.href=url; a.download="ana-wa-lamoura-backup.json"; a.click();
  URL.revokeObjectURL(url);
}
$("myName").value=get("me","أنا");
$("partnerName").value=get("partner","لمورة");
$("startDate").value=startDate;
updateHome();
renderQuestion();
updateClock();
</script>
</body>
</html>
