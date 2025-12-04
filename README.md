<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Silvercore | Premium Digital Marketing Agency</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --black-bg: #0a0a0a;
            --dark-gray: #111111;
            --medium-gray: #1a1a1a;
            --light-gray: #2a2a2a;
            --neon-purple: #b026ff;
            --neon-blue: #0066ff;
            --neon-purple-glow: rgba(176, 38, 255, 0.7);
            --neon-blue-glow: rgba(0, 102, 255, 0.7);
            --text-primary: #ffffff;
            --text-secondary: #b3b3b3;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--black-bg);
            color: var(--text-primary);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Navigation */
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 1.5rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(10, 10, 10, 0.9);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(176, 38, 255, 0.2);
            z-index: 1000;
            transition: all 0.3s ease;
        }

        .navbar.scrolled {
            padding: 1rem 5%;
            background: rgba(10, 10, 10, 0.95);
        }

        .nav-logo {
            font-size: 1.8rem;
            font-weight: 800;
            background: linear-gradient(45deg, var(--neon-purple), var(--neon-blue));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
        }

        .nav-links a {
            color: var(--text-primary);
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: var(--neon-purple);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(45deg, var(--neon-purple), var(--neon-blue));
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .cta-button {
            background: linear-gradient(45deg, var(--neon-purple), var(--neon-blue));
            border: none;
            padding: 0.8rem 1.5rem;
            border-radius: 4px;
            color: white;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
        }

        .cta-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 25px var(--neon-purple-glow);
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding: 0 5%;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(176, 38, 255, 0.1) 0%, rgba(10, 10, 10, 0) 70%);
            animation: pulse 8s ease-in-out infinite;
        }

        .hero-content {
            max-width: 600px;
            z-index: 2;
        }

        .hero h1 {
            font-size: 3.5rem;
            font-weight: 800;
            margin-bottom: 1.5rem;
            line-height: 1.2;
            opacity: 0;
            transform: translateY(30px);
            animation: fadeUp 1s ease 0.5s forwards;
        }

        .gradient-text {
            background: linear-gradient(45deg, var(--neon-purple), var(--neon-blue));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero p {
            font-size: 1.2rem;
            color: var(--text-secondary);
            margin-bottom: 2rem;
            opacity: 0;
            transform: translateY(30px);
            animation: fadeUp 1s ease 0.8s forwards;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
            opacity: 0;
            transform: translateY(30px);
            animation: fadeUp 1s ease 1.1s forwards;
        }

        .btn-primary, .btn-secondary {
            padding: 1rem 2rem;
            border: none;
            border-radius: 4px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
            text-align: center;
        }

        .btn-primary {
            background: linear-gradient(45deg, var(--neon-purple), var(--neon-blue));
            color: white;
            box-shadow: 0 5px 15px var(--neon-purple-glow);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px var(--neon-blue-glow);
        }

        .btn-secondary {
            background: transparent;
            color: var(--text-primary);
            border: 2px solid var(--light-gray);
        }

        .btn-secondary:hover {
            border-color: var(--neon-purple);
            transform: translateY(-3px);
        }

        /* Services Section */
        .services {
            padding: 100px 5%;
            background: var(--dark-gray);
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 3rem;
            opacity: 0;
            transform: translateY(30px);
        }

        .packages-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .package-card {
            background: var(--medium-gray);
            border-radius: 10px;
            padding: 2.5rem;
            position: relative;
            overflow: hidden;
            border: 1px solid transparent;
            transition: all 0.3s ease;
            opacity: 0;
            transform: translateY(30px);
        }

        .package-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(45deg, var(--neon-purple), var(--neon-blue));
        }

        .package-card:hover {
            transform: translateY(-10px);
            border-color: var(--neon-purple);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
        }

        .package-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--text-primary);
        }

        .price {
            font-size: 2.5rem;
            font-weight: 800;
            margin-bottom: 1.5rem;
            background: linear-gradient(45deg, var(--neon-purple), var(--neon-blue));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .price span {
            font-size: 1rem;
            font-weight: 400;
            color: var(--text-secondary);
        }

        .features {
            list-style: none;
            margin-bottom: 2rem;
        }

        .features li {
            padding: 0.5rem 0;
            color: var(--text-secondary);
            position: relative;
            padding-left: 1.5rem;
        }

        .features li::before {
            content: '✓';
            position: absolute;
            left: 0;
            color: var(--neon-purple);
            font-weight: bold;
        }

        .card-cta {
            width: 100%;
            padding: 1rem;
            background: transparent;
            border: 2px solid var(--neon-purple);
            color: var(--text-primary);
            border-radius: 4px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .card-cta:hover {
            background: var(--neon-purple);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px var(--neon-purple-glow);
        }

        /* Process Section */
        .process {
            padding: 100px 5%;
            background: var(--black-bg);
        }

        .process-steps {
            display: flex;
            justify-content: space-between;
            max-width: 1000px;
            margin: 0 auto;
            position: relative;
        }

        .process-steps::before {
            content: '';
            position: absolute;
            top: 40px;
            left: 10%;
            right: 10%;
            height: 2px;
            background: linear-gradient(90deg, var(--neon-purple), var(--neon-blue));
        }

        .step {
            text-align: center;
            position: relative;
            z-index: 2;
            opacity: 0;
            transform: translateY(30px);
        }

        .step-icon {
            width: 80px;
            height: 80px;
            background: var(--dark-gray);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 1rem;
            border: 2px solid var(--neon-purple);
            font-size: 1.5rem;
            color: var(--neon-purple);
        }

        .step h4 {
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
        }

        .step p {
            color: var(--text-secondary);
            font-size: 0.9rem;
        }

        /* Portfolio Section */
        .portfolio {
            padding: 100px 5%;
            background: var(--dark-gray);
        }

        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .portfolio-item {
            background: var(--medium-gray);
            border-radius: 10px;
            overflow: hidden;
            position: relative;
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.3s ease;
        }

        .portfolio-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
        }

        .portfolio-image {
            width: 100%;
            height: 200px;
            background: linear-gradient(45deg, var(--neon-purple), var(--neon-blue));
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
        }

        .portfolio-content {
            padding: 1.5rem;
        }

        .portfolio-content h4 {
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
        }

        .portfolio-content p {
            color: var(--text-secondary);
            font-size: 0.9rem;
            margin-bottom: 1rem;
        }

        .metrics {
            display: flex;
            justify-content: space-between;
        }

        .metric {
            text-align: center;
        }

        .metric-value {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--neon-purple);
        }

        .metric-label {
            font-size: 0.8rem;
            color: var(--text-secondary);
        }

        /* Add-ons Section */
        .addons {
            padding: 100px 5%;
            background: var(--black-bg);
        }

        .addons-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .addon-card {
            background: var(--medium-gray);
            border-radius: 10px;
            padding: 2rem;
            border: 1px solid var(--light-gray);
            transition: all 0.3s ease;
            opacity: 0;
            transform: translateY(30px);
            position: relative;
            overflow: hidden;
        }

        .addon-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(45deg, var(--neon-purple), var(--neon-blue));
        }

        .addon-card:hover {
            transform: translateY(-5px);
            border-color: var(--neon-purple);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
        }

        .addon-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, var(--neon-purple), var(--neon-blue));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .addon-card h4 {
            font-size: 1.3rem;
            margin-bottom: 1rem;
            color: var(--text-primary);
        }

        .addon-price {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
            color: var(--neon-purple);
        }

        .addon-features {
            list-style: none;
            margin-bottom: 1.5rem;
        }

        .addon-features li {
            padding: 0.3rem 0;
            color: var(--text-secondary);
            position: relative;
            padding-left: 1.2rem;
            font-size: 0.9rem;
        }

        .addon-features li::before {
            content: '▶';
            position: absolute;
            left: 0;
            color: var(--neon-blue);
            font-size: 0.7rem;
        }

        .addon-cta {
            width: 100%;
            padding: 0.8rem;
            background: transparent;
            border: 1px solid var(--neon-purple);
            color: var(--text-primary);
            border-radius: 4px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 0.9rem;
        }

        .addon-cta:hover {
            background: var(--neon-purple);
            transform: translateY(-2px);
        }

        /* CTA Section */
        .cta-section {
            padding: 100px 5%;
            background: linear-gradient(135deg, var(--dark-gray), var(--black-bg));
            text-align: center;
        }

        .cta-section h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            opacity: 0;
            transform: translateY(30px);
        }

        .cta-section p {
            font-size: 1.2rem;
            color: var(--text-secondary);
            margin-bottom: 2rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            opacity: 0;
            transform: translateY(30px);
        }

        /* Footer */
        .footer {
            background: var(--dark-gray);
            padding: 3rem 5%;
            border-top: 1px solid var(--light-gray);
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .footer-column h4 {
            margin-bottom: 1rem;
            color: var(--text-primary);
        }

        .footer-column a {
            display: block;
            color: var(--text-secondary);
            text-decoration: none;
            margin-bottom: 0.5rem;
            transition: color 0.3s ease;
        }

        .footer-column a:hover {
            color: var(--neon-purple);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 2rem;
            margin-top: 2rem;
            border-top: 1px solid var(--light-gray);
            color: var(--text-secondary);
        }

        /* Animations */
        @keyframes fadeUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); opacity: 0.5; }
            50% { transform: scale(1.1); opacity: 0.8; }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        /* Floating elements */
        .floating-element {
            position: absolute;
            background: linear-gradient(45deg, var(--neon-purple), var(--neon-blue));
            border-radius: 50%;
            opacity: 0.1;
            animation: float 6s ease-in-out infinite;
        }

        .float-1 {
            width: 100px;
            height: 100px;
            top: 20%;
            right: 10%;
            animation-delay: 0s;
        }

        .float-2 {
            width: 150px;
            height: 150px;
            bottom: 20%;
            left: 5%;
            animation-delay: 2s;
        }

        .float-3 {
            width: 80px;
            height: 80px;
            top: 60%;
            right: 20%;
            animation-delay: 4s;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero-buttons {
                flex-direction: column;
            }

            .process-steps {
                flex-direction: column;
                gap: 2rem;
            }

            .process-steps::before {
                display: none;
            }

            .packages-grid {
                grid-template-columns: 1fr;
            }

            .addons-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav class="navbar">
        <div class="nav-logo">SILVERCORE</div>
        <div class="nav-links">
            <a href="#services">Services</a>
            <a href="#process">Process</a>
            <a href="#portfolio">Portfolio</a>
            <a href="#addons">Add-ons</a>
            <a href="#contact" class="cta-button">Get Quote</a>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero">
        <div class="floating-element float-1"></div>
        <div class="floating-element float-2"></div>
        <div class="floating-element float-3"></div>
        
        <div class="hero-content">
            <h1>Forge The <span class="gradient-text">Core</span> Of Your Business</h1>
            <p>Premium digital marketing that builds unbreakable foundations for sustainable growth. We create marketing systems that work like gravity.</p>
            <div class="hero-buttons">
                <a href="#services" class="btn-primary">View Packages</a>
                <a href="#portfolio" class="btn-secondary">Case Studies</a>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section class="services" id="services">
        <h2 class="section-title">Our <span class="gradient-text">Packages</span></h2>
        <div class="packages-grid">
            <div class="package-card">
                <h3>🥉 The Foundation Forge</h3>
                <div class="price">$1,499<span>/month</span></div>
                <ul class="features">
                    <li>5-Page Professional Website</li>
                    <li>Basic SEO Setup</li>
                    <li>2 Social Media Platforms</li>
                    <li>8 Posts/Month + Graphics</li>
                    <li>2 Short-Form Videos</li>
                    <li>Basic Analytics</li>
                </ul>
                <button class="card-cta" onclick="window.open('https://forms.gle/U8UcGpfpaSsbPJES7', '_blank')">Get Started</button>
            </div>

            <div class="package-card">
                <h3>🥈 The Silver Tier</h3>
                <div class="price">$2,999<span>/month</span></div>
                <ul class="features">
                    <li>10-Page Custom Website</li>
                    <li>Advanced SEO Strategy</li>
                    <li>3 Social Media Platforms</li>
                    <li>12 Posts + 16 Stories/Month</li>
                    <li>4 Short-Form + 1 Long-Form Video</li>
                    <li>Monthly Performance Reports</li>
                    <li>Community Management</li>
                </ul>
                <button class="card-cta" onclick="window.open('https://forms.gle/U8UcGpfpaSsbPJES7', '_blank')">Get Started</button>
            </div>

            <div class="package-card">
                <h3>🥇 The Adamant Tier</h3>
                <div class="price">$5,500+<span>/month</span></div>
                <ul class="features">
                    <li>Fully Custom Website + CRO</li>
                    <li>4-5 Social Platforms</li>
                    <li>20 Posts + Daily Stories</li>
                    <li>8 Short-Form + 2 Long-Form Videos</li>
                    <li>Paid Ad Creative Sets</li>
                    <li>Bi-Weekly Strategy Calls</li>
                    <li>Advanced Motion Graphics</li>
                </ul>
                <button class="card-cta" onclick="window.open('https://forms.gle/U8UcGpfpaSsbPJES7', '_blank')">Get Started</button>
            </div>
        </div>
    </section>

    <!-- Process Section -->
    <section class="process" id="process">
        <h2 class="section-title">Our <span class="gradient-text">Process</span></h2>
        <div class="process-steps">
            <div class="step">
                <div class="step-icon">1</div>
                <h4>Audit & Strategy</h4>
                <p>Deep dive analysis of your current marketing core</p>
            </div>
            <div class="step">
                <div class="step-icon">2</div>
                <h4>Build & Implement</h4>
                <p>Forge your custom marketing foundation</p>
            </div>
            <div class="step">
                <div class="step-icon">3</div>
                <h4>Launch & Scale</h4>
                <p>Activate your growth engines systematically</p>
            </div>
            <div class="step">
                <div class="step-icon">4</div>
                <h4>Analyze & Optimize</h4>
                <p>Continuous improvement for maximum ROI</p>
            </div>
        </div>
    </section>

    <!-- Portfolio Section -->
    <section class="portfolio" id="portfolio">
        <h2 class="section-title">Our <span class="gradient-text">Work</span></h2>
        <div class="portfolio-grid">
            <div class="portfolio-item">
                <div class="portfolio-image">
                    <i class="fas fa-chart-line"></i>
                </div>
                <div class="portfolio-content">
                    <h4>SaaS Tech Company</h4>
                    <p>Complete marketing overhaul for B2B SaaS platform</p>
                    <div class="metrics">
                        <div class="metric">
                            <div class="metric-value">+180%</div>
                            <div class="metric-label">Leads/Month</div>
                        </div>
                        <div class="metric">
                            <div class="metric-value">-45%</div>
                            <div class="metric-label">Cost Per Lead</div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="portfolio-item">
                <div class="portfolio-image">
                    <i class="fas fa-shopping-cart"></i>
                </div>
                <div class="portfolio-content">
                    <h4>E-commerce Brand</h4>
                    <p>Full funnel optimization for premium products</p>
                    <div class="metrics">
                        <div class="metric">
                            <div class="metric-value">+220%</div>
                            <div class="metric-label">Revenue</div>
                        </div>
                        <div class="metric">
                            <div class="metric-value">3.2x</div>
                            <div class="metric-label">ROI</div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="portfolio-item">
                <div class="portfolio-image">
                    <i class="fas fa-dumbbell"></i>
                </div>
                <div class="portfolio-content">
                    <h4>Fitness App</h4>
                    <p>Launch strategy and user acquisition campaign</p>
                    <div class="metrics">
                        <div class="metric">
                            <div class="metric-value">+1500</div>
                            <div class="metric-label">New Users</div>
                        </div>
                        <div class="metric">
                            <div class="metric-value">-60%</div>
                            <div class="metric-label">CAC</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Add-ons Section -->
    <section class="addons" id="addons">
        <h2 class="section-title">Premium <span class="gradient-text">Add-ons</span></h2>
        <div class="addons-grid">
            <div class="addon-card">
                <div class="addon-icon">
                    <i class="fas fa-store"></i>
                </div>
                <h4>E-commerce Store</h4>
                <div class="addon-price">$1,500 one-time</div>
                <ul class="addon-features">
                    <li>Full online store setup</li>
                    <li>Product catalog integration</li>
                    <li>Payment gateway configuration</li>
                    <li>Inventory management system</li>
                </ul>
                <button class="addon-cta" onclick="window.open('https://forms.gle/U8UcGpfpaSsbPJES7', '_blank')">Add to Package</button>
            </div>

            <div class="addon-card">
                <div class="addon-icon">
                    <i class="fas fa-funnel-dollar"></i>
                </div>
                <h4>Sales Funnel</h4>
                <div class="addon-price">$2,000 one-time</div>
                <ul class="addon-features">
                    <li>Complete funnel architecture</li>
                    <li>Lead magnet creation</li>
                    <li>Email sequence setup</li>
                    <li>Conversion optimization</li>
                </ul>
                <button class="addon-cta" onclick="window.open('https://forms.gle/U8UcGpfpaSsbPJES7', '_blank')">Add to Package</button>
            </div>

            <div class="addon-card">
                <div class="addon-icon">
                    <i class="fas fa-ad"></i>
                </div>
                <h4>Paid Ads Management</h4>
                <div class="addon-price">$750-$1,500/month</div>
                <ul class="addon-features">
                    <li>Campaign strategy & setup</li>
                    <li>Daily monitoring & optimization</li>
                    <li>A/B testing implementation</li>
                    <li>ROI tracking & reporting</li>
                </ul>
                <button class="addon-cta" onclick="window.open('https://forms.gle/U8UcGpfpaSsbPJES7', '_blank')">Add to Package</button>
            </div>

            <div class="addon-card">
                <div class="addon-icon">
                    <i class="fas fa-blog"></i>
                </div>
                <h4>Content Writing</h4>
                <div class="addon-price">$500/article</div>
                <ul class="addon-features">
                    <li>SEO-optimized blog articles</li>
                    <li>Keyword research included</li>
                    <li>Professional copywriting</li>
                    <li>Content strategy alignment</li>
                </ul>
                <button class="addon-cta" onclick="window.open('https://forms.gle/U8UcGpfpaSsbPJES7', '_blank')">Add to Package</button>
            </div>

            <div class="addon-card">
                <div class="addon-icon">
                    <i class="fas fa-film"></i>
                </div>
                <h4>Advanced Video Production</h4>
                <div class="addon-price">$300-600/video</div>
                <ul class="addon-features">
                    <li>Professional motion graphics</li>
                    <li>Color grading & sound design</li>
                    <li>Custom animations</li>
                    <li>YouTube optimization</li>
                </ul>
                <button class="addon-cta" onclick="window.open('https://forms.gle/U8UcGpfpaSsbPJES7', '_blank')">Add to Package</button>
            </div>

            <div class="addon-card">
                <div class="addon-icon">
                    <i class="fas fa-tachometer-alt"></i>
                </div>
                <h4>Conversion Rate Optimization</h4>
                <div class="addon-price">$900/month</div>
                <ul class="addon-features">
                    <li>Website performance audit</li>
                    <li>A/B testing implementation</li>
                    <li>User behavior analysis</li>
                    <li>Continuous optimization</li>
                </ul>
                <button class="addon-cta" onclick="window.open('https://forms.gle/U8UcGpfpaSsbPJES7', '_blank')">Add to Package</button>
            </div>
        </div>
    </section>

    <!-- CTA Section -->
    <section class="cta-section" id="contact">
        <h2>Ready to Fortify Your Business?</h2>
        <p>Stop leaving growth to chance. Let's build an unbreakable marketing core that drives predictable revenue.</p>
        <a href="https://forms.gle/U8UcGpfpaSsbPJES7" target="_blank" class="btn-primary">Get Your Free Core Audit</a>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <div class="footer-content">
            <div class="footer-column">
                <h4>Silvercore</h4>
                <p>Building unbreakable marketing foundations for premium brands.</p>
            </div>
            <div class="footer-column">
                <h4>Services</h4>
                <a href="#services">The Foundation Forge</a>
                <a href="#services">The Silver Tier</a>
                <a href="#services">The Adamant Tier</a>
                <a href="#addons">Add-on Services</a>
            </div>
            <div class="footer-column">
                <h4>Company</h4>
                <a href="#about">About Us</a>
                <a href="#portfolio">Portfolio</a>
                <a href="#contact">Contact</a>
                <a href="#blog">Blog</a>
            </div>
            <div class="footer-column">
                <h4>Connect</h4>
                <a href="#">LinkedIn</a>
                <a href="#">Instagram</a>
                <a href="#">Twitter</a>
                <a href="#">Facebook</a>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2024 Silvercore. All rights reserved. Forge Your Core.</p>
        </div>
    </footer>

    <script>
        // Scroll animations
        document.addEventListener('DOMContentLoaded', function() {
            // Navbar scroll effect
            const navbar = document.querySelector('.navbar');
            window.addEventListener('scroll', function() {
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

            const observer = new IntersectionObserver(function(entries) {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = '1';
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            }, observerOptions);

            // Observe all animated elements
            document.querySelectorAll('.section-title, .package-card, .step, .portfolio-item, .addon-card, .cta-section h2, .cta-section p').forEach(el => {
                observer.observe(el);
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

            // Add click event to all CTA buttons
            document.querySelectorAll('.card-cta, .addon-cta').forEach(button => {
                button.addEventListener('click', function() {
                    window.open('https://forms.gle/U8UcGpfpaSsbPJES7', '_blank');
                });
            });
        });
    </script>
</body>
</html>
