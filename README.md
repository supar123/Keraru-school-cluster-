
<html lang="om">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>Keraru School Cluster — Login</title>

  <!-- Supabase JS -->
  <script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: Arial, sans-serif;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #073b66, #1683b8);
      padding: 20px;
    }

    .login-box {
      width: 100%;
      max-width: 430px;
      background: white;
      border-radius: 20px;
      padding: 30px;
      box-shadow: 0 15px 40px rgba(0,0,0,0.25);
    }

    .logo {
      width: 80px;
      height: 80px;
      margin: 0 auto 15px;
      border-radius: 50%;
      background: #073b66;
      color: white;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 32px;
      font-weight: bold;
    }

    h1 {
      text-align: center;
      color: #073b66;
      font-size: 26px;
      margin-bottom: 8px;
    }

    .subtitle {
      text-align: center;
      color: #666;
      margin-bottom: 25px;
      line-height: 1.5;
    }

    label {
      display: block;
      margin-bottom: 7px;
      font-weight: bold;
      color: #333;
    }

    input {
      width: 100%;
      padding: 13px;
      border: 1px solid #ccc;
      border-radius: 10px;
      margin-bottom: 17px;
      font-size: 16px;
      outline: none;
    }

    input:focus {
      border-color: #1683b8;
      box-shadow: 0 0 0 3px rgba(22,131,184,0.12);
    }

    button {
      width: 100%;
      border: none;
      padding: 14px;
      border-radius: 10px;
      background: #073b66;
      color: white;
      font-size: 16px;
      font-weight: bold;
      cursor: pointer;
      margin-top: 5px;
    }

    button:hover {
      background: #1683b8;
    }

    button:disabled {
      opacity: 0.6;
      cursor: not-allowed;
    }

    .forgot {
      display: block;
      text-align: right;
      margin: -5px 0 15px;
      color: #1683b8;
      cursor: pointer;
      font-size: 14px;
    }

    .message {
      display: none;
      padding: 12px;
      margin-bottom: 15px;
      border-radius: 8px;
      line-height: 1.5;
      font-size: 14px;
    }

    .success {
      display: block;
      background: #e8f7ee;
      color: 
    .footer {
      text-align: center;
      margin-top: 25px;
      color: #777;
      font-size: 13px;
      line-height: 1.6;
    }

    @media (max-width: 480px) {
      .login-box {
        padding: 23px;
      }

      h1 {
        font-size: 23px;
      }
    }
  </style>
</head>

<body>

  <div class="login-box">

    <div class="logo">K</div>

    <h1>Keraru School Cluster</h1>

    <p class="subtitle">
      Sirna Hordoffii fi To'annoo<br>
      Manneen Barnootaa
    </p>

    <div id="message" class="message"></div>

    <!-- LOGIN FORM -->
    <form id="loginForm">

      <label for="email">Email</label>
      <input
        type="email"
        id="email"
        placeholder="Email keessan galchaa"
        required
        autocomplete="email"
      >

      <label for="password">Password</label>
      <input
        type="password"
        id="password"
        placeholder="Password keessan galchaa"
        required
        autocomplete="current-password"
      >

      <span class="forgot" id="forgotPassword">
        Password irraanfattee?
      </span>

      <button type="submit" id="loginButton">
        🔐 Seeni
      </button>

    </form>

    <div class="footer">
      Godina Harargee Lixaa — Aanaa Doobbaa<br>
      Keraru / Qaraaruu School Cluster
    </div>

  </div>


<script>
  /* =====================================================
     SUPABASE CONFIGURATION
     ===================================================== */

  const SUPABASE_URL =
    "https://blwpuiannyditjsaghdn.supabase.co";

  const SUPABASE_KEY =
    "sb_publishable_hJanJxqPXpTnFv-GTtjNWg_ITFJe-D7";

  const supabaseClient =
    window.supabase.createClient(
      SUPABASE_URL,
      

  /* =====================================================
     MESSAGE FUNCTION
     
    message.textContent = text;

    message.className =
      "message aseClient.auth.getSession();

    if (session) {

      window.location.href =
        "dashboard.html";

    }

  }

  loginForm.addEventListener(
    
      event.preventDefault();

      co
        document.getElementById("password").value;

      if (!email || !password) {

        showMessage(
          "Email fi Password guutaa.",
          "error"
        


      loginButton.disabled = true;

      loginButton.textContent =
        "Seenaa jira...";


      co
        data,
        error
      } =t supabaseClient.auth.signInWithPassword({
        email: email,
        password: password
    
          "Login hin mil
        r
      


      if (data.session) {

        showMessage(
          "Milkaa'eera! Dashboarditti ce'aa...",
          "success"
        );

        setTimeout(f {

          window.location.href =
            "dashboard.html";

        }, 700);

      }

    }
  );



    
        document.getElementById("email").value.trim();


      if (!email) {

        showMessage(
          "Jalqaba Email keessan 
      } = await supabaseClient.auth.resetPasswordForEmail(
        email,
        {
          redirectTo:
            window.location.origin +
            window.location.pathname.replace(
              "index.html",qQqqq
      }


      showMessage(
        "Link haaromsaa Password email keessanitti ergameera.",
        "success"
      );

    
        event === "SIGNED_IN" &&
        session
      ) {

        window.location.href =
          "dashboard.html";

      }

    }
  );

</script>

</body>
</html>
