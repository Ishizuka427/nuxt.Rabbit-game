<script>
<html lang="ja">
  <head>
    <meta charset="utf-8">
    <title>Rabbit-game</title>
    
  </head>
      <p>POINT: <span id="point"></span></p>
      <button onclick="location.reload()">CONTINUE</button>
      <div class="game">


      </div>

</script>

<style>
 body {
        display: flex;
      }
      p {
      text-align: center;
      }
      .game {
        left: 0px;
        margin: auto;
      }
      .box {
        width: 100px;
        height: 100px;
        background: skyblue;
        cursor: pointer;
        transition: 0.8s;
        margin: 0 8px 8px 0;
        text-align: center;
        line-height: 100px;
      }
      .win {
        background-image: url("./img/usagi.png");
        background-size: 100px;
        border-radius: 50%;
        transform: rotate(360deg);
      }
      .lose {
        background-image: url("./img/yagi.png");
        background-size: 100px;
        border-radius: 50%;
        transform: scale(0.9);
      }
      </style>
