
<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Peoplerecorder.com - Vigilância Oculta</title>
<style>
  body {
    background: #111;
    color: #eee;
    font-family: Arial, sans-serif;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 20px;
  }
  h1 {
    margin-bottom: 20px;
  }
  #inputSection {
    margin-bottom: 20px;
  }
  input[type="text"] {
    font-size: 1rem;
    padding: 8px;
    width: 300px;
  }
  button {
    font-size: 1rem;
    padding: 8px 16px;
    margin-left: 10px;
    cursor: pointer;
  }
  #videoWrapper {
    position: relative;
    width: 640px;
    height: 360px;
    border: 2px solid #333;
    background: black;
    display: none;
  }
  video {
    width: 100%;
    height: 100%;
  }
  #entity {
    position: absolute;
    width: 80px;
    height: 80px;
    background: rgba(0,0,0,0.7);
    border-radius: 12px;
    box-shadow: 0 0 15px 3px rgba(0,0,0,0.9);
    top: 100px;
    left: 400px;
    opacity: 0;
    transition: opacity 1s ease-in-out;
  }
  /* camera lens detail */
  #entity::before {
    content: "";
    position: absolute;
    top: 20px;
    left: 25px;
    width: 30px;
    height: 30px;
    border-radius: 50%;
    background: radial-gradient(circle at center, #444, #000);
    box-shadow: inset 0 0 10px #222;
  }
</style>
</head>
<body>
<h1>Peoplerecorder.com</h1>
<div id="inputSection">
  <input type="text" id="locationInput" placeholder="Digite a localização para ver a câmera" />
  <button onclick="mostrarVideo()">Ver Câmera</button>
</div>
<div id="videoWrapper">
  <video id="cameraVideo" src="https://interactive-examples.mdn.mozilla.net/media/cc0-videos/flower.webm" controls autoplay muted loop></video>
  <div id="entity"></div>
</div>

<script>
  function mostrarVideo() {
    const loc = document.getElementById("locationInput").value.trim();
    if (loc === "") {
      alert("Por favor, digite uma localização.");
      return;
    }

    // Aqui você pode adicionar lógica para diferentes locais, mas por enquanto é fixo
    document.getElementById("videoWrapper").style.display = "block";

    // Mostrar e esconder a entidade com efeito de desaparecimento para criar desconforto
    const entity = document.getElementById("entity");
    let visible = false;
    setInterval(() => {
      visible = !visible;
      entity.style.opacity = visible ? "0.6" : "0";
    }, 3000);
  }
</script>
</body>
</html>
