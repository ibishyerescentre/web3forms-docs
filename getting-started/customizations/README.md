<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="utf-8">
<title>Inscription</title>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
  body {
    font-family: Arial, sans-serif;
    background: #f2f2f7;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
  }
  .card {
    background: white;
    width: 360px;
    padding: 32px;
    border-radius: 14px;
    box-shadow: 0 6px 20px rgba(0,0,0,0.1);
    text-align: center;
  }
  .langs a {
    margin: 0 4px;
    cursor: pointer;
    color: #0062ff;
    font-weight: bold;
    text-decoration: none;
  }
  h2 { margin-bottom: 10px; }
  p { margin-bottom: 20px; color: #444; }
  input {
    width: 100%;
    padding: 12px;
    border: 1px solid #cdd3da;
    border-radius: 8px;
    margin-bottom: 15px;
    font-size: 15px;
  }
  button {
    width: 100%;
    padding: 13px;
    background: #0062ff;
    color: white;
    border: none;
    border-radius: 10px;
    font-size: 15px;
    cursor: pointer;
  }
  button:hover { background: #004fcc; }
</style>
</head>
<body>

<div class="card">

  <!-- Sélecteur de langue -->
  <div class="langs">
    <a onclick="setLang('fr')">FR</a> |
    <a onclick="setLang('en')">EN</a> |
    <a onclick="setLang('es')">ES</a> |
    <a onclick="setLang('cn')">中文</a> |
    <a onclick="setLang('it')">IT</a>
  </div>

  <h2 id="title">Pas encore membre ?</h2>
  <p id="subtitle">Réservez au meilleur prix en vous inscrivant gratuitement :</p>

  <form action="https://formsubmit.co/ibishyerescentre@proton.me" method="POST">

    <input type="hidden" name="_captcha" value="false">
    <input type="hidden" name="_next" value="https://google.com">

    <input type="email" name="email" id="email" placeholder="Adresse e-mail" required>

    <button type="submit" id="btn">M’inscrire gratuitement</button>
  </form>

</div>

<script>
function setLang(lang) {
  const texts = {
    fr: {
      title: "Pas encore membre ?",
      subtitle: "Réservez au meilleur prix en vous inscrivant gratuitement :",
      email: "Adresse e-mail",
      btn: "M’inscrire gratuitement"
    },
    en: {
      title: "Not a member yet?",
      subtitle: "Book at the best price by signing up for free:",
      email: "Email address",
      btn: "Sign up for free"
    },
    es: {
      title: "¿Aún no eres miembro?",
      subtitle: "Reserva al mejor precio registrándote gratis:",
      email: "Correo electrónico",
      btn: "Registrarme gratis"
    },
    cn: {
      title: "还不是会员？",
      subtitle: "免费注册即可享受最优惠价格：",
      email: "电子邮件",
      btn: "免费注册"
    },
    it: {
      title: "Non sei ancora membro?",
      subtitle: "Prenota al miglior prezzo iscrivendoti gratuitamente:",
      email: "Indirizzo email",
      btn: "Iscriviti gratis"
    }
  };

  document.getElementById('title').innerText = texts[lang].title;
  document.getElementById('subtitle').innerText = texts[lang].subtitle;
  document.getElementById('email').placeholder = texts[lang].email;
  document.getElementById('btn').innerText = texts[lang].btn;

  document.documentElement.lang = lang;
}
</script>

</body>
</html>
