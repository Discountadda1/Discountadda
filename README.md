<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>My Professional Store</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <header>
    <h1>My Professional Store</h1>
    <nav>
      <button onclick="toggleCart()">View Cart (<span id="cart-count">0</span>)</button>
    </nav>
  </header>

  <main class="product-grid" id="product-list">
    <!-- Products will be injected by JS -->
  </main>

  <div id="cart-modal" class="cart-modal hidden">
    <div class="cart-content">
      <h2>Your Cart</h2>
      <div id="cart-items"></div>
      <p>Total: $<span id="cart-total">0.00</span></p>
      <button onclick="checkout()">Checkout</button>
      <button onclick="toggleCart()">Close</button>
    </div>
  </div>

  <footer>
    &copy; 2025 My Professional Store. All rights reserved.
  </footer>

  <script src="script.js"></script>
</body>
</html>
body {
  margin: 0;
  font-family: 'Segoe UI', sans-serif;
  background: #f4f4f4;
}

header {
  background: #2c3e50;
  color: white;
  padding: 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

nav button {
  background: #27ae60;
  color: white;
  border: none;
  padding: 10px 16px;
  border-radius: 5px;
  cursor: pointer;
}

.product-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 20px;
  padding: 40px;
}

.product {
  background: white;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 2px 6px rgba(0,0,0,0.1);
  text-align: center;
}

.product img {
  width: 100%;
  height: 180px;
  object-fit: cover;
  border-radius: 8px;
}

.product h3 {
  margin: 15px 0 10px;
}

.product p {
  color: #444;
}

.product button {
  background: #27ae60;
  color: white;
  border: none;
  padding: 10px 15px;
  margin-top: 10px;
  border-radius: 5px;
  cursor: pointer;
}

.cart-modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

.cart-content {
  background: white;
  padding: 30px;
  border-radius: 12px;
  width: 90%;
  max-width: 400px;
}

.cart-content button {
  margin-top: 15px;
}

.hidden {
  display: none;
}

footer {
  background: #2c3e50;
  color: white;
  text-align: center;
  padding: 15px;
}
const products = [
  {
    id: 1,
    name: "Handgripper (60kg)",
    price: 139,
    image: "https://via.placeholder.com/300x180?text=Handgripper"
  },
  {
    id: 2,
    name: "Gaming Trigger",
    price: 179,
    image: "https://via.placeholder.com/300x180?text=Gaming+Trigger"
  },
  {
    id: 3,
    name: "Gaming Gloves",
    price: 39,
    image: "https://via.placeholder.com/300x180?text=Gaming+Gloves"
  },
  {
    id: 4,
    name: "Stainless Watch",
    price: 179,
    image: "https://via.placeholder.com/300x180?text=Stainless+Watch"
  },
  {
    id: 5,
    name: "Bat Gripper with Cone",
    price: 220,
    image: "https://via.placeholder.com/300x180?text=Bat+Gripper+with+Cone"
  }
];

let cart = [];

// ... (rest of the script remains unchanged)
