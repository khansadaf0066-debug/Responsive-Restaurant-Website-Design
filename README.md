# Responsive-Restaurant-Website-Design
Front-End Web Designer &amp; Developer
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Urban Spice Kitchen | Authentic Flavors Crafted Fresh</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&family=Poppins:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-red: #D32F2F;
            --dark-red: #B71C1C;
            --orange: #FF6F00;
            --yellow: #FFC107;
            --black: #1a1a1a;
            --dark-gray: #2d2d2d;
            --light-gray: #f5f5f5;
            --white: #ffffff;
        }

        body {
            font-family: 'Poppins', sans-serif;
            line-height: 1.6;
            color: var(--black);
            overflow-x: hidden;
        }

        h1, h2, h3, h4 {
            font-family: 'Playfair Display', serif;
            font-weight: 600;
        }

        /* Navigation */
        .navbar {
            background: var(--black);
            padding: 15px 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.3);
        }

        .navbar .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            color: var(--yellow);
            font-size: 24px;
            font-weight: 700;
            font-family: 'Playfair Display', serif;
        }

        .logo i {
            color: var(--orange);
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 30px;
            align-items: center;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--white);
            font-weight: 500;
            transition: color 0.3s;
            font-size: 15px;
        }

        .nav-links a:hover {
            color: var(--yellow);
        }

        .btn-reserve-nav {
            background: var(--primary-red);
            color: var(--white) !important;
            padding: 10px 25px;
            border-radius: 25px;
            transition: all 0.3s;
        }

        .btn-reserve-nav:hover {
            background: var(--orange);
            transform: translateY(-2px);
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: var(--white);
        }

        /* Hero Section */
        .hero {
            margin-top: 60px;
            background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?w=1200') center/cover;
            min-height: 90vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: var(--white);
            padding: 0 20px;
        }

        .hero-content h1 {
            font-size: 56px;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
            line-height: 1.2;
        }

        .hero-content h1 span {
            color: var(--yellow);
        }

        .hero-content p {
            font-size: 22px;
            margin-bottom: 40px;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }

        .hero-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn-primary {
            background: var(--primary-red);
            color: var(--white);
            padding: 16px 40px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            font-size: 16px;
            transition: all 0.3s;
            display: inline-block;
            border: 2px solid var(--primary-red);
        }

        .btn-primary:hover {
            background: var(--dark-red);
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(211, 47, 47, 0.3);
        }

        .btn-secondary {
            background: transparent;
            color: var(--white);
            padding: 16px 40px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            font-size: 16px;
            transition: all 0.3s;
            display: inline-block;
            border: 2px solid var(--white);
        }

        .btn-secondary:hover {
            background: var(--white);
            color: var(--black);
            transform: translateY(-3px);
        }

        /* Section Styling */
        .section {
            padding: 80px 20px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            font-size: 42px;
            margin-bottom: 20px;
            color: var(--black);
            position: relative;
            padding-bottom: 15px;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(to right, var(--primary-red), var(--orange), var(--yellow));
        }

        .section-subtitle {
            text-align: center;
            color: #666;
            margin-bottom: 50px;
            font-size: 18px;
        }

        /* About Section */
        .about {
            background: var(--light-gray);
        }

        .about-content {
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
            font-size: 18px;
            line-height: 1.8;
            color: #555;
        }

        /* Menu Section */
        .menu-section {
            background: var(--white);
        }

        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }

        .dish-card {
            background: var(--white);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
            transition: transform 0.3s, box-shadow 0.3s;
            border: 1px solid #eee;
        }

        .dish-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.2);
        }

        .dish-image {
            width: 100%;
            height: 220px;
            object-fit: cover;
        }

        .dish-info {
            padding: 25px;
        }

        .dish-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
        }

        .dish-name {
            font-size: 22px;
            color: var(--black);
            font-family: 'Playfair Display', serif;
        }

        .dish-price {
            font-size: 24px;
            font-weight: 700;
            color: var(--primary-red);
        }

        .dish-description {
            color: #666;
            margin-bottom: 15px;
            line-height: 1.6;
        }

        .dish-category {
            display: inline-block;
            background: var(--orange);
            color: var(--white);
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: 600;
        }

        /* Why Choose Us */
        .features {
            background: linear-gradient(135deg, var(--black) 0%, var(--dark-gray) 100%);
            color: var(--white);
        }

        .features .section-title {
            color: var(--white);
        }

        .features .section-title::after {
            background: linear-gradient(to right, var(--orange), var(--yellow));
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }

        .feature-card {
            background: rgba(255,255,255,0.05);
            padding: 35px 25px;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s;
            border: 1px solid rgba(255,255,255,0.1);
        }

        .feature-card:hover {
            background: rgba(255,255,255,0.1);
            transform: translateY(-5px);
        }

        .feature-icon {
            width: 70px;
            height: 70px;
            background: linear-gradient(135deg, var(--primary-red), var(--orange));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            font-size: 28px;
            color: var(--white);
        }

        .feature-card h4 {
            font-size: 20px;
            margin-bottom: 10px;
            color: var(--yellow);
        }

        .feature-card p {
            color: #ccc;
            font-size: 14px;
        }

        /* Testimonials */
        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }

        .testimonial-card {
            background: var(--white);
            padding: 35px;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
            position: relative;
            border-left: 4px solid var(--orange);
        }

        .testimonial-card::before {
            content: '"';
            font-size: 80px;
            color: var(--orange);
            opacity: 0.2;
            position: absolute;
            top: 10px;
            left: 20px;
            font-family: 'Playfair Display', serif;
        }

        .testimonial-text {
            font-style: italic;
            margin-bottom: 20px;
            color: #555;
            line-height: 1.8;
            position: relative;
            z-index: 1;
        }

        .testimonial-author {
            font-weight: 600;
            color: var(--black);
            font-size: 16px;
        }

        .testimonial-rating {
            color: var(--yellow);
            margin-bottom: 10px;
        }

        /* Reservation Section */
        .reservation {
            background: linear-gradient(135deg, var(--primary-red) 0%, var(--dark-red) 100%);
            color: var(--white);
        }

        .reservation .section-title {
            color: var(--white);
        }

        .reservation .section-title::after {
            background: var(--yellow);
        }

        .reservation-form {
            max-width: 600px;
            margin: 40px auto 0;
            background: var(--white);
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.3);
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            color: var(--black);
            font-weight: 500;
        }

        .form-group input,
        .form-group select {
            width: 100%;
            padding: 14px;
            border: 2px solid #ddd;
            border-radius: 10px;
            font-family: 'Poppins', sans-serif;
            font-size: 15px;
            transition: border-color 0.3s;
        }

        .form-group input:focus,
        .form-group select:focus {
            outline: none;
            border-color: var(--orange);
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }

        .btn-submit {
            width: 100%;
            padding: 16px;
            background: linear-gradient(135deg, var(--orange), var(--primary-red));
            color: var(--white);
            border: none;
            border-radius: 10px;
            font-size: 18px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            font-family: 'Poppins', sans-serif;
        }

        .btn-submit:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 20px rgba(211, 47, 47, 0.4);
        }

        .form-message {
            margin-top: 15px;
            text-align: center;
            padding: 10px;
            border-radius: 5px;
            display: none;
        }

        .form-message.success {
            background: #d4edda;
            color: #155724;
            display: block;
        }

        .form-message.error {
            background: #f8d7da;
            color: #721c24;
            display: block;
        }

        /* Footer */
        footer {
            background: var(--black);
            color: var(--white);
            padding: 60px 20px 30px;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-section h3 {
            color: var(--yellow);
            margin-bottom: 20px;
            font-size: 22px;
        }

        .footer-section p,
        .footer-section a {
            color: #aaa;
            text-decoration: none;
            line-height: 1.8;
            transition: color 0.3s;
        }

        .footer-section a:hover {
            color: var(--orange);
        }

        .footer-section i {
            margin-right: 10px;
            color: var(--orange);
            width: 20px;
        }

        .social-icons {
            display: flex;
            gap: 15px;
            margin-top: 15px;
        }

        .social-icons a {
            width: 40px;
            height: 40px;
            background: rgba(255,255,255,0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s;
        }

        .social-icons a:hover {
            background: var(--primary-red);
            transform: translateY(-3px);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid #333;
            color: #777;
            font-size: 14px;
        }

        /* Modal for Menu */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.8);
            z-index: 2000;
            overflow-y: auto;
        }

        .modal-content {
            background: var(--white);
            max-width: 900px;
            margin: 50px auto;
            padding: 40px;
            border-radius: 20px;
            position: relative;
            animation: modalSlide 0.3s;
        }

        @keyframes modalSlide {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .close-modal {
            position: absolute;
            top: 20px;
            right: 20px;
            font-size: 30px;
            cursor: pointer;
            color: var(--black);
            width: 40px;
            height: 40px;
            background: var(--light-gray);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s;
        }

        .close-modal:hover {
            background: var(--primary-red);
            color: var(--white);
            transform: rotate(90deg);
        }

        .menu-category {
            margin-bottom: 40px;
        }

        .menu-category h3 {
            color: var(--primary-red);
            font-size: 28px;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 3px solid var(--orange);
        }

        .menu-item {
            display: flex;
            justify-content: space-between;
            align-items: start;
            padding: 15px 0;
            border-bottom: 1px dashed #ddd;
        }

        .menu-item-info h4 {
            color: var(--black);
            margin-bottom: 5px;
        }

        .menu-item-info p {
            color: #666;
            font-size: 14px;
        }

        .menu-item-price {
            font-weight: 700;
            color: var(--primary-red);
            font-size: 18px;
            white-space: nowrap;
            margin-left: 20px;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
                position: absolute;
                top: 100%;
                left: 0;
                right: 0;
                background: var(--black);
                flex-direction: column;
                padding: 20px;
                gap: 15px;
            }

            .nav-links.active {
                display: flex;
            }

            .mobile-menu-btn {
                display: block;
            }

            .hero-content h1 {
                font-size: 36px;
            }

            .hero-content p {
                font-size: 18px;
            }

            .form-row {
                grid-template-columns: 1fr;
            }

            .section-title {
                font-size: 32px;
            }

            .hero-buttons {
                flex-direction: column;
                align-items: center;
            }

            .btn-primary,
            .btn-secondary {
                width: 100%;
                max-width: 300px;
                text-align: center;
            }
        }

        /* Scroll to top button */
        .scroll-top {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 50px;
            height: 50px;
            background: var(--primary-red);
            color: var(--white);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            opacity: 0;
            transition: all 0.3s;
            z-index: 999;
            box-shadow: 0 5px 15px rgba(211, 47, 47, 0.3);
        }

        .scroll-top.visible {
            opacity: 1;
        }

        .scroll-top:hover {
            background: var(--orange);
            transform: translateY(-5px);
        }
    </style>
