# github.io
<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="UTF-8">
<title>めだかガチャ</title>
<style>
body {
  background: black;
  color: white;
  text-align: center;
  font-family: sans-serif;
  padding-top: 50px;
}
h1 {
  font-size: 50px;
}
button {
  padding: 15px 30px;
  font-size: 20px;
  cursor: pointer;
  margin-top: 20px;
  border-radius: 10px;
  border: none;
  background: gold;
  color: black;
}
#result {
  margin-top: 30px;
  font-size: 30px;
  color: yellow;
}
</style>
</head>
<body>

<h1>めだかガチャ</h1>
<p>ボタンを押して今日のめだかを引こう！</p>
<button onclick="gacha()">ガチャを回す</button>

<div id="result"></div>

<script>
const medakaList = ["白めだか", "黒めだか", "黄金めだか", "光めだか", "ヒレ長めだか"];

function gacha() {
  const randomIndex = Math.floor(Math.random() * medakaList.length);
  const resultDiv = document.getElementById("result");
  resultDiv.innerHTML = "あなたのめだかは… <strong>" + medakaList[randomIndex] + "</strong>！✨";
}
</script>

</body>
</html>
