<!DOCTYPE html>
<html lang="ca">
<head>
  <meta charset="UTF-8">
  <title>Mapa interactiu de ciutats mexicanes amb noms indígenes</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.7.1/dist/leaflet.css" />
  <style>
    #mapa { height: 100vh; }
  </style>
</head>
<body>
  <div id="mapa"></div>
  
  <script src="https://unpkg.com/leaflet@1.7.1/dist/leaflet.js"></script>
  <script>
    const mapa = L.map('mapa').setView([23.6345, -102.5528], 5); // Centre aproximat de Mèxic

    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
      attribution: 'Mapa: &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a>'
    }).addTo(mapa);

    const ciutats = [
      { nom: "Mexico-Tenochtitlán", coords: [19.4326, -99.1332], significat: "Lloc del déu Mexi + ciutat de la tunera de pedra" },
      { nom: "Cuernavaca (Cuauhnáhuac)", coords: [18.9242, -99.2216], significat: "Prop del bosc" },
      { nom: "Xochimilco", coords: [19.2620, -99.1026], significat: "Camp de flors" },
      { nom: "Tlaxcala", coords: [19.3139, -98.2400], significat: "Lloc de les tortillas" },
      { nom: "Teotihuacán", coords: [19.6925, -98.8434], significat: "Lloc on els homes es converteixen en déus" },
      { nom: "Oaxaca", coords: [17.0732, -96.7266], significat: "Lloc dels huajes (derivat zapotec)" },
      { nom: "Tuxtla Gutiérrez", coords: [16.7529, -93.1169], significat: "Lloc dels conills" },
      { nom: "Texcoco", coords: [19.5155, -98.8796], significat: "A la vora de l’aigua pedregosa" },
      { nom: "Zacatecas", coords: [22.7709, -102.5832], significat: "Gent de l’herba" },
      { nom: "Chetumal", coords: [18.5001, -88.2962], significat: "Lloc on es recull aigua del plàtan (maia)" }
    ];

    ciutats.forEach(ciutat => {
      L.marker(ciutat.coords).addTo(mapa)
        .bindPopup(`<b>${ciutat.nom}</b><br>${ciutat.significat}`);
    });
  </script>
</body>
</html>
