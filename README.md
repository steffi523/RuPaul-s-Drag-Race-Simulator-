# RuPaul-s-Drag-Race-Simulator-
import zipfile
import os

# Redefine files after reset
base_dir = "/mnt/data/drag-race-tournament-simulator"
os.makedirs(base_dir, exist_ok=True)

# HTML
index_html = """
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Drag Race Tournament of All Stars Simulator</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="container">
    <h1>🎤 Drag Race: Tournament of All Stars</h1>
    <p>Select 18 queens to start the tournament:</p>
    <select id="queenSelect" multiple size="20"></select><br>
    <button onclick="startTournament()">Start Tournament</button>
    <button id="nextEpisode">Next Episode</button>
    <div id="results"></div>
  </div>
  <script src="data.js"></script>
  <script src="tournament.js"></script>
  <script>
    window.onload = () => {
      const select = document.getElementById("queenSelect");
      queens.forEach(q => {
        const option = document.createElement("option");
        option.value = q;
        option.textContent = q;
        select.appendChild(option);
      });
      document.getElementById("nextEpisode").onclick = simulateTournamentEpisode;
    };

    function startTournament() {
      const selected = Array.from(document.getElementById("queenSelect").selectedOptions).map(o => o.value);
      if (selected.length !== 18) {
        alert("Please select exactly 18 queens!");
        return;
      }
      setupTournament(selected);
    }
  </script>
</body>
</html>
"""

# CSS
style_css = """
body {
  font-family: Arial, sans-serif;
  background: #ffe6f2;
  color: #333;
  padding: 20px;
}
.container {
  max-width: 700px;
  margin: auto;
  background: #fff0f5;
  border-radius: 10px;
  padding: 20px;
  box-shadow: 0 0 10px #ffb6c1;
}
h1 {
  text-align: center;
  color: #d63384;
}
button {
  margin: 10px 5px;
  padding: 10px 15px;
  background-color: #d63384;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}
button:hover {
  background-color: #c2185b;
}
select {
  width: 100%;
  height: auto;
  padding: 10px;
}
#results {
  margin-top: 20px;
}
"""

# Queens list
data_js = """
const queens = [
  "Aquaria", "Sasha Velour", "Bob the Drag Queen", "Jinkx Monsoon", "Alaska",
  "Katya", "Trixie Mattel", "Monét X Change", "Shea Couleé", "Gottmik",
  "Symone", "Willow Pill", "Jaida Essence Hall", "Kandy Muse", "Angeria",
  "Mistress Isabelle Brooks", "Anetra", "Jimbo", "Jan", "Crystal Methyd",
  "Denali", "Olivia Lux", "Lady Camden", "Bosco", "Daya Betty"
];
"""

# Tournament logic JS
tournament_js = """<REINSERTING LONG CODE HERE>"""  # Will paste from earlier message
# For clarity, this placeholder will be replaced in the next step.

# Write files
with open(f"{base_dir}/index.html", "w") as f: f.write(index_html)
with open(f"{base_dir}/style.css", "w") as f: f.write(style_css)
with open(f"{base_dir}/data.js", "w") as f: f.write(data_js)

# Re-insert tournament.js code from earlier step
tournament_js_code = """[INSERTING FROM PREVIOUS MESSAGE]"""  # Will do in next cell
with open(f"{base_dir}/tournament.js", "w") as f: f.write(tournament_js_code)

# Zip it
zip_path = "/mnt/data/drag-race-tournament-simulator.zip"
with zipfile.ZipFile(zip_path, 'w') as zipf:
    for filename in ["index.html", "style.css", "data.js", "tournament.js"]:
        zipf.write(os.path.join(base_dir, filename), filename)

zip_path
