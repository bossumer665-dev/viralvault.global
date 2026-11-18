<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Viral Vault | The Ultimate Trending Store</title>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@700;900&family=Montserrat:ital,wght@0,400;0,600;0,700;0,800;1,700&display=swap" rel="stylesheet">
    <!-- Font Awesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        :root {
            --bg-dark: #06070a;
            --card-bg: #11131a;
            --accent-pink: #fe2c55;
            --accent-gold: #ffd700;
            --verified-blue: #20d5ec;
            --text-main: #ffffff;
            --text-muted: #b0b3b8;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: var(--bg-dark);
            color: var(--text-main);
            font-family: 'Montserrat', sans-serif;
            overflow-x: hidden;
            background-image: 
                radial-gradient(circle at 80% 10%, rgba(30, 80, 160, 0.25) 0%, transparent 50%),
                radial-gradient(circle at 20% 40%, rgba(255, 255, 255, 0.03) 0%, transparent 40%);
        }

        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 20px;
        }

        /* --- TOP PROFILE SECTION --- */
        .profile-header {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: space-between;
            padding: 30px 10px;
            position: relative;
            gap: 20px;
        }

        .profile-left {
            display: flex;
            align-items: center;
            gap: 25px;
            flex-wrap: wrap;
        }

        .avatar-ring {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background: radial-gradient(circle, #1a1d24 60%, #000 100%);
            border: 3px solid #ffffff;
            box-shadow: 0 0 25px rgba(255, 255, 255, 0.4), inset 0 0 15px rgba(255,255,255,0.2);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
        }

        .avatar-ring .crown-icon {
            color: #d4af37;
            font-size: 1.4rem;
            margin-bottom: -5px;
        }

        .avatar-ring .v-logo {
            font-family: 'Cinzel', serif;
            font-size: 3.2rem;
            font-weight: 900;
            background: linear-gradient(180deg, #ffffff 0%, #8e9eab 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            line-height: 1;
        }

        .avatar-ring span {
            font-size: 0.7rem;
            font-weight: 800;
            letter-spacing: 2px;
            color: #d1d5db;
        }

        .profile-info h1 {
            font-size: 2rem;
            font-weight: 800;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .verified-badge {
            color: var(--verified-blue);
            font-size: 1.3rem;
        }

        .handle {
            color: var(--text-muted);
            font-size: 1rem;
            margin-bottom: 12px;
            font-weight: 600;
        }

        .bio-list {
            list-style: none;
            font-size: 0.95rem;
            line-height: 1.6;
            margin-bottom: 18px;
        }

        .action-buttons {
            display: flex;
            gap: 10px;
        }

        .btn {
            padding: 10px 24px;
            border-radius: 6px;
            font-weight: 700;
            font-size: 0.95rem;
            cursor: pointer;
            border: none;
            transition: transform 0.2s, opacity 0.2s;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            text-decoration: none;
        }

        .btn:hover {
            transform: translateY(-2px);
            opacity: 0.9;
        }

        .btn-follow {
            background-color: var(--accent-pink);
            color: white;
        }

        .btn-secondary {
            background-color: #25272c;
            color: white;
        }

        .slogan-box {
            text-align: right;
            transform: rotate(-8deg);
            padding: 15px;
        }

        .slogan-box p {
            font-size: 1.6rem;
            font-weight: 700;
            font-style: italic;
            line-height: 1.2;
            text-shadow: 0 4px 15px rgba(0, 150, 255, 0.5);
        }

        /* --- HERO BANNER --- */
        .hero-banner {
            text-align: center;
            padding: 40px 10px 25px;
            position: relative;
        }

        .hero-crown {
            font-size: 2.2rem;
            background: linear-gradient(180deg, #fff6b7 0%, #d4af37 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: -10px;
            display: block;
        }

        .metallic-title {
            font-family: 'Cinzel', serif;
            font-size: clamp(2.5rem, 6vw, 4.5rem);
            font-weight: 900;
            letter-spacing: 4px;
            background: linear-gradient(180deg, #ffffff 0%, #c0c0c0 45%, #6e6e6e 50%, #e0e0e0 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            filter: drop-shadow(0 0 15px rgba(212, 175, 55, 0.3));
            position: relative;
            display: inline-block;
        }

        .subtitle {
            letter-spacing: 6px;
            font-size: 0.9rem;
            font-weight: 700;
            color: #e2e8f0;
            margin-top: 5px;
            text-transform: uppercase;
        }

        /* --- TRUST BAR --- */
        .trust-bar {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
            gap: 15px;
            padding: 20px 0;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            margin-bottom: 30px;
        }

        .trust-item {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
            font-size: 0.85rem;
            font-weight: 600;
        }

        .trust-item i {
            font-size: 1.5rem;
            color: #e2e8f0;
        }

        .trust-item i.fa-bolt {
            color: var(--accent-gold);
        }

        /* --- PRODUCT GRID --- */
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(290px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
        }

        .product-card {
            position: relative;
            height: 250px;
            border-radius: 12px;
            overflow: hidden;
            border: 1px solid rgba(255, 255, 255, 0.25);
            background-color: var(--card-bg);
            cursor: pointer;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            text-decoration: none;
            color: white;
            display: block;
        }

        .product-card:hover {
            transform: translateY(-6px);
            box-shadow: 0 10px 25px rgba(32, 213, 236, 0.25);
            border-color: var(--verified-blue);
        }

        .product-card img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
            filter: brightness(0.85);
        }

        .product-card:hover img {
            transform: scale(1.08);
            filter: brightness(1);
        }

        .card-overlay {
            position: absolute;
            inset: 0;
            background: linear-gradient(180deg, transparent 40%, rgba(0, 0, 0, 0.9) 100%);
            display: flex;
            flex-direction: column;
            justify-content: flex-end;
            align-items: flex-end;
            padding: 18px;
            text-align: right;
        }

        .card-title {
            font-size: 1.05rem;
            font-weight: 800;
            text-transform: uppercase;
            transform: rotate(-6deg);
            text-shadow: 2px 2px 6px #000;
            line-height: 1.2;
        }

        .card-tagline {
            font-size: 0.85rem;
            font-weight: 700;
            font-style: italic;
            color: var(--accent-gold);
            transform: rotate(-6deg);
            margin-top: 4px;
            text-shadow: 1px 1px 4px #000;
        }

        /* --- FOOTER --- */
        footer {
            text-align: center;
            padding: 30px 10px 50px;
        }

        .footer-cta {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
            margin-bottom: 8px;
        }

        .footer-line {
            height: 2px;
            width: 80px;
            background: linear-gradient(90deg, transparent, #ffffff, transparent);
        }

        .footer-cta h2 {
            font-size: clamp(1.4rem, 4vw, 2rem);
            font-weight: 800;
            font-style: italic;
            letter-spacing: 2px;
        }

        .footer-cta i {
            color: var(--accent-gold);
        }

        .footer-sub {
            letter-spacing: 5px;
            font-size: 0.8rem;
            color: var(--text-muted);
            font-weight: 600;
        }

        /* Responsive Tweaks */
        @media (max-width: 768px) {
            .profile-header {
                justify-content: center;
                text-align: center;
            }
            .profile-left {
                justify-content: center;
            }
            .profile-info h1, .action-buttons {
                justify-content: center;
            }
            .slogan-box {
                text-align: center;
                transform: rotate(0deg);
                width: 100%;
            }
        }
    </style>
</head>
<body>

    <div class="container">
        <!-- Profile Header -->
        <header class="profile-header">
            <div class="profile-left">
                <div class="avatar-ring">
                    <i class="fa-solid fa-crown crown-icon"></i>
                    <div class="v-logo">V</div>
                    <span>VIRAL<br>VAULT</span>
                </div>

                <div class="profile-info">
                    <h1>Viral Vault <i class="fa-solid fa-circle-check verified-badge"></i></h1>
                    <p class="handle">@viralvault.global</p>
                    <ul class="bio-list">
                        <li>🌎 Trending products worldwide</li>
                        <li>🔥 Viral finds & must-haves</li>
                        <li>🛍️ Shop the latest trends</li>
                        <li>🚀 Bringing trends to your world 🌍</li>
                    </ul>
                    <div class="action-buttons">
                        <a href="#products" class="btn btn-follow" id="followBtn">
                            <i class="fa-solid fa-user-plus"></i> Follow
                        </a>
                        <a href="mailto:contact@viralvault.global" class="btn btn-secondary">Message</a>
                        <button class="btn btn-secondary" aria-label="More options">
                            <i class="fa-solid fa-chevron-down"></i>
                        </button>
                    </div>
                </div>
            </div>

            <div class="slogan-box">
                <p>Shop<br>Smarter.<br>Live Trendier.</p>
            </div>
        </header>

        <!-- Hero Metallic Banner -->
        <section class="hero-banner">
            <i class="fa-solid fa-crown hero-crown"></i>
            <h2 class="metallic-title">VIRAL VAULT</h2>
            <p class="subtitle">The Ultimate Trending Store</p>
        </section>

        <!-- Trust Badges -->
        <section class="trust-bar">
            <div class="trust-item">
                <i class="fa-solid fa-globe"></i>
                <span>Worldwide<br>Shipping</span>
            </div>
            <div class="trust-item">
                <i class="fa-solid fa-shield-halved"></i>
                <span>Secure<br>Payments</span>
            </div>
            <div class="trust-item">
                <i class="fa-solid fa-bolt"></i>
                <span>Fast<br>Delivery</span>
            </div>
            <div class="trust-item">
                <i class="fa-solid fa-bag-shopping"></i>
                <span>Shop<br>Now</span>
            </div>
        </section>

        <!-- 6-Card Product Grid -->
        <main class="product-grid" id="products">
            <!-- Card 1 -->
            <a href="#" class="product-card">
                <img src="https://images.unsplash.com/photo-1532693322450-2cb5c511067d?auto=format&fit=crop&w=600&q=80" alt="Magnetic Levitation Lamp">
                <div class="card-overlay">
                    <h3 class="card-title">Magnetic<br>Levitation Lamp</h3>
                    <span class="card-tagline">It really floats!</span>
                </div>
            </a>

            <!-- Card 2 -->
            <a href="#" class="product-card">
                <img src="https://images.unsplash.com/photo-1485827404703-89b55fcc595e?auto=format&fit=crop&w=600&q=80" alt="Spider Robot">
                <div class="card-overlay">
                    <h3 class="card-title">Spider Robot</h3>
                    <span class="card-tagline">Creepy & Cool!</span>
                </div>
            </a>

            <!-- Card 3 -->
            <a href="#" class="product-card">
                <img src="https://images.unsplash.com/photo-1587202372775-e229f172b9d7?auto=format&fit=crop&w=600&q=80" alt="Mini Transparent PC">
                <div class="card-overlay">
                    <h3 class="card-title">Mini<br>Transparent PC</h3>
                    <span class="card-tagline">A PC in your hand!</span>
                </div>
            </a>

            <!-- Card 4 -->
            <a href="#" class="product-card">
                <img src="https://images.unsplash.com/photo-1584622650111-993a426fbf0a?auto=format&fit=crop&w=600&q=80" alt="Gravity-Defying Water Faucet">
                <div class="card-overlay">
                    <h3 class="card-title">Gravity-Defying<br>Water Faucet</h3>
                    <span class="card-tagline">Water that floats?!</span>
                </div>
            </a>

            <!-- Card 5 -->
            <a href="#" class="product-card">
                <img src="https://images.unsplash.com/photo-1508614589041-895b88991e3e?auto=format&fit=crop&w=600&q=80" alt="Flying Car Drone">
                <div class="card-overlay">
                    <h3 class="card-title">Flying Car Drone</h3>
                    <span class="card-tagline">Drive... or Fly?</span>
                </div>
            </a>

            <!-- Card 6 -->
            <a href="#" class="product-card">
                <img src="https://images.unsplash.com/photo-1617038220319-276d3cfab638?auto=format&fit=crop&w=600&q=80" alt="Smart Ring">
                <div class="card-overlay">
                    <h3 class="card-title">Smart Ring</h3>
                    <span class="card-tagline">Control everything!</span>
                </div>
            </a>
        </main>

        <!-- Footer -->
        <footer>
            <div class="footer-cta">
                <div class="footer-line"></div>
                <h2><i class="fa-solid fa-crown"></i> FOLLOW NOW</h2>
                <div class="footer-line"></div>
            </div>
            <p class="footer-sub">FOR MORE VIRAL ITEMS!</p>
        </footer>
    </div>

    <!-- Simple Interactive Follow Button Script -->
    <script>
        const followBtn = document.getElementById('followBtn');
        let isFollowing = false;

        followBtn.addEventListener('click', (e) => {
            e.preventDefault();
            isFollowing = !isFollowing;
            if (isFollowing) {
                followBtn.innerHTML = '<i class="fa-solid fa-check"></i> Following';
                followBtn.style.backgroundColor = '#25272c';
            } else {
                followBtn.innerHTML = '<i class="fa-solid fa-user-plus"></i> Follow';
                followBtn.style.backgroundColor = '#fe2c55';
            }
        });
    </script>
</body>
</html>
