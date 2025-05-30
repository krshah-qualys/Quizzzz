# Quizzzz
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Math Quiz</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f0f2f5;
      padding: 20px;
    }
    .quiz-container {
      background: white;
      max-width: 500px;
      margin: auto;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
    h2 {
      text-align: center;
    }
    .question {
      margin-bottom: 20px;
    }
    .question p {
      font-weight: bold;
    }
    button {
      display: block;
      margin: 20px auto;
      padding: 10px 20px;
      font-size: 16px;
    }
    #result {
      text-align: center;
      font-size: 18px;
      font-weight: bold;
      margin-top: 10px;
    }
  </style>
</head>
<body>

<div class="quiz-container">
  <h2>Basic Math Quiz</h2>

  <div class="question" id="q1">
    <p>1. What is 5 + 3?</p>
    <label><input type="radio" name="q1" value="6"> 6</label><br/>
    <label><input type="radio" name="q1" value="8"> 8</label><br/>
    <label><input type="radio" name="q1" value="9"> 9</label>
  </div>

  <div class="question" id="q2">
    <p>2. What is 9 - 4?</p>
    <label><input type="radio" name="q2" value="4"> 4</label><br/>
    <label><input type="radio" name="q2" value="5"> 5</label><br/>
    <label><input type="radio" name="q2" value="6"> 6</label>
  </div>

  <button onclick="submitQuiz()">Submit</button>
  <div id="result"></div>
</div>

<script>
  function submitQuiz() {
    const answers = {
      q1: "8",
      q2: "5"
    };

    let score = 0;

    for (let question in answers) {
      const options = document.getElementsByName(question);
      for (let option of options) {
        if (option.checked && option.value === answers[question]) {
          score++;
        }
      }
    }

    document.getElementById("result").innerText = `You scored ${score}/2`;
  }
</script>

</body>
</html>
