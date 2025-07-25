# melgoy-market
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Melgoy Market</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .header {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 20px;
            margin-bottom: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            color: white;
            box-shadow: 0 8px 32px rgba(31, 38, 135, 0.37);
        }

        .logo {
            font-size: 24px;
            font-weight: bold;
            background: linear-gradient(45deg, #FFD700, #FFA500);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .user-info {
            display: flex;
            align-items: center;
            gap: 20px;
        }

        .coins {
            background: linear-gradient(45deg, #FFD700, #FFA500);
            padding: 10px 20px;
            border-radius: 25px;
            font-weight: bold;
            color: #333;
            display: flex;
            align-items: center;
            gap: 8px;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        .login-section, .marketplace {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            padding: 30px;
            margin-bottom: 20px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
        }

        .login-form {
            max-width: 400px;
            margin: 0 auto;
            text-align: center;
        }

        .login-form h2 {
            color: #333;
            margin-bottom: 20px;
            font-size: 28px;
        }

        .form-group {
            margin-bottom: 20px;
            text-align: left;
        }

        .form-group label {
            display: block;
            margin-bottom: 5px;
            color: #555;
            font-weight: 500;
        }

        .form-group input {
            width: 100%;
            padding: 12px;
            border: 2px solid #ddd;
            border-radius: 10px;
            font-size: 16px;
            transition: border-color 0.3s;
        }

        .form-group input:focus {
            outline: none;
            border-color: #667eea;
        }

        .btn {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            padding: 12px 30px;
            border: none;
            border-radius: 25px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }

        .tabs {
            display: flex;
            gap: 10px;
            margin-bottom: 20px;
        }

        .tab {
            padding: 10px 20px;
            background: #f0f0f0;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s;
        }

        .tab.active {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 20px;
        }

        .product-card {
            background: white;
            border-radius: 15px;
            padding: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s, box-shadow 0.3s;
            border: 2px solid transparent;
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
            border-color: #667eea;
        }

        .product-image {
            width: 100%;
            height: 150px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 48px;
            margin-bottom: 15px;
        }

        .product-title {
            font-size: 18px;
            font-weight: bold;
            color: #333;
            margin-bottom: 10px;
        }

        .product-price {
            font-size: 20px;
            font-weight: bold;
            color: #667eea;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 5px;
        }

        .seller-info {
            font-size: 14px;
            color: #666;
            margin-bottom: 15px;
        }

        .btn-buy {
            width: 100%;
            background: linear-gradient(45deg, #4CAF50, #45a049);
            color: white;
            padding: 10px;
            border: none;
            border-radius: 10px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
        }

        .btn-buy:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(76, 175, 80, 0.4);
        }

        .btn-buy:disabled {
            background: #ccc;
            cursor: not-allowed;
            transform: none;
            box-shadow: none;
        }

        .sell-form {
            background: white;
            border-radius: 15px;
            padding: 20px;
            margin-bottom: 20px;
        }

        .sell-form h3 {
            color: #333;
            margin-bottom: 20px;
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
        }

        .success-message {
            background: #d4edda;
            border: 1px solid #c3e6cb;
            color: #155724;
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 20px;
            text-align: center;
        }

        .hidden {
            display: none;
        }

        @media (max-width: 768px) {
            .form-row {
                grid-template-columns: 1fr;
            }
            
            .header {
                flex-direction: column;
                gap: 15px;
                text-align: center;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <div class="logo">🛒 Melgoy Market</div>
            <div class="user-info" id="userInfo" style="display: none;">
                <span>Welcome, <span id="username"></span>!</span>
                <div class="coins">
                    🪙 <span id="coinCount">100</span> Coins
                </div>
                <button class="btn" onclick="logout()">Logout</button>
            </div>
        </div>

        <div class="login-section" id="loginSection">
            <div class="login-form">
                <h2>Welcome to Melgoy Market! 🎒</h2>
                <p style="margin-bottom: 20px; color: #666;">Join your school marketplace and get 100 free coins to start trading!</p>
                
                <div class="tabs" style="margin-bottom: 20px;">
                    <button class="tab active" id="loginTab" onclick="showAuthTab('login')">🔑 Login</button>
                    <button class="tab" id="signupTab" onclick="showAuthTab('signup')">📝 Sign Up</button>
                </div>

                <div id="loginForm">
                    <div class="form-group">
                        <label for="loginName">Your Name</label>
                        <input type="text" id="loginName" placeholder="Enter your name" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="loginPassword">Password</label>
                        <input type="password" id="loginPassword" placeholder="Enter your password" required>
                    </div>
                    
                    <button class="btn" onclick="login()">Login 🚀</button>
                </div>

                <div id="signupForm" class="hidden">
                    <div class="form-group">
                        <label for="signupName">Your Name</label>
                        <input type="text" id="signupName" placeholder="Enter your name" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="signupPassword">Create Password</label>
                        <input type="password" id="signupPassword" placeholder="Create a password" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="confirmPassword">Confirm Password</label>
                        <input type="password" id="confirmPassword" placeholder="Confirm your password" required>
                    </div>
                    
                    <button class="btn" onclick="signup()">Sign Up & Get 100 Coins! 🪙</button>
                </div>
            </div>
        </div>

        <div class="marketplace hidden" id="marketplace">
            <div class="tabs">
                <button class="tab active" onclick="showTab('buy')">🛒 Buy Items</button>
                <button class="tab" onclick="showTab('sell')">💰 Sell Items</button>
            </div>

            <div id="buyTab">
                <div class="products-grid" id="productsGrid">
                    <!-- Products will be loaded here -->
                </div>
            </div>

            <div id="sellTab" class="hidden">
                <div class="sell-form">
                    <h3>📝 List Your Item</h3>
                    <div id="sellSuccess" class="success-message hidden">
                        Item listed successfully! 🎉
                    </div>
                    
                    <div class="form-row">
                        <div class="form-group">
                            <label for="itemName">Item Name</label>
                            <input type="text" id="itemName" placeholder="e.g., Blue Pen">
                        </div>
                        <div class="form-group">
                            <label for="itemPrice">Price (Coins)</label>
                            <input type="number" id="itemPrice" placeholder="e.g., 15" min="1">
                        </div>
                    </div>
                    
                    <div class="form-group">
                        <label for="itemImage">Item Picture</label>
                        <input type="file" id="itemImage" accept="image/*" style="width: 100%; padding: 12px; border: 2px solid #ddd; border-radius: 10px;">
                        <small style="color: #666; font-size: 12px;">Upload a clear photo of your item</small>
                    </div>
                    
                    <div class="form-group">
                        <label for="itemCategory">Category</label>
                        <select id="itemCategory" style="width: 100%; padding: 12px; border: 2px solid #ddd; border-radius: 10px;">
                            <option value="pen">✏️ Pens</option>
                            <option value="pencil">✏️ Pencils</option>
                            <option value="eraser">🧽 Erasers</option>
                            <option value="notebook">📓 Notebooks</option>
                            <option value="calculator">🔢 Calculators</option>
                            <option value="other">📦 Other</option>
                        </select>
                    </div>
                    
                    <div class="form-group">
                        <label for="itemDescription">Description</label>
                        <textarea id="itemDescription" placeholder="Describe your item..." style="width: 100%; padding: 12px; border: 2px solid #ddd; border-radius: 10px; min-height: 80px; resize: vertical;"></textarea>
                    </div>
                    
                    <button class="btn" onclick="listItem()">📋 List Item</button>
                </div>
            </div>
        </div>
    </div>

    <script>
        let currentUser = null;
        let userCoins = 100;
        let users = {}; // Store user accounts
        let products = [];

        function showAuthTab(tab) {
            document.querySelectorAll('#loginSection .tab').forEach(t => t.classList.remove('active'));
            
            if (tab === 'login') {
                document.getElementById('loginTab').classList.add('active');
                document.getElementById('loginForm').classList.remove('hidden');
                document.getElementById('signupForm').classList.add('hidden');
            } else {
                document.getElementById('signupTab').classList.add('active');
                document.getElementById('loginForm').classList.add('hidden');
                document.getElementById('signupForm').classList.remove('hidden');
            }
        }

        function signup() {
            const name = document.getElementById('signupName').value.trim();
            const password = document.getElementById('signupPassword').value.trim();
            const confirmPassword = document.getElementById('confirmPassword').value.trim();

            if (!name || !password || !confirmPassword) {
                alert('Please fill in all fields!');
                return;
            }

            if (password !== confirmPassword) {
                alert('Passwords do not match!');
                return;
            }

            if (password.length < 4) {
                alert('Password must be at least 4 characters long!');
                return;
            }

            if (users[name]) {
                alert('A user with this name already exists! Please choose a different name.');
                return;
            }

            // Create new user account
            users[name] = {
                name: name,
                password: password,
                coins: 100,
                joinDate: new Date().toLocaleDateString()
            };

            alert('🎉 Account created successfully! You can now login with your credentials.');
            
            // Clear signup form and switch to login
            document.getElementById('signupName').value = '';
            document.getElementById('signupPassword').value = '';
            document.getElementById('confirmPassword').value = '';
            showAuthTab('login');
        }

        function login() {
            const name = document.getElementById('loginName').value.trim();
            const password = document.getElementById('loginPassword').value.trim();

            if (!name || !password) {
                alert('Please enter both name and password!');
                return;
            }

            if (!users[name]) {
                alert('No account found with this name. Please sign up first!');
                return;
            }

            if (users[name].password !== password) {
                alert('Incorrect password! Please try again.');
                return;
            }

            currentUser = users[name];
            userCoins = currentUser.coins;
            
            document.getElementById('loginSection').style.display = 'none';
            document.getElementById('marketplace').classList.remove('hidden');
            document.getElementById('userInfo').style.display = 'flex';
            document.getElementById('username').textContent = name;
            document.getElementById('coinCount').textContent = userCoins;
            
            loadProducts();
        }

        function logout() {
            // Save current user's coins before logout
            if (currentUser) {
                users[currentUser.name].coins = userCoins;
            }
            
            currentUser = null;
            userCoins = 100;
            
            document.getElementById('loginSection').style.display = 'block';
            document.getElementById('marketplace').classList.add('hidden');
            document.getElementById('userInfo').style.display = 'none';
            
            // Clear forms
            document.getElementById('loginName').value = '';
            document.getElementById('loginPassword').value = '';
            document.getElementById('signupName').value = '';
            document.getElementById('signupPassword').value = '';
            document.getElementById('confirmPassword').value = '';
            
            // Reset to login tab
            showAuthTab('login');
        }

        function showTab(tab) {
            document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
            event.target.classList.add('active');
            
            if (tab === 'buy') {
                document.getElementById('buyTab').classList.remove('hidden');
                document.getElementById('sellTab').classList.add('hidden');
            } else {
                document.getElementById('buyTab').classList.add('hidden');
                document.getElementById('sellTab').classList.remove('hidden');
            }
        }

        function loadProducts() {
            const grid = document.getElementById('productsGrid');
            grid.innerHTML = '';

            if (products.length === 0) {
                grid.innerHTML = '<div style="text-align: center; color: #666; grid-column: 1/-1; padding: 40px;">No items for sale yet. Be the first to list something! 🚀</div>';
                return;
            }

            products.forEach(product => {
                const canAfford = userCoins >= product.price;
                const isOwnItem = product.seller === currentUser.name;
                
                const card = document.createElement('div');
                card.className = 'product-card';
                
                // Display image or emoji
                const imageDisplay = product.image ? 
                    `<img src="${product.image}" alt="${product.name}" style="width: 100%; height: 150px; object-fit: cover; border-radius: 10px;">` :
                    `<div class="product-image">${product.emoji}</div>`;
                
                card.innerHTML = `
                    ${imageDisplay}
                    <div class="product-title">${product.name}</div>
                    <div class="product-price">🪙 ${product.price} coins</div>
                    <div class="seller-info">Sold by: ${product.seller}</div>
                    <p style="color: #666; font-size: 14px; margin-bottom: 15px;">${product.description}</p>
                    <button class="btn-buy" onclick="buyItem(${product.id})" 
                            ${!canAfford || isOwnItem ? 'disabled' : ''}>
                        ${isOwnItem ? 'Your Item' : !canAfford ? 'Not Enough Coins' : 'Buy Now'}
                    </button>
                `;
                grid.appendChild(card);
            });
        }

        function buyItem(productId) {
            const product = products.find(p => p.id === productId);
            if (!product) return;

            if (userCoins < product.price) {
                alert('Not enough coins!');
                return;
            }

            if (confirm(`Buy ${product.name} for ${product.price} coins?`)) {
                // Deduct coins from buyer
                userCoins -= product.price;
                users[currentUser.name].coins = userCoins;
                
                // Add coins to seller's account
                if (users[product.seller]) {
                    users[product.seller].coins += product.price;
                }
                
                document.getElementById('coinCount').textContent = userCoins;
                
                // Remove the bought item
                products = products.filter(p => p.id !== productId);
                
                alert(`🎉 You bought ${product.name}! ${product.price} coins have been transferred to ${product.seller}. Contact them to arrange pickup/delivery.`);
                loadProducts();
            }
        }

        function listItem() {
            const name = document.getElementById('itemName').value.trim();
            const price = parseInt(document.getElementById('itemPrice').value);
            const category = document.getElementById('itemCategory').value;
            const description = document.getElementById('itemDescription').value.trim();
            const imageFile = document.getElementById('itemImage').files[0];

            if (!name || !price || !description) {
                alert('Please fill in all required fields!');
                return;
            }

            if (price < 1) {
                alert('Price must be at least 1 coin!');
                return;
            }

            const categoryEmojis = {
                pen: '✏️',
                pencil: '✏️',
                eraser: '🧽',
                notebook: '📓',
                calculator: '🔢',
                other: '📦'
            };

            const newProduct = {
                id: Date.now(),
                name: name,
                price: price,
                category: category,
                seller: currentUser.name,
                description: description,
                emoji: categoryEmojis[category],
                image: null
            };

            // If image is uploaded, convert to base64
            if (imageFile) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    newProduct.image = e.target.result;
                    addProductToList(newProduct);
                };
                reader.readAsDataURL(imageFile);
            } else {
                addProductToList(newProduct);
            }
        }

        function addProductToList(product) {
            products.unshift(product);
            
            // Clear form
            document.getElementById('itemName').value = '';
            document.getElementById('itemPrice').value = '';
            document.getElementById('itemDescription').value = '';
            document.getElementById('itemImage').value = '';
            
            // Show success message
            document.getElementById('sellSuccess').classList.remove('hidden');
            setTimeout(() => {
                document.getElementById('sellSuccess').classList.add('hidden');
            }, 3000);
            
            // Switch to buy tab to see the new item
            showTab('buy');
            document.querySelectorAll('.tab')[0].classList.add('active');
            document.querySelectorAll('.tab')[1].classList.remove('active');
            
            loadProducts();
        }
    </script>
</body>
</html>
