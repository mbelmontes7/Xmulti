<script>
    let score = 0;
    let answer = '';
    let seconds = 30;
    let timeLeft = true;
    let highScore = localStorage.getItem('multiplication_game_high_score') || 0;
  
    const generateQuestion = () => {
      const num1 = Math.floor(Math.random() * 10) + 1;
      const num2 = Math.floor(Math.random() * 10) + 1;
      return `${num1} x ${num2}`;
    };
  
    let question = generateQuestion();
  
    const checkAnswer = () => {
      const [num1, num2] = question.split('x').map((str) => parseInt(str.trim()));
      const correctAnswer = num1 * num2;
      if (parseInt(answer) === correctAnswer) {
        score += 1;
        question = generateQuestion();
        answer = '';
      } else {
        answer = '';
      }
    };
  
    const countdown = setInterval(() => {
      if (timeLeft) {
        seconds--;
        if (seconds <= 0) {
          clearInterval(countdown);
          timeLeft = false;
          if (score > highScore) {
            highScore = score;
            localStorage.setItem('multiplication_game_high_score', highScore);
          }
        }
      }
    }, 1000);
  </script>
  
  <h1>Multiplication Game</h1>
  
  {#if timeLeft}
    <h2>Score: {score} High Score: {highScore} Time Left: {seconds}</h2>
    <h3>What is {question}?</h3>
  
    <input type="text" bind:value={answer} on:keydown={(e) => { if (e.key === 'Enter') checkAnswer() }} />
  
    <button on:click={checkAnswer}>Submit</button>
  {:else}
    <h2>Game Over</h2>
    <h3>Your Score: {score} High Score: {highScore}</h3>
    <button on:click={() => {seconds = 30; score = 0; question = generateQuestion(); timeLeft = true;}}>Play Again</button>
  {/if}
  <style>
    
  </style>
  