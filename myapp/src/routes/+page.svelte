<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
<script>
    let result = 0;
    let num1 = 0;
    let num2 = 0;
    let operator = "";
    
    function calculate() {
      switch (operator) {
        case "+":
          result = num1 + num2;
          break;
        case "-":
          result = num1 - num2;
          break;
        case "*":
          result = num1 * num2;
          break;
        case "/":
          result = num1 / num2;
          break;
        case "x²":
          result = num1 * num1;
          break;
        default:
          result = 0;
      }
    }
  </script>
  
  <style>
    h1 {
      text-align: center;
    }
    
    .container {
      display: flex;
      flex-direction: column;
      align-items: center;
      margin-top: 50px;
    }
    
    .row {
      display: flex;
      justify-content: center;
      margin-bottom: 20px;
    }
    
    button {
      padding: 10px 20px;
      font-size: 24px;
      margin: 0 10px;
      cursor: pointer;
    }
    
    input {
      padding: 10px;
      font-size: 24px;
      text-align: right;
    }
  </style>
  
  <div class="container">
    <h1>Svelte Calculator</h1>
        <div class="row">
            <input type="number" bind:value={result} readonly />
        </div>
    <div class="row">    
      <input type="number" bind:value={num1} />
      <button on:click={() => operator = "+"}>+</button>
      <button on:click={() => operator = "-"}>-</button>
      <button on:click={() => operator = "*"}>*</button>
      <button on:click={() => operator = "/"}>/</button>
      <button on:click={() => operator = "x²"}>x²</button>
      <input type="number" bind:value={num2} />
      <button on:click={calculate}>=</button>
    </div>
  </div>