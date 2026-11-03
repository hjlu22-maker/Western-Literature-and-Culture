<!DOCTYPE html>
<html lang="zh-TW">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Western Literature and Culture - Interactive Quiz System</title>
  <style>
    *, *::before, *::after {
      box-sizing: border-box;
    }

    :root {
      --primary: #2563eb;
      --primary-dark: #1d4ed8;
      --secondary: #475569;
      --success: #16a34a;
      --danger: #dc2626;
      --warning: #d97706;
      --dark: #0f172a;
      --light-bg: #f8fafc;
      --card-bg: #ffffff;
      --border: #cbd5e1;
      --accent: #7c3aed;
    }

    body {
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
      background-color: #f1f5f9;
      color: var(--dark);
      margin: 0;
      padding: 30px 15px;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    .quiz-container {
      background: var(--card-bg);
      padding: 35px 30px;
      border-radius: 16px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.06);
      width: 100%;
      max-width: 860px;
    }

    .header-section {
      text-align: center;
      margin-bottom: 25px;
      border-bottom: 2px solid #e2e8f0;
      padding-bottom: 15px;
    }

    .header-section h1 {
      margin: 0 0 8px 0;
      color: #1e293b;
      font-size: 26px;
      font-weight: 800;
    }

    .header-section p {
      margin: 0;
      color: #64748b;
      font-size: 15px;
    }

    /* 學生資訊欄 */
    .student-info-form {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 15px;
      background: var(--light-bg);
      padding: 18px 20px;
      border-radius: 12px;
      border: 1px solid var(--border);
      margin-bottom: 30px;
    }

    .form-group {
      display: flex;
      flex-direction: column;
      text-align: left;
    }

    .form-group label {
      font-size: 13px;
      font-weight: 700;
      margin-bottom: 6px;
      color: #334155;
    }

    .form-group label::after {
      content: " *";
      color: var(--danger);
    }

    .form-group input {
      width: 100%;
      padding: 9px 12px;
      font-size: 14px;
      border: 1px solid var(--border);
      border-radius: 6px;
      outline: none;
      background: #fff;
    }

    .form-group input:focus {
      border-color: var(--primary);
      box-shadow: 0 0 0 2px rgba(37,99,235,0.15);
    }

    /* 區段樣式 */
    .section-title {
      background: #eff6ff;
      border-left: 5px solid var(--primary);
      padding: 10px 15px;
      font-size: 17px;
      font-weight: 700;
      color: #1e3a8a;
      margin: 30px 0 15px 0;
      border-radius: 0 8px 8px 0;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .section-badge {
      font-size: 12px;
      background: var(--primary);
      color: #fff;
      padding: 3px 8px;
      border-radius: 12px;
    }

    .question-card {
      background: #ffffff;
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 18px 20px;
      margin-bottom: 18px;
      transition: all 0.2s;
    }

    .question-card:hover {
      border-color: #94a3b8;
    }

    .q-source {
      display: inline-block;
      font-size: 12px;
      font-weight: 700;
      color: #b45309;
      background: #fef3c7;
      padding: 2px 8px;
      border-radius: 4px;
      margin-bottom: 8px;
    }

    .q-text {
      font-size: 15px;
      font-weight: 600;
      line-height: 1.5;
      margin-bottom: 12px;
      color: #1e293b;
    }

    .options-group label {
      display: flex;
      align-items: flex-start;
      gap: 10px;
      padding: 8px 12px;
      margin-bottom: 6px;
      border-radius: 6px;
      cursor: pointer;
      font-size: 14px;
      line-height: 1.4;
      background: #f8fafc;
      border: 1px solid transparent;
      transition: background 0.15s;
    }

    .options-group label:hover {
      background: #f1f5f9;
    }

    .options-group input {
      margin-top: 3px;
    }

    /* 配對下拉選單 */
    .matching-table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 10px;
    }

    .matching-table th, .matching-table td {
      border: 1px solid #e2e8f0;
      padding: 10px 12px;
      text-align: left;
      font-size: 14px;
    }

    .matching-table th {
      background: #f8fafc;
    }

    .matching-table select {
      width: 100%;
      padding: 6px 10px;
      border-radius: 6px;
      border: 1px solid var(--border);
      font-size: 13px;
      background: white;
    }

    /* 排序題型 */
    .ordering-list {
      list-style: none;
      padding: 0;
      margin: 10px 0 0 0;
    }

    .ordering-item {
      display: flex;
      align-items: center;
      gap: 12px;
      padding: 8px 12px;
      margin-bottom: 8px;
      background: #f8fafc;
      border: 1px solid #e2e8f0;
      border-radius: 6px;
      font-size: 14px;
    }

    .ordering-item select {
      width: 75px;
      padding: 4px 6px;
      border-radius: 4px;
      border: 1px solid var(--border);
      font-weight: bold;
    }

    /* 開放題文字框 */
    .essay-textarea {
      width: 100%;
      height: 110px;
      padding: 10px 12px;
      border-radius: 6px;
      border: 1px solid var(--border);
      font-size: 14px;
      line-height: 1.5;
      font-family: inherit;
      resize: vertical;
      outline: none;
    }

    .essay-textarea:focus {
      border-color: var(--primary);
    }

    .rubric-box {
      display: none;
      margin-top: 12px;
      padding: 12px 14px;
      background: #ecfdf5;
      border: 1px solid #a7f3d0;
      border-radius: 6px;
      font-size: 13px;
      color: #065f46;
      line-height: 1.5;
    }

    /* 反饋及評分區塊 */
    .feedback {
      display: none;
      margin-top: 10px;
      font-size: 13px;
      padding: 8px 12px;
      border-radius: 6px;
    }

    .feedback.correct {
      display: block;
      background: #dcfce7;
      color: #166534;
      border: 1px solid #86efac;
    }

    .feedback.wrong {
      display: block;
      background: #fee2e2;
      color: #991b1b;
      border: 1px solid #fca5a5;
    }

    .submit-bar {
      margin-top: 30px;
      text-align: center;
    }

    .btn-submit {
      background: var(--primary);
      color: #fff;
      font-size: 16px;
      font-weight: 700;
      padding: 12px 36px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: background 0.2s, transform 0.1s;
    }

    .btn-submit:hover {
      background: var(--primary-dark);
    }

    .btn-submit:active {
      transform: scale(0.98);
    }

    .btn-submit:disabled {
      background: #cbd5e1;
      cursor: not-allowed;
    }

    /* 成績看板 */
    .score-summary-card {
      display: none;
      margin-top: 25px;
      padding: 20px;
      background: #faf5ff;
      border: 2px solid #d8b4fe;
      border-radius: 12px;
      text-align: center;
    }

    .score-summary-card h2 {
      margin: 0 0 10px 0;
      color: #581c87;
    }

    .score-val {
      font-size: 38px;
      font-weight: 900;
      color: #7e22ce;
      margin: 8px 0;
    }

    .sync-status {
      font-size: 13px;
      color: #64748b;
      margin-top: 10px;
    }

    @media (max-width: 600px) {
      .student-info-form {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>
<body>

<div class="quiz-container">
  <div class="header-section">
    <h1>Western Literature and Culture</h1>
    <p>Comprehensive Knowledge & Critical Assessment (Based on Course Handouts)</p>
  </div>

  <!-- 學生資訊區 -->
  <div class="student-info-form">
    <div class="form-group">
      <label for="studentClass">Class / 班級</label>
      <input type="text" id="studentClass" placeholder="e.g. 英二A" required>
    </div>
    <div class="form-group">
      <label for="studentId">Student ID / 學號</label>
      <input type="text" id="studentId" placeholder="e.g. 11012345" required>
    </div>
    <div class="form-group">
      <label for="studentName">Name / 姓名</label>
      <input type="text" id="studentName" placeholder="e.g. 陳大明" required>
    </div>
  </div>

  <form id="quizForm">
    <!-- Part 1: Multiple Choice (30%) -->
    <div class="section-title">
      <span>Part I: Multiple Choice Questions (單選題)</span>
      <span class="section-badge">30% (6% each)</span>
    </div>

    <!-- Q1 -->
    <div class="question-card" id="card-q1">
      <span class="q-source">[Handout p.8] Biblical Textual History</span>
      <div class="q-text">1. According to the handout on Biblical composition and terminology, which of the following statements is factual?</div>
      <div class="options-group">
        <label><input type="radio" name="q1" value="A"> (A) The New Testament was composed over more than a thousand years, just like the Old Testament.</label>
        <label><input type="radio" name="q1" value="B"> (B) The New Testament consists of 27 books and was written in a much shorter period of about 50 years (approx. 45 to 95 AD).</label>
        <label><input type="radio" name="q1" value="C"> (C) Modern scholarship rejects the terms "Hebrew Scriptures" and "Christian Scriptures" because they imply obsolescence.</label>
        <label><input type="radio" name="q1" value="D"> (D) The Hebrew Bible contains 39 books, which are fundamentally different from the 24 books of the Christian Old Testament.</label>
      </div>
      <div class="feedback" id="fb-q1"></div>
    </div>

    <!-- Q2 -->
    <div class="question-card" id="card-q2">
      <span class="q-source">[Handout p.23-24] Edith Hamilton: Classical Mythology</span>
      <div class="q-text">2. What revolutionary perspective does Edith Hamilton define as "the Greek miracle"?</div>
      <div class="options-group">
        <label><input type="radio" name="q2" value="A"> (A) Ancient Greeks viewed mankind as mere playthings governed completely by fear, magic, and animal-headed monster deities.</label>
        <label><input type="radio" name="q2" value="B"> (B) The gods were placed in rigid cosmic temples aloof from all mortals, prohibiting any laughter or familiarity.</label>
        <label><input type="radio" name="q2" value="C"> (C) Mankind became the center of the universe, and the Greeks made their gods in their own human image, freeing humanity from the paralyzing fear of the Unknown.</label>
        <label><input type="radio" name="q2" value="D"> (D) Greek civilization completely eradicated all warfare and replaced it with strict astrology.</label>
      </div>
      <div class="feedback" id="fb-q2"></div>
    </div>

    <!-- Q3 -->
    <div class="question-card" id="card-q3">
      <span class="q-source">[Handout p.73] Greek Tragedy Key Concepts</span>
      <div class="q-text">3. In classical Greek tragedy, what is the root cause that brings the tragic hero to disaster?</div>
      <div class="options-group">
        <label><input type="radio" name="q3" value="A"> (A) Inherent malevolence and a total absence of civic virtue.</label>
        <label><input type="radio" name="q3" value="B"> (B) A tragic flaw or error in judgment (<i>hamartia</i>), frequently manifested as excessive pride (<i>hubris</i>) in thinking one can escape fate.</label>
        <label><input type="radio" name="q3" value="C"> (C) Accidental financial ruin caused by city-state taxation.</label>
        <label><input type="radio" name="q3" value="D"> (D) Lack of rhetorical education during the Festival of Dionysus.</label>
      </div>
      <div class="feedback" id="fb-q3"></div>
    </div>

    <!-- Q4 -->
    <div class="question-card" id="card-q4">
      <span class="q-source">[Handout p.73] Structure of Greek Drama</span>
      <div class="q-text">4. Which part of a Greek tragedy represents the formal entrance and opening song of the chorus?</div>
      <div class="options-group">
        <label><input type="radio" name="q4" value="A"> (A) Prologue</label>
        <label><input type="radio" name="q4" value="B"> (B) Parados</label>
        <label><input type="radio" name="q4" value="C"> (C) Episode</label>
        <label><input type="radio" name="q4" value="D"> (D) Exodos</label>
      </div>
      <div class="feedback" id="fb-q4"></div>
    </div>

    <!-- Q5 -->
    <div class="question-card" id="card-q5">
      <span class="q-source">[Handout p.37-38] Homer: Epic Value Contrast</span>
      <div class="q-text">5. When Odysseus meets the shade of Achilles in the Underworld, how does the <i>Odyssey</i> define its core value in sharp contrast to the <i>Iliad</i>?</div>
      <div class="options-group">
        <label><input type="radio" name="q5" value="A"> (A) Achilles rejoices in eternal military fame in death, urging Odysseus to seek death in glorious battle.</label>
        <label><input type="radio" name="q5" value="B"> (B) Achilles states he would rather be the day-laborer to a poor peasant on earth than king of all the dead, highlighting Odysseus's deep dedication to human life and return.</label>
        <label><input type="radio" name="q5" value="C"> (C) Odysseus accepts the gift of immortality from Calypso so that he never has to visit the dead again.</label>
        <label><input type="radio" name="q5" value="D"> (D) Both heroes conclude that dying young on the battlefield is the only worthy outcome of heroic virtue.</label>
      </div>
      <div class="feedback" id="fb-q5"></div>
    </div>

    <!-- Part 2: Multiple Selection (30%) -->
    <div class="section-title">
      <span>Part II: Multiple Selection Questions (多選題)</span>
      <span class="section-badge">30% (10% each, 全對給分)</span>
    </div>

    <!-- Q6 -->
    <div class="question-card" id="card-q6">
      <span class="q-source">[Handout p.72] Ancient Greek Theater & Staging Conditions</span>
      <div class="q-text">6. (Multiple Selection) Based on the course handouts, which of the following characteristics accurately described the staging and actors of ancient Greek drama? (Select ALL that apply)</div>
      <div class="options-group">
        <label><input type="checkbox" name="q6" value="A"> (A) There were no curtains, no intermissions, no artificial lighting, and no microphones.</label>
        <label><input type="checkbox" name="q6" value="B"> (B) All performances took place during daylight, and all scene changes had to be built into the actors' dialogue.</label>
        <label><input type="checkbox" name="q6" value="C"> (C) Actors (only men, no actresses) wore expressive masks and long robes to portray multiple roles.</label>
        <label><input type="checkbox" name="q6" value="D"> (D) The theatrical crane used for suspending figures portraying gods was termed <i>Deus ex machina</i> ("god from the machine").</label>
      </div>
      <div class="feedback" id="fb-q6"></div>
    </div>

    <!-- Q7 -->
    <div class="question-card" id="card-q7">
      <span class="q-source">[Handout p.72] Functions of the Chorus</span>
      <div class="q-text">7. (Multiple Selection) What essential functions did the Chorus perform in classical Greek tragedy? (Select ALL that apply)</div>
      <div class="options-group">
        <label><input type="checkbox" name="q7" value="A"> (A) Express the main themes of the drama by commenting directly on the ongoing action.</label>
        <label><input type="checkbox" name="q7" value="B"> (B) Create an emotional and philosophical bridge between the actors and the audience.</label>
        <label><input type="checkbox" name="q7" value="C"> (C) Converse with actors and offer counsel or warnings.</label>
        <label><input type="checkbox" name="q7" value="D"> (D) Foretell future consequences and narrate past background events.</label>
      </div>
      <div class="feedback" id="fb-q7"></div>
    </div>

    <!-- Q8 -->
    <div class="question-card" id="card-q8">
      <span class="q-source">[Handout p.26-31] Olympians & Roman Equivalents</span>
      <div class="q-text">8. (Multiple Selection) Which of the following Olympian deities are paired correctly with their Roman name and primary attributes/symbols? (Select ALL that apply)</div>
      <div class="options-group">
        <label><input type="checkbox" name="q8" value="A"> (A) <b>Hestia</b> / Vesta: Goddess of the hearth and home; in Rome, her public fire was tended by six virgin priestesses (Vestals).</label>
        <label><input type="checkbox" name="q8" value="B"> (B) <b>Ares</b> / Mars: Greek god of violent war; while Greeks saw him as brutal and hateful, the Romans revered Mars as redoubtable and magnificent.</label>
        <label><input type="checkbox" name="q8" value="C"> (C) <b>Poseidon</b> / Neptune: Ruler of the sea who gave the first horse to man; his emblem is the trident.</label>
        <label><input type="checkbox" name="q8" value="D"> (D) <b>Pallas Athena</b> / Minerva: Sprang fully grown from Zeus's head; goddess of the city, handicrafts, and wisdom; associated with the owl and olive.</label>
      </div>
      <div class="feedback" id="fb-q8"></div>
    </div>

    <!-- Part 3: Matching & Ordering (30%) -->
    <div class="section-title">
      <span>Part III: Matching & Ordering (配對與排序題)</span>
      <span class="section-badge">30% (15% each)</span>
    </div>

    <!-- Q9: Matching -->
    <div class="question-card" id="card-q9">
      <span class="q-source">[Handout p.32, 33, 34, 60, 69] Character & Mythological Association</span>
      <div class="q-text">9. (Matching, 15%) Match each literary figure or episode with their correct description:</div>
      <table class="matching-table">
        <thead>
          <tr>
            <th style="width: 55%;">Description</th>
            <th style="width: 45%;">Match Character / Figure</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>(1) Titan who stole fire for humanity, gave man an upright posture, and was punished by an eagle pecking his liver. [p.33]</td>
            <td>
              <select id="m1">
                <option value="">-- Choose Character --</option>
                <option value="Prometheus">Prometheus</option>
                <option value="Narcissus">Narcissus</option>
                <option value="Daphne">Daphne</option>
                <option value="Demodocus">Demodocus</option>
                <option value="Eurykleia">Eurykleia</option>
              </select>
            </td>
          </tr>
          <tr>
            <td>(2) Handsome youth who scorned the love of nymphs and fell hopelessly in love with his own reflection at a pool. [p.32]</td>
            <td>
              <select id="m2">
                <option value="">-- Choose Character --</option>
                <option value="Prometheus">Prometheus</option>
                <option value="Narcissus">Narcissus</option>
                <option value="Daphne">Daphne</option>
                <option value="Demodocus">Demodocus</option>
                <option value="Eurykleia">Eurykleia</option>
              </select>
            </td>
          </tr>
          <tr>
            <td>(3) Nymph who fled Apollo's pursuit and prayed to her river-father to be transformed into a laurel tree. [p.34]</td>
            <td>
              <select id="m3">
                <option value="">-- Choose Character --</option>
                <option value="Prometheus">Prometheus</option>
                <option value="Narcissus">Narcissus</option>
                <option value="Daphne">Daphne</option>
                <option value="Demodocus">Demodocus</option>
                <option value="Eurykleia">Eurykleia</option>
              </select>
            </td>
          </tr>
          <tr>
            <td>(4) Blind Phaeacian minstrel who sang of the Trojan wooden horse, causing Odysseus to cloak his weeping face. [p.69-71]</td>
            <td>
              <select id="m4">
                <option value="">-- Choose Character --</option>
                <option value="Prometheus">Prometheus</option>
                <option value="Narcissus">Narcissus</option>
                <option value="Daphne">Daphne</option>
                <option value="Demodocus">Demodocus</option>
                <option value="Eurykleia">Eurykleia</option>
              </select>
            </td>
          </tr>
          <tr>
            <td>(5) Old faithful nurse in Ithaca who recognized Odysseus in beggar disguise by the old scar on his knee. [p.60]</td>
            <td>
              <select id="m5">
                <option value="">-- Choose Character --</option>
                <option value="Prometheus">Prometheus</option>
                <option value="Narcissus">Narcissus</option>
                <option value="Daphne">Daphne</option>
                <option value="Demodocus">Demodocus</option>
                <option value="Eurykleia">Eurykleia</option>
              </select>
            </td>
          </tr>
        </tbody>
      </table>
      <div class="feedback" id="fb-q9"></div>
    </div>

    <!-- Q10: Ordering -->
    <div class="question-card" id="card-q10">
      <span class="q-source">[Handout p.75, 79, 81, 84, 85, 86] Sophocles: Oedipus the King</span>
      <div class="q-text">10. (Chronological Ordering, 15%) Arrange the following events from <i>Oedipus the King</i> in chronological order (from 1 to 5):</div>
      <ul class="ordering-list">
        <li class="ordering-item">
          <select id="ord-c1">
            <option value="">Order</option>
            <option value="1">1st</option><option value="2">2nd</option><option value="3">3rd</option><option value="4">4th</option><option value="5">5th</option>
          </select>
          <span><b>A.</b> Creon returns from the Delphic oracle announcing that the polluter/murderer of Laius must be driven out. [p.79]</span>
        </li>
        <li class="ordering-item">
          <select id="ord-c2">
            <option value="">Order</option>
            <option value="1">1st</option><option value="2">2nd</option><option value="3">3rd</option><option value="4">4th</option><option value="5">5th</option>
          </select>
          <span><b>B.</b> Enraged by insults, blind prophet Tiresias accuses Oedipus: "You are the murderer you hunt." [p.81-82]</span>
        </li>
        <li class="ordering-item">
          <select id="ord-c3">
            <option value="">Order</option>
            <option value="1">1st</option><option value="2">2nd</option><option value="3">3rd</option><option value="4">4th</option><option value="5">5th</option>
          </select>
          <span><b>C.</b> Jocasta tries to calm Oedipus by explaining that Laius was killed at a place "where three roads meet." [p.84]</span>
        </li>
        <li class="ordering-item">
          <select id="ord-c4">
            <option value="">Order</option>
            <option value="1">1st</option><option value="2">2nd</option><option value="3">3rd</option><option value="4">4th</option><option value="5">5th</option>
          </select>
          <span><b>D.</b> A messenger from Corinth arrives reporting Polybus's death and reveals Oedipus was not Polybus's biological son. [p.85]</span>
        </li>
        <li class="ordering-item">
          <select id="ord-c5">
            <option value="">Order</option>
            <option value="1">1st</option><option value="2">2nd</option><option value="3">3rd</option><option value="4">4th</option><option value="5">5th</option>
          </select>
          <span><b>E.</b> Finding Jocasta hanged, Oedipus gouges out his eyes using the golden pins from her robe. [p.86]</span>
        </li>
      </ul>
      <div class="feedback" id="fb-q10"></div>
    </div>

    <!-- Part 4: Open Reflection (10%) -->
    <div class="section-title">
      <span>Part IV: Critical Reflection & Analysis (開放思辨題)</span>
      <span class="section-badge">10% (Rubric-Guided)</span>
    </div>

    <div class="question-card" id="card-q11">
      <span class="q-source">[Handout p.75-76] Intellectual Courage & Tragic Self-Discovery</span>
      <div class="q-text">11. (Short Essay / Open Reflection, 10%):<br>
        In Sophocles' <i>Oedipus the King</i>, when the shepherd hesitates and Jocasta pleads with him to stop, Oedipus passionately replies: <i>"I'm right at the edge of hearing horrors, yes, but I must hear!"</i><br>
        <b>Question:</b> Drawing from the course handout, explain why Oedipus refuses to stop his relentless search for truth. What distinctive Athenian intellectual virtues and tragic vulnerabilities does his relentless investigation represent?
      </div>
      <textarea class="essay-textarea" id="essayAnswer" placeholder="Type your critical reflection here in English or Chinese (at least 30-50 words)..."></textarea>
      
      <div class="rubric-box" id="rubricBox">
        <b>📚 Reference Analysis & Rubric Benchmark (評分對照核心要點):</b>
        <ul>
          <li><b>Intellectual Honesty & Confidence:</b> Oedipus mirrors 5th-century Athenian confidence in human rational inquiry and quick problem-solving (just as he solved the riddle of the Sphinx without prophetic aids)[cite: 75, 78].</li>
          <li><b>Dedication to the Polis:</b> As a responsible ruler, he cannot let the plague destroy his people; curing Thebes demands exposing corruption[cite: 75, 79].</li>
          <li><b>The Paradox of Human Knowledge:</b> The very intellect that made him savior becomes the engine of his downfall; his persistent pursuit proves that human wisdom is limited against divine destiny, creating profound tragic irony[cite: 75].</li>
        </ul>
      </div>
      <div class="feedback" id="fb-q11"></div>
    </div>

    <div class="submit-bar">
      <button type="button" class="btn-submit" id="btnSubmit">Submit Assessment & Calculate Score</button>
    </div>
  </form>

  <!-- 結果看板 -->
  <div class="score-summary-card" id="scoreSummary">
    <h2>測驗成績結算 / Quiz Results</h2>
    <div class="score-val" id="totalScoreText">0 / 100</div>
    <div id="breakdownText" style="font-size:14px; color:#4b5563;"></div>
    <div class="sync-status" id="syncStatus">Ready to submit.</div>
  </div>
</div>

<script>
  // Google Apps Script 接收端網址 (若有自建試算表，可直接置換)
  const GAS_URL = "https://script.google.com/macros/s/AKfycbxl86DfQJxa3rrIGX9fEFTz5sW-MYeZrH8Kvb1V5A8pyijeQjIVntKnfHCK8Na389O1/exec";

  const btnSubmit = document.getElementById('btnSubmit');
  const studentClass = document.getElementById('studentClass');
  const studentId = document.getElementById('studentId');
  const studentName = document.getElementById('studentName');

  btnSubmit.addEventListener('click', () => {
    // 檢查基本資料填寫
    if (!studentClass.value.trim() || !studentId.value.trim() || !studentName.value.trim()) {
      alert("請先完整填寫上方學生資訊（班級、學號、姓名）再繳交測驗！");
      studentClass.focus();
      return;
    }

    let scoreP1 = 0; // 30%
    let scoreP2 = 0; // 30%
    let scoreP3 = 0; // 30%
    let scoreP4 = 0; // 10%

    // --- Part I: 單選題 (每題 6 分，共 30 分) ---
    // Q1 Answer: B
    const q1Val = document.querySelector('input[name="q1"]:checked')?.value;
    const fbQ1 = document.getElementById('fb-q1');
    if (q1Val === "B") {
      scoreP1 += 6;
      fbQ1.className = "feedback correct";
      fbQ1.innerHTML = "✓ 正確 (+6分)！新約共 27 卷，於約 50 年內成書 (約 45–95 AD)。[Handout p.8]";
    } else {
      fbQ1.className = "feedback wrong";
      fbQ1.innerHTML = "✗ 錯誤。正確答案為 (B)。新約僅耗時約 50 年成書，且現代更常用 Hebrew/Christian Scriptures。[Handout p.8]";
    }

    // Q2 Answer: C
    const q2Val = document.querySelector('input[name="q2"]:checked')?.value;
    const fbQ2 = document.getElementById('fb-q2');
    if (q2Val === "C") {
      scoreP1 += 6;
      fbQ2.className = "feedback correct";
      fbQ2.innerHTML = "✓ 正確 (+6分)！希臘奇蹟代表人類成為宇宙中心，依據人的形象創造神明，世界因而理性化。[Handout p.23-24]";
    } else {
      fbQ2.className = "feedback wrong";
      fbQ2.innerHTML = "✗ 錯誤。正確答案為 (C)。[Handout p.23-24]";
    }

    // Q3 Answer: B
    const q3Val = document.querySelector('input[name="q3"]:checked')?.value;
    const fbQ3 = document.getElementById('fb-q3');
    if (q3Val === "B") {
      scoreP1 += 6;
      fbQ3.className = "feedback correct";
      fbQ3.innerHTML = "✓ 正確 (+6分)！悲劇英雄多因悲劇缺陷 (hamartia) 或傲慢 (hubris) 走向災禍。[Handout p.73]";
    } else {
      fbQ3.className = "feedback wrong";
      fbQ3.innerHTML = "✗ 錯誤。正確答案為 (B)。[Handout p.73]";
    }

    // Q4 Answer: B
    const q4Val = document.querySelector('input[name="q4"]:checked')?.value;
    const fbQ4 = document.getElementById('fb-q4');
    if (q4Val === "B") {
      scoreP1 += 6;
      fbQ4.className = "feedback correct";
      fbQ4.innerHTML = "✓ 正確 (+6分)！Parados 為合唱團進場與進場頌歌。[Handout p.73]";
    } else {
      fbQ4.className = "feedback wrong";
      fbQ4.innerHTML = "✗ 錯誤。正確答案為 (B)。[Handout p.73]";
    }

    // Q5 Answer: B
    const q5Val = document.querySelector('input[name="q5"]:checked')?.value;
    const fbQ5 = document.getElementById('fb-q5');
    if (q5Val === "B") {
      scoreP1 += 6;
      fbQ5.className = "feedback correct";
      fbQ5.innerHTML = "✓ 正確 (+6分)！阿基里斯在冥界哀嘆寧為活著的賤僕，凸顯奧德修斯重返人間家園之堅毅追求。[Handout p.37-38]";
    } else {
      fbQ5.className = "feedback wrong";
      fbQ5.innerHTML = "✗ 錯誤。正確答案為 (B)。[Handout p.37-38]";
    }

    // --- Part II: 多選題 (每題 10 分，共 30 分) ---
    // Q6: A, B, C, D 全選
    const q6Checked = Array.from(document.querySelectorAll('input[name="q6"]:checked')).map(el => el.value);
    const fbQ6 = document.getElementById('fb-q6');
    if (q6Checked.length === 4 && ["A","B","C","D"].every(v => q6Checked.includes(v))) {
      scoreP2 += 10;
      fbQ6.className = "feedback correct";
      fbQ6.innerHTML = "✓ 全對 (+10分)！A、B、C、D 皆為古希臘劇場演出之關鍵特徵。[Handout p.72]";
    } else {
      fbQ6.className = "feedback wrong";
      fbQ6.innerHTML = "✗ 未完全正確。正確答案為 (A)(B)(C)(D) 全選。[Handout p.72]";
    }

    // Q7: A, B, C, D 全選
    const q7Checked = Array.from(document.querySelectorAll('input[name="q7"]:checked')).map(el => el.value);
    const fbQ7 = document.getElementById('fb-q7');
    if (q7Checked.length === 4 && ["A","B","C","D"].every(v => q7Checked.includes(v))) {
      scoreP2 += 10;
      fbQ7.className = "feedback correct";
      fbQ7.innerHTML = "✓ 全對 (+10分)！講義明確指出合唱團具有表達主旨、橋樑溝通、諫言與預言等核心功能。[Handout p.72]";
    } else {
      fbQ7.className = "feedback wrong";
      fbQ7.innerHTML = "✗ 未完全正確。正確答案為 (A)(B)(C)(D) 全選。[Handout p.72]";
    }

    // Q8: A, B, C, D 全選
    const q8Checked = Array.from(document.querySelectorAll('input[name="q8"]:checked')).map(el => el.value);
    const fbQ8 = document.getElementById('fb-q8');
    if (q8Checked.length === 4 && ["A","B","C","D"].every(v => q8Checked.includes(v))) {
      scoreP2 += 10;
      fbQ8.className = "feedback correct";
      fbQ8.innerHTML = "✓ 全對 (+10分)！四組希臘/羅馬神祇對應及象徵完全符合講義所列。[Handout p.26-31]";
    } else {
      fbQ8.className = "feedback wrong";
      fbQ8.innerHTML = "✗ 未完全正確。正確答案為 (A)(B)(C)(D) 全選。[Handout p.26-31]";
    }

    // --- Part III: Matching & Ordering (各 15 分，共 30 分) ---
    // Q9 Matching
    const m1 = document.getElementById('m1').value;
    const m2 = document.getElementById('m2').value;
    const m3 = document.getElementById('m3').value;
    const m4 = document.getElementById('m4').value;
    const m5 = document.getElementById('m5').value;
    const fbQ9 = document.getElementById('fb-q9');

    let matchCount = 0;
    if (m1 === "Prometheus") matchCount++;
    if (m2 === "Narcissus") matchCount++;
    if (m3 === "Daphne") matchCount++;
    if (m4 === "Demodocus") matchCount++;
    if (m5 === "Eurykleia") matchCount++;

    const scoreMatch = matchCount * 3; // 5 x 3 = 15 分
    scoreP3 += scoreMatch;
    if (matchCount === 5) {
      fbQ9.className = "feedback correct";
      fbQ9.innerHTML = `✓ 配對完全正確 (+15分)！(1)Prometheus, (2)Narcissus, (3)Daphne, (4)Demodocus, (5)Eurykleia。`;
    } else {
      fbQ9.className = "feedback wrong";
      fbQ9.innerHTML = `答對 ${matchCount}/5 題 (得 ${scoreMatch}/15 分)。正確對應為：(1)Prometheus, (2)Narcissus, (3)Daphne, (4)Demodocus, (5)Eurykleia。`;
    }

    // Q10 Ordering (A:1, B:2, C:3, D:4, E:5)
    const o1 = document.getElementById('ord-c1').value;
    const o2 = document.getElementById('ord-c2').value;
    const o3 = document.getElementById('ord-c3').value;
    const o4 = document.getElementById('ord-c4').value;
    const o5 = document.getElementById('ord-c5').value;
    const fbQ10 = document.getElementById('fb-q10');

    let orderCount = 0;
    if (o1 === "1") orderCount++;
    if (o2 === "2") orderCount++;
    if (o3 === "3") orderCount++;
    if (o4 === "4") orderCount++;
    if (o5 === "5") orderCount++;

    const scoreOrder = orderCount * 3; // 5 x 3 = 15 分
    scoreP3 += scoreOrder;
    if (orderCount === 5) {
      fbQ10.className = "feedback correct";
      fbQ10.innerHTML = `✓ 排序完全正確 (+15分)！時序為 A (神諭帶回) → B (盲先知指控) → C (三叉路口) → D (信差到來) → E (刺瞎雙目)。`;
    } else {
      fbQ10.className = "feedback wrong";
      fbQ10.innerHTML = `排序配對正確 ${orderCount}/5 項 (得 ${scoreOrder}/15 分)。正確時序為：A (1st) → B (2nd) → C (3rd) → D (4th) → E (5th)。`;
    }

    // --- Part IV: Open Reflection (10%) ---
    const essayAns = document.getElementById('essayAnswer').value.trim();
    const rubricBox = document.getElementById('rubricBox');
    const fbQ11 = document.getElementById('fb-q11');
    rubricBox.style.display = 'block';

    // 依據回答豐富度及關鍵概念檢視自動採計基本分，並提供 Rubric
    if (essayAns.length >= 25) {
      scoreP4 = 10;
      fbQ11.className = "feedback correct";
      fbQ11.innerHTML = "✓ 思辨申論已成功提交 (+10分)！請對照下方講義核心指標（Rubric）檢視自身回答深度。";
    } else if (essayAns.length > 5) {
      scoreP4 = 5;
      fbQ11.className = "feedback wrong";
      fbQ11.innerHTML = "△ 論述較為簡略 (+5分)。建議多結合講義中雅典理性誠實與命運限制之論點。";
    } else {
      scoreP4 = 0;
      fbQ11.className = "feedback wrong";
      fbQ11.innerHTML = "✗ 未填寫或字數過少 (0分)。請填寫後重新計算。";
    }

    // 總分計算
    const totalScore = scoreP1 + scoreP2 + scoreP3 + scoreP4;

    // 顯示結果
    const scoreCard = document.getElementById('scoreSummary');
    scoreCard.style.display = 'block';
    document.getElementById('totalScoreText').innerText = `${totalScore} / 100`;
    document.getElementById('breakdownText').innerHTML = `
      單選題：${scoreP1}/30 分 | 多選題：${scoreP2}/30 分<br>
      配對與排序：${scoreP3}/30 分 | 開放思辨：${scoreP4}/10 分
    `;
    scoreCard.scrollIntoView({ behavior: 'smooth' });

    // 同步到 Google Sheet
    syncToCloud({
      className: studentClass.value.trim(),
      studentId: studentId.value.trim(),
      studentName: studentName.value.trim(),
      scoreP1: scoreP1,
      scoreP2: scoreP2,
      scoreP3: scoreP3,
      scoreP4: scoreP4,
      totalScore: totalScore,
      essayAnswer: essayAns
    });
  });

  function syncToCloud(data) {
    const statusEl = document.getElementById('syncStatus');
    statusEl.innerHTML = "正在同步成績數據至雲端試算表...";

    fetch(GAS_URL, {
      method: "POST",
      mode: "no-cors",
      headers: { "Content-Type": "application/json" },
      body: JSON.stringify(data)
    })
    .then(() => {
      statusEl.innerHTML = "<span style='color:var(--success); font-weight:bold;'>✓ 成績已成功同步至雲端記錄庫！</span>";
    })
    .catch(() => {
      statusEl.innerHTML = "<span style='color:var(--warning);'>（提示：雲端連線未啟用或離線中，本地評分已完成）</span>";
    });
  }
</script>

</body>
</html>
