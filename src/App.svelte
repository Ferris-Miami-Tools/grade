<script>
  let rq = '0';
  let hq = '0';
  let lab = '0';
  let python = '0';
  let sql = '0';
  let cc = '0';
  let result = undefined;
  const calculateGrade = () => {
    result = (0.1 * Number(rq)) + (0.05 * Number(hq)) + (0.1 * Number(lab)) + (0.325 * Number(python)) + (0.325 * Number(sql)) + (0.1 * Number(cc));
  };
</script>

<header>
  <h1>Grade Calculator</h1>
</header>

<main>
  <form on:submit|preventDefault={calculateGrade}>
    <label for="rq">
      Reading Quizzes:
      <input type="text" bind:value={rq} required name="rq" id="rq" inputmode="numeric" pattern="[0-9]*.[0-9]*" />
    </label>
    <label for="hq">
      Homework Quizzes:
      <input type="text" bind:value={hq} required name="hq" id="hq" inputmode="numeric" pattern="[0-9]*.[0-9]*" />
    </label>
    <label for="lab">
      Lab Exercises:
      <input type="text" bind:value={lab} required name="lab" id="lab" inputmode="numeric" pattern="[0-9]*.[0-9]*" />
    </label>
    <label for="python">
      Python Exam:
      <input type="text" bind:value={python} required name="python" id="python" inputmode="numeric" pattern="[0-9]*.[0-9]*" />
    </label>
    <label for="sql">
      SQL Exam:
      <input type="text" bind:value={sql} required name="sql" id="sql" inputmode="numeric" pattern="[0-9]*.[0-9]*" />
    </label>
    <label for="cc">
      Client Challenge:
      <input type="text" bind:value={cc} required name="cc" id="cc" inputmode="numeric" pattern="[0-9]*.[0-9]*" />
    </label>
    <button>Calculate Final Grade</button>
    {#if typeof(result) !== "undefined"}
      <output name="result" for="rq hq lab python sql cc">Final Grade: {Math.round(result)}%</output>
    {/if}
  </form>
</main>

<footer>
  <p>Made with 💜 by Joshua Ferris</p>
</footer>

<style>
  h1 {
    font-size: 3.2em;
    line-height: 1.1;
  }

  main {
    padding: 1em;
  }

  form {
    text-align: left;
    display: flex;
    flex-direction: column;
    gap: 1em;
  }

  label {
    display: block;
    cursor: pointer;
    width: 100%;
  }

  input {
    width: 100%;
    margin-top: 0.5em;
    padding: 0.5em .75em;
    vertical-align: middle;
    border: 1px solid #e1e4e8;
    border-radius: 0.75em;
    outline: none;
  }

  button {
    width: 100%;
    padding: 0.6em 1.2em;
    font-size: 1em;
    font-weight: 700;
    font-family: inherit;
    border-radius: 1em;
    border: 1px solid transparent;
    background-color: #f9f9f9;
    cursor: pointer;
    transition: border-color 0.25s;
  }

  button:hover {
    border-color: #646cff;
  }

  button:focus, button:focus-visible {
    outline: 4px auto -webkit-focus-ring-color;
  }

  output {
    font-size: 1.5em;
    font-weight: 700;
    text-align: center;
  }

  footer {
    text-align: center;
  }

  @media (prefers-color-scheme: dark) {
    button {
      background-color: #1a1a1a;
    }
  }
</style>
