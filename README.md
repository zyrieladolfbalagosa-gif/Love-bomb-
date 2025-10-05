<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Love Calculator</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #fff0f5;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    .calculator, .lyrics {
      background: #ffffff;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.2);
      width: 300px;
      text-align: center;
    }

    #display {
      width: 100%;
      height: 50px;
      font-size: 24px;
      margin-bottom: 10px;
      padding: 10px;
      text-align: right;
      border: 1px solid #ccc;
      border-radius: 5px;
    }

    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }

    button {
      padding: 15px;
      font-size: 18px;
      background-color: #f06292;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }

    button:hover {
      background-color: #ec407a;
    }

    .lyrics h2 {
      color: #d81b60;
    }

    .lyrics p {
      white-space: pre-line;
      color: #4a148c;
      font-size: 16px;
      margin-top: 15px;
    }
  </style>
</head>
<body>

  <!-- Calculator UI -->
  <div class="calculator" id="calculator">
    <input type="text" id="display" disabled>
    <div class="buttons">
      <button onclick="press('7')">7</button>
      <button onclick="press('8')">8</button>
      <button onclick="press('9')">9</button>
      <button onclick="press('/')">/</button>
      
      <button onclick="press('4')">4</button>
      <button onclick="press('5')">5</button>
      <button onclick="press('6')">6</button>
      <button onclick="press('*')">*</button>
      
      <button onclick="press('1')">1</button>
      <button onclick="press('2')">2</button>
      <button onclick="press('3')">3</button>
      <button onclick="press('-')">-</button>
      
      <button onclick="press('0')">0</button>
      <button onclick="press('.')">.</button>
      <button onclick="calculate()">=</button>
      <button onclick="press('+')">+</button>

      <button onclick="clearDisplay()" style="grid-column: span 4; background-color: #b0bec5;">C</button>
    </div>
  </div>

  <!-- Lyrics Section (hidden initially) -->
  <div class="lyrics" id="lyrics" style="display: none;">
    <h2>🎶 Pwede Bang Tayo Na Lang? 🎶</h2>
    <p>
Pwede bang tayo na lang?<br>
Kahit sa panaginip lang<br>
Sa dami ng tao sa mundo<br>
Ikaw lang ang gusto ko<br><br>

Sana'y maramdaman mo rin<br>
Ang tibok nitong damdamin<br>
Di ko na kayang itago pa<br>
Ang pag-ibig kong para sa'yo sinta 💖
    </p>
  </div>

  <script>
    let display = document.getElementById('display');

    function press(val) {
      display.value += val;
    }

    function clearDisplay() {
      display.value = '';
    }

    function calculate() {
      if (display.value === '123') {
        document.getElementById('calculator').style.display = 'none';
        document.getElementById('lyrics').style.display = 'block';
      } else {
        try {
          display.value = eval(display.value);
        } catch {
          display.value = 'Error';
        }
      }
    }
  </script>

</body>
</html>
