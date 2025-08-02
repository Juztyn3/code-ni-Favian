

11:59 PM
You sent
<!DOCTYPE html>
<html lang="en">
<head>
  <meta name="google-site-verification" content="DwYFvllQckka1741Br1QlGlTPy0-sFLHFDzJ-nQrnIc" />
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Surprise Box</title>
  <style>
    * { box-sizing: border-box; }

    body {
      margin: 0;
      height: 100vh;
      background: #fff0f5;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      font-family: Arial, sans-serif;
    }

    .box-wrapper {
      position: relative;
      width: 220px;
      height: 220px;
      display: flex;
      align-items: flex-end;
      justify-content: center;
    }

    .box-body {
      width: 100%;
      height: 100%;
      background: #ff4d6d;
      border: 4px solid #d73757;
      border-radius: 10px;
      position: relative;
      z-index: 1;
    }

    .box-lid {
      position: absolute;
      width: 100%;
      height: 40px;
      background: #ff6b81;
      top: 0;
      left: 0;
      border-radius: 10px 10px 0 0;
      border: 4px solid #d73757;
      z-index: 2;
      transition: top 0.5s ease;
    }

    .box-lid.open {
      top: -100px;
    }

    .video-container {
      position: absolute;
      top: -200px;
      width: 220px;
      background: white;
      padding: 10px;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
      opacity: 0;
      transform: translateY(30px);
      transition: all 0.5s ease;
      z-index: 3;
    }

    .video-container.show {
      opacity: 1;
      transform: translateY(0);
    }

    video {
      width: 100%;
      height: 130px;
      object-fit: cover;
      border-radius: 8px;
    }

    .buttons {
      margin-top: 30px;
    }

    button {
      padding: 10px 20px;
      margin: 0 10px;
      background: #ff4d6d;
      color: white;
      border: none;
      border-radius: 5px;
      font-weight: bold;
      cursor: pointer;
    }

    button:hover {
      background: #c92f4f;
    }
  </style>
</head>
<body>

  <div class="box-wrapper">
    <div class="video-container" id="videoBox">
      <video id="loveVideo" autoplay loop controls playsinline>
        <source src="myday.mp4" type="video/mp4" />
        Your browser does not support the video tag.
      </video>
    </div>
    <div class="box-lid" id="lid"></div>
    <div class="box-body"></div>
  </div>

  <div class="buttons">
    <button onclick="openBox()">OPEN</button>
    <button onclick="closeBox()">CLOSE</button>
  </div>

  <script>
    const lid = document.getElementById("lid");
    const videoBox = document.getElementById("videoBox");
    const video = document.getElementById("loveVideo");

    function openBox() {
      lid.classList.add("open");
      videoBox.classList.add("show");
      video.play();
    }

    function closeBox() {
      lid.classList.remove("open");
      videoBox.classList.remove("show");
      video.pause();
      video.currentTime = 0;
    }
  </script>

</body>
</html>
