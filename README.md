# dojashop
i g
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EliteFashion - Premium Clothing Brand</title>
    <style>
        /* Reset and Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            color: #333;
            scroll-behavior: smooth;
        }

        /* Color Palette */
        :root {
            --primary-color: #1a1a1a;
            --secondary-color: #f5f5f5;
            --accent-color: #e74c3c;
            --text-color: #333;
            --light-gray: #f8f8f8;
            --dark-gray: #666;
        }

        /* Typography */
        h1, h2, h3, h4, h5, h6 {
            font-weight: 700;
            margin-bottom: 1rem;
        }

        h1 {
            font-size: 3rem;
        }

        h2 {
            font-size: 2.5rem;
        }

        h3 {
            font-size: 2rem;
        }

        p {
            margin-bottom: 1rem;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(26, 26, 26, 0.9);
            backdrop-filter: blur(10px);
            z-index: 1000;
            transition: all 0.3s ease;
        }

        nav.scrolled {
            background: rgba(26, 26, 26, 1);
        }

        nav .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            color: #fff;
            font-size: 1.8rem;
            font-weight: 700;
            text-decoration: none;
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 2rem;
        }

        .nav-links a {
            color: #fff;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s ease;
        }

        .nav-links a:hover {
            color: var(--accent-color);
        }

        /* Back to Top Button */
        .back-to-top {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            background: var(--accent-color);
            color: #fff;
            border: none;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            cursor: pointer;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s ease;
            z-index: 1000;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
        }

        .back-to-top.show {
            opacity: 1;
            visibility: visible;
        }

        .back-to-top:hover {
            background: #c0392b;
            transform: translateY(-3px);
        }

        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            z-index: 2000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
        }

        .modal-content {
            background-color: #fff;
            margin: 10% auto;
            padding: 2rem;
            border-radius: 10px;
            width: 90%;
            max-width: 500px;
            position: relative;
        }

        .close {
            position: absolute;
            top: 1rem;
            right: 1rem;
            font-size: 2rem;
            cursor: pointer;
            color: var(--dark-gray);
        }

        .close:hover {
            color: var(--primary-color);
        }

        .order-form input,
        .order-form select {
            width: 100%;
            padding: 0.75rem;
            margin-bottom: 1rem;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-family: inherit;
        }

        .order-form button {
            background: var(--accent-color);
            color: #fff;
            border: none;
            padding: 0.75rem 1.5rem;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 600;
            transition: background 0.3s ease;
        }

        .order-form button:hover {
            background: #c0392b;
        }

        /* Back to Top Button */
        .back-to-top {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            background: var(--accent-color);
            color: #fff;
            border: none;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            cursor: pointer;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s ease;
            z-index: 1000;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
        }

        .back-to-top.show {
            opacity: 1;
            visibility: visible;
        }

        .back-to-top:hover {
            background: #c0392b;
            transform: translateY(-3px);
        }

        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            z-index: 2000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
        }

        .modal-content {
            background-color: #fff;
            margin: 10% auto;
            padding: 2rem;
            border-radius: 10px;
            width: 90%;
            max-width: 500px;
            position: relative;
        }

        .close {
            position: absolute;
            top: 1rem;
            right: 1rem;
            font-size: 2rem;
            cursor: pointer;
            color: var(--dark-gray);
        }

        .close:hover {
            color: var(--primary-color);
        }

        .order-form input,
        .order-form select {
            width: 100%;
            padding: 0.75rem;
            margin-bottom: 1rem;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-family: inherit;
        }

        .order-form button {
            background: var(--accent-color);
            color: #fff;
            border: none;
            padding: 0.75rem 1.5rem;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 600;
            transition: background 0.3s ease;
        }

        .order-form button:hover {
            background: #c0392b;
        }

        .hamburger {
            display: none;
            flex-direction: column;
            cursor: pointer;
        }

        .hamburger span {
            width: 25px;
            height: 3px;
            background: #fff;
            margin: 3px 0;
            transition: 0.3s;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('https://images.unsplash.com/photo-1441986300917-64674bd600d8?ixlib=rb-4.0.3&auto=format&fit=crop&w=1350&q=80') center/cover no-repeat;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: #fff;
        }

        .hero-content {
            max-width: 800px;
            padding: 2rem;
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            animation: fadeInUp 1s ease-out;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            animation: fadeInUp 1.2s ease-out;
        }

        .btn {
            display: inline-block;
            padding: 1rem 2rem;
            background: var(--accent-color);
            color: #fff;
            text-decoration: none;
            border-radius: 5px;
            font-weight: 600;
            transition: all 0.3s ease;
            border: 2px solid var(--accent-color);
        }

        .btn:hover {
            background: transparent;
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(231, 76, 60, 0.3);
        }

        .btn-secondary {
            background: transparent;
            border: 2px solid #fff;
            margin-left: 1rem;
        }

        .btn-secondary:hover {
            background: #fff;
            color: var(--primary-color);
        }

        /* Sections */
        section {
            padding: 5rem 2rem;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        /* Products Section */
        .products {
            background: var(--secondary-color);
        }

        .products h2 {
            text-align: center;
            margin-bottom: 3rem;
            color: var(--primary-color);
        }

        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .product-card {
            background: #fff;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.6s ease;
        }

        .product-card.animate {
            opacity: 1;
            transform: translateY(0);
        }

        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
        }

        .product-image {
            height: 300px;
            background-size: cover;
            background-position: center;
            position: relative;
            overflow: hidden;
        }

        .product-overlay {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(231, 76, 60, 0.8);
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .product-card:hover .product-overlay {
            opacity: 1;
        }

        .product-info {
            padding: 1.5rem;
        }

        .product-name {
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
            color: var(--primary-color);
        }

        .product-price {
            font-size: 1.1rem;
            color: var(--accent-color);
            font-weight: 600;
        }

        /* About Section */
        .about {
            background: var(--primary-color);
            color: #fff;
        }

        .about .container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }

        .about-text h3 {
            color: #fff;
        }

        /* Contact Section */
        .contact {
            background: var(--light-gray);
        }

        .contact .container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
        }

        .contact-form input,
        .contact-form textarea {
            width: 100%;
            padding: 1rem;
            margin-bottom: 1rem;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-family: inherit;
        }

        .contact-form button {
            background: var(--accent-color);
            color: #fff;
            border: none;
            padding: 1rem 2rem;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 600;
            transition: background 0.3s ease;
        }

        .contact-form button:hover {
            background: #c0392b;
        }

        /* Footer */
        footer {
            background: var(--primary-color);
            color: #fff;
            padding: 3rem 2rem 1rem;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .footer-section h4 {
            margin-bottom: 1rem;
        }

        .footer-section p,
        .footer-section a {
            color: #ccc;
            text-decoration: none;
            margin-bottom: 0.5rem;
            display: block;
        }

        .footer-section a:hover {
            color: var(--accent-color);
        }

        .social-icons {
            display: flex;
            gap: 1rem;
        }

        .social-icons a {
            color: #fff;
            font-size: 1.5rem;
            transition: color 0.3s ease;
        }

        .social-icons a:hover {
            color: var(--accent-color);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 2rem;
            border-top: 1px solid #444;
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
                position: absolute;
                top: 100%;
                left: 0;
                width: 100%;
                background: var(--primary-color);
                flex-direction: column;
                padding: 1rem 0;
            }

            .nav-links.active {
                display: flex;
            }

            .nav-links li {
                margin: 0;
                text-align: center;
                padding: 1rem 0;
            }

            .hamburger {
                display: flex;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1.1rem;
            }

            .about .container {
                grid-template-columns: 1fr;
            }

            .contact .container {
                grid-template-columns: 1fr;
            }

            .footer-content {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 480px) {
            .hero h1 {
                font-size: 2rem;
            }

            .hero-content {
                padding: 1rem;
            }

            section {
                padding: 3rem 1rem;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav id="navbar">
        <div class="container">
            <a href="#home" class="logo">EliteFashion</a>
            <ul class="nav-links" id="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#products">Products</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <div class="hamburger" id="hamburger">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Elevate Your Style</h1>
            <p>Discover premium clothing that defines your unique fashion statement. Quality craftsmanship meets contemporary design.</p>
            <a href="#products" class="btn">Shop Now</a>
            <a href="#about" class="btn btn-secondary">Learn More</a>
        </div>
    </section>

    <!-- Products Section -->
    <section id="products" class="products">
        <div class="container">
            <h2>Featured Collection</h2>
            <div class="product-grid">
                <div class="product-card">
                    <div class="product-image" style="background-image: url('https://images.unsplash.com/photo-1521572163474-6864f9cf17ab?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80');">
                        <div class="product-overlay">
                            <a href="#" class="btn">Buy Now</a>
                        </div>
                    </div>
                    <div class="product-info">
                        <h3 class="product-name">Classic Denim Jacket</h3>
                        <p class="product-price">$89.99</p>
                    </div>
                </div>
                <div class="product-card">
                    <div class="product-image" style="background-image: url('https://images.unsplash.com/photo-1553062407-98eeb64c6a62?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80');">
                        <div class="product-overlay">
                            <a href="#" class="btn">Buy Now</a>
                        </div>
                    </div>
                    <div class="product-info">
                        <h3 class="product-name">Elegant Evening Dress</h3>
                        <p class="product-price">$129.99</p>
                    </div>
                </div>
                <div class="product-card">
                    <div class="product-image" style="background-image: url('https://images.unsplash.com/photo-1506629905607-0b5b8b5e4b8b?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80');">
                        <div class="product-overlay">
                            <a href="#" class="btn">Buy Now</a>
                        </div>
                    </div>
                    <div class="product-info">
                        <h3 class="product-name">Casual Sneakers</h3>
                        <p class="product-price">$79.99</p>
                    </div>
                </div>
                <div class="product-card">
                    <div class="product-image" style="background-image: url('https://images.unsplash.com/photo-1551028719-00167b16eac5?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80');">
                        <div class="product-overlay">
                            <a href="#" class="btn">Buy Now</a>
                        </div>
                    </div>
                    <div class="product-info">
                        <h3 class="product-name">Stylish Sunglasses</h3>
                        <p class="product-price">$49.99</p>
                    </div>
                </div>
                <div class="product-card">
                    <div class="product-image" style="background-image: url('https://images.unsplash.com/photo-1544966503-7cc5ac882d5f?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80');">
                        <div class="product-overlay">
                            <a href="#" class="btn">Buy Now</a>
                        </div>
                    </div>
                    <div class="product-info">
                        <h3 class="product-name">Leather Handbag</h3>
                        <p class="product-price">$159.99</p>
                    </div>
                </div>
                <div class="product-card">
                    <div class="product-image" style="background-image: url('https://images.unsplash.com/photo-1506629905607-0b5b8b5e4b8b?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80');">
                        <div class="product-overlay">
                            <a href="#" class="btn">Buy Now</a>
                        </div>
                    </div>
                    <div class="product-info">
                        <h3 class="product-name">Comfortable Hoodie</h3>
                        <p class="product-price">$69.99</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
        <div class="container">
            <div class="about-text">
                <h3>About EliteFashion</h3>
                <p>EliteFashion is more than just clothing – it's a lifestyle. We curate collections that blend timeless elegance with contemporary trends, ensuring every piece tells a story of quality and style.</p>
                <p>Our commitment to sustainability and ethical practices means you can look good while feeling good about your choices.</p>
                <a href="#products" class="btn">Explore Our Collection</a>
            </div>
            <div class="about-image">
                <img src="https://images.unsplash.com/photo-1441986300917-64674bd600d8?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Fashion boutique" style="width: 100%; border-radius: 10px;">
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
        <div class="container">
            <div class="contact-info">
                <h3>Get In Touch</h3>
                <p>Have questions about our products or need styling advice? We'd love to hear from you!</p>
                <p><strong>Email:</strong> info@elitefashion.com</p>
                <p><strong>Phone:</strong> +1 (555) 123-4567</p>
                <p><strong>Address:</strong> 123 Fashion Street, Style City, SC 12345</p>
            </div>
            <div class="contact-form">
                <h3>Send us a Message</h3>
                <form>
                    <input type="text" placeholder="Your Name" required>
                    <input type="email" placeholder="Your Email" required>
                    <textarea placeholder="Your Message" rows="5" required></textarea>
                    <button type="submit">Send Message</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h4>EliteFashion</h4>
                    <p>Elevating fashion since 2020. Premium quality, timeless style.</p>
                </div>
                <div class="footer-section">
                    <h4>Quick Links</h4>
                    <a href="#home">Home</a>
                    <a href="#products">Products</a>
                    <a href="#about">About</a>
                    <a href="#contact">Contact</a>
                </div>
                <div class="footer-section">
                    <h4>Follow Us</h4>
                    <div class="social-icons">
                        <a href="#" title="Facebook"><i class="fab fa-facebook-f"></i></a>
                        <a href="#" title="Instagram"><i class="fab fa-instagram"></i></a>
                        <a href="#" title="Twitter"><i class="fab fa-twitter"></i></a>
                        <a href="#" title="Pinterest"><i class="fab fa-pinterest"></i></a>
                    </div>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2023 EliteFashion. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <!-- Back to Top Button -->
    <button class="back-to-top" id="backToTop"><i class="fas fa-arrow-up"></i></button>

    <!-- Order Modal -->
    <div id="orderModal" class="modal">
        <div class="modal-content">
            <span class="close" id="closeModal">&times;</span>
            <h3>Order Product</h3>
            <form class="order-form" id="orderForm">
                <input type="text" placeholder="Your Name" required>
                <input type="email" placeholder="Your Email" required>
                <input type="tel" placeholder="Phone Number" required>
                <input type="text" placeholder="Shipping Address" required>
                <select required>
                    <option value="">Select Product</option>
                    <option value="Classic Denim Jacket">Classic Denim Jacket - $89.99</option>
                    <option value="Elegant Evening Dress">Elegant Evening Dress - $129.99</option>
                    <option value="Casual Sneakers">Casual Sneakers - $79.99</option>
                    <option value="Stylish Sunglasses">Stylish Sunglasses - $49.99</option>
                    <option value="Leather Handbag">Leather Handbag - $159.99</option>
                    <option value="Comfortable Hoodie">Comfortable Hoodie - $69.99</option>
                </select>
                <button type="submit">Place Order</button>
            </form>
        </div>
    </div>

    <script>
        // Navigation toggle for mobile
        const hamburger = document.getElementById('hamburger');
        const navLinks = document.getElementById('nav-links');

        hamburger.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            hamburger.classList.toggle('active');
        });

        // Close mobile menu when clicking a link
        navLinks.addEventListener('click', (e) => {
            if (e.target.tagName === 'A') {
                navLinks.classList.remove('active');
                hamburger.classList.remove('active');
            }
        });

        // Navbar background change on scroll
        const navbar = document.getElementById('navbar');
        window.addEventListener('scroll', () => {
            if (window.scrollY > 100) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });

        // Intersection Observer for scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('animate');
                }
            });
        }, observerOptions);

        // Observe product cards
        const productCards = document.querySelectorAll('.product-card');
        productCards.forEach(card => {
            observer.observe(card);
        });

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Form submission (prevent default for demo)
        const contactForm = document.querySelector('.contact-form form');
        contactForm.addEventListener('submit', (e) => {
            e.preventDefault();
            alert('Thank you for your message! We\'ll get back to you soon.');
            contactForm.reset();
        });

        // Add Font Awesome for social icons (using web font)
        const fontAwesome = document.createElement('link');
        fontAwesome.rel = 'stylesheet';
        fontAwesome.href = 'https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css';
        document.head.appendChild(fontAwesome);

        // Back to Top Button functionality
        const backToTopButton = document.getElementById('backToTop');
        window.addEventListener('scroll', () => {
            if (window.scrollY > 300) {
                backToTopButton.classList.add('show');
            } else {
                backToTopButton.classList.remove('show');
            }
        });

        backToTopButton.addEventListener('click', () => {
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        });

        // Order Modal functionality
        const orderModal = document.getElementById('orderModal');
        const closeModal = document.getElementById('closeModal');
        const orderForm = document.getElementById('orderForm');
        const buyNowButtons = document.querySelectorAll('.product-overlay .btn');

        buyNowButtons.forEach(button => {
            button.addEventListener('click', (e) => {
                e.preventDefault();
                orderModal.style.display = 'block';
            });
        });

        closeModal.addEventListener('click', () => {
            orderModal.style.display = 'none';
        });

        window.addEventListener('click', (e) => {
            if (e.target === orderModal) {
                orderModal.style.display = 'none';
            }
        });

        orderForm.addEventListener('submit', (e) => {
            e.preventDefault();
            alert('Thank you for your order! We will process it shortly.');
            orderForm.reset();
            orderModal.style.display = 'none';
        });
    </script>
</body>
</html>

