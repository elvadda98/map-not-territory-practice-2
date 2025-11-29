<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Map–Territory Practice 2</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      max-width: 900px;
      margin: 20px auto;
      line-height: 1.5;
      padding: 0 10px;
    }
    h1, h2 {
      margin-top: 1.4em;
    }
    .card {
      border: 1px solid #bbb;
      border-radius: 8px;
      padding: 14px;
      margin: 14px 0;
      background: #fafafa;
    }
    .question-title {
      font-weight: bold;
      margin-bottom: 8px;
    }
    .feedback {
      margin-top: 8px;
      padding: 8px;
      border-radius: 6px;
      background: #fff;
      border-left: 4px solid #888;
      display: none;
    }
    .correct {
      border-left-color: green;
      color: green;
    }
    .incorrect {
      border-left-color: darkred;
      color: darkred;
    }
    button {
      margin-top: 6px;
      padding: 6px 10px;
      border-radius: 6px;
      border: 1px solid #666;
      cursor: pointer;
    }
  </style>
</head>
<body>

<h1>Map–Territory Practice 2 (Advanced)</h1>
<p>
  This advanced practice challenges your ability to detect subtle mistakes
  in reasoning. Select your answer — if it’s wrong, a detailed explanation
  will appear telling you <strong>exactly</strong> why.
</p>

<!-- QUESTION TEMPLATE -->
<div class="card">
  <div class="question-title">1. Student Motivation Dashboard</div>
  <p>
    A school uses a dashboard that assigns each student a “motivation score”
    (0–100) based on attendance, homework completion, and punctuality.
    A teacher decides to give less attention to a specific student because
    his score is low, assuming he is “not interested in learning.”
    <br><br>
    Is the teacher confusing the map with the territory?
  </p>
  <label><input type="radio" name="q1" value="yes"> Yes</label><br>
  <label><input type="radio" name="q1" value="no"> No</label><br>
  <button onclick="checkQ(1)">Check</button>
  <div id="fb1" class="feedback"></div>
</div>

<div class="card">
  <div class="question-title">2. Business Experiment Results</div>
  <p>
    An entrepreneur tests two landing pages for Subito English. Page A gets
    8% sign-ups, Page B gets 10%. The entrepreneur concludes that Page B
    “is definitely better in all contexts” and therefore stops all further
    testing.
    <br><br>
    Is this a map–territory confusion?
  </p>
  <label><input type="radio" name="q2" value="yes"> Yes</label><br>
  <label><input type="radio" name="q2" value="no"> No</label><br>
  <button onclick="checkQ(2)">Check</button>
  <div id="fb2" class="feedback"></div>
</div>

<div class="card">
  <div class="question-title">3. Salary Benchmark Spreadsheet</div>
  <p>
    A consultant keeps a spreadsheet showing average hourly rates for similar
    professionals in Italy. When a client proposes a lower rate but also
    offers long-term collaboration and exposure, the consultant rejects it
    immediately because “the spreadsheet says the rate is too low.”
    <br><br>
    Is this a confusion between map and territory?
  </p>
  <label><input type="radio" name="q3" value="yes"> Yes</label><br>
  <label><input type="radio" name="q3" value="no"> No</label><br>
  <button onclick="checkQ(3)">Check</button>
  <div id="fb3" class="feedback"></div>
</div>

<div class="card">
  <div class="question-title">4. Investment Ratios</div>
  <p>
    An investor screens for value stocks using low P/E and P/B ratios.  
    After finding a company with low ratios, he reads the annual reports,
    listens to calls, and analyses industry conditions before deciding.
    <br><br>
    Is the investor confusing map and territory?
  </p>
  <label><input type="radio" name="q4" value="yes"> Yes</label><br>
  <label><input type="radio" name="q4" value="no"> No</label><br>
  <button onclick="checkQ(4)">Check</button>
  <div id="fb4" class="feedback"></div>
</div>

<div class="card">
  <div class="question-title">5. First Impressions in Partnerships</div>
  <p>
    You meet a potential HR partner at a trade fair.  
    The first conversation feels “cold,” so you tell yourself
    “this person is probably unhelpful” and avoid following up,
    even though trade fairs are stressful environments where people
    often behave differently than usual.
    <br><br>
    Is this a map–territory confusion?
  </p>
  <label><input type="radio" name="q5" value="yes"> Yes</label><br>
  <label><input type="radio" name="q5" value="no"> No</label><br>
  <button onclick="checkQ(5)">Check</button>
  <div id="fb5" class="feedback"></div>
</div>

<script>
  const answers = {
    1: "yes",
    2: "yes",
    3: "yes",
    4: "no",
    5: "yes"
  };

  const explanations = {
    1: {
      yes: "Correct! The dashboard score is a map — it measures only a small slice of reality. Low motivation score ≠ true motivation. It ignores home problems, learning styles, anxiety, or hidden effort.",
      no: "Incorrect. The motivation score is only a simplified model. It measures attendance, not interest, curiosity, or personal struggles. The teacher is treating a limited metric as the entire truth — classic map–territory error."
    },
    2: {
      yes: "Correct! A landing-page conversion rate is a map — a simplified snapshot of behaviour. It doesn’t prove that Page B will always win across seasons, audiences, channels, or sample sizes. The entrepreneur is overfitting the map.",
      no: "Incorrect. Conversion tests are maps, not full territory. The entrepreneur is assuming one small experiment captures all future behaviour — dangerous overgeneralisation."
    },
    3: {
      yes: "Correct! The spreadsheet shows typical market rates (map). But the real territory includes context: long-term relationships, referrals, stability, reputation, and future opportunities. Rejecting solely based on a map is incomplete thinking.",
      no: "Incorrect. The spreadsheet is a simplified representation. It doesn’t capture long-term strategic value. Treating it as absolute truth is a map–territory confusion."
    },
    4: {
      yes: "Incorrect. The investor uses ratios as a starting point — that’s a map — but then investigates real company behaviour (territory). This is the correct use of maps, not a confusion.",
      no: "Correct! Ratios are just screening tools. The investor checks the actual business afterwards, which means he is using maps wisely and validating them with reality."
    },
    5: {
      yes: "Correct. A first impression is a cognitive map — fast, simplified, often inaccurate. The real territory is how the person behaves when not stressed or rushed. Assuming the map is the territory is the error.",
      no: "Incorrect. First impressions are notorious low-quality maps. Trade fair behaviour is not representative territory. Avoiding follow-up based on that is exactly the confusion this model warns against."
    }
  };

  function checkQ(num) {
    const name = "q" + num;
    const radios = document.getElementsByName(name);
    let choice = null;

    for (const r of radios) {
      if (r.checked) choice = r.value;
    }

    const fb = document.getElementById("fb" + num);
    fb.style.display = "block";

    if (!choice) {
      fb.className = "feedback incorrect";
      fb.innerHTML = "Please select an answer.";
      return;
    }

    if (choice === answers[num]) {
      fb.className = "feedback correct";
      fb.innerHTML = explanations[num][choice];
    } else {
      fb.className = "feedback incorrect";
      fb.innerHTML = explanations[num][choice];
    }
  }
</script>

</body>
</html>
