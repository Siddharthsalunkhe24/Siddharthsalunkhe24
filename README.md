<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Farm to Consumer Marketplace</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: #f0f8ea;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .header {
            background-color: #2e7d32;
            color: white;
            padding: 15px 0;
            text-align: center;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .page {
            display: none;
            padding: 30px;
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            margin-top: 20px;
        }

        .active {
            display: block;
        }

        .form-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            margin-bottom: 5px;
            font-weight: 600;
            color: #333;
        }

        input, textarea, select {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 16px;
        }

        button {
            background-color: #2e7d32;
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
            transition: background-color 0.3s;
        }

        button:hover {
            background-color: #1b5e20;
        }

        .btn-secondary {
            background-color: #757575;
            margin-right: 10px;
        }

        .btn-secondary:hover {
            background-color: #616161;
        }

        .back-btn {
            background-color: #757575;
            margin-top: 20px;
        }

        .card {
            border: 1px solid #ddd;
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 15px;
            background-color: #fff;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
        }

        .card h3 {
            color: #2e7d32;
            margin-bottom: 10px;
        }

        .category-list {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin-bottom: 20px;
        }

        .category-item {
            background-color: #e8f5e9;
            padding: 15px;
            border-radius: 8px;
            cursor: pointer;
            transition: transform 0.3s, box-shadow 0.3s;
            text-align: center;
            width: calc(33.33% - 10px);
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
        }

        .category-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .product-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
        }

        .product-card {
            border: 1px solid #ddd;
            border-radius: 8px;
            padding: 15px;
            background-color: #fff;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
        }

        .product-card h3 {
            color: #2e7d32;
            margin-bottom: 10px;
        }

        .product-details {
            margin-bottom: 15px;
        }

        .product-actions {
            display: flex;
            justify-content: flex-end;
        }

        .welcome-page {
            text-align: center;
            padding: 40px 0;
        }

        .welcome-buttons {
            margin-top: 30px;
            display: flex;
            justify-content: center;
            gap: 20px;
        }

        .alert {
            padding: 10px;
            background-color: #f8d7da;
            color: #721c24;
            border-radius: 4px;
            margin-bottom: 20px;
            display: none;
        }

        .success {
            background-color: #d4edda;
            color: #155724;
        }
        .image-gallery {
    margin-top: 30px;
    display: flex;
    justify-content: center;
    gap: 20px;
    flex-wrap: wrap;
}

.image-gallery img {
    border-radius: 10px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    width: 200px;
    height: 150px;
    object-fit: cover;
}

.about-us-section {
    margin-top: 40px;
    padding: 30px;
    background-color: #ffffff;
    border-radius: 20px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    max-width: 900px;
    margin-left: auto;
    margin-right: auto;
    text-align: center;
}
    </style>
