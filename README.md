# Western-Literature-and-Culture
     <!DOCTYPE html>
<html lang="zh-TW">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>西洋文學與文化評分系統 (雲端連動版)</title>
  <style>
    *, *::before, *::after {
      box-sizing: border-box;
    }

    :root {
      --primary: #3498db;
      --success: #2ecc71;
      --warning: #f1c40f;
      --danger: #e74c3c;
      --purple: #8e44ad;
      --orange: #e67e22;
      --teal: #1abc9c;
      --dark: #1e293b;
      --light-bg: #f8fafc;
      --border: #cbd5e1;
    }

    body {
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
      background-color: #f0f4f8;
      color: var(--dark);
      margin: 0;
      padding: 30px 15px;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    .inapp-warning {
      display: none;
      background-color: #fff3cd;
      color: #856404;
      border: 1px solid #ffeeba;
      padding: 12px;
      border-radius: 8px;
      margin-bottom: 15px;
      width: 100%;
      max-width: 700px;
      font-size: 14px;
      line-height: 1.5;
      text-align: center;
    }

    .instructor-card {
      background: white;
      padding: 30px 25px;
      border-radius: 20px;
      box-shadow: 0 15px 35px rgba(0,0,0,0.08);
      width: 100%;
      max-width: 700px;
      position: relative;
    }

    .header-container {
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;
      margin-bottom: 20px;
    }

    h1 {
      text-align: center;
      color: var(--dark);
      font-size: 24px;
      margin: 0;
      font-weight: 700;
    }

    .btn-teacher-lock {
      position: absolute;
      right: 0;
      background: transparent;
      border: 1px solid #cbd5e1;
      color: #64748b;
      padding: 4px 10px;
      font-size: 12px;
      border-radius: 20px;
      cursor: pointer;
      transition: all 0.2s;
    }

    .btn-teacher-lock:hover {
      background: #f1f5f9;
      color: var(--dark);
    }

    .teacher-panel {
      display: none; 
      background: #eef6fb;
      border: 1px solid #bee3f8;
      border-radius: 12px;
      padding: 15px;
      margin-bottom: 20px;
      animation: fadeIn 0.3s ease-in-out;
    }

    .panel-title {
      font-size: 14px;
      font-weight: 700;
      color: var(--dark);
      margin-bottom: 10px;
      display: flex;
      align-items: center;
      gap: 5px;
    }

    .teacher-actions {
      display: flex;
      gap: 10px;
      flex-wrap: wrap;
      align-items: center;
    }

    .btn-file-label {
      background-color: var(--teal);
      color: white;
      padding: 8px 14px;
      border-radius: 6px;
      font-size: 13px;
      font-weight: 600;
      cursor: pointer;
      display: inline-block;
      transition: background 0.2s;
    }

    .btn-file-label:hover {
      background-color: #16a085;
    }

    .btn-random {
      background-color: var(--orange);
      color: white;
      padding: 8px 14px;
      border-radius: 6px;
      font-size: 13px;
      font-weight: 600;
      border: none;
      cursor: pointer;
      transition: background 0.2s;
    }

    .btn-random:hover {
      background-color: #d35400;
    }

    .bank-status {
      font-size: 12px;
      color: #64748b;
      margin-top: 8px;
    }

    .student-info-form {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 10px;
      background: var(--light-bg);
      padding: 15px;
      border-radius: 12px;
      border: 1px solid var(--border);
      margin-bottom: 20px;
      width: 100%;
    }

    .form-group {
      display: flex;
      flex-direction: column;
      text-align: left;
      width: 100%;
    }

    .form-group label {
      font-size: 13px;
      font-weight: 600;
      margin-bottom: 4px;
      color: var(--dark);
      white-space: nowrap;
    }

    .form-group label::after {
      content: " *";
      color: var(--danger);
    }

    .form-group input {
      width: 100%;
      padding: 8px 12px;
      font-size: 14px;
      border: 1px solid var(--border);
      border-radius: 6px;
      outline: none;
    }

    .form-group input:focus {
      border-color: var(--primary);
    }

    /* 句子呈現區 (精美字型與自然間距) */
    .sentence-box {
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
      font-size: 26px;
      font-weight: 600;
      line-height: 1.8;
      padding: 24px 28px;
      background: #ffffff;
      border-radius: 16px;
      border: 2px solid #cbd5e1;
      margin-bottom: 20px;
      text-align: left;
      word-break: break-word;
      letter-spacing: 0.01em;
      box-shadow: inset 0 2px 4px rgba(0,0,0,0.02);
    }

    /* 單字標示與縮補優化 */
    .w-unit {
      display: inline-block;
      margin: 2px 1px;
      padding: 2px 8px;
      border-radius: 6px;
      font-weight: 600;
      transition: all 0.2s ease-in-out;
    }

    .w-unit.pending {
      color: #334155;
      background: transparent;
      padding: 2px 0px;
      margin: 0;
    }

    .w-unit.correct {
      color: #ffffff;
      background-color: var(--success);
    }

    .w-unit.wrong {
      color: #ffffff;
      background-color: var(--danger);
    }

    .w-unit.missing {
      color: #ffffff;
      background-color: var(--warning);
    }

    .legend {
      display: flex;
      justify-content: center;
      gap: 12px;
      margin-bottom: 20px;
      font-size: 13px;
      flex-wrap: wrap;
    }

    .legend-item { display: flex; align-items: center; gap: 5px; }
    .dot { width: 10px; height: 10px; border-radius: 3px; }

    .control-panel {
      display: flex;
      gap: 10px;
      justify-content: center;
      margin-bottom: 20px;
      flex-wrap: wrap;
    }

    button {
      padding: 10px 18px;
      font-size: 14px;
      font-weight: 600;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: transform 0.1s, opacity 0.2s;
    }

    button:active { transform: scale(0.98); }
    .btn-audio { background: #e2e8f0; color: var(--dark); }
    .btn-mic { background: var(--primary); color: white; }
    .btn-next { background: var(--purple); color: white; }
    
    .btn-mic.recording {
      background: var(--danger);
      animation: pulse 1s infinite alternate;
    }

    button:disabled {
      background-color: #cbd5e1;
      color: #94a3b8;
      cursor: not-allowed;
    }

    .score-board {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 10px;
      background: var(--light-bg);
      padding: 15px;
      border-radius: 12px;
      border: 1px solid #e2e8f0;
      text-align: center;
    }

    .score-card { padding: 5px; }
    .score-num { font-size: 26px; font-weight: 800; margin-top: 4px; }
    .score-num.count { color: var(--purple); }
    .score-num.complete { color: var(--success); }
    .score-num.total { color: var(--primary); }

    .feedback-msg {
      grid-column: span 3;
      margin-top: 8px;
      font-weight: bold;
      color: #475569;
      border-top: 1px dashed #cbd5e1;
      padding-top: 12px;
      line-height: 1.5;
      font-size: 14px;
    }

    @keyframes pulse { from { opacity: 1; } to { opacity: 0.7; } }
    @keyframes fadeIn { from { opacity: 0; transform: translateY(-10px); } to { opacity: 1; transform: translateY(0); } }

    @media (max-width: 500px) {
      .sentence-box { font-size: 22px; padding: 18px 20px; }
      .student-info-form { grid-template-columns: 1fr; }
      .score-board { grid-template-columns: 1fr; }
      .feedback-msg { grid-column: span 1; }
    }
  </style>
</head>
<body>

<div class="inapp-warning" id="inAppWarning">
  ⚠️ 偵測到您正在使用 App 內建瀏覽器。<br>
  請點擊右上角 **「⋮」** 或 **「分享」** 按鈕，選擇 **「在 Chrome / Safari 中開啟」** 以存取麥克風。
</div>

<div class="instructor-card">
  <div class="header-container">
    <h1>學生口說發音評分系統</h1>
    <button class="btn-teacher-lock" id="btnTeacherLock">🔒 教師解鎖</button>
  </div>

  <!-- 老師題庫設定區 (授權驗證後顯示) -->
  <div class="teacher-panel" id="teacherPanel">
    <div class="panel-title">📚 題庫切換與自訂（教師功能）</div>
    <div class="teacher-actions">
      <button class="btn-random" id="btnRandom5">🎲 隨機載入 5 句日常英語</button>
      <label class="btn-file-label" for="fileInput">📁 上傳 text.txt 自訂題庫</label>
      <input type="file" id="fileInput" accept=".txt" style="display: none;">
    </div>
    <div class="bank-status" id="bankStatus">目前題庫：預設格言題庫（共 6 條）</div>
  </div>

  <!-- 1. 學生資訊填寫區 -->
  <div class="student-info-form">
    <div class="form-group">教師解
      <label for="studentClass">班級</label>
      <input type="text" id="studentClass" placeholder="例如: 英A1" required>
    </div>
    <div class="form-group">
      <label for="studentId">學號</label>
      <input type="text" id="studentId" placeholder="例如: 1090123" required>
    </div>
    <div class="form-group">
      <label for="studentName">姓名</label>
      <input type="text" id="studentName" placeholder="例如: 王小明" required>
    </div>
  </div>

  <!-- 2. 圖例說明區 -->
  <div class="legend">
    <div class="legend-item"><span class="dot" style="background: #7f8c8d"></span> 未練習</div>
    <div class="legend-item"><span class="dot" style="background: var(--success)"></span> 發音正確</div>
    <div class="legend-item"><span class="dot" style="background: var(--danger)"></span> 發音錯誤</div>
    <div class="legend-item"><span class="dot" style="background: var(--warning)"></span> 漏唸單字</div>
  </div>

  <!-- 3. 目標句子顯示區 -->
  <div class="sentence-box" id="sentenceBox"></div>

  <!-- 4. 控制按鈕區 -->
  <div class="control-panel">
    <button class="btn-audio" id="btnAudio">🔊 聽示範(美音)</button>
    <button class="btn-mic" id="btnMic">🎙️ 開始錄音演練</button>
    <button class="btn-next" id="btnNext">🔄 換下一題</button>
  </div>

  <!-- 5. 評分與反饋面板 -->
  <div class="score-board">
    <div class="score-card">
      <div>已嘗試次數</div>
      <div class="score-num count" id="attemptCountDisplay">0 次</div>
    </div>
    <div class="score-card">
      <div>句子完整度</div>
      <div class="score-num complete" id="completionScore">0%</div>
    </div>
    <div class="score-card">
      <div>發音精準度</div>
      <div class="score-num total" id="accuracyScore">0%</div>
    </div>
    <div class="feedback-msg" id="feedbackMsg">請填寫上方學生資訊，再開始練習。</div>
  </div>
</div>

<script>
// 授權教師 Email
const AUTHORIZED_TEACHER_EMAIL = "audreyshih32@gm.chihlee.edu.tw";

// 偵測內建瀏覽器 (LINE, Messenger, Teams 等)
const ua = navigator.userAgent || navigator.vendor || window.opera;
const isInApp = (ua.indexOf("Line") > -1) || (ua.indexOf("FBAN") > -1) || (ua.indexOf("FBAV") > -1) || (ua.indexOf("Instagram") > -1) || (ua.indexOf("Teams") > -1);
if (isInApp) {
  document.getElementById('inAppWarning').style.display = 'block';
}

const GAS_URL = "https://script.google.com/macros/s/AKfycbxl86DfQJxa3rrIGX9fEFTz5sW-MYeZrH8Kvb1V5A8pyijeQjIVntKnfHCK8Na389O1/exec";

// 常用英語資料庫
const dailyEnglishPool = [
  "How's it going with you today?",
  "Could you give me a quick hand with this?",
  "Sorry, I didn't quite catch what you said.",
  "Let's grab a cup of coffee sometime this week.",
  "Do you happen to know where the restroom is?",
  "That sounds like a wonderful idea!",
  "I'll get back to you as soon as possible.",
  "What do you feel like eating for dinner tonight?",
  "Take your time, there is no rush at all.",
  "Thanks a lot for taking the time to help me."
];

// 預設題庫
let sentenceBank = [
  "I hope this company offers me a job because I really want to work there.",
  "I filled out the job application, and now I'm waiting to hear back from the company.",
  "Looking for a job can be difficult, especially for people who are new to work.",
  "application.",
  "professional.",
  "career."
];

let currentSentenceIndex = 0;
let targetSentence = sentenceBank[currentSentenceIndex];
let targetWords = [];
let displayWords = [];
let attemptCount = 0;

const studentClass = document.getElementById('studentClass');
const studentId = document.getElementById('studentId');
const studentName = document.getElementById('studentName');
const sentenceBox = document.getElementById('sentenceBox');
const btnAudio = document.getElementById('btnAudio');
const btnMic = document.getElementById('btnMic');
const btnNext = document.getElementById('btnNext');
const btnTeacherLock = document.getElementById('btnTeacherLock');
const teacherPanel = document.getElementById('teacherPanel');
const btnRandom5 = document.getElementById('btnRandom5');
const fileInput = document.getElementById('fileInput');
const bankStatus = document.getElementById('bankStatus');
const attemptCountDisplay = document.getElementById('attemptCountDisplay');
const completionScore = document.getElementById('completionScore');
const accuracyScore = document.getElementById('accuracyScore');
const feedbackMsg = document.getElementById('feedbackMsg');

// 檢查解鎖狀態
if (localStorage.getItem('teacherUnlocked') === 'true') {
  teacherPanel.style.display = 'block';
  btnTeacherLock.innerText = "🔓 教師已解鎖";
}

// 教師權限驗證事件
btnTeacherLock.addEventListener('click', () => {
  if (teacherPanel.style.display === 'block') {
    if (confirm("是否要鎖定並隱藏教師功能區？")) {
      teacherPanel.style.display = 'none';
      btnTeacherLock.innerText = "🔒 教師解鎖";
      localStorage.removeItem('teacherUnlocked');
    }
    return;
  }

  const inputEmail = prompt("請輸入授權教師 Email 以解鎖自訂題庫功能：");
  if (inputEmail && inputEmail.trim().toLowerCase() === AUTHORIZED_TEACHER_EMAIL.toLowerCase()) {
    alert("驗證成功！已解鎖教師功能區。");
    teacherPanel.style.display = 'block';
    btnTeacherLock.innerText = "🔓 教師已解鎖";
    localStorage.setItem('teacherUnlocked', 'true');
  } else if (inputEmail !== null) {
    alert("Email 驗證失敗，無權限存取教師功能！");
  }
});

function initSentence(sentenceText) {
  targetSentence = sentenceText;
  targetWords = targetSentence.toLowerCase().match(/\b[\w'-]+\b/g) || [];
  displayWords = targetSentence.split(/(\s+)/);

  let wordCounter = 0;
  sentenceBox.innerHTML = displayWords.map(chunk => {
    if (/\b[\w'-]+\b/.test(chunk)) {
      const html = `<span class="w-unit pending" id="w-${wordCounter}" data-word="${chunk.toLowerCase().replace(/[^\w'-]/g, '')}">${chunk}</span>`;
      wordCounter++;
      return html;
    }
    return chunk;
  }).join('');
}

function resetScoresAndLoadFirst() {
  currentSentenceIndex = 0;
  initSentence(sentenceBank[0]);
  completionScore.innerText = "0%";
  accuracyScore.innerText = "0%";
  attemptCount = 0;
  attemptCountDisplay.innerText = "0次";
  if (checkFormValidity()) {
    feedbackMsg.innerText = `已成功載入新題庫（共 ${sentenceBank.length} 題），請點擊錄音開始練習。`;
  }
}

initSentence(targetSentence);

// 隨機增加 5 個日常生活常用英語句子
btnRandom5.addEventListener('click', () => {
  const shuffled = [...dailyEnglishPool].sort(() => 0.5 - Math.random());
  sentenceBank = shuffled.slice(0, 5);
  bankStatus.innerText = `目前題庫：隨機日常生活英語（共 5 條）`;
  resetScoresAndLoadFirst();
});

// 上傳 text.txt 檔自訂題庫
fileInput.addEventListener('change', (e) => {
  const file = e.target.files[0];
  if (!file) return;

  const reader = new FileReader();
  reader.onload = (event) => {
    const text = event.target.result;
    const lines = text.split(/\r?\n/).map(line => line.trim().replace(/^"|"$/g, '')).filter(line => line.length > 0);
    
    if (lines.length > 0) {
      sentenceBank = lines;
      bankStatus.innerText = `目前題庫：自訂檔案 ${file.name}（共 ${lines.length} 條）`;
      resetScoresAndLoadFirst();
    } else {
      alert("上傳的文字檔內沒有有效英文句子！");
    }
  };
  reader.readAsText(file, 'UTF-8');
});

btnNext.addEventListener('click', () => {
  currentSentenceIndex = (currentSentenceIndex + 1) % sentenceBank.length;
  initSentence(sentenceBank[currentSentenceIndex]);
  completionScore.innerText = "0%";
  accuracyScore.innerText = "0%";
  if (checkFormValidity()) {
    feedbackMsg.innerText = `已切換至第 ${currentSentenceIndex + 1} / ${sentenceBank.length} 題，點擊錄音按鈕開始練習。`;
  }
});

function checkFormValidity() {
  if (studentClass.value.trim() !== "" && studentId.value.trim() !== "" && studentName.value.trim() !== "") {
    btnMic.disabled = false;
    if (feedbackMsg.innerText.includes("請填寫上方學生資訊")) {
      feedbackMsg.innerText = "基本資料已填寫，點擊按鈕開始錄音。";
    }
    return true;
  } else {
    btnMic.disabled = true;
    feedbackMsg.innerText = "請填寫上方學生資訊，再開始練習。";
    return false;
  }
}

[studentClass, studentId, studentName].forEach(input => {
  input.addEventListener('input', checkFormValidity);
});
checkFormValidity();

// TTS 發音
btnAudio.addEventListener('click', () => {
  const synth = window.speechSynthesis;
  synth.cancel();

  const utterance = new SpeechSynthesisUtterance(targetSentence);
  utterance.lang = 'en-US';
  utterance.rate = 0.85;

  const voices = synth.getVoices();
  if (voices.length > 0) {
    const usVoice = voices.find(v => v.lang.includes('en-US') || v.lang.includes('en_US'));
    if (usVoice) utterance.voice = usVoice;
  }

  synth.speak(utterance);
});

// 語音辨識
const SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;
if (!SpeechRecognition) {
  feedbackMsg.innerText = "您的瀏覽器不支援語音辨識，請使用 Chrome 或 Safari 開啟。";
  btnMic.disabled = true;
} else {
  const recognition = new SpeechRecognition();
  recognition.lang = 'en-US';
  recognition.interimResults = false;

  btnMic.addEventListener('click', () => {
    if (!checkFormValidity()) return;
    try { recognition.start(); } catch(e) { recognition.stop(); }
  });

  recognition.onstart = () => {
    btnMic.classList.add('recording');
    btnMic.innerText = " 學生錄音中...";
    feedbackMsg.innerText = `正在聆聽 [${studentClass.value}] ${studentName.value} 同學的發音...`;
    for (let i = 0; i < targetWords.length; i++) {
      const el = document.getElementById(`w-${i}`);
      if(el) el.className = "w-unit pending";
    }
  };

  recognition.onend = () => {
    btnMic.classList.remove('recording');
    btnMic.innerText = "🎙️ 開始錄音演練";
  };

  recognition.onresult = (event) => {
    attemptCount++;
    attemptCountDisplay.innerText = `${attemptCount}次`;

    const studentSpeech = event.results[0][0].transcript;
    const studentWords = studentSpeech.toLowerCase().match(/\b[\w'-]+\b/g) || [];

    let sIdx = 0;
    let correctCount = 0;
    let missingCount = 0;
    let wrongCount = 0;

    for (let tIdx = 0; tIdx < targetWords.length; tIdx++) {
      const target = targetWords[tIdx];
      const el = document.getElementById(`w-${tIdx}`);

      if (sIdx < studentWords.length) {
        if (studentWords[sIdx] === target) {
          if(el) el.className = "w-unit correct";
          correctCount++;
          sIdx++;
        } else {
          const nextMatchIndex = studentWords.slice(sIdx).indexOf(target);
          if (nextMatchIndex !== -1) {
            if(el) el.className = "w-unit missing";
            missingCount++;
          } else {
            if(el) el.className = "w-unit wrong";
            wrongCount++;
            sIdx++;
          }
        }
      } else {
        if (el) el.className = "w-unit missing";
        missingCount++;
      }
    }

    const attemptWordsCount = correctCount + wrongCount;
    const completionRate = Math.round((attemptWordsCount / targetWords.length) * 100);
    const accuracyRate = attemptWordsCount > 0 ? Math.round((correctCount / attemptWordsCount) * 100) : 0;

    completionScore.innerText = `${completionRate}%`;
    accuracyScore.innerText = `${accuracyRate}%`;

    feedbackMsg.innerHTML = `<div>正在同步第 ${attemptCount} 次練習數據至雲端...</div>`;
    sendDataToGoogleSheet(completionRate, accuracyRate, studentSpeech, attemptCount, targetSentence);
  };

  recognition.onerror = (event) => {
    feedbackMsg.innerText = `錯誤: ${event.error}。請確認已允許麥克風權限。`;
  };
}

function sendDataToGoogleSheet(completion, accuracy, transcript, currentAttempt, targetSentenceText) {
  const payload = {
    className: studentClass.value.trim(),
    studentId: studentId.value.trim(),
    studentName: studentName.value.trim(),
    attemptCount: currentAttempt,
    targetSentence: targetSentenceText,
    completion: completion,
    accuracy: accuracy,
    transcript: transcript
  };

  fetch(GAS_URL, {
    method: "POST",
    mode: "no-cors",
    headers: { "Content-Type": "application/json" },
    body: JSON.stringify(payload)
  })
  .then(() => {
    feedbackMsg.innerHTML = `
      <span style="color:var(--success)">第 ${currentAttempt} 次練習成績已成功同步！</span><br>
      ${studentName.value} 同學實際說出: "<span style="color:#7f8c8d; font-style: italic;">${transcript}</span>"
    `;
  })
  .catch(err => {
    feedbackMsg.innerHTML = `<span style="color:var(--danger)">雲端同步失敗，請檢查網路。</span>`;
  });
}
</script>

</body>
</html>




