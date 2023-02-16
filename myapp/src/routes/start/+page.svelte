<script>
    let email = '';
    let password = '';
    let error = '';
  
    async function login() {
      try {
        await login(email, password);
        // redirect to dashboard
      } catch (error) {
        console.error(error);
        error = 'Invalid email or password';
      }
    }
  </script>
  
  <style>
    .login-button {
      width: 320px;
      padding: 0px;
      background-color: #1e0202;
      border-radius: 8px;
      box-shadow: 0 0 10px rgba(90, 8, 185, 0.2);
    }
  
    .input {
      display: block;
      width: 100%;
      margin-bottom: 16px;
      padding: 8px;
      border: 1px solid #ccc;
      border-radius: 4px;
      font-size: 16px;
    }
  
    .error {
      color: #ff4136;
      margin-bottom: 16px;
      text-align: center;
    }
  
    .login-button {
      display: block;
      width: 100%;
      padding: 8px;
      border: none;
      border-radius: 4px;
      font-size: 16px;
      color: #fff;
      background-color: #0074d9;
      cursor: pointer;
      transition: background-color 0.2s;
    }
  
    .login-button:hover {
      background-color: #0062ac;
    }
  </style>
  
  <div class="login-form">
    <h2>Login here</h2>
    <input type="email" class="input" placeholder="Email" bind:value={email} />
    <input type="password" class="input" placeholder="Password" bind:value={password} />
    {#if error}
      <div class="error">{error}</div>
    {/if}
    <button class="login-button" on:click={login}>Login</button>
  </div>
  