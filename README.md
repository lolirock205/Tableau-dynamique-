<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Générateur de Table de Multiplication</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 20px;
      background : deeppink;
    }
    table {
      border-collapse: collapse;
      margin-top: 20px;
    }
    td, th {
      border: 1px solid black;
      padding: 8px;
      text-align: center;
      background : orange;
    }
    input, button {
      padding: 5px;
      margin: 5px;
    }
  </style>
</head>
<body>
  <h2> Table de Multiplication dynamique</h2>

  <label>Entrer un nombre :
    <input type="number" id="nombre" placeholder="" min="1">
  </label>
  <button onclick="genererTable()">Afficher la table</button>

  <div id="résultat"></div>
  <script>
    function genererTable() {
      const n = parseInt(document.getElementById("nombre").value);
      const conteneur = document.getElementById("résultat");

      if (isNaN(n)) {
        conteneur.innerHTML = "<p>Veuillez entrer un nombre valide.</p>";
        return;
      }

      let html = "<table><tr><th>Multiplication</th><th>résultat</th></tr>";
      for (let i = 1; i <= 10; i++) {
        html += `<tr><td>${n} × ${i}</td><td>${n * i}</td></tr>`;
      }
      html += "</table>";
      conteneur.innerHTML = html;
    }
  </script>
</body>
</html>
