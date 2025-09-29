# all5<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>JKS Group Combined Website</title>
<style>
  /* Basic resets and typography */
  body {
    font-family: Arial, sans-serif;
    background: #f7fafc;
    margin: 0;
    color: #205081;
  }
  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: #e3effa;
    padding: 16px 36px;
    font-weight: 600;
    color: #2e6aa7;
    border-bottom: 3px solid #7fd0f0;
  }
  .main-menu {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
    margin: 20px auto 30px;
    width: 90%;
  }
  .menu-box {
    background: #f4fafe;
    border: 2px solid #85bbeb;
    border-radius: 10px;
    min-width: 160px;
    padding: 25px 15px;
    text-align: center;
    font-size: 1.1em;
    cursor: pointer;
    box-shadow: 0 2px 8px #dde8f9;
    transition: background 0.3s ease;
    font-weight: 600;
    color: #205081;
  }
  .menu-box:hover {
    background: #d0e6fb;
  }
  .section-container {
    max-width: 900px;
    margin: 0 auto 40px;
    background: #fff;
    border-radius: 10px;
    box-shadow: 0 3px 14px #d3d7dbcc;
    padding: 20px 30px 30px;
    display: none;
  }
  .section-container.active {
    display: block;
  }
  h2.section-title {
    color: #295bb6;
    text-align: center;
    margin-bottom: 20px;
    font-weight: 700;
    font-size: 1.5em;
  }
  /* E-commerce form styles */
  form {
    max-width: 520px;
    margin: 0 auto;
  }
  label {
    font-weight: 600;
    display: block;
    margin-top: 20px;
    margin-bottom: 6px;
    font-size: 1.05em;
  }
  input, textarea {
    width: 100%;
    padding: 11px 12px;
    border-radius: 6px;
    border: 1.6px solid #85bbeb;
    font-size: 1em;
    font-family: Arial, sans-serif;
    resize: vertical;
  }
  textarea {
    min-height: 80px;
  }
  button.submit-btn {
    background-color: #205081;
    border: none;
    color: white;
    padding: 15px 28px;
    border-radius: 10px;
    font-size: 1.12em;
    font-weight: 700;
    cursor: pointer;
    margin-top: 28px;
    width: 100%;
    transition: background-color 0.3s;
  }
  button.submit-btn:hover {
    background-color: #2e6aa7;
  }
  .success-message {
    margin-top: 18px;
    color: #0a6a33;
    font-weight: 600;
    text-align: center;
  }
</style>
</head>
<body>

<div class="header">
  <span>Profile</span>
  <span>Add Cash</span>
</div>

<div class="main-menu">
  <div class="menu-box" onclick="showSection('dashboard')">Dashboard Home</div>
  <div class="menu-box" onclick="showSection('ecommerce')">My E-commerce</div>
  <div class="menu-box" onclick="showSection('homeService')">Home Service & Accessories</div>
  <!-- Add more menu boxes for other sections -->
</div>

<!-- Dashboard Section -->
<div id="dashboard" class="section-container active">
  <h2 class="section-title">JKS Group Dashboard</h2>
  <div style="text-align:center; font-size:1.2em; font-weight: 500; color:#316796; padding: 25px 0; border: 2px solid #7fd0f0; border-radius: 8px; max-width:700px; margin:0 auto 20px;">
    Add (or) product display
  </div>
</div>

<!-- E-commerce Section -->
<div id="ecommerce" class="section-container">
  <h2 class="section-title">My E-commerce Order Form</h2>
  <form id="orderForm">
    <label for="name">Full Name</label>
    <input type="text" id="name" name="name" placeholder="Enter your full name" required />
    
    <label for="mobile">Mobile Number</label>
    <input type="tel" id="mobile" name="mobile" placeholder="Enter mobile number" pattern="[0-9]{10,15}" required />
    
    <label for="orderDetails">Order Details</label>
    <textarea id="orderDetails" name="orderDetails" placeholder="Write your order details here" required></textarea>
    
    <label for="address">Delivery Address</label>
    <textarea id="address" name="address" placeholder="Enter your delivery address" required></textarea>
    
    <button type="submit" class="submit-btn">Submit Order via WhatsApp</button>
    <p id="successMsg" class="success-message" style="display:none;">Your order message has been prepared in WhatsApp.</p>
  </form>
</div>

<!-- Home Service Section -->
<div id="homeService" class="section-container">
  <div style="max-width:800px; margin: 0 auto;">
    <h2 class="section-title">Home Service and Accessories</h2>
    <div>
      <h3>Car & Vehicle</h3>
      <ul>
        <li>Car wash & repair (mechanic)</li>
        <li>Bike wash & repair</li>
        <li>Barber shop (male & female)</li>
        <li>16th boundary service</li>
        <li>Car driver (lease)</li>
        <li>General car driver</li>
      </ul>
    </div>
    <div>
      <h3>Home & Technical Services</h3>
      <ul>
        <li>Computer tailor</li>
        <li>Electrical technician / electrician</li>
        <li>Helpers (home need)</li>
        <li>Home cleaning & shifting</li>
        <li>Plumber (tools & equipment)</li>
        <li>Painter (brushes, paints etc.)</li>
        <li>Technician services (wiring, tools etc.)</li>
      </ul>
    </div>
    <div>
      <h3>Technology Repairs & Installation</h3>
      <ul>
        <li>CC camera installation</li>
        <li>Computer repair</li>
        <li>Mobile repair</li>
      </ul>
    </div>
    <div>
      <h3>Culinary Services</h3>
      <ul>
        <li>Chefs / Cooking specialists</li>
      </ul>
    </div>
  </div>
</div>

<script>
  // Function to switch section visibility
  function showSection(id) {
    document.querySelectorAll('.section-container').forEach(c => c.classList.remove('active'));
    document.getElementById(id).classList.add('active');
    clearFormMessage();
  }

  // WhatsApp order message handling for e-commerce form
  const orderForm = document.getElementById('orderForm');
  const successMsg = document.getElementById('successMsg');

  orderForm.addEventListener('submit', event => {
    event.preventDefault();
    const name = orderForm.name.value.trim();
    const mobile = orderForm.mobile.value.trim();
    const orderDetails = orderForm.orderDetails.value.trim();
    const address = orderForm.address.value.trim();

    if (!name || !mobile || !orderDetails || !address) {
      alert('Please fill in all fields.');
      return;
    }

    const message = `Hello, I would like to place an order.%0A%0AName: ${name}%0AMobile: ${mobile}%0AOrder Details: ${orderDetails}%0ADelivery Address: ${address}`;

    const whatsappNumber = "918977143043"; // Your WhatsApp number (with country code)
    const whatsappURL = `https://wa.me/${whatsappNumber}?text=${message}`;

    successMsg.style.display = 'block';
    window.open(whatsappURL, '_blank');
    orderForm.reset();
  });

  function clearFormMessage() {
    successMsg.style.display = 'none';
  }

  // Show dashboard section by default
  showSection('dashboard');
</script>

</body>
</html>
