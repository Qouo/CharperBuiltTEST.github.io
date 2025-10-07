<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Charper Built - S2000 Performance Specialists</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;600;700;900&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-bg: #0A0A0A;
            --secondary-bg: #151515;
            --card-bg: #1A1A1A;
            --accent-red: #CC0000;
            --accent-red-dark: #A00000;
            --text-white: #FFFFFF;
            --text-gray: #AAAAAA;
            --border-color: #2A2A2A;
            --hover-bg: #202020;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            background-color: var(--primary-bg);
            color: var(--text-white);
            line-height: 1.6;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background-color: rgba(10, 10, 10, 0.98);
            backdrop-filter: blur(20px);
            z-index: 1000;
            border-bottom: 1px solid var(--border-color);
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.5);
        }

        nav .container {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 2rem;
        }

        nav .logo {
            display: flex;
            align-items: center;
        }

        nav .logo img {
            height: 50px;
            width: auto;
            filter: brightness(1.1);
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 2.5rem;
        }

        nav a {
            color: var(--text-gray);
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
            font-size: 0.9rem;
            letter-spacing: 0.5px;
            text-transform: uppercase;
            position: relative;
            padding: 0.5rem 0;
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--accent-red);
            transition: width 0.3s;
        }

        nav a:hover,
        nav a.active {
            color: var(--text-white);
        }

        nav a:hover::after,
        nav a.active::after {
            width: 100%;
        }

        /* Container */
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        /* Page Container */
        .page {
            display: none;
            padding-top: 80px;
            min-height: 100vh;
        }

        .page.active {
            display: block;
        }

        section {
            padding: 4rem 0;
        }

        /* Hero Section */
        .hero {
            min-height: 85vh;
            display: flex;
            align-items: center;
            background: linear-gradient(135deg, var(--primary-bg) 0%, var(--secondary-bg) 100%);
            position: relative;
            overflow: hidden;
            margin-top: -80px;
            padding-top: 80px;
        }

        .hero::before {
            content: '';
            position: absolute;
            width: 800px;
            height: 800px;
            background: radial-gradient(circle, rgba(204, 0, 0, 0.1) 0%, transparent 70%);
            top: -400px;
            right: -400px;
            animation: pulse 8s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); opacity: 0.1; }
            50% { transform: scale(1.1); opacity: 0.15; }
        }

        .hero-content {
            position: relative;
            z-index: 2;
        }

        .hero h1 {
            font-size: 4.5rem;
            font-weight: 900;
            line-height: 1.1;
            margin-bottom: 1.5rem;
            letter-spacing: -2px;
            background: linear-gradient(135deg, #FFFFFF 0%, #CCCCCC 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero h1 span {
            background: linear-gradient(135deg, var(--accent-red) 0%, #FF0000 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero p {
            font-size: 1.3rem;
            color: var(--text-gray);
            margin-bottom: 3rem;
            max-width: 700px;
            font-weight: 300;
        }

        .btn {
            display: inline-block;
            background: linear-gradient(135deg, var(--accent-red) 0%, var(--accent-red-dark) 100%);
            color: var(--text-white);
            padding: 1.2rem 3rem;
            text-decoration: none;
            font-weight: 700;
            border-radius: 4px;
            transition: all 0.3s;
            border: 2px solid var(--accent-red);
            font-size: 0.95rem;
            letter-spacing: 1px;
            text-transform: uppercase;
            position: relative;
            overflow: hidden;
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: left 0.5s;
        }

        .btn:hover::before {
            left: 100%;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(204, 0, 0, 0.4);
        }

        .btn-secondary {
            background: transparent;
            border: 2px solid var(--text-gray);
            color: var(--text-gray);
        }

        .btn-secondary:hover {
            background: var(--text-gray);
            color: var(--primary-bg);
            box-shadow: 0 10px 30px rgba(170, 170, 170, 0.2);
        }

        /* Value Props */
        .value-props {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 4rem;
        }

        .value-card {
            background: linear-gradient(135deg, var(--card-bg) 0%, var(--secondary-bg) 100%);
            padding: 2.5rem;
            border-radius: 12px;
            border: 1px solid var(--border-color);
            transition: all 0.4s;
            position: relative;
            overflow: hidden;
        }

        .value-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, var(--accent-red), transparent);
            transform: scaleX(0);
            transform-origin: left;
            transition: transform 0.4s;
        }

        .value-card:hover {
            transform: translateY(-8px);
            border-color: var(--accent-red);
            box-shadow: 0 15px 40px rgba(204, 0, 0, 0.2);
        }

        .value-card:hover::before {
            transform: scaleX(1);
        }

        .value-card h3 {
            font-size: 1.6rem;
            margin-bottom: 1rem;
            color: var(--accent-red);
            font-weight: 700;
        }

        .value-card p {
            color: var(--text-gray);
            line-height: 1.8;
        }

        /* Section Headers */
        .section-header {
            text-align: center;
            margin-bottom: 4rem;
        }

        .section-header h2 {
            font-size: 3.5rem;
            font-weight: 900;
            margin-bottom: 1rem;
            letter-spacing: -1px;
        }

        .section-header h2 span {
            color: var(--accent-red);
        }

        .section-header p {
            font-size: 1.2rem;
            color: var(--text-gray);
            max-width: 700px;
            margin: 0 auto;
            font-weight: 300;
        }

        /* Engine Cards */
        .engine-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(380px, 1fr));
            gap: 2.5rem;
            margin-bottom: 4rem;
        }

        .engine-card {
            background: var(--card-bg);
            border-radius: 12px;
            overflow: hidden;
            border: 1px solid var(--border-color);
            transition: all 0.4s;
            position: relative;
        }

        .engine-card::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(135deg, transparent 0%, rgba(204, 0, 0, 0.1) 100%);
            opacity: 0;
            transition: opacity 0.4s;
            pointer-events: none;
        }

        .engine-card:hover {
            transform: translateY(-10px);
            border-color: var(--accent-red);
            box-shadow: 0 20px 50px rgba(204, 0, 0, 0.3);
        }

        .engine-card:hover::after {
            opacity: 1;
        }

        .engine-card-img {
            width: 100%;
            height: 280px;
            background-size: cover;
            background-position: center;
            position: relative;
            overflow: hidden;
        }

        .engine-card-img::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, var(--accent-red), #FF0000);
        }

        .engine-card-content {
            padding: 2.5rem;
        }

        .engine-card-content h3 {
            font-size: 2rem;
            margin-bottom: 1rem;
            color: var(--text-white);
            font-weight: 700;
        }

        .engine-card-content p {
            color: var(--text-gray);
            margin-bottom: 1rem;
            line-height: 1.9;
        }

        .engine-card-content strong {
            color: var(--text-white);
        }

        .price-tag {
            font-size: 1.8rem;
            font-weight: 900;
            background: linear-gradient(135deg, var(--accent-red) 0%, #FF0000 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-top: 1.5rem;
        }

        /* NSC Info Box */
        .nsc-info {
            background: linear-gradient(135deg, var(--card-bg) 0%, var(--secondary-bg) 100%);
            padding: 3.5rem;
            border-radius: 12px;
            border-left: 4px solid var(--accent-red);
            margin-top: 4rem;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.3);
        }

        .nsc-info h3 {
            font-size: 2.5rem;
            margin-bottom: 1.5rem;
            color: var(--accent-red);
            font-weight: 700;
        }

        .nsc-benefits {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-top: 2.5rem;
        }

        .nsc-benefits li {
            list-style: none;
            padding-left: 2rem;
            position: relative;
            color: var(--text-gray);
            font-size: 1.05rem;
        }

        .nsc-benefits li::before {
            content: '✓';
            position: absolute;
            left: 0;
            color: var(--accent-red);
            font-weight: 900;
            font-size: 1.3rem;
        }

        /* Transmission Table */
        .trans-table {
            background: var(--card-bg);
            border-radius: 12px;
            overflow: hidden;
            border: 1px solid var(--border-color);
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.3);
        }

        .trans-table table {
            width: 100%;
            border-collapse: collapse;
        }

        .trans-table th,
        .trans-table td {
            padding: 1.8rem;
            text-align: left;
            border-bottom: 1px solid var(--border-color);
        }

        .trans-table th {
            background: linear-gradient(135deg, var(--secondary-bg) 0%, var(--card-bg) 100%);
            font-weight: 700;
            color: var(--accent-red);
            text-transform: uppercase;
            font-size: 0.85rem;
            letter-spacing: 1.5px;
        }

        .trans-table td {
            color: var(--text-gray);
            font-size: 1.05rem;
        }

        .trans-table tr {
            transition: background 0.3s;
        }

        .trans-table tr:hover {
            background-color: rgba(204, 0, 0, 0.05);
        }

        .trans-table .price {
            color: var(--text-white);
            font-weight: 700;
            font-size: 1.2rem;
        }

        .trans-table .highlight {
            background: rgba(204, 0, 0, 0.08);
        }

        .trans-table .highlight td {
            font-weight: 600;
        }

        /* Service Section */
        .labor-rates {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2.5rem;
            margin-bottom: 4rem;
        }

        .rate-card {
            background: linear-gradient(135deg, var(--card-bg) 0%, var(--secondary-bg) 100%);
            padding: 3rem;
            border-radius: 12px;
            border: 2px solid var(--accent-red);
            text-align: center;
            transition: all 0.3s;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        .rate-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(204, 0, 0, 0.3);
        }

        .rate-card h3 {
            font-size: 1.4rem;
            margin-bottom: 1.5rem;
            color: var(--text-gray);
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .rate-card .rate {
            font-size: 3rem;
            font-weight: 900;
            color: var(--accent-red);
        }

        .service-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 1.5rem;
        }

        .service-item {
            background: var(--card-bg);
            padding: 1.8rem;
            border-radius: 8px;
            border: 1px solid var(--border-color);
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: all 0.3s;
        }

        .service-item:hover {
            border-color: var(--accent-red);
            transform: translateX(5px);
            background: var(--hover-bg);
        }

        .service-item span:first-child {
            color: var(--text-white);
            font-weight: 600;
            font-size: 1.05rem;
        }

        .service-item span:last-child {
            color: var(--accent-red);
            font-weight: 700;
            font-size: 1.3rem;
        }

        /* Contact Section */
        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
        }

        .contact-info {
            background: linear-gradient(135deg, var(--card-bg) 0%, var(--secondary-bg) 100%);
            padding: 3.5rem;
            border-radius: 12px;
            border: 1px solid var(--border-color);
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.3);
        }

        .contact-info h3 {
            font-size: 2.5rem;
            margin-bottom: 2.5rem;
            color: var(--accent-red);
            font-weight: 700;
        }

        .info-item {
            margin-bottom: 2.5rem;
        }

        .info-item strong {
            display: block;
            color: var(--text-white);
            margin-bottom: 0.8rem;
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 1.5px;
        }

        .info-item p {
            color: var(--text-gray);
            font-size: 1.2rem;
        }

        .info-item a {
            color: var(--text-gray);
            text-decoration: none;
            transition: color 0.3s;
        }

        .info-item a:hover {
            color: var(--accent-red);
        }

        .contact-form {
            background: linear-gradient(135deg, var(--card-bg) 0%, var(--secondary-bg) 100%);
            padding: 3.5rem;
            border-radius: 12px;
            border: 1px solid var(--border-color);
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.3);
        }

        .form-group {
            margin-bottom: 2rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.8rem;
            color: var(--text-white);
            font-weight: 600;
            text-transform: uppercase;
            font-size: 0.85rem;
            letter-spacing: 1px;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1.2rem;
            background-color: var(--secondary-bg);
            border: 1px solid var(--border-color);
            border-radius: 6px;
            color: var(--text-white);
            font-family: 'Montserrat', sans-serif;
            transition: all 0.3s;
            font-size: 1rem;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--accent-red);
            background-color: var(--card-bg);
            box-shadow: 0 0 0 3px rgba(204, 0, 0, 0.1);
        }

        .form-group textarea {
            resize: vertical;
            min-height: 180px;
        }

        /* Configurator */
        .configurator-container {
            background: var(--card-bg);
            border-radius: 12px;
            overflow: hidden;
            border: 1px solid var(--border-color);
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.3);
        }

        .configurator-content {
            display: grid;
            grid-template-columns: 1fr 400px;
            gap: 0;
        }

        .config-options {
            padding: 3rem;
            border-right: 1px solid var(--border-color);
        }

        .config-section {
            margin-bottom: 3rem;
        }

        .config-section h3 {
            font-size: 1.5rem;
            color: var(--accent-red);
            margin-bottom: 1.5rem;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .option-group {
            margin-bottom: 2rem;
        }

        .option-group label {
            display: block;
            color: var(--text-gray);
            margin-bottom: 0.8rem;
            font-weight: 600;
            text-transform: uppercase;
            font-size: 0.85rem;
            letter-spacing: 1px;
        }

        .option-group select {
            width: 100%;
            padding: 1rem;
            background: var(--secondary-bg);
            border: 1px solid var(--border-color);
            border-radius: 6px;
            color: var(--text-white);
            font-family: 'Montserrat', sans-serif;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s;
        }

        .option-group select:focus {
            outline: none;
            border-color: var(--accent-red);
            box-shadow: 0 0 0 3px rgba(204, 0, 0, 0.1);
        }

        .checkbox-group {
            display: grid;
            gap: 1rem;
        }

        .checkbox-item {
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 1rem;
            background: var(--secondary-bg);
            border-radius: 6px;
            border: 1px solid var(--border-color);
            cursor: pointer;
            transition: all 0.3s;
        }

        .checkbox-item:hover {
            border-color: var(--accent-red);
            background: var(--hover-bg);
        }

        .checkbox-item input[type="checkbox"] {
            width: 20px;
            height: 20px;
            cursor: pointer;
            accent-color: var(--accent-red);
        }

        .checkbox-item label {
            flex: 1;
            cursor: pointer;
            margin: 0;
            text-transform: none;
            font-weight: 400;
            color: var(--text-white);
        }

        .checkbox-item .option-price {
            color: var(--accent-red);
            font-weight: 700;
        }

        .config-summary {
            background: linear-gradient(135deg, var(--secondary-bg) 0%, var(--primary-bg) 100%);
            padding: 3rem;
            position: sticky;
            top: 100px;
            height: fit-content;
        }

        .config-summary h3 {
            font-size: 1.8rem;
            color: var(--text-white);
            margin-bottom: 2rem;
            font-weight: 700;
        }

        .summary-item {
            display: flex;
            justify-content: space-between;
            padding: 1rem 0;
            border-bottom: 1px solid var(--border-color);
            color: var(--text-gray);
        }

        .summary-item.total {
            border-bottom: none;
            border-top: 2px solid var(--accent-red);
            margin-top: 1.5rem;
            padding-top: 1.5rem;
            font-size: 1.5rem;
            font-weight: 900;
            color: var(--text-white);
        }

        .summary-item.total span:last-child {
            color: var(--accent-red);
        }

        /* Footer */
        footer {
            background: var(--secondary-bg);
            padding: 3rem 0;
            text-align: center;
            border-top: 1px solid var(--border-color);
            margin-top: 6rem;
        }

        footer p {
            color: var(--text-gray);
        }

        /* Responsive */
        @media (max-width: 1200px) {
            .configurator-content {
                grid-template-columns: 1fr;
            }

            .config-options {
                border-right: none;
                border-bottom: 1px solid var(--border-color);
            }

            .config-summary {
                position: relative;
                top: 0;
            }
        }

        @media (max-width: 968px) {
            nav ul {
                gap: 1.5rem;
            }

            .hero h1 {
                font-size: 3rem;
            }

            .section-header h2 {
                font-size: 2.5rem;
            }

            .contact-content {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            .engine-grid {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 768px) {
            nav .container {
                flex-direction: column;
                gap: 1rem;
            }

            nav ul {
                flex-wrap: wrap;
                justify-content: center;
                gap: 1rem;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1.1rem;
            }

            section {
                padding: 3rem 0;
            }

            .trans-table th,
            .trans-table td {
                padding: 1rem;
                font-size: 0.9rem;
            }

            .value-props,
            .labor-rates,
            .service-list {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav>
        <div class="container">
            <div class="logo">
                <img src="https://i.imgur.com/placeholder-logo.png" alt="Charper Built Logo">
            </div>
            <ul>
                <li><a href="#" data-page="home" class="active">Home</a></li>
                <li><a href="#" data-page="engines">Engines</a></li>
                <li><a href="#" data-page="transmissions">Transmissions</a></li>
                <li><a href="#" data-page="service">Service</a></li>
                <li><a href="#" data-page="configurator">Configurator</a></li>
                <li><a href="#" data-page="contact">Contact</a></li>
            </ul>
        </div>
    </nav>

    <!-- HOME PAGE -->
    <div id="home-page" class="page active">
        <section class="hero">
            <div class="container">
                <div class="hero-content">
                    <h1>The Pinnacle of <span>F-Series</span> Performance</h1>
                    <p>Track-tested, dyno-proven engineering. S2000 Specialists located in Maryville, TN.</p>
                    <a href="#" data-page="engines" class="btn">EXPLORE ENGINE BUILDS</a>
                    
                    <div class="value-props">
                        <div class="value-card">
                            <h3>Engine Mastery</h3>
                            <p>Advanced NSC plating technology combining OEM reliability with cutting-edge performance engineering.</p>
                        </div>
                        <div class="value-card">
                            <h3>Proven Performance</h3>
                            <p>370+ HP naturally aspirated builds. Track-tested and dyno-verified on pump gas.</p>
                        </div>
                        <div class="value-card">
                            <h3>Specialized Service</h3>
                            <p>Dedicated S2000 experts with years of R&D, testing, and refinement in the F-series platform.</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- ENGINES PAGE -->
    <div id="engines-page" class="page">
        <section class="hero" style="min-height: 60vh;">
            <div class="container">
                <div class="hero-content">
                    <h1><span>Engine</span> Builds</h1>
                    <p>From OEM reliability to track-dominating performance, every build is blueprinted to perfection.</p>
                </div>
            </div>
        </section>

        <section>
            <div class="container">
                <div class="engine-grid">
                    <div class="engine-card">
                        <div class="engine-card-img" style="background-image: linear-gradient(rgba(0,0,0,0.3), rgba(0,0,0,0.3)), url('https://i.imgur.com/placeholder-pinnacle.jpg'); background-color: #2A2A2A;"></div>
                        <div class="engine-card-content">
                            <h3>Pinnacle F-Series</h3>
                            <p>370+ HP at the crank. 300+ WHP on pump fuel. No sleeves. NSC-plated OEM aluminum for maximum durability. Rev-happy, durable, and streetable.</p>
                            <p><strong>Includes:</strong> NSC plating, lightest rotating assembly, chamber-modified head, WPC bearings, ARP head studs, full assembly.</p>
                            <div class="price-tag">Starting at $10,950</div>
                            <p style="font-size: 0.9rem; margin-top: 0.5rem; color: #666;">(with customer-supplied core)</p>
                        </div>
                    </div>

                    <div class="engine-card">
                        <div class="engine-card-img" style="background-image: linear-gradient(rgba(0,0,0,0.3), rgba(0,0,0,0.3)), url('https://i.imgur.com/placeholder-nsc.jpg'); background-color: #2A2A2A;"></div>
                        <div class="engine-card-content">
                            <h3>OEM NSC Builds</h3>
                            <p>Modern tech. OEM roots. Built for the future. The ultimate evolution combining legendary reliability with Nickel Silicon Carbide plating technology.</p>
                            <p><strong>Includes:</strong> OEM pistons and rods, NSC plated cylinder bores, upgraded Toda timing chain, balanced and blueprinted assembly.</p>
                            <div class="price-tag">Starting at $5,900</div>
                            <p style="font-size: 0.9rem; margin-top: 0.5rem; color: #666;">(50% deposit required)</p>
                        </div>
                    </div>

                    <div class="engine-card">
                        <div class="engine-card-img" style="background-image: linear-gradient(rgba(0,0,0,0.3), rgba(0,0,0,0.3)), url('https://i.imgur.com/placeholder-frm.jpg'); background-color: #2A2A2A;"></div>
                        <div class="engine-card-content">
                            <h3>OEM Refreshed</h3>
                            <p>All OEM refreshed engines are blueprinted and confirmed to meet original specifications while retaining FRM bores. Only genuine Honda gaskets, seals, and hard parts.</p>
                            <p><strong>F20C:</strong> Short Block $4,800 | Long Block $6,300</p>
                            <p><strong>F22C:</strong> Short Block $5,200 | Long Block $6,700</p>
                            <div class="price-tag">Core Exchange Required</div>
                        </div>
                    </div>
                </div>

                <div class="nsc-info">
                    <h3>What is NSC (Nickel Silicon Carbide)?</h3>
                    <p>We replace the original FRM (Fiber Reinforced Metal) cylinder liners with Nickel Silicon Carbide plating — the same advanced surface technology used in modern supercars and MotoGP engines.</p>
                    <ul class="nsc-benefits">
                        <li>40% stronger than OEM FRM liners</li>
                        <li>20–30% lower friction than factory</li>
                        <li>No sleeves to shift, crack, or wear unevenly</li>
                        <li>Superior heat transfer and ring seal</li>
                    </ul>
                    <p style="margin-top: 2rem; font-weight: 600; color: var(--text-white);">The result is OEM-like reliability, with improved performance and longevity, all while retaining factory drivability.</p>
                </div>
            </div>
        </section>
    </div>

    <!-- TRANSMISSIONS PAGE -->
    <div id="transmissions-page" class="page">
        <section class="hero" style="min-height: 60vh;">
            <div class="container">
                <div class="hero-content">
                    <h1>The Ultimate <span>Manual Transmission</span></h1>
                    <p>New OEM assemblies and WPC-treated perfection. The smoothest shifting experience ever created.</p>
                </div>
            </div>
        </section>

        <section>
            <div class="container">
                <div class="trans-table">
                    <table>
                        <thead>
                            <tr>
                                <th>Stage / Type</th>
                                <th>AP1 Price</th>
                                <th>AP2 Price</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td>Stage 1 Prebuilt</td>
                                <td class="price">$2,400</td>
                                <td class="price">$2,700</td>
                            </tr>
                            <tr>
                                <td>Stage 2 Prebuilt</td>
                                <td class="price">$2,900</td>
                                <td class="price">$3,200</td>
                            </tr>
                            <tr>
                                <td>Stage 3 Prebuilt</td>
                                <td class="price">$4,500</td>
                                <td class="price">$4,800</td>
                            </tr>
                            <tr>
                                <td><strong>*NEW* OEM Assembly</strong></td>
                                <td class="price">$5,900</td>
                                <td class="price">$6,500</td>
                            </tr>
                            <tr class="highlight">
                                <td><strong>Pinnacle S2000 (WPC Treated)</strong></td>
                                <td class="price">$8,400</td>
                                <td class="price">$8,700</td>
                            </tr>
                        </tbody>
                    </table>
                </div>

                <div style="margin-top: 3rem; background: linear-gradient(135deg, var(--card-bg) 0%, var(--secondary-bg) 100%); padding: 2.5rem; border-radius: 12px; border: 1px solid var(--border-color); box-shadow: 0 10px 40px rgba(0, 0, 0, 0.3);">
                    <h3 style="color: var(--accent-red); margin-bottom: 1rem; font-size: 1.8rem;">Additional Services</h3>
                    <p style="color: var(--text-gray); font-size: 1.1rem;">Transmission assembly/blueprinting and repair - <span style="color: var(--accent-red); font-weight: 700;">$1,100 + parts</span></p>
                </div>

                <div style="margin-top: 4rem; background: linear-gradient(135deg, var(--card-bg) 0%, var(--secondary-bg) 100%); padding: 3rem; border-radius: 12px; border-left: 4px solid var(--accent-red); box-shadow: 0 10px 40px rgba(0, 0, 0, 0.3);">
                    <h3 style="color: var(--accent-red); font-size: 2rem; margin-bottom: 1.5rem;">About Our Transmissions</h3>
                    <p style="color: var(--text-gray); line-height: 1.9; margin-bottom: 1.5rem;">Many know the S2000 as having one of the best manual transmissions ever made. Unfortunately, OEM transmission parts have long been discontinued by Honda. However, we have an extensive stock of all new OEM S2000 transmission parts.</p>
                    <p style="color: var(--text-gray); line-height: 1.9;">We offer complete NEW OEM internal assemblies in an original casing. In our quest to continually improve upon the original design, we also offer what we consider the pinnacle of all manual transmissions - A 100% coverage WPC surface treatment to every contact surface within the rotating assembly. This provides the smoothest feeling manual transmission that has ever existed.</p>
                </div>
            </div>
        </section>
    </div>

    <!-- SERVICE PAGE -->
    <div id="service-page" class="page">
        <section class="hero" style="min-height: 60vh;">
            <div class="container">
                <div class="hero-content">
                    <h1>Service & <span>Maintenance</span></h1>
                    <p>S2000 specialist services for all your maintenance needs. From basic service to complete rebuilds.</p>
                </div>
            </div>
        </section>

        <section>
            <div class="container">
                <div class="section-header">
                    <h2>Labor <span>Rates</span></h2>
                </div>

                <div class="labor-rates">
                    <div class="rate-card">
                        <h3>Chassis Work</h3>
                        <div class="rate">$120<span style="font-size: 1.5rem; font-weight: 400;">/hr</span></div>
                    </div>
                    <div class="rate-card">
                        <h3>Engine Work</h3>
                        <div class="rate">$190<span style="font-size: 1.5rem; font-weight: 400;">/hr</span></div>
                    </div>
                </div>

                <div class="section-header" style="margin-top: 4rem;">
                    <h2>Basic <span>Services</span></h2>
                </div>

                <div class="service-list">
                    <div class="service-item">
                        <span>Oil Change</span>
                        <span>$60</span>
                    </div>
                    <div class="service-item">
                        <span>Brake Fluid Flush</span>
                        <span>$120</span>
                    </div>
                    <div class="service-item">
                        <span>Multipoint Inspection</span>
                        <span>$120</span>
                    </div>
                    <div class="service-item">
                        <span>Valve Adjustment</span>
                        <span>$285</span>
                    </div>
                    <div class="service-item">
                        <span>Compression Test</span>
                        <span>$190</span>
                    </div>
                    <div class="service-item">
                        <span>Leak Down Test</span>
                        <span>$285</span>
                    </div>
                    <div class="service-item">
                        <span>Soft Top Replacement</span>
                        <span>$750</span>
                    </div>
                </div>

                <div style="margin-top: 4rem; background: linear-gradient(135deg, var(--card-bg) 0%, var(--secondary-bg) 100%); padding: 3rem; border-radius: 12px; border-left: 4px solid var(--accent-red); box-shadow: 0 10px 40px rgba(0, 0, 0, 0.3);">
                    <h3 style="color: var(--accent-red); font-size: 2rem; margin-bottom: 1.5rem;">S2000 Specialist</h3>
                    <p style="color: var(--text-gray); line-height: 1.9;">Any service your S2000 requires can be completed at our location. From complete engine rebuilds to chassis corner balancing to basic service needs. Contact us to inquire about your specific needs.</p>
                </div>
            </div>
        </section>
    </div>

    <!-- CONFIGURATOR PAGE -->
    <div id="configurator-page" class="page">
        <section class="hero" style="min-height: 60vh;">
            <div class="container">
                <div class="hero-content">
                    <h1>Engine <span>Configurator</span></h1>
                    <p>Build your dream F-Series engine. Select options and see your total in real-time.</p>
                </div>
            </div>
        </section>

        <section>
            <div class="container">
                <div class="configurator-container">
                    <div class="configurator-content">
                        <div class="config-options">
                            <div class="config-section">
                                <h3>Base Engine</h3>
                                <div class="option-group">
                                    <label>Select Your Build</label>
                                    <select id="base-engine">
                                        <option value="10950">Pinnacle 2.3L F-Series - $10,950</option>
                                        <option value="11750">Pinnacle 2.5L F-Series - $11,750</option>
                                        <option value="5900">OEM NSC Shortblock - $5,900</option>
                                        <option value="4800">F20C Short Block - $4,800</option>
                                        <option value="6300">F20C Long Block - $6,300</option>
                                        <option value="5200">F22C Short Block - $5,200</option>
                                        <option value="6700">F22C Long Block - $6,700</option>
                                    </select>
                                </div>
                            </div>

                            <div class="config-section">
                                <h3>Aesthetic Options</h3>
                                <div class="checkbox-group">
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="paint" value="380">
                                        <label for="paint">Engine Painting</label>
                                        <span class="option-price">+$380</span>
                                    </div>
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="valve-cover" value="150">
                                        <label for="valve-cover">Valve Cover Refresh</label>
                                        <span class="option-price">+$150</span>
                                    </div>
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="hardware" value="125">
                                        <label for="hardware">New Girdle, Oil Pan, Chain Case Bolts</label>
                                        <span class="option-price">+$125</span>
                                    </div>
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="flywheel" value="225">
                                        <label for="flywheel">ARP Flywheel Bolts & Spacer</label>
                                        <span class="option-price">+$225</span>
                                    </div>
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="balancer" value="425">
                                        <label for="balancer">Fluidampr Harmonic Balancer (Highly Recommended)</label>
                                        <span class="option-price">+$425</span>
                                    </div>
                                </div>
                            </div>

                            <div class="config-section">
                                <h3>Performance Add-Ons</h3>
                                <div class="checkbox-group">
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="port-match" value="1150">
                                        <label for="port-match">Intake/Exhaust Manifold Port Matching & Quench Pad Optimization</label>
                                        <span class="option-price">+$1,150</span>
                                    </div>
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="cnc-head" value="1300">
                                        <label for="cnc-head">CNC Ported Cylinder Head</label>
                                        <span class="option-price">+$1,300</span>
                                    </div>
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="steel-valves" value="350">
                                        <label for="steel-valves">Steel Valves</label>
                                        <span class="option-price">+$350</span>
                                    </div>
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="ti-valves" value="1400">
                                        <label for="ti-valves">Titanium Valves with Lash Caps (Required >9K RPM)</label>
                                        <span class="option-price">+$1,400</span>
                                    </div>
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="cams" value="1300">
                                        <label for="cams">Stroker or 10K-Spec Cams (Includes Degreeing)</label>
                                        <span class="option-price">+$1,300</span>
                                    </div>
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="springs" value="500">
                                        <label for="springs">Ultra Valve Spring Kit</label>
                                        <span class="option-price">+$500</span>
                                    </div>
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="keepers" value="150">
                                        <label for="keepers">New AP1 Keepers (Required for Upgraded Valvetrain)</label>
                                        <span class="option-price">+$150</span>
                                    </div>
                                </div>
                            </div>

                            <div class="config-section">
                                <h3>Intake & Exhaust</h3>
                                <div class="checkbox-group">
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="header-charper" value="1100">
                                        <label for="header-charper">Charper Spec Header w/ 2.5" Collector</label>
                                        <span class="option-price">+$1,100</span>
                                    </div>
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="header-custom" value="1500">
                                        <label for="header-custom">Custom Header w/ 2.5" Collector</label>
                                        <span class="option-price">+$1,500</span>
                                    </div>
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="collector-3" value="200">
                                        <label for="collector-3">Upgrade to 3" Collector</label>
                                        <span class="option-price">+$200</span>
                                    </div>
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="header-lightweight" value="1200">
                                        <label for="header-lightweight">Superlight 321 Stainless Header</label>
                                        <span class="option-price">+$1,200</span>
                                    </div>
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="itbs" value="1950">
                                        <label for="itbs">AT Power ITBs</label>
                                        <span class="option-price">+$1,950</span>
                                    </div>
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="map-block" value="350">
                                        <label for="map-block">MAP Block</label>
                                        <span class="option-price">+$350</span>
                                    </div>
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="filter-kit" value="200">
                                        <label for="filter-kit">Filter Kit</label>
                                        <span class="option-price">+$200</span>
                                    </div>
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="injectors" value="600">
                                        <label for="injectors">ID1050X Injectors</label>
                                        <span class="option-price">+$600</span>
                                    </div>
                                </div>
                            </div>

                            <div class="config-section">
                                <h3>Dry Sump / Oil System</h3>
                                <div class="checkbox-group">
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="dry-sump" value="3900">
                                        <label for="dry-sump">Daily Engineering Dry Sump System</label>
                                        <span class="option-price">+$3,900</span>
                                    </div>
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="oil-package" value="1800">
                                        <label for="oil-package">Oil Tank, Radiator, and Cooler Package</label>
                                        <span class="option-price">+$1,800</span>
                                    </div>
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="oil-lines" value="300">
                                        <label for="oil-lines">Oil Lines</label>
                                        <span class="option-price">+$300</span>
                                    </div>
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="oil-filter" value="300">
                                        <label for="oil-filter">Peterson Oil Line Filter</label>
                                        <span class="option-price">+$300</span>
                                    </div>
                                    <div class="checkbox-item">
                                        <input type="checkbox" id="ac-bracket" value="325">
                                        <label for="ac-bracket">Optional AC/Alternator Bracket</label>
                                        <span class="option-price">+$325</span>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <div class="config-summary">
                            <h3>Build Summary</h3>
                            <div id="summary-list">
                                <div class="summary-item">
                                    <span>Base Engine</span>
                                    <span id="base-price">$10,950</span>
                                </div>
                                <div class="summary-item">
                                    <span>Options Total</span>
                                    <span id="options-total">$0</span>
                                </div>
                                <div class="summary-item total">
                                    <span>Total Price</span>
                                    <span id="total-price">$10,950</span>
                                </div>
                            </div>
                            <div style="margin-top: 2rem;">
                                <a href="#" data-page="contact" class="btn" style="width: 100%; text-align: center;">REQUEST QUOTE</a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- CONTACT PAGE -->
    <div id="contact-page" class="page">
        <section class="hero" style="min-height: 60vh;">
            <div class="container">
                <div class="hero-content">
                    <h1>Get In <span>Touch</span></h1>
                    <p>Contact us to discuss your S2000 build or service needs.</p>
                </div>
            </div>
        </section>

        <section>
            <div class="container">
                <div class="contact-content">
                    <div class="contact-info">
                        <h3>Contact Information</h3>
                        <div class="info-item">
                            <strong>Location</strong>
                            <p>Maryville, TN</p>
                            <p style="font-size: 1rem;">(Just south of Knoxville)</p>
                        </div>
                        <div class="info-item">
                            <strong>Phone</strong>
                            <p><a href="tel:865-268-4382">865-268-4382</a></p>
                        </div>
                        <div class="info-item">
                            <strong>Email</strong>
                            <p><a href="mailto:Sales@Charperbuilt.com">Sales@Charperbuilt.com</a></p>
                        </div>
                    </div>

                    <div class="contact-form">
                        <form id="contact-form">
                            <div class="form-group">
                                <label>Name</label>
                                <input type="text" required>
                            </div>
                            <div class="form-group">
                                <label>Email</label>
                                <input type="email" required>
                            </div>
                            <div class="form-group">
                                <label>Phone</label>
                                <input type="tel">
                            </div>
                            <div class="form-group">
                                <label>Message</label>
                                <textarea required></textarea>
                            </div>
                            <button type="submit" class="btn">SEND MESSAGE</button>
                        </form>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- Footer -->
    <footer>
        <div class="container">
            <p>&copy; 2025 Charper Built. All rights reserved. S2000 Performance Specialists.</p>
        </div>
    </footer>

    <script>
        // Page Navigation
        const pages = document.querySelectorAll('.page');
        const navLinks = document.querySelectorAll('nav a');

        function showPage(pageName) {
            pages.forEach(page => {
                page.classList.remove('active');
            });
            
            const targetPage = document.getElementById(`${pageName}-page`);
            if (targetPage) {
                targetPage.classList.add('active');
                window.scrollTo(0, 0);
            }

            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.dataset.page === pageName) {
                    link.classList.add('active');
                }
            });
        }

        navLinks.forEach(link => {
            link.addEventListener('click', (e) => {
                e.preventDefault();
                const pageName = link.dataset.page;
                showPage(pageName);
            });
        });

        // Configurator Functionality
        const baseEngineSelect = document.getElementById('base-engine');
        const checkboxes = document.querySelectorAll('.checkbox-item input[type="checkbox"]');
        const basePriceEl = document.getElementById('base-price');
        const optionsTotalEl = document.getElementById('options-total');
        const totalPriceEl = document.getElementById('total-price');

        function updatePrice() {
            let basePrice = parseInt(baseEngineSelect.value);
            let optionsTotal = 0;

            checkboxes.forEach(checkbox => {
                if (checkbox.checked) {
                    optionsTotal += parseInt(checkbox.value);
                }
            });

            let totalPrice = basePrice + optionsTotal;

            basePriceEl.textContent = `${basePrice.toLocaleString()}`;
            optionsTotalEl.textContent = `${optionsTotal.toLocaleString()}`;
            totalPriceEl.textContent = `${totalPrice.toLocaleString()}`;
        }

        baseEngineSelect.addEventListener('change', updatePrice);
        checkboxes.forEach(checkbox => {
            checkbox.addEventListener('change', updatePrice);
        });

        // Form Submission
        document.getElementById('contact-form').addEventListener('submit', (e) => {
            e.preventDefault();
            alert('Thank you for your message! We will get back to you soon.');
            e.target.reset();
        });
    </script>
</body>
</html>
