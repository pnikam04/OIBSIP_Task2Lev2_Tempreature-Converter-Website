# OIBSIP_Task2Lev2_Tempreature-Converter-Website
I Developed this  Temperature Converter Website using HTML &amp; CSS , JAVA SCRIPT
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Temperature Converter</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        margin: 0;
        background-color: #f0f0f0;
      }

      .container {
        text-align: center;
        background: #fff;
        padding: 20px;
        border-radius: 10px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
      }

      .converter {
        margin-top: 20px;
      }

      #temperatureInput {
        padding: 10px;
        width: 200px;
        margin-bottom: 20px;
        border: 1px solid #ddd;
        border-radius: 5px;
      }

      .options {
        margin-bottom: 20px;
      }

      .options input {
        margin-right: 10px;
      }

      button {
        padding: 10px 20px;
        background-color: #007bff;
        color: #fff;
        border: none;
        border-radius: 5px;
        cursor: pointer;
      }

      button:hover {
        background-color: #0056b3;
      }

      #result {
        margin-top: 20px;
        font-size: 1.2em;
        color: #333;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <h1>Temperature Converter</h1>
      <div class="converter">
        <input
          type="text"
          id="temperatureInput"
          placeholder="Enter temperature"
        />
        <div class="options">
          <input
            type="radio"
            id="celsius"
            name="unit"
            value="celsius"
            checked
          />
          <label for="celsius">Celsius</label>
          <input type="radio" id="fahrenheit" name="unit" value="fahrenheit" />
          <label for="fahrenheit">Fahrenheit</label>
          <input type="radio" id="kelvin" name="unit" value="kelvin" />
          <label for="kelvin">Kelvin</label>
        </div>
        <button onclick="convertTemperature()">Convert</button>
        <div id="result"></div>
      </div>
    </div>
    <script>
      function convertTemperature() {
        const tempInput = document.getElementById("temperatureInput").value;
        const selectedUnit = document.querySelector(
          'input[name="unit"]:checked'
        ).value;
        const resultDiv = document.getElementById("result");

        if (isNaN(tempInput)) {
          resultDiv.textContent = "Please enter a valid number.";
          return;
        }

        const temperature = parseFloat(tempInput);
        let result = "";

        if (selectedUnit === "celsius") {
          result = `Fahrenheit: ${((temperature * 9) / 5 + 32).toFixed(
            2
          )} °F | Kelvin: ${(temperature + 273.15).toFixed(2)} K`;
        } else if (selectedUnit === "fahrenheit") {
          result = `Celsius: ${(((temperature - 32) * 5) / 9).toFixed(
            2
          )} °C | Kelvin: ${(((temperature - 32) * 5) / 9 + 273.15).toFixed(
            2
          )} K`;
        } else if (selectedUnit === "kelvin") {
          result = `Celsius: ${(temperature - 273.15).toFixed(
            2
          )} °C | Fahrenheit: ${(((temperature - 273.15) * 9) / 5 + 32).toFixed(
            2
          )} °F`;
        }

        resultDiv.textContent = result;
      }
    </script>
  </body>
</html>
