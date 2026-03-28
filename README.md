<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AvBrothers Fashion</title>

<style>
body {margin:0;font-family:sans-serif;background:#f5f5f5;}

header {
  background:#111;color:white;padding:15px;
  display:flex;justify-content:space-between;
  align-items:center;
}

header h2 {margin:0;}

.search {
  padding:5px;border-radius:5px;border:none;
}

.container {
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
  gap:15px;padding:15px;
}

.card {
  background:white;border-radius:10px;
  overflow:hidden;box-shadow:0 0 10px rgba(0,0,0,0.1);
}

.card img {
  width:100%;height:250px;object-fit:cover;
}

.card h3 {margin:10px;}

.price {color:green;margin:0 10px;}

.btn {
  margin:10px;background:red;color:white;
  border:none;padding:10px;border-radius:5px;
  width:90%;
}

#cartBox {
  position:fixed;right:10px;top:70px;
  background:white;padding:10px;
  border-radius:10px;box-shadow:0 0 10px rgba(0,0,0,0.2);
  width:200px;
}

#cartItems {font-size:14px;}

footer {
  text-align:center;padding:10px;
  background:black;color:white;
}
</style>

</head>

<body>

<header>
  <h2>🔥 AvBrothers</h2>
  <input type="text" class="search" placeholder="Search..." onkeyup="searchProduct(this.value)">
</header>

<div class="container" id="products">

<div class="card">
<img src="top1.jpg">
<h3>NEVER GIVE UP Top(Green)</h3>
<p class="price">₹199</p>
<button class="btn" onclick="addToCart('NEVER GIVE UP Top',199)">Add to Cart</button>
</div>

<div class="card">
<img src="kurti1.jpg">
<h3>Stylish Kurti(White)</h3>
<p class="price">₹299</p>
<button class="btn" onclick="addToCart('NEVER GIVE UP Top',199)">Add to Cart</button>
</div>

<div class="card">
<img src="top2.jpg">
<h3>NEVER GIVE UP Top(Black)</h3>
<p class="price">₹199</p>
<button class="btn" onclick="addToCart('Black Top',249)">Add to Cart</button>
</div>

<div class="card">
<img src="top3.jpg">
<h3>White Top</h3>
<p class="price">₹249</p>
<button class="btn" onclick="addToCart('White Top',199)">Add to Cart</button>
</div>

</div>

<div id="cartBox">
<h4>🛒 Cart</h4>
<div id="cartItems">No items</div>
<p>Total: ₹<span id="total">0</span></p>
<button onclick="orderNow()">Order</button>
</div>

<footer>
© 2026 AvBrothers Fashion
</footer>

<script>
let items = [];
let total = 0;

function addToCart(name, price){
  items.push(name);
  total += price;

  document.getElementById("cartItems").innerHTML = items.join("<br>");
  document.getElementById("total").innerText = total;
}

function orderNow(){
  let msg = "Order:\n" + items.join(", ") + "\nTotal ₹" + total;
  window.open("https://wa.me/7248906682 text=" + encodeURIComponent(msg));
}

function searchProduct(value){
  let cards = document.querySelectorAll(".card");
  value = value.toLowerCase();

  cards.forEach(card=>{
    let text = card.innerText.toLowerCase();
    card.style.display = text.includes(value) ? "block" : "none";
  });
}
</script>

</body>
</html>