</head>
<body>

    <!-- Navigation -->
    <nav class="navbar">
        <div class="container">
            <div class="logo">
                <i class="fas fa-utensils"></i>
                <span>Urban Spice Kitchen</span>
            </div>
            <button class="mobile-menu-btn" onclick="toggleMenu()">
                <i class="fas fa-bars"></i>
            </button>
            <ul class="nav-links" id="navLinks">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#menu" onclick="openMenuModal()">Menu</a></li>
                <li><a href="#features">Why Us</a></li>
                <li><a href="#testimonials">Reviews</a></li>
                <li><a href="#reservation" class="btn-reserve-nav">Reserve Table</a></li>
            </ul>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Authentic Flavors <span>Crafted Fresh</span> Every Day</h1>
            <p>Experience a perfect blend of traditional recipes and modern dining.</p>
            <div class="hero-buttons">
                <a href="#" class="btn-primary" onclick="openMenuModal(); return false;">
                    <i class="fas fa-book-open"></i> View Menu
                </a>
                <a href="#reservation" class="btn-secondary">
                    <i class="fas fa-calendar-check"></i> Reserve Table
                </a>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="section about">
        <h2 class="section-title">Our Story</h2>
        <p class="section-subtitle">Passion on Every Plate</p>
        <div class="about-content">
            <p>Urban Spice Kitchen was founded with a simple goal: serving delicious food made from fresh ingredients while creating memorable dining experiences. Our chefs bring years of expertise, combining time-honored traditions with innovative culinary techniques. Every dish tells a story of flavor, passion, and dedication to excellence.</p>
        </div>
    </section>

    <!-- Popular Dishes Section -->
    <section id="menu" class="section menu-section">
        <h2 class="section-title">Popular Dishes</h2>
        <p class="section-subtitle">Customer Favorites</p>
        <div class="menu-grid">
            <div class="dish-card">
                <img src="https://images.unsplash.com/photo-1603894584373-5ac82b2ae398?w=400" alt="Butter Chicken" class="dish-image">
                <div class="dish-info">
                    <div class="dish-header">
                        <h3 class="dish-name">Butter Chicken</h3>
                        <span class="dish-price">₹349</span>
                    </div>
                    <p class="dish-description">Rich creamy tomato gravy with tender chicken pieces, cooked in tandoor and finished with butter and cream.</p>
                    <span class="dish-category">Main Course</span>
                </div>
            </div>

            <div class="dish-card">
                <img src="https://images.unsplash.com/photo-1567188040759-fb8a883dc6d8?w=400" alt="Paneer Tikka" class="dish-image">
                <div class="dish-info">
                    <div class="dish-header">
                        <h3 class="dish-name">Paneer Tikka</h3>
                        <span class="dish-price">₹299</span>
                    </div>
                    <p class="dish-description">Chargrilled cottage cheese marinated in yogurt and aromatic spices, served with mint chutney.</p>
                    <span class="dish-category">Appetizer</span>
                </div>
            </div>

            <div class="dish-card">
                <img src="https://images.unsplash.com/photo-1563379091339-03b21ab4a4f8?w=400" alt="Chicken Biryani" class="dish-image">
                <div class="dish-info">
                    <div class="dish-header">
                        <h3 class="dish-name">Chicken Biryani</h3>
                        <span class="dish-price">₹329</span>
                    </div>
                    <p class="dish-description">Aromatic basmati rice layered with spiced chicken, saffron, and fried onions. Served with raita.</p>
                    <span class="dish-category">Main Course</span>
                </div>
            </div>

            <div class="dish-card">
                <img src="https://images.unsplash.com/photo-1599487488170-d11ec9c172f0?w=400" alt="Tandoori Platter" class="dish-image">
                <div class="dish-info">
                    <div class="dish-header">
                        <h3 class="dish-name">Tandoori Platter</h3>
                        <span class="dish-price">₹549</span>
                    </div>
                    <p class="dish-description">Mixed grilled specialties including chicken tikka, seekh kebab, fish tikka, and paneer tikka.</p>
                    <span class="dish-category">For Sharing</span>
                </div>
            </div>
        </div>
        <div style="text-align: center; margin-top: 40px;">
            <button class="btn-primary" onclick="openMenuModal()">
                <i class="fas fa-list"></i> View Full Menu
            </button>
        </div>
    </section>

    <!-- Why Choose Us Section -->
    <section id="features" class="section features">
        <h2 class="section-title">Why Dine With Us</h2>
        <p class="section-subtitle" style="color: #ccc;">The Urban Spice Difference</p>
        <div class="features-grid">
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-leaf"></i>
                </div>
                <h4>Fresh Ingredients</h4>
                <p>We source only the freshest, highest quality ingredients for every dish we serve.</p>
            </div>

            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-user-tie"></i>
                </div>
                <h4>Experienced Chefs</h4>
                <p>Our master chefs bring decades of culinary expertise and passion to your plate.</p>
            </div>

            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-users"></i>
                </div>
                <h4>Family Friendly</h4>
                <p>A warm, welcoming atmosphere perfect for family gatherings and celebrations.</p>
            </div>

            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-calendar-check"></i>
                </div>
                <h4>Online Reservations</h4>
                <p>Book your table easily online with instant confirmation and flexible timing.</p>
            </div>

            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-bolt"></i>
                </div>
                <h4>Fast Service</h4>
                <p>Quick, attentive service without compromising on quality or taste.</p>
            </div>

            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-wine-glass-alt"></i>
                </div>
                <h4>Great Ambiance</h4>
                <p>Modern decor with traditional touches creates the perfect dining environment.</p>
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section id="testimonials" class="section">
        <h2 class="section-title">Customer Reviews</h2>
        <p class="section-subtitle">What Our Guests Say</p>
        <div class="testimonials-grid">
            <div class="testimonial-card">
                <div class="testimonial-rating">
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                </div>
                <p class="testimonial-text">Best biryani I've had in Mumbai. The flavors are authentic and the portions are generous. Will definitely come back again!</p>
                <div class="testimonial-author">— Aman M.</div>
            </div>

            <div class="testimonial-card">
                <div class="testimonial-rating">
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                </div>
                <p class="testimonial-text">Beautiful ambiance and excellent service. The butter chicken is to die for. Perfect spot for date night or family dinner.</p>
                <div class="testimonial-author">— Sarah D.</div>
            </div>

            <div class="testimonial-card">
                <div class="testimonial-rating">
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                </div>
                <p class="testimonial-text">Perfect place for family dinners. The staff is incredibly friendly and the food is consistently delicious. Highly recommend the tandoori platter!</p>
                <div class="testimonial-author">— Rohit P.</div>
            </div>
        </div>
    </section>

    <!-- Reservation Section -->
    <section id="reservation" class="section reservation">
        <h2 class="section-title">Reserve a Table</h2>
        <p class="section-subtitle" style="color: rgba(255,255,255,0.9);">Book Your Dining Experience</p>
        <form class="reservation-form" id="reservationForm">
            <div class="form-group">
                <label for="name"><i class="fas fa-user"></i> Full Name</label>
                <input type="text" id="name" placeholder="Enter your full name" required>
            </div>

            <div class="form-group">
                <label for="phone"><i class="fas fa-phone"></i> Phone Number</label>
                <input type="tel" id="phone" placeholder="Enter your phone number" required>
            </div>

            <div class="form-row">
                <div class="form-group">
                    <label for="guests"><i class="fas fa-users"></i> Number of Guests</label>
                    <select id="guests" required>
                        <option value="">Select guests</option>
                        <option value="1">1 Person</option>
                        <option value="2">2 People</option>
                        <option value="3">3 People</option>
                        <option value="4">4 People</option>
                        <option value="5">5 People</option>
                        <option value="6">6 People</option>
                        <option value="7+">7+ People</option>
                    </select>
                </div>

                <div class="form-group">
                    <label for="date"><i class="fas fa-calendar"></i> Date</label>
                    <input type="date" id="date" required>
                </div>
            </div>

            <div class="form-row">
                <div class="form-group">
                    <label for="time"><i class="fas fa-clock"></i> Time</label>
                    <select id="time" required>
                        <option value="">Select time</option>
                        <option value="11:00 AM">11:00 AM</option>
                        <option value="11:30 AM">11:30 AM</option>
                        <option value="12:00 PM">12:00 PM</option>
                        <option value="12:30 PM">12:30 PM</option>
                        <option value="01:00 PM">01:00 PM</option>
                        <option value="01:30 PM">01:30 PM</option>
                        <option value="02:00 PM">02:00 PM</option>
                        <option value="07:00 PM">07:00 PM</option>
                        <option value="07:30 PM">07:30 PM</option>
                        <option value="08:00 PM">08:00 PM</option>
                        <option value="08:30 PM">08:30 PM</option>
                        <option value="09:00 PM">09:00 PM</option>
                        <option value="09:30 PM">09:30 PM</option>
                        <option value="10:00 PM">10:00 PM</option>
                    </select>
                </div>

                <div class="form-group">
                    <label for="occasion"><i class="fas fa-gift"></i> Occasion (Optional)</label>
                    <select id="occasion">
                        <option value="">Select occasion</option>
                        <option value="Birthday">Birthday</option>
                        <option value="Anniversary">Anniversary</option>
                        <option value="Date Night">Date Night</option>
                        <option value="Family Dinner">Family Dinner</option>
                        <option value="Business Meeting">Business Meeting</option>
                        <option value="Other">Other</option>
                    </select>
                </div>
            </div>

            <button type="submit" class="btn-submit">
                <i class="fas fa-calendar-check"></i> Reserve Now
            </button>
            <div id="formMessage" class="form-message"></div>
        </form>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h3><i class="fas fa-utensils"></i> Urban Spice Kitchen</h3>
                <p>Experience authentic flavors crafted with passion and the freshest ingredients. Your satisfaction is our priority.</p>
                <div class="social-icons">
                    <a href="#" aria-label="Facebook"><i class="fab fa-facebook-f"></i></a>
                    <a href="#" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
                    <a href="#" aria-label="Twitter"><i class="fab fa-twitter"></i></a>
                    <a href="#" aria-label="WhatsApp"><i class="fab fa-whatsapp"></i></a>
                </div>
            </div>

            <div class="footer-section">
                <h3><i class="fas fa-map-marker-alt"></i> Visit Us</h3>
                <p>
                    <i class="fas fa-location-dot"></i> 123 Spice Market Road,<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Kurla West, Mumbai - 400070<br>
                    <i class="fas fa-phone"></i> +91 9221486538<br>
                    <i class="fas fa-envelope"></i> info@urbanspicekitchen.com
                </p>
            </div>

            <div class="footer-section">
                <h3><i class="fas fa-clock"></i> Opening Hours</h3>
                <p>
                    <i class="fas fa-calendar-day"></i> Monday - Friday<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;11:00 AM - 11:00 PM<br>
                    <i class="fas fa-calendar-day"></i> Saturday - Sunday<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;10:00 AM - 12:00 AM
                </p>
            </div>

            <div class="footer-section">
                <h3><i class="fas fa-link"></i> Quick Links</h3>
                <p>
                    <a href="#home">Home</a><br>
                    <a href="#about">About Us</a><br>
                    <a href="#" onclick="openMenuModal(); return false;">Our Menu</a><br>
                    <a href="#reservation">Reservations</a><br>
                    <a href="#testimonials">Reviews</a>
                </p>
            </div>
        </div>

        <div class="footer-bottom">
            <p>&copy; 2025 Urban Spice Kitchen. All Rights Reserved. | Crafted with <i class="fas fa-heart" style="color: var(--primary-red);"></i> for food lovers</p>
        </div>
    </footer>

    <!-- Full Menu Modal -->
    <div id="menuModal" class="modal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeMenuModal()">&times;</span>
            <h2 class="section-title" style="margin-bottom: 30px;">Our Complete Menu</h2>
            
            <div class="menu-category">
                <h3><i class="fas fa-drumstick-bite"></i> Appetizers</h3>
                <div class="menu-item">
                    <div class="menu-item-info">
                        <h4>Paneer Tikka</h4>
                        <p>Chargrilled cottage cheese with spices</p>
                    </div>
                    <div class="menu-item-price">₹299</div>
                </div>
                <div class="menu-item">
                    <div class="menu-item-info">
                        <h4>Chicken Tikka</h4>
                        <p>Boneless chicken marinated in yogurt and spices</p>
                    </div>
                    <div class="menu-item-price">₹349</div>
                </div>
                <div class="menu-item">
                    <div class="menu-item-info">
                        <h4>Seekh Kebab</h4>
                        <p>Minced meat skewers with aromatic herbs</p>
                    </div>
                    <div class="menu-item-price">₹329</div>
                </div>
                <div class="menu-item">
                    <div class="menu-item-info">
                        <h4>Vegetable Samosa (2 pcs)</h4>
                        <p>Crispy pastry filled with spiced potatoes</p>
                    </div>
                    <div class="menu-item-price">₹149</div>
                </div>
            </div>

            <div class="menu-category">
                <h3><i class="fas fa-utensils"></i> Main Course</h3>
                <div class="menu-item">
                    <div class="menu-item-info">
                        <h4>Butter Chicken</h4>
                        <p>Creamy tomato gravy with tandoori chicken</p>
                    </div>
                    <div class="menu-item-price">₹349</div>
                </div>
                <div class="menu-item">
                    <div class="menu-item-info">
                        <h4>Chicken Biryani</h4>
                        <p>Aromatic rice with spiced chicken and saffron</p>
                    </div>
                    <div class="menu-item-price">₹329</div>
                </div>
                <div class="menu-item">
                    <div class="menu-item-info">
                        <h4>Paneer Butter Masala</h4>
                        <p>Cottage cheese in rich tomato cream gravy</p>
                    </div>
                    <div class="menu-item-price">₹299</div>
                </div>
                <div class="menu-item">
                    <div class="menu-item-info">
                        <h4>Lamb Rogan Josh</h4>
                        <p>Tender lamb in aromatic Kashmiri gravy</p>
                    </div>
                    <div class="menu-item-price">₹449</div>
                </div>
                <div class="menu-item">
                    <div class="menu-item-info">
                        <h4>Fish Curry</h4>
                        <p>Fresh fish in coconut based curry</p>
                    </div>
                    <div class="menu-item-price">₹379</div>
                </div>
            </div>

            <div class="menu-category">
                <h3><i class="fas fa-bread-slice"></i> Breads</h3>
                <div class="menu-item">
                    <div class="menu-item-info">
                        <h4>Butter Naan</h4>
                        <p>Soft leavened bread with butter</p>
                    </div>
                    <div class="menu-item-price">₹89</div>
                </div>
                <div class="menu-item">
                    <div class="menu-item-info">
                        <h4>Garlic Naan</h4>
                        <p>Naan topped with fresh garlic and coriander</p>
                    </div>
                    <div class="menu-item-price">₹109</div>
                </div>
                <div class="menu-item">
                    <div class="menu-item-info">
                        <h4>Tandoori Roti</h4>
                        <p>Whole wheat bread from clay oven</p>
                    </div>
                    <div class="menu-item-price">₹69</div>
                </div>
                <div class="menu-item">
                    <div class="menu-item-info">
                        <h4>Stuffed Kulcha</h4>
                        <p>Bread stuffed with spiced potatoes</p>
                    </div>
                    <div class="menu-item-price">₹129</div>
                </div>
            </div>

            <div class="menu-category">
                <h3><i class="fas fa-ice-cream"></i> Desserts</h3>
                <div class="menu-item">
                    <div class="menu-item-info">
                        <h4>Gulab Jamun (2 pcs)</h4>
                        <p>Fried milk solids in sugar syrup</p>
                    </div>
                    <div class="menu-item-price">₹149</div>
                </div>
                <div class="menu-item">
                    <div class="menu-item-info">
                        <h4>Rasmalai</h4>
                        <p>Cottage cheese dumplings in sweet milk</p>
                    </div>
                    <div class="menu-item-price">₹169</div>
                </div>
                <div class="menu-item">
                    <div class="menu-item-info">
                        <h4>Kulfi</h4>
                        <p>Traditional Indian ice cream</p>
                    </div>
                    <div class="menu-item-price">₹129</div>
                </div>
            </div>

            <div class="menu-category">
                <h3><i class="fas fa-glass-water"></i> Beverages</h3>
                <div class="menu-item">
                    <div class="menu-item-info">
                        <h4>Masala Chai</h4>
                        <p>Spiced Indian tea</p>
                    </div>
                    <div class="menu-item-price">₹79</div>
                </div>
                <div class="menu-item">
                    <div class="menu-item-info">
                        <h4>Mango Lassi</h4>
                        <p>Yogurt drink with mango</p>
                    </div>
                    <div class="menu-item-price">₹149</div>
                </div>
                <div class="menu-item">
                    <div class="menu-item-info">
                        <h4>Fresh Lime Soda</h4>
                        <p>Sweet or salty lime drink</p>
                    </div>
                    <div class="menu-item-price">₹99</div>
                </div>
            </div>
        </div>
    </div>

    <!-- Scroll to Top Button -->
    <div class="scroll-top" id="scrollTop" onclick="scrollToTop()">
        <i class="fas fa-arrow-up"></i>
    </div>

    <script>
        // Mobile Menu Toggle
        function toggleMenu() {
            document.getElementById('navLinks').classList.toggle('active');
        }

        // Close mobile menu when clicking on a link
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                document.getElementById('navLinks').classList.remove('active');
            });
        });

        // Smooth Scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                const href = this.getAttribute('href');
                if (href !== '#' && !this.onclick) {
                    e.preventDefault();
                    const target = document.querySelector(href);
                    if (target) {
                        target.scrollIntoView({
                            behavior: 'smooth',
                            block: 'start'
                        });
                    }
                }
            });
        });

        // Modal Functions
        function openMenuModal() {
            document.getElementById('menuModal').style.display = 'block';
            document.body.style.overflow = 'hidden';
        }

        function closeMenuModal() {
            document.getElementById('menuModal').style.display = 'none';
            document.body.style.overflow = 'auto';
        }

        // Close modal when clicking outside
        window.onclick = function(event) {
            const modal = document.getElementById('menuModal');
            if (event.target === modal) {
                closeMenuModal();
            }
        }

        // Reservation Form Handling
        document.getElementById('reservationForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const name = document.getElementById('name').value.trim();
            const phone = document.getElementById('phone').value.trim();
            const guests = document.getElementById('guests').value;
            const date = document.getElementById('date').value;
            const time = document.getElementById('time').value;
            const occasion = document.getElementById('occasion').value;
            
            // Validation
            if (!name || !phone || !guests || !date || !time) {
                showMessage('Please fill in all required fields.', 'error');
                return;
            }
            
            // Phone validation (Indian format)
            const phoneRegex = /^[6-9]\d{9}$/;
            if (!phoneRegex.test(phone.replace(/\s/g, ''))) {
                showMessage('Please enter a valid 10-digit mobile number.', 'error');
                return;
            }
            
            // Date validation (should be today or future)
            const selectedDate = new Date(date);
            const today = new Date();
            today.setHours(0, 0, 0, 0);
            if (selectedDate < today) {
                showMessage('Please select a future date.', 'error');
                return;
            }
            
            // Success - Create WhatsApp message
            let message = `*New Table Reservation*%0A%0A`;
            message += `*Name:* ${name}%0A`;
            message += `*Phone:* ${phone}%0A`;
            message += `*Guests:* ${guests}%0A`;
            message += `*Date:* ${date}%0A`;
            message += `*Time:* ${time}%0A`;
            if (occasion) {
                message += `*Occasion:* ${occasion}%0A`;
            }
            message += `%0AI would like to reserve a table at Urban Spice Kitchen.`;
            
            // Show success message
            showMessage('Reservation request submitted! Redirecting to WhatsApp...', 'success');
            
            // Open WhatsApp after 1.5 seconds
            setTimeout(() => {
                window.open(`https://wa.me/919221486538?text=${message}`, '_blank');
                // Reset form
                this.reset();
                setTimeout(() => {
                    showMessage('', '');
                }, 3000);
            }, 1500);
        });

        function showMessage(text, type) {
            const messageDiv = document.getElementById('formMessage');
            messageDiv.textContent = text;
            messageDiv.className = 'form-message ' + type;
        }

        // Scroll to Top Button
        window.onscroll = function() {
            const scrollTop = document.getElementById('scrollTop');
            if (document.body.scrollTop > 300 || document.documentElement.scrollTop > 300) {
                scrollTop.classList.add('visible');
            } else {
                scrollTop.classList.remove('visible');
            }
        };

        function scrollToTop() {
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        }

        // Set minimum date to today for reservation
        document.addEventListener('DOMContentLoaded', function() {
            const dateInput = document.getElementById('date');
            const today = new Date().toISOString().split('T')[0];
            dateInput.setAttribute('min', today);
        });

        // Add active class to navbar on scroll
        window.addEventListener('scroll', function() {
            const navbar = document.querySelector('.navbar');
            if (window.scrollY > 50) {
                navbar.style.background = 'rgba(26, 26, 26, 0.95)';
            } else {
                navbar.style.background = 'var(--black)';
            }
        });
    </script>
</body>
</html>
