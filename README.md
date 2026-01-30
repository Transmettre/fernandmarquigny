# fernandmarquigny

<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Audioguide de la ville</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 20px;
    }

    .container {
      background: white;
      border-radius: 20px;
      box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
      padding: 60px 50px;
      max-width: 500px;
      width: 100%;
      text-align: center;
    }

    .icon {
      font-size: 64px;
      margin-bottom: 30px;
    }

    h1 {
      color: #2d3748;
      font-size: 28px;
      font-weight: 600;
      margin-bottom: 15px;
      line-height: 1.4;
    }

    .subtitle {
      color: #718096;
      font-size: 16px;
      margin-bottom: 40px;
    }

    .select-wrapper {
      position: relative;
      margin-bottom: 30px;
    }

    select {
      width: 100%;
      padding: 16px 20px;
      font-size: 16px;
      border: 2px solid #e2e8f0;
      border-radius: 12px;
      background-color: #f7fafc;
      color: #2d3748;
      cursor: pointer;
      transition: all 0.3s ease;
      appearance: none;
      font-weight: 500;
    }

    select:hover {
      border-color: #667eea;
      background-color: #fff;
    }

    select:focus {
      outline: none;
      border-color: #667eea;
      background-color: #fff;
      box-shadow: 0 0 0 3px rgba(102, 126, 234, 0.1);
    }

    .select-wrapper::after {
      content: '▼';
      position: absolute;
      right: 20px;
      top: 50%;
      transform: translateY(-50%);
      pointer-events: none;
      color: #667eea;
      font-size: 12px;
    }

    .btn {
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      color: white;
      border: none;
      padding: 16px 40px;
      font-size: 16px;
      font-weight: 600;
      border-radius: 12px;
      cursor: pointer;
      transition: all 0.3s ease;
      box-shadow: 0 4px 15px rgba(102, 126, 234, 0.4);
    }

    .btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 6px 20px rgba(102, 126, 234, 0.5);
    }

    .btn:active {
      transform: translateY(0);
    }

    .footer {
      margin-top: 30px;
      color: #a0aec0;
      font-size: 14px;
    }

    @media (max-width: 600px) {
      .container {
        padding: 40px 30px;
      }

      h1 {
        font-size: 24px;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="icon">🎧</div>
    
    <h1>Bienvenue sur l'audioguide</h1>
    <p class="subtitle">Choisissez votre langue pour commencer</p>
    
    <div class="select-wrapper">
      <select id="languageSelect">
        <option value="">Sélectionnez une langue</option>
        <option value="fr">🇫🇷 Français</option>
        <option value="en">🇬🇧 English</option>
        <option value="es">🇪🇸 Español</option>
        <option value="de">🇩🇪 Deutsch</option>
        <option value="it">🇮🇹 Italiano</option>
      </select>
    </div>
    
    <button class="btn" onclick="startTour()">Commencer la visite</button>
    
    <div class="footer">
      Profitez de votre visite guidée
    </div>
  </div>

  <script>
    function startTour() {
      const language = document.getElementById('languageSelect').value;
      
      if (!language) {
        alert('Veuillez sélectionner une langue / Please select a language');
        return;
      }
      
      // Ici vous pouvez rediriger vers la page de visite correspondante
      alert('Démarrage de la visite en ' + document.getElementById('languageSelect').selectedOptions[0].text);
      // window.location.href = 'tour-' + language + '.html';
    }

    // Permettre de démarrer avec la touche Entrée
    document.getElementById('languageSelect').addEventListener('keypress', function(e) {
      if (e.key === 'Enter') {
        startTour();
      }
    });
  </script>
</body>
</html>