</head>
<body>
    <div class="header">
        <h1>Farm to Consumer Marketplace</h1>
    </div>

    <div class="container">
        <!-- Auth Pages -->
        <div id="authPage" class="page active">
            <div class="welcome-page">
                <h2>Welcome to Farm to Consumer Marketplace</h2>
                <p>Connect directly with farmers or find fresh produce</p>
                
                <div class="welcome-buttons">
                    <button id="showLoginBtn">Login</button>
                    <button id="showRegisterBtn">Register</button>
                </div>
            </div>
        </div>

        <div id="registerPage" class="page">
            <h2>Register</h2>
            <div id="registerAlert" class="alert"></div>
            
            <form id="registerForm">
                <div class="form-group">
                    <label for="registerName">Full Name</label>
                    <input type="text" id="registerName" required>
                </div>
                
                <div class="form-group">
                    <label for="registerMobile">Mobile Number</label>
                    <input type="tel" id="registerMobile" required>
                </div>
                
                <div class="form-group">
                    <label for="registerPassword">Password</label>
                    <input type="password" id="registerPassword" required>
                </div>
                
                <button type="submit">Register</button>
                <button type="button" class="back-btn" onclick="showPage('authPage')">Back</button>
            </form>
        </div>

        <div id="loginPage" class="page">
            <h2>Login</h2>
            <div id="loginAlert" class="alert"></div>
            
            <form id="loginForm">
                <div class="form-group">
                    <label for="loginMobile">Mobile Number</label>
                    <input type="tel" id="loginMobile" required>
                </div>
                
                <div class="form-group">
                    <label for="loginPassword">Password</label>
                    <input type="password" id="loginPassword" required>
                </div>
                
                <button type="submit">Login</button>
                <button type="button" class="back-btn" onclick="showPage('authPage')">Back</button>
            </form>
        </div>

      <div id="homePage" class="page">
        <h2>Welcome <span id="userNameDisplay"></span></h2>
        <p>Select your role to continue:</p>
        
        <div class="welcome-buttons">
            <button id="farmerBtn">Farmer Dashboard</button>
            <button id="consumerBtn">Consumer Dashboard</button>
        </div>
        
        <button type="button" class="back-btn" id="logoutBtn">Logout</button>
    
        <!-- Image Gallery -->
        <div class="image-gallery" style="margin-top: 100px;">
            <img src="/home/siddhi/Desktop/grocery/images.jpeg" alt="Farm 1">
            <img src="/home/siddhi/Desktop/grocery/vegf.jpeg" alt="Farm 2">
            <img src="/home/siddhi/Desktop/grocery/gnt.jpg" alt="Farm 3">
        </div>
    
        <!-- About Us Section -->
        <div class="about-us-section" style="margin-top: 170px;">
            <h2>About Us</h2>
            <p style="margin-top: 10px;">
                Our mission is to connect farmers directly with consumers, ensuring freshness,transparency,trust and fair pricing. 
                
                contact Details : 9158578827, siddharths14@gmail.com
            </p>
        </div>
    </div>

        <!-- Farmer Pages -->
        <div id="farmerPage" class="page">
            <h2>Farmer Dashboard</h2>
            
            <div class="card">
                <h3>Add New Product</h3>
                <form id="addProductForm">
                    <div class="form-group">
                        <label for="productName">Product Name</label>
                        <input type="text" id="productName" required>
                        

                    </div>
                    
                    <div class="form-group">
                        <label for="productCategory">Category</label>
                        <select id="productCategory" required>
                            <option value="">Select Category</option>
                            <option value="Rice">Rice</option>
                            <option value="Wheat">Wheat</option>
                            <option value="pulses">pulses</option>
                            <option value="Fruits">Fruits</option>
                            <option value="Vegetables">Vegetables</option>
                        </select>
                    </div>
                    
                    <div class="form-group">
                        <label for="productPrice">Price per unit (₹)</label>
                        <input type="number" id="productPrice" min="1" step="0.01" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="productQuantity">Available Quantity</label>
                        <input type="number" id="productQuantity" min="1" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="productUnit">Unit</label>
                        <select id="productUnit" required>
                            <option value="kg">Kilogram (kg)</option>
                            <option value="g">Gram (g)</option>
                            <option value="piece">Piece</option>
                            <option value="dozen">Dozen</option>
                        </select>
                    </div>
                    
                    <div class="form-group">
                        <label for="productDescription">Description</label>
                        <textarea id="productDescription" rows="4" required></textarea>
                    </div>
                    <div class="form-group">
                        <label for="farmerPhone">Phone Number</label>
                        <input type="tel" id="farmerPhone" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="farmerAddress">Address</label>
                        <input type="text" id="farmerAddress" required>
                    </div>
                    
                    
                    <button type="submit">Add Product</button>
                </form>
            </div>
            
            <h3>Your Listed Products</h3>
            <div id="farmerProductsList"></div>
            
            <button type="button" class="back-btn" onclick="showPage('homePage')">Back to Home</button>
        </div>

        <!-- Consumer Pages -->
        <div id="consumerPage" class="page">
            <h2>Consumer Dashboard</h2>
            <p>Browse products by category:</p>
            
            <div class="category-list">
                <div class="category-item" data-category="Rice">
                    <h3>Rice</h3>
                </div>
                <div class="category-item" data-category="Wheat">
                    <h3>Wheat</h3>
                </div>
                <div class="category-item" data-category="pulses">
                    <h3>pulses</h3>
                </div>
                <div class="category-item" data-category="Fruits">
                    <h3>Fruits</h3>
                </div>
                <div class="category-item" data-category="Vegetables">
                    <h3>Vegetables</h3>
                </div>
            </div>
            
            <button type="button" class="back-btn" onclick="showPage('homePage')">Back to Home</button>
        </div>

        <div id="categoryProductsPage" class="page">
            <h2>Products in <span id="categoryTitle"></span></h2>
            
            <div id="categoryProductsList" class="product-list"></div>
            
            <button type="button" class="back-btn" onclick="showPage('consumerPage')">Back to Categories</button>
        </div>
    </div>

    <script>
        // DOM Elements
        const pages = document.querySelectorAll('.page');
        
        // Show Page Function
        function showPage(pageId) {
            pages.forEach(page => {
                page.classList.remove('active');
            });
            document.getElementById(pageId).classList.add('active');
        }

        // Initialize Local Storage if needed
        function initializeLocalStorage() {
            if (!localStorage.getItem('users')) {
                localStorage.setItem('users', JSON.stringify([]));
            }
            if (!localStorage.getItem('products')) {
                localStorage.setItem('products', JSON.stringify([]));
            }
        }

        // User Authentication Functions
        function registerUser(name, mobile, password) {
            const users = JSON.parse(localStorage.getItem('users'));
            
            // Check if user already exists
            const existingUser = users.find(user => user.mobile === mobile);
            if (existingUser) {
                return { success: false, message: 'User with this mobile number already exists!' };
            }
            
            // Add new user
            const newUser = { id: Date.now().toString(), name, mobile, password };
            users.push(newUser);
            localStorage.setItem('users', JSON.stringify(users));
            
            return { success: true, user: newUser };
        }

        function loginUser(mobile, password) {
            const users = JSON.parse(localStorage.getItem('users'));
            const user = users.find(user => user.mobile === mobile && user.password === password);
            
            if (user) {
                sessionStorage.setItem('currentUser', JSON.stringify(user));
                return { success: true, user };
            } else {
                return { success: false, message: 'Invalid mobile number or password!' };
            }
        }

        function logoutUser() {
            sessionStorage.removeItem('currentUser');
            showPage('authPage');
        }

        // Product Functions
        function addProduct(productData) {
            const products = JSON.parse(localStorage.getItem('products'));
            const newProduct = {
                id: Date.now().toString(),
                farmerId: getCurrentUser().id,
                farmerName: getCurrentUser().name,
                ...productData
            };
            
            products.push(newProduct);
            localStorage.setItem('products', JSON.stringify(products));
            
            return newProduct;
        }

        function getProductsByFarmer(farmerId) {
            const products = JSON.parse(localStorage.getItem('products'));
            return products.filter(product => product.farmerId === farmerId);
        }

        function getProductsByCategory(category) {
            const products = JSON.parse(localStorage.getItem('products'));
            return products.filter(product => product.category === category);
        }

        function getCurrentUser() {
            return JSON.parse(sessionStorage.getItem('currentUser'));
        }

        // UI Rendering Functions
        function renderFarmerProducts() {
            const currentUser = getCurrentUser();
            const farmerProducts = getProductsByFarmer(currentUser.id);
            const productsListElement = document.getElementById('farmerProductsList');
            
            if (farmerProducts.length === 0) {
                productsListElement.innerHTML = '<p>You have no products listed yet.</p>';
                return;
            }
            
            let html = '';
            farmerProducts.forEach(product => {
                html += `
                    <div class="card">
                        <h3>${product.name}</h3>
                        <div class="product-details">
                            <p><strong>Category:</strong> ${product.category}</p>
                            <p><strong>Price:</strong> ₹${product.price} per ${product.unit}</p>
                            <p><strong>Available:</strong> ${product.quantity} ${product.unit}</p>
                            <p><strong>Description:</strong> ${product.description}</p>
                            <p><strong>Phone:</strong> ${product.phone}</p>
                            <p><strong>Address:</strong> ${product.address}</p>
                        </div>
                    </div>
                `;
            });
            
            productsListElement.innerHTML = html;
        }

        function renderCategoryProducts(category) {
            const categoryProducts = getProductsByCategory(category);
            const categoryProductsListElement = document.getElementById('categoryProductsList');
            document.getElementById('categoryTitle').textContent = category;
            
            if (categoryProducts.length === 0) {
                categoryProductsListElement.innerHTML = '<p>No products available in this category.</p>';
                return;
            }
            
            let html = '';
            categoryProducts.forEach(product => {
                html += `
                    <div class="product-card">
                        <h3>${product.name}</h3>
                        <div class="product-details">
                            <p><strong>Farmer:</strong> ${product.farmerName}</p>
                            <p><strong>Price:</strong> ₹${product.price} per ${product.unit}</p>
                            <p><strong>Available:</strong> ${product.quantity} ${product.unit}</p>
                            <p><strong>Description:</strong> ${product.description}</p>
                            <p><strong>Phone:</strong> ${product.phone}</p>
                            <p><strong>Address:</strong> ${product.address}</p>
                        </div>
                        <div class="product-actions">
                            <button class="buy-btn" data-product-id="${product.id}">Buy Now</button>
                        </div>
                    </div>
                `;
            });
            
            categoryProductsListElement.innerHTML = html;
            
            // Add event listeners to buy buttons
            document.querySelectorAll('.buy-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const productId = this.getAttribute('data-product-id');
                    alert('Purchase functionality will be implemented in the future!');
                });
            });
        }

        // Event Listeners
        document.addEventListener('DOMContentLoaded', () => {
            initializeLocalStorage();
            
            // Check if user is logged in
            const currentUser = getCurrentUser();
            if (currentUser) {
                document.getElementById('userNameDisplay').textContent = currentUser.name;
                showPage('homePage');
            }
            
            // Auth Navigation
            document.getElementById('showLoginBtn').addEventListener('click', () => showPage('loginPage'));
            document.getElementById('showRegisterBtn').addEventListener('click', () => showPage('registerPage'));
            
            // Register Form
            document.getElementById('registerForm').addEventListener('submit', function(e) {
                e.preventDefault();
                
                const name = document.getElementById('registerName').value;
                const mobile = document.getElementById('registerMobile').value;
                const password = document.getElementById('registerPassword').value;
                
                const result = registerUser(name, mobile, password);
                
                if (result.success) {
                    // Auto-login after registration
                    sessionStorage.setItem('currentUser', JSON.stringify(result.user));
                    document.getElementById('userNameDisplay').textContent = result.user.name;
                    showPage('homePage');
                } else {
                    const alertElement = document.getElementById('registerAlert');
                    alertElement.textContent = result.message;
                    alertElement.style.display = 'block';
                    
                    setTimeout(() => {
                        alertElement.style.display = 'none';
                    }, 3000);
                }
            });
            
            // Login Form
            document.getElementById('loginForm').addEventListener('submit', function(e) {
                e.preventDefault();
                
                const mobile = document.getElementById('loginMobile').value;
                const password = document.getElementById('loginPassword').value;
                
                const result = loginUser(mobile, password);
                
                if (result.success) {
                    document.getElementById('userNameDisplay').textContent = result.user.name;
                    showPage('homePage');
                } else {
                    const alertElement = document.getElementById('loginAlert');
                    alertElement.textContent = result.message;
                    alertElement.style.display = 'block';
                    
                    setTimeout(() => {
                        alertElement.style.display = 'none';
                    }, 3000);
                }
            });
            
            // Logout Button
            document.getElementById('logoutBtn').addEventListener('click', logoutUser);
            
            // Navigation Buttons
            document.getElementById('farmerBtn').addEventListener('click', () => {
                showPage('farmerPage');
                renderFarmerProducts();
            });
            
            document.getElementById('consumerBtn').addEventListener('click', () => {
                showPage('consumerPage');
            });
            
            // Add Product Form
            document.getElementById('addProductForm').addEventListener('submit', function(e) {
                e.preventDefault();
                
                const productData = {
    name: document.getElementById('productName').value,
    category: document.getElementById('productCategory').value,
    price: parseFloat(document.getElementById('productPrice').value),
    quantity: parseInt(document.getElementById('productQuantity').value),
    unit: document.getElementById('productUnit').value,
    description: document.getElementById('productDescription').value,
    phone: document.getElementById('farmerPhone').value,
    address: document.getElementById('farmerAddress').value
};

                
                addProduct(productData);
                renderFarmerProducts();
                
                // Reset form
                this.reset();
                alert('Product added successfully!');
            });
            
            // Category Items
            document.querySelectorAll('.category-item').forEach(item => {
                item.addEventListener('click', function() {
                    const category = this.getAttribute('data-category');
                    renderCategoryProducts(category);
                    showPage('categoryProductsPage');
                });
            });
        });
    </script>
</body>
</html>
