<script>
    let email = '';
    let password = '';
  
    function handleLogin() {
      // handle login
    }
  </script>
  
  <style>
    .login-page {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
  
    .login-form {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      width: 500px;
      padding: 100px;
      background-color: #170537;
      border-radius: 80px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
    }
  
    .input {
      display: block;
      width: 100%;
      margin-bottom: 25px;
      padding: 10px;
      border: 1px solid #5f09a1;
      border-radius: 40px;
      font-size: 25px;
    }
  
    .login-button {
      display: block;
      width: 100%;
      padding: 8px;
      border: none;
      border-radius: 4px;
      font-size: 16px;
      color: #0c0c00;
      background-color: #020346;
      cursor: pointer;
      transition: background-color 0.2s;
    }
  
    .login-button:hover {
      background-color: #900b85;
    }
  </style>
  
  <div class="login-page">
    <div class="login-form">
      <h2>Login</h2>
      <input type="email" class="input" placeholder="Email" bind:value={email} />
      <input type="password" class="input" placeholder="Password" bind:value={password} />
      <button class="login-button" on:click={handleLogin}>Login</button>
    </div>
 
  </div>
  
 