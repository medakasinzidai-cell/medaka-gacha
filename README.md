<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="UTF-8">
<title>めだかオリパ</title>
<style>
body {
  background: #0a0a0a;
  color: #fff;
  text-align: center;
  font-family: 'Segoe UI', sans-serif;
  padding-top: 50px;
}

h1 {
  font-size: 50px;
  color: #ffd700;
  text-shadow: 0 0 10px gold;
}

.button {
  padding: 20px 40px;
  font-size: 24px;
  border: none;
  border-radius: 15px;
  background: linear-gradient(to right, gold, orange);
  color: black;
  cursor: pointer;
  margin-top: 30px;
  transition: transform 0.2s;
}
.button:hover {
  transform: scale(1.1);
}

#pack {
  margin: 40px auto;
  width: 200px;
  height: 300px;
  background: linear-gradient(to bottom, #222, #555);
  border-radius: 15px;
  box-shadow: 0 0 20px #ffd700;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 24px;
  color: #ffd700;
  transition: transform 0.5s;
}

#pack.open {
  transform: scale(1.2) rotateY(180deg);
}

#result {
  margin-top: 30px;
  font-size: 28px;
  color: #00ffea;
  text-shadow: 0 0 10px #00ffea;
}

img.medaka {
  width: 150px;
  margin-top: 20px;
  border-radius: 10px;
  box-shadow: 0 0 20px #00ffea;
}
</style>
</head>
<body>

<h1>めだかオリパガチャ</h1>
<p>ボタンを押して今日のめだかを引こう！</p>

<div id="pack">PACK</div>

<button class="button" onclick="gacha()">開封する</button>

<div id="result"></div>

<script>
const medakaList = [
  {name: "白めだか", img: "https://via.placeholder.com/150/ffffff/000000?text=白めだか"},
  {name: "黒めだか", img: "https://via.placeholder.com/150/000000/ffffff?text=黒めだか"},
  {name: "黄金めだか", img: "https://via.placeholder.com/150/ffd700/000000?text=黄金めだか"},
  {name: "光めだか", img: "https://via.placeholder.com/150/00ffff/000000?text=光めだか"},
  {name: "ヒレ長めだか", img: "https://via.placeholder.com/150/ff00ff/000000?text=ヒレ長めだか"}
];

function gacha() {
  const pack = document.getElementById("pack");
  const result = document.getElementById("result");

  // アニメーション
  pack.classList.add("open");

  setTimeout(() => {
    const choice = medakaList[Math.floor(Math.random() * medakaList.length)];
    result.innerHTML = `あなたのめだかは… <strong>${choice.name}</strong>！✨<br><img class="medaka" src="${choice.img}" alt="${choice.name}">`;
    pack.classList.remove("open");
  }, 700); // 0.7秒後に結果表示
}
</script>

</body>
</html>
