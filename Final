<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Chinese Exam – All Sections</title>
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
  <style>
    body { font-family: 'Inter', 'Segoe UI', Arial, sans-serif; background: #f6f6fa; color: #222a35; margin: 0;}
    .container { max-width: 950px; margin: 36px auto; background: #fff; border-radius: 18px; box-shadow: 0 8px 60px rgba(36,47,90,0.10); padding: 46px 32px 36px 32px; min-height: 88vh;}
    .section { margin-bottom: 40px; border-bottom: 2px solid #e1e5f1; padding-bottom: 22px;}
    .section:last-child { border-bottom: none;}
    h1 { text-align: center; color: #20448a; font-size: 2.3em; margin-bottom: 12px; margin-top: 2px; font-weight: 700;}
    h2 { color: #28508a; margin: 12px 0 18px 0; font-size: 1.22em; font-weight: 700; border-left: 6px solid #20448a; padding-left: 13px;}
    .jump-links { margin-bottom: 20px; display: flex; flex-wrap: wrap; gap:13px; justify-content:center;}
    .jump-links a { text-decoration:none; color:#2351a2; font-weight:600; font-size:.98em; background:#e6eafb; border:1.4px solid #3564b4; padding:6px 18px; border-radius:18px; letter-spacing: .01em; transition:background 0.22s, color 0.23s, border 0.18s;}
    .jump-links a:hover { background: #dbe2f5; color: #143c74; border-color: #143c74;}
    .question-block { margin-bottom: 18px; padding: 14px 15px 13px 15px; border-radius: 9px; background: #fafdff; border: 1px solid #e4e8f3; box-shadow: 0 2px 11px rgba(54,91,170,0.032);}
    .audio-block { margin: 7px 0 15px 0; }
    .options button { display:block; width:100%; padding:12px 13px; margin-bottom: 6px; font-size: 1.02em; border: 1.7px solid #3666b7; background:#fff; color:#20448a; cursor:pointer; border-radius:6px; text-align:left; transition:background 0.13s, color 0.14s, border 0.14s;}
    .options button.selected { background: #3666b7; color:#fff; border: 1.8px solid #20448a;}
    .options button.correct { background: #cff7e4; color: #187951; border:1.7px solid #19a967;}
    .options button.incorrect { background: #faeeee; color: #cf362a; border:1.7px solid #be3c1d;}
    .text-input, .text-area, .name-input { width: 99%; padding: 10px 13px; margin-top: 7px; font-size: 1.03em; border: 1.45px solid #b3bfd8; border-radius: 6px; background:#fafdff; color: #212f44; transition: border 0.2s;}
    .text-area { min-height: 75px; }
    .name-input { max-width: 350px; font-weight:600;}
    .submit-btn, .start-btn { display:block; margin: 34px auto 0 auto; padding: 13px 38px; font-size:1.13em; font-weight:700; background:#20448a; color:#fff; border:none; border-radius:9px; cursor:pointer; box-shadow: 0 3px 17px rgba(54,91,131,0.11); transition:background 0.22s; letter-spacing:.02em;}
    .submit-btn:active, .start-btn:active { background:#1c376c; }
    #responses-area { display: none; margin: 40px auto 0 auto; max-width: 950px;}
    .answers-block { background: #f8fafd; border: 1.65px solid #ccd8f3; border-radius: 11px; padding: 28px; margin-bottom: 22px; box-shadow:0 3px 12px #dde5f2d3;}
    .answers-block h3 { color: #245292;}
    .answer-table { border-collapse:collapse; width:100%;margin:20px 0;}
    .answer-table th, .answer-table td { border: 1px solid #e0e3ea; padding:7px 10px;}
    .answer-table th { background:#e6eafb; color:#20448a; }
    .answer-table td { background:#fff;}
    .answer-table tr.correct td { background: #cff7e4; color: #019b63;}
    .answer-table tr.incorrect td { background: #faeeee; color: #cf362a;}
    .checkmark { font-weight: 900; color: #19a967; font-size:1.19em;}
    .xmark { font-weight: 900; color: #cf362a; font-size:1.19em;}
    .congrats { text-align:center; font-size:1.7em; color:#28508a; margin-top: 18px; margin-bottom: 21px; font-weight:700;}
    .essay-block { background:#fff; border:1.7px solid #b2bdda; padding:18px; border-radius:8px;}
    .manual-mark {color:#365b83;font-weight:600;}
    .student-header {font-size:1.15em;margin-bottom:7px;}
    .timer-bar { padding: 10px 0 18px 0; text-align: center; font-size: 1.18em; color: #28508a; font-weight: 600;}
    .hidden {display: none !important;}
    @media (max-width: 1040px) { .container,#responses-area {padding:2vw;} .answers-block{padding:5vw;} }
    @media (max-width: 700px) { .container,#responses-area{padding:1vw;} .answers-block{padding:0.5vw;} }
    iframe, audio {max-width:99vw;}
  </style>
<script>
let timer = 0, timerInterval, examStarted = false;
function formatTimer(secs) { let m = String(Math.floor(secs/60)).padStart(2,"0"); let s = String(secs%60).padStart(2,"0"); return `${m}:${s}`; }
function updateTimer() {
  const display = document.getElementById("timer-display");
  if (display) display.textContent = "Exam Timer: " + formatTimer(timer);
}
function tickTimer() {
  timer++;
  updateTimer();
}
function startExam() {
  examStarted = true;
  document.getElementById("timer-bar").innerHTML = '<span id="timer-display">Exam Timer: 00:00</span>';
  document.getElementById("main-form").classList.remove("hidden");
  document.getElementById("start-area").classList.add("hidden");
  document.querySelectorAll("#main-form input,#main-form textarea,#main-form button").forEach(function(el){
    if (!el.classList.contains("submit-btn")) el.disabled = false;
  });
  updateTimer();
  timerInterval = setInterval(tickTimer, 1000);
}
function selectOption(qid, btn) {
  if (!examStarted) return;
  var parent = btn.parentElement;
  for (var i = 0; i < parent.children.length; i++) { parent.children[i].classList.remove('selected');}
  btn.classList.add('selected');
}
function getSelectedOptionText(parent) {
  const btn = parent.querySelector('.selected');
  return btn ? btn.innerText.trim() : "";
}
function escapeHtml(str) { return String(str||"").replace(/</g, '&lt;').replace(/>/g, '&gt;').replace(/"/g, '&quot;').replace(/'/g, '&#039;'); }
function compareStrings(ans, key) {
  return (ans || "").replace(/[\s。．.]+/g, '').toLowerCase() === (key || '').replace(/[\s。．.]+/g, '').toLowerCase();
}
const answerKey = {
Q1: "b. 中国城", Q2: "b. 酸辣汤", Q3: "b. 下雪了", Q4: "c. 坐地铁",
Q5: "b. 开生日晚会", Q6: "b. 唱歌跳舞", Q7: "b. 饮料或者水果", Q8: "d. 大学的北边", Q9: "c. 她的眼睛又红又痒", Q10: "c. 一天三次",
Q36: "b. 我把书放在桌子上", Q37: "b. 我去过中国", Q38: "a. 我一吃饭就睡觉", Q39: "a. 他比我高", Q40: "a. 我没有他那么高", Q41: "b. 不下雨了", Q42: "a. 他不但很聪明，而且很帅",
Q43: "b. 我一点儿时间都没有", Q44: "a. 我家离学校很近", Q45: "a. 天气越来越暖和", Q46: "b. 我对花生过敏", Q47: "a. 我学了三年了", Q48: "a. 我没有时间，再说也没有钱",
Q49: "a. 请说得慢一点儿", Q50: "a. 他正在吃饭呢",
Q11: "我一回家就做功课。", Q12: "中国菜又好吃又便宜。", Q13: "悉尼没有北京那么冷。", Q14: "我学中文学了两年了。", Q15: "图书馆离学生活动中心很近。",
Q16: "他到医院去看病。", Q17: "我去过中国城三次。", Q18: "天气越来越冷了。", Q19: "请把这些药吃完。", Q20: "他又聪明又用功。",
Q21: "今天的天气冷是冷，可是没下雨。", Q22: "李友觉得滑冰没有打篮球有意思。", Q23: "糖醋鱼甜甜的，酸酸的，好吃极了。",
Q24: "我考完试就去电脑中心。", Q25: "我喜欢学中文，因为中文比日文容易一点儿。",
Q26: "我这个星期太忙了，一点儿时间都没有。", Q27: "你一往左拐，图书馆就在运动场和书店中间。", Q28: "她正在切蛋糕呢。",
Q29: "我学了两年中文了。", Q30: "把书放在桌子上。",
Q31: "He takes medicine three times a day, two pills each time.",
Q32: "The weather is getting colder and colder.",
Q33: "I am allergic to peanuts.",
Q34: "Where did you learn Chinese?",
Q35: "The library is very close to the sports field.",
Q51: "你给我五十块，我找你二十块零五分。", Q52: "不但今天下雨，而且明天也下雨。",
Q53: "我的同学们去年都去了中国，可是我没去。", Q54: "他去了图书馆，所以今天不能跟我们去饭馆吃饭。",
Q55: "那个地方比学校远一点儿，我们坐车去吧。", Q56: "我昨天见了他。",
Q57: "我不舒服，我头疼死了。", Q58: "他对海鲜过敏。", Q59: "我没把作业做完。",
Q60: "他正在客厅唱歌。"
};

// === GOOGLE SHEETS SUBMISSION SETTINGS ===
// After you deploy the Google Apps Script, paste your Web App URL between the quotes below.
// It should end with /exec
const GOOGLE_SCRIPT_URL = "PASTE_YOUR_GOOGLE_APPS_SCRIPT_WEB_APP_URL_HERE";

async function submitToGoogleSheet(payload) {
  if (!GOOGLE_SCRIPT_URL || GOOGLE_SCRIPT_URL.includes("PASTE_YOUR")) {
    console.warn("Google Sheets URL is not set yet. Results were shown locally only.");
    return false;
  }
  try {
    await fetch(GOOGLE_SCRIPT_URL, {
      method: "POST",
      mode: "no-cors",
      headers: { "Content-Type": "text/plain;charset=utf-8" },
      body: JSON.stringify(payload)
    });
    return true;
  } catch (error) {
    console.error("Could not submit to Google Sheets:", error);
    return false;
  }
}

async function onSubmitExam(event) {
  event.preventDefault();
  clearInterval(timerInterval);
  var name = document.getElementById('student-name').value.trim();
  if(!name) {
    alert("Please enter your name before submitting.");
    document.getElementById('student-name').focus();
    return false;
  }
  var answers = {}, allQuestions = [];
  for (let q = 1; q <= 10; q++) { answers['Q'+q] = getSelectedOptionText(document.getElementById('q'+q+'_block')); allQuestions.push('Q'+q);}
  for (let q = 11; q <= 20; q++) { let inp = document.getElementById('q'+q+'_input'); answers['Q'+q] = inp ? inp.value.trim() : ''; allQuestions.push('Q'+q);}
  for (let q = 21; q <= 30; q++) { let inp = document.getElementById('q'+q+'_input'); answers['Q'+q] = inp ? inp.value.trim() : ''; allQuestions.push('Q'+q);}
  for (let q = 31; q <= 35; q++) { let inp = document.getElementById('q'+q+'_input'); answers['Q'+q] = inp ? inp.value.trim() : ''; allQuestions.push('Q'+q);}
  for (let q = 36; q <= 50; q++) { answers['Q'+q] = getSelectedOptionText(document.getElementById('g'+q+'_block')); allQuestions.push('Q'+q);}
  for (let q = 51; q <= 60; q++) { let inp = document.getElementById('q'+q+'_input'); answers['Q'+q] = inp ? inp.value.trim() : ''; allQuestions.push('Q'+q);}
  answers['Q61'] = document.getElementById('q61_essay').value.trim();
  document.getElementById("main-form").style.display = "none";
  document.getElementById("responses-area").style.display = "block";
  let right = 0, total = 0;
  let out = `<div class="congrats">Congratulations on completing the exam! <span style="font-size:1.3em;vertical-align:middle;">❤️&nbsp;🇨🇳</span></div>
    <div class="timer-bar" style="font-size:1.08em;color:#284e93;margin-bottom:28px;">Time taken: ${formatTimer(timer)}</div>
    <div class="answers-block"><div class="student-header"><b>Name:</b> ${escapeHtml(name)}</div><h3>Section 1, 2, 3, 4, 5 & 6: Auto-marked</h3>
    <div style="overflow-x:auto"><table class="answer-table"><tr>
      <th>Q#</th><th>Your Answer</th><th>Correct Answer</th><th>✔/✘</th></tr>`;
  for(let i=0;i<allQuestions.length;i++) {
    const qn = allQuestions[i];
    let studentAns = answers[qn] || "";
    let corrAns = answerKey[qn] || "[unavailable]";
    let correct;
    if (qn === "Q61") continue;
    if (qn.replace(/[^\d]/g,"") < 11 || (Number(qn.replace(/[^\d]/g,"")) >= 36 && Number(qn.replace(/[^\d]/g,"")) <= 50)) {
      correct = studentAns === corrAns;
    } else { correct = compareStrings(studentAns,corrAns);}
    if(correct) right++; total++;
    out += `<tr class="${correct ? 'correct' : (studentAns ? 'incorrect' : '')}"><td>${qn.replace("Q","")}</td>
        <td>${escapeHtml(studentAns)}</td><td>${escapeHtml(corrAns)}</td>
      <td style="text-align:center;">${studentAns ? (correct ? '<span class="checkmark">&#10004;</span>' : '<span class="xmark">&#10008;</span>') : ""}</td></tr>`;
  }
  const submissionPayload = {
    submittedAt: new Date().toISOString(),
    name: name,
    timeTaken: formatTimer(timer),
    autoMarkedScore: right,
    autoMarkedTotal: total,
    answers: answers
  };
  const submittedToSheet = await submitToGoogleSheet(submissionPayload);

  out += `<div style="background:${submittedToSheet ? '#eaf8ef' : '#fff8e6'};border:1px solid ${submittedToSheet ? '#8fd19e' : '#e7c86f'};padding:12px 14px;border-radius:8px;margin-bottom:16px;color:#2a3d5b;">
    ${submittedToSheet ? 'Your exam has been submitted to the teacher.' : 'Your exam result is shown below. The teacher submission link has not been set up yet, so please screenshot or copy this page.'}
  </div>`;

  out += `</table>
    <b>Auto-marked sections score: ${right} / ${total}</b></div>
    <h3>Section 7: Manual Marking (Short Essay)</h3>
    <div class="manual-mark">
      <b>Essay prompt:</b> Write a short paragraph (150–200 Chinese characters) on ONE of the topics using at least 8 required grammar points.<br><br>
      <span style="color:#2a3d5b;">Student's Essay:</span>
      <div class="essay-block" style="margin-top:7px;">${escapeHtml(answers["Q61"]||"")}</div>
    </div>
  </div>
  <p><a href="#" onclick="window.location.reload();return false;">Back to exam for another student</a></p>`;
  document.getElementById("responses-area").innerHTML = out;
  return false;
}
window.onload = function(){
  document.querySelectorAll("#main-form input,#main-form textarea,#main-form button").forEach(function(el){
    if (!el.classList.contains("name-input") && !el.classList.contains("submit-btn")) el.disabled = true;
  });
}
</script>
</head>
<body>
  <div id="timer-bar" class="timer-bar"></div>
  <div id="start-area" class="container">
    <h1>Chinese Exam – All Sections</h1>
    <div style="font-size:1.14em;margin-bottom:1.3em;color:#28508a;">
      Enter your full name to begin the exam.<br>
      <input type="text" id="student-name" class="name-input" maxlength="40" required placeholder="Enter your full name" style="margin-top:1em;"><br>
      <button type="button" class="start-btn" onclick="if(document.getElementById('student-name').value.trim()){startExam();}">Start Exam</button>
    </div>
    <em>Once you click "Start Exam", the timer will begin and the exam will unlock.</em>
  </div>
  <div class="container hidden" id="main-form">
    <div class="jump-links">
      <a href="#section1">Audio Comprehension</a>
      <a href="#section2">Rearranging Words</a>
      <a href="#section3">English → Mandarin</a>
      <a href="#section4">Mandarin → English</a>
      <a href="#section5">Grammar</a>
      <a href="#section6">Fix the Errors</a>
      <a href="#section7">Short Essay</a>
    </div>
    <form onsubmit="onSubmitExam(event)">
<!-- ================== SECTION 1 ====================== -->
<div class="section" id="section1">
  <h2>Section 1: Audio Comprehension (Q1–Q10)</h2>
  <div style="color:#555; margin-bottom:18px;">Listen to the audio and select the best answer for each question.</div>
  <div class="question-block" id="audio1_block">
    <div class="audio-block"><b>Audio 1:</b><br>
      <audio controls>
        <source src="https://media.vocaroo.com/mp3/13gEATSurdRo" type="audio/mpeg">Your browser does not support the audio element.
      </audio>
    </div>
  </div>
  <div class="question-block" id="q1_block"><div class="question">Q1. Where did Li You go yesterday?</div>
    <div class="options">
      <button type="button" onclick="selectOption('q1', this)">a. 公园</button>
      <button type="button" onclick="selectOption('q1', this)">b. 中国城</button>
      <button type="button" onclick="selectOption('q1', this)">c. 图书馆</button>
      <button type="button" onclick="selectOption('q1', this)">d. 医院</button>
    </div>
  </div>
  <div class="question-block" id="q2_block"><div class="question">Q2. What dish did Li You NOT order?</div>
    <div class="options">
      <button type="button" onclick="selectOption('q2', this)">a. 糖醋鱼</button>
      <button type="button" onclick="selectOption('q2', this)">b. 酸辣汤</button>
      <button type="button" onclick="selectOption('q2', this)">c. 饺子</button>
      <button type="button" onclick="selectOption('q2', this)">d. 酸辣汤</button>
    </div>
  </div>
  <div class="question-block" id="q3_block"><div class="question">Q3. What was the weather like yesterday afternoon?</div>
    <div class="options">
      <button type="button" onclick="selectOption('q3', this)">a. 下雨了</button>
      <button type="button" onclick="selectOption('q3', this)">b. 下雪了</button>
      <button type="button" onclick="selectOption('q3', this)">c. 晴天</button>
      <button type="button" onclick="selectOption('q3', this)">d. 刮风了</button>
    </div>
  </div>
  <div class="question-block" id="q4_block"><div class="question">Q4. How does Wang Peng suggest getting to the park?</div>
    <div class="options">
      <button type="button" onclick="selectOption('q4', this)">a. 坐公共汽车</button>
      <button type="button" onclick="selectOption('q4', this)">b. 开车</button>
      <button type="button" onclick="selectOption('q4', this)">c. 坐地铁</button>
      <button type="button" onclick="selectOption('q4', this)">d. 走路</button>
    </div>
  </div>
  <div class="question-block" id="audio2_block">
    <div class="audio-block"><b>Audio 2:</b><br>
      <audio controls>
        <source src="https://media.vocaroo.com/mp3/1ezvPPYDMQkh" type="audio/mpeg">Your browser does not support the audio element.
      </audio>
    </div>
  </div>
  <div class="question-block" id="q5_block"><div class="question">Q5. What is Wang Peng doing tomorrow?</div>
    <div class="options">
      <button type="button" onclick="selectOption('q5', this)">a. 去参加晚会</button>
      <button type="button" onclick="selectOption('q5', this)">b. 开生日晚会</button>
      <button type="button" onclick="selectOption('q5', this)">c. 去看医生</button>
      <button type="button" onclick="selectOption('q5', this)">d. 去图书馆</button>
    </div>
  </div>
<!-- Q6 -->
<div class="question-block" id="q6_block"><div class="question">Q6. What will they do after eating?</div>
  <div class="options">
    <button type="button" onclick="selectOption('q6', this)">a. 看电视</button>
    <button type="button" onclick="selectOption('q6', this)">b. 唱歌跳舞</button>
    <button type="button" onclick="selectOption('q6', this)">c. 玩游戏</button>
    <button type="button" onclick="selectOption('q6', this)">d. 打开礼物</button>
  </div>
</div>
<!-- Q7 -->
<div class="question-block" id="q7_block"><div class="question">Q7. What does Wang Peng want Li You to bring?</div>
  <div class="options">
    <button type="button" onclick="selectOption('q7', this)">a. 礼物</button>
    <button type="button" onclick="selectOption('q7', this)">b. 饮料或者水果</button>
    <button type="button" onclick="selectOption('q7', this)">c. 蛋糕</button>
    <button type="button" onclick="selectOption('q7', this)">d. 花</button>
  </div>
</div>
<!-- Q8 -->
<div class="question-block" id="q8_block"><div class="question">Q8. Where does Wang Peng live?</div>
  <div class="options">
    <button type="button" onclick="selectOption('q8', this)">a. 大学的南边</button>
    <button type="button" onclick="selectOption('q8', this)">b. 大学的东边</button>
    <button type="button" onclick="selectOption('q8', this)">c. 大学的西边</button>
    <button type="button" onclick="selectOption('q8', this)">d. 大学的北边</button>
  </div>
</div>
<!-- Q9 -->
<div class="question-block" id="q9_block"><div class="question">Q9. What is wrong with Wang Hong?</div>
  <div class="options">
    <button type="button" onclick="selectOption('q9', this)">a. 她感冒了</button>
    <button type="button" onclick="selectOption('q9', this)">b. 她肚子疼</button>
    <button type="button" onclick="selectOption('q9', this)">c. 她的眼睛又红又痒</button>
    <button type="button" onclick="selectOption('q9', this)">d. 她发烧了</button>
  </div>
</div>
<!-- Q10 -->
<div class="question-block" id="q10_block"><div class="question">Q10. How many times a day should Wang Hong take her medicine?</div>
  <div class="options">
    <button type="button" onclick="selectOption('q10', this)">a. 一天一次</button>
    <button type="button" onclick="selectOption('q10', this)">b. 一天两次</button>
    <button type="button" onclick="selectOption('q10', this)">c. 一天三次</button>
    <button type="button" onclick="selectOption('q10', this)">d. 一天四次</button>
  </div>
</div>
</div>
<!-- SECTION 2: Rearranging Words -->
<div class="section" id="section2">
  <h2>Section 2: Rearranging Words (Q11–Q20)</h2>
  <div style="color:#555; margin-bottom:18px;">Rearrange each group of words to form the correct sentence.</div>
  <!-- Q11-Q20 -->
  <div class="question-block"><div class="question">Q11. 一 / 我 / 回家 / 就 / 做功课</div><input id="q11_input" type="text" class="text-input" placeholder="Type the correct sentence here"></div>
  <div class="question-block"><div class="question">Q12. 中国菜 / 又 / 好吃 / 又 / 便宜</div><input id="q12_input" type="text" class="text-input" placeholder="Type the correct sentence here"></div>
  <div class="question-block"><div class="question">Q13. 悉尼 / 没有 / 北京 / 那么 / 冷</div><input id="q13_input" type="text" class="text-input" placeholder="Type the correct sentence here"></div>
  <div class="question-block"><div class="question">Q14. 我 / 中文 / 学 / 了 / 两年 / 了</div><input id="q14_input" type="text" class="text-input" placeholder="Type the correct sentence here"></div>
  <div class="question-block"><div class="question">Q15. 图书馆 / 离 / 学生活动中心 / 很近</div><input id="q15_input" type="text" class="text-input" placeholder="Type the correct sentence here"></div>
  <div class="question-block"><div class="question">Q16. 到 / 医院 / 去 / 他 / 看病</div><input id="q16_input" type="text" class="text-input" placeholder="Type the correct sentence here"></div>
  <div class="question-block"><div class="question">Q17. 我 / 去过 / 中国城 / 三次</div><input id="q17_input" type="text" class="text-input" placeholder="Type the correct sentence here"></div>
  <div class="question-block"><div class="question">Q18. 天气 / 越来越 / 冷 / 了</div><input id="q18_input" type="text" class="text-input" placeholder="Type the correct sentence here"></div>
  <div class="question-block"><div class="question">Q19. 请 / 把 / 这些药 / 吃完</div><input id="q19_input" type="text" class="text-input" placeholder="Type the correct sentence here"></div>
  <div class="question-block"><div class="question">Q20. 他 / 又 / 聪明 / 又 / 用功</div><input id="q20_input" type="text" class="text-input" placeholder="Type the correct sentence here"></div>
</div>
<!-- SECTION 3: English to Mandarin -->
<div class="section" id="section3">
  <h2>Section 3: English to Mandarin Translation (Q21–Q30)</h2>
  <div style="color:#555; margin-bottom:18px;">Translate the following English sentences into Mandarin.</div>
  <div class="question-block"><div class="question">Q21. Although today's weather is cold, it is not raining. (adjective 是 adjective, 但是……)</div><input id="q21_input" type="text" class="text-input" placeholder="Write the Mandarin sentence here"></div>
  <div class="question-block"><div class="question">Q22. Li You thinks that skating is not as interesting as playing basketball. (comparative using 没有)</div><input id="q22_input" type="text" class="text-input" placeholder="Write the Mandarin sentence here"></div>
  <div class="question-block"><div class="question">Q23. Sweet and sour fish is a bit sweet and a bit sour, and it is extremely tasty. (adjective reduplication)</div><input id="q23_input" type="text" class="text-input" placeholder="Write the Mandarin sentence here"></div>
  <div class="question-block"><div class="question">Q24. I will go to the computer centre immediately after I finish my test. (VC construction)</div><input id="q24_input" type="text" class="text-input" placeholder="Write the Mandarin sentence here"></div>
  <div class="question-block"><div class="question">Q25. I like to learn Chinese because it is a bit easier than Japanese. (一点儿)</div><input id="q25_input" type="text" class="text-input" placeholder="Write the Mandarin sentence here"></div>
  <div class="question-block"><div class="question">Q26. I am so busy this week. I have no time at all. (一…也/都 没 + verb)</div><input id="q26_input" type="text" class="text-input" placeholder="Write the Mandarin sentence here"></div>
  <div class="question-block"><div class="question">Q27. As soon as you turn left, the library is just in between the sports field and the bookshop. (一….就…..)</div><input id="q27_input" type="text" class="text-input" placeholder="Write the Mandarin sentence here"></div>
  <div class="question-block"><div class="question">Q28. She is cutting cake. (action in progress with 呢)</div><input id="q28_input" type="text" class="text-input" placeholder="Write the Mandarin sentence here"></div>
  <div class="question-block"><div class="question">Q29. I have been studying Chinese for two years. (time duration)</div><input id="q29_input" type="text" class="text-input" placeholder="Write the Mandarin sentence here"></div>
  <div class="question-block"><div class="question">Q30. Put the book on the table. (把 construction)</div><input id="q30_input" type="text" class="text-input" placeholder="Write the Mandarin sentence here"></div>
</div>
<!-- SECTION 4: Mandarin to English -->
<div class="section" id="section4">
  <h2>Section 4: Mandarin to English Translation (Q31–Q35)</h2>
  <div style="color:#555; margin-bottom:18px;">Translate the following Mandarin sentences into English.</div>
  <div class="question-block"><div class="question">Q31. 他每天吃三次药，一次两片。</div>
    <input id="q31_input" type="text" class="text-input" placeholder="Write your English translation here"></div>
  <div class="question-block"><div class="question">Q32. 天气越来越冷了。</div>
    <input id="q32_input" type="text" class="text-input" placeholder="Write your English translation here"></div>
  <div class="question-block"><div class="question">Q33. 我对花生过敏。</div>
    <input id="q33_input" type="text" class="text-input" placeholder="Write your English translation here"></div>
  <div class="question-block"><div class="question">Q34. 你是在哪儿学的中文？</div>
    <input id="q34_input" type="text" class="text-input" placeholder="Write your English translation here"></div>
  <div class="question-block"><div class="question">Q35. 图书馆离运动场很近。</div>
    <input id="q35_input" type="text" class="text-input" placeholder="Write your English translation here"></div>
</div>
<!-- SECTION 5: Grammar MCQs -->
<div class="section" id="section5">
  <h2>Section 5: Grammar (Q36–Q50)</h2>
  <div style="color:#555; margin-bottom:18px;">Choose the most appropriate answer for each question.</div>
  <!-- Q36-Q50: See original prompt for full blocks (here's example for Q36) -->
  <div class="question-block" id="g36_block"><div class="question">Q36. Which sentence correctly uses 把?</div>
    <div class="options">
      <button type="button" onclick="selectOption('g36', this)">a. 我把书在桌子上放</button>
      <button type="button" onclick="selectOption('g36', this)">b. 我把书放在桌子上</button>
      <button type="button" onclick="selectOption('g36', this)">c. 我放书在桌子上把</button>
      <button type="button" onclick="selectOption('g36', this)">d. 书我把放在桌子上</button>
    </div>
  </div><!-- Q37 -->
<div class="question-block" id="g37_block">
  <div class="question">Q37. Which sentence means "I have been to China"?</div>
  <div class="options">
    <button type="button" onclick="selectOption('g37', this)">a. 我去中国了</button>
    <button type="button" onclick="selectOption('g37', this)">b. 我去过中国</button>
    <button type="button" onclick="selectOption('g37', this)">c. 我要去中国</button>
    <button type="button" onclick="selectOption('g37', this)">d. 我在中国</button>
  </div>
</div>
<!-- Q38 -->
<div class="question-block" id="g38_block">
  <div class="question">Q38. Which sentence correctly uses 一…就…?</div>
  <div class="options">
    <button type="button" onclick="selectOption('g38', this)">a. 我一吃饭就睡觉</button>
    <button type="button" onclick="selectOption('g38', this)">b. 一我吃饭就睡觉</button>
    <button type="button" onclick="selectOption('g38', this)">c. 我吃饭一就睡觉</button>
    <button type="button" onclick="selectOption('g38', this)">d. 我吃饭就一睡觉</button>
  </div>
</div>
<!-- Q39 -->
<div class="question-block" id="g39_block">
  <div class="question">Q39. Which sentence means "He is taller than me"?</div>
  <div class="options">
    <button type="button" onclick="selectOption('g39', this)">a. 他比我高</button>
    <button type="button" onclick="selectOption('g39', this)">b. 他比我矮</button>
    <button type="button" onclick="selectOption('g39', this)">c. 我没有他高</button>
    <button type="button" onclick="selectOption('g39', this)">d. 他比我高一点儿</button>
  </div>
</div>
<!-- Q40 -->
<div class="question-block" id="g40_block">
  <div class="question">Q40. Which sentence uses 没有 correctly for comparison?</div>
  <div class="options">
    <button type="button" onclick="selectOption('g40', this)">a. 我没有他那么高</button>
    <button type="button" onclick="selectOption('g40', this)">b. 我没有他高那么</button>
    <button type="button" onclick="selectOption('g40', this)">c. 我没有那么他高</button>
    <button type="button" onclick="selectOption('g40', this)">d. 我那么没有他高</button>
  </div>
</div>
<!-- Q41 -->
<div class="question-block" id="g41_block">
  <div class="question">Q41. Which sentence means "It's not raining anymore"?</div>
  <div class="options">
    <button type="button" onclick="selectOption('g41', this)">a. 不下雪了</button>
    <button type="button" onclick="selectOption('g41', this)">b. 不下雨了</button>
    <button type="button" onclick="selectOption('g41', this)">c. 没下雨了</button>
    <button type="button" onclick="selectOption('g41', this)">d. 不雨下了</button>
  </div>
</div>
<!-- Q42 -->
<div class="question-block" id="g42_block">
  <div class="question">Q42. Which sentence correctly uses 不但…而且?</div>
  <div class="options">
    <button type="button" onclick="selectOption('g42', this)">a. 他不但很聪明，而且很帅</button>
    <button type="button" onclick="selectOption('g42', this)">b. 他不但很聪明，而且很帅了</button>
    <button type="button" onclick="selectOption('g42', this)">c. 他不但很聪明很帅</button>
    <button type="button" onclick="selectOption('g42', this)">d. 不但他很聪明，而且很帅</button>
  </div>
</div>
<!-- Q43 -->
<div class="question-block" id="g43_block">
  <div class="question">Q43. Which sentence means "I have no time at all"?</div>
  <div class="options">
    <button type="button" onclick="selectOption('g43', this)">a. 我有一点时间</button>
    <button type="button" onclick="selectOption('g43', this)">b. 我一点儿时间都没有</button>
    <button type="button" onclick="selectOption('g43', this)">c. 我没有一点儿时间</button>
    <button type="button" onclick="selectOption('g43', this)">d. 我时间都没有一点儿</button>
  </div>
</div>
<!-- Q44 -->
<div class="question-block" id="g44_block">
  <div class="question">Q44. Which sentence correctly uses 离?</div>
  <div class="options">
    <button type="button" onclick="selectOption('g44', this)">a. 我家离学校很近</button>
    <button type="button" onclick="selectOption('g44', this)">b. 我家离学校很近吗</button>
    <button type="button" onclick="selectOption('g44', this)">c. 离我家学校很近</button>
    <button type="button" onclick="selectOption('g44', this)">d. 学校离我家很近吗</button>
  </div>
</div>
<!-- Q45 -->
<div class="question-block" id="g45_block">
  <div class="question">Q45. Which sentence means "The weather is getting warmer and warmer"?</div>
  <div class="options">
    <button type="button" onclick="selectOption('g45', this)">a. 天气越来越暖和</button>
    <button type="button" onclick="selectOption('g45', this)">b. 天气越来越冷</button>
    <button type="button" onclick="selectOption('g45', this)">c. 天气暖和越来越</button>
    <button type="button" onclick="selectOption('g45', this)">d. 越来越天气暖和</button>
  </div>
</div>
<!-- Q46 -->
<div class="question-block" id="g46_block">
  <div class="question">Q46. Which sentence correctly uses 对…过敏?</div>
  <div class="options">
    <button type="button" onclick="selectOption('g46', this)">a. 我对花生对过敏</button>
    <button type="button" onclick="selectOption('g46', this)">b. 我对花生过敏</button>
    <button type="button" onclick="selectOption('g46', this)">c. 我过敏对花生</button>
    <button type="button" onclick="selectOption('g46', this)">d. 我花生过敏对</button>
  </div>
</div>
<!-- Q47 -->
<div class="question-block" id="g47_block">
  <div class="question">Q47. Which sentence means "I have studied for three years"?</div>
  <div class="options">
    <button type="button" onclick="selectOption('g47', this)">a. 我学了三年了</button>
    <button type="button" onclick="selectOption('g47', this)">b. 我学三年了</button>
    <button type="button" onclick="selectOption('g47', this)">c. 我学了三年</button>
    <button type="button" onclick="selectOption('g47', this)">d. 三年我学了</button>
  </div>
</div>
<!-- Q48 -->
<div class="question-block" id="g48_block">
  <div class="question">Q48. Which sentence correctly uses 再说?</div>
  <div class="options">
    <button type="button" onclick="selectOption('g48', this)">a. 我没有时间，再说也没有钱</button>
    <button type="button" onclick="selectOption('g48', this)">b. 我没有时间再说也没有钱</button>
    <button type="button" onclick="selectOption('g48', this)">c. 我没有时间，也再说没有钱</button>
    <button type="button" onclick="selectOption('g48', this)">d. 再说我没有时间，也没有钱</button>
  </div>
</div>
<!-- Q49 -->
<div class="question-block" id="g49_block">
  <div class="question">Q49. Which sentence means "Please speak a little more slowly"?</div>
  <div class="options">
    <button type="button" onclick="selectOption('g49', this)">a. 请说得慢一点儿</button>
    <button type="button" onclick="selectOption('g49', this)">b. 请说慢一点儿得</button>
    <button type="button" onclick="selectOption('g49', this)">c. 请慢一点儿说</button>
    <button type="button" onclick="selectOption('g49', this)">d. 请说得一点儿慢</button>
  </div>
</div>
<!-- Q50 -->
<div class="question-block" id="g50_block">
  <div class="question">Q50. Which sentence correctly uses 正在…呢?</div>
  <div class="options">
    <button type="button" onclick="selectOption('g50', this)">a. 他正在吃饭呢</button>
    <button type="button" onclick="selectOption('g50', this)">b. 他正在吃饭了呢</button>
    <button type="button" onclick="selectOption('g50', this)">c. 他正在呢吃饭</button>
    <button type="button" onclick="selectOption('g50', this)">d. 他吃饭正在呢</button>
  </div>
</div>
</div>
<!-- ================== SECTION 6: Fix the Errors (Q51-Q60) =================== -->
<div class="section" id="section6">
  <h2>Section 6: Fix the Errors (Q51–Q60)</h2>
  <div style="color:#555; margin-bottom:18px;">Rewrite each sentence correctly.</div>
  <div class="question-block"><div class="question">Q51. 你给我五十块，找你二十块零五分。</div><input id="q51_input" type="text" class="text-input" placeholder="Rewrite the corrected sentence"></div>
  <div class="question-block"><div class="question">Q52. 今天不但下雨，而且明天也下雨。</div><input id="q52_input" type="text" class="text-input" placeholder="Rewrite the corrected sentence"></div>
  <div class="question-block"><div class="question">Q53. 我的同学们去年都去了中国，可是我不去。</div><input id="q53_input" type="text" class="text-input" placeholder="Rewrite the corrected sentence"></div>
  <div class="question-block"><div class="question">Q54. 他去过图书馆，所以今天不能跟我们去饭馆吃饭。</div><input id="q54_input" type="text" class="text-input" placeholder="Rewrite the corrected sentence"></div>
  <div class="question-block"><div class="question">Q55. 那个地方比学校有点儿远，我们坐车去吧。</div><input id="q55_input" type="text" class="text-input" placeholder="Rewrite the corrected sentence"></div>
  <div class="question-block"><div class="question">Q56. 昨天我见面了他。</div><input id="q56_input" type="text" class="text-input" placeholder="Rewrite the corrected sentence"></div>
  <div class="question-block"><div class="question">Q57. 我不舒服，因为我头疼死了。</div><input id="q57_input" type="text" class="text-input" placeholder="Rewrite the corrected sentence"></div>
  <div class="question-block"><div class="question">Q58. 他对海鲜过敏了。</div><input id="q58_input" type="text" class="text-input" placeholder="Rewrite the corrected sentence"></div>
  <div class="question-block"><div class="question">Q59. 我把作业没做完。</div><input id="q59_input" type="text" class="text-input" placeholder="Rewrite the corrected sentence"></div>
  <div class="question-block"><div class="question">Q60. 他正在唱歌在客厅。</div><input id="q60_input" type="text" class="text-input" placeholder="Rewrite the corrected sentence"></div>
</div>

<!-- ================== SECTION 7: Short Essay =================== -->
<div class="section" id="section7">
  <h2>Section 7: Short Essay/Narrative (Q61)</h2>
  <div style="color:#555;">
    Write a short paragraph (150–200 Chinese characters) about <b>ONE</b> of the following topics using at least <b>8</b> of the listed grammar patterns.<br>
    <b>Topics (choose ONE):</b>
    <ol>
      <li>Compare Australian and Chinese cultural differences (weather, dining out, directions, birthday party, or seeing a doctor)</li>
      <li>Describe a time you or your friend got sick (symptoms, seeing the doctor, treatment)</li>
      <li>Describe your favorite season and why (weather, activities, food)</li>
    </ol>
    <b>Grammar patterns to use (at least 8):</b><br>
    比 (comparison), 没有 (comparison), 不但…而且, 一…就…, 过 (past experience), 把 (disposal construction), 对…过敏, 越来越, 多/少 + verb, Verb + complement (e.g., 吃完, 看懂, 找到), 到 + place + 去 + action, 离 (distance from), 再说 (moreover), 了 (change of state), Adjective reduplication (e.g., 甜甜的)
  </div>
  <textarea class="text-area" id="q61_essay" placeholder="Type your essay here in Chinese (150–200 characters)"></textarea>
</div>

<button type="submit" class="submit-btn">Submit Exam</button>
</form>
</div>
<div id="responses-area"></div>
</body>
</html>
