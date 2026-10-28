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
      text-align:
