# Khudi.html<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Pami and Khudi Tiffin Services</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;800&display=swap" rel="stylesheet">
    <style>
        /* --- MODERN "GLASS" THEME --- */
        :root {
            --primary: #FF416C; 
            --bg-gradient: linear-gradient(120deg, #f6d365 0%, #fda085 100%);
            --glass: rgba(255, 255, 255, 0.9);
            --glass-border: rgba(255, 255, 255, 0.5);
            --text-dark: #2d3436;
            --student: #FF9F43;
            --worker: #2e86de;
        }

        body { 
            font-family: 'Montserrat', sans-serif; 
            margin: 0; 
            padding: 0; 
            background: var(--bg-gradient); 
            background-attachment: fixed;
            color: var(--text-dark); 
            padding-bottom: 90px;
            min-height: 100vh;
        }
        
        /* HEADER */
        header { 
            background: var(--glass);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            padding: 20px; 
            text-align: center; 
            border-bottom: 1px solid var(--glass-border);
            position: sticky; top: 0; z-index: 1000;
            box-shadow: 0 4px 30px rgba(0, 0, 0, 0.05);
        }
        .brand-name { font-size: 20px; font-weight: 800; color: #d63031; text-transform: uppercase; letter-spacing: 1px; line-height: 1.2; }
        .location-tag { font-size: 11px; color: #555; background: rgba(0,0,0,0.05); padding: 4px 12px; border-radius: 20px; display: inline-block; margin-top: 5px; font-weight: 600; }

        /* SLIDESHOW */
        .slider-container { width: 92%; margin: 20px auto; border-radius: 20px; overflow: hidden; box-shadow: 0 10px 25px rgba(0,0,0,0.2); }
        .slider-wrapper { display: flex; transition: transform 0.5s ease-in-out; }
        .slide img { width: 100%; height: 200px; object-fit: cover; }

        /* CARDS */
        .card { 
            background: var(--glass); 
            margin: 15px 15px 25px 15px; 
            padding: 25px; 
            border-radius: 25px; 
            box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.1);
            border: 1px solid var(--glass-border);
            animation: floatUp 0.6s ease-out;
            position: relative;
        }
        @keyframes floatUp { from { opacity: 0; transform: translateY(30px); } to { opacity: 1; transform: translateY(0); } }

        h2 { margin: 0 0 10px 0; font-size: 18px; font-weight: 800; color: #2d3436; }
        p { font-size: 13px; color: #636e72; line-height: 1.6; margin: 0; }

        /* CATEGORY BUTTONS */
        .category-row { display: flex; gap: 15px; padding: 0 15px; }
        .cat-btn { 
            flex: 1; background: var(--glass); padding: 20px; border-radius: 20px; text-align: center; 
            box-shadow: 0 5px 15px rgba(0,0,0,0.05); border: 1px solid white; transition: transform 0.2s;
        }
        .cat-btn:active { transform: scale(0.95); }
        .cat-icon { font-size: 32px; margin-bottom: 5px; display: block; }
        .cat-title { font-size: 12px; font-weight: 800; text-transform: uppercase; }

        /* MENU ITEMS */
        .menu-list { margin-top: 15px; }
        .menu-item { display: flex; align-items: center; padding: 12px 0; border-bottom: 1px solid rgba(0,0,0,0.05); color: #444; font-size: 14px; font-weight: 600; }
        .menu-icon { margin-right: 12px; font-size: 18px; background: #ffeaa7; padding: 5px; border-radius: 8px; }

        /* SUBSCRIPTION TICKET */
        .ticket {
            background: linear-gradient(135deg, #ee5253, #ff9f43); color: white; padding: 25px; border-radius: 20px; text-align: center; position: relative;
            box-shadow: 0 10px 20px rgba(238, 82, 83, 0.3); overflow: hidden;
        }
        .ticket-circle { position: absolute; width: 20px; height: 20px; background: #f6d365; border-radius: 50%; top: 50%; margin-top: -10px; }
        .ticket-left { left: -10px; } .ticket-right { right: -10px; }
        .price-tag { font-size: 42px; font-weight: 800; margin: 5px 0; text-shadow: 2px 2px 0 rgba(0,0,0,0.1); }
        .price-sub { font-size: 12px; opacity: 0.9; font-weight: 600; letter-spacing: 1px; text-transform: uppercase; }

        /* BUTTONS */
        .btn-autopay {
            display: block; background: #2d3436; color: white; text-decoration: none; padding: 15px; border-radius: 12px; text-align: center; font-weight: 800; margin-top: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2); position: relative; overflow: hidden;
        }
        .btn-autopay::after { content: "⚡ AUTO-RENEW"; position: absolute; top: 5px; right: 5px; font-size: 8px; background: #00b894; padding: 2px 6px; border-radius: 4px; }
        
        .btn-buy-tiffin {
            display: block; width: 100%; background: linear-gradient(to right, #11998e, #38ef7d); color: white; text-align: center; padding: 10px; border-radius: 50px; text-decoration: none; font-weight: 700; margin-top: 10px; box-sizing: border-box;
        }

        /* TIFFIN BOX PRODUCT CARD STYLE */
        .product-flex { display: flex; align-items: center; gap: 15px; }
        .product-img { width: 80px; height: 80px; border-radius: 15px; object-fit: cover; border: 2px solid white; box-shadow: 0 4px 10px rgba(0,0,0,0.1); }

        /* BOTTOM NAV */
        .nav-pill { 
            position: fixed; bottom: 20px; left: 50%; transform: translateX(-50%); width: 85%; background: #2d3436; border-radius: 50px; 
            display: flex; justify-content: space-around; padding: 12px 20px; box-shadow: 0 10px 30px rgba(0,0,0,0.3); z-index: 999; 
        }
        .nav-item { color: #b2bec3; font-size: 20px; cursor: pointer; transition: 0.3s; position: relative; }
        .nav-item.active { color: #ff9f43; transform: scale(1.2); }
        .nav-item.active::after { content: ''; position: absolute; bottom: -5px; left: 50%; transform: translateX(-50%); width: 4px; height: 4px; background: #ff9f43; border-radius: 50%; }

        .page { display: none; } .page.active { display: block; }
    </style>
</head>
<body>

    <header>
        <div class="brand-name">Pami and Khudi<br>Tiffin Services</div>
        <div class="location-tag">📍 Niyamagiri Vedanta Nagar</div>
    </header>

    <div id="home" class="page active">
        <div class="slider-container">
            <div class="slider-wrapper" id="slider">
                <div class="slide"><img src="https://images.unsplash.com/photo-1565557623262-b51c2513a641?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Tasty Food"></div>
                <div class="slide"><img src="https://images.unsplash.com/photo-1606491956991-2f1b62f6b0f5?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Lunch Box"></div>
            </div>
        </div>

        <div class="card">
            <h2>👋 Welcome!</h2>
            <p>Delicious, home-cooked meals delivered with love. Now simpler and more affordable.</p>
        </div>

        <div class="category-row">
            <div class="cat-btn" onclick="showPage('students', document.getElementById('nav-student'))">
                <span class="cat-icon">🎒</span>
                <span class="cat-title" style="color: var(--student)">Students</span>
            </div>
            <div class="cat-btn" onclick="showPage('workers', document.getElementById('nav-worker'))" style="opacity: 0.7;">
                <span class="cat-icon">🏭</span>
                <span class="cat-title" style="color: var(--worker)">Workers</span>
            </div>
        </div>
    </div>

    <div id="students" class="page">
        <div class="card" style="background: #fff3cd; border-color: #ffeeba; padding: 15px;">
            <div style="font-weight: 800; color: #856404; font-size: 12px; margin-bottom: 5px;">⚠️ PLEASE NOTE</div>
            <p style="color: #856404; font-size: 12px;">Bring your own tiffin box. Stick a name label on it before depositing.</p>
        </div>

        <div class="card" style="border: 2px solid #38ef7d;">
            <div style="position: absolute; top: -10px; right: -10px; background: #38ef7d; color: #000; font-size: 10px; font-weight: 800; padding: 5px 10px; border-radius: 20px;">NEED ONE?</div>
            <h2 style="font-size: 14px;">🛍️ Buy Premium Tiffin Box</h2>
            <div class="product-flex" style="margin-top: 15px;">
                <img src="https://images.unsplash.com/photo-1606491956689-2ea28c674456?ixlib=rb-4.0.3&auto=format&fit=crop&w=200&q=80" class="product-img">
                <div>
                    <div style="font-size: 12px; color: #666;">4-Tier Steel Carrier</div>
                    <div style="font-size: 20px; font-weight: 800; color: #2d3436;">₹500 <span style="font-size: 10px; font-weight: 400;">/ One Time</span></div>
                </div>
            </div>
            <a href="upi://pay?pa=9348854171@ybl&pn=PamiKhudiTiffin&am=500&cu=INR" class="btn-buy-tiffin">
                Pay ₹500 & Buy Tiffin
            </a>
        </div>

        <div class="card">
            <h2>🎒 Student Lunch Menu</h2>
            <div class="menu-list">
                <div class="menu-item"><span class="menu-icon">🥘</span> Healthy Veg Thali</div>
                <div class="menu-item"><span class="menu-icon">🥚</span> Egg Rice (Wed/Sat)</div>
                <div class="menu-item"><span class="menu-icon">🥕</span> Seasonal Green Veg</div>
            </div>
        </div>

        <div class="card">
            <h2>📅 Monthly Subscription</h2>
            
            <div class="ticket">
                <div class="ticket-circle ticket-left"></div>
                <div class="ticket-circle ticket-right"></div>
                <div class="price-sub">Student Lunch Pass</div>
                <div class="price-tag">₹1300</div>
                <div style="font-size: 12px; opacity: 0.8;">Per Month • 26 Days</div>
            </div>

            <a href="upi://pay?pa=9348854171@ybl&pn=PamiKhudiTiffin&am=1300&cu=INR" class="btn-autopay">
                Activate Subscription (₹1300)
                <div style="font-size: 10px; font-weight: 400; margin-top: 5px; opacity: 0.7;">Tap to pay via PhonePe/GPay</div>
            </a>
            
            <div style="text-align: center; margin-top: 15px;">
                <a href="https://wa.me/919348854171?text=Hi%20Pami%20and%20Khudi,%20I%20have%20paid%201300%20for%20subscription" style="color: #2d3436; font-size: 11px; text-decoration: none; font-weight: 600;">
                    Need Help? Chat on WhatsApp
                </a>
            </div>
        </div>
    </div>

    <div id="workers" class="page">
        <div class="card">
            <div style="text-align: center; padding: 20px;">
                <span style="font-size: 40px;">🚧</span>
                <h2>Coming Soon</h2>
                <p>We are updating the menu for Vedanta Workers.</p>
                <a href="https://wa.me/919348854171" style="display:inline-block; margin-top:15px; color:var(--worker); font-weight:bold; text-decoration:none;">Get Notified &rarr;</a>
            </div>
        </div>
    </div>

    <div class="nav-pill">
        <div class="nav-item active" id="nav-home" onclick="showPage('home', this)">🏠</div>
        <div class="nav-item" id="nav-student" onclick="showPage('students', this)">🎒</div>
        <div class="nav-item" id="nav-worker" onclick="showPage('workers', this)">🏭</div>
    </div>

    <script>
        function showPage(pageId, element) {
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.getElementById(pageId).classList.add('active');
            
            document.querySelectorAll('.nav-item').forEach(i => i.classList.remove('active'));
            if(element) element.classList.add('active');
            
            window.scrollTo(0, 0);
        }
        
        let slideIndex = 0;
        const slides = document.querySelectorAll('.slide');
        const slider = document.getElementById('slider');
        function showSlides() {
            slideIndex++;
            if (slideIndex >= slides.length) slideIndex = 0;
            slider.style.transform = `translateX(-${slideIndex * 100}%)`;
        }
        setInterval(showSlides, 3000);
    </script>
</body>
</html>
