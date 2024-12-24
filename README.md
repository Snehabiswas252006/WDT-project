<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gadget Zone - Shop Electronics</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <style>
        /* General Styles */
        body {
            font-family: 'Poppins', sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
            overflow-x: hidden;
        }
        h1, h2, h3 {
            color: #fff;
            font-weight: 600;
        }
        .nav-link {
            color: #ffffff !important;
            font-weight: 500;
        }
        .nav-link:hover {
            color: #ff6347 !important;
        }

        /* Header Styles */
        header {
            background: #0a0a0a;
            padding: 20px 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 9999;
            opacity: 0;
            animation: fadeIn 1s ease-in-out forwards 0.5s;
        }
        .navbar {
            max-width: 1200px;
            margin: 0 auto;
        }
        .navbar-brand {
            color: #ff6347;
            font-size: 28px;
            font-weight: 700;
        }

        /* Hero Section */
        .hero {
            background: url('https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRE4OS-V3FPNIqAstLOULPH9Y7bG7LjFFjPmw&s') no-repeat center center;
            background-size:cover;
            height: 100vh;
            color: white;
            text-align: center;
            display: flex;
            flex-direction: column;
            justify-content: center;
            animation: fadeInHero 1.5s ease-in-out forwards;
        }
        .hero h1 {
            font-size: 60px;
            font-weight: 700;
            margin-bottom: 20px;
            text-transform: uppercase;
            background-color: purple;
            padding: 10px 20px;
            animation: slideInLeft 1s ease-out forwards;
        }
        .hero p {
            background-color: plum;
            padding: 10px 20px;
            animation: fadeIn 2s ease-in-out forwards;
            color:black;
        }
        .hero .btn-primary {
            background-color: rgb(248, 176, 188);
            color: black;
            padding: 10px 30px;
            font-size: 18px;
            border-radius: 30px;
            transition: background-color 0.3s ease;
            animation: bounce 2s infinite;
        }
        .hero .btn-primary:hover {
            background-color: palevioletred;
        }

        /* Product Section */
        .products {
            padding: 50px 0;
            background-color: #fff;
            text-align: center;
            animation: slideIn 2s ease-out;
        }
        .product-card {
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            transition: transform 0.3s ease-in-out;
            margin-bottom: 30px;
            opacity: 0;
            animation: fadeInProduct 2s ease-in-out forwards;
        }
        .product-card:hover {
            transform: scale(1.05);
        }
        .product-card img {
            width: 100%;
            border-radius: 8px;
        }
        .product-card .card-body {
            background-color: #f8f8f8;
            padding: 20px;
        }
        .product-card .card-title {
            font-size: 22px;
            color: #333;
            font-weight: 600;
        }
        .product-card .btn-info {
            background-color: #ff6347;
            color: white;
            border-radius: 25px;
            transition: background-color 0.3s ease;
        }
        .product-card .btn-info:hover {
            background-color: #ff4500;
        }

        /* Footer Section */
        footer {
            background-color: #333;
            color: #fff;
            padding: 20px 0;
            text-align: center;
            font-size: 14px;
            opacity: 0;
            animation: fadeInFooter 2s ease-in-out forwards 1s;
        }

        /* Animations */
        @keyframes fadeIn {
            0% { opacity: 0; }
            100% { opacity: 1; }
        }

        @keyframes fadeInHero {
            0% { opacity: 0; }
            100% { opacity: 1; }
        }

        @keyframes fadeInProduct {
            0% { opacity: 0; }
            100% { opacity: 1; }
        }

        @keyframes fadeInFooter {
            0% { opacity: 0; }
            100% { opacity: 1; }
        }

        @keyframes slideIn {
            0% { transform: translateY(100px); opacity: 0; }
            100% { transform: translateY(0); opacity: 1; }
        }

        @keyframes slideInLeft {
            0% { transform: translateX(-100px); opacity: 0; }
            100% { transform: translateX(0); opacity: 1; }
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {
                transform: translateY(0);
            }
            40% {
                transform: translateY(-10px);
            }
            60% {
                transform: translateY(-5px);
            }
        }
    </style>
</head>
<body>

    <!-- Header -->
    <header>
        <nav class="navbar navbar-expand-lg navbar-dark">
            <div class="container">
                <img src="data:image/jpeg;base64,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" alt="logo" width="50">
                <a class="navbar-brand" href="#">Ambrosia:An alluring aura</a>
                <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse" id="navbarNav">
                    <ul class="navbar-nav ms-auto">
                        <li class="nav-item"><a class="nav-link" href="./home.html">Home</a></li>
                        <li class="nav-item"><a class="nav-link" href="./shop.html">Shop</a></li>
                        <li class="nav-item"><a class="nav-link" href="./aboutus.html">About Us</a></li>
                        <li class="nav-item"><a class="nav-link" href="./contact.html">Contact</a></li>
                        <li class="nav-item"><a class="nav-link" href="./login2.html">Login</a></li>
                        <li class="nav-item"><a class="nav-link" href="./createnew.html">Create</a></li>
                    </ul>
                </div>
            </div>
        </nav>
    </header>

    <!-- Hero Section -->
    <div class="hero">
        <h1>Explore the Latest Kpop Merch</h1>
        <p>Your one-stop shop for the best kpop merches.</p>
        <a href="#products" class="btn btn-primary">Shop Now</a>
    </div>

    <!-- Products Section -->
    <div class="container products" id="products">
        <h2>Featured Products</h2>
        <div class="row">
            <!-- Product 1 -->
            <div class="col-md-4">
                <div class="card product-card">
                    <img src="data:image/jpeg;base64,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" class="card-img-top" alt="Smartphone">
                    <div class="card-body">
                        <h5 class="card-title">Albums and Photobooks</h5>
                        <a href="./mobile.html" class="btn btn-info">Explore Now</a>
                    </div>
                </div>
            </div>
            <!-- Product 2 -->
            <div class="col-md-4">
                <div class="card product-card">
                    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTZyvEvnJbSYLWBCfA5kBN2EXREPxMuWpX4cA&s" class="card-img-top" alt="Laptop">
                    <div class="card-body">
                        <h5 class="card-title">Lightsticks</h5>
                        <a href="./laptop.html" class="btn btn-info">Explore Now</a>
                    </div>
                </div>
            </div>
            <!-- Product 3 -->
            <div class="col-md-4">
                <div class="card product-card">
                    <img src="data:image/jpeg;base64,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" class="card-img-top" alt="Wireless Headphones">
                    <div class="card-body">
                        <h5 class="card-title">Kpop Combo Tshirts</h5>
                        <a href="./headphone.html" class="btn btn-info">Explore Now</a>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <p>&copy; 2024 Ambrosia. All rights reserved.</p>
    </footer>

    <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.11.6/dist/umd/popper.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.0/dist/js/bootstrap.min.js"></script>
</body>
</html>
