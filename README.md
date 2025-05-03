<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>AP Inter 1st Year Results 2025 - Search</title>
  <style>
    body { font-family: Arial, sans-serif; background: #f7f7f7; margin: 0; padding: 20px; }
    .container {
      background: #fff;
      max-width: 650px;
      margin: 40px auto;
      padding: 30px 40px;
      border-radius: 10px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.08);
    }
    h2 { color: #0066cc; }
    .input-group { margin-bottom: 20px; }
    label { font-weight: bold; }
    input[type="text"] {
      padding: 8px;
      width: 220px;
      font-size: 1em;
      border: 1px solid #aaa;
      border-radius: 4px;
      margin-right: 10px;
    }
    button {
      padding: 8px 18px;
      font-size: 1em;
      background: #0066cc;
      color: #fff;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    }
    button:hover { background: #004999; }
    .error { color: #c00; margin-top: 10px; }
    .result-card { margin-top: 30px; }
    .student-details, .grades-table { margin-bottom: 20px; }
    .student-details span { display: inline-block; min-width: 160px; font-weight: bold; }
    table { width: 100%; border-collapse: collapse; background: #fafafa; }
    th, td { border: 1px solid #ddd; padding: 10px 8px; text-align: center; }
    th { background: #f0f8ff; color: #333; }
    .grade-A1 { color: #228B22; font-weight: bold; }
    .grade-A2 { color: #2E8B57; font-weight: bold; }
    .grade-B1 { color: #4682B4; font-weight: bold; }
    .grade-B2 { color: #1E90FF; font-weight: bold; }
    .grade-C1 { color: #DAA520; font-weight: bold; }
    .grade-C2 { color: #FF8C00; font-weight: bold; }
    .grade-D1 { color: #B22222; font-weight: bold; }
    .grade-F { color: #DC143C; font-weight: bold; }
    .summary { margin-top: 20px; font-size: 1.1em; }
    .note { margin-top: 10px; font-size: 0.95em; color: #555; }
  </style>
</head>
<body>
  <div class="container">
    <h2>AP Inter 1st Year Results 2025</h2>
    <div class="input-group">
      <label for="hallTicketInput">Enter Hall Ticket Number:</label>
      <input type="text" id="hallTicketInput" maxlength="10" placeholder="e.g. 2504126254">
      <button onclick="showResult()">Get Result</button>
    </div>
    <div id="errorMsg" class="error"></div>
    <div id="resultArea"></div>
  </div>
  <script>
    // Sample data: Add more students as needed
    const resultsData = {
      "2504126254": {
        name: "Pallula Surya Prakash",
        group: "Bi.P.C (Biology, Physics, Chemistry)",
        results: [
          { subject: "English", marks: 85, max: 100, grade: "A2" },
          { subject: "Second Language (Telugu)", marks: 76, max: 100, grade: "B1" },
          { subject: "Botany (Theory + Practical)", marks: 55, max: 60, grade: "A1" },
          { subject: "Zoology (Theory + Practical)", marks: 58, max: 60, grade: "A1" },
          { subject: "Physics (Theory + Practical)", marks: 48, max: 60, grade: "B1" },
          { subject: "Chemistry (Theory + Practical)", marks: 43, max: 60, grade: "B2" }
        ],
        total: 365,
        maxTotal: 440,
        result: "PASSED"
      }
      // Add more hall tickets and their data here
    };

    function showResult() {
      const hallTicket = document.getElementById('hallTicketInput').value.trim();
      const resultArea = document.getElementById('resultArea');
      const errorMsg = document.getElementById('errorMsg');
      resultArea.innerHTML = '';
      errorMsg.textContent = '';

      if (!hallTicket) {
        errorMsg.textContent = "Please enter a hall ticket number.";
        return;
      }
      if (!resultsData[hallTicket]) {
        errorMsg.textContent = "Result not found for this hall ticket number.";
        return;
      }

      const data = resultsData[hallTicket];
      let tableRows = '';
      data.results.forEach(r => {
        tableRows += `
          <tr>
            <td>${r.subject}</td>
            <td>${r.marks}</td>
            <td>${r.max}</td>
            <td class="grade-${r.grade}">${r.grade}</td>
          </tr>
        `;
      });

      resultArea.innerHTML = `
        <div class="result-card">
          <div class="student-details">
            <div><span>Name:</span> ${data.name}</div>
            <div><span>Hall Ticket No:</span> ${hallTicket}</div>
            <div><span>Group:</span> ${data.group}</div>
          </div>
          <table class="grades-table">
            <tr>
              <th>Subject</th>
              <th>Marks Obtained</th>
              <th>Maximum Marks</th>
              <th>Grade</th>
            </tr>
            ${tableRows}
          </table>
          <div class="summary">
            <strong>Total Marks:</strong> ${data.total} / ${data.maxTotal}<br>
            <strong>Result:</strong> ${data.result}
          </div>
          <div class="note">
            <em>Note: This is a sample result format. For official results, please refer to the BIEAP website.</em>
          </div>
        </div>
      `;
    }
  </script>
</body>
</html>
